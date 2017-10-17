---
title: 'Tutorial: Publicar servicios WCF con el adaptador WCF-NetMsmq | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e623b6dc-32e5-467c-bb7d-68b7a75723c1
caps.latest.revision: "46"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38530cfdbde78e96fb41093c79b6a5d1bb8fd132
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2017
---
# <a name="walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter"></a>Tutorial: Publicar servicios WCF con el adaptador WCF-NetMsmq
  
> [!NOTE]
>  Para obtener más información acerca de los adaptadores, vea [adaptadores de BizTalk Server](../core/adapters-in-biztalk-server.md).  
  
## <a name="introduction"></a>Introducción
  
 En [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], se puede publicar una orquestación como un Servicio [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]. A través de una ubicación de recepción de BizTalk, una orquestación puede exponer un extremo de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], lo que permite que un cliente [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] lo llame El **Asistente de publicación de servicio de WCF de BizTalk** proporciona una manera sencilla para exponer una orquestación como ubicación de recepción.  
  
 El adaptador de WCF-NetMsmq utiliza el **NetMsmqBinding** enlace para proporcionar soporte técnico para el uso de Microsoft Message Queuing (también conocido como MSMQ) como su transporte subyacente. El cliente de un Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] envía mensajes [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] a una cola MSMQ mediante la ubicación de recepción configurada para usar el adaptador de WCF-NetMSMQ. El adaptador toma los mensajes de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] de la cola MSMQ, los convierte a formato [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los escribe en la base de datos de cuadro de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 En este tutorial se muestra cómo una aplicación de consola cliente de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] usa el adaptador de WCF-NetMsmq para comunicarse con un Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], hospedado en una aplicación de la consola .NET, mediante una cola de mensajes MSMQ. Muestra cómo se publican los metadatos para una ubicación de recepción con el Asistente para publicación de Servicio WCF de BizTalk. También se muestra cómo se configura una aplicación Web para admitir la publicación de metadatos.  
  
 Cuando concluya el tutorial, comprenderá cómo se realizan las tareas siguientes:  
  
-   En Visual Studio, use la **implementar** comando para implementar ensamblados de BizTalk a una instancia local de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. De este modo, se creará una aplicación de BizTalk que se rellenará con los ensamblados. Un ensamblado de BizTalk contiene información de recursos, como orquestaciones, canalizaciones, esquemas y asignaciones que se utilizarán en una solución de BizTalk.  
  
-   En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], configure una ubicación de recepción de WCF-NetMsmq para hospedar el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] publicado.  
  
-   Desde el **Asistente de publicación de servicio de WCF de BizTalk**, cree la aplicación Web para publicar los metadatos para una ubicación de recepción. El cliente que envía mensajes a la ubicación de recepción usa estos metadatos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo los pasos descritos en este ejemplo, asegúrese de que el entorno instala los siguientes requisitos previos:  
  
-   Tanto en el equipo que genera los ensamblados y ejecuta el proceso de implementación y el equipo que ejecuta el ejemplo requieren Microsoft Windows Server, .NET Framework y BizTalk Server.  
  
-   El equipo que se usa para generar los ensamblados y ejecutar el proceso de implementación requiere Microsoft Visual Studio.  
  
-   El equipo que ejecuta el ejemplo requiere los adaptadores de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y las herramientas de administración de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Se trata de opciones de instalación durante la instalación de Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
-   En los equipos que use para realizar las tareas administrativas, debe ejecutar una cuenta de usuario que sea miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar los parámetros de aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esta cuenta de usuario también debe ser miembro del grupo de administradores local para la implementación de la aplicación, la administración de las instancias de host y otras tareas que puedan ser necesarias.  
  
-   En cualquier equipo que requiera [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] capacidad, complete el procedimiento de instalación única para la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] ejemplos en [http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510).  
  
-   En el equipo que ejecuta el ejemplo e importa un enlace o un archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], asegúrese de que el host no es un host de confianza. De lo contrario, se producirá un error en la importación.  
  
-   Debe descargar el código del tutorial y extraerlo en el equipo. Este tutorial es una parte de todo el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] paquete de tutoriales del adaptador. Puede descargar el archivo **WCFAdapterWalkthroughs.exe** desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Developer Center en [http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140).  
  
## <a name="build-and-deploy-the-biztalk-solution-biztalkapp"></a>Compilar e implementar la solución de BizTalk, BizTalkApp  
  
1.  Extraiga WCFNetMsmqAdapterPublishing.exe en **C:\WCFNetMsmqAdapterPublishing**.  
  
2.  En Visual Studio, abra el **WCFNetMsmqAdapterPublishing.sln** archivo.  
  
3.  En el Explorador de soluciones, expanda **BizTalkApp**y, a continuación, abra **OrderProcess.odx** para revisar. La orquestación de ejemplo recibe mensajes de solicitud de pedido y devuelve simplemente el orden de mensajes de respuesta.  
  
4.  Dado que la **BizTalkApp** ensamblado debe instalarse en la GAC, necesitará un archivo de clave de nombre seguro para completar el proceso de implementación. Haga clic en el **BizTalkApp** del proyecto y, a continuación, haga clic en **propiedades**. En el **propiedades** página, haga clic en **firma**y seleccione **firmar el ensamblado**. Haga clic en la flecha hacia abajo en la **elegir un archivo de clave de nombre seguro** la lista desplegable, haga clic en  **\<nuevo >** y escriba `keyfile.snk` en el **nombre de archivo de clave** cuadro de texto. Desactive la opción **proteger mi archivo de clave con una contraseña**y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en el **implementación** ficha y, a continuación, cambie la **Server** propiedad si usa un servidor de base de datos diferente para la base de datos de administración de BizTalk además **LOCALHOST**.  Asegúrese de **aplicación de BizTalk** valor se establece en **WCFNetMsmqAdapterPublishing**. Asegúrese de **instalar en la caché Global de ensamblados** está establecido en **True**.  
  
6.  En el Explorador de soluciones, haga clic en el **BizTalkApp** del proyecto y, a continuación, haga clic en **volver a generar**.  
  
7.  En el Explorador de soluciones, haga clic en **BizTalkApp**y, a continuación, haga clic en **implementar**.  
  
## <a name="configure-the-application"></a>Configurar la aplicación  
  
1.  Asegúrese de que el componente Message Queue Server (MSMQ) esté instalado en el equipo. Para ello:  
  
    1.  Haga clic en **iniciar**, haga clic en **equipo**y, a continuación, haga clic en **administrar** para abrir **el administrador del servidor**.  
  
    2.  Expanda el **características** nodo.  Si **Message Queue Server** no es está instalado, haga clic en **características**y seleccione **agregar características**. Comprobar **Message Queue Server**, haga clic en **siguiente**y, a continuación, haga clic en **instalar** para instalar MSMQ en el sistema.  
  
2.  Asegúrese de que Message Queue Server (MSMQ) se haya iniciado en el equipo para que el adaptador de WCF-NetMsmq pueda usarlo. Para ello:  
  
    1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Services**.  
  
    2.  En **servicios**, asegúrese de que el **estado** de la **Message Queue Server** servicio es **iniciado**. Si no se ha iniciado el servicio, haga clic en **Message Queue Server**y, a continuación, haga clic en **iniciar**.  
  
3.  Cree la cola de destino que la ubicación de recepción usa, en la que el adaptador de WCF-NetMsmq toma los mensajes entrantes de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] de los clientes.  
  
    1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.  
  
    2.  En **administración de equipos**, expanda **servicios y aplicaciones**, expanda **Message Queue Server**, haga clic en **colas privadas**, seleccione **New**y, a continuación, haga clic en **cola privada**.  
  
    3.  En el **cola privada nueva** cuadro de diálogo, escriba `WCFNetMsmqAdapterPublishing` en el **nombre de la cola** cuadro de texto, seleccione la **transaccional** casilla de verificación y, a continuación, haga clic en **Aceptar** .  
  
4.  Cree una ubicación de recepción WCF-NetMsmq para la aplicación de ejemplo. Para ello:  
  
    1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
    2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **WCFNetMsmqAdapterPublishing**, haga clic en **Puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
    3.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **nombre** cuadro de texto, escriba `WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder`y, a continuación, haga clic en **Aceptar**.  
  
    4.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción**.  
  
    5.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** cuadro de texto, escriba `WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder.NetMsmq`.  
  
    6.  En el **propiedades de la ubicación de recepción** cuadro de diálogo la **transporte** junto a la sección **tipo**, seleccione **WCF-NetMsmq** desde el lista desplegable y, a continuación, haga clic en **configurar**.  
  
    7.  En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, en la **General** ficha la **dirección (URI)** cuadro de texto, escriba `net.msmq://localhost/private/WCFNetMsmqAdapterPublishing`.  
  
    8.  En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo la **enlace** ficha, asegúrese de que el **transaccional** casilla está activada.  
  
        > [!NOTE]
        >  Como ha creado la cola de destino como una cola transaccional, debe activar esta casilla de verificación. Si no se activa, la ubicación de recepción no se habilitará ya que existirá una discrepancia entre el requisito transaccional de la ubicación de recepción y el de la cola MSMQ subyacente.  
  
    9. En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo la **seguridad** ficha, seleccione **ninguno** desde el **modo de seguridad** lista desplegable .  
  
        > [!NOTE]
        >  En este tutorial se supone que MSMQ está instalado con la integración [!INCLUDE[btsAD](../includes/btsad-md.md)] deshabilitada en el equipo. El valor predeterminado, **WindowsDomain**, para la **MsmqAuthenticationMode** propiedad está disponible cuando [!INCLUDE[btsAD](../includes/btsad-md.md)] está habilitada la integración.  
  
    10. En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
5.  Cree un puerto de envío de archivos para la aplicación de ejemplo. Este puerto se usa para enrutar la respuesta desde el pedido de compra de la orquestación subyacente del servicio.  
  
    1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **WCFNetMsmqAdapterPublishing**, haga clic en **puertos de envío**, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  
  
    2.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** cuadro de texto, escriba `WCFNetMsmqAdapterPublishing.SendPurchaseOrder.File`.  
  
    3.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **transporte** junto a la sección **tipo**, seleccione **archivo** en la lista desplegable y, a continuación, Haga clic en **configurar**.  
  
    4.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **General** ficha la **carpeta de destino** cuadro de texto, escriba `C:\WCFNetMsmqAdapterPublishing\Out`y, a continuación, haga clic en **Aceptar** .  
  
    5.  En el **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
6.  Especifique el nombre de host y los enlaces de la aplicación de ejemplo. Para ello:  
  
    1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **WCFNetMsmqAdapterPublishing**, expanda **orquestaciones**, haga clic en la orquestación de ejemplo, haga clic en **propiedades**, haga clic en **enlaces**y establezca **Host** a **BizTalkServerApplication** u otro host adecuado.  
  
    2.  En el **propiedades de orquestación** cuadro de diálogo, seleccione **WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder** desde el **puertos de recepción** la lista desplegable para el  **PurchaseOrderRequestPort**.  
  
    3.  En el **propiedades de orquestación** cuadro de diálogo, seleccione **WCFNetMsmqAdapterPublishing.SendPurchaseOrder.File** desde el **grupos de puertos de envío y puertos de envío** lista desplegable para el **PurchaseOrderResponsePort**.  
  
    4.  En el **propiedades de orquestación** cuadro de diálogo, haga clic en **Aceptar** para guardar la configuración.  
  
## <a name="publish-the-metadata-for-the-wcf-netmsmq-receive-location"></a>Publicar los metadatos para ubicación de recepción de WCF-NetMsmq  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Asistente de publicación de servicio de WCF de BizTalk**.  
  
2.  En el **éste es el Asistente para publicación de servicio WCF de BizTalk** página, haga clic en **siguiente**.  
  
3.  En el **tipo de servicio WCF** página, seleccione la **extremo de sólo metadatos (MEX)** ubicación de recepción de la casilla de verificación para publicar los metadatos para el WCFNetMsmq. Seleccione **WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder.NetMsmq** desde el **Publicar metadatos para la ubicación de recepción** lista desplegable y, a continuación, haga clic en **siguiente**.  
  
4.  En el **crear servicio WCF** página, seleccione **publicar orquestaciones de BizTalk como servicio WCF**y, a continuación, haga clic en **siguiente**.  
  
5.  En el **ensamblado de BizTalk** página, en la **archivo de ensamblado de BizTalk (\*.dll)** cuadro de texto, haga clic en **examinar** para ir a la **C:\ WCFNetMsmqAdapterPublishing\BizTalkApp\bin\Development** carpeta, haga doble clic en el ensamblado que contiene la orquestación de ejemplo para publicar y, a continuación, haga clic en **siguiente**.  
  
6.  En el **orquestaciones y puertos** página, asegúrese de que el **puerto: PurchaseOrderRequestPort** nodo está seleccionado en la página y, a continuación, haga clic en **siguiente**.  
  
     Se publicará el intercambio de metadatos para el puerto de recepción y el cliente lo usará para enviar mensajes a la ubicación de recepción.  
  
7.  En el **propiedades del servicio WCF** página, en la **espacio de nombres de destino del servicio WCF** cuadro de texto, escriba un URI que desee que este [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] de servicio para usar y, a continuación, haga clic en **siguiente**. En este tutorial, deje la dirección URI predeterminada, `http://tempuri.org/`.  
  
8.  En el **ubicación del servicio WCF** página, lleve a cabo las siguientes acciones para especificar la ubicación de la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] services para crear y, a continuación, haga clic en **siguiente**:  
  
    1.  En el **ubicación** cuadro de texto, escriba el directorio Web nombre donde la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] ejecuciones del servicio o haga clic en **examinar** y seleccione un directorio Web. En este tutorial, deje la ubicación predeterminada (http://localhost/*\<nombre de ensamblado de BizTalk >*) en el **ubicación** cuadro de texto.  
  
    2.  Seleccione el **permitir acceso anónimo al servicio WCF** opción. Esta opción agrega acceso anónimo al directorio virtual creado. Es necesario seleccionarla para permitir la autenticación anónima para la aplicación Web que se creará en este tutorial.  
  
9. En el **resumen de servicio WCF** página, haga clic en **crear** para crear el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] service.  
  
10. En el **completar BizTalk WCF Asistente para publicar servicios** página, haga clic en **finalizar**.  
  
## <a name="configure-the-web-application-hosting-the-published-metadata-service"></a>Configurar la aplicación Web que hospeda el servicio de metadatos publicados  
  
1.  Abra un símbolo del sistema, vaya a la **C:\inetpub\wwwroot\Microsoft.Samples.BizTalk.WCF.NetMsmqPublishing.BizTalkApp** carpeta donde el **Asistente de publicación de servicio de WCF de BizTalk** creado el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]servicio. Abra la **Web.config** archivo mediante el Bloc de notas.  
  
2.  En el Bloc de notas, agregue la siguiente línea dentro de la  **\<system.web >** elemento:  
  
    ```  
    <trust level="Full" originUrl="" />  
    ```  
  
    > [!NOTE]
    >  Este valor es opcional. Esta configuración concede a la aplicación ASP.NET que hospeda el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] publicado acceso a cualquier recurso que sea competencia de la seguridad del sistema operativo.  
  
3.  Pruebe el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] publicado mediante el uso de Internet Explorer de la siguiente forma:  
  
    1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
    2.  En el Administrador de IIS, cree un grupo de aplicaciones en el que se ejecutará este servicio y que tenga los permisos correctos para la base de datos de BizTalk. Haga clic en **grupos de aplicaciones**, haga clic en **Agregar grupo de aplicaciones**, escriba un nombre para el grupo de aplicaciones y, a continuación, haga clic en **Aceptar**.  
  
    3.  Expanda **grupos de aplicaciones**, haga clic en el grupo de aplicaciones recién creado y, a continuación, seleccione **configuración avanzada**. En **modelo de proceso** sección, especifique la cuenta que tiene acceso a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en el **identidad** campo.  
  
    4.  Expanda **sitios Web**, expanda **sitio Web predeterminado**y, a continuación, expanda la aplicación Web que creó el Asistente para publicación de servicio WCF de BizTalk.  
  
    5.  En el Administrador de IIS, en el panel central, haga clic en **vista de contenido** para mostrar los archivos de la aplicación.  
  
    6.  Haga clic en el **Microsoft_Samples_BizTalk_WCF_NetMsmqPublishing_BizTalkApp_OrderProcess_PurchaseOrderRequestPort.svc** servicio de archivos que la **Asistente de publicación de servicio de WCF de BizTalk** crea y, a continuación, haga clic en **examinar**. Se abrirá Internet Explorer para mostrar la **BizTalkServerInstance Service** página que indica que una instancia de la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio se está ejecutando. La página muestra una dirección WSDL completa que puede copiar y usar con la herramienta de metadatos de servicio (svcutil.exe) o desde dentro de Visual Studio, para recuperar el proxy de código y una configuración de archivo que puede usarse para crear una aplicación de cliente para el servicio.  
  
    7.  Copiar en el Portapapeles la línea de comandos con la dirección WSDL completa de **BizTalkServerInstance Service** página que muestra Internet Explorer en el paso anterior.  
  
         **svcutil.exe http://localhost/Microsoft.Samples.BizTalk.WCF.NetMsmqPublishing.BizTalkApp/Microsoft_Samples_BizTalk_WCF_NetMsmqPublishing_BizTalkApp_OrderProcess_PurchaseOrderRequestPort.svc?wsdl**  
  
## <a name="build-the-client-application"></a>Compile la aplicación cliente  
  
1.  Abra un símbolo del sistema de Visual Studio como administrador y vaya a la **C:\WCFNetMsmqAdapterPublishing\WCFClient** carpeta. Aquí es donde colocará archivo de configuración de la aplicación y de la clase de proxy.  
  
2.  Pegue toda la línea de comandos de svcutil.exe que contiene la dirección WSDL completa que ha copiado en el procedimiento anterior y presione ENTRAR. Esto crea la clase de proxy, **BizTalkServiceInstance.cs**y el archivo de configuración de aplicación, **output.config**. Mantenga la ventana de símbolo del sistema abierta para su uso durante la última sección.  
  
3.  En Visual Studio, en el Explorador de soluciones, haga clic en **WCFClient**, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.  
  
4.  En el **Agregar elemento existente** cuadro de diálogo, vaya a la **WCFClient** carpeta, seleccione **todos los archivos (\*.\*)**  en el **archivos de tipo** lista desplegable, seleccione la **BizTalkServiceInstance.cs** y **output.config** de archivos y, a continuación, haga clic en  **Agregar**.  
  
5.  Expanda **WCFClient**, haga clic en **output.config**, haga clic en **cambiar el nombre de**y, a continuación, escriba `App.config` como el nuevo nombre.  
  
6.  Haga doble clic en **Program.cs** para revisar cómo se llama publicado [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio que utiliza la clase de proxy generada por svcutil.exe.  
  
7.  Expanda **referencias**y, a continuación, asegúrese de que el **WCFClient** proyecto tiene **System.ServiceModel.dll** que se hace referencia.  
  
8.  Haga clic en el **WCFClient** de proyecto y seleccione **generar**. Mantenga Visual Studio abierta y vaya a la sección siguiente.  
  
## <a name="test-the-sample-solution-with-the-wcf-netmsmq-adapter"></a>Probar la solución de ejemplo con el adaptador de WCF-NetMsmq  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **WCFNetMsmqAdapterPublishing** aplicación y, a continuación, haga clic en **iniciar**. En el **iniciar** cuadro de diálogo, haga clic en **iniciar**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **configuración de plataforma**, expanda **instancias de Host**, haga clic en **BizTalkServerApplication** u otro procede de la instancia de host y, a continuación, haga clic en **reiniciar**. Aunque este paso no es necesario, es aconsejable asegurarse de que el ejemplo funciona correctamente hasta este punto.  
  
3.  En Visual Studio, en el **depurar** menú, haga clic en **iniciar sin depurar** para ejecutar la aplicación WCFClient. Esto envía un mensaje de ejemplo a la ubicación de recepción WCF-NetMsmq. Aparecerá el mensaje de salida siguiente que indica que se ha enviado el mensaje.  
  
     **Ubicación de recepción de una llamada a la operación de envío de WCF-NetMsmq**  
  
     **Presione cualquier tecla para cerrar la aplicación cliente de WCF**  
  
4.  Presione cualquier tecla para cerrar la aplicación WCFClient.  
  
5.  En la Visual Studio Command Prompt, vaya a la **C:\WCFNetMsmqAdapterPublishing\Out** carpeta y, a continuación, asegúrese de que el mensaje de respuesta que existe la aplicación WCFClient.  
  
6.  Haga doble clic en el archivo de {GUID} .xml para abrirlo en Internet Explorer y ver el **OrderID** valor procesadas por el servicio.  
  
## <a name="see-also"></a>Vea también  
 [Configurar un WCF-NetMsmq ubicación de recepción](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)   
 [Tutoriales del adaptador WCF](../core/wcf-adapter-walkthroughs.md)   
 [Adaptadores de recepción de la publicación de metadatos de servicio de WCF](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)