---
title: 'Tutorial: Consumir servicios WCF con el adaptador WCF-BasicHttp | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d280198-ba55-4937-91c9-19d6d0ed3194
caps.latest.revision: 49
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3c85d550e7a1429e18035629517017c90b44c9e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "26010981"
---
# <a name="walkthrough-consuming-wcf-services-with-the-wcf-basichttp-adapter"></a>Tutorial: Consumir servicios WCF con el adaptador WCF-BasicHttp
  
> [!NOTE]
>  Para obtener más información acerca de los adaptadores, vea [adaptadores de BizTalk Server](../core/adapters-in-biztalk-server.md).  
  
## <a name="introduction"></a>Introducción
  
 En este tutorial, va a consumir un servicio de [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] hospedado en Internet Information Services (IIS), mediante la mensajería de BizTalk y el adaptador de envío de WCF-BasicHttp. Este adaptador usa el **BasicHttpBinding** enlace para proporcionar una implementación de la pila de protocolos o transporte compatible con versiones anteriores de servicios Web para que sirvan como puente entre Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] funcionalidad. Una orquestación puede enlazarse con un puerto de envío que use un adaptador de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] para llamar a un servicio de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y aprovechar su funcionalidad en su procesamiento empresarial lógico.  
  
 El adaptador de WCF-BasicHttp se compone tanto de un adaptador de envío como de uno de recepción. En este ejemplo, va a usar únicamente la parte de envío del adaptador para realizar solicitudes de Servicio WCF a través del protocolo HTTP para un Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].  Para un puerto de envío de petición-respuesta, el adaptador de envío envía a un Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y recibe una respuesta como resultado.  Por el contrario, un adaptador de recepción de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] permite que una orquestación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se publique y llame externamente desde una aplicación cliente de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Hacer referencia a la [publicar servicios WCF](../core/publishing-wcf-services.md) para obtener información adicional.  
  
 Cuando concluya el tutorial, comprenderá cómo se realizan las tareas siguientes:  
  
-   Desde [!INCLUDE[btsCoName](../includes/btsconame-md.md)]Visual Studio, use la **implementar** comando para implementar los ensamblados que contienen el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución y la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio a una instancia local de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. De este modo, se creará una aplicación de BizTalk que se rellenará con los ensamblados.  
  
-   En Visual Studio, use la **Asistente de consumición de servicio WCF de BizTalk** para generar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] esquemas y tipos necesarios para consumir el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] service. También se genera una orquestación vacía, que se puede usar y enlazar con un puerto lógico. Esta orquestación se compila y se implementa junto con los esquemas y tipos. Sin embargo, el procesamiento del flujo de trabajo de la orquestación aquí está vacío y no se usa en este ejemplo, ya que solamente se trata de un escenario de mensajería de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], configure el enrutamiento basado en contenido mediante el uso del puerto de envío WCF-BasicHttp. Configurará el **SOAPAction** encabezado que el destino [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio espera recibir.  
  
-   Desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], configure la expresión de filtro para enrutar los mensajes de error SOAP que un Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] puede enviar a una carpeta de salida.  
  
-   Desde el Administrador de Internet Information Services (IIS), configure la aplicación web que hospeda el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] para que exponga sus metadatos. Una vez habilitada, la **Asistente de consumición de servicio WCF de BizTalk** puede obtener estos metadatos para generar tipos y esquemas para tener acceso a la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo los pasos descritos en este ejemplo, asegúrese de que el entorno instala los siguientes requisitos previos:  
  
-   El equipo que genera los ensamblados y ejecuta el proceso de implementación tanto el equipo que ejecuta el ejemplo requieren Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]y Microsoft BizTalk Server.  
  
-   El equipo que se usa para generar los ensamblados y ejecutar el proceso de implementación requiere Microsoft Visual Studio.  
  
-   El equipo que ejecuta el ejemplo requiere los adaptadores de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y las herramientas de administración de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Estas son opciones para instalar durante la instalación de Microsoft BizTalk Server.  
  
-   En los equipos que use para realizar las tareas administrativas, debe ejecutar una cuenta de usuario que sea miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar los parámetros de aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esta cuenta de usuario también debe ser miembro del grupo de administradores local para la implementación de la aplicación, la administración de las instancias de host y otras tareas que puedan ser necesarias.  
  
-   En cualquier equipo que requiera [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] capacidad, complete el procedimiento de instalación única para la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] ejemplos en [ http://go.microsoft.com/fwlink/?LinkId=135510 ](http://go.microsoft.com/fwlink/?LinkId=135510).  
  
-   En el equipo que ejecuta el ejemplo e importa un enlace o un archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], asegúrese de que el host no es un host de confianza. De lo contrario, se producirá un error en la importación.  
  
-   Debe descargar el código del tutorial y extraerlo en el equipo.  Este tutorial es una parte de todo el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] paquete de tutoriales del adaptador. Puede descargar el archivo **WCFAdapterWalkthroughs.exe** desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Developer Center en[http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140).  
  
## <a name="deploy-the-sample-wcf-service"></a>Implementar el servicio WCF de ejemplo  
  
1.  Ejecutar la extracción automática **WCFBasicHttpSendAdapter.exe** de archivos y extraiga los archivos en el **C:\WCFBasicHttpSendAdapter** carpeta.  
  
2.  Abra la **C:\WCFBasicHttpSendAdapter\WCFBasicHttpSendAdapter.sln** en Visual Studio.  
  
3.  En el Explorador de soluciones, expanda la **BasicHttpWCFServiceConsuming** proyecto. Este proyecto es el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] que llamará el puerto de envío. Será hospedado en un entorno de host administrado mediante Internet Information Services (IIS). El hospedaje en IIS usa la activación basada en mensajes para administrar la activación y duración del servicio. Expanda **App_Code**y, a continuación, abra **OrderProcess.cs** para revisar. Esto [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio recibe los mensajes de solicitud de pedido a través de la **OrderRequest** método. El archivo OrderProcess.cs contiene la definición de interfaz y la implementación del Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Simplemente devuelve pedido mensajes de respuesta a través de la **OrderResponse** método.  
  
4.  Revise el archivo OrderProcess.svc. Solo contiene una línea que se usa para indicar a IIS que debe activar el servicio para una aplicación cliente. El **@ServiceHost** atributo utilizado para hospedar el servicio es un punto de extensibilidad dentro del [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] modelo de programación. Utiliza un modelo de generador **ServiceHostFactory** para crear una instancia de **ServiceHost** con una instancia de la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio para administrar las solicitudes entrantes. Creación de instancias de esta instancia se basa en el **ServiceBehaviorAttribute.ConcurrencyMode** propiedad, que determina si un servicio admite un subproceso, varios subprocesos o llamadas reentrantes. Creación de instancias también se determina mediante la **ServiceBehavior.InstanceMode** propiedad, que determina si una sola instancia dará servicio a todos los llamadores (singleton), si se crea una instancia por llamada (sin estado), o si una instancia se creará para cada sesión (con estado).  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming.OrderProcessServiceType" %>  
    ```  
  
5.  En Visual Studio, en el Explorador de soluciones, abra **Web.config** para revisar. Si se hospeda en IIS, el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] se configura mediante un archivo Web.config, en lugar del archivo app.config (como es el caso cuando se hospeda en una aplicación de consola).  
  
    -   Asegúrese de que el **httpGetEnabled** atributo de la \< **serviceMetaData** \> elemento está establecido en `true` para que el **servicio de WCF de BizTalk Asistente para consumición** puede consumir los metadatos para el servicio.  
  
    -   Asegúrese de que el **modo** atributo de la \< **seguridad** \> elemento está establecido en **ninguno**. Dado que este tutorial usa el **ninguno** modo de seguridad, la aplicación que hospeda este servicio debe configurarse para permitir el acceso anónimo de Web.  
  
6.  Dado que la **Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming** ensamblado debe instalarse en la GAC, necesitará un archivo de clave de nombre seguro para completar el proceso de implementación. Haga clic en el **BasicHttpWcfServiceConsuming** del proyecto y, a continuación, haga clic en **propiedades**. En el **propiedades** página, haga clic en **firma**y seleccione **firmar el ensamblado**. Haga clic en la flecha hacia abajo en la **elegir un archivo de clave de nombre seguro** la lista desplegable, haga clic en  **\<New\>** y escriba `keyfile.snk` en el **nombre de archivo de clave**cuadro de texto.  Desactive la opción **proteger mi archivo de clave con una contraseña**y, a continuación, haga clic en **Aceptar**.  
  
7.  En el Explorador de soluciones, haga clic en **BasicHttpWcfServiceConsuming**y, a continuación, haga clic en **volver a generar**.  
  
8.  Mediante el Explorador de Windows, copie el contenido de **C:\WCFBasicHttpSendAdapter\BasicHttpWCFServiceConsuming** a la **C:\InetPub\wwwroot** carpeta.  
  
9. Configure la aplicación web para que hospede el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] de la siguiente forma:  
  
    1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
    2.  Cree un grupo de aplicaciones en el que se va a ejecutar este servicio. Haga clic en **grupos de aplicaciones**, haga clic en **Agregar grupo de aplicaciones...** , escriba un nombre para el grupo de aplicaciones y, a continuación, haga clic en **Aceptar**.  
  
    3.  Expanda **grupos de aplicaciones**, haga clic en el grupo de aplicaciones recién creado y, a continuación, seleccione **configuración avanzada**. En **modelo de proceso** sección, especifique la cuenta que tiene acceso a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en el **identidad** campo.  
  
    4.  Expanda **sitios**, expanda **sitio Web predeterminado**, haga clic en **BasicHttpWCFServiceConsuming**y, a continuación, haga clic en **convertir en aplicación**para crear una aplicación Web para este [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio.  
  
    5.  En el **convertir en aplicación** cuadro de diálogo, haga clic en **seleccione** para seleccionar el grupo de aplicaciones creado anteriormente y, a continuación, haga clic en **Aceptar**.  
  
    6.  En la vista de características, haga clic en el **autenticación** icono y asegúrese de que el **autenticación anónima** opción es **habilitado**. Esto es compatible con [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicios con el **ninguno** modo de seguridad.  
  
10. Pruebe el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] publicado, de la siguiente manera:  
  
    1.  En el Administrador de IIS, expanda **sitios Web**y, a continuación, expanda **BasicHttpWCFServiceConsuming**.  
  
    2.  En el Administrador de IIS, en el panel derecho, haga clic en **OrderProcess.svc**y, a continuación, haga clic en **examinar**. Se abrirá Internet Explorer para mostrar la **OrderProcessServiceType Service** página que indica que ha creado correctamente un ejecución [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio. La página también incluye una dirección WSDL completa que puede copiar y usar con una herramienta de metadatos de servicio (svcutil.exe) para crear código de proxy y un archivo de configuración que puede usarse para desarrollar una aplicación cliente para el servicio.  
  
    3.  Copie la dirección completa de WSDL en el Portapapeles del sistema. No copie la **"svcutil.exe"** parte: **http://localhost/BasicHttpWcfServiceConsuming/OrderProcess.svc?wsdl**  
  
## <a name="add-the-schemas-and-types-for-the-wcf-basichttp-adapter-to-the-sample-biztalk-application"></a>Agregar esquemas y tipos para el adaptador de WCF-BasicHttp a la aplicación de BizTalk de ejemplo  
  
1.  Puesto que el adaptador llama al Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], necesita información de los esquemas y tipos sobre cómo realizar esa llamada al servicio mediante los metadatos. **BizTalkApp** proporciona los artefactos para consumir el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] service. En Visual Studio, en el Explorador de soluciones, haga clic en **BizTalkApp**, haga clic en **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2.  En el **agregar elementos generados** cuadro de diálogo, en la **plantillas** sección, seleccione **consumir servicio WCF**y, a continuación, haga clic en **agregar**.  
  
3.  En el **éste es el Asistente para consumición de servicio de BizTalk WCF** página, haga clic en **siguiente**. Este asistente leerá los metadatos y creará esquemas y tipos.  
  
4.  En el **origen de metadatos** página, seleccione la **punto de conexión de intercambio de metadatos (MEX)** opción consuma los metadatos de la dirección URL que ha copiado en el Portapapeles en el procedimiento anterior y, a continuación, haga clic en **Siguiente**.  
  
5.  En el **extremo de metadatos** , pegue la dirección WSDL completa que ha copiado en el procedimiento anterior para la **dirección de metadatos** lista desplegable y, a continuación, haga clic en **obtener** para obtener el documento de metadatos para el ejemplo [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio. Obtener los metadatos permite la **siguiente** botón. Para continuar, haga clic en **Siguiente** .  
  
6.  En el **Importar resumen de metadatos de servicio de WCF** página, revise la configuración. Este cuadro de diálogo muestra los resúmenes de espacio de nombres, de XSD y de WSDL de los metadatos que van a importarse. También muestra dónde se escribirá orquestación (.odx), los enlaces (.xml) y los archivos de esquema (.xsd) durante el proceso de importación. Haga clic en **importación** para crear los artefactos de BizTalk y los tipos que se usará para consumir el ejemplo [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio.  
  
7.  En el **completar el Asistente para consumición de servicio de BizTalk WCF** página, haga clic en **finalizar**.  
  
8.  En Visual Studio, en el Explorador de soluciones, la **Asistente de consumición de servicio WCF de BizTalk** genera los siguientes archivos:  
  
    -   Un archivo de orquestación **OrderProcessServiceType.odx**. No hay ninguna fase de flujo de trabajo en esta orquestación. Sin embargo, puede agregarla y enlazarla a puertos lógicos para consumir el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Contiene los tipos importantes de BizTalk, tales como tipos de puerto y tipos de mensaje de varias partes, que se usan en este ejemplo. Para ver esta información, haga doble clic en el **OrderProcessServiceType.odx** orquestación. Haga clic en **vista**, haga clic en **otras ventanas**y haga clic en **Vista orquestación**. Expanda **tipos**, expanda **tipos de puerto**y, a continuación, expanda **IOrderProcess**. Verá el **enviar** método. Expanda ese método y verá el **OrderRequest** y **OrderResponse** tipos de puertos. Haga clic en cada tipo de puerto y ver sus **descripción** campos en el Explorador de propiedades y vea el WSDL diferentes mensajes de entrada y salida. Haga clic en **tipos de mensaje de varias partes** y ver el **OrderRequest** y **OrderResponse** tipos de mensaje de varias partes. Haga clic en sus **descripción** campos y ver el WSDL de mensajes de nombres para cada tipo de mensaje.  
  
    -   Se generan dos archivos de esquema. El primer archivo de esquema (**OrderProcessServiceType_biztalk_WCF_basichttpsendadapter_basichttpWCFserviceconsuming.xsd**) define los tipos de mensaje que el ejemplo [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] utiliza el servicio. Usa el **OrderID** campo ambos **OrderRequest** y **OrderResponse** llamadas.  
  
    -   El segundo archivo de esquema (**OrderProcessServiceType_schemas_microsoft_com_2003_10_Serialization.xsd**) exportado por [DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722) para los tipos, elementos y atributos de la espacio de nombres, http://schemas.microsoft.com/2003/10/Serialization/.  
  
    -   Se generan dos archivos de enlace, que se usará más adelante para crear la aplicación de BizTalk: **OrderProcessServiceType.BindingInfo.xml** y **OrderProcessServiceType_Custom.BindingInfo.xml**. En general, usará normalmente el archivo de enlace no personalizado. Sin embargo, en raras situaciones en las que tenga un elemento de enlace personalizado, use el archivo de enlace personalizado. El elemento de enlace personalizado crea puertos de envío para las aplicaciones. Haga doble clic en el **OrderProcessServiceType.BindingInfo.xml** de archivos y busque la **puertoEnvío** línea de definición y revise el puerto de envío que se crearán al importar este enlace de archivos en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
        ```  
        <SendPort Name="WCFSendPort_OrderProcessServiceType_ServiceEndpoint" …  >  
        ```  
  
    -   Estos archivos se usan para que los puertos de envío que usan el adaptador de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] consuman el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] de ejemplo descrito en los metadatos.  
  
## <a name="deploy-the-sample-biztalk-solution-biztalkapp"></a>Implementar la solución de BizTalk de ejemplo, BizTalkApp  
  
1.  Implemente la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de la siguiente forma:  
  
    1.  En Visual Studio, en el Explorador de soluciones, haga clic en **BizTalkApp**y, a continuación, haga clic en **propiedades** .  
  
    2.  En el **Diseñador de proyectos** ventana, haga clic en **implementación** ficha y, a continuación, cambie la **Server** propiedad si utiliza un servidor de base de datos diferente para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Base de datos de administración. Asegúrese de que el nombre de aplicación es **WCFBasicHttpSendAdapter**.  
  
    3.  En Visual Studio, en el Explorador de soluciones, haga clic en **BizTalkApp**y, a continuación, haga clic en **volver a generar**.  
  
    4.  En Visual Studio, en el Explorador de soluciones, haga clic en **BizTalkApp**y, a continuación, haga clic en **implementar**.  Esto implementará el ensamblado Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BizTalkApp en la GAC y los artefactos a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación denominada **WCFBasicHttpSendAdapter**.  
  
2.  Configure un puerto de envío WCF-BasicHttp en la aplicación de BizTalk de la siguiente forma:  
  
    1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
    2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **grupo de BizTalk**, expanda **aplicaciones**, haga clic en **WCFBasicHttpSendAdapter**, seleccione **Importación**y, a continuación, haga clic en **enlaces**.  
  
    3.  En el **importar enlaces** cuadro de diálogo, vaya a la **C:\WCFBasicHttpSendAdapter\BizTalkApp** carpeta, seleccione **OrderProcessServiceType.BindingInfo.xml**y, a continuación, haga clic en **Abiertos**. Este es uno de los archivos de enlace creados por la **Asistente de consumición de servicio WCF de BizTalk** previamente. Esto crea la **WCFSendPort_OrderProcessServiceType_ServiceEndpoint** puerto de envío.  
  
    4.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **WCFBasicHttpSendAdapter**y, a continuación, haga clic en **puertos de envío**.  
  
    5.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en el panel derecho, haga doble clic en **WCFSendPort_OrderProcessServiceType_ServiceEndpoint**, que se creó mediante la importación del archivo de enlace OrderProcessServiceType.BindingInfo.xml. Se abrirá la **propiedades de puerto de envío** cuadro de diálogo.  
  
    6.  En el **propiedades de puerto de envío** cuadro de diálogo, haga clic en **configurar**.  
  
    7.  En el **General** ficha revisión el **dirección (URI)** campo de **http://localhost/BasicHttpWcfServiceConsuming/OrderProcess.svc**. Esta es la dirección del Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] hospedado en IIS al que llamara el adaptador de WCF-BasicHttp.  
  
    8.  Revise el contenido de la **encabezado de acción SOAP/acción** cuadro de texto:  
  
        ```  
        <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
          <Operation Name="Submit" Action="http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming/IOrderProcess/Submit" />  
        </BtsActionMapping>  
        ```  
  
         Este campo indica la intención del mensaje de solicitud SOAP HTTP saliente. Aquí sirve para llamar a la operación de envío en la interfaz IOrderProcess del espacio de nombres Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming.  
  
        > [!NOTE]
        >  El archivo de enlace que el **Asistente de consumición de servicio WCF de BizTalk** genera usa la acción de asignación de formato para la **StaticAction** propiedad. Cuando use enrutamiento por contenidos para adaptadores para enviar mensajes a los servicios WCF de envío de WCF, debe establecer el **BTS. Operación** propiedad en componentes de canalización para el formato de asignación de acciones como el campo que se usará para el enrutamiento por contenidos. De forma alternativa, puede usar el formato de acción única para el enrutamiento por contenidos. En este tutorial, va a usar el formato de acción única. Para obtener más información sobre el formato de acción única y el formato de asignación de acciones, vea la **cuadro de diálogo de propiedades de transporte de WCF-BasicHttp, envío, General** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
    9. Haga clic en **Aceptar** dos veces para volver a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
3.  Cree un puerto de recepción estático unidireccional y una ubicación de recepción ARCHIVOS. Un puerto de recepción es un contenedor lógico para una o más ubicaciones de recepción. Aquí es donde se colocará un mensaje de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] de ejemplo que el adaptador de archivo recogerá y enviará al Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].  
  
    1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **WCFBasicHttpSendAdapter**, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en  **Unidireccional puerto de recepción**.  
  
    2.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **nombre** cuadro de texto, escriba `WCFBasicSendAdapter.ReceivePurchaseOrder`y, a continuación, haga clic en **Aceptar**.  
  
    3.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **WCFBasicHttpSendAdapter.ReceivePurchaseOrder**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción** .  
  
    4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** cuadro de texto, escriba `WCFBasicSendAdapter.ReceivePurchaseOrder.FILE`.  
  
    5.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en el **transporte** junto a la sección **tipo**, seleccione **archivo** en la lista desplegable, y, a continuación, haga clic en **configurar**.  
  
    6.  En el **propiedades de transporte de archivo** cuadro de diálogo la **General** ficha la **carpeta recepción** cuadro de texto, escriba `C:\WCFBasicHttpSendAdapter\OrderRequestIn`y, a continuación, haga clic en **Aceptar**.  
  
    7.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
4.  Cree un filtro para enrutar mensajes al puerto de envío WCF-BasicHttp desde la ubicación de recepción de archivo que ha creado en el paso anterior. Un filtro asociado con un puerto actúa como una cláusula "where" de SQL, de modo que si evalúa el mensaje como true se proporcionará a ese puerto.  
  
    1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **WCFBasicHttpSendAdapter**, haga clic en **puertos de envío**y, a continuación, haga doble clic en **WCFSendPort_OrderProcessServiceType_ ServiceEndpoint**.  
  
    2.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **filtros** ficha, seleccione **BTS. ReceivePortName** en el **propiedad** , escriba `WCFBasicSendAdapter.ReceivePurchaseOrder` en el **valor** campo y, a continuación, haga clic en **Aceptar**. Esta expresión de filtro enruta los mensajes entrantes del puerto de recepción WCFBasicSendAdapter.ReceivePurchaseOrder hasta este puerto de envío WCF-BasicHttp.  
  
5.  Cree dos puertos de envío de archivo para la aplicación de ejemplo. El primer puerto de envío envía mensajes de respuesta de salida al puerto de archivo del Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. El segundo puerto de envío se usa para controlar los mensajes con errores enviados desde el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y destinados al cliente.  
  
    1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **WCFBasicHttpSendAdapter**, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en  **Puerto de envío unidireccional estático**.  
  
    2.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** cuadro de texto, escriba `WCFBasicSendAdapter.SendPurchaseOrder.FILE`.  
  
    3.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **transporte** sección junto a tipo, seleccione **archivo** desde la lista desplegable y, a continuación, haga clic en **configurar** .  
  
    4.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **General** ficha la **carpeta de destino** cuadro de texto, escriba `C:\WCFBasicHttpSendAdapter\OrderResponseOut`y, a continuación, haga clic en **Aceptar** .  
  
    5.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **filtros** ficha, seleccione **BTS. MessageType** en el **propiedad** , escriba `http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWCFServiceConsuming#OrderResponse` en el **valor** campo para especificar el tipo de mensaje de respuesta de la muestra [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio, y a continuación, haga clic en **Aceptar**. Esta expresión de filtro enruta los mensaje de respuesta del Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] de ejemplo para este puerto de envío de archivo. El puerto de envío se suscribe a mensajes de tipo OrderResponse mediante la especificación de ese tipo en la propiedad de filtro. Éste es el tipo de mensaje del mensaje de respuesta del Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].  
  
    6.  En el **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
    7.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **WCFBasicHttpSendAdapter**, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en  **Puerto de envío unidireccional estático**.  
  
    8.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** cuadro de texto, escriba `WCFAdapterErrorSend.FILE`.  
  
    9. En el **propiedades de puerto de envío** cuadro de diálogo, en la **transporte** junto a la sección **tipo**, seleccione **archivo** en la lista desplegable y, a continuación, Haga clic en **configurar**.  
  
    10. En el **propiedades de transporte de archivo** cuadro de diálogo, en la **General** ficha la **carpeta de destino** cuadro de texto, escriba `C:\WCFBasicHttpSendAdapter\WCFAdapterErrorOut\`y, a continuación, haga clic en **Aceptar** .  
  
    11. En el **propiedades de puerto de envío** cuadro de diálogo, en la **filtros** ficha, seleccione **WCF. IsFault** en el **propiedad** , escriba `True` en el **valor** campo y, a continuación, haga clic en **Aceptar**. Dentro de una aplicación se puede detectar una excepción o error activando el **WCF. IsFault** propiedad del mensaje que se envía de vuelta al llamador. Esta propiedad se establecerá en **True** si el mensaje que se envía es un mensaje de error SOAP. Esta expresión de filtro enruta los mensaje con errores del Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] de ejemplo para este puerto de envío de archivo.  
  
6.  Especifique el nombre de host y los enlaces de la aplicación de ejemplo. Para ello:  
  
     En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **WCFBasicHttpSendAdapter**, expanda **orquestaciones**, haga clic en el  **Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BizTalkApp.OrderProcessServiceTypeClient** orquestación, haga clic en **propiedades**, haga clic en **enlaces**, establezca **Host** a **BizTalkServerApplication**y, a continuación, haga clic en **Aceptar** para guardar la configuración.  
  
## <a name="test-the-sample-solution-with-the-wcf-basichttp-send-adapter"></a>Adaptador de envío de prueba de la solución de ejemplo con WCF-BasicHttp  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **WCFBasicHttpSendAdapter**y, a continuación, haga clic en **iniciar**.  
  
2.  En el **iniciar** cuadro de diálogo, haga clic en **iniciar**.  
  
3.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **configuración de plataforma**, expanda **instancias de Host**, haga clic en **BizTalkServerApplication** u otro procede de la instancia de host y, a continuación, haga clic en **reiniciar**.  
  
4.  Abra un símbolo del sistema, escriba **iisreset** para reciclar IIS y sus servicios dependientes y, a continuación, presione ENTRAR.  
  
5.  En el símbolo del sistema, copie **C:\WCFBasicHttpSendAdapter\TestData\WCFBasicSendAdapter.OrderRequest.Sample.xml** a la **C:\WCFBasicHttpSendAdapter\OrderRequestIn** carpeta. Este mensaje se enruta a bidireccional **WcfSendPort_OrderProcessServiceType_ServiceEndpoint** puerto de envío de petición-respuesta estático.  El lado de envío de este bidireccional llamadas del puerto de envío **enviar** método en el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio hospedado en IIS. El resultado se devuelve al puerto de respuesta de la **WcfSendPort_OrderProcessServiceType_ServiceEndpoint** puerto de envío.  El **WCFBasicSendAdapter.SendPurchaseOrder.FILE** puerto de envío tiene una suscripción que se desencadenará cuando el tipo del mensaje es **http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWCFServiceConsuming#OrderResponse**. Obtendrá el mensaje procesado correctamente y escribirlo en el **C:\WCFBasicHttpSendAdapter\OrderResponseOut** carpeta.  
  
6.  Compruebe el **C:\WCFBasicHttpSendAdapter\OrderResponseOut** carpeta para un mensaje de respuesta de la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] servicio.  
  
7.  En el símbolo del sistema, **C:\WCFBasicHttpSendAdapter\TestData\WCFBasicSendAdapter.OrderRequest.Invalid.xml** a la **C:\WCFBasicHttpSendAdapter\OrderRequestIn** carpeta. Este mensaje contiene un espacio de nombres no válido, por lo que el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] devuelve un mensaje de error.  
  
8.  Compruebe el **C:\WCFBasicHttpSendAdapter\WCFAdapterErrorOut** carpeta de un archivo XML que contiene el mensaje de error desde el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] service. Mire el \< **faultstring** \> campo que muestra la causa del mensaje de error como un cuerpo de mensaje no válido.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Publicar servicios WCF con el adaptador WCF-BasicHttp](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [Cómo usar el servicio de WCF de BizTalk consumiendo Asistente para consumir un servicio WCF](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)   
 [Especificación del cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md)