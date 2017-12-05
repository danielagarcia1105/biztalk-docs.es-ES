---
title: "Tutorial: Utilizar sobres XML (básicos) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- content-based routing, promoting properties
- promoting properties, routing messages
- promoting properties, content-based routing
- routing, messages
- routing, promoting properties
ms.assetid: 02d0c596-0cfe-4bae-9f1b-d7dbc17e18a9
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9090c4ee7d576bb7ab610cd81637680d837b2cae
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-using-xml-envelopes-basic"></a>Tutorial: Utilizar sobres XML (básicos)
En este ejemplo se demuestra un desensamblado de sobre XML básico implementando parte de un sistema de seguimiento de errores ficticio. El ejemplo cumple los requisitos siguientes:  
  
1.  Los mensajes de error se registran en varias ubicaciones físicas de la compañía y se envían a una ubicación central para su procesamiento en varios sistemas de servidor.  
  
2.  Los mensajes de error escriben en formato XML.  
  
3.  Un mensaje de error se puede enviar por sí solo, sin sobre, o como un lote contenido en un sobre.  
  
## <a name="prerequisites"></a>Requisitos previos  
 En este ejemplo que debe estar familiarizado con la creación de proyectos de BizTalk, al firmar un ensamblado y, mediante la consola de administración de BizTalk Server para ver las aplicaciones y los puertos. También debe estar familiarizado con las ideas presentadas en [Tutorial: implementar una aplicación básica de BizTalk](../core/walkthrough-deploying-a-basic-biztalk-application.md).  
  
## <a name="what-this-example-does"></a>Qué se hace en este ejemplo  
 En el ejemplo se procesan los mensajes de entrada que contienen un solo mensaje de error o un lote de éstos. Para ello, se define un esquema de sobres y se usa la canalización XmlDisassembler.  
  
## <a name="example"></a>Ejemplo  
 Para crear el ejemplo, siga los pasos que se especifican en las secciones que se presentan a continuación.  
  
### <a name="create-a-new-biztalk-project"></a>Cree un nuevo proyecto de BizTalk  
 Antes de generar una solución, es preciso crear un proyecto de BizTalk, asegurarse de que se le ha asignado un nombre seguro y un nombre de aplicación. La asignación de un nombre de aplicación evita que BizTalk Server implemente la solución en la aplicación de BizTalk predeterminada.  
  
##### <a name="to-create-and-configure-a-new-biztalk-project"></a>Para crear y configurar un nuevo proyecto de BizTalk  
  
1.  Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para crear un nuevo proyecto de BizTalk. Asigne al proyecto el **BasicXMLEnvelope**.  
  
2.  Genere un archivo de clave y asígnelo al proyecto. Para obtener más información acerca de esta tarea, vea [cómo configurar un archivo de clave de ensamblado de nombre seguro](../core/how-to-configure-a-strong-name-assembly-key-file.md).  
  
3.  En las propiedades de configuración de implementación para el proyecto, asigne un **nombre de la aplicación** y establecer **reiniciar instancias de Host** a `True`. Al definir esta marca, se ordena al host que borre todas las instancias del ensamblado almacenadas en caché.  
  
### <a name="create-the-error-schema"></a>Crear el esquema de error  
 En este paso, se creará el esquema de error. Define el mensaje clave para el sistema.  
  
##### <a name="to-create-the-error-schema"></a>Para crear el esquema de error  
  
1.  Agregue un nuevo esquema denominado "Error" al proyecto.  
  
2.  Cambiar el espacio de nombres de destino para el esquema como **http://BasicXMLEnvelope**.  
  
3.  Cambiar la propiedad de esquema **Element FormDefault** en el **avanzadas** categoría a **Qualified**. Con ello, se indica que el espacio de nombres de destino debe calificar los elementos declarados localmente en un documento de instancia.  
  
4.  Cambie el nombre del nodo raíz "Error" y cree cinco elementos secundarios con los tipos que se indican:  
  
    -   ID, xs:int  
  
    -   Type, xs:int  
  
    -   Priority, xs:string  
  
    -   Description, xs:string  
  
    -   ErrorDateTime, xs:string  
  
     El esquema tendrá el siguiente aspecto:  
  
     ![Esquema de Error completado](../core/media/error-schema.gif "error_schema")  
  
5.  Cree un mensaje de ejemplo para este esquema Este mensaje se usa para comprobar que los mensajes sencillos, no contenidos en un sobre, se procesan correctamente. Un mensaje de ejemplo es:  
  
    ```  
    <Error xmlns="http://BasicXMLEnvelope">  
      <ID>1</ID>  
      <Type>5</Type>  
      <Priority>Low</Priority>  
      <Description>Sprocket widget prints reports slowly.</Description>  
      <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
    </Error>  
    ```  
  
     Guarde este mensaje en un archivo en el directorio del proyecto.  
  
### <a name="create-the-envelope-schema"></a>Crear el esquema de sobres  
 El sobre contiene uno o más mensajes de error. En este ejemplo básico, el sobre no tiene propiedades ni elementos propios.  
  
##### <a name="to-create-the-envelope-schema"></a>Para crear el esquema de sobres  
  
1.  Agregue un nuevo esquema denominado "Envelope" al proyecto BasicXMLEnvelope.  
  
2.  Cambiar el espacio de nombres de destino para **http://BasicXMLEnvelope**.  
  
3.  Cambie el nombre del nodo raíz de "Root" a "Envelope".  
  
4.  Ahora, marque el esquema como esquema de sobres. Haga clic en el  **\<esquema\>**  nodo. En el panel Propiedades, establezca la propiedad de referencia de esquema **sobres** a `OK`.  
  
5.  Establecer el **XPath de cuerpo** propiedad. Para ello, haga clic en el **sobres** nodo. En la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) botón en el **XPath de cuerpo** propiedad, seleccione **sobres**y, a continuación, haga clic en **Aceptar**.  
  
6.  Agregue un elemento secundario Cualquier elemento al nodo Envelope. El mensaje de error estará contenido en este elemento. El esquema tendrá el siguiente aspecto:  
  
     ![Esquema de sobre completado](../core/media/envelope-schema.gif "envelope_schema")  
  
7.  Cree un mensaje de ejemplo que contenga un sobre y uno o varios ejemplos de mensajes. Es un mensaje de ejemplo:  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error>  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
     Guarde este mensaje en un archivo en el directorio del proyecto.  
  
### <a name="deploy-and-configure-the-send-and-receive-ports"></a>Implementar y configurar los puertos de envío y recepción  
 Con los esquemas creados, será necesario compilar el proyecto e implementarlo. Una vez implementado, se podrá utilizar la consola de administración de BizTalk Server para configurar los puertos de envío y recepción.  
  
##### <a name="to-deploy-basicxmlenvelope"></a>Para implementar BasicXMLEnvelope  
  
1.  De [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], elija **implementar BasicXMLEnvelope** en el menú Generar. Se generará e implementará en BizTalk Server como la aplicación "BasicXMLEnvelope".  
  
2.  En la consola de administración de BizTalk Server, expanda el **aplicaciones** grupo para comprobar que **BasicXMLEnvelope** está presente como una aplicación personalizada.  
  
##### <a name="to-configure-the-receive-port"></a>Para configurar el puerto de recepción  
  
1.  Utilice el Explorador de Windows para crear un directorio denominado "Receive" en la **BasicXMLEnvelope** directorio del proyecto.  
  
2.  En la consola de administración de BizTalk Server, expanda el **BasicXMLEnvelope** aplicación, haga clic en **puertos de recepción**, seleccione **nuevo**y, a continuación, haga clic en **Unidireccional puerto de recepción**.  
  
3.  En el **propiedades de puerto de recepción** diálogo cuadro, establezca el nombre del puerto de "Recepción".  
  
4.  Haga clic en ubicaciones de recepción y, a continuación, haga clic en **New** para agregar un puerto de recepción. Defina "ReceiveError" como nombre del nuevo puerto. Establecer el **canalización de recepción** a **XMLReceive**. Para **tipo de transporte**, seleccione **archivo**y, a continuación, haga clic en **configurar**.  
  
5.  Seleccione el directorio de recepción creado anteriormente y haga clic en **Aceptar**. Con ello, el puerto de recepción debería estar configurado. Haga clic en **Aceptar** para cerrar.  
  
##### <a name="to-configure-the-send-port"></a>Para configurar el puerto de envío  
  
1.  Utilice el Explorador de Windows para crear un directorio denominado "Send" en la **BasicXMLEnvelope** directorio del proyecto.  
  
2.  En la consola de administración de BizTalk Server, expanda el **BasicXMLEnvelope** aplicación, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en  **Unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, establezca el nombre del puerto de "Envío".  
  
4.  Para **tipo de transporte**, seleccione **archivo**y, a continuación, haga clic en **configurar**. Establece la carpeta de destino en el directorio de envío que creó anteriormente y haga clic en **Aceptar**.  
  
5.  Haga clic en **filtros** y agregue un filtro único:  
  
    -   BTS. MessageType == **http://BasicXMLEnvelope#Error**  
  
6.  Haga clic en **Aceptar** para completar la configuración de puerto de envío. Con ello, el puerto de envío debería estar configurado.  
  
### <a name="run-the-example"></a>Ejecutar el ejemplo  
 Ha llegado el momento de ejecutar el ejemplo. Tras utilizar la consola de administración de BizTalk Server para iniciar la aplicación BasicXMLEnvelope, se copiarán los archivos de prueba en la ubicación de recepción y se observará lo que se produce en la ubicación de envío.  
  
##### <a name="to-run-the-basicxmlenvelope-example"></a>Para ejecutar el ejemplo BasicXMLEnvelope  
  
1.  En la consola de administración de BizTalk Server, haga clic en el **BasicXMLEnvelope** aplicación y, a continuación, haga clic en **iniciar**. Con ello, se darán de alta los puertos de recepción y envío y se iniciarán.  
  
2.  Coloque cada uno de archivos de ejemplo en el directorio de recepción. Si usa los ejemplos facilitados anteriormente, encontrará tres mensajes de error individuales en la ubicación de envío cuando se complete el procesamiento.  
  
## <a name="extending-the-example"></a>Ampliar el ejemplo  
 Puede ampliar el ejemplo para adaptarlo a otros requisitos. En esta sección se tratan dos escenarios comunes.  
  
-   Si se envía un lote de errores dentro de un sobre, los errores en mensajes individuales del desensamblado no deberían prohibir el procesamiento ulterior de los demás mensajes sin errores.  
  
-   Los errores deberán enviarse a distintas ubicaciones según la prioridad del error. Los mensajes de alta prioridad se envían antes, mientras que los demás niveles de prioridad se administran por los canales normales.  
  
 En las siguientes secciones se amplía el ejemplo de modo que incluya estos requisitos.  
  
### <a name="recoverable-interchange-processing"></a>Procesamiento de intercambio recuperable  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]admite el procesamiento de intercambio recuperable. Esta característica permite garantizar que los lotes de mensajes con errores se traten individualmente en el desensamblado, y no como un lote.  
  
##### <a name="to-configure-the-example-for-recoverable-interchange-processing"></a>Para configurar el ejemplo para el procesamiento de intercambio recuperable  
  
1.  En la consola de administración de BizTalk Server, expanda el **BasicXMLEnvelope** aplicación, haga clic en **puertos de recepción**y, a continuación, haga doble clic en el puerto de recepción. Éste es el puerto creado anteriormente.  
  
2.  En el **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **ubicaciones de recepción**. Haga clic en **propiedades** para que aparezca el **propiedades de ubicación de recepción ReceiveError** cuadro de diálogo. Haga clic en el botón de puntos suspensivos (**...** ) botón la **canalización de recepción**.  
  
3.  En el **configurar canalización: XMLReceive** cuadro de diálogo, establezca la **procesamiento de intercambio recuperable** propiedad `True`y, a continuación, haga clic en **Aceptar**.  
  
4.  Haga clic en **Aceptar** para cerrar el **propiedades de la ubicación de recepción** cuadro de diálogo y, a continuación, haga clic en **Aceptar** para cerrar el **propiedades de puerto de recepción** cuadro de diálogo cuadro.  
  
##### <a name="to-create-a-sample-file-and-run-the-example"></a>Para crear un archivo de ejemplo y ejecutar el ejemplo  
  
1.  Para crear un archivo de ejemplo, realice una copia del archivo de ejemplo de sobre creado en el ejemplo, agregue un espacio de nombres inexistente a una de las instancias de error y guarde el archivo:  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails to return any sprockets even though some exist</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error xmlns="http://ThisIsAnError">  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
2.  En la consola de administración de BizTalk Server, haga clic en **aplicaciones** y compruebe que la **BasicXMLEnvelope** aplicación se está ejecutando.  
  
3.  Coloque el mensaje en la ubicación de recepción. Después del procesamiento, deberá encontrar el primer mensaje en la ubicación de envío y el segundo, de baja prioridad, en la cola de suspensión.  
  
### <a name="content-based-routing-cbr"></a>Enrutamiento por contenidos (CBR)  
 También puede utilizar el enrutamiento por contenidos para enrutar mensajes según su contenido. En este escenario, en enrutamiento se basa en la prioridad. Los mensajes con prioridad alta van a una ubicación de envío y los mensajes con prioridad media o baja van a otra.  
  
 Para ampliar el ejemplo, debe completar las tareas siguientes:  
  
1.  Promover la **prioridad** campo del esquema de Error en el proyecto BasicXMLEnvelope. El enrutamiento por contenidos se basa en propiedades promocionadas para enrutar los mensajes. Para obtener más información, consulte [promocionar propiedades](../core/promoting-properties.md).  
  
2.  Cree y configure dos puertos adicionales. Los puertos usan un filtro para garantizar que reciben los mensajes apropiados.  
  
##### <a name="to-promote-the-priority-field-in-the-error-schema"></a>Para promocionar el campo Priority del esquema de error  
  
1.  Con el **BasicXMLEnvelope** proyecto abierto en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el **Error** esquema y expanda el **Error** nodo.  
  
2.  Haga clic en el **prioridad** elemento, seleccione **promover**y, a continuación, haga clic en **promoción rápida**.  
  
3.  Haga clic en **Aceptar** para confirmar la adición de un nuevo esquema de propiedad para las propiedades promocionadas.  
  
4.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, abra el nuevo esquema de propiedades PropertySchema.xsd. Quite "Field1" del esquema.  
  
5.  Vuelva a compilar e implementar la solución. En el menú Generar, elija Implementar BasicXMLEnvelope.  
  
6.  El proyecto se configuró para restablecer la instancia de host cuando se vuelve a implementar la solución. Si lo ha modificado, deberá detener e iniciar el host.  
  
##### <a name="to-configure-the-low-and-medium-priority-send-port"></a>Para configurar el puerto de envío de prioridad media y baja  
  
1.  Utilice el Explorador de Windows para crear un directorio denominado "SendLowMediumPriority" en la **BasicXMLEnvelope** directorio del proyecto.  
  
2.  En la consola de administración de BizTalk Server, expanda el **BasicXMLEnvelope** aplicación, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en  **Unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, establezca el nombre del puerto "SendLowMediumPriority".  
  
4.  Para **tipo de transporte**, seleccione **archivo**y, a continuación, haga clic en **configurar**. Defina el directorio creado anteriormente como la carpeta de destino. Haga clic en **Aceptar** para cerrar.  
  
5.  Haga clic en **filtros** y agregue tres expresiones de filtro:  
  
    -   BTS.MessageType == http://BasicXMLEnvelope#Error And  
  
    -   BasicXMLEnvelope.PropertySchema.Priority == Low Or  
  
    -   BasicXMLEnvelope.PropertySchema.Priority == Medium  
  
6.  Haga clic en **Aceptar** para completar la configuración de puerto de envío de prioridad Media y baja.  
  
##### <a name="to-configure-the-high-priority-send-port"></a>Para configurar el puerto de envío de prioridad alta  
  
1.  Utilice el Explorador de Windows para crear un directorio denominado "SendHighPriority" en la **BasicXMLEnvelope** directorio del proyecto.  
  
2.  En la consola de administración de BizTalk Server, expanda el **BasicXMLEnvelope** aplicación, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en  **Unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, establezca el nombre del puerto "SendHighPriority".  
  
4.  Para **tipo de transporte**, seleccione **archivo**y, a continuación, haga clic en **configurar**. Defina el directorio creado anteriormente como la carpeta de destino. Haga clic en **Aceptar** para cerrar.  
  
5.  Haga clic en **filtros** y agregue dos expresiones de filtro:  
  
    -   BTS.MessageType == http://BasicXMLEnvelope#Error And  
  
    -   BasicXMLEnvelope.PropertySchema.Priority == High  
  
6.  Haga clic en **Aceptar** para completar la configuración de puerto de envío de prioridad alta.  
  
##### <a name="to-test-the-routing-solution"></a>Para probar la solución de enrutamiento  
  
1.  En la consola de administración de BizTalk Server, expanda el **aplicaciones** de grupo, haga clic en el **BasicXMLEnvelope** aplicación y, a continuación, haga clic en **iniciar**. Cuando se le pida que confirme, haga clic en **iniciar**. Se darán de alta los nuevos puertos de envío.  
  
2.  Coloque el mensaje de prueba en la ubicación de recepción. Observe cómo se enrutan los mensajes de error a las distintas ubicaciones de envío:  
  
    -   Los mensajes de error con prioridad baja, media o alta que no tengan errores al procesarse se enrutan a la ubicación de envío original (configurada en el ejemplo principal) y a las ubicaciones de envío por prioridad. Para los mensajes con prioridad media o baja, aparece una copia en la ubicación de envío original y en la ubicación de envío de prioridad media o baja.  
  
    -   Si el procesamiento de intercambio recuperable está habilitado, los mensajes de error con errores no se enrutan, y los mensajes sin errores se enrutan correctamente según lo esperado. Los mensajes con errores no se enrutan porque este tipo de mensaje no coincide con el tipo usado en los filtros configurados.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de intercambio recuperable](../core/recoverable-interchange-processing.md)   
 [Promoción de propiedades](../core/promoting-properties.md)   
 [CBRSample (ejemplo de BizTalk Server)](../core/cbrsample-biztalk-server-sample.md)