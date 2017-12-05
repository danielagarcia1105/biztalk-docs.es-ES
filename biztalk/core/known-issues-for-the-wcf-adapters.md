---
title: Problemas conocidos de los adaptadores de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 423c6021-5fb7-48c9-9319-11e7a18c775c
caps.latest.revision: "54"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c296dfb2ca1f05a2f403aa31a73b67934fb23a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-for-the-wcf-adapters"></a>Problemas conocidos de los adaptadores de WCF
En este tema se describe los problemas conocidos de los adaptadores WCF incluidos con BizTalk Server.  
  
## <a name="a-message-that-fails-in-the-inbound-soap-marshaling-processing-is-not-suspended-in-wcf-receive-adapters"></a>Un mensaje que produce error en el procesamiento del cálculo de referencia de SOAP entrante no se suspende en los adaptadores de recepción WCF.  
 Cuando un mensaje llega a un adaptador de recepción WCF, el adaptador de WCF crea un mensaje de BizTalk desde el mensaje SOAP entrante y, a continuación, pasa el mensaje de BizTalk al proxy de transporte, administrado por el Gestor extremo. Si se produce un error en el adaptador al leer el sobre y el cuerpo SOAP durante la creación del mensaje de BizTalk, el mensaje no se suspende debido a que el adaptador usa el lector rápido, no almacenado en caché y progresivo para obtener acceso al mensaje SOAP.  
  
 Debe comprobar el mensaje con errores en el registro de eventos. Por ejemplo, puede usar una expresión de ruta de cuerpo en el **mensajes** ficha en el cuadro de diálogo de propiedades WCF adaptador transporte para especificar cómo crear el cuerpo del mensaje de BizTalk entrante de un mensaje SOAP entrante a través del adaptador WCF. Cuando se suministra una expresión de ruta de cuerpo no válido para el mensaje SOAP entrante en el **mensajes** pestaña, el adaptador no se puede crear el mensaje de BizTalk y no se puede suspender el mensaje entrante. Para obtener más información acerca de cómo utilizar la expresión de ruta de acceso de cuerpo en el **mensajes** pestaña, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).  
  
 La siguiente ilustración muestra la **mensajes** ficha en el que puede especificar cómo crear mensajes de BizTalk entrantes desde los mensajes SOAP entrantes.  
  
## <a name="a-message-that-fails-in-the-inbound-soap-marshaling-processing-is-not-suspended-in-wcf-send-adapters"></a>Un mensaje que produce error en el procesamiento del cálculo de referencia de SOAP entrante no se suspende en los adaptadores de envío WCF.  
 Un puerto de petición-respuesta de WCF puede recibir un mensaje WCF como mensaje de respuesta. Cuando el mensaje llega al adaptador de envío WCF, el adaptador de WCF crea el mensaje de BizTalk desde el mensaje SOAP entrante y, a continuación, pasa el mensaje de BizTalk al proxy de transporte, que es administrado por el Gestor extremo. Si se produce un error en el adaptador al leer el sobre y el cuerpo SOAP durante la creación del mensaje de BizTalk, el mensaje no se suspende debido a que el adaptador usa el lector rápido, no almacenado en caché y progresivo para obtener acceso al mensaje SOAP.  
  
 Debe comprobar el mensaje con errores en el registro de eventos. Por ejemplo, puede usar una expresión XPath en el **mensajes** ficha en el cuadro de diálogo de propiedades WCF adaptador transporte para especificar cómo crear el cuerpo del mensaje de BizTalk entrante de un mensaje SOAP entrante a través del adaptador WCF. Cuando se suministra una expresión XPath no válida para el mensaje SOAP entrante en el **mensajes** pestaña, el adaptador no se puede crear el mensaje de BizTalk y no se puede suspender el mensaje entrante. Para obtener más información acerca de cómo utilizar la expresión XPath en el **mensajes** pestaña, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).  
  
 La siguiente ilustración muestra la **mensajes** pestaña del adaptador de envío WCF-NetNamedPipe como un ejemplo.  
  
 ![Adaptadores de envío de la pestaña mensajes en WCF](../core/media/54623ccf-49a9-4b6a-9487-da0d94bab64d.gif "54623ccf-49a9-4b6a-9487-da0d94bab64d")  
  
## <a name="messages-can-be-lost-when-using-onewaybindingelement-in-a-two-way-transport-with-custom-binding-in-non-transactional-wcf-receive-locations"></a>Los mensajes se pueden perder al usar OneWayBindingElement en un transporte bidireccional con enlace personalizado en ubicaciones de recepción no transaccionales WCF.  
 En una comunicación bidireccional, los adaptadores de WCF seguirán devolviendo la respuesta hasta que los mensajes no se hayan guardado en la base de datos de cuadro de mensajes. No obstante, el uso **OneWayBindingElement** genera una respuesta ficticia inmediatamente antes de enviar el mensaje recibido al adaptador de WCF. Por lo tanto, si configura un enlace personalizado con un **OneWayBindingElement** en la pila de canales para el transporte bidireccional en no transaccionales, ubicaciones de recepción, se pueden perder mensajes porque los adaptadores de WCF procesan los datos recibidos mensajes de forma unidireccional.  
  
## <a name="default-values-of-the-readerquotas-attributes-in-the-wcf-custom-and-wcf-customisolated-transport-properties-dialog-boxes-are-used-when-constructing-the-bindings"></a>Al construir los enlaces, se usan los valores predeterminados de los atributos de ReaderQuotas del cuadro de diálogo Propiedades de transporte de los adaptadores de WCF-Custom y WCF-CustomIsolated.  
 Cuadros de diálogo de propiedades de transporte de WCF-Custom y WCF-CustomIsolated la **ReaderQuotas** valores de atributo se muestran como cero. No obstante, al construir los enlaces, se usan los siguientes valores:  
  
|Attribute|Description|Valor|  
|---------------|-----------------|-----------|  
|maxArrayLength|Un entero positivo que especifica la longitud máxima permitida de matriz.|16384|  
|maxBytesPerRead|Un entero positivo que especifica el número máximo permitido de bytes devueltos por lectura.|4096|  
|maxDepth|Un entero positivo que especifica la profundidad máxima de anidación de nodos por lectura.|32|  
|maxNameTableCharCount|Un entero positivo que especifica el número máximo permitido de caracteres en un nombre de tabla.|16384|  
|maxStringContentLength|Un entero positivo que especifica el número máximo permitido de caracteres en el contenido de un elemento XML.|8192|  
  
## <a name="the-wcf-receive-locations-may-be-disabled-if-you-change-the-wcf-adapter-type-and-keep-the-same-address"></a>Las ubicaciones de recepción WCF pueden deshabilitarse si se cambia el tipo de adaptador de WCF y se mantiene la misma dirección.  
 Si cambia el tipo de adaptador, por ejemplo, cambiar el tipo de adaptador WCF de WCF-NetTcp a WCF-Custom con el enlace NetTcp y mantener la misma dirección, la ubicación de recepción puede deshabilitarse debido al problema de almacenamiento en caché en el Administrador de punto de conexión. Para solucionar este problema, puede llevar a cabo uno de los siguientes procedimientos:  
  
-   Reiniciar el servicio BTSNTSvc.  
  
-   Cambiar el URI a una dirección diferente y guardarlo y, a continuación, volver a cambiar el URI a la dirección original y volver a guardarlo.  
  
## <a name="the-wcf-action-set-in-the-orchestration-does-not-override-the-action-setting-in-the-static-send-port"></a>La acción WCF establecida en la orquestación no sobrescribe la configuración de la acción del puerto de envío estático.  
 Si establece la **WCF. Acción** propiedad de contexto en la orquestación, debe dejar el **acción** campo en blanco en el cuadro de diálogo de propiedades de transporte WCF adaptador. Si también especifica una acción en el puerto de envío estático, el **WCF. Acción** propiedad de contexto se establece en la orquestación se reemplazará por el valor establecido en el puerto de envío estático.  
  
## <a name="propagating-a-fault-message-is-not-supported-in-the-transactional-send"></a>La propagación de un mensaje de error no es compatible en el envío transaccional.  
 El **propagar mensaje de error** opción en los puertos de envío de petición-respuesta le permite enrutar los mensajes que se producirá un error en el procesamiento de salida a una aplicación de suscripción. Sin embargo, si la **Habilitar transacciones** también se selecciona la casilla de verificación en el cuadro de diálogo de propiedades de transporte y la transacción se anula o no se puede usar cuando la respuesta de error llega al adaptador, no podrá propagar el mensajes de error en cualquier aplicación de suscripción.  
  
## <a name="the-msmq-cluster-resource-group-needs-to-be-restarted-before-restarting-the-biztalk-host-cluster-resource-group-during-the-cluster-failover"></a>El grupo de recursos de clúster MSMQ debe reiniciarse antes de que se reinicie el grupo de recursos de clúster Host de BizTalk durante la conmutación por error del clúster.  
 En un escenario de conmutación por error del clúster, cuando tiene lugar una conmutación por error, el grupo de recursos de clúster MSMQ debe reiniciarse antes de que se reinicie el grupo de recursos de clúster Host de BizTalk. Si se produce un error al hacerlo, puede que se deshabiliten las ubicaciones de recepción de MSMQ. Para solucionar este problema, puede hacer que el grupo de recursos de clúster BizTalk Host dependa del grupo de recursos de clúster de MSMQ para asegurarse de que el grupo de recursos de clúster MSMQ se inicie antes que el grupo de recursos de clúster BizTalk Host. De forma alternativa, puede reiniciar el grupo de recursos de clúster BizTalk Host para solucionar este problema.  
  
## <a name="you-receive-an-error-when-sending-messages-to-a-wcf-service-that-uses-wsfederationhttpbinding-in-the-endpoint"></a>Recibe un error al enviar mensajes a un Servicio WCF que use wsFederationHttpBinding en el extremo.  
 Recibe un error parecido al siguiente:  
  
```  
The adapter failed to transmit message going to send port "MySendPort" with URL "http://localohost/MywsFedHttp". It will be retransmitted after the retry interval specified for this Send Port. Details:"The channel is configured to use interactive initializer 'System.ServiceModel.Security.InfocardInteractiveChannelInitializer', but the channel was Opened without calling DisplayInitializationUI.  Call DisplayInitializationUI before calling Open or other methods on this channel.".  
```  
  
 Este comportamiento es así por diseño. Adaptadores de WCF no pueden enviar mensajes a los servicios WCF que usan **wsFederationHttpBinding** en sus extremos.  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-enable-you-to-select-message-types-or-port-types-from-the-wsdl"></a>El Asistente para consumición del Servicio WCF de BizTalk no permite seleccionar tipos de mensajes o tipos de puertos desde WSDL.  
 El Asistente para consumición del Servicio WCF de BizTalk no permite seleccionar tipos de mensajes o tipos de puertos desde WSDL al importar los servicios WCF. Para solucionar esta limitación, puede usar el siguiente código para obtener los esquemas y, a continuación, agregar los esquemas deseados a sus proyectos de BizTalk:  
  
```  
svcutil.exe /t:metadata http://service/metadataendpoint  
```  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-allow-the-combination-of-one-way-and-request-response-operations"></a>El Asistente para consumición del Servicio WCF de BizTalk no permite la combinación de operaciones de petición-respuesta y unidireccionales.  
 El Asistente para consumición del Servicio WCF de BizTalk no permite importar los tipos de puerto que tengan una combinación de operaciones de petición-respuesta y unidireccionales. Para solucionar esto, puede usar la herramienta de utilidad de metadatos del modelo de servicio para generar los tipos de puerto.  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-allow-you-to-set-certificate-credentials-when-retrieving-the-wsdl"></a>El Asistente para consumición del Servicio WCF de BizTalk no permite establecer credenciales al recuperar el WSDL.  
 El Asistente para consumición del Servicio WCF de BizTalk no permite establecer credenciales de certificado al recuperar el WSDL. Para resolver este problema, puede usar la herramienta de utilidad de metadatos de ServiceModel para generar el WSDL y XSD archivos desde los servicios WCF que se va a utilizar con las credenciales de certificado configurado en el archivo svcutil.exe.config y, a continuación, importación en el servicio de WCF de BizTalk Asistente para consumición eligiendo **archivos de metadatos (WSDL y XSD)** opción en el **origen de metadatos** página.  
  
## <a name="wcf-adapters-do-not-support-one-way-operations"></a>Los adaptadores de WCF no admiten operaciones unidireccionales.  
 Recibirá un mensaje de error similar al siguiente al consumir servicios WCF publicados con los adaptadores de WCF (excepto el adaptador de recepción WCF-netmsmq) si la **IsOneWay** propiedad está establecida en **true**en el cliente. Esto es porque el **System.ServiceModel.OperationContractAttribute.IsOneWay** propiedad de los servicios WCF publicados con los adaptadores de WCF (excepto el adaptador de recepción de los servicios publicados con WCF-NetMsmq) está establecida en **false** incluso para ubicaciones de recepción la unidireccionales.  
  
```  
The channel received an unexpected input message while closing. Your Channel.Close() calls are not synchronized.  
```  
  
 Recibirá un mensaje de error similar al siguiente al consumir los servicios WCF especificados con la **IsOneWay** propiedad establecida en **true**. Los mensajes que envíe desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se suspenderán como reanudables.  
  
```  
The request operation at net.tcp://localhost:8088/MyService/tcp did not receive a reply within timeout 00:01:00.  
```  
  
## <a name="a-memory-leak-may-occur-when-sending-messages-to-non-transactional-msmq-queues-using-wcf-netmsmq-binding"></a>Al enviar mensajes a colas MSMQ no transaccionales con el enlace WCF-NetMsmq, puede producirse una pérdida de memoria.  
 Al enviar mensajes a colas MSMQ no transaccionales con el enlace WCF-NetMsmq, puede producirse una pérdida de memoria en el servicio BizTalk NT. Esto puede producirse al enviar mensajes a una cola MSMQ no transaccional con el transporte WCF-NetMsmq o al enviar mensajes a una cola MSMQ no transaccional mediante el uso de netMsmqBinding con el transporte WCF-Custom.  
  
 Para resolver el problema, debe instalar la revisión de .NET Framework 3.0 descrita en el artículo de Knowledge Base 936512 en [http://go.microsoft.com/fwlink/?LinkId=92962](http://go.microsoft.com/fwlink/?LinkId=92962). La revisión no requiere un reinicio del sistema, pero es necesario reiniciar el servicio BizTalk NT que aloja los puertos de envío que usan el enlace WCF-NetMsmq.  
  
## <a name="you-may-receive-exception-when-communicating-with-apache-web-servers-using-wcf-basichttp-adapter"></a>Puede que reciba una excepción al comunicarse con servidores Web Apache con el adaptador de WCF-BasicHttp.  
 Al usar el adaptador de WCF-BasicHttp con la seguridad de transporte para comunicarse con un servidor Web Apache, puede que reciba excepciones similares a las siguientes:  
  
```  
System.Net.WebException: The underlying connection was closed: An unexpected error occurred on a send.  
System.IO.IOException: Unable to write data to the transport connection: An established connection was aborted by the software in your host machine. System.Net.Sockets.SocketException: An established connection was aborted by the software in your host machine  
```  
  
 Para solucionar este problema, debe usar el adaptador de WCF-Custom en lugar del adaptador de WCF-BasicHttp para comunicarse con los servidores Web Apache de la siguiente manera:  
  
1.  Cree un puerto de envío y establezca el tipo de transporte en **WCF-Custom**.  
  
2.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo la **enlace** ficha, seleccione **customBinding** desde el **BindingType** lista desplegable.  
  
3.  En **CustomeBindingElement**, haga clic en **httpTransport**y, a continuación, haga clic en **quitar extensión**.  
  
4.  Haga clic en **CustomeBindingElement**y, a continuación, haga clic en **Agregar extensión**.  
  
5.  En el **Seleccionar extensión de elemento de enlace** cuadro de diálogo, seleccione **httpTransport** y, a continuación, haga clic en **Aceptar**.  
  
6.  Haga clic en **httpTransport**y, a continuación, en la **configuración** panel, establezca el valor de **keepAliveEnabled** a **False**.  
  
7.  Haga clic en **textMessageEncoding**y, a continuación, en la **configuración** panel, establezca el valor de **messageVersion** a `Soap11WSAddressing10`.  
  
8.  Puede que tenga que configurar propiedades adicionales según sea necesario.  
  
## <a name="biztalk-server-does-not-work-with-wcf-clients-that-using-clientviabehavior-for-multiple-hop-conversations"></a>BizTalk Server no funciona con clientes de WCF que usen ClientViaBehavior para conversaciones de varios saltos.  
 Los clientes de WCF usan ClientViaBehavior cuando el destino de red inmediato no sea el procesador intencionado del mensaje para habilitar conversaciones de varios saltos cuando la aplicación que realiza la llamada no tiene por qué saber el destino final. Si especifica ClientViaBehavior y establece la dirección de destino en un servicio remoto en el que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] actuará como intermediario, recibirá un mensaje de error parecido al siguiente:  
  
```  
The message with To 'net.tcp://localhost:5555/test.svc' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher. Check that the sender and receiver's EndpointAddresses agree  
```