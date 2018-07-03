---
title: 'Tutorial: Desensamblador de archivo sin formato con un encabezado y finalizador | Microsoft Docs'
description: Utilice al Asistente para esquemas de archivo sin formato para crear un esquema de encabezado, el esquema de finalizador y el esquema de cuerpo y, a continuación, desensamblar un archivo sin formato de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715af9cc-d718-483d-b593-64462aa5a58b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a39361e4da6dec9acf023911466f07572a3de13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983917"
---
# <a name="walkthrough-flat-file-disassembly-using-a-header-and-trailer"></a>Tutorial: Desensamblador de archivo sin formato con un encabezado y finalizador

## <a name="overview"></a>Información general
En este tutorial se muestra el uso de esquemas creados por el Asistente para esquema de archivo sin formato a fin de llevar a cabo el desensamblado de un archivo con un encabezado, un finalizador y un cuerpo de mensaje repetido. En este tutorial se desarrollará parte de un sistema de seguimiento de errores ficticio que cumple con los siguientes requisitos:  
  
- Los mensajes de error se registran en varias ubicaciones físicas de la compañía y se envían a una ubicación central para su procesamiento en varios sistemas de servidor.  
  
- Los mensajes de error se escriben en el formato de archivo sin formato que contiene un encabezado que indica la ubicación, un cuerpo que contiene uno o varios mensajes y un finalizador que indica el número de lote.  
  
- Los mensajes se consideran no válidos si no tienen un encabezado, un cuerpo y un finalizador.  
  
  Cuando se completa un tutorial, es preciso disponer de una aplicación de BizTalk Server que procese archivos sin formatos y los escriba como XML para que lo procese un sistema de servidor.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para este ejemplo, es preciso saber desenvolverse con la creación de proyectos de BizTalk Server, la firma de un ensamblado y el uso de la consola de administración de BizTalk Server para ver aplicaciones y puertos. También debe estar familiarizado con las ideas presentadas en [Tutorial: implementar una aplicación básica de BizTalk](../core/walkthrough-deploying-a-basic-biztalk-application.md). También resultará de utilidad cierta familiaridad de nivel básico con el Asistente para esquemas de archivo sin formato, aunque no constituye un requisito necesario.  
  
## <a name="what-this-example-does"></a>Qué se hace en este ejemplo  
 En este ejemplo, se procesan mensajes de archivo sin formato de entrada mediante una canalización personalizada y el componente Desensamblador de archivo sin formato. Los mensajes se analizan mediante esquemas de cuerpo, finalizador y encabezado y, seguidamente, se escriben en una ubicación de envío para el procesamiento de servidor.  
  
## <a name="example"></a>Ejemplo  
 Para crear el ejemplo, siga los pasos que se especifican en las secciones que se presentan a continuación.  
  
### <a name="create-a-new-biztalk-project"></a>Cree un nuevo proyecto de BizTalk  
 Antes de generar una solución, es preciso crear un proyecto de BizTalk, asegurarse de que se le ha asignado un nombre seguro y un nombre de aplicación. La asignación de un nombre de aplicación evita que BizTalk Server implemente la solución en la aplicación de BizTalk predeterminada.  
  
1. Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para crear un nuevo proyecto de BizTalk. Llame al proyecto **FFDisassemblerWalkthrough**.  
  
2. Genere un archivo de clave y asígnelo al proyecto. Para obtener más información acerca de esta tarea, vea [Signing Page, Project Designer](http://go.microsoft.com/fwlink/?LinkId=125876).  
  
3. En las propiedades de implementación para el proyecto, establezca **nombre de la aplicación** en "FlatFileExample" y establezca **reiniciar instancias de Host** a `True`. Al definir esta marca, se ordena al host que borre todas las instancias del ensamblado almacenadas en caché.  
  
### <a name="create-the-sample-data-file"></a>Crear el archivo de datos del ejemplo  
Antes de generar esquemas, es necesario crear un archivo de prueba.   
  
1.  Inicie Bloc de notas u otro procesador de texto.  
  
2.  Cree un archivo de prueba de ejemplo. El archivo consta de un encabezado que indica la ubicación que informa de los errores, un finalizador con un Id. para este lote y un cuerpo compuesto de uno o varios registros de errores. El formato del archivo es el siguiente:  
  
    ```  
    Location  
    ERRORid|type|priority|description|errorDateTime  
    …additional error records   
    BatchID  
    ```  
  
    El registro de ERROR está etiquetado con el texto "ERROR" y delimitado por el "&#124;" carácter (frente al caso posicional). Los elementos de datos del registro ERROR se describen en la siguiente tabla.  
  
    |Elemento|Tipo de datos|Descripción|  
    |---|---|---|  
    |Id.|integer|ID de este error.|  
    |Tipo|integer|Tipo de error.|  
    |Prioridad|string|Indicador de prioridad: alta, Media o baja.|  
    |Descripción|string|Descripción del error.|  
    |ErrorDateTime|DateTime|Fecha y hora del error.|  
  
    El archivo puede tener uno o varios registros ERROR.  
  
     **--O BIEN--**
  
     Copie los datos de ejemplo siguiente en el nuevo archivo. La última línea contiene un salto de línea al final:
  
    ```  
    East Coast Facility  
    ERROR102|0|High|Sprocket query fails.|1999-05-31T13:20:00.000-05:00  
    ERROR16502|2|Low|Time threshold exceeded.|1999-05-31T13:20:00.000-05:00  
    8675309  
  
    ```  
  
3.  Guarde el nuevo archivo de ejemplo en el directorio del proyecto. Use un nombre descriptivo como "ArchivoErrores.txt" para localizarlo fácilmente.  
  
### <a name="create-and-test-the-header-trailer-and-body-schemas"></a>Crear y probar los esquemas de cuerpo, finalizador y encabezado  
 Una vez creado el archivo de datos del ejemplo, el paso siguiente es crear los esquemas de cuerpo, finalizador y encabezado. Estos esquemas se utilizan con el componente de canalización de recepción Desensamblador de archivos sin formato para procesar mensajes recibidos.  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-header-schema"></a>Utilice al Asistente para esquemas de archivo sin formato para crear el esquema de encabezado  
  
1.  Agregue un nuevo esquema al proyecto. En el Explorador de soluciones, haga clic en **FFDisassemblerWalkthrough**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **archivos de esquema** y seleccione **Asistente para esquemas de archivo sin formato**. Asígnele al nuevo esquema "el nombre Header.xsd" y, a continuación, haga clic en **agregar**.  
  
3.  En el **Bienvenido al Asistente para esquema de BizTalk de planos archivo** página, haga clic en **siguiente**.  
  
4.  En el **información de esquema de archivo sin formato** página, haga clic en **examinar** y busque el archivo de datos de ejemplo que creó anteriormente. Cambiar el **nombre del registro** por "Encabezado", compruebe la página de códigos y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Si se ha guardado el archivo de ejemplo en formato Unicode, la página de código será Little-Endian-UTF16 (1200). Esto no tendrá ninguna repercusión negativa en el ejemplo.  
  
5.  A continuación, seleccione los datos de documento. En el **seleccionar datos del documento** página, resalte la primera línea de datos, incluidos los caracteres de nueva línea {CR} y {LF}, tal como se muestra:  
  
     ![Datos seleccionados para el esquema de encabezado](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")  
  
     Haga clic en **Siguiente**.  
  
6.  En el **Seleccionar formato de registro** página, haga clic en **siguiente** para aceptar el valor predeterminado. Se puede aceptar el valor predeterminado "por símbolo delimitador" porque el archivo de datos no utiliza posición relativa.  
  
7.  En el **registro delimitado** página, haga clic en **siguiente**.  
  
8.  Ahora, podrá especificar elementos secundarios. El encabezado contiene un elemento denominado “Location”.  
  
     ![Nodo ubicación definido para el encabezado](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")  
  
     Para continuar, haga clic en **Siguiente** .  
  
9. En el **vista esquema** , comprueba el esquema.  
  
     ![Esquema de encabezado que muestra la vista de esquema completó](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")  
  
     Cuando esté satisfecho, haga clic en **finalizar** para completar el asistente.  
  
10. Haga clic en el **\<esquema\>** nodo en el panel de esquema de encabezado. En el panel Propiedades, cambie **Element FormDefault** a **Qualified**. Con ello, se indica que el espacio de nombres de destino debe calificar los elementos declarados localmente en un documento de instancia.  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-trailer-schema"></a>Utilice al Asistente para esquemas de archivo sin formato para crear el esquema de finalizador  
  
1.  Agregue un nuevo esquema al proyecto. En el Explorador de soluciones, haga clic en **FFDisassemblerWalkthrough**, apunte a **agregar** y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **archivos de esquema** y seleccione **Asistente para esquemas de archivo sin formato**. Asígnele al nuevo esquema "el nombre Trailer.xsd" y, a continuación, haga clic en **agregar**.  
  
3.  En el **Bienvenido al Asistente para esquema de BizTalk de planos archivo** página, haga clic en **siguiente**.  
  
4.  En el **información de esquema de archivo sin formato** página, haga clic en **examinar** y busque el archivo de datos de ejemplo que creó anteriormente. Cambiar el **nombre del registro** a "Finalizador", compruebe la página de códigos y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Si se ha guardado el archivo de ejemplo en formato Unicode, la página de código será Little-Endian-UTF16 (1200). Esto no tendrá ninguna repercusión negativa en el ejemplo.  
  
5.  A continuación, seleccione los datos de documento. En el **seleccionar datos del documento** página, resalte la última línea de datos, incluidos los caracteres de nueva línea {CR} y {LF}, tal como se muestra:  
  
     ![Datos seleccionados para el esquema de finalizador](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")  
  
     Haga clic en **Siguiente**.  
  
6.  En el **Seleccionar formato de registro** página, haga clic en **siguiente** para aceptar el valor predeterminado. Se puede aceptar el valor predeterminado "por símbolo delimitador" porque el archivo de datos no utiliza posición relativa.  
  
7.  En el **registro delimitado** página, haga clic en **siguiente**.  
  
8.  Ahora, podrá especificar elementos secundarios. El encabezado contiene un elemento denominado “BatchID”.  
  
     ![Nodo ubicación definido para el finalizador](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")  
  
     Para continuar, haga clic en **Siguiente** .  
  
9. En el **vista esquema** , comprueba el esquema.  
  
     ![Esquema de finalizador de vista que muestra completado](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")  
  
     Cuando esté satisfecho, haga clic en **finalizar** para completar el asistente.  
  
10. Haga clic en el **\<esquema\>** nodo en el panel de esquema de finalizador. En el panel Propiedades, cambie **elementFormDefault** a **Qualified**. Con ello, se indica que el espacio de nombres de destino debe calificar los elementos declarados localmente en un documento de instancia.  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-body-schema"></a>Utilice al Asistente para esquemas de archivo sin formato para crear el esquema del cuerpo  
  
1.  Agregue un nuevo esquema al proyecto. En el Explorador de soluciones, haga clic en **FFDisassemblerWalkthrough**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **archivos de esquema** y seleccione **Asistente para esquemas de archivo sin formato**. Asígnele al nuevo esquema "el nombre Body.xsd" y, a continuación, haga clic en **agregar**.  
  
3.  En el **Bienvenido al Asistente para esquema de BizTalk de planos archivo** página, haga clic en **siguiente**.  
  
4.  En el **información de esquema de archivo sin formato** página, haga clic en **examinar** y busque el archivo de datos de ejemplo que creó anteriormente. Cambiar el **nombre del registro** como "Cuerpo", compruebe la página de códigos y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Si se ha guardado el archivo de ejemplo en formato Unicode, la página de código será Little-Endian-UTF16 (1200). Esto no tendrá ninguna repercusión negativa en el ejemplo.  
  
5.  A continuación, seleccione los datos de documento. En el **seleccionar datos del documento** página, resalte dos y tres líneas de datos, incluidos los caracteres de nueva línea {CR} y {LF}, tal como se muestra:  
  
     ![Datos seleccionados para el esquema de cuerpo](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")  
  
     Haga clic en **Siguiente**.  
  
6.  En el **Seleccionar formato de registro** página, haga clic en **siguiente** para aceptar el valor predeterminado. Se puede aceptar el valor predeterminado "por símbolo delimitador" porque el archivo de datos no utiliza posición relativa.  
  
7.  En el **registro delimitado** página, seleccione **siguiente**.  
  
8.  A continuación, defina los elementos secundarios. Cambio **Body_Child1** a **Error**y establezca su tipo de elemento en **repitiendo registro**. Establecer el **Body_Child2** tipo de registro de elemento para **omitir**.  
  
9. En el **vista esquema** página, haga clic en **siguiente** para definir los elementos secundarios del registro de Error.  
  
10. En el **seleccionar datos del documento** página, haga clic en **siguiente**. El Asistente selecciona los datos de definición del registro correctamente.  
  
11. En el **Seleccionar formato de registro** página, haga clic en **siguiente**. El símbolo delimitador da formato a los datos.  
  
12. En el **registro delimitado** página, seleccione **&#124;** para el **delimitador secundario**. A continuación, seleccione el **registro tiene un identificador de etiquetas** casilla de verificación y escriba **ERROR** para el valor de etiqueta.  
  
     ![Configurar registro delimitado con identificador de etiquetas](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")  
  
     Haga clic en **Siguiente**.  
  
13. Ahora, defina los elementos secundarios del registro de errores.  
  
     ![Registro de errores definidos con cinco elementos](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")  
  
     Haga clic en **Siguiente**.  
  
14. En el **vista esquema** , comprueba el esquema.  
  
     ![Esquema de cuerpo de la vista que muestra completado](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")  
  
     Si ha cometido algún error, haga clic en **volver** y realice las correcciones necesarias. Cuando esté satisfecho, haga clic en **finalizar** para completar el asistente.  
  
15. Haga clic en el **\<esquema\>** nodo en el panel de esquema de cuerpo. En el panel Propiedades, cambie **Element FormDefault** a **Qualified**. Con ello, se indica que el espacio de nombres de destino debe calificar los elementos declarados localmente en un documento de instancia.  
  
16. Haga clic en el **\<Error\>** nodo en el panel de esquema de cuerpo. En el panel Propiedades, cambie **Max Occurs** a **1**. Con ello, el Desensamblador de archivos sin formato divide cada uno de los errores en su propio mensaje.  
  
##### <a name="test-the-schemas-using-ffdasm"></a>Probar los esquemas mediante FFDasm  
  
1.  Abra un símbolo del sistema y cambie el directorio al que le corresponde al proyecto.  
  
2.  En el símbolo del sistema, ejecute FFDasm.exe, tal como se muestra a continuación.  
  
    ```  
    <Samples Path>\SDK\Utilities\PipelineTools\FFDasm ErrorFile.txt  -hs header.xsd -bs body.xsd -ts Trailer.xsd  
    ```  
  
     Para obtener información acerca de la ubicación de esta y otras herramientas de canalización, consulte [herramientas de canalización](../core/pipeline-tools.md).  
  
3.  FFDasm.exe debe producir dos archivos de salida denominados {GUID}.xml, uno para cada registro ERROR en el archivo de prueba. El registro ERROR de alta prioridad tiene el aspecto siguiente:  
  
    ```  
    <Body xmlns="http://FFDisassemblerWalkthrough.Body">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <DateTime>1999-05-31T13:20:00.000-05:00</DateTime>  
      </Error>  
    </Body>  
    ```  
  
### <a name="create-a-custom-receive-pipeline"></a>Crear una canalización de recepción personalizada  
 Ahora que están definidos los esquemas de archivo sin formato, será necesario crear una canalización personalizada que utilice el componente Desensamblador de archivos sin formato. Seguidamente, el Desensamblador de archivos sin formato puede configurarse para utilizar los esquemas de finalizador, cuerpo y encabezado para fragmentar mensajes.    
 
1.  Agregue una nueva canalización de recepción al proyecto. En el Explorador de soluciones, haga clic en el **FFDisassemblerWalkthrough** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **archivos de canalización** y, a continuación, haga clic en **canalización de recepción**. Nombre de la nueva canalización "FFReceivePipeline" y, a continuación, haga clic en **agregar**.  
  
3.  Para configurar la nueva canalización, arrastre el componente Desensamblador de archivos sin formato desde el panel Cuadro de herramientas hasta el paso de desensamblado.  
  
4.  En el panel Propiedades, establezca la **esquema de documento** a **como FFDisassemblerWalkthrough.Body**, **esquema de encabezado** a  **Como FFDisassemblerWalkthrough.Header** y **esquema de finalizador** a **como FFDisassemblerWalkthrough.Trailer**.  
  
### <a name="deploy-the-application-and-configure-the-send-and-receive-ports"></a>Implementar la aplicación y configurar los puertos de envío y recepción  
 Con los esquemas y la canalización de recepción personalizada creados, será necesario compilar el proyecto e implementarlo. Una vez implementado, se podrá utilizar la consola de administración de BizTalk Server para configurar los puertos de envío y recepción.  

##### <a name="deploy"></a>Implementar  
1. Desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], implementar la solución con el botón secundario en el proyecto y, a continuación, haciendo clic en **implementar**.  
  
2. Mediante la consola de administración de BizTalk Server, expanda el **aplicaciones** grupo para comprobar que **FlatFileExample** está presente como una aplicación personalizada.  
  
##### <a name="configure-the-receive-port"></a>Configurar el puerto de recepción  
  
1.  Usar el Explorador de Windows para crear un directorio denominado "Receive" en el **FFDisassemblerWalkthrough** directorio del proyecto.  
  
2.  En la consola de administración de BizTalk Server, expanda el **FlatFileExample** aplicación, haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **Unidireccional puerto de recepción**.  
  
3.  En el **propiedades de puerto de recepción** diálogo cuadro, establezca el nombre del puerto "receiveerror"como.  
  
4.  Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New** para agregar una ubicación de recepción. Nombre la nueva ubicación de recepción "ReceiveErrorLocation". Establecer el **canalización de recepción** a **FFReceivePipeline**. Para **tipo de transporte**, seleccione **archivo**y, a continuación, haga clic en **configurar**. Seleccione el directorio de recepción creado y, a continuación, establezca el **máscara de archivo** como *.txt.  
  
5.  Haga clic en **Aceptar**. Con ello, el puerto de recepción debería estar configurado. Haga clic en **Aceptar** para cerrar.  
  
##### <a name="configure-the-send-port"></a>Configurar el puerto de envío  
  
1.  Usar el Explorador de Windows para crear un directorio denominado "Send" en el **FFDisassemblerWalkthrough** directorio del proyecto.  
  
2.  En la consola de administración de BizTalk Server, expanda el **FlatFileExample** aplicación, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **Puerto de envío unidireccional estático...**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, establezca el nombre del puerto de "Envío".  
  
4.  Tipo de transporte, seleccione **archivo**y, a continuación, haga clic en **configurar**. Defina el directorio de envío creado anteriormente como la carpeta de destino.  
  
5.  Ahora, configure el filtro. Haga clic en **filtros** y agregue una expresión:  
  
    -   BTS. MessageType == **http://FFDisassemblerWalkthrough.Body#Body**  
  
6.  Haga clic en **Aceptar** para completar la configuración de puerto de envío. Con ello, el puerto de envío debería estar configurado.  
  
### <a name="run-the-example"></a>Ejecutar el ejemplo  
 Ha llegado el momento de ejecutar el ejemplo. Después de usar la consola de administración de BizTalk Server para iniciar la aplicación, copie los archivos de prueba en la ubicación de recepción y observará lo que se produce en la ubicación de envío.  
  
1.  En la consola de administración de BizTalk Server, haga clic en el **FlatFileExample** aplicación y, a continuación, haga clic en **iniciar**. Esto da de alta e inicia el envío y puertos de recepción.  
  
2.  Suelte la copia del archivo Errorfile.txt de ejemplo en el directorio de recepción. Se deberían escribir dos archivos de salida en el directorio de envío.  
  
