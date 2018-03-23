---
title: Cómo configurar un puerto de envío WCF-NetNamedPipe | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57684e09-1f72-4bde-976c-3fcec65dc182
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed9b2138aaad8c2cccb60d75d7331c2331eeddc
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-configure-a-wcf-netnamedpipe-send-port"></a>Cómo configurar un puerto de envío WCF-NetNamedPipe
El puerto de envío WCF-NetNamedPipe se puede configurar mediante programación o con la consola de administración de BizTalk.  
  
## <a name="configuration-properties"></a>Propiedades de configuración
  
 El modelo de objetos del explorador de BizTalk expone una interfaz específica del adaptador para puertos de envío denominado **ITransportInfo** que tiene el **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta una bolsa de propiedades de configuración de puerto de envío WCF-NetNamedPipe con la forma de pareja nombre-valor de cadenas XML.  
  
 El **TransportTypeData** propiedad de la **ITransportInfo** interfaz no es necesaria. Si no se establece, el adaptador usa los valores predeterminados para la configuración de puerto de envío WCF-NetNamedPipe, como se indica en la siguiente tabla.  
  
 La siguiente tabla enumera las propiedades de configuración que puede establecer en el modelo de objetos del Explorador de BizTalk para puertos de envío WCF-NetNamedPipe.  
  
|Nombre de la propiedad|Tipo|Description|  
|-------------------|----------|-----------------|  
|**Identidad**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;Identidad&gt;<br /><br /> &lt;valor de userPrincipalName = "username@contoso.com" /&gt;<br /><br /> &lt;/Identity&gt;|Especifique la identidad de servicio que espera este puerto de envío. Esta configuración permite al puerto de envío autenticar el servicio. En el proceso de negociación entre el cliente y el servicio, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad del servicio esperado coincide con los valores de este elemento.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**StaticAction**|String|Especifique el **SOAPAction** campo de encabezado para los mensajes salientes. Esta propiedad también puede establecerse a través de la propiedad de contexto de mensaje **WCF. Acción** en una canalización o una orquestación. Puede especificar este valor de dos maneras diferentes: el formato de acción única y el formato de asignación de acciones. Si establece esta propiedad en el formato de acción única: por ejemplo, http://contoso.com/Svc/Op1- el **SOAPAction** encabezado mensajes salientes siempre se establece en el valor especificado en esta propiedad.<br /><br /> Si establece esta propiedad en el formato de asignación de acción, la salida **SOAPAction** encabezado viene determinado por la **BTS. Operación** propiedad de contexto. Por ejemplo, si esta propiedad se establece en el siguiente formato XML y **BTS. Operación** propiedad está establecida en Op1, el adaptador de envío WCF usa http://contoso.com/Svc/Op1 para los salientes **SOAPAction** encabezado.<br /><br /> \<BtsActionMapping\><br /><br /> \<Nombre de la operación = "Op1" Action = "http://contoso.com/Svc/Op1" /\><br /><br /> \<Nombre de la operación = "Op2" Action = "http://contoso.com/Svc/Op2" /\><br /><br /> \</BtsActionMapping\><br /><br /> Si los mensajes salientes proceden de un puerto de orquestación, las instancias de orquestación establecen dinámicamente la **BTS. Operación** propiedad con el nombre de la operación del puerto. Si los mensajes salientes se enrutan con enrutamiento por contenidos, puede establecer el **BTS. Operación** propiedad en componentes de canalización.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**OpenTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de apertura del canal.<br /><br /> Valor predeterminado: 00:01:00|  
|**SendTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de envío. Si usa un puerto de envío de petición-respuesta, este valor especifica un marco temporal para que se complete la interacción, incluso cuando el servicio devuelva un mensaje grande.<br /><br /> Valor predeterminado: 00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de cierre del canal.<br /><br /> Valor predeterminado: 00:01:00|  
|**MaxReceivedMessageSize**|Integer|Especificar el tamaño máximo, en bytes, para mensajes (con encabezados incluidos) que se pueden recibir a través de la red. El tamaño de los mensajes se limita mediante la cantidad de memoria asignada a cada mensaje. Puede usar esta propiedad para limitar la exposición a ataques por denegación de servicio (DoS).<br /><br /> Valor predeterminado: 65536|  
|**EnableTransaction**|Boolean|Especificar si un mensaje se transmite al servicio de destino y se elimina de la base de datos de cuadro de mensajes en un contexto transaccional usando el **WS-AtomicTransaction** protocolo.<br /><br /> Valor predeterminado: **False**|  
|**TransactionProtocol**|Enum<br /><br /> -   **OleTransaction**<br />-   **WS-AtomicTransaction**|Especificar el protocolo de transacción que se usará con este enlace.<br /><br /> Valor predeterminado: **OleTransaction**|  
|**SecurityMode**|Enum<br /><br /> -   **Ninguno**-deshabilita la seguridad.<br />-   **Transporte**:-seguridad se proporciona mediante la seguridad basada en transporte subyacente. Con este modo es posible controlar el nivel de protección.|Especificar el tipo de seguridad que se usa.<br /><br /> Valor predeterminado: **transporte**|  
|**TransportProtectionLevel**|Enum<br /><br /> -   **Ninguno** -sin protección.<br />-   **Inicio de sesión** -se firman los mensajes.<br />-   **EncryptAndSign** -mensajes se cifrarán y firmarán.|Especificar el nivel de protección de la canalización con nombre. Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere. El cifrado proporciona privacidad de nivel de datos durante el transporte.<br /><br /> Valor predeterminado: **EncryptAndSign**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar la parte del cuerpo de mensaje de BizTalk para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.<br />-   **UseTemplate** -usar la plantilla proporcionada en el **OutboundXMLTemplate** propiedad que se va a crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.<br /><br /> Para obtener más información sobre cómo usar el **OutboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF salientes.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**OutboundXMLTemplate**|String<br /><br /> Para obtener más información sobre cómo usar el **OutboundXMLTemplate** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la plantilla con formato XML para el contenido del mensaje SOAP **cuerpo** elemento de un mensaje saliente. Esta propiedad es necesaria si la **OutboundBodyLocation** propiedad está establecida en **UseTemplate**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar el contenido del mensaje SOAP **cuerpo** elemento de un mensaje entrante para crear la parte del cuerpo de mensaje de BizTalk. Si el elemento **Body** tiene varios elementos secundarios, sólo el primero de ellos será la parte del cuerpo del mensaje de BizTalk. Esta propiedad sólo es válida para puertos de petición-respuesta.<br />-   **UseEnvelope** -crear la parte del cuerpo de mensaje de BizTalk desde el mensaje de SOAP completo **sobres** de un mensaje entrante.<br />-   **UseBodyPath** -usar la expresión de ruta de cuerpo en el **InboundBodyPathExpression** propiedad que se va a crear la parte del cuerpo de mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del elemento **Cuerpo** de SOAP de un mensaje entrante. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF entrantes.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**InboundBodyPathExpression**|String<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyPathExpression** propiedad, vea [propiedades y esquema de propiedades de adaptadores de WCF](../core/wcf-adapters-property-schema-and-properties.md).|Especificar la expresión de ruta de cuerpo para identificar una parte específica de un mensaje entrante utilizada para crear la parte del cuerpo del mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del mensaje SOAP **cuerpo** nodo de un mensaje entrante. Si esta expresión de ruta de cuerpo devuelve varios nodos, solo se elegirá el primero de ellos para la parte del cuerpo del mensaje de BizTalk. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **XML**<br />-   **Base64** -codificación Base64.<br />-   **Hex** : Hexadecimal codificación.<br />-   **Cadena** : codificación de texto - UTF-8.<br />-   **XML** -los adaptadores WCF crean el cuerpo del mensaje de BizTalk con el XML externo del nodo seleccionado por la expresión de ruta de acceso de cuerpo en **InboundBodyPathExpression**.|Especificar el tipo de codificación que el adaptador de envío WCF-NetNamedPipe usa para descodificar el nodo identificado por la ruta de cuerpo especificada en **InboundBodyPathExpression**. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Valor predeterminado: **XML**|  
|**PropagateFaultMessage**|Boolean<br /><br /> -   **True** -enrutar el mensaje que se produce un error de procesamiento de salida a una aplicación de suscripción (por ejemplo, otro puerto o programación de orquestación de recepción).<br />-   **False** -suspender mensajes erróneos y generar una confirmación negativa (NACK).|Especificar si se enrutan o se suspenden mensajes que han generado errores en el procesamiento de salida.<br /><br /> Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Valor predeterminado: **True**|  
  
## <a name="configure-a-wcf-netnamedpipe-send-port-with-the-biztalk-administration-console"></a>Configurar un puerto de envío WCF-NetNamedPipe con la consola de administración de BizTalk
  
 Se pueden establecer las variables del adaptador de puerto de envío WCF-NetNamedPipe en la consola de administración de BizTalk. Si no se establecen las propiedades del puerto de envío, se usan los valores predeterminados de la configuración del puerto de envío WCF-NetNamedPipe, como se indica en la tabla anterior.  
  
## <a name="configure-variables-for-a-wcf-netnamedpipe-send-port"></a>Configurar variables para un puerto de envío WCF-NetNamedPipe  
  
1.  En la consola de administración de BizTalk, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones del puerto de envío y especifique **WCF-NetNamedPipe** para el **tipo** opción en el **transporte** sección de la **General**ficha.  
  
2.  En el **General** ficha la **transporte** sección, haga clic en el **configurar** situado junto a **tipo**.  
  
3.  En el **propiedades de transporte de WCF-NetNamedPipe** cuadro de diálogo, en la **General** pestaña, configure la dirección del extremo, la identidad del servicio y la **SOAPAction** encabezado para el puerto de envío WCF-NetNamedPipe. Para obtener más información sobre la **General** pestaña en el **propiedades de transporte de WCF-NetNamedPipe** cuadro de diálogo, vea la **cuadro diálogo de propiedades de transporte WCF-NetNamedPipe, envío, General** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
4.  En el **propiedades de transporte de WCF-NetNamedPipe** cuadro de diálogo, en la **enlace** pestaña, configure las propiedades de tiempo de espera y transacción. Para obtener más información sobre la **enlace** pestaña en el **propiedades de transporte de WCF-NetNamedPipe** cuadro de diálogo, vea el **enlace de cuadro de diálogo de propiedades de transporte WCF-NetNamedPipe, envío,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
5.  En el **propiedades de transporte de WCF-NetNamedPipe** cuadro de diálogo, en la **seguridad** ficha, defina las capacidades de seguridad del puerto de envío WCF-NetNamedPipe. Para obtener más información sobre la **seguridad** pestaña en el **propiedades de transporte de WCF-NetNamedPipe** cuadro de diálogo, vea la **cuadro de diálogo de propiedades de transporte WCF-NetNamedPipe, envío, seguridad**  ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
6.  En el **propiedades de transporte de WCF-NetNamedPipe** cuadro de diálogo, en la **mensajes** ficha, especifique la selección de datos de SOAP **cuerpo** elemento. Para obtener más información sobre la **mensajes** pestaña en el **propiedades de transporte de WCF-NetNamedPipe** cuadro de diálogo, vea el **mensajes del cuadro de diálogo de propiedades de transporte WCF-NetNamedPipe, envío,**  ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="configure-a-wcf-netnamedpipe-send-port-programmatically"></a>Configurar un puerto de envío WCF-NetNamedPipe mediante programación
  
 Puede usar el siguiente formato para establecer las propiedades:  
  
```  
<CustomProps>  
  <TransportProtectionLevel vt="8">EncryptAndSign</TransportProtectionLevel>  
  <TransactionProtocol vt="8">OleTransactions</TransactionProtocol>  
  <InboundBodyPathExpression vt="8" />  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <EnableTransaction vt="11">0</EnableTransaction>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
</CustomProps>  
  
```  
  
 El siguiente fragmento de código muestra la creación de un puerto de envío WCF-NetNamedPipe:  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetNamedPipe send port.  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-NetNamedPipe"];  
sendPort.PrimaryTransport.Address = "net.pipe://mycomputer/private/samplequeue";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  
  
## <a name="see-also"></a>Vea también  
 [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)   
 [Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)   
 [Configurar el adaptador de WCF-NetNamedPipe](../core/configuring-the-wcf-netnamedpipe-adapter.md)   
 [Configuración de puertos de envío dinámico mediante el uso de propiedades de contexto de adaptadores de WCF](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)