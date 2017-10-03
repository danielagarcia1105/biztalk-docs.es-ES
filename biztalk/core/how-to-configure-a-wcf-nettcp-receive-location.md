---
title: "Cómo configurar ubicación de recepción de WCF-NetTcp | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 937862ca-14cb-4eda-8176-38c15423679e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37ad7fc1ac3ede003c273e789ab465136b8d6abe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-nettcp-receive-location"></a>Cómo configurar una ubicación de recepción WCF-NetTcp
Puede configurar una ubicación de recepción WCF-NetTcp mediante programación o con la consola de administración de BizTalk.  
  
## <a name="configuration-properties"></a>Propiedades de configuración
  
 El modelo de objetos del Explorador de BizTalk permite crear y configurar ubicaciones de recepción mediante programación. El modelo de objetos del explorador de BizTalk expone la**IReceiveLocation** recibir interfaz de configuración de ubicación que tenga un **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta una bolsa de propiedades de configuración de ubicación de recepción WCF-NetTcp con formato de un par nombre - valor de cadenas XML. Para establecer esta propiedad en el modelo de objetos del explorador de BizTalk, debe establecer el **InboundTransportLocation** propiedad de la **IReceiveLocation** interfaz.  
  
 El **TransportTypeData** propiedad de la **IReceiveLocation** interfaz no tiene que establecerse. Si no se establece, el adaptador de WCF-NetTcp usa los valores predeterminados para la configuración de la ubicación de recepción WCF-NetTcp, como se indica en la siguiente tabla.  
  
 La siguiente tabla enumera las propiedades de configuración que se pueden establecer en el modelo de objetos para el Explorador de BizTalk para la ubicación de recepción WCF-NetTcp.  
  
|Nombre de la propiedad|Tipo|Description|  
|-------------------|----------|-----------------|  
|**Identidad**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;identidad&gt;<br /><br /> &lt;valor de userPrincipalName = "username@contoso.com" /&gt;<br /><br /> &lt;/Identity&gt;|Especificar la identidad de servicio que proporciona esta ubicación de recepción. Los valores que se pueden especificar para el **identidad** propiedad difieren según la configuración de seguridad. Esta configuración hace posible que el cliente autentique la ubicación de recepción. En el proceso de negociación entre el cliente y el servicio, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad del servicio esperado coincide con los valores de este elemento.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**OpenTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de apertura del canal.<br /><br /> Valor predeterminado: 00:01:00|  
|**SendTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de envío. Si usa un puerto de recepción solicitud-respuesta, este valor especifica un marco temporal para que se complete la interacción, incluso cuando el cliente devuelva un mensaje grande.<br /><br /> Valor predeterminado: 00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de cierre del canal.<br /><br /> Valor predeterminado: 00:01:00|  
|**MaxReceivedMessageSize**|Integer|Especificar el tamaño máximo, en bytes, para mensajes (con encabezados incluidos) que se pueden recibir a través de la red. El tamaño de los mensajes se limita mediante la cantidad de memoria asignada a cada mensaje. Puede usar esta propiedad para limitar la exposición a ataques por denegación de servicio (DoS).<br /><br /> El adaptador de WCF-NetTcp usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) clase en el modo de transferencia almacenado en búfer para comunicarse con un punto de conexión. Para el modo de transporte almacenado en búfer, el [NetTcpBinding.MaxBufferSize](http://go.microsoft.com/fwlink/?LinkId=81088) propiedad siempre es igual al valor de esta propiedad.<br /><br /> Valor predeterminado: 65536|  
|**EnableTransaction**|Boolean|Especificar si un mensaje se envía a la base de datos de cuadro de mensajes mediante la transacción procedente de clientes. Si esta propiedad se establece en **True**, los clientes deberán enviar mensajes mediante el protocolo thetransaction especificado en el **TransactionProtocol** propiedad. Si los clientes envían mensajes fuera del ámbito transaccional, esta ubicación de recepción devolverá una excepción a los clientes y no se suspenderá ningún mensaje.<br /><br /> La opción sólo está disponible para las ubicaciones de recepción unidireccionales. Si los clientes envían mensajes en un contexto transaccional para las ubicaciones de recepción de solicitud-respuesta, se devolverá una excepción a los clientes y no se suspenderá ningún mensaje.<br /><br /> Valor predeterminado:`False`|  
|**TransactionProtocol**|Enum<br /><br /> -   **OleTransaction**<br />-   **WS-AtomicTransaction**|Especificar el protocolo de transacciones que se usará con esta ubicación de recepción.<br /><br /> Valor predeterminado: **OleTransaction**|  
|**LeaseTimeout**|**System.TimeSpan**|Especificar la duración máxima de una conexión agrupada activa. Después de transcurrir el tiempo especificado, la conexión se cierra cuando se atiende la solicitud actual.<br /><br /> El adaptador de WCF-NetTcp usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) clase para comunicarse con un punto de conexión. Cuando se usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) en escenarios con equilibrio de carga, considere la posibilidad de reducir el tiempo de espera de concesión predeterminado. Para obtener más información acerca del equilibrio de carga cuando se usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087), vea el tema correspondiente en la sección Vea también.<br /><br /> Valor predeterminado: 00:05:00|  
|**MaxConcurrentCalls**|Integer|Especificar el número de llamadas concurrentes en una instancia de servicio única. Las llamadas que superan el límite se ponen en cola. El rango de esta propiedad es desde 1 a Int32.MaxValue.<br /><br /> Valor predeterminado: 200|  
|**SecurityMode**|Enum<br /><br /> -   **Ninguno**<br />-   **Mensaje**<br />-   **Transporte**<br />-   **TransportWithMessageCredential**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **SecurityMode** propiedad, vea la **modo de seguridad** propiedad en el **delcuadrodediálogodepropiedadesdetransporteWCF-NetTcp,recepción,seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el tipo de seguridad que se usa.<br /><br /> Valor predeterminado: **transporte**|  
|**TransportClientCredentialType**|Enum<br /><br /> -   **Ninguno**<br />-   **Windows**<br />-   **Certificado**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **TransportClientCredentialType** propiedad, vea la **tipo de credencial de cliente de transporte** propiedad en el **transporte WCF-NetTcp Seguridad de cuadro de diálogo, recepción, las propiedades** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación del cliente.<br /><br /> Valor predeterminado: **Windows**|  
|**TransportProtectionLevel**|Enum<br /><br /> -   **Ninguno**: sin protección.<br />-   **Inicio de sesión**: se firman los mensajes.<br />-   **EncryptAndSign**: los mensajes se cifrarán y firmarán.|Definir la seguridad en el nivel de transporte TCP. Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere. El cifrado proporciona privacidad de nivel de datos durante el transporte.<br /><br /> Valor predeterminado: **EncryptAndSign**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **Ninguno**<br />-   **Windows**<br />-   **Nombre de usuario**<br />-   **Certificado**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **MessageClientCredentialType** propiedad, vea la **tipo de credencial de cliente de mensaje** propiedad en la **propiedades de transporte de WCF-NetTcp Cuadro de diálogo cuadro, recepción, seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación de cliente mediante la seguridad basada en mensajes.<br /><br /> Valor predeterminado: **Windows**|  
|**AlgorithmSuite**|Enum<br /><br /> Para obtener más información acerca de los nombres de miembro para el **AlgorithmSuite** propiedad, vea la **conjunto de algoritmos** propiedad en la **cuadro de diálogo de propiedades de transporte WCF-NetTcp, recepción, seguridad**  ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el cifrado de mensajes y los algoritmos de encapsulado de claves. Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).<br /><br /> Valor predeterminado: **Basic256**|  
|**ServiceCertificate**|String|Especificar la huella digital del certificado X.509 para esta ubicación de recepción que los clientes utilizan para autenticar el servicio. El certificado que se usará para esta propiedad debe estar instalado en el **mi** almacenar en la **usuario actual** ubicación. **Nota:** debe instalar el certificado de servicio en la **usuario actual** ubicación de la cuenta de usuario para el controlador de recepción que aloja esta ubicación de recepción. <br /><br /> El valor predeterminado es una cadena vacía.|  
|**UseSSO**|Boolean|Especificar si se usa el inicio de sesión único (SSO) empresarial para recuperar credenciales de cliente y emitir, así, un vale de SSO. Para obtener más información acerca de las configuraciones de seguridad compatibles con SSO, vea la sección "Enterprise Single Sign-On compatibilidad the WCF-NetTcp adaptador de recepción" en la **delcuadrodediálogodepropiedadesdetransporteWCF-NetTcp,recepción,seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar el contenido del mensaje SOAP **cuerpo** elemento de un mensaje entrante para crear la parte del cuerpo de mensaje de BizTalk. Si el elemento **Body** tiene varios elementos secundarios, sólo el primero de ellos será la parte del cuerpo del mensaje de BizTalk.<br />-   **UseEnvelope** -crear la parte del cuerpo de mensaje de BizTalk desde el mensaje de SOAP completo **sobres** de un mensaje entrante.<br />-   **UseBodyPath** -usar la expresión de ruta de cuerpo en el **InboundBodyPathExpression** propiedad que se va a crear la parte del cuerpo de mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del elemento **Cuerpo** de SOAP de un mensaje entrante. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF entrantes.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**InboundBodyPathExpression**|String<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyPathExpression** propiedad, vea [propiedades y esquema de propiedades de adaptadores de WCF](../core/wcf-adapters-property-schema-and-properties.md).|Especificar la expresión de ruta de cuerpo para identificar una parte específica de un mensaje entrante utilizada para crear la parte del cuerpo del mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del mensaje SOAP **cuerpo** nodo de un mensaje entrante. Si esta expresión de ruta de cuerpo devuelve varios nodos, solo se elegirá el primero de ellos para la parte del cuerpo del mensaje de BizTalk. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -codificación Base64.<br />-   **Hex** : Hexadecimal codificación.<br />-   **Cadena** : codificación de texto - UTF-8.<br />-   **XML** -los adaptadores WCF crean el cuerpo del mensaje de BizTalk con el XML externo del nodo seleccionado por la expresión de ruta de acceso de cuerpo en **InboundBodyPathExpression**.|Especifique el tipo de codificación que WCF-NetTcp adaptador de recepción utiliza para descodificar el nodo identificado por la expresión de ruta de acceso de cuerpo especificada en **InboundBodyPathExpression**. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**.<br /><br /> Valor predeterminado: **XML**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar la parte del cuerpo de mensaje de BizTalk para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje de respuesta saliente.<br />-   **UseTemplate** -usar la plantilla proporcionada en el **OutboundXMLTemplate** propiedad que se va a crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje de respuesta saliente.<br /><br /> Para obtener más información sobre cómo usar el **OutboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF salientes. Esta propiedad sólo es válida para las ubicaciones de recepción de solicitud-respuesta.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**OutboundXMLTemplate**|String<br /><br /> Para obtener más información sobre cómo usar el **OutboundXMLTemplate** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la plantilla con formato XML para el contenido del mensaje SOAP **cuerpo** elemento de un mensaje de respuesta saliente. Esta propiedad es necesaria si la **OutboundBodyLocation** propiedad está establecida en **UseTemplate**. Esta propiedad sólo es válida para las ubicaciones de recepción de solicitud-respuesta.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**SuspendMessageOnFailure**|Boolean|Especificar si se va a suspender el mensaje de solicitud cuyo procesamiento de entrada no se puede realizar correctamente debido a un error de canalización de recepción o de enrutamiento.<br /><br /> Valor predeterminado: **True**|  
|**IncludeExceptionDetailInFaults**|Boolean|Especificar si se va a incluir información de excepción administrada en el detalle de los errores SOAP devueltos al cliente para fines de depuración.<br /><br /> Valor predeterminado: **False**|  
  
## <a name="configure-a-wcf-nettcp-receive-location-with-the-biztalk-administration-console"></a>Configurar WCF-NetTcp ubicación de recepción con la consola de administración de BizTalk
  
 Se pueden establecer variables de adaptador de ubicación de recepción WCF-NetTcp en la consola de administración de BizTalk. Si no se definen propiedades en la ubicación de recepción, se utilizarán los valores predeterminados del controlador de recepción establecidos en la consola de administración de BizTalk.  
  
> [!NOTE]
>  Antes de completar este procedimiento, debe haber agregado un puerto de recepción. Para obtener más información, consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
## <a name="configure-variables-for-a-wcf-nettcp-receive-location"></a>Configurar variables para la ubicación de recepción de WCF-NetTcp  
  
1.  En la consola de administración de BizTalk, expanda la opción **Administración de BizTalkServer 2009**, **Grupo de BizTalk**, **Aplicaciones**y, a continuación, expanda la aplicación en la que desea crear una ubicación de recepción.  
  
2.  En la consola de administración de BizTalk, en el panel izquierdo, haga clic en el nodo **Puerto de recepción** . A continuación, en el panel de la derecha, haga clic con el botón secundario en el puerto de recepción asociado con una ubicación de recepción existente o que desee asociar con una nueva ubicación de recepción. A continuación, haga clic en **Propiedades**.  
  
3.  En el **propiedades de puerto de recepción** cuadro de diálogo, en el panel izquierdo, seleccione **ubicaciones de recepción**y, a continuación, en el panel derecho, haga doble clic en otra ubicación de recepción o haga clic en **New**para crear una nueva ubicación de recepción.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **transporte** junto a la sección **tipo**, seleccione **WCF-NetTcp** en la lista desplegable lista y, a continuación, haga clic en **configurar**.  
  
5.  En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, en la **General** pestaña, configure la dirección del extremo y ubicación de recepción de la identidad del servicio de WCF-NetTcp. Para obtener más información sobre la **General** pestaña en el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, vea la **cuadro diálogo de propiedades de transporte WCF-NetTcp, recepción, General**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
6.  En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, en la **enlace** pestaña, configure las propiedades de tiempo de espera y transacción. Para obtener más información sobre la **enlace** pestaña en el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, vea el **enlace de cuadro de diálogo de propiedades de transporte WCF-NetTcp, recepción,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
7.  En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo la **seguridad** ficha, definir la seguridad de la ubicación de recepción de las capacidades de WCF-NetTcp. Para obtener más información acerca de la **seguridad** pestaña en el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, vea la **seguridad del cuadro de diálogo de propiedades de transporte WCF-NetTcp, recepción,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
8.  En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, en la **mensajes** ficha, especifique la selección de datos de SOAP **cuerpo** elemento. Para obtener más información sobre la **mensajes** pestaña en el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, vea el **mensajes del cuadro de diálogo de propiedades de transporte WCF-NetTcp, recepción,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
##<a name="configure-a-wcf-nettcp-receive-location-programmatically"></a>Configurar WCF-NetTcp mediante programación de la ubicación de recepción
  
 Puede usar el siguiente formato para establecer las propiedades:  
  
```  
<CustomProps>  
  <InboundBodyPathExpression vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <UseSSO vt="11">0</UseSSO>  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Message</SecurityMode>  
  <TransportClientCredentialType vt="8">Windows</TransportClientCredentialType>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <SuspendMessageOnFailure vt="11">0</SuspendMessageOnFailure>  
  <EnableTransaction vt="11">0</EnableTransaction>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <IncludeExceptionDetailInFaults vt="11">0</IncludeExceptionDetailInFaults>  
  <MaxConcurrentCalls vt="3">16</MaxConcurrentCalls>  
  <ServiceCertificate vt="8" />  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 El siguiente fragmento de código muestra la creación de una ubicación de recepción WCF-NetTcp:  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetTcp receive location   
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
  <InboundBodyLocation vt=""8"">UseBodyElement</InboundBodyLocation>  
  <UseSSO vt=""11"">0</UseSSO>  
  <Identity vt=""8"">  
    <identity>  
    <userPrincipalName value=""username@contoso.com"" />  
    </identity>  
  </Identity>  
</CustomProps>";  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  
// Add a new BizTalk application  
Application application = explorer.AddNewApplication();  
application.Name = "SampleBizTalkApplication";  
// Save  
explorer.SaveChanges();  
  
// Add a new one-way receive port  
IReceivePort receivePort = application.AddNewReceivePort(false);  
receivePort.Name = "SampleReceivePort";  
// Add a new one-way receive location  
IReceiveLocation recieveLocation = receivePort.AddNewReceiveLocation();  
recieveLocation.Name = "SampleReceiveLocation";  
// Find a receive handler for WCF-NetTcp   
int i = 0;  
for(i=0; i < explorer.ReceiveHandlers.Count; ++i)   
{  
    if("WCF-NetTcp" == explorer.ReceiveHandlers[i].TransportType.Name)  
        break;  
}  
recieveLocation.ReceiveHandler = explorer.ReceiveHandlers[i];  
recieveLocation.Address = "net.tcp://mycomputer/samplepath";  
recieveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
recieveLocation.TransportType = explorer.ProtocolTypes["WCF-NetTcp"];  
recieveLocation.TransportTypeData = transportConfigData;  
// Save  
explorer.SaveChanges();   
```  
  
## <a name="see-also"></a>Vea también  
 [Adaptadores de recepción de la publicación de metadatos de servicio de WCF](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)   
 [Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md)   
 [Cómo cambiar contraseñas y cuentas de servicio](../core/how-to-change-service-accounts-and-passwords.md)   
 [Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)   
 [Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [Equilibrio de carga](http://go.microsoft.com/fwlink/?LinkId=81089)   
 [Configurar el adaptador de WCF-NetTcp](../core/configuring-the-wcf-nettcp-adapter.md)