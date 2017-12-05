---
title: 'Paso 4: Configurar el entorno de BizTalk Server para pruebas de carga | Documentos de Microsoft'
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f336c5f-5a18-493d-8fc0-a8a475ab47b3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2e8b2b3751f31401ef0353944be0bdad3cbb2b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-4-configure-biztalk-server-environment-for-load-testing"></a>Paso 4: Configurar el entorno de BizTalk Server para pruebas de carga
Este tema proporciona información para crear las ubicaciones de recepción de BizTalk Server, puertos de recepción y puertos de envío necesarios para ejecutar el código de ejemplo que se describen en los temas [paso 1: crear una prueba unitaria para enviar documentos a BizTalk Server](~/technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md) y [paso 3: crear una prueba de carga para llevar a cabo varias pruebas unitarias simultáneamente](~/technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md).  
  
## <a name="configure-biztalk-server-environment-for-load-tests"></a>Configurar el entorno de BizTalk Server para pruebas de carga  
 Como se describe en el tema [paso 3: crear una prueba de carga para realizar pruebas de unidad varios simultáneamente](~/technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md), la prueba de carga **BTS_Messaging_Step** está configurado para ejecutar las pruebas unitarias  **BTSMessaging** y **BTSMessaging2**. A su vez, estas pruebas unitarias cargar una copia del mensaje C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml y enviarlo a los puntos de conexión **BTSMessagingEP** y **BTSMessagingEP2** tal como se define en la siguiente sección del archivo de configuración (app.config) de aplicación del proyecto:  
  
 \<\!--BTSMessagingEP--\>\<extremo address="net.tcp://*equipo de BizTalk Server*: 8123/btsloadtest" enlace = "netTcpBinding" bindingConfiguration = contrato de "netTcpBinding" = " System.ServiceModel.Channels.IRequestChannel"nombre ="BTSMessagingEP"/\>\<extremo address="net.tcp://*equipo de BizTalk Server*: 8123/btsloadtest "enlace ="netTcpBinding" bindingConfiguration = "netTcpBinding" contract="System.ServiceModel.Channels.IRequestChannel" nombre = "BTSMessagingEP2" /                  \>  
  
> [!NOTE]
>  Como se indicó anteriormente, *equipo de BizTalk Server* es un marcador de posición para los nombres de equipo de servidor BizTalk Server reales o, en el caso de que los equipos de servidor de BizTalk están configurados como miembros de un clúster de equilibrio de carga de red (NLB); *Equipo de BizTalk Server* es un marcador de posición para el nombre o la dirección del servidor virtual de NLB correspondiente.  
  
 Para fines de este ejemplo, se utilizaron los dos equipos con BizTalk Server y la base de datos de cuadro de mensaje de BizTalk Server estaba en un equipo remoto de SQL Server.  
  
### <a name="create-biztalk-server-send-and-receive-hosts"></a>Crear el envío de BizTalk Server y Hosts de recepción  
 Siga los pasos descritos en el tema de documentación de BizTalk Server [cómo crear un nuevo Host](http://go.microsoft.com/fwlink/?LinkId=208595) (http://go.microsoft.com/fwlink/?LinkId=208595) para crear un host de BizTalk Server "Enviar" para puertos de envío y los controladores de adaptador de envío. Configurar el host con las siguientes propiedades:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|Nombre|TxHost|  
|Tipo|En curso|  
|Permitir el seguimiento de host|Asegúrese de que esta casilla no está marcada.|  
|autenticación de confianza|Asegúrese de que esta casilla no está marcada.|  
|sólo de 32 bits|Asegúrese de que esta casilla no está marcada.|  
|Establecer este host como predeterminado del grupo|Asegúrese de que esta casilla no está marcada.|  
|Grupo de Windows|El grupo de Windows que se usa para controlar el acceso a este host y las instancias de host asociadas. El grupo de ventana creado para el host en proceso predeterminado se denomina cualquiera  *\<nombre_equipo\>*\BizTalk usuarios de la aplicación (para un solo servidor instalación de BizTalk Server) o  *\<Nombre de dominio\>*\BizTalk usuarios de la aplicación (para una instalación de BizTalk Server, que requiere el uso de grupos de dominio con varios servidores). **Nota:***\<nombre_equipo\>*  y  *\<nombre de dominio\>*  son marcadores de posición para el nombre real del equipo o el nombre de dominio se utiliza cuando se creó el grupo.   <br /><br /> Si se crea un nuevo grupo para este host, que debe tener los privilegios descritos en el tema [grupos Host](http://go.microsoft.com/fwlink/?LinkId=208803) (http://go.microsoft.com/fwlink/?LinkId=208803) en la documentación de BizTalk Server.|  
  
 Repita los pasos que seguir al crear el host de "Envío" para crear un host de "Recepción". Configurar el host de "Receive" con los valores de propiedad siguientes:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|Nombre|RxHost|  
|Tipo|En curso|  
|Permitir el seguimiento de host|Asegúrese de que esta casilla no está marcada.|  
|autenticación de confianza|Asegúrese de que esta casilla no está marcada.|  
|sólo de 32 bits|Asegúrese de que esta casilla no está marcada.|  
|Establecer este host como predeterminado del grupo|Asegúrese de que esta casilla no está marcada.|  
|Grupo de Windows|El grupo de Windows que se usa para controlar el acceso a este host y las instancias de host asociadas. El grupo de ventana creado para el host en proceso predeterminado se denomina cualquiera  *\<nombre_equipo\>*\BizTalk usuarios de la aplicación (para un solo servidor instalación de BizTalk Server) o  *\<Nombre de dominio\>*\BizTalk usuarios de la aplicación (para una instalación de BizTalk Server, que requiere el uso de grupos de dominio con varios servidores). **Nota:***\<nombre_equipo\>*  y  *\<nombre de dominio\>*  son marcadores de posición para el nombre real del equipo o el nombre de dominio se utiliza cuando se creó el grupo.   <br /><br /> Si se crea un nuevo grupo para este host, que debe tener los privilegios descritos en el tema [grupos Host](http://go.microsoft.com/fwlink/?LinkId=208803) (http://go.microsoft.com/fwlink/?LinkId=208803) en la documentación de BizTalk Server.|  
  
### <a name="create-instances-of-the-biztalk-server-send-and-receive-hosts"></a>Crear instancias de envío de BizTalk Server y Hosts de recepción  
 Siga los pasos descritos en el tema de documentación de BizTalk Server [cómo agregar una instancia de Host](http://go.microsoft.com/fwlink/?LinkId=208596) (http://go.microsoft.com/fwlink/?LinkId=208596) para crear e iniciar instancias de host de BizTalk Server "Enviar". Configurar una instancia de host de "Envío" ejecutar en cada servidor BizTalk Server en el grupo de BizTalk Server y configurar cada instancia de host con los valores de propiedad siguientes:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|**Nombre de host**|Seleccione **TxHost** en la lista desplegable lista situada junto al **nombre de Host**.|  
|**Server**|Seleccione el servidor de BizTalk que se ejecutará esta instancia de host de la lista desplegable junto a **Server**.|  
|**Inicio de sesión**|1.  Haga clic en el **configurar** botón para mostrar el **las credenciales de inicio de sesión** cuadro de diálogo.<br />2.  En el **las credenciales de inicio de sesión** cuadro de diálogo Escriba los siguientes valores para las propiedades especificadas:<br />     **Propiedad**<br />     **Inicio de sesión**: nombre de cuenta de usuario que sea miembro del grupo de Windows asociado a este host de BizTalk Server.<br />     **Contraseña**: contraseña para la cuenta de usuario especificada en el **inicio de sesión** cuadro de texto.<br />3.  Haga clic en **Aceptar** para cerrar el **las credenciales de inicio de sesión** cuadro de diálogo.|  
|**Deshabilitar la instancia de host se inicie.**|Asegúrese de que esta casilla no está marcada.|  
  
 Después de crear la instancia de host, haga doble clic en la instancia de host y seleccione **iniciar** en el menú contextual.  
  
 Repita los pasos que seguir al crear las instancias de host de "Envío" para crear instancias de host de "Recepción". Configurar una instancia de host de "Recepción" ejecutar en cada servidor BizTalk Server en el grupo de BizTalk Server y configurar cada instancia de host con los valores de propiedad siguientes:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|Nombre de host|Seleccione **RxHost** en la lista desplegable lista situada junto al **nombre de Host**.|  
|Server|Seleccione el servidor de BizTalk que se ejecutará esta instancia de host de la lista desplegable junto a **Server**.|  
|Inicio de sesión|1.  Haga clic en el **configurar** botón para mostrar el **las credenciales de inicio de sesión** cuadro de diálogo.<br />2.  En el **las credenciales de inicio de sesión** cuadro de diálogo Escriba los siguientes valores para las propiedades especificadas:<br />     **Propiedad**<br />     **Inicio de sesión**: nombre de cuenta de usuario que sea miembro del grupo de Windows asociado a este host de BizTalk Server.<br />     **Contraseña**: contraseña para la cuenta de usuario especificada en el **inicio de sesión** cuadro de texto.<br />3.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo de credenciales de inicio de sesión.|  
|Deshabilitar inicio de instancia de host|Asegúrese de que esta casilla no está marcada.|  
  
 Después de crear la instancia de host, haga doble clic en la instancia de host y seleccione **iniciar** en el menú contextual.  
  
### <a name="create-a-biztalk-server-receive-port"></a>Crear un servidor BizTalk Server puerto de recepción  
 Siga los pasos descritos en el tema [cómo crear un puerto de recepción](http://go.microsoft.com/fwlink/?LinkID=154843) (http://go.microsoft.com/fwlink/?LinkID=154843) en la documentación de BizTalk Server para crear un puerto de recepción unidireccional. Al crear el puerto de recepción, deje todas las propiedades en valores predeterminados, excepto como se indica en la tabla siguiente:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|General\Name|BTSLoadTestMessaging.OneWay.ReceivePort|  
|Tipo de General\Port|Unidireccional|  
|General\Authentication|Sin autenticación|  
|General\Enable enrutamiento para mensajes con errores|Asegúrese de que esta casilla no está marcada.|  
|General\Description|Deje en blanco|  
|Asignaciones de entrada|Ninguno|  
|Seguimiento|Asegúrese de que todas las casillas sin control.|  
|Ubicaciones de recepción|Haga clic en **New**, se mostrará el **propiedades de la ubicación de recepción** cuadro de diálogo que debe configurarse como se describe en la sección siguiente, **crear una ubicación de recepción de BizTalk Server** .|  
  
### <a name="create-a-biztalk-server-receive-location"></a>Crear un servidor BizTalk Server ubicación de recepción  
 En el **propiedades de la ubicación de recepción** muestra el cuadro de diálogo al crear el puerto de recepción de BizTalk Server, se aplican los valores de propiedad especificado:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|Nombre:|BTSLoadTest.Messaging.OneWay.WCF Customer.ReceiveLocation|  
|Controlador de recepción:|RxHost|  
|Canalización de recepción:|PassThruReceive|  
|Descripción:|Déjelo en blanco|  
|Tipo:|Seleccione **WCF-Custom** desde la lista desplegable y, a continuación, haga clic en el **configurar** botón, se mostrará el **propiedades de transporte de WCF-Custom** cuadro de diálogo que debería ser configurado como se describe en la sección siguiente, **configurar el transporte de recepción WCF-Custom**.|  
  
### <a name="configure-the-wcf-custom-receive-transport"></a>Configurar el transporte de recepción WCF-Custom  
 En el **propiedades de transporte de WCF-Custom** muestra el cuadro de diálogo al crear la ubicación de recepción de BizTalk Server, deje todas las propiedades en valores predeterminados, excepto como se indica en la tabla siguiente:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|General\Address (URI)|NET. TCP://localhost: 8123/btsloadtest|  
|Tipo de Binding\Binding|netTcpbinding|  
|Binding\NetTcpBindingElement\listenBacklog|400|  
|Binding\NetTcpBindingElement\maxConnections|400|  
|Binding\Security\NetTcpSecurityElement\mode|Ninguno|  
|Behavior\ServiceBehavior\serviceThrottling\ServiceThrottlingElement **Nota:** para agregar el comportamiento de serviceThrottling a la lista de comportamientos, ServiceBehavior del menú contextual, haga clic en **Agregar extensión**, seleccione **serviceThrottling** en la lista de extensiones de comportamiento y, a continuación, haga clic en **Aceptar**.|Establecer el **ServiceThrottlingElement** propiedades a los valores siguientes:<br /><br /> -   **maxConcurrentCalls** 400<br />-   **maxConcurrentInstances** 400<br />-   **maxConcurrentSessions** 400|  
|Behavior\ServiceBehavior\serviceDebug\ServiceDebugElement **Nota:** para agregar el comportamiento de serviceDebug a la lista de comportamientos, ServiceBehavior del menú contextual, haga clic en **Agregar extensión**, seleccione **serviceDebug** en la lista de extensiones de comportamiento y, a continuación, haga clic en **Aceptar**.|Deje la lista de **ServiceDebugElement** propiedades en sus valores predeterminados (vacíos) excepto las propiedades siguientes, que deben cambiarse a un valor de True:<br /><br /> -   **httpHelpPageEnabled** True<br />-   **httpsHelpPageEnabled** True<br />-   **includeExceptionDetailInFaults** True|  
  
 Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte de WCF-Custom y, a continuación, haga clic en **Aceptar** otra vez para cerrar el cuadro de diálogo Propiedades de la ubicación de recepción.  
  
### <a name="create-a-biztalk-server-send-port"></a>Crear un puerto de envío de BizTalk Server  
 Siga los pasos descritos en el tema [cómo crear un puerto de envío](http://go.microsoft.com/fwlink/?LinkID=154845) (http://go.microsoft.com/fwlink/?LinkID=154845) en la documentación de BizTalk Server para crear un **unidireccional estático** puerto de envío. Al crear el puerto de envío, deje todas las propiedades en valores predeterminados, excepto como se indica en la tabla siguiente:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|General\Name|BTSLoadTest.Messaging.Send.WCF-Custom|  
|Controlador General\Send|TxHost|  
|Canalización de General\Send|PassThruTransmit|  
|Filters\Name|BTS.ReceivePortName|  
|Filters\Operator|==|  
|Filters\Value|BTSLoadTest.Messaging.OneWay.ReceivePort|  
|Filters\Group por|Y **Nota:** si estas propiedades se configuran con los valores correctos, el filtro debe mostrarse como `BTS.ReceivePortName == BTSLoadTest.Messaging.OneWay.ReceivePort` tal como se muestra en la parte inferior de la página filtros del cuadro de diálogo Propiedades de puerto de envío b Ox. Como resultado de aplicar este filtro, este puerto de envío se suscribe a cualquier mensaje recibido por BizTalk Server a través del puerto de recepción denominado BTSLoadTest.Messaging.OneWay.ReceivePort.|  
|Seguimiento|Asegúrese de que todas las casillas sin control.|  
|General\Type|Seleccione **WCF-Custom** desde la lista desplegable y, a continuación, haga clic en el **configurar** botón, se mostrará el **propiedades de transporte de WCF-Custom** cuadro de diálogo que debería ser configurado como se describe en la sección siguiente, **configurar el transporte de envío WCF-Custom**.|  
  
### <a name="configure-the-wcf-custom-send-transport"></a>Configurar el transporte de envío WCF-Custom  
 En el **propiedades de transporte de WCF-Custom** muestra el cuadro de diálogo al crear el puerto de envío de BizTalk Server, deje todas las propiedades en valores predeterminados, excepto como se indica en la tabla siguiente:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|General\Address (URI)|NET.TCP://*\<nombre_equipo\>*: 2001/TCP1 **importante:***\<nombre_equipo\>*  es un marcador de posición en el nombre de equipo real utilizado para hospedar IndigoService.exe, que está diseñado para consumir mensajes enviados a través de WCF.   Dado que IndigoService.exe requiere recursos muy poco, a menudo es absolutamente aceptable para ejecutar IndigoService.exe en el equipo de SQL Server que se utiliza para las bases de datos del grupo de BizTalk Server. IndigoService.exe forma parte del Asistente para prueba comparativa de BizTalk, que está disponible en [Asistente para prueba comparativa](http://go.microsoft.com/fwlink/?LinkID=186347) (http://go.microsoft.com/fwlink/?LinkID=186347).|  
|Tipo de Binding\Binding|**customBinding**|  
  
 Al igual que con la mayoría de los tipos de enlace de WCF-Custom, la **customBinding** tipo de enlace expone varias propiedades, que se deben establecer en los siguientes valores:  
  
1.  En el **enlace** sección hay un **CustomBindingElement** propiedad con un asociado **configuración** sección. Dejar todos los valores en la sección de configuración para el **CustomBindingElement** propiedad en sus valores predeterminados.  
  
2.  A continuación, en **CustomBindingElement** haga **textMessageEncoding** y seleccione **quitar extensión (SUPR)**. Del mismo modo, haga clic en **httpTransport** y seleccione **quitar extensión (SUPR)**.  
  
3.  Ahora haga clic en **CustomBindingElement** y seleccione **Agregar extensión Ins** para mostrar la **Seleccionar extensión de elemento de enlace** cuadro de diálogo.  
  
4.  Seleccione **binaryMessageEncoding** y haga clic en **Aceptar** para agregar la **binaryMessageEncoding** extensión de elemento. Repita los pasos para mostrar el **Seleccionar extensión de elemento de enlace** cuadro de diálogo y desplácese hacia abajo la lista de extensiones de elementos disponibles hasta que vea el **tcpTransport** extensión de elemento, seleccione **tcpTransport** y haga clic en **Aceptar**.  
  
5.  En **CustomBindingElement** seleccione la **tcpTransport** elemento y en la sección de configuración para **tcpTransport**, deje todas las propiedades en valores predeterminados excepto como en la siguiente tabla se incluyen:  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |connectionBufferSize|2097152|  
    |maxBufferSize|2097152|  
    |maxPendingAccepts|400|  
    |maxPendingConnections|400|  
    |listenBacklog|400|  
    |maxBufferPoolSize|2097152|  
    |maxReceivedMessageSize|2097152|  
  
6.  En el **tcpTransport** elemento select la **ConnectionPoolSettings** elemento y deja todas las propiedades en de forma predeterminada los valores excepto para la **maxOutboundConnectionsPerEndpoint** propiedad, que debe cambiarse a un valor de 400.  
  
7.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo Propiedades de transporte de WCF-Custom, a continuación, haga clic en **Aceptar** otra vez para cerrar el BTSLoadTest.Messaging.Send.WCF-Custom: cuadro de diálogo de propiedades de puerto de envío.  
  
### <a name="configure-a-computer-to-consume-messages-sent-by-the-biztalk-server-send-port"></a>Configurar un equipo para consumir mensajes enviados por el puerto de envío de BizTalk Server  
 Como se describió anteriormente, la IndigoService.exe está diseñado para consumir mensajes enviados a través de WCF. IndigoService.exe forma parte del Asistente para prueba comparativa de BizTalk, que está disponible en [Asistente para prueba comparativa](http://go.microsoft.com/fwlink/?LinkID=186347) (http://go.microsoft.com/fwlink/?LinkID=186347). La manera más fácil de configurar y ejecutar IndigoService.exe para fines de este ejemplo es simplemente Descargue el archivo zip de Asistente para la prueba comparativa de BizTalk desde el [página de descarga del Asistente para prueba comparativa](http://go.microsoft.com/fwlink/?LinkID=209100) (http://go.Microsoft.com/fwlink/?) LinkID = 209100) y extraiga los archivos siguientes 4 en el equipo que desea ejecutar IndigoService.exe:  
  
1.  \IndigoService\bin\Release\IndigoService.exe  
  
2.  \IndigoService\bin\Release\IndigoService.exe.config  
  
3.  \IndigoService\bin\Release\Response.Xml  
  
4.  \IndigoService\bin\Release\StartIndigoService.bat  
  
 A continuación, inicie IndigoService.exe haciendo doble clic en StartIndigoService.bat. IndigoService.exe consume mensajes enviados al extremo especificado en el archivo IndigoService.exe.config:  
  
 \<dirección del extremo = "NET. TCP://localhost: 2001/TCP1" enlace = "netTcpBinding" bindingConfiguration = "Binding1" name = "endpoint1" contract="IndigoService.IServiceTwoWaysVoidNonTransactional" /\>  
  
 Por lo tanto, la dirección del puerto de envío está configurada con una dirección (URI) de net.tcp://*\<nombre_equipo\>*: 2001/TCP1  
  
 Dado que IndigoService.exe requiere recursos muy poco, a menudo es absolutamente aceptable para ejecutar IndigoService.exe en el equipo de SQL Server que se utiliza para las bases de datos de BizTalk Server.  
  
### <a name="disable-tracking-and-throttling-for-the-biztalk-server-group"></a>Deshabilitar el seguimiento y la limitación del grupo de BizTalk Server  
 Para determinar el rendimiento sostenible máximo absoluto del sistema, mensajes de seguimiento y la limitación se deben deshabilitar antes de comenzar las pruebas de carga. Esto puede hacerse mediante la consola de administración de BizTalk Server, siga estos pasos:  
  
1.  Inicie la consola de administración de BizTalk Server. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **BizTalk Server 2010** y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En **administración de BizTalk Server**, seleccione el grupo de BizTalk si aparece o si no aparece, haga clic en **administración de BizTalk Server**, seleccione **conectar a grupo existente** , escriba el nombre de SQL Server que aloja la base de datos de administración de BizTalk Server del grupo de BizTalk junto a **nombre de SQL Server:**, escriba el nombre del nombre de base de datos de administración del grupo de BizTalk junto a **Nombre de base de datos:** y, a continuación, haga clic en **Aceptar**.  
  
3.  Haga clic en el nodo de grupo de BizTalk y seleccione **configuración** para mostrar la **panel de configuración de BizTalk**.  
  
4.  Haga clic para seleccionar **Hosts** en el panel izquierdo del panel de configuración de BizTalk.  
  
5.  Haga clic en la lista desplegable junto a **Host** para seleccionar uno de los hosts que se utilizará durante las pruebas de rendimiento.  
  
6.  Deje propiedades en sus valores predeterminados excepto como se indicó en la tabla siguiente:  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |**General\Move datos de seguimiento a DTA DB**|Desactive esta casilla si está activada.|  
    |**Solo para General\32 bits**|Desactive esta casilla si está activada.|  
    |**General\Polling Intervals\Messaging**|Establecer en un valor de 20000000|  
    |**General\Polling Intervals\Orchestrations**|Establecer en un valor de 20000000|  
    |**Mensajes de proceso Throttling\In basada en recursos**|Establecer en un valor de 10.000|  
    |**Tamaño de la cola del mensaje de Throttling\Internal basada en recursos**|Establecer en un valor de 10.000|  
    |**Recuento de Throttling\Message basada en recursos de base de datos**|Establecer en un valor de 0|  
    |**Basada en recursos Throttling\Memory Usage\Process virtual**|Establecer en un valor de 0|  
    |**Invalidación de Throttling\Publishing\Throttling basada en tasas**|Establecer para no limitar|  
    |**Invalidación de Throttling\Delivery\Throttling basada en tasas**|Establecer para no limitar|  
  
7.  Repita el procedimiento descrito en el paso 6 para todos los hosts que se usará durante el transcurso de las pruebas de rendimiento.  
  
8.  Haga clic para seleccionar **instancias de Host** en el panel izquierdo del panel de configuración de BizTalk.  
  
9. Haga clic en la lista desplegable junto a **instancia de Host:** para seleccionar una de las instancias de host que se usará para las pruebas de rendimiento.  
  
10. Deje los valores de propiedad en su configuración predeterminada excepto el cambio el **.NET CLR máximo de subprocesos de trabajo** en un valor de **100** y cambie el **subprocesos de trabajo de .NET CLR mínimo** a un valor de **25**.  
  
11. Repita el procedimiento descrito en el paso 10 para cada instancia de host que se usará durante el transcurso de las pruebas de rendimiento.  
  
 Aunque deshabilitar el seguimiento y la limitación de ningún modo representan lo que debe realizarse en un escenario de producción, porque estas operaciones son tan caras desde una perspectiva del rendimiento tiene sentido deshabilitarlas para averiguar el sostenible máximo es true Rendimiento (MST) de un entorno de BizTalk Server. Esto permite que los evaluadores ver claramente el impacto de rendimiento de cualquier ajuste que se ha aplicado en el entorno de. Por supuesto, puede hacerse un argumento que no se debe deshabilitar el seguimiento y si sabe que la aplicación de BizTalk Server requerirá seguimiento desde el principio, a continuación, se debe habilitar el seguimiento. Dicho esto, **todo lo posible debe realizarse para deshabilitar la limitación para fines de pruebas de rendimiento**. Limitación es muy útil para evitar que un servidor BizTalk Server "caer" debido a una carga excesiva en un entorno de producción. Sin embargo, no desea habilitar durante las pruebas de rendimiento porque es un gran impacto sobre el rendimiento y porque si limitación aparece durante una prueba de carga, tendrá un tiempo muy difícil determinar qué nivel de rendimiento de limitación su Realmente puede conseguir la aplicación de BizTalk Server. Los temas siguientes describen cómo realizar pruebas de carga de paso para insertar el entorno de BizTalk Server más allá de MST y, a continuación, tome real MST con pruebas de carga constante. Si está habilitada la limitación se resultaba casi imposible insertar el entorno de BizTalk más allá de MST para que a su vez podría detectar qué el true es MST.