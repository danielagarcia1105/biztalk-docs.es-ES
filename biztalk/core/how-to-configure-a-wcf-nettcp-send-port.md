---
title: "Cómo configurar un puerto de envío WCF-NetTcp | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8fff07e-b08e-4f95-8ce2-27b508674a5c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8992a2c37295c7badab856e7a92a8f083ac9123b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-nettcp-send-port"></a>Cómo configurar un puerto de envío WCF-NetTcp
Los puertos de envío WCF-NetTcp pueden configurarse mediante programación, o bien utilizando la consola de administración de BizTalk.  
  
## <a name="configuration-properties"></a>Propiedades de configuración
  
 El modelo de objetos del explorador de BizTalk expone una interfaz específica del adaptador para puertos de envío denominado **ITransportInfo** que tiene el **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta una bolsa de propiedades de configuración de puerto de envío WCF-NetTcp con la forma de par nombre-valor de cadenas XML.  
  
 El **TransportTypeData** propiedad de la **ITransportInfo** interfaz no es necesaria. Si no se establece, el adaptador usa los valores predeterminados para la configuración del puerto de envío WCF-NetTcp, como se indica en la siguiente tabla.  
  
 En la tabla siguiente se enumeran las propiedades de configuración que pueden definirse en el Modelo de objetos para el Explorador de BizTalk para los puertos de envío WCF-NetTcp.  
  
|Nombre de la propiedad|Tipo|Description|  
|-------------------|----------|-----------------|  
|**Identidad**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;identidad&gt;<br /><br /> &lt;valor de userPrincipalName = "username@contoso.com" /&gt;<br /><br /> &lt;/Identity&gt;|Especifique la identidad de servicio que espera este puerto de envío. Esta configuración permite al puerto de envío autenticar el servicio. En el proceso de negociación entre el cliente y el servicio, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad del servicio esperado coincide con los valores de este elemento.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**StaticAction**|String|Especifique el **SOAPAction** campo de encabezado para los mensajes salientes. Esta propiedad también puede establecerse a través de la propiedad de contexto de mensaje **WCF. Acción** en una canalización o una orquestación. Puede especificar este valor de dos maneras diferentes: el formato de acción única y el formato de asignación de acciones. Si establece esta propiedad en el formato de acción única: por ejemplo, http://contoso.com/Svc/Op1: el **SOAPAction** encabezado mensajes salientes siempre se establece en el valor especificado en esta propiedad.<br /><br /> Si establece esta propiedad en el formato de asignación de acción, la salida **SOAPAction** encabezado viene determinado por la **BTS. Operación** propiedad de contexto. Por ejemplo, si esta propiedad se establece en el siguiente formato XML y **BTS. Operación** propiedad está establecida en Op1, el adaptador de envío WCF usa http://contoso.com/Svc/Op1 para el saliente **SOAPAction** encabezado.<br /><br /> \<BtsActionMapping ><br /><br /> \<Nombre de la operación = "Op1" Action = "http://contoso.com/Svc/Op1" / ><br /><br /> \<Nombre de la operación = "Op2" Action = "http://contoso.com/Svc/Op2" / ><br /><br /> \</ BtsActionMapping ><br /><br /> Si los mensajes salientes proceden de un puerto de orquestación, las instancias de orquestación establecen dinámicamente la **BTS. Operación** propiedad con el nombre de la operación del puerto. Si los mensajes salientes se enrutan con enrutamiento por contenidos, puede establecer el **BTS. Operación** propiedad en componentes de canalización.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**OpenTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de apertura del canal.<br /><br /> Valor predeterminado: 00:01:00|  
|**SendTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de envío. Si usa un puerto de envío de petición-respuesta, este valor especifica un marco temporal para que se complete la interacción, incluso cuando el servicio devuelva un mensaje grande.<br /><br /> Valor predeterminado: 00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de cierre del canal.<br /><br /> Valor predeterminado: 00:01:00|  
|**MaxReceivedMessageSize**|Integer|Especificar el tamaño máximo, en bytes, para mensajes (con encabezados incluidos) que se pueden recibir a través de la red. El tamaño de los mensajes se limita mediante la cantidad de memoria asignada a cada mensaje. Puede usar esta propiedad para limitar la exposición a ataques por denegación de servicio (DoS).<br /><br /> El adaptador de WCF-NetTcp usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) clase en el modo de transferencia almacenado en búfer para comunicarse con un punto de conexión. Para el modo de transporte almacenado en búfer, el [NetTcpBinding.MaxBufferSize](http://go.microsoft.com/fwlink/?LinkId=81088) propiedad siempre es igual al valor de esta propiedad.<br /><br /> Valor predeterminado: 65536|  
|**EnableTransaction**|Boolean|Especificar si un mensaje se transmite al servicio de destino y se elimina de la base de datos de cuadro de mensajes en un contexto transaccional usando el protocolo de transacción especificado en la **TransactionProtocol** propiedad.<br /><br /> Valor predeterminado: **False**|  
|**TransactionProtocol**|Enum<br /><br /> -   **OleTransaction**<br />-   **WS-AtomicTransaction**|Especificar el protocolo de transacción que se usará con este enlace.<br /><br /> Valor predeterminado: **OleTransaction**|  
|**SecurityMode**|Enum<br /><br /> -   **Ninguno**<br />-   **Mensaje**<br />-   **Transporte**<br />-   **TransportWithMessageCredential**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **SecurityMode** propiedad, vea la **modo de seguridad** propiedad en el **delcuadrodediálogodepropiedadesdetransporteWCF-NetTcp,envío,seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el tipo de seguridad que se usa.<br /><br /> Valor predeterminado: **transporte**|  
|**TransportClientCredentialType**|Enum<br /><br /> -   **Ninguno**<br />-   **Windows**<br />-   **Certificado**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **TransportClientCredentialType** propiedad, vea la **tipo de credencial de cliente de transporte** propiedad en el **transporte WCF-NetTcp Seguridad de cuadro de diálogo, envío, las propiedades** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación del puerto de envío.<br /><br /> Valor predeterminado: **Windows**|  
|**TransportProtectionLevel**|Enum<br /><br /> -   **Ninguno** -sin protección.<br />-   **Inicio de sesión** -se firman los mensajes.<br />-   **EncryptAndSign** -mensajes se cifrarán y firmarán.|Especificar la seguridad en el nivel de transporte TCP. Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere. El cifrado proporciona privacidad de nivel de datos durante el transporte.<br /><br /> Valor predeterminado: **EncryptAndSign**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **Ninguno**<br />-   **Windows**<br />-   **Nombre de usuario**<br />-   **Certificado**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **MessageClientCredentialType** propiedad, vea la **tipo de credencial de cliente de mensaje** propiedad en la **propiedades de transporte de WCF-NetTcp Cuadro de diálogo cuadro, envío, seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación de cliente mediante la seguridad basada en mensajes.<br /><br /> Valor predeterminado: **Windows**|  
|**AlgorithmSuite**|Enum<br /><br /> Para obtener más información acerca de los nombres de miembro para el **AlgorithmSuite** propiedad, vea la **conjunto de algoritmos** propiedad en la **cuadro de diálogo de propiedades de transporte WCF-NetTcp, envío, seguridad**  ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el cifrado de mensajes y los algoritmos de encapsulado de claves. Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).<br /><br /> Valor predeterminado: **Basic256**|  
|**ClientCertificate**|String|Especificar la huella digital del certificado X.509 para la autenticación de este puerto de envío en servicios. Esta propiedad es necesaria si la **ClientCredentialsType** propiedad está establecida en **certificado**. El certificado que se usará para esta propiedad debe estar instalado en el **mi** almacenar en la **usuario actual** ubicación.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**AffiliateApplicationName**|String|Especificar la aplicación afiliada que se utilizará para el inicio de sesión único empresarial (SSO).<br /><br /> El valor predeterminado es una cadena vacía.|  
|**UseSSO**|Boolean|Especificar si se utiliza el inicio de sesión único (SSO) para recuperar credenciales de cliente para la autenticación con el servidor de destino.<br /><br /> Valor predeterminado: **False**|  
|**UserName**|String|Especifique el nombre de usuario que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**. No tiene que usar el formato dominio\usuario para esta propiedad.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**Contraseña**|String|Especifique la contraseña que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar la parte del cuerpo de mensaje de BizTalk para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.<br />-   **UseTemplate** -usar la plantilla proporcionada en el **OutboundXMLTemplate** propiedad que se va a crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.<br /><br /> Para obtener más información sobre cómo usar el **OutboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF salientes.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**OutboundXMLTemplate**|String<br /><br /> Para obtener más información sobre cómo usar el **OutboundXMLTemplate** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la plantilla con formato XML para el contenido del mensaje SOAP **cuerpo** elemento de un mensaje saliente. Esta propiedad es necesaria si la **OutboundBodyLocation** propiedad está establecida en **UseTemplate**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar el contenido del mensaje SOAP **cuerpo** elemento de un mensaje entrante para crear la parte del cuerpo de mensaje de BizTalk. Si el elemento **Body** tiene varios elementos secundarios, sólo el primero de ellos será la parte del cuerpo del mensaje de BizTalk. Esta propiedad sólo es válida para puertos de petición-respuesta.<br />-   **UseEnvelope** -crear la parte del cuerpo de mensaje de BizTalk desde el mensaje de SOAP completo **sobres** de un mensaje entrante.<br />-   **UseBodyPath** -usar la expresión de ruta de cuerpo en el **InboundBodyPathExpression** propiedad que se va a crear la parte del cuerpo de mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del elemento **Cuerpo** de SOAP de un mensaje entrante. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF entrantes.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**InboundBodyPathExpression**|String<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyPathExpression** propiedad, vea [propiedades y esquema de propiedades de adaptadores de WCF](../core/wcf-adapters-property-schema-and-properties.md).|Especificar la expresión de ruta de cuerpo para identificar una parte específica de un mensaje entrante utilizada para crear la parte del cuerpo del mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del mensaje SOAP **cuerpo** nodo de un mensaje entrante. Si esta expresión de ruta de cuerpo devuelve varios nodos, solo se elegirá el primero de ellos para la parte del cuerpo del mensaje de BizTalk. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **XML**<br />-   **Base64** -codificación Base64.<br />-   **Hex** : Hexadecimal codificación.<br />-   **Cadena** : codificación de texto - UTF-8.<br />-   **XML** -los adaptadores WCF crean el cuerpo del mensaje de BizTalk con el XML externo del nodo seleccionado por la expresión de ruta de acceso de cuerpo en **InboundBodyPathExpression**.|Especificar el tipo de codificación que el adaptador de envío WCF-NetTcp usa para descodificar el nodo identificado por la expresión XPath especificada en **InboundBodyPathExpression**. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Valor predeterminado: **XML**|  
|**PropagateFaultMessage**|Boolean<br /><br /> -   **True** -enrutar el mensaje que se produce un error de procesamiento de salida a una aplicación de suscripción (por ejemplo, otro puerto o programación de orquestación de recepción).<br />-   **False** -suspender mensajes erróneos y generar una confirmación negativa (NACK).|Especificar si se enrutan o se suspenden mensajes que han generado errores en el procesamiento de salida.<br /><br /> Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Valor predeterminado: **True**|  
  
 **Cómo configurar un puerto de envío WCF-NetTcp con la consola de administración de BizTalk**  
  
 Se pueden establecer variables del adaptador de puerto de envío WCF-NetTcp en la consola de administración de BizTalk. Si no se establecen las propiedades del puerto de envío, se usan los valores predeterminados de la configuración del puerto de envío WCF-NetTcp, como se indica en la tabla anterior.  
  
## <a name="configure-variables-for-a-wcf-nettcp-send-port"></a>Configurar variables para un puerto de envío WCF-NetTcp  
  
1.  En la consola de administración de BizTalk, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones del puerto de envío y especifique **WCF-NetTcp** para el **tipo** opción en el **transporte** sección de la **General** pestaña.  
  
2.  En el **General** ficha la **transporte** sección, haga clic en el **configurar** situado junto a **tipo**.  
  
3.  En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo la **General** pestaña, configure la dirección del extremo, la identidad del servicio y la **SOAPAction** encabezado para el Puerto de envío WCF-NetTcp. Para obtener más información sobre la **General** pestaña en el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, vea el **cuadro de diálogo de propiedades de transporte de WCF-NetTcp, envío, General** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
4.  En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, en la **enlace** pestaña, configure las propiedades de tiempo de espera y transacción. Para obtener más información sobre la **enlace** pestaña en el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, vea el **enlace de cuadro de diálogo de propiedades de transporte WCF-NetTcp, envío,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
5.  En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, en la **seguridad** ficha, defina las capacidades de seguridad del puerto de envío WCF-NetTcp. Para obtener más información sobre la **seguridad** pestaña en el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, vea el **delcuadrodediálogodepropiedadesdetransporteWCF-NetTcp,envío,seguridad**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
6.  En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, en la **mensajes** ficha, especifique la selección de datos de SOAP **cuerpo** elemento. Para obtener más información sobre la **mensajes** pestaña en el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, vea el **mensajes del cuadro de diálogo de propiedades de transporte WCF-NetTcp, envío,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="configure-a-wcf-nettcp-send-port-programmatically"></a>Configurar un puerto de envío WCF-NetTcp mediante programación
  
 Puede usar el siguiente formato para establecer las propiedades:  
  
 \<CustomProps >  
  
```  
  <UseSSO vt="11">0</UseSSO>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <InboundBodyPathExpression vt="8" />  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <TransportClientCredentialType vt="8">Windows</TransportClientCredentialType>  
  <ClientCertificate vt="8" />  
  <TransactionProtocol vt="8">OleTransactions</TransactionProtocol>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <TransportProtectionLevel vt="8">EncryptAndSign</TransportProtectionLevel>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <EnableTransaction vt="11">0</EnableTransaction>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 El siguiente fragmento de código muestra la creación de un puerto de envío WCF-NetTcp:  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetTcp send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 <StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
<OpenTimeout vt=""8"">00:01:00</OpenTimeout>  
                               </CustomProps>";  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  
// Add a new BizTalk application  
Application application = explorer.AddNewApplication();  
application.Name = "SampleBizTalkApplication";  
// Save  
explorer.SaveChanges();  
  
// Add a new static one-way send port  
SendPort sendPort = application.AddNewSendPort(false, false);   
sendPort.Name = "SampleSendPort";  
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-NetTcp"];  
sendPort.PrimaryTransport.Address = "net.tcp://mycomputer/private/samplequeue";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  
  
## <a name="see-also"></a>Vea también  
 [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)   
 [Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)   
 [Configurar el adaptador de WCF-NetTcp](../core/configuring-the-wcf-nettcp-adapter.md)   
 [Configuración de puertos de envío dinámicos mediante propiedades de contexto de adaptadores de WCF](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)