---
title: Configurar un puerto de envío WCF-WSHttp | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035d9a62-b8a3-4705-a7bc-b62676437206
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4b27136c01db4414d43d30790474a0deb339aee
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752354"
---
# <a name="how-to-configure-a-wcf-wshttp-send-port"></a>Cómo configurar un puerto de envío WCF-WSHttp
Los puertos de de envío WCF-WSHttp pueden configurarse mediante programación, o bien utilizando la consola de administración de BizTalk.  

## <a name="configuration-properties"></a>Propiedades de configuración

 El modelo de objetos del explorador de BizTalk expone una interfaz específica del adaptador para puertos de envío denominado **ITransportInfo** que tiene el **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta una bolsa de propiedades de configuración de puerto de envío WCF-WSHttp con la forma de pareja nombre-valor de cadenas XML.  

 El **TransportTypeData** propiedad de la **ITransportInfo** interfaz no es necesaria. Si no se establece, el adaptador usa los valores predeterminados para la configuración del puerto de envío WCF-WSHttp, como se indica en la siguiente tabla.  

 En la tabla siguiente se enumeran las propiedades de configuración que pueden establecerse en el modelo de objetos para el Explorador de BizTalk para los puertos de envío WCF-WSHttp.  


| Nombre de propiedad | Tipo |  Descripción |
|---|---|---|
| **Identidad**            |  Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;identidad&gt;<br /><br /> &lt;valor de userPrincipalName = "username@contoso.com" /&gt;<br /><br /> &lt;/Identity&gt; |  Especifique la identidad de servicio que espera este puerto de envío. Esta configuración permite al puerto de envío autenticar el servicio. En el proceso de negociación entre el cliente y el servicio, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad del servicio esperado coincide con los valores de este elemento.<br /><br /> El valor predeterminado es una cadena vacía.  |
|  **StaticAction**          |  : Cadena  | Especifique el **SOAPAction** campo de encabezado HTTP para mensajes salientes. Esta propiedad también se puede establecer a través de la propiedad de contexto de mensaje **WCF. Acción** en una canalización u orquestación. Puede especificar este valor de dos maneras diferentes: el formato de acción única y el formato de asignación de acciones. Si establece esta propiedad en el formato de acción única: por ejemplo, <`http://contoso.com/Svc/Op1-`> el **SOAPAction** encabezado mensajes salientes siempre se establece en el valor especificado en esta propiedad.<br /><br /> Si establece esta propiedad en el formato de asignación de acción, la salida **SOAPAction** encabezado viene determinada por la **BTS. Operación** propiedad de contexto. Por ejemplo, si esta propiedad se establece en el siguiente formato XML y el **BTS. Operación** propiedad está establecida en Op1, el adaptador de envío WCF usa <http://contoso.com/Svc/Op1> para salida **SOAPAction** encabezado.<br /><br /> \<BtsActionMapping\><br /><br /> \<Nombre de la operación = "Op1" Action = "<http://contoso.com/Svc/Op1>" /\><br /><br /> \<Nombre de la operación = "Op2" Action = "<http://contoso.com/Svc/Op2>" /\><br /><br /> \</ BtsActionMapping\><br /><br /> Si los mensajes salientes proceden de un puerto de orquestación, las instancias de orquestación establecen dinámicamente el **BTS. Operación** propiedad con el nombre de la operación del puerto. Si los mensajes salientes se enrutan con enrutamiento por contenidos, puede establecer el **BTS. Operación** propiedad en componentes de canalización.<br /><br /> El valor predeterminado es una cadena vacía. |
|          **OpenTimeout**          | **System.TimeSpan** |  Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de apertura del canal.<br /><br /> Valor predeterminado: 00:01:00  |
|          **SendTimeout**          | **System.TimeSpan**  |  Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de envío. Si usa un puerto de envío de petición-respuesta, este valor especifica un marco temporal para que se complete la interacción, incluso cuando el servicio devuelva un mensaje grande.<br /><br /> Valor predeterminado: 00:01:00  |
|         **CloseTimeout**          |  **System.TimeSpan**  |  Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de cierre del canal.<br /><br /> Valor predeterminado: 00:01:00  |
|    **MaxReceivedMessageSize**     | Integer  | Especificar el tamaño máximo, en bytes, para mensajes (con encabezados incluidos) que se pueden recibir a través de la red. El tamaño de los mensajes se limita mediante la cantidad de memoria asignada a cada mensaje. Puede usar esta propiedad para limitar la exposición a ataques por denegación de servicio (DoS).<br /><br /> Valor predeterminado: 65536  |
|        **MessageEncoding**        |  Enum<br /><br /> -   **Texto** -usar un codificador de mensajes de texto.<br />-   **MTOM** -usar un codificador Message Transmission organización Mechanism 1.0 (MTOM).  |  Especificar el codificador que se usa para codificar el mensaje SOAP.<br /><br /> Valor predeterminado: **texto**  |
|         **TextEncoding**          | Enum<br /><br /> -   **unicodeFFF** -codificación Unicode BigEndian.<br />-   **UTF-16** : 16 bits de codificación.<br />-   **UTF-8** : 8 bits de codificación.  | Especificar el juego que se usará para emitir los mensajes en el enlace de codificación de caracteres cuando el **MessageEncoding** propiedad está establecida en **texto**.<br /><br /> Valor predeterminado: **utf-8**  |
|       **EnableTransaction**       |  Boolean  |  Especificar si un mensaje se transmite al servicio de destino y se elimina de la base de datos de cuadro de mensajes en un contexto transaccional usando el **WS-AtomicTransaction** protocolo.<br /><br /> Valor predeterminado: **False**  |
|         **SecurityMode**          |  Enum<br /><br /> -   **Ninguno**<br />-   **Mensaje**<br />-   **Transporte**<br />-   **TransportWithMessageCredential**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **SecurityMode** propiedad, vea el **modo de seguridad** propiedad en el **delcuadrodediálogodepropiedadesdetransporteWCF-WSHttp,envío,seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].   | Especificar el tipo de seguridad que se usa.<br /><br /> Valor predeterminado: **ninguno**  |
| **TransportClientCredentialType** |  Enum<br /><br /> -   **Ninguno**<br />-   **Básico**<br />-   **Windows**<br />-   **Certificado**<br />-   **Resumen**<br />-   **NTLM**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **TransportClientCredentialType** propiedad, vea el **tipo de credencial de cliente de transporte** propiedad en el **transporte WCF-WSHttp Seguridad de propiedades del cuadro de diálogo, envío,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  |  Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación del puerto de envío.<br /><br /> Valor predeterminado: **ninguno**  |
|  **MessageClientCredentialType**  | Enum<br /><br /> -   **Ninguno**<br />-   **Windows**<br />-   **Nombre de usuario**<br />-   **Certificado**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **MessageClientCredentialType** propiedad, vea el **tipo de credencial de cliente de mensajes** propiedad en el **propiedades de transporte WCF-WSHttp Cuadro de diálogo cuadro, envío, seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  | Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación de cliente mediante la seguridad basada en mensajes.<br /><br /> Valor predeterminado: **nombre de usuario**  |
|        **AlgorithmSuite**         | Enum<br /><br /> Para obtener más información acerca de los nombres de miembro para el **AlgorithmSuite** propiedad, vea el **algorithmsuite** propiedad en el **cuadro de diálogo de propiedades de transporte WCF-WSHttp, envío, seguridad**  ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  |  Especificar el cifrado de mensajes y los algoritmos de encapsulado de claves. Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).<br /><br /> Valor predeterminado: **Basic256**  |
|  **NegotiateServiceCredential**   |  Boolean<br /><br /> Para obtener más información acerca de los nombres de miembro para el **NegotiateServiceCredential** propiedad, vea el **negociar credencial de servicio** propiedad en el **propiedades de transporte WCF-WSHttp Cuadro de diálogo cuadro, envío, seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. |  Especificar si la credencial de servicio se suministra en este puerto de envío fuera de banda o se obtiene del servicio en este puerto de envío a través de un proceso de negociación. Dicha negociación es precursora del intercambio de mensajes habitual.<br /><br /> Valor predeterminado: **False**|
|     **EnableSecurityContext**     | Boolean  |  Especificar si un token de contexto de seguridad se establece mediante un **WS-SecureConversation** exchange entre este puerto de envío y el servicio. Si esta propiedad se establece en **True** , a continuación, el servicio de destino debe admitir **WS-SecureConversation**.<br /><br /> Valor predeterminado: **True**  |
|       **ClientCertificate**       | String  |  Especificar la huella digital del certificado X.509 para la autenticación de este puerto de envío en servicios. Esta propiedad es necesaria si la **ClientCredentialsType** propiedad está establecida en **certificado**. El certificado que se usará para esta propiedad debe estar instalado en el **mi** almacenar en el **usuario actual** ubicación.<br /><br /> El valor predeterminado es una cadena vacía. |
|      **ServiceCertificate**       |  String  |  Especificar la huella digital del certificado X.509 para la autenticación del servicio al que este puerto de envío envía mensajes. El certificado que se usará para esta propiedad debe estar instalado en el **otras personas** almacenar en el **máquina Local** ubicación.<br /><br /> El valor predeterminado es una cadena vacía.  |
|   **AffiliateApplicationName**    |  String  | Especificar la aplicación afiliada que se utilizará para el inicio de sesión único empresarial (SSO).<br /><br /> El valor predeterminado es una cadena vacía. |
|            **UseSSO**             |   Boolean  |  Especificar si se utiliza el inicio de sesión único (SSO) para recuperar credenciales de cliente para la autenticación con el servidor de destino.<br /><br /> Valor predeterminado: **False** |
|           **UserName**            |  String  |  Especifique el nombre de usuario que se usará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**. No tiene que usar el formato dominio\usuario para esta propiedad.<br /><br /> El valor predeterminado es una cadena vacía. |
|           **Contraseña**            |  String  | Especifique la contraseña que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**.<br /><br /> El valor predeterminado es una cadena vacía. |
|          **ProxyToUse**           | Enum<br /><br /> -   **Ninguno** -no usar un servidor proxy para este puerto de envío.<br />-   **Default** -usar la configuración de proxy en el controlador de envío que aloja este puerto de envío.<br />-   **UserSpecified** -usar el servidor proxy especificado en el **ProxyAddress** propiedad.  | Especificar el servidor de proxy que se va a utilizar para el tráfico HTTP saliente.<br /><br /> Valor predeterminado: **ninguno**  |
|         **ProxyAddress**          | String |  Especificar la dirección del servidor proxy. Use la **https** o **http** esquema según la configuración de seguridad. Esta dirección puede ir seguida de dos puntos y el número de puerto. Por ejemplo, `http://127.0.0.1:8080`.<br /><br /> El valor predeterminado es una cadena vacía. |
|         **ProxyUserName**         |  String  | Especificar el nombre de usuario que se utilizará para el proxy. El adaptador de WCF-WSHttp aprovecha la [WSHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81206) en el modo de transferencia almacenado en búfer para comunicarse con un punto de conexión. Credenciales del proxy de **WSHttpBinding** son aplicables solo cuando el modo de seguridad es **transporte**, o **ninguno**. Si establece la **SecurityMode** propiedad **mensaje** o **TransportWithMessageCredential**, el adaptador WCF-WSHttp no utiliza la credencial especificada en el  **ProxyUserName** y **ProxyPassword** propiedades para la autenticación con el proxy. **Nota:** WCF-WSHttp adaptador de envío utiliza la autenticación básica para el proxy. <br /><br /> El valor predeterminado es una cadena vacía.  |
|         **ProxyPassword**         |  String  |  Especificar la contraseña que se utilizará para el proxy.<br /><br /> El valor predeterminado es una cadena vacía.|
|     **OutboundBodyLocation**      |  Enum<br /><br /> -   **UseBodyElement** -usar la parte del cuerpo de mensaje de BizTalk para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.<br />-   **UseTemplate** -usar la plantilla proporcionada en el **OutboundXMLTemplate** propiedad para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.<br /><br /> Para obtener más información sobre cómo usar el **OutboundBodyLocation** propiedad, vea [especificando el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).  |  Especifique la selección de datos de SOAP **cuerpo** elemento de mensajes WCF salientes.<br /><br /> Valor predeterminado: **UseBodyElement**  |
|      **OutboundXMLTemplate**      |  String<br /><br /> Para obtener más información sobre cómo usar el **OutboundXMLTemplate** propiedad, vea [especificando el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).  |  Especifique la plantilla con formato XML para el contenido del mensaje SOAP **cuerpo** elemento de un mensaje saliente. Esta propiedad es necesaria si la **OutboundBodyLocation** propiedad está establecida en **UseTemplate**.<br /><br /> El valor predeterminado es una cadena vacía.  |
|      **InboundBodyLocation**      | Enum<br /><br /> -   **UseBodyElement** -usar el contenido del mensaje SOAP **cuerpo** elemento de un mensaje entrante para crear la parte del cuerpo de mensaje de BizTalk. Si el elemento **Body** tiene varios elementos secundarios, sólo el primero de ellos será la parte del cuerpo del mensaje de BizTalk. Esta propiedad sólo es válida para puertos de petición-respuesta.<br />-   **UseEnvelope** -crear la parte del cuerpo de mensaje de BizTalk de SOAP completo **sobres** de un mensaje entrante.<br />-   **UseBodyPath** -usar la expresión de ruta de cuerpo en el **InboundBodyPathExpression** propiedad para crear la parte del cuerpo de mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del elemento **Cuerpo** de SOAP de un mensaje entrante. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyLocation** propiedad, vea [especificando el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md). |  Especifique la selección de datos de SOAP **cuerpo** elemento de mensajes WCF entrantes.<br /><br /> Valor predeterminado: **UseBodyElement**  |
|   **InboundBodyPathExpression**   |  String<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyPathExpression** propiedad, vea [propiedades y esquema de propiedades de adaptadores de WCF](../core/wcf-adapters-property-schema-and-properties.md).  |  Especificar la expresión de ruta de cuerpo para identificar una parte específica de un mensaje entrante utilizada para crear la parte del cuerpo del mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del SOAP **cuerpo** nodo de un mensaje entrante. Si esta expresión de ruta de cuerpo devuelve varios nodos, solo se elegirá el primero de ellos para la parte del cuerpo del mensaje de BizTalk. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> El valor predeterminado es una cadena vacía.  |
|      **InboundNodeEncoding**      |  Enum<br /><br /> -   **Base64** -codificación Base64.<br />-   **Hex** : Hexadecimal codificación.<br />-   **Cadena** : codificación de texto - UTF-8.<br />-   **XML** -los adaptadores WCF crean el cuerpo del mensaje de BizTalk con el XML externo del nodo seleccionado por la expresión de ruta de cuerpo en **InboundBodyPathExpression**.  |  Especifique el tipo de codificación que el adaptador de envío WCF-WSHttp usa para descodificar el nodo identificado por la ruta de cuerpo especificada en **InboundBodyPathExpression**. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Valor predeterminado: **XML**  |
|     **PropagateFaultMessage**     | Boolean<br /><br /> -   **True** -enrutar el mensaje que se produce un error de procesamiento de salida a una aplicación de suscripción (por ejemplo, otro programación de orquestación o puerto de recepción).<br />-   **False** -suspender mensajes erróneos y generar una confirmación negativa (NACK). |  Especificar si se enrutan o se suspenden mensajes que han generado errores en el procesamiento de salida.<br /><br /> Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Valor predeterminado: **True**  |

## <a name="configure-a-wcf-wshttp-send-port-with-the-biztalk-administration-console"></a>Configurar un puerto de envío WCF-WSHttp con la consola de administración de BizTalk

 Se pueden establecer variables del adaptador de puerto de envío WCF-WSHttp en la consola de administración de BizTalk. Si no se establecen las propiedades del puerto de envío, se usan los valores predeterminados de la configuración del puerto de envío WCF-WSHttp, como se indica en la tabla anterior.  

## <a name="configure-variables-for-a-wcf-wshttp-send-port"></a>Configurar variables para un puerto de envío WCF-WSHttp  

1. En la consola de administración de BizTalk, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones de puerto de envío y especifique **WCF-WSHttp** para el **tipo** opción el **transporte** sección de la **General** pestaña.  

2. En el **General** ficha la **transporte** sección, haga clic en el **configurar** situado junto a **tipo**.  

3. En el **propiedades de transporte WCF-WSHttp** cuadro de diálogo el **General** pestaña, configure la dirección del punto de conexión, la identidad del servicio y el **SOAPAction** encabezado HTTP el puerto de envío WCF-WSHttp. Para obtener más información sobre la **General** pestaña en el **propiedades de transporte WCF-WSHttp** cuadro de diálogo, vea el **cuadro de diálogo de propiedades de transporte WCF-WSHttp, envío, General** pestaña [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  

4. En el **propiedades de transporte WCF-WSHttp** cuadro de diálogo el **enlace** pestaña, configure las propiedades de tiempo de espera, codificación y transacción. Para obtener más información sobre la **enlace** pestaña en el **propiedades de transporte WCF-WSHttp** cuadro de diálogo, vea el **enlace del cuadro de diálogo de propiedades de transporte WCF-WSHttp, envío,** pestaña [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  

5. En el **propiedades de transporte WCF-WSHttp** cuadro de diálogo el **seguridad** pestaña, defina las capacidades de seguridad del puerto de envío WCF-WSHttp. Para obtener más información sobre la **seguridad** pestaña en el **propiedades de transporte WCF-WSHttp** cuadro de diálogo, vea el **delcuadrodediálogodepropiedadesdetransporteWCF-WSHttp,envío,seguridad**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

6. En el **propiedades de transporte WCF-WSHttp** cuadro de diálogo el **Proxy** pestaña, configure la configuración de proxy para el puerto de envío WCF-WSHttp. Para obtener más información sobre la **Proxy** pestaña en el **propiedades de transporte WCF-WSHttp** cuadro de diálogo, vea el **Proxy del cuadro de diálogo de propiedades de transporte WCF-WSHttp, envío,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

7. En el **propiedades de transporte WCF-WSHttp** cuadro de diálogo el **mensajes** ficha, especifique la selección de datos de SOAP **cuerpo** elemento. Para obtener más información sobre la **mensajes** pestaña en el **propiedades de transporte WCF-WSHttp** cuadro de diálogo, vea el **mensajes del cuadro de diálogo de propiedades de transporte WCF-WSHttp, envío,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

## <a name="configure-a-wcf-wshttp-send-port-programmatically"></a>Configurar un puerto de envío WCF-WSHttp mediante programación

 Puede usar el siguiente formato para establecer las propiedades:  

```  
 <CustomProps>    
  <ServiceCertificate vt="8" />  
  <UseSSO vt="11">0</UseSSO>  
  <InboundBodyPathExpression vt="8" />  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <Identity vt="8" />  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Message</SecurityMode>  
  <TransportClientCredentialType vt="8">Windows</TransportClientCredentialType>  
  <TextEncoding vt="8">utf-8</TextEncoding>  
  <NegotiateServiceCredential vt="11">-1</NegotiateServiceCredential>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <ClientCertificate vt="8" />  
  <ProxyUserName vt="8" />  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <ProxyToUse vt="8">Default</ProxyToUse>  
  <EnableTransaction vt="11">0</EnableTransaction>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <EstablishSecurityContext vt="11">-1</EstablishSecurityContext>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
  <ProxyAddress vt="8" />  
  <MessageEncoding vt="8">Text</MessageEncoding>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  

```  

 El siguiente fragmento de código muestra la creación de un puerto de envío WCF-WSHttp:  

```  
// Use BizTalk Explorer object model to create new WCF-WSHttp send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 <StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
                                 <MessageEncoding vt=""8"">Text</MessageEncoding>  
                                 <TextEncoding vt=""8"">utf-8</TextEncoding>  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-WSHttp"];  
sendPort.PrimaryTransport.Address = "http://mycomputer/samplepath";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  

## <a name="see-also"></a>Vea también  
 [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)   
 [Configuración del adaptador de WCF-WSHttp](../core/configuring-the-wcf-wshttp-adapter.md)   
 [Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)   
 [Configuración de puertos de envío dinámico mediante el uso de propiedades de contexto de adaptadores de WCF](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)
