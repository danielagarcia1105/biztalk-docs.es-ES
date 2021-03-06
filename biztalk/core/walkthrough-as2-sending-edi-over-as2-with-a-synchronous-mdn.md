---
title: 'Tutorial (AS2): Enviar EDI a través de AS2 con un MDN sincrónico | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21891d29-eb22-4b31-9258-14b72ae675dc
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b5417adfd53498891eccb2845b815f475e861a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982333"
---
# <a name="walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn"></a>Tutorial (AS2): Enviar EDI a través de AS2 con un MDN sincrónico
Este tutorial proporciona un conjunto de procedimientos paso a paso que crea una solución para el envío de mensajes EDI a través de AS2 con un MDN sincrónico. Puede crear y probar la solución completa en este tutorial en un único equipo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:  
  
- Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- El equipo que ejecuta el tutorial debe tener Internet Information Services (IIS) 7 instalado.  
  
- Si el equipo que ejecuta el tutorial tiene instalada la versión de 64 bits de Windows, debe asegurarse de que los hosts de BizTalk están marcados como de 32 bits solamente. Además debe asegurarse de que IIS tiene establecida en True la opción de habilitar aplicaciones de 32 bits para los grupos de aplicaciones. Para obtener más información, consulte [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md).  
  
## <a name="how-the-solution-sends-an-edias2-message-and-returns-a-synchronous-mdn"></a>Cómo la solución envía un mensaje EDI y AS2 y devuelve un MDN sincrónico  
 La solución hará lo siguiente:  
  
1. Un puerto de recepción de archivos unidireccional recibe un intercambio EDI de Contoso.  
  
   > [!NOTE]
   >  Puede que los eventos de esta lista no se produzcan en el orden mostrado.  
  
2. Mediante la canalización de recepción de paso a través, el puerto de recepción coloca el mensaje de prueba en el cuadro de mensajes sin modificar.  
  
3. Un puerto de envío bidireccional estático recoge el intercambio EDI y lo codifica en formato AS2.  
  
4. El puerto de envío envía el intercambio EDI con codificación AS2 a través del transporte AS2 a la entidad Fabrikam.  
  
5. El puerto de recepción bidireccional en Fabrikam recibe el mensaje AS2 mediante el directorio virtual de Fabrikam. La canalización de recepción descodifica el intercambio EDI a partir de AS2 y coloca el intercambio EDI en el cuadro de mensajes.  
  
6. El puerto de envío asociado al puerto de recepción bidireccional devuelve un MDN sincrónico.  
  
7. El puerto de recepción asociado al puerto de envío bidireccional recibe el MDN y lo coloca en el cuadro de mensajes.  
  
8. Un puerto de envío unidireccional estático con una canalización de envío de paso a través recoge el MDN.  
  
9. El puerto de envío unidireccional envía el MDN a una carpeta local.  
  
10. Un puerto de envío unidireccional estático con una canalización de envío de paso a través recoge el mensaje EDI.  
  
11. El puerto de envío unidireccional envía el mensaje EDI a una carpeta local.  
  
    La siguiente ilustración muestra la arquitectura de esta solución.  
  
    ![Envío de AS2 con un MDN sincrónico](../core/media/270d24b7-3b5d-45cc-ba06-6c9f74717194.gif "270d24b7-3b5d-45cc-ba06-6c9f74717194")  
  
## <a name="the-functionality-in-this-solution"></a>La funcionalidad en esta solución  
 Los siguientes puntos se aplican a la funcionalidad de este tutorial:  
  
-   Este tutorial se ocupa de la funcionalidad AS2, no de la funcionalidad EDI. Como resultado, todos los puertos implicados en el procesamiento de AS2 usan las canalizaciones AS2Receive o AS2Send, no AS2EdiReceive ni AS2EdiSend. Los puertos que no están implicados en el procesamiento de AS2 usan las canalizaciones PassThruReceive o PassThruTransmit.  
  
-   No se ha habilitado la generación de informes de estado.  
  
-   Esta solución no configura el almacenamiento de mensajes, el cifrado, la compresión ni la firma en la base de datos sin repudio. Para conocer los procedimientos sobre cómo configurar estas propiedades, vea [configurar propiedades de AS2](../core/configuring-as2-properties.md).  
  
## <a name="configuring-and-testing-the-walkthrough"></a>Configuración y prueba del tutorial  
 Los procedimientos necesarios para esta solución son:  
  
- Generar e implementar un proyecto de BizTalk con el esquema de mensaje necesario, de modo que el esquema esté disponible para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lo utilice a la hora de procesar el intercambio recibido.  
  
- Habilitar el filtro ISAPI de BTS que se utiliza para la recepción del mensaje AS2.  
  
- Crear un directorio virtual de Fabrikam que reciba el mensaje AS2 de Contoso, como se configura en la ubicación de recepción.  
  
- Especifique que Windows SharePoint Services no administra el directorio virtual de Fabrikam.  
  
- Crear un puerto de recepción de archivos unidireccional para recibir el mensaje de prueba EDI que se enviará mediante transporte AS2. Cree la carpeta local en la que se va a recibir el mensaje de prueba.  
  
- Crear un puerto de envío HTTP bidireccional estático para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envíe el mensaje AS2 que contiene documento empresarial EDI a Fabrikam y reciba la respuesta MDN. Configure la canalización de envío para que sea la canalización AS2Send y la canalización de recepción para que sea la canalización AS2Receive.  
  
- Cree un puerto de recepción HTTP bidireccional para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba el mensaje AS2 y envíe la respuesta MDN. Configure AS2Receive como canalización de recepción y AS2Send como canalización de envío. Configurar la ubicación de recepción para recibir el mensaje AS2 mediante el directorio virtual de Fabrikam.  
  
  > [!NOTE]
  >  Esta solución está destinada a un equipo único; como resultado, el puerto de envío bidireccional que envía el mensaje AS2 (desde Contoso) y el puerto de recepción bidireccional que recibe el mensaje AS2 (como Fabrikam) están en el mismo equipo.  
  
- Cree un puerto de envío de archivos unidireccional estático (con una canalización de envío de paso a través) para enrutar el MDN a una carpeta local. Crear la carpeta local.  
  
- Cree un puerto de envío de archivos unidireccional estático (con una canalización de envío de paso a través) para enrutar la carga del mensaje a una carpeta local. Crear la carpeta local.  
  
  > [!NOTE]
  >  Si no tiene un puerto de envío para suscribirse a la carga del mensaje, se suspenderá en el cuadro de mensajes.  
  
- Crear una entidad (socio comercial) para Fabrikam y Contoso.  
  
- Crear un perfil de negocio para cada una de las entidades comerciales.  
  
- Crear un acuerdo AS2 entre los perfiles de negocio de Fabrikam y Contoso. El acuerdo AS2 debe contener propiedades para enviar un mensaje AS2 y recibir un MDN sincrónico como devolución.  
  
- Probar el tutorial con un intercambio de prueba EDI.  
  
  > [!NOTE]
  >  En un mensaje de prueba, puede usar el archivo SamplePO.txt usado en el tutorial de programadores de la interfaz EDI. Ese archivo se incluye en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\. Es un mensaje X12 850.  
  
### <a name="configuring-the-walkthrough"></a>Configuración del tutorial  
 En esta sección se describen los procedimientos para configurar el tutorial.  
  
##### <a name="to-deploy-the-message-schema"></a>Para implementar el esquema de mensajes  
  
1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree o abra un proyecto de BizTalk.  
  
   > [!NOTE]
   >  Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI. Si no, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
2. Haga clic en el proyecto, elija **agregar**y, a continuación, haga clic en **elemento existente**. Para usar el archivo SamplePO.txt para probar su solución, acceda a la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI. Seleccione el esquema X12_00401_850.xsd y, a continuación, haga clic en **agregar**.  
  
   > [!NOTE]
   >  Para usar un esquema EDI diferente, vaya a la [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI carpeta. Si los esquemas EDI no se han descomprimido en las carpetas XSD_SchemaEDI, ejecute el **MicrosoftEdiXSDTemplates.exe** archivo en la carpeta XSD_SchemaEDI para descomprimir los esquemas en la carpeta predeterminada.  
  
3. Defina el archivo de clave de ensamblado y, a continuación, genere e implemente el ensamblado.  
  
##### <a name="to-enable-the-bts-isapi-filter"></a>Para habilitar el filtro ISAPI de BTS  
  
1. Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.  
  
   > [!TIP]
   >  Según el sistema operativo, la opción Herramientas administrativas puede no estar disponible en el menú Inicio. En tales casos, haga clic en **iniciar**, haga clic en **ejecutar**y escriba `inetmgr` para abrir el Administrador de Internet Information Services (IIS).  
  
2. Seleccione la entrada de servidor Web raíz y, en el **vista características**, haga doble clic en **asignaciones de controlador** y, a continuación, en el panel Acciones haga clic en **Agregar asignación de Script**.  
  
   > [!NOTE]
   >  La configuración de la asignación de script en el nivel de servidor web hará que esta asignación se aplique a todos los sitios web secundarios. Si desea restringir la asignación a un sitio Web o una carpeta Virtual específica, seleccione el sitio de destino o la carpeta en lugar del servidor Web.  
  
3. En el **Agregar asignación de Script** diálogo cuadro, escriba `BtsHttpReceive.dll` en el **ruta de acceso de solicitud** campo.  
  
4. En el **ejecutable** , a continuación, haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive. Seleccione BtsHttpReceive.dll y haga clic en **Aceptar**.  
  
5. Escriba `BizTalk HTTP Receive` en el `Name` campo y, a continuación, haga clic en **restricciones de solicitudes**.  
  
6. En el **restricciones de solicitudes** cuadro de diálogo, seleccione el **verbos** pestaña y, a continuación, seleccione **uno de los siguientes verbos**. Escriba `POST` como verbo.  
  
7. En el **acceso** ficha, seleccione **Script** y, a continuación, haga clic en **Aceptar**.  
  
8. Haga clic en **Aceptar** y cuando se le solicite que permita la extensión ISAPI, haga clic en **Sí**.  
  
##### <a name="to-configure-the-fabrikam-web-page"></a>Para configurar la página Web de Fabrikam  
  
1. En el Administrador de IIS, haga clic en **grupos de aplicaciones** y seleccione **Agregar grupo de aplicaciones**.  
  
2. En **Agregar grupo de aplicaciones** diálogo cuadro, escriba **BizTalkAppPool** en **nombre**y, a continuación, seleccione **.NET Framework V4.0.30210** en el **Versión de .NET framework** lista desplegable. Haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  El número de versión puede variar en función de la versión de [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] instalada en el equipo.  
  
3. Seleccione **grupos de aplicaciones**, en el **vista características** seleccione **BizTalkAppPool**y, a continuación, haga clic en **configuración avanzada** en el  **Acciones** panel.  
  
4. En el **configuración avanzada** cuadro de diálogo, seleccione **identidad** y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
5. En el **identidad del grupo de aplicaciones** cuadro de diálogo, seleccione **cuenta personalizada** y, a continuación, haga clic en **establecer**.  
  
6. Escriba el **nombre de usuario** y **contraseña** para una cuenta de usuario que sea miembro del grupo Administradores, escriba la contraseña en **Confirmar contraseña** y, a continuación, haga clic en **Aceptar** tres veces para volver al administrador de IIS.  
  
7. En el Administrador de IIS, abra el **sitios** carpeta. Haga clic en el **sitio Web predeterminado** nodo y, a continuación, seleccione **Agregar aplicación**.  
  
8. En el **Agregar aplicación** diálogo cuadro, escriba **Fabrikam** en **Alias**y, a continuación, haga clic en **seleccione**.  
  
9. En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione **BizTalkAppPool** y haga clic en **Aceptar**.  
  
10. Haga clic en el botón de puntos suspensivos (...) y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive para la **ruta de acceso física**.  
  
11. Haga clic en **configuración de pruebas** y compruebe que no hay ningún error que se muestra en el **Probar conexión** cuadro de diálogo. Haga clic en **Cerrar**y, a continuación, en **Aceptar**.  
  
12. En el Administrador de IIS, seleccione el directorio virtual de Fabrikam y, en el **vista características**, haga doble clic en **autenticación**.  
  
13. En el **autenticación** página, seleccione **autenticación anónima** y compruebe que la **estado** es **habilitado**. Si el **estado** es **deshabilitado**, haga clic en **habilitar** en el **acciones** panel.  
  
##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a>Para especificar que Windows SharePoint Services no administra su directorio virtual  
  
1.  Si Windows SharePoint Services está instalado en el equipo, haga clic en **iniciar**, apunte a **todos los programas**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
    > [!NOTE]
    >  Este procedimiento es necesario si Windows SharePoint Server está instalado en el mismo equipo en el que está configurando el tutorial. En ese caso, debe especificar que Windows SharePoint Server no esté administrando su directorio virtual de ISS.  
  
2.  En el **Administración Central** página, en **Administración Central**, haga clic en **Application Management**.  
  
3.  En el **Application Management** página, haga clic en **definir rutas administradas**.  
  
4.  En el **definir rutas administradas** página, en **agregar una nueva ruta de acceso**, en el **ruta** texto, escriba `Fabrikam`. En **tipo**, haga clic en **ruta excluida**y, a continuación, haga clic en **Aceptar**.  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-test-message"></a>Para crear un puerto de recepción para recibir el mensaje de prueba EDI  
  
1. En el Explorador de Windows, cree una carpeta local en la que recibir el intercambio EDI de Contoso.  
  
2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de recepción** nodo bajo el **BizTalk Application 1** nodo, seleccione **New**y, a continuación, haga clic en  **Unidireccional puerto de recepción**.  
  
3. Nombre del puerto de recepción como **RecvISAFromCont**y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  
  
4. Haga clic en **Nueva**.  
  
5. Nombre de la ubicación de recepción, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
6. Para **carpeta recepción**, escriba el nombre de la carpeta que creó en el paso 1.  
  
7. Para **máscara de archivo**, escriba la extensión del archivo. Si usa el archivo SamplePO.txt como mensaje de prueba, escriba  **\*.txt**. Haga clic en **Aceptar**.  
  
8. Para **canalización de recepción**, acepte el valor predeterminado de **PassThruReceive**.  
  
9. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
10. Haga clic en el **ubicaciones de recepción** nodo, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
##### <a name="to-create-a-two-way-send-port-to-send-the-edi-interchange-over-as2-to-fabrikam-and-receive-an-mdn-response"></a>Procedimiento para crear un puerto de envío bidireccional que envíe el intercambio EDI a través de AS2 a Fabrikam y reciba una respuesta MDN  
  
1. > [!NOTE]
   >  Un puerto de envío bidireccional estático recoge el intercambio EDI y lo codifica en formato AS2. A continuación envía el intercambio EDI con codificación AS2 a través del transporte AS2 a la entidad Fabrikam. Más adelante, el puerto de recepción asociado al puerto de envío bidireccional recibe el MDN de Fabrikam y lo coloca en el cuadro de mensajes.  
  
    En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **New**y, a continuación, haga clic en **Puerto de envío de petición-respuesta estático**.  
  
2. En el **propiedades de puerto de envío** cuadro de diálogo, nombre el puerto de envío. Para esta solución, denomine el puerto de envío como **SendISAToFab_RecMDN**.  
  
3. En el **transporte** sección, seleccione **HTTP** para **tipo**y, a continuación, haga clic en **configurar**.  
  
4. En el **propiedades de transporte HTTP** cuadro de diálogo para **dirección URL de destino**, escriba **http://localhost/Fabrikam/BTSHttpReceive.dll**.  
  
5. Borrar **Habilitar codificación fragmentada**y, a continuación, haga clic en **Aceptar**.  
  
6. En **canalización de envío**, seleccione **AS2Send**.  
  
7. En **canalización de recepción**, seleccione **AS2Receive**.  
  
8. En el árbol de consola, seleccione **filtros**. Para **propiedad**, escriba **BTS. ReceivePortName**; para **operador**, escriba **==**; y para **valor** escriba el nombre del puerto de recepción que recibirá el EDI intercambio (`RecvISAFromCont`).  
  
9. Haga clic en **Aceptar**.  
  
10. Haga clic en el **puertos de envío** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-two-way-receive-port-to-receive-the-as2-message-and-return-an-mdn"></a>Procedimiento para crear un puerto de recepción bidireccional para recibir el mensaje AS2 y devolver un MDN  
  
1. > [!NOTE]
   >  El puerto de recepción bidireccional en Fabrikam recibe el mensaje AS2 mediante el directorio virtual de Fabrikam. La canalización de recepción descodifica el intercambio EDI a partir de AS2 y coloca el intercambio EDI en el cuadro de mensajes. El puerto de envío asociado al puerto de recepción bidireccional devuelve un MDN sincrónico.  
  
    En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **BizTalk Application 1** nodo, haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **Puerto de recepción de solicitud-respuesta**.  
  
2. Nombre del puerto de recepción como **RecvAS2ForFab**y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  
  
3. Haga clic en **Nueva**.  
  
4. En el **propiedades de ubicación de recepción** cuadro de diálogo, el nombre de la ubicación de recepción, seleccione **HTTP** para **tipo**y, a continuación, haga clic en **configurar**.  
  
5. En el **propiedades de transporte HTTP** diálogo cuadro, escriba **/Fabrikam/BTSHttpReceive.dll** para **directorio Virtual más extensión ISAPI**. Borrar **devolver controlador de correlación en caso de éxito** y seleccione **suspender solicitudes con errores**. Haga clic en **Aceptar**.  
  
6. Seleccione **AS2Receive** para el **canalización de recepción**, y **AS2Send** para el **canalización de envío**. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
7. Haga clic en el **ubicaciones de recepción** nodo, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a>Para crear un puerto de envío con el fin de enviar la carga EDI a una carpeta local  
  
1. En el Explorador de Windows, cree una carpeta local a la que enviar el intercambio EDI.  
  
2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
3. En el **propiedades de puerto de envío** cuadro de diálogo nombre al puerto de envío **SendEDIMsg**. Seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
4. En el **propiedades de transporte de archivo** cuadro de diálogo para **carpeta de destino**, especifique la carpeta local que ha creado para la carga EDI.  
  
5. Para **nombre de archivo**, escriba el nombre de archivo. Si usa el archivo SamplePO.txt como mensaje de prueba, escriba **%MessageID%.txt**. Haga clic en **Aceptar**.  
  
6. Acepte el valor predeterminado de **PassThruTransmit** para **canalización de envío**.  
  
7. Haga clic en **filtros** en la consola del árbol y agregar propiedades de filtro para recoger la carga EDI. En la primera línea, para **propiedad**, escriba **BTS. ReceivePortName**; para **operador**, escriba **==**; para **valor**, escriba el nombre del puerto de recepción que recibe de AS2 mensaje (`RecvAS2ForFab`); y para **Agrupar por**, acepte **y**. En la segunda línea, para **propiedad**, escriba **EdiIntAS.IsAS2PayloadMessage**; para **operador**, escriba **==**; y para **Valor**, escriba **True**.  
  
8. Haga clic en **Aceptar**.  
  
9. Haga clic en el **puertos de envío** nodo, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a>Para crear un puerto de envío con el fin de enviar el MDN a una carpeta local  
  
1. En el Explorador de Windows, cree una carpeta local a la que va a enviar el MDN.  
  
2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
3. En el **propiedades de puerto de envío** cuadro de diálogo nombre al puerto de envío **SendMDN**. Seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
4. En el **propiedades de transporte de archivo** cuadro de diálogo para **carpeta de destino**, especifique la carpeta local que ha creado para enviar el MDN.  
  
5. Para **nombre de archivo**, escriba **%MessageID%.msg**. Haga clic en **Aceptar**.  
  
6. Acepte el valor predeterminado de **PassThruTransmit** para **canalización de envío**.  
  
7. Haga clic en **filtros** en el árbol de consola. Para **propiedad**, escriba **BTS. SPName**; para **operador**, escriba **==**; para **valor**, escriba el nombre del puerto de envío que envía el mensaje AS2 (`SendISAToFab_RecMDN`); y para **Agrupar por**, acepte **y**. En una segunda línea, para **propiedad**, escriba **EdiIntAS.IsAS2MdnResponseMessage**; para **operador**, escriba **==**; para **Valor**, escriba **True**.  
  
8. Haga clic en **Aceptar**.  
  
9. Haga clic en el **puertos de envío** nodo, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>Para crear una entidad y un perfil de negocio para Fabrikam  
  
1. Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2. Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite las partes o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es para la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  
  
3. Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
4. En el **propiedades de perfil** cuadro de diálogo el **General** , escriba **Fabrikam_Profile** en el **nombre** cuadro de texto.  
  
   > [!NOTE]
   >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** , especifique un nombre para el perfil.  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>Para crear una entidad y un perfil de negocio para Contoso  
  
1. Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2. Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite las partes o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es para la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  
  
3. Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
4. En el **propiedades de perfil** cuadro de diálogo el **General** , escriba **Contoso_Profile** en el **nombre** cuadro de texto.  
  
   > [!NOTE]
   >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** , especifique un nombre para el perfil.  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a>Para crear un acuerdo AS2 entre los dos perfiles de negocio  
  
1.  Haga clic en **Contoso_Profile**, apunte a **New**y, a continuación, haga clic en **contrato**.  
  
2.  En el **propiedades generales** página, para el **nombre** texto, escriba un nombre para el acuerdo.  
  
3.  Desde el **protocolo** lista desplegable, seleccione **AS2**.  
  
4.  En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **Fabrikam**.  
  
5.  En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **Fabrikam_Profile**.  
  
     Observará que las dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha sirve para configurar un acuerdo AS2 unidireccional.  
  
6.  Realizar las tareas siguientes en el **Contoso -> Fabrikam** ficha.  
  
    1.  En el **identificadores** , escriba valores para **AS2-desde** y **AS2-para**. Para **AS2-desde**, escriba `Contoso`. Para **AS2 - To**, escriba `Fabrikam`.  
  
    2.  En el **confirmaciones (MDN)** página, realice lo siguiente:  
  
        1.  Seleccione el **procesar el MDN entrante en el cuadro de mensajes para las opciones de enrutado y entrega** casilla de verificación.  
  
            > [!NOTE]
            >  Comprobando la **procesar el MDN entrante en el cuadro de mensajes para las opciones de enrutado y entrega** es necesaria para las pruebas de este tutorial, porque sólo entonces el MDN devuelto se eliminarán en el cuadro de mensajes. Esto permite crear un puerto de envío para suscribirse al MDN y enviar el MDN a un directorio local, de modo que se pueda comprobar la transmisión AS2.  
  
        2.  Seleccione el **solicitar MDN** casilla de verificación.  
  
        3.  Asegúrese de que el **solicitar MDN firmado** casilla está desactivada.  
  
        4.  Deje **solicitar MDN asíncrono** desactivada.  
  
        5.  En **Disposition-Notification-To**, escriba cualquier valor. El valor de este campo no se usa durante el procesamiento de AS2, pero se debe especificar un valor en el campo.  
  
    3.  En el **puertos de envío** página, asocie el puerto de envío bidireccional que se va a enviar el intercambio EDI a Fabrikam. En el **puertos de envío** cuadrícula, en el **nombre** columna, haga clic en una celda vacía y, en la lista desplegable, seleccione el puerto de envío **SendISAToFab_RecMDN**.  
  
7.  Realizar las tareas siguientes en el **Fabrikam -> Contoso** ficha.  
  
    > [!NOTE]
    >  En este tutorial, especificamos el valor necesario en la ficha para que se pueda crear un acuerdo correctamente. Para crear correctamente un acuerdo, ambas fichas de acuerdo unidireccional deben tener valores definidos para **AS2_From** y **AS2-para**.  
  
    1.  En el **identificadores** , escriba valores para **AS2-desde** y **AS2-para**. Para **AS2-desde**, escriba `Fabrikam`. Para **AS2 - To**, escriba `Contoso`.  
  
8.  Haga clic en **Aplicar**.  
  
9. Haga clic en **Aceptar**. El acuerdo recién agregado aparece en la **acuerdos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  
  
### <a name="testing-the-walkthrough"></a>Probar el tutorial  
 Esta sección proporciona información acerca de cómo probar el tutorial.  
  
##### <a name="to-test-the-solution"></a>Para probar la solución  
  
1. En el Explorador de Windows, vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial. Copia el **SamplePO.txt** archivo.  
  
2. Pegar la **SamplePO.txt** archivo en la carpeta local que ha creado para recibir el mensaje de prueba de Contoso.  
  
3. Desplácese a la carpeta local que ha creado para enviar la carga EDI. Confirme que la carpeta contiene un archivo EDI. Abra el archivo y el mensaje de prueba original, y compruebe que tienen el mismo contenido.  
  
4. Desplácese a la carpeta local que ha creado para enviar el MDN resultante. Confirme que la carpeta contiene un archivo. Abra el archivo y confirme que es un archivo MDN.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo y configuración de soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)