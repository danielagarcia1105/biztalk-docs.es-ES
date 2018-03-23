---
title: Cómo configurar un puerto de envío WCF-Custom | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a195c047-5d5c-478b-accd-252e9dc5cfe8
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c615e2f54e1d7db9115a2607162f6eae1dffc01a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-configure-a-wcf-custom-send-port"></a>Cómo configurar un puerto de envío WCF-Custom
Los puertos de envío WCF-Custom pueden configurarse mediante programación, o bien utilizando la consola de administración de BizTalk.  
  
## <a name="configuration-properties"></a>Propiedades de configuración
  
 El modelo de objetos del explorador de BizTalk expone una interfaz específica del adaptador para puertos de envío denominado **ITransportInfo** que tiene el **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta una bolsa de propiedades de configuración de puerto de envío WCF-Custom con la forma de par nombre-valor de cadenas XML.  
  
 El **TransportTypeData** propiedad de la **ITransportInfo** interfaz no es necesaria. Si no se establece, el adaptador usa los valores predeterminados para la configuración del puerto de envío WCF-Custom, como se indica en la siguiente tabla.  
  
 En la tabla siguiente se enumeran las propiedades de configuración que pueden establecerse en el modelo de objetos para el Explorador de BizTalk para los puertos de envío WCF-Custom.  
  
|Nombre de la propiedad|Tipo|Description|  
|-------------------|----------|-----------------|  
|**Identidad**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;Identidad&gt;<br /><br /> &lt;valor de userPrincipalName = "username@contoso.com" /&gt;<br /><br /> &lt;/Identity&gt;|Especifique la identidad de servicio que espera este puerto de envío. Esta configuración permite al puerto de envío autenticar el servicio. En el proceso del protocolo de enlace entre el cliente y el servicio, la infraestructura de WCF garantizará que la identidad de servicio esperada coincida con los valores de este elemento. Los valores que se pueden especificar para el **identidad** propiedad difieren según la configuración de seguridad.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**StaticAction**|String|Especifique el **SOAPAction** campo de encabezado para los mensajes salientes. Esta propiedad también puede establecerse a través de la propiedad de contexto de mensaje **WCF. Acción** en una canalización o una orquestación. Puede especificar este valor de dos maneras diferentes: el formato de acción única y el formato de asignación de acciones. Si establece esta propiedad en el formato de acción única: por ejemplo, http://contoso.com/Svc/Op1- el **SOAPAction** encabezado mensajes salientes siempre se establece en el valor especificado en esta propiedad.<br /><br /> Si establece esta propiedad en el formato de asignación de acción, la salida **SOAPAction** encabezado viene determinado por la **BTS. Operación** propiedad de contexto. Por ejemplo, si esta propiedad se establece en el siguiente formato XML y **BTS. Operación** propiedad está establecida en Op1, el adaptador de envío WCF usa http://contoso.com/Svc/Op1 para los salientes **SOAPAction** encabezado.<br /><br /> \<BtsActionMapping\><br /><br /> \<Nombre de la operación = "Op1" Action = "http://contoso.com/Svc/Op1" /\><br /><br /> \<Nombre de la operación = "Op2" Action = "http://contoso.com/Svc/Op2" /\><br /><br /> \</BtsActionMapping\><br /><br /> Si los mensajes salientes proceden de un puerto de orquestación, las instancias de orquestación establecen dinámicamente la **BTS. Operación** propiedad con el nombre de la operación del puerto. Si los mensajes salientes se enrutan con enrutamiento por contenidos, puede establecer el **BTS. Operación** propiedad en componentes de canalización.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**BindingType**|Enum<br /><br /> Para obtener más información acerca de los nombres de miembro para el **BindingType** propiedad, vea la **BindingType** propiedad en el **enlace de cuadro de diálogo de propiedades de transporte WCF-Custom, envío,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|Especificar el tipo de enlace que se va a usar para el extremo que utiliza este puerto de envío. **Nota:** si utiliza un enlace personalizado, el **BindingType** propiedad puede configurarse con los enlaces personalizados. Para obtener más información sobre cómo usar el enlace personalizado, vea [cómo habilitar los puntos de extensibilidad de WCF con los adaptadores de WCF](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md).|  
|**BindingConfiguration**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;binding name="netNamedPipeBinding"&gt;&lt;readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" /&gt;&lt;security mode="None" /&gt;&lt;/binding&gt;|Especificar una cadena XML con el **\<enlace\>** elemento que se va a configurar los distintos tipos de enlaces predefinidos proporcionados por Windows Communication Foundation (WCF). Para obtener más información acerca del enlace proporcionado por el sistema y el enlace personalizado, vea los temas correspondiente enumerados en la sección Vea también. **Nota:** BizTalk Server no admite todos los tipos de los elementos de extensión de enlace que se pueden configurar con el **BindingConfiguration** propiedad. <br /><br /> El valor predeterminado es una cadena vacía.|  
|**EndpointBehaviorConfiguration**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;nombre = "sampleBehavior"&gt;&lt;callbackTimeouts /&gt;&lt;/behavior&gt;|Especificar una cadena XML con el **\<comportamiento\>** elemento de la **\<endpointBehaviors\>** elemento que se va a configurar las opciones de comportamiento de un Punto de conexión WCF. Para obtener más información sobre la **\<endpointBehaviors\>** elemento, vea el tema correspondiente en la sección Vea también. **Nota:** BizTalk Server no admite todos los tipos de los elementos de extensión de comportamiento que se pueden configurar con el **EndpointBehaviorConfiguration** propiedad. <br /><br /> El valor predeterminado es una cadena vacía.|  
|**AffiliateApplicationName**|String|Especificar la aplicación afiliada que se utilizará para el inicio de sesión único empresarial (SSO).<br /><br /> El valor predeterminado es una cadena vacía.|  
|**UseSSO**|Boolean|Especificar si se utiliza el inicio de sesión único (SSO) para recuperar credenciales de cliente para la autenticación con el servidor de destino.<br /><br /> Valor predeterminado: **False**|  
|**UserName**|String|Especifique el nombre de usuario que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**. No tiene que usar el formato dominio\usuario para esta propiedad.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**Contraseña**|String|Especifique la contraseña que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar la parte del cuerpo de mensaje de BizTalk para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.<br />-   **UseTemplate** -usar la plantilla proporcionada en el **OutboundXMLTemplate** propiedad que se va a crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.<br /><br /> Para obtener más información sobre cómo usar el **OutboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF salientes.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**OutboundXMLTemplate**|String<br /><br /> Para obtener más información sobre cómo usar el **OutboundXMLTemplate** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la plantilla con formato XML para el contenido del mensaje SOAP **cuerpo** elemento de un mensaje saliente. Esta propiedad es necesaria si la **OutboundBodyLocation** propiedad está establecida en **UseTemplate**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar el contenido del mensaje SOAP **cuerpo** elemento de un mensaje entrante para crear la parte del cuerpo de mensaje de BizTalk. Si el elemento **Body** tiene varios elementos secundarios, sólo el primero de ellos será la parte del cuerpo del mensaje de BizTalk. Esta propiedad sólo es válida para puertos de petición-respuesta.<br />-   **UseEnvelope** -crear la parte del cuerpo de mensaje de BizTalk desde el mensaje de SOAP completo **sobres** de un mensaje entrante.<br />-   **UseBodyPath** -usar la expresión de ruta de cuerpo en el **InboundBodyPathExpression** propiedad que se va a crear la parte del cuerpo de mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del elemento **Cuerpo** de SOAP de un mensaje entrante. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF entrantes.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**InboundBodyPathExpression**|String<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyPathExpression** propiedad, vea [propiedades y esquema de propiedades de adaptadores de WCF](../core/wcf-adapters-property-schema-and-properties.md).|Especificar la expresión de ruta de cuerpo para identificar una parte específica de un mensaje entrante utilizada para crear la parte del cuerpo del mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del mensaje SOAP **cuerpo** nodo de un mensaje entrante. Si esta expresión de ruta de cuerpo devuelve varios nodos, solo se elegirá el primero de ellos para la parte del cuerpo del mensaje de BizTalk. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **XML**<br />-   **Base64** -codificación Base64.<br />-   **Hex** : Hexadecimal codificación.<br />-   **Cadena** : codificación de texto - UTF-8.<br />-   **XML** -los adaptadores WCF crean el cuerpo del mensaje de BizTalk con el XML externo del nodo seleccionado por la expresión de ruta de acceso de cuerpo en **InboundBodyPathExpression**.|Especifique el tipo de codificación que el adaptador de envío WCF-Custom se usa para descodificar el nodo identificado por la ruta de cuerpo especificada en **InboundBodyPathExpression**. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Valor predeterminado: **XML**|  
|**PropagateFaultMessage**|Boolean<br /><br /> -   **True** -enrutar el mensaje que se produce un error de procesamiento de salida a una aplicación de suscripción (por ejemplo, otro puerto o programación de orquestación de recepción).<br />-   **False** -suspender mensajes erróneos y generar una confirmación negativa (NACK).|Especificar si se enrutan o se suspenden mensajes que han generado errores en el procesamiento de salida.<br /><br /> Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Valor predeterminado: **True**|  
|**ReferencedBindings**|Blob XML<br /><br /> Ejemplo:<br /><br /> \<**BindingConfiguration** vt="8"\><br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;nombre de enlace = "sampleBinding"&gt;<br /><br /> &lt;modo de seguridad = "Mensaje"&gt;<br /><br /> &lt;message issuedKeyType="AsymmetricKey"&gt;<br /><br /> &lt;dirección del emisor = "http://www.contoso.com/samplests" enlace = "wsFederationHttpBinding" bindingConfiguration = "**contosoSTSBinding**" /&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/seguridad&gt;<br /><br /> &lt;/ enlace&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> \</**BindingConfiguration**\><br /><br /> \<**ReferencedBindings** vt="8"\><br /><br /> &lt;bindings&gt;<br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;nombre de enlace = "**contosoSTSBinding**"&gt;<br /><br /> &lt;modo de seguridad = "Mensaje"&gt;<br /><br /> &lt;message negotiateServiceCredential="false"&gt;<br /><br /> &lt;dirección del emisor = "http://northwind.com/samplests" bindingConfiguration = "**northwindBinding**" enlace = "wsHttpBinding"&gt;<br /><br /> &lt;/issuer&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/seguridad&gt;<br /><br /> &lt;/ enlace&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> &lt;wsHttpBinding&gt;<br /><br /> &lt;nombre de enlace = "**northwindBinding**"&gt;<br /><br /> &lt;modo de seguridad = "Mensaje"&gt;<br /><br /> &lt;message clientCredentialType="Certificate" /&gt;<br /><br /> &lt;/seguridad&gt;<br /><br /> &lt;/ enlace&gt;<br /><br /> &lt;/wsHttpBinding&gt;<br /><br /> &lt;/bindings&gt;<br /><br /> \</**ReferencedBindings** \> **Nota:** el **ReferencedBinding** no debe contener la configuración de enlace utilizada en el **BindingConfiguration**  propiedad.|Especificar las configuraciones de enlace al que hace referencia el **bindingConfiguration** atributo de la **\<emisor\>** (elemento) para el  **wsFederationHttpBinding** y **customBinding**, lo que indica el Token de seguridad servicio (STS) que emite tokens de seguridad. Para obtener más información sobre la **\<emisor\>** elemento, vea el tema "\<emisor\>" en [ http://go.microsoft.com/fwlink/?LinkId=83476 ](http://go.microsoft.com/fwlink/?LinkId=83476).<br /><br /> La información de enlace, como la **\<emisor\>** (elemento) para la **wsFederationHttpBinding** y **customBinding** puede ser configurar a través de la **BindingConfiguration** propiedad de WCF-Custom y los adaptadores de WCF-CustomIsolated. Todas las configuraciones de enlace que se hace referencia para esta propiedad se deben colocar en el formulario de la [ \<enlaces\> ](http://go.microsoft.com/fwlink/?LinkID=80878) elemento. **Nota:** no se puede configurar esta propiedad en el **enlace** ficha en el cuadro de diálogo de propiedades de transporte. Puede importar y exportar esta propiedad mediante la **importación/exportación** ficha en el cuadro de diálogo de propiedades de transporte de los adaptadores de WCF-Custom y WCF-CustomIsolated. **Nota:** el **bindingConfiguration** atributo de la **\<emisor\>** el elemento debe hacer referencia a un nombre de enlace válido en esta propiedad. **Nota:** el **\<emisor\>** elemento en las configuraciones de enlace que se hace referencia puede hacer referencia a una configuración de enlace diferentes en t su propiedad si esta cadena de referencia no hace que un círculo dependencia. <br /><br /> El valor predeterminado es una cadena vacía.|  
  
## <a name="configure-a-wcf-custom-send-port-with-the-biztalk-administration-console"></a>Configurar un puerto de envío WCF-Custom con la consola de administración de BizTalk
  
 Se pueden establecer variables del adaptador de puerto de envío WCF-Custom en la consola de administración de BizTalk. Si no se establecen las propiedades del puerto de envío, se usan los valores predeterminados de la configuración del puerto de envío WCF-Custom, como se indica en la tabla anterior.  
  
## <a name="configure-variables-for-a-wcf-custom-send-port"></a>Configurar variables para un puerto de envío WCF-Custom  
  
1.  Si planea usar los puntos de extensibilidad WCF, tales como los elementos de enlace personalizados, el elemento de comportamiento personalizado y los componentes de canal personalizados, al configurar el adaptador de WCF-Custom, debe agregar los ensamblados que implementan los puntos de extensibilidad y todos los ensamblados dependientes en la caché de ensamblados global tanto en el equipo de procesamiento de BizTalk (equipo en tiempo de ejecución), como en el equipo de administración. Además, debe registrar los componentes de extensión en el archivo machine.config. Para obtener más información acerca de cómo utilizar los puntos de extensibilidad WCF con el adaptador personalizado de WCF, vea [cómo habilitar los puntos de extensibilidad de WCF con los adaptadores de WCF](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md).  
  
2.  En la consola de administración de BizTalk, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones del puerto de envío y especifique **WCF-Custom** para el **tipo** opción en el **transporte** sección de la **General** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
3.  En el **General** ficha la **transporte** sección, haga clic en el **configurar** situado junto a **tipo**.  
  
4.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo la **General** pestaña, configure la dirección del extremo, la identidad del servicio y la **SOAPAction** encabezado para el Puerto de envío WCF-Custom. Para obtener más información sobre la **General** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea el **cuadro de diálogo de propiedades de transporte de WCF-Custom, envío, General** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
5.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, en la **enlace** pestaña, configure distintos tipos de enlaces predefinidos o personalizados de WCF. Para obtener más información sobre la **enlace** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea el **enlace de cuadro de diálogo de propiedades de transporte WCF-Custom, envío,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
6.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, en la **comportamiento** pestaña, configure el comportamiento del extremo para este puerto de envío. Un comportamiento del extremo es un conjunto de los elementos de extensión de comportamiento que modifican o amplían la funcionalidad de servicio o cliente. Para obtener más información sobre la **comportamiento** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea la **comportamiento del cuadro de diálogo de propiedades de transporte WCF-Custom, envío,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
7.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, en la **credenciales** ficha, especifique las credenciales que se utilizará al enviar mensajes. Para obtener más información sobre la **credenciales** pestaña en el **propiedades de transporte de WCF-Custom** vea de cuadro de diálogo el **delcuadrodediálogodepropiedadesdetransporteWCF-Custom,envío,credenciales**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
8.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, en la **mensajes** ficha, especifique la selección de datos de SOAP **cuerpo** elemento. Para obtener más información sobre la **mensajes** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea el **mensajes del cuadro de diálogo de propiedades de transporte WCF-Custom, envío,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
9. En el **propiedades de transporte de WCF-Custom** cuadro de diálogo la **importación/exportación** ficha, importar y exportar la **dirección (URI)** y **deidentidaddeextremo** propiedades en el **General** ficha, información de enlace de la **enlace** pestaña y el comportamiento de punto de conexión en el **comportamiento** ficha para este puerto de envío. Para obtener más información sobre la **importación/exportación** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea la **cuadro de diálogo de propiedades de transporte WCF-Custom, envío, importación y exportación** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
## <a name="configure-a-wcf-custom-send-port-programmatically"></a>Configurar un puerto de envío WCF-Custom mediante programación  
  
 Puede usar el siguiente formato para establecer las propiedades:  
  
```  
<CustomProps>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <InboundBodyPathExpression vt="8" />  
  <EndpointBehaviorConfiguration vt="8"><behavior name="sampleBehavior"><callbackTimeouts /></behavior></EndpointBehaviorConfiguration>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <BindingConfiguration vt="8"><binding name="NetNamedPipeOrderProcessService.OrderProcessServieEndpoint"><readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" /><security mode="None" /></binding></BindingConfiguration>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <UseSSO vt="11">0</UseSSO>  
  <AffiliateApplicationName vt="8" />  
  <BindingType vt="8">netNamedPipeBinding</BindingType>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <UserName vt="8" />  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
</CustomProps>  
  
```  
  
 El siguiente fragmento de código muestra la creación de un puerto de envío WCF-Custom:  
  
```  
// Use BizTalk Explorer object model to create new WCF-Custom send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 <StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
                                 <EndpointBehaviorConfiguration vt=""8""><behavior name=""sampleBehavior""><callbackTimeouts /></behavior></EndpointBehaviorConfiguration>  
                                 <BindingType vt=""8"">netNamedPipeBinding</BindingType>  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-Custom"];  
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
 [Configurar el adaptador de WCF-Custom](../core/configuring-the-wcf-custom-adapter.md)   
 [Configuración de puertos de envío dinámicos mediante propiedades de contexto de adaptadores de WCF](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)   
 [\<Enlaces\>](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<comportamiento\> de \<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879)