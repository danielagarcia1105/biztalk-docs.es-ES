---
title: "Cómo configurar un puerto de envío WCF-NetMsmq | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13f55e53-12af-473b-b73f-1c98edadfc28
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6475e7a33f31a4a2a609f1af90301ad96cecb74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-netmsmq-send-port"></a>Cómo configurar un puerto de envío WCF-NetMsmq 
Los puertos de de envío WCF-NetMsmq pueden configurarse mediante programación, o bien utilizando la consola de administración de BizTalk.  
  
## <a name="configuration-properties"></a>Propiedades de configuración
  
 El modelo de objetos del explorador de BizTalk expone una interfaz específica del adaptador para puertos de envío denominado **ITransportInfo** que tiene el **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta una bolsa de propiedades de configuración de puerto de envío WCF-NetMsmq con la forma de par nombre-valor de cadenas XML.  
  
 El **TransportTypeData** propiedad de la **ITransportInfo** interfaz no es necesaria. Si no se establece, el adaptador usa los valores predeterminados para la configuración del puerto de envío WCF-NetMsmq, como se indica en la siguiente tabla.  
  
 En la tabla siguiente se enumeran las propiedades de configuración que pueden definirse en el Modelo de objetos para el Explorador de BizTalk para los puertos de envío WCF-NetMsmq.  
  
|Nombre de la propiedad|Tipo|Description|  
|-------------------|----------|-----------------|  
|**Identidad**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;identidad&gt;<br /><br /> &lt;valor de userPrincipalName = "username@contoso.com" /&gt;<br /><br /> &lt;/Identity&gt;|Especifique la identidad de servicio que espera este puerto de envío. Esta configuración permite al puerto de envío autenticar el servicio. En el proceso de negociación entre el cliente y el servicio, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad del servicio esperado coincide con los valores de este elemento.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**StaticAction**|String|Especifique el **SOAPAction** campo de encabezado para los mensajes salientes. Esta propiedad también puede establecerse a través de la propiedad de contexto de mensaje **WCF. Acción** en una canalización o una orquestación. Puede especificar este valor de dos maneras diferentes: el formato de acción única y el formato de asignación de acciones. Si establece esta propiedad en el formato de acción única-por ejemplo, http://contoso.com/Svc/Op1-el **SOAPAction** encabezado mensajes salientes siempre se establece en el valor especificado en esta propiedad.<br /><br /> Si establece esta propiedad en el formato de asignación de acción, la salida **SOAPAction** encabezado viene determinado por la **BTS. Operación** propiedad de contexto. Por ejemplo, si esta propiedad se establece en el siguiente formato XML y **BTS. Operación** propiedad está establecida en Op1, el adaptador de envío WCF usa http://contoso.com/Svc/Op1 para el saliente **SOAPAction** encabezado.<br /><br /> \<BtsActionMapping ><br /><br /> \<Nombre de la operación = "Op1" Action = "http://contoso.com/Svc/Op1" / ><br /><br /> \<Nombre de la operación = "Op2" Action = "http://contoso.com/Svc/Op2" / ><br /><br /> \</ BtsActionMapping ><br /><br /> Si los mensajes salientes proceden de un puerto de orquestación, las instancias de orquestación establecen dinámicamente la **BTS. Operación** propiedad con el nombre de la operación del puerto. Si los mensajes salientes se enrutan con enrutamiento por contenidos, puede establecer el **BTS. Operación** propiedad en componentes de canalización.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**OpenTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de apertura del canal.<br /><br /> Valor predeterminado: 00:01:00|  
|**SendTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de envío. Si usa un puerto de envío de petición-respuesta, este valor especifica un marco temporal para que se complete la interacción, incluso cuando el servicio devuelva un mensaje grande.<br /><br /> Valor predeterminado: 00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de cierre del canal.<br /><br /> Valor predeterminado: 00:01:00|  
|**EnableTransactional**|Boolean|Especificar el tipo de la cola de mensajes del servicio de destino: transaccional o no transaccional. Si esta propiedad se establece en **True**, cada mensaje procesado por este puerto de envío se entrega sólo una vez y se notifica al remitente de errores de entrega. Para enviar mensajes a través de envío transaccional de puertos, tanto el **duradero** y **exactlyOnce** elementos del servicio de enlace deben estar establecido en **True**. Si esta propiedad se establece en **False**, los mensajes se transfieren sin garantía de entrega.<br /><br /> Valor predeterminado: **True**|  
|**DeadLetterQueue**|Enum<br /><br /> -   **Ninguno** -ninguna cola de mensajes no enviados que se va a usarse.<br />-   **Sistema** -utilizar la cola de mensajes no enviados para todo el sistema.<br />-   **Personalizado** -usar una cola de mensajes no enviados personalizada.|Especificar la cola de mensajes con problemas de entrega a la que se transferirán los mensajes que no se han podido entregar a la aplicación. Para obtener más información sobre los mensajes entregados a la cola de mensajes no enviados, consulte el **enlace de cuadro de diálogo de propiedades de transporte WCF-NetMsmq, envío,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].<br/><br/> **Tenga en cuenta**: la cola de mensajes no enviados personalizada se admite sólo en Message Queuing (MSMQ) 4.0, lanzado con Windows Vista. <br /><br /> Valor predeterminado: **sistema**|  
|**CustomDeadLetterQueue**|String|Especifique el URI completo con el **net.msmq** esquema para la ubicación de la cola de mensajes no enviados por aplicación, donde se colocan los mensajes que han expirado o cuya transferencia o entrega ha fallado. Por ejemplo, net.msmq://localhost/deadLetterQueueName. La cola de mensajes con problemas de entrega es una cola en el administrador de cola de la aplicación de envío para mensajes caducados que no se han podido entregar. Esta propiedad es necesaria si la **DeadLetterQueue** propiedad está establecida en **personalizado**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**TimeToLive**|**System.TimeSpan**|Especificar el período de validez de los mensajes antes de que caduquen y se coloquen en la cola de mensajes con problemas de entrega. Esta propiedad se define para garantizar que los mensajes con limitaciones temporales no se conviertan en obsoletos antes de que este puerto de envío los procese. Se dice que los mensajes que se encuentren en una cola y no hayan sido consumidos por este puerto de envío en el intervalo especificado caducarán. Los mensajes caducados se envían a una cola especial denominada cola de mensajes con problemas de entrega. La ubicación de la cola de mensajes no enviados se establece con el **DeadLetterQueue** propiedad.<br /><br /> Valor predeterminado: 1.00:00:00|  
|**UseSourceJournal**|Boolean|Especificar si se deben almacenar copias de mensajes procesados por este puerto de envío en la cola de diario de origen.<br /><br /> Valor predeterminado: **False**|  
|**SecurityMode**|Enum<br /><br /> -   **Ninguno**<br />-   **Mensaje**<br />-   **Transporte**<br />-   **Ambos**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **SecurityMode** propiedad, vea la **modo de seguridad** propiedad en el **delcuadrodediálogodepropiedadesdetransporteWCF-NetMsmq,envío,seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el tipo de seguridad que se usa.<br /><br /> Valor predeterminado: **transporte**|  
|**MsmqAuthenticationMode**|Enum<br /><br /> -   **Ninguno**<br />-   **WindowsDomain**<br />-   **Certificado**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **MsmqAuthenticationMode** propiedad, vea la **MsmqAuthenticationMode** propiedad en el **el cuadro de diálogo de propiedades de transporte de WCF-NetMsmq Enviar, seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar cómo el transporte de MSMQ debe autenticar el mensaje.<br /><br /> Valor predeterminado: **WindowsDomain**|  
|**MsmqProtectionLevel**|Enum<br /><br /> -   **Ninguno**: sin protección.<br />-   **Inicio de sesión**: se firman los mensajes.<br />-   **EncryptAndSign**: los mensajes se cifrarán y firmarán. Para usar este nivel de protección, debe habilitar **integración de Active Directory** para **MSMQ**.|Especificar el modo en que los mensajes están protegidos en el nivel de transporte de MSMQ.<br /><br /> Valor predeterminado: **inicio de sesión**|  
|**MsmqSecureHashAlgorithm**|Enum<br /><br /> -   **MD5**<br />-   **SHA1**<br />-   **SHA25**<br />-   **SHA512**|Especificar el algoritmo hash que se usará para calcular la síntesis del mensaje. Esta propiedad no está disponible si la **MsmqProtectionLevel** propiedad está establecida en **ninguno**.<br /><br /> Valor predeterminado: **SHA1**|  
|**MsmqEncryptionAlgorithm**|Enum<br /><br /> -   **RC4Stream**<br />-   **AES**|Especificar el algoritmo que se usará para el cifrado de mensajes a través de la red al transferir mensajes entre los administradores de cola de mensajes. Esta propiedad está disponible solo si el **MsmqProtectionLevel** propiedad está establecida en **EncryptAndSign**.<br /><br /> Valor predeterminado: **RC4Stream**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **Ninguno**<br />-   **Windows**<br />-   **Nombre de usuario**<br />-   **Certificado**<br /><br /> Para obtener más información acerca de los nombres de miembro para el **MessageClientCredentialType** propiedad, vea la **tipo de credencial de cliente de mensaje** propiedad en la **propiedades de transporte de WCF-NetMsmq Cuadro de diálogo cuadro, envío, seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación de cliente mediante la seguridad basada en mensajes.<br /><br /> Valor predeterminado: **Windows**|  
|**AlgorithmSuite**|Enum<br /><br /> Para obtener más información acerca de los nombres de miembro para el **AlgorithmSuite** propiedad, vea la **conjunto de algoritmos** propiedad en la **cuadro de diálogo de propiedades de transporte WCF-NetMsmq, envío, seguridad**  ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el cifrado de mensajes y los algoritmos de encapsulado de claves. Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).<br /><br /> Valor predeterminado: **Basic256**|  
|**ClientCertificate**|String|Especificar la huella digital del certificado X.509 para la autenticación de este puerto de envío en servicios. Esta propiedad es necesaria si la **ClientCredentialsType** propiedad está establecida en **certificado**. El certificado que se usará para esta propiedad debe estar instalado en el **mi** almacenar en la **usuario actual** ubicación.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**ServiceCertificate**|String|Especificar la huella digital del certificado X.509 para la autenticación del servicio al que este puerto de envío envía mensajes. El certificado que se usará para esta propiedad debe estar instalado en el **otras personas** almacenar en la **equipo Local** ubicación.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**AffiliateApplicationName**|String|Especificar la aplicación afiliada que se utilizará para el inicio de sesión único empresarial (SSO).<br /><br /> El valor predeterminado es una cadena vacía.|  
|**UseSSO**|Boolean|Especificar si se utiliza el inicio de sesión único (SSO) para recuperar credenciales de cliente para la autenticación con el servidor de destino.<br /><br /> Valor predeterminado: **False**|  
|**UserName**|String|Especifique el nombre de usuario que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**. No tiene que usar el formato dominio\usuario para esta propiedad.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**Contraseña**|String|Especifique la contraseña que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar la parte del cuerpo de mensaje de BizTalk para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.<br />-   **UseTemplate** -usar la plantilla proporcionada en el **OutboundXMLTemplate** propiedad que se va a crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.<br /><br /> Para obtener más información sobre cómo usar el **OutboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF salientes.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**OutboundXMLTemplate**|String<br /><br /> Para obtener más información sobre cómo usar el **OutboundXMLTemplate** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la plantilla con formato XML para el contenido del mensaje SOAP **cuerpo** elemento de un mensaje saliente. Esta propiedad es necesaria si la **OutboundBodyLocation** propiedad está establecida en **UseTemplate**.<br /><br /> El valor predeterminado es una cadena vacía.|  
  
## <a name="configure-a-wcf-netmsmq-send-port-with-the-biztalk-administration-console"></a>Configurar un puerto de envío WCF-NetMsmq con la consola de administración de BizTalk
  
 Se pueden establecer variables del adaptador de puerto de envío WCF-NetMsmq en la consola de administración de BizTalk. Si no se establecen las propiedades del puerto de envío, se usan los valores predeterminados de la configuración del puerto de envío WCF-NetMsmq, como se indica en la tabla anterior.  
  
## <a name="configure-variables-for-a-wcf-netmsmq-send-port"></a>Configurar variables para un puerto de envío WCF-NetMsmq  
  
1.  En la consola de administración de BizTalk, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones del puerto de envío y especifique **WCF-NetMsmq** para el **tipo** opción en el **transporte** sección de la **General** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
2.  En el **General** ficha la **transporte** sección, haga clic en el **configurar** situado junto a **tipo**.  
  
3.  En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo la **General** pestaña, configure la dirección del extremo, la identidad del servicio y la **SOAPAction** encabezado para el Puerto de envío WCF-NetMsmq. Para obtener más información sobre la **General** pestaña en el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, vea la **cuadro diálogo de propiedades de transporte WCF-NetMsmq, envío, General**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
4.  En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, en la **enlace** pestaña, configure las propiedades de tiempo de espera y la transacción y configuración de cola. Para obtener más información sobre la **enlace** pestaña en el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, vea el **enlace de cuadro de diálogo de propiedades de transporte WCF-NetMsmq, envío,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
5.  En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, en la **seguridad** ficha, defina las capacidades de seguridad del puerto de envío WCF-NetMsmq. Para obtener más información sobre la **seguridad** pestaña en el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, vea el **delcuadrodediálogodepropiedadesdetransporteWCF-NetMsmq,envío,seguridad**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
6.  En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, en la **mensajes** ficha, especifique la selección de datos de SOAP **cuerpo** elemento. Para obtener más información sobre la **mensajes** pestaña en el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, vea el **mensajes del cuadro de diálogo de propiedades de transporte WCF-NetMsmq, envío,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
## <a name="configure-a-wcf-netmsmq-send-port-programmatically"></a>Configurar un puerto de envío WCF-NetMsmq mediante programación
  
 Puede usar el siguiente formato para establecer las propiedades:  
  
```  
<CustomProps>  
  <ServiceCertificate vt="8" />  
  <UseSSO vt="11">0</UseSSO>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <MsmqProtectionLevel vt="8">Sign</MsmqProtectionLevel>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <UseSourceJournal vt="11">0</UseSourceJournal>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <CustomDeadLetterQueue vt="8" />  
  <ClientCertificate vt="8" />  
  <MsmqEncryptionAlgorithm vt="8">RC4Stream</MsmqEncryptionAlgorithm>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <MsmqSecureHashAlgorithm vt="8">Sha1</MsmqSecureHashAlgorithm>  
  <EnableTransaction vt="11">-1</EnableTransaction>  
  <TimeToLive vt="8">1.00:00:00</TimeToLive>  
  <MsmqAuthenticationMode vt="8">WindowsDomain</MsmqAuthenticationMode>  
  <DeadLetterQueue vt="8">System</DeadLetterQueue>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 El siguiente fragmento de código muestra la creación de un puerto de envío WCF-NetMsmq:  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetMsmq send port.  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-NetMsmq"];  
sendPort.PrimaryTransport.Address = "net.msmq://mycomputer/private/samplequeue";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  
  
## <a name="see-also"></a>Vea también  
 [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)   
 [Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)   
 [Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [Configurar el adaptador de WCF-NetMsmq](../core/configuring-the-wcf-netmsmq-adapter.md)   
 [Configuración de puertos de envío dinámicos mediante propiedades de contexto de adaptadores de WCF](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)