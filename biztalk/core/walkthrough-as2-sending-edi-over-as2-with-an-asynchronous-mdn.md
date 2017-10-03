---
title: "Tutorial (AS2): Enviar EDI a través de AS2 con un MDN asíncrono | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83644ac9-7023-4b09-966c-7c41d36f6b11
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e80d5429f109167a91297f69963f0fc46d6e7948
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn"></a>Tutorial (AS2): Enviar EDI a través de AS2 con un MDN asíncrono
Este tutorial proporciona un conjunto de procedimientos paso a paso que crea una solución para el envío de mensajes EDI a través de AS2 con un MDN asíncrono.  Puede crear y probar la solución completa de este tutorial en un único equipo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:  
  
-   Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   El equipo que ejecuta el tutorial debe tener Internet Information Services (IIS) 7 instalado.  
  
-   Si el equipo que ejecuta el tutorial tiene instalada la versión de 64 bits de Windows, debe asegurarse de que los hosts de BizTalk están marcados como de 32 bits solamente. Además debe asegurarse de que IIS tiene establecida en True la opción de habilitar aplicaciones de 32 bits para los grupos de aplicaciones. Para obtener más información, consulte [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md).  
  
## <a name="how-the-solution-sends-an-edias2-message-and-returns-an-asynchronous-mdn"></a>Cómo la solución envía un mensaje EDI y AS2 y devuelve un MDN asíncrono  
 La solución hará lo siguiente:  
  
1.  Un puerto de recepción de archivos unidireccional recibe un intercambio EDI de Contoso.  
  
    > [!NOTE]
    >  Puede que los eventos de esta lista no se produzcan en el orden mostrado.  
  
2.  Utiliza una canalización de recepción de paso a través, el puerto de recepción coloca el mensaje de prueba en el MeassageBox sin cambios.  
  
3.  Un puerto de envío unidireccional estático recoge el intercambio EDI y lo codifica en formato AS2.  
  
4.  El puerto de envío envía el intercambio EDI a través del transporte AS2 a la entidad Fabrikam.  
  
5.  El puerto de recepción unidireccional en Fabrikam recibe el mensaje AS2 mediante el directorio virtual de Fabrikam. La canalización de recepción descodifica el intercambio EDI a partir de AS2 y coloca el intercambio EDI en el cuadro de mensajes.  
  
6.  El mismo puerto de recepción unidireccional también genera un MDN y lo coloca en el cuadro de mensajes.  
  
7.  Un puerto de envío unidireccional estático recoge el mensaje EDI.  
  
8.  El puerto de envío unidireccional estático envía el mensaje EDI a una carpeta local.  
  
9. Un puerto de envío unidireccional dinámico recoge el MDN asíncrono.  
  
10. El puerto de envío unidireccional dinámico envía el MDN a Contoso.  
  
11. Un puerto de recepción unidireccional recibe el MDN y lo coloca en el cuadro de mensajes.  
  
12. Un puerto de envío unidireccional estático con una canalización de envío de paso a través recoge el MDN.  
  
13. El puerto de envío unidireccional envía el MDN a una carpeta local.  
  
 La siguiente ilustración muestra la arquitectura de esta solución.  
  
 ![Envío de AS2 con un MDN asíncrono](../core/media/343bbfcc-5387-426c-8700-db9738816218.gif "343bbfcc-5387-426c-8700-db9738816218")  
  
## <a name="the-functionality-in-this-solution"></a>La funcionalidad en esta solución  
 Los siguientes puntos se aplican a la funcionalidad de este tutorial:  
  
-   Este tutorial se ocupa de la funcionalidad AS2, no de la funcionalidad EDI. Como resultado, todos los puertos implicados en el procesamiento de AS2 usan las canalizaciones AS2Receive o AS2Send, no AS2EdiReceive ni AS2EdiSend. Los puertos que no están implicados en el procesamiento de AS2 usan las canalizaciones PassThruReceive o PassThruTransmit.  
  
-   No se ha habilitado la generación de informes de estado.  
  
-   Esta solución no configura el almacenamiento de mensajes, el cifrado, la compresión ni la firma en la base de datos sin repudio. Para conocer los procedimientos acerca de cómo configurar estas propiedades, vea [configurar propiedades de AS2](../core/configuring-as2-properties.md).  
  
## <a name="configuring-and-testing-the-walkthrough"></a>Configuración y prueba del tutorial  
 Los procedimientos necesarios para esta solución son:  
  
-   Generar e implementar un proyecto de BizTalk con el esquema de mensaje necesario, de modo que el esquema esté disponible para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lo utilice a la hora de procesar el intercambio recibido.  
  
-   Habilitar el filtro ISAPI de BTS que se utiliza para la recepción del mensaje AS2.  
  
-   Crear un directorio virtual de Fabrikam que reciba el mensaje AS2 de Contoso, como se configura en la ubicación de recepción.  
  
-   Crear un directorio virtual de Contoso que reciba el mensaje AS2 de Fabrikam, tal y como se configura en la ubicación de recepción.  
  
-   Especificar que Windows SharePoint Services no administre los directorios virtuales de Fabrikam y Contoso.  
  
-   Crear un puerto de recepción de archivos unidireccional para recibir el mensaje de prueba EDI que se enviará mediante transporte AS2. Cree la carpeta local en la que se va a recibir el mensaje de prueba.  
  
-   Crear un puerto de envío HTTP unidireccional estático para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envíe el mensaje AS2 que contiene el documento empresarial EDI a Fabrikam. Configurar la canalización de envío para que sea la canalización AS2Send.  
  
-   Crear un puerto de recepción HTTP unidireccional para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba el mensaje AS2. Configurar la canalización de recepción para que sea la canalización AS2Receive. Configurar la ubicación de recepción para recibir el mensaje AS2 mediante el directorio virtual de Fabrikam.  
  
-   Cree un puerto de envío de archivos unidireccional estático (con una canalización de envío de paso a través) para enrutar la carga del mensaje a una carpeta local. Crear la carpeta local.  
  
    > [!NOTE]
    >  Si no tiene un puerto de envío para suscribirse a la carga del mensaje, se suspenderá en el cuadro de mensajes.  
  
-   Crear un puerto de envío HTTP unidireccional dinámico para devolver el MDN a Contoso.  
  
    > [!NOTE]
    >  La solución de prueba está en un equipo único; como resultado, el puerto de envío unidireccional que envía el mensaje AS2 (desde Contoso) y el puerto de envío unidireccional que envía la respuesta MDN (desde Fabrikam) están en el mismo equipo.  
  
-   Crear un puerto de recepción unidireccional para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba la respuesta de MDN de Fabrikam.  
  
-   Cree un puerto de envío de archivos unidireccional estático (con una canalización de envío de paso a través) para enrutar el MDN a una carpeta local. Crear la carpeta local.  
  
-   Crear una entidad (socio comercial) para Fabrikam y Contoso.  
  
-   Crear un perfil de negocio para cada una de las entidades comerciales.  
  
-   Crear un acuerdo AS2 entre los perfiles de negocio de Fabrikam y Contoso. El acuerdo AS2 contendría las propiedades para enviar un mensaje AS2 y recibir un MDN asincrónico en respuesta.  
  
-   Probar el tutorial con un intercambio de prueba EDI.  
  
    > [!NOTE]
    >  En un mensaje de prueba, puede usar el archivo SamplePO.txt usado en el tutorial de programadores de la interfaz EDI. Ese archivo se incluye en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\. Es un mensaje X12 850.  
  
### <a name="configuring-the-walkthrough"></a>Configuración del tutorial  
 En esta sección se describen los procedimientos para configurar el tutorial.  
  
##### <a name="to-deploy-the-message-schema"></a>Para implementar el esquema de mensajes  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree o abra un proyecto de BizTalk.  
  
    > [!NOTE]
    >  Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI. Si no es así, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
2.  Haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **elemento existente**. Para usar el archivo SamplePO.txt para probar su solución, acceda a la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI. Seleccione el esquema X12_00401_850.xsd y, a continuación, haga clic en **agregar**.  
  
    > [!NOTE]
    >  Para usar un esquema EDI diferente, vaya a la [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI carpeta. Si los esquemas EDI no se han descomprimido en las carpetas XSD_SchemaEDI, ejecute el **MicrosoftEdiXSDTemplates.exe** archivo en la carpeta XSD_SchemaEDI para descomprimir los esquemas en la carpeta predeterminada.  
  
3.  Defina el archivo de clave de ensamblado y, a continuación, genere e implemente el ensamblado.  
  
##### <a name="to-enable-the-bts-isapi-filter"></a>Para habilitar el filtro ISAPI de BTS  
  
1.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.  
  
    > [!TIP]
    >  Según el sistema operativo, la opción Herramientas administrativas puede no estar disponible en el menú Inicio. En tales casos, haga clic en **iniciar**, haga clic en **ejecutar**y escriba `inetmgr` para abrir el Administrador de Internet Information Services (IIS).  
  
2.  Seleccione la entrada de servidor Web raíz y en el **vista características**, haga doble clic en **asignaciones de controlador** y, a continuación, en el panel Acciones haga clic en **Agregar asignación de Script**.  
  
    > [!NOTE]
    >  La configuración de la asignación de script en el nivel de servidor web hará que esta asignación se aplique a todos los sitios web secundarios. Si desea restringir la asignación a un sitio Web o una carpeta Virtual específico, seleccione el sitio de destino o la carpeta en lugar del servidor Web.  
  
3.  En el **Agregar asignación de Script** diálogo cuadro, escriba `BtsHttpReceive.dll` en el **ruta de acceso de solicitud** campo.  
  
4.  En el **ejecutable** , a continuación, haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive. Seleccione BtsHttpReceive.dll y haga clic en **Aceptar**.  
  
5.  Escriba `BizTalk HTTP Receive` en el `Name` campo y, a continuación, haga clic en **restricciones de solicitudes**.  
  
6.  En el **restricciones de solicitudes** cuadro de diálogo, seleccione la **verbos** ficha y, a continuación, seleccione **uno de los siguientes verbos**. Escriba `POST` como verbo.  
  
7.  En el **acceso** ficha, seleccione **Script** y, a continuación, haga clic en **Aceptar**.  
  
8.  Haga clic en **Aceptar** y cuando se le pida que permita la extensión ISAPI, haga clic en **Sí**.  
  
##### <a name="to-configure-the-fabrikam-web-page"></a>Para configurar la página Web de Fabrikam  
  
1.  En el Administrador de IIS, haga clic en **grupos de aplicaciones** y seleccione **Agregar grupo de aplicaciones**.  
  
2.  En el **Agregar grupo de aplicaciones** diálogo cuadro, escriba **BizTalkAppPool** en **nombre**y, a continuación, seleccione **.NET Framework V4.0.30210** en el **Versión de .NET framework** lista desplegable. Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  El número de versión puede variar en función de la versión de [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] instalada en el equipo.  
  
3.  Seleccione **grupos de aplicaciones**, en la **vista características** seleccione **BizTalkAppPool**y, a continuación, haga clic en **configuración avanzada** en el  **Acciones** panel.  
  
4.  En el **configuración avanzada** cuadro de diálogo, seleccione **identidad** y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
5.  En el **identidad del grupo de aplicaciones** cuadro de diálogo, seleccione **cuenta personalizada** y, a continuación, haga clic en **establecer**.  
  
6.  Escriba el **nombre de usuario** y **contraseña** para una cuenta de usuario que sea miembro del grupo Administradores, escriba la contraseña en **Confirmar contraseña** y, a continuación, haga clic en **Aceptar** tres veces para volver al administrador de IIS.  
  
7.  En el Administrador de IIS, abra el **sitios** carpeta. Haga clic con el botón secundario en el sitio web predeterminado y, a continuación, seleccione Agregar aplicación.  
  
8.  En el **Agregar aplicación** diálogo cuadro, escriba **Fabrikam** en **Alias**y, a continuación, haga clic en **seleccione**.  
  
9. En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione **BizTalkAppPool** y haga clic en **Aceptar**.  
  
10. Haga clic en el botón de puntos suspensivos (...) y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive para la **ruta de acceso física**.  
  
11. Haga clic en **configuración de pruebas** y comprobar que no hay ningún error que se muestra en el **Probar conexión** cuadro de diálogo. Haga clic en **Cerrar**y, a continuación, en **Aceptar**.  
  
12. En el Administrador de IIS, seleccione el directorio virtual de Contoso y en el **vista características**, haga doble clic en **autenticación**.  
  
13. En **autenticación**, seleccione **autenticación anónima** y compruebe que la **estado** es **habilitado**. Si el **estado** es **deshabilitado**, haga clic en **habilitar** en el **acciones** panel.  
  
##### <a name="to-configure-the-contoso-web-page"></a>Para configurar la página Web de Contoso  
  
1.  En el Administrador de IIS, abra el **sitios** carpeta. Haga clic con el botón secundario en el sitio web predeterminado y, a continuación, seleccione Agregar aplicación.  
  
2.  En el **Agregar aplicación** diálogo cuadro, escriba **Contoso** en **Alias**y, a continuación, haga clic en **seleccione**.  
  
3.  En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione **BizTalkAppPool** y haga clic en **Aceptar**.  
  
4.  Haga clic en el botón de puntos suspensivos (...) y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive para la **ruta de acceso física**.  
  
5.  Haga clic en **configuración de pruebas** y comprobar que no hay ningún error que se muestra en el **Probar conexión** cuadro de diálogo. Haga clic en **Cerrar**y, a continuación, en **Aceptar**.  
  
6.  En el Administrador de IIS, seleccione el directorio virtual de Contoso y en el **vista características**, haga doble clic en **autenticación**.  
  
7.  En **autenticación**, seleccione **autenticación anónima** y compruebe que la **estado** es **habilitado**. Si el **estado** es **deshabilitado**, haga clic en **habilitar** en el **acciones** panel.  
  
##### <a name="to-specify-that-the-fabrikam-and-contoso-virtual-directories-are-not-managed-by-windows-sharepoint-services"></a>Para especificar que Windows SharePoint Services no administre los directorios virtuales de Fabrikam y Contoso  
  
1.  Si Windows SharePoint Services está instalado en el equipo, haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
    > [!NOTE]
    >  Este procedimiento es necesario si Windows SharePoint Server está instalado en el mismo equipo en el que está configurando el tutorial. En ese caso, debe especificar que Windows SharePoint Server no esté administrando su directorio virtual de ISS.  
  
2.  En el **Administración Central** página, en **Administración Central**, haga clic en **Application Management**.  
  
3.  En el **administración de aplicaciones** página, haga clic en **definir rutas administradas**.  
  
4.  En el **definir rutas administradas** página, en **agregar una nueva ruta de acceso**, en la **ruta de acceso** texto cuadro, escriba `Fabrikam`. En **tipo**, haga clic en **ruta excluida**y, a continuación, haga clic en **Aceptar**.  
  
5.  Repita el paso 4 para el directorio virtual de Contoso.  
  
6.  Cerrar la **definir rutas administradas** página.  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-test-message"></a>Para crear un puerto de recepción para recibir el mensaje de prueba EDI  
  
1.  En el Explorador de Windows, cree una carpeta local en la que recibir el intercambio EDI de Contoso.  
  
2.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de recepción** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Unidireccional puerto de recepción**.  
  
3.  Nombre del puerto de recepción como **RecvISAFromCont**y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  
  
4.  Haga clic en **Nueva**.  
  
5.  Nombre de la ubicación de recepción, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
6.  Para **carpeta recepción**, escriba el nombre de la carpeta que creó en el paso 1.  
  
7.  Para la máscara del archivo, especifique la extensión del archivo. Si está utilizando el archivo SamplePO.txt como mensaje de prueba, escriba  **\*.txt**. Haga clic en **Aceptar**.  
  
8.  Para **canalización de recepción**, acepte el valor predeterminado de **PassThruReceive**.  
  
9. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
10. Haga clic en el **ubicaciones de recepción** nodo, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
##### <a name="to-create-a-send-port-to-send-the-edi-interchange-over-as2-to-fabrikam"></a>Para crear un puerto de envío para enviar el intercambio EDI mediante AS2 a Fabrikam  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  
  
2.  En el **propiedades de puerto de envío** cuadro de diálogo, el envío de nombre de puerto como **SendISAToFab**.  
  
3.  En el **transporte** sección, seleccione **HTTP** para **tipo**y, a continuación, haga clic en **configurar**.  
  
4.  En el **propiedades de transporte HTTP** cuadro de diálogo para **dirección URL de destino**, escriba **http://localhost/Fabrikam/BTSHttpReceive.dll**.  
  
5.  Desactive **Habilitar codificación fragmentada**y, a continuación, haga clic en **Aceptar**.  
  
6.  En **canalización de envío**, seleccione **AS2Send**.  
  
7.  En el árbol de consola, seleccione **filtros**. Para **propiedad**, escriba **BTS. ReceivePortName**; para **operador**, escriba  **==** ; y para **valor** escriba el nombre del puerto de recepción que recibirá el EDI intercambio (`RecvISAFromCont`).  
  
8.  Haga clic en **Aceptar**.  
  
9. Haga clic en el **puertos de envío** nodo en la consola de administración, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-receive-port-for-fabrikam-to-receive-the-as2-message"></a>Para crear un puerto de recepción para que Fabrikam reciba el mensaje AS2  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pulse el botón derecho en la consola de administración, bajo el nodo BizTalk Application 1, **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
2.  Nombre del puerto de recepción como **RecvAS2ForFabrikam**y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  
  
3.  Haga clic en **Nueva**.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, el nombre de la ubicación de recepción, seleccione **HTTP** para **tipo**y, a continuación, haga clic en **configurar**.  
  
5.  En el **propiedades de transporte HTTP** diálogo cuadro, escriba **/Fabrikam/BTSHttpReceive.dll** para **directorio Virtual más extensión ISAPI**. Desactive **devolver controlador de correlación en caso de éxito** y seleccione **suspender solicitudes con errores**. Haga clic en **Aceptar**.  
  
6.  Seleccione **AS2Receive** para el **canalización de recepción**. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
7.  Haga clic en el **ubicaciones de recepción** nodo, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a>Para crear un puerto de envío con el fin de enviar la carga EDI a una carpeta local  
  
1.  En el Explorador de Windows, cree una carpeta local a la que enviar el intercambio EDI.  
  
2.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** cuadro de diálogo nombre al puerto de envío **SendEDIToFab**. Seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
4.  En el **propiedades de transporte de archivo** cuadro de diálogo para **carpeta de destino**, especifique la carpeta local que ha creado para la carga EDI.  
  
5.  Para **nombre de archivo**, escriba el nombre de archivo. Si está utilizando el archivo SamplePO.txt como mensaje de prueba, escriba **%MessageID%.txt**. Haga clic en **Aceptar**.  
  
6.  Acepte el valor predeterminado de **PassThruTransmit** para **canalización de envío**.  
  
7.  Haga clic en **filtros** en la consola del árbol y agregar propiedades de filtro para recoger la carga EDI. En la primera línea, para **propiedad**, escriba **BTS. ReceivePortName**; para **operador**, escriba  **==** ; para **valor**, escriba el nombre del puerto de recepción que recibe de AS2 mensaje (`RecvAS2ForFabrikam`); y para **Agrupar por**, acepte **y**. En la segunda línea, para **propiedad**, escriba **EdiIntAS.IsAS2PayloadMessage**; para **operador**, escriba  **==** ; y para **Valor**, escriba **True**.  
  
8.  Haga clic en **Aceptar**.  
  
9. Haga clic en el **puertos de envío** nodo, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-dynamic-one-way-send-port-to-return-the-mdn"></a>Para crear un puerto de envío unidireccional dinámico para devolver el MDN  
  
1.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional dinámico**.  
  
2.  En el **propiedades de puerto de envío** cuadro de diálogo nombre al puerto de envío **Send_MDN**.  
  
3.  Para **canalización de envío**, escriba AS2Send.  
  
4.  Haga clic en **filtros** en la consola del árbol y agregar propiedades de filtro para recoger la carga EDI. En la primera línea, para **propiedad**, escriba **BTS. ReceivePortName**; para **operador**, escriba  **==** ; para **valor**, escriba el nombre del puerto de recepción que recibe de AS2 mensaje (`RecvAS2ForFabrikam`); y para **Agrupar por**, acepte **y**. En la segunda línea, para **propiedad**, escriba **EdiIntAS.IsAS2AsynchronousMDN**; para **operador**, escriba  **==** ; y para **Valor**, escriba **True**.  
  
5.  Haga clic en **Aceptar**.  
  
6.  Haga clic en el **puertos de envío** nodo, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-receive-port-to-receive-the-mdn-from-fabrikam"></a>Para crear un puerto de recepción para que reciba el MDN de Fabrikam  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pulse el botón derecho en la consola de administración, bajo el nodo BizTalk Application 1, **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
2.  Nombre del puerto de recepción como **RecvMDNFromFab**y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  
  
3.  Haga clic en **Nueva**.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, el nombre de la ubicación de recepción, seleccione **HTTP** para **tipo**y, a continuación, haga clic en **configurar**.  
  
5.  En el **propiedades de transporte HTTP** diálogo cuadro, escriba **/Contoso/BTSHTTPReceive.dll** para **directorio Virtual más extensión ISAPI**. Desactive **devolver controlador de correlación en caso de éxito** y seleccione **suspender solicitudes con errores**. Haga clic en **Aceptar**.  
  
6.  Seleccione **AS2Receive** para el **canalización de recepción**. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
7.  Haga clic en el **ubicaciones de recepción** nodo, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a>Para crear un puerto de envío con el fin de enviar el MDN a una carpeta local  
  
1.  En el Explorador de Windows, cree una carpeta local a la que va a enviar el MDN.  
  
2.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, asigne el nombre el puerto de envío. Seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
4.  En el **propiedades de transporte de archivo** cuadro de diálogo para **carpeta de destino**, especifique la carpeta local que ha creado para enviar el MDN.  
  
5.  Para **nombre de archivo**, escriba **%MessageID%.msg**. Haga clic en **Aceptar**.  
  
6.  Acepte el valor predeterminado de **PassThruTransmit** para **canalización de envío**.  
  
7.  Haga clic en **filtros** en el árbol de consola. Para **propiedad**, escriba **BTS. ReceivePortName**; para **operador**, escriba  **==** ; para **valor**, escriba el nombre del puerto de recepción que recibe el MDN (`RecvMDNFromFab`); y para **Agrupar por**, acepte **y**. En una segunda línea, para **propiedad**, escriba **EdiIntAS.IsAS2MdnResponseMessage**. Para **operador**, escriba  **==** . Para **valor**, escriba **True**.  
  
8.  Haga clic en **Aceptar**.  
  
9. Haga clic en el **puertos de envío** nodo, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>Para crear una entidad y un perfil de negocio para Fabrikam  
  
1.  Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite entidad o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es de la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  
  
3.  Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
4.  En el **propiedades de perfil** cuadro de diálogo la **General** escriba **Fabrikam_Profile** en el **nombre** cuadro de texto.  
  
    > [!NOTE]
    >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** página, especifique un nombre para el perfil.  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>Para crear una entidad y un perfil de negocio para Contoso  
  
1.  Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite entidad o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es de la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  
  
3.  Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
4.  En el **propiedades de perfil** cuadro de diálogo la **General** escriba **Contoso_Profile** en el **nombre** cuadro de texto.  
  
    > [!NOTE]
    >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** página, especifique un nombre para el perfil.  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a>Para crear un acuerdo AS2 entre los dos perfiles de negocio  
  
1.  Haga clic en **Contoso_Profile**, seleccione **New**y, a continuación, haga clic en **acuerdo**.  
  
2.  En el **propiedades generales** página, para la **nombre** texto cuadro, escriba un nombre para el acuerdo.  
  
3.  Desde el **protocolo** lista desplegable, seleccione **AS2**.  
  
4.  En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **Fabrikam**.  
  
5.  En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **Fabrikam_Profile**.  
  
     Observará que dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha sirve para configurar un acuerdo AS2 unidireccional.  
  
6.  Realizar las tareas siguientes en el **Contoso -> Fabrikam** ficha.  
  
    1.  En el **identificadores** página, escriba los valores para **AS2-de** y **AS2-a**. Para **AS2-de**, escriba `Contoso`. Para **AS2 - To**, escriba `Fabrikam`.  
  
    2.  En el **confirmaciones (MDN)** página, realice lo siguiente:  
  
        1.  Seleccione el **procesar el MDN entrante en el cuadro de mensajes para opciones de enrutado y entrega** casilla de verificación.  
  
            > [!NOTE]
            >  Comprobando el **procesar el MDN entrante en el cuadro de mensajes para opciones de enrutado y entrega** es necesaria para las pruebas de este tutorial, porque sólo entonces el MDN devuelto se eliminarán en el cuadro de mensajes. Esto permite crear un puerto de envío para suscribirse al MDN y enviar el MDN a un directorio local, de modo que se pueda comprobar la transmisión AS2.  
  
        2.  Seleccione el **solicitar MDN** casilla de verificación.  
  
        3.  Asegúrese de que el **solicitar MDN firmado** casilla de verificación está desactivada.  
  
        4.  Seleccione el **solicitar MDN asíncrono** casilla de verificación.  
  
        5.  En **Receipt-Delivery-Option (URL)**, escriba **http://localhost/Contoso/BTSHttpReceive.dll**.  
  
        6.  El **Disposition-Notification-To** se establece en el valor de forma predeterminada especifica para **Receipt-Delivery-Option (URL)** propiedad. El valor de este campo no se utiliza durante el procesamiento de AS2.  
  
    3.  En el **puertos de envío** página, asocie el puerto de envío bidireccional que se van a enviar el intercambio EDI a Fabrikam. En el **puertos de envío** cuadrícula, en la **nombre** columna, haga clic en una celda vacía y, en la lista desplegable, seleccione el puerto de envío **SendISAToFab**.  
  
7.  Realizar las tareas siguientes en el **Fabrikam -> Contoso** ficha.  
  
    > [!NOTE]
    >  En este tutorial, especificamos el valor necesario en la ficha para que se pueda crear un acuerdo correctamente. Para crear correctamente un acuerdo, ambas fichas de acuerdo unidireccional deben tener valores definidos para **AS2_From** y **AS2-a**.  
  
    1.  En el **identificadores** página, escriba los valores para **AS2-de** y **AS2-a**. Para **AS2-de**, escriba `Fabrikam`. Para **AS2 - To**, escriba `Contoso`.  
  
8.  Haga clic en **Aplicar**.  
  
9. Haga clic en **Aceptar**. El acuerdo recién agregado se muestra en el **contratos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  
  
### <a name="testing-the-walkthrough"></a>Probar el tutorial  
 Esta sección proporciona información acerca de cómo probar el tutorial.  
  
##### <a name="to-test-the-solution"></a>Para probar la solución  
  
1.  En el Explorador de Windows, vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial. Copia la **SamplePO.txt** archivo.  
  
2.  Pegar la **SamplePO.txt** archivo en la carpeta local que ha creado para recibir el mensaje de prueba de Contoso.  
  
3.  Desplácese a la carpeta local que ha creado para enviar la carga EDI. Confirme que la carpeta contiene un archivo EDI. Abra el archivo y el mensaje de prueba original, y compruebe que tienen el mismo contenido.  
  
4.  Desplácese a la carpeta local que ha creado para enviar el MDN resultante. Confirme que la carpeta contiene un archivo de prueba, abra el archivo y confirme que es un archivo MDN.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)