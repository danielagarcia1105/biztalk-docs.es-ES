---
title: Cómo configurar un WCF-Custom ubicación de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2092cd4-6612-4ac3-81f3-dd25438837ae
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9c46434f22fe94ce046b7e7caf855d7f7a3eed4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-configure-a-wcf-custom-receive-location"></a>Cómo configurar una ubicación de recepción WCF-Custom
Puede configurar una ubicación de recepción WCF-Custom mediante programación o con la consola de administración de BizTalk.  
  
## <a name="configuration-properties"></a>Propiedades de configuración
  
 El modelo de objetos del Explorador de BizTalk permite crear y configurar ubicaciones de recepción mediante programación. El modelo de objetos del explorador de BizTalk expone la**IReceiveLocation** recibir interfaz de configuración de ubicación que tenga un **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta una bolsa de propiedades de configuración de ubicación de recepción WCF-Custom con formato de un par de nombre y valor de cadenas XML. Para establecer esta propiedad en el modelo de objetos del explorador de BizTalk, debe establecer el **InboundTransportLocation** propiedad de la **IReceiveLocation** interfaz.  
  
 El **TransportTypeData** propiedad de la **IReceiveLocation** interfaz no tiene que establecerse. Si no se establece, el adaptador de WCF-Custom usa los valores predeterminados para la configuración de la ubicación de recepción WCF-Custom, como se indica en la siguiente tabla.  
  
 La siguiente tabla enumera las propiedades de configuración que se pueden establecer en el modelo de objetos del Explorador de BizTalk para la ubicación de recepción WCF-Custom.  
  
|Nombre de la propiedad|Tipo|Description|  
|-------------------|----------|-----------------|  
|**Identidad**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;Identidad&gt;<br /><br /> &lt;valor de userPrincipalName = "username@contoso.com" /&gt;<br /><br /> &lt;/Identity&gt;|Especificar la identidad de servicio que proporciona esta ubicación de recepción. Los valores que se pueden especificar para el **identidad** propiedad difieren según la configuración de seguridad. Esta configuración hace posible que el cliente autentique la ubicación de recepción. En el proceso de negociación entre el cliente y el servicio, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad del servicio esperado coincide con los valores de este elemento.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**BindingType**|Enum<br /><br /> -   **basicHttpBinding**<br />-   **customBinding**<br />-   **mexHttpBinding**<br />-   **mexHttpsBinding**<br />-   **mexNamedPipeBinding**<br />-   **mexTcpBinding**<br />-   **netMsmqBinding**<br />-   **netNamedPipeBinding**<br />-   **netPeerTcpBinding**<br />-   **netTcpBinding**<br />-   **wsDualHttpBinding**<br />-   **wsFederationHttpBinding**<br />-   **wsHttpBinding**|Especificar el tipo de enlace que se va a usar para el extremo que utiliza esta ubicación de recepción. **Nota:** si utiliza un enlace personalizado, el **BindingType** propiedad puede configurarse con los enlaces personalizados. Para obtener más información sobre cómo usar el enlace personalizado, vea [cómo habilitar los puntos de extensibilidad de WCF con los adaptadores de WCF](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md). <br /><br /> El valor predeterminado es una cadena vacía.|  
|**BindingConfiguration**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;nombre de enlace = "netNamedPipeBinding"&gt;&lt;SECURITYMODE = "None" /&gt; &lt; /enlace&gt;|Especificar una cadena XML con el **\<enlace\>** elemento que se va a configurar los distintos tipos de enlaces predefinidos proporcionados por Windows Communication Foundation (WCF). Para obtener más información sobre el enlace proporcionado por el sistema y el enlace personalizado, vea los temas correspondientes en la sección Vea también. **Nota:** BizTalk Server no admite todos los tipos de los elementos de extensión de enlace que se pueden configurar con el **BindingConfiguration** propiedad. <br /><br /> El valor predeterminado es una cadena vacía.|  
|**ServiceBehaviorConfiguration**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;behavior name="SampleServiceBehavior"&gt;&lt;serviceMetadata httpGetEnabled="true" httpGetUrl="http://mycomputer:9995/SampleMex" /&gt;&lt;serviceCredentials /&gt;&lt;/behavior&gt;|Especificar una cadena XML con el **\<comportamiento\>** elemento de la **\<serviceBehaviors\>** elemento que se va a configurar las opciones de comportamiento de WCF servicio. Para obtener más información sobre la **\<serviceBehaviors\>** elemento, vea el tema correspondiente en la sección Vea también.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**EndpointBehaviorConfiguration**|Blob XML<br /><br /> Ejemplo:<br /><br /> &lt;nombre = "sampleBehavior"&gt;&lt;callbackTimeouts /&gt;&lt;/behavior&gt;|Especificar una cadena XML con el **\<comportamiento\>** elemento de la **\<endpointBehaviors\>** elemento que se va a configurar las opciones de comportamiento de un Punto de conexión WCF. Para obtener más información sobre la **\<endpointBehaviors\>** elemento, vea el tema correspondiente en la sección Vea también. **Nota:** BizTalk Server no admite todos los tipos de los elementos de extensión de comportamiento que se pueden configurar con el **EndpointBehaviorConfiguration** propiedad. <br /><br /> El valor predeterminado es una cadena vacía.|  
|**CredentialType**|Enum<br /><br /> -   **Ninguno**: usar ninguna credencial cuando la ubicación de recepción envíe mensajes de petición para sondear un servicio externo o la ubicación de recepción no necesita sondear ningún servicio externo.<br />-   **IssueTicket**: uso empresarial único Sign-On (SSO) para recuperar credenciales de cliente y emitir un vale de SSO. Esta opción requiere el uso del modo de seguridad que permite que la ubicación de recepción suplante la cuenta de usuario para emitir un vale de SSO.<br />-   **UserAccount**: usar las credenciales especificadas en el **nombre de usuario** y **contraseña** propiedades de ubicación de recepción envíe mensajes de petición para sondear un servicio externo.<br />-   **Error de GetCredentials**: usar la aplicación afiliada SSO especificada en el **AffiliateApplicationName** propiedad cuando la ubicación de recepción envía mensajes de petición para sondear un servicio externo.|Especificar el tipo de credenciales de la ubicación de recepción que se van a usar al sondear un servicio externo<br /><br /> Valor predeterminado: **ninguno**|  
|**UserName**|String|Especificar el nombre de usuario que se va a usar con esta ubicación de recepción al sondear un servicio externo con el fin de recuperar los mensajes de respuesta. Esta propiedad es necesaria cuando la **CredentialType** propiedad está establecida en **UserAccount**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**Contraseña**|String|Especificar la contraseña que se va a usar con esta ubicación de recepción al sondear un servicio externo con el fin de recuperar los mensajes de respuesta. Esta propiedad es necesaria cuando la **CredentialType** propiedad está establecida en **UserAccount**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**AffiliateApplicationName**|String|Especificar la aplicación afiliada de SSO que se va a usar para devolver credenciales externas cuando la ubicación de recepción envíe mensajes de petición para sondear un servicio externo. La aplicación afiliada de SSO especificada debe tener una asignación entre la cuenta de Windows con la que se ejecuta la ubicación de recepción y la cuenta del servicio externo. Esta propiedad es necesaria cuando la **CredentialType** propiedad está establecida en **GetCredentials**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**OrderedProcessing**|Boolean|Especificar si se va a conservar el orden de los mensajes al procesarlos (para su uso con el enlace NetMsmq).<br /><br /> Valor predeterminado: **False**|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar el contenido del mensaje SOAP **cuerpo** elemento de un mensaje entrante para crear la parte del cuerpo de mensaje de BizTalk. Si el elemento **Body** tiene varios elementos secundarios, sólo el primero de ellos será la parte del cuerpo del mensaje de BizTalk.<br />-   **UseEnvelope** -crear la parte del cuerpo de mensaje de BizTalk desde el mensaje de SOAP completo **sobres** de un mensaje entrante.<br />-   **UseBodyPath** -usar la expresión de ruta de cuerpo en el **InboundBodyPathExpression** propiedad que se va a crear la parte del cuerpo de mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del elemento **Cuerpo** de SOAP de un mensaje entrante. Esta propiedad sólo es válida para puertos de petición-respuesta.<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF entrantes.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**InboundBodyPathExpression**|String<br /><br /> Para obtener más información sobre cómo usar el **InboundBodyPathExpression** propiedad, vea [propiedades y esquema de propiedades de adaptadores de WCF](../core/wcf-adapters-property-schema-and-properties.md).|Especificar la expresión de ruta de cuerpo para identificar una parte específica de un mensaje entrante utilizada para crear la parte del cuerpo del mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del mensaje SOAP **cuerpo** nodo de un mensaje entrante. Si esta expresión de ruta de cuerpo devuelve varios nodos, solo se elegirá el primero de ellos para la parte del cuerpo del mensaje de BizTalk. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -codificación Base64.<br />-   **Hex** : Hexadecimal codificación.<br />-   **Cadena** : codificación de texto - UTF-8.<br />-   **XML** -los adaptadores WCF crean el cuerpo del mensaje de BizTalk con el XML externo del nodo seleccionado por la expresión de ruta de acceso de cuerpo en **InboundBodyPathExpression**.|Especifique el tipo de codificación que WCF-Custom adaptador de recepción utiliza para descodificar el nodo identificado por la expresión de ruta de acceso de cuerpo especificada en **InboundBodyPathExpression**. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**.<br /><br /> Valor predeterminado: **XML**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -usar la parte del cuerpo de mensaje de BizTalk para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje de respuesta saliente.<br />-   **UseTemplate** -usar la plantilla proporcionada en el **OutboundXMLTemplate** propiedad que se va a crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje de respuesta saliente.<br /><br /> Para obtener más información sobre cómo usar el **OutboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF salientes. Esta propiedad sólo es válida para las ubicaciones de recepción de solicitud-respuesta.<br /><br /> Valor predeterminado: **UseBodyElement**|  
|**OutboundXMLTemplate**|String<br /><br /> Para obtener más información sobre cómo usar el **OutboundXMLTemplate** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).|Especifique la plantilla con formato XML para el contenido del mensaje SOAP **cuerpo** elemento de un mensaje de respuesta saliente. Esta propiedad es necesaria si la **OutboundBodyLocation** propiedad está establecida en **UseTemplate**. Esta propiedad sólo es válida para las ubicaciones de recepción de solicitud-respuesta.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**DisableLocationOnFailure**|Boolean|Especificar si se va a deshabilitar la ubicación de recepción cuyo procesamiento de entrada no se puede realizar correctamente debido a un error de canalización de recepción o de enrutamiento.<br /><br /> Valor predeterminado: **False**|  
|**SuspendMessageOnFailure**|Boolean|Especificar si se va a suspender el mensaje de solicitud cuyo procesamiento de entrada no se puede realizar correctamente debido a un error de canalización de recepción o de enrutamiento.<br /><br /> Valor predeterminado: **True**|  
|**IncludeExceptionDetailInFaults**|Boolean|Especificar si se va a incluir información de excepción administrada en el detalle de los errores SOAP devueltos al cliente para fines de depuración.<br /><br /> Valor predeterminado: **False**|  
|**ReferencedBindings**|Blob XML<br /><br /> Ejemplo:<br /><br /> \<**BindingConfiguration** vt="8"\><br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;nombre de enlace = "sampleBinding"&gt;<br /><br /> &lt;modo de seguridad = "Mensaje"&gt;<br /><br /> &lt;message issuedKeyType="AsymmetricKey"&gt;<br /><br /> &lt;dirección del emisor = "http://www.contoso.com/samplests" enlace = "wsFederationHttpBinding" bindingConfiguration = "**contosoSTSBinding**" /&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/seguridad&gt;<br /><br /> &lt;/ enlace&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> \</**BindingConfiguration**\><br /><br /> \<**ReferencedBindings** vt="8"\><br /><br /> &lt;bindings&gt;<br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;nombre de enlace = "**contosoSTSBinding**"&gt;<br /><br /> &lt;modo de seguridad = "Mensaje"&gt;<br /><br /> &lt;message negotiateServiceCredential="false"&gt;<br /><br /> &lt;dirección del emisor = "http://northwind.com/samplests" bindingConfiguration = "**northwindBinding**" enlace = "wsHttpBinding"&gt;<br /><br /> &lt;/issuer&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/seguridad&gt;<br /><br /> &lt;/ enlace&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> &lt;wsHttpBinding&gt;<br /><br /> &lt;nombre de enlace = "**northwindBinding**"&gt;<br /><br /> &lt;modo de seguridad = "Mensaje"&gt;<br /><br /> &lt;message clientCredentialType="Certificate" /&gt;<br /><br /> &lt;/seguridad&gt;<br /><br /> &lt;/ enlace&gt;<br /><br /> &lt;/wsHttpBinding&gt;<br /><br /> &lt;/bindings&gt;<br /><br /> \</**ReferencedBindings** \> **Nota:** el **ReferencedBinding** no debe contener la configuración de enlace utilizada en el **BindingConfiguration**  propiedad.|Especificar las configuraciones de enlace al que hace referencia el **bindingConfiguration** atributo de la **\<emisor\>** (elemento) para el  **wsFederationHttpBinding** y **customBinding**, lo que indica el Token de seguridad servicio (STS) que emite tokens de seguridad. Para obtener más información sobre la **\<emisor\>** elemento, vea el tema "\<emisor\>" en [ http://go.microsoft.com/fwlink/?LinkId=83476 ](http://go.microsoft.com/fwlink/?LinkId=83476).<br /><br /> La información de enlace, como la **\<emisor\>** (elemento) para la **wsFederationHttpBinding** y **customBinding** puede ser configurar a través de la **BindingConfiguration** propiedad de WCF-Custom y los adaptadores de WCF-CustomIsolated. Todas las configuraciones de enlace que se hace referencia para esta propiedad se deben colocar en el formulario de la [ \<enlaces\> ](http://go.microsoft.com/fwlink/?LinkID=80878) elemento. **Nota:** no se puede configurar esta propiedad en el **enlace** ficha en el cuadro de diálogo de propiedades de transporte. Puede importar y exportar esta propiedad mediante la **importación/exportación** ficha en el cuadro de diálogo de propiedades de transporte de los adaptadores de WCF-Custom y WCF-CustomIsolated. **Nota:** el **bindingConfiguration** atributo de la **\<emisor\>** el elemento debe hacer referencia a un nombre de enlace válido en esta propiedad. **Nota:** el **\<emisor\>** elemento en las configuraciones de enlace que se hace referencia puede hacer referencia a una configuración de enlace diferentes en t su propiedad si esta cadena de referencia no hace que un círculo dependencia. <br /><br /> El valor predeterminado es una cadena vacía.|  
  
## <a name="configure-a-wcf-custom-receive-location-with-the-biztalk-administration-console"></a>Configurar un WCF-Custom ubicación de recepción con la consola de administración de BizTalk
  
 Se pueden establecer variables de adaptador de ubicación de recepción WCF-Custom en la consola de administración de BizTalk. Si no se definen propiedades en la ubicación de recepción, se utilizarán los valores predeterminados del controlador de recepción establecidos en la consola de administración de BizTalk.  
  
> [!NOTE]
>  Antes de completar este procedimiento, debe haber agregado un puerto de recepción. Para obtener más información, consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
## <a name="configure-variables-for-a-wcf-custom-receive-location"></a>Configurar variables para la ubicación de recepción de un WCF-Custom  
  
1.  Si planea usar los puntos de extensibilidad WCF, tales como los elementos de enlace personalizados, el elemento de comportamiento personalizado y los componentes de canal personalizados, al configurar el adaptador de WCF-Custom, debe agregar los ensamblados que implementan los puntos de extensibilidad y todos los ensamblados dependientes en la caché de ensamblados global tanto en el equipo de procesamiento de BizTalk (equipo en tiempo de ejecución), como en el equipo de administración. Además, debe registrar los componentes de extensión en el archivo machine.config. Para obtener más información acerca de cómo utilizar los puntos de extensibilidad WCF con el adaptador personalizado de WCF, vea [cómo habilitar los puntos de extensibilidad de WCF con los adaptadores de WCF](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md).  
  
2.  En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación en el que desea crear una ubicación de recepción.  
  
3.  En la consola de administración de BizTalk, en el panel izquierdo, haga clic en el nodo **Puerto de recepción** . A continuación, en el panel de la derecha, haga clic con el botón secundario en el puerto de recepción asociado con una ubicación de recepción existente o que desee asociar con una nueva ubicación de recepción. A continuación, haga clic en **Propiedades**.  
  
4.  En el **propiedades de puerto de recepción** cuadro de diálogo, en el panel izquierdo, seleccione **ubicaciones de recepción**y, a continuación, en el panel derecho, haga doble clic en otra ubicación de recepción o haga clic en **New**para crear una nueva ubicación de recepción.  
  
5.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en el **transporte** junto a la sección **tipo**, seleccione **WCF-Custom** en la lista desplegable lista y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, en la **General** pestaña, configure la dirección del extremo y ubicación de recepción de la identidad del servicio de WCF-Custom. Para obtener más información sobre la **General** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea la **cuadro diálogo de propiedades de transporte WCF-Custom, recepción, General**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
7.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, en la **enlace** pestaña, configure distintos tipos de enlaces predefinidos o personalizados de WCF. Para obtener más información sobre la **enlace** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea el **enlace de cuadro de diálogo de propiedades de transporte WCF-Custom, recepción,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
8.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, en la **comportamiento** pestaña, configure el punto de conexión y comportamientos de servicio para esta ubicación de recepción. Un comportamiento de extremo consiste en un conjunto de elementos de extensión de comportamiento que modifican o amplían el servicio o la funcionalidad del cliente. Para obtener más información sobre la **comportamiento** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea la **comportamiento del cuadro de diálogo de propiedades de transporte WCF-Custom, recepción,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
9. En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, en la **otros** pestaña, configure las credenciales para esta ubicación de recepción para usar al sondear un servicio externo, y si esta ubicación de recepción conserva el mensaje orden al procesar mensajes. Para obtener más información sobre la **otros** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea el **cuadro de diálogo de propiedades de transporte de WCF-Custom, recepción, otros** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
10. En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, en la **mensajes** ficha, especifique la selección de datos de SOAP **cuerpo** elemento. Para obtener más información sobre la **mensajes** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea el **mensajes del cuadro de diálogo de propiedades de transporte WCF-Custom, recepción,**ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
11. En el **propiedades de transporte de WCF-Custom** cuadro de diálogo la **importación/exportación** ficha, importar y exportar la **dirección (URI)** y **deidentidaddeextremo** propiedades en el **General** ficha, información de enlace de la **enlace** pestaña y el comportamiento de punto de conexión en el **comportamiento** ficha para esta recepción ubicación. Para obtener más información sobre la **importación/exportación** pestaña en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, vea la **cuadro de diálogo de propiedades de transporte WCF-Custom, recepción, importación y exportación**  ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  

## <a name="configure-a-wcf-custom-receive-location-programmatically"></a>Configurar una ubicación de recepción de WCF-Custom mediante programación
  
 Puede usar el siguiente formato para establecer las propiedades:  
  
```  
<CustomProps>  
  <InboundBodyPathExpression vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <BindingConfiguration vt="8"><binding name="netNamedPipeBinding"><security mode="None" /></binding></BindingConfiguration>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <CredentialType vt="8">GetCredentials</CredentialType>  
  <Identity vt="8" />  
  <ServiceBehaviorConfiguration vt="8"><behavior name="SampleServiceBehavior"><serviceMetadata httpGetEnabled="true" httpGetUrl="http://mycomputer:9995/SampleService/Mex" /><serviceCredentials /></behavior></ServiceBehaviorConfiguration>  
  <Password vt="1" />  
  <OrderedProcessing vt="11">-1</OrderedProcessing>  
  <IncludeExceptionDetailInFaults vt="11">0</IncludeExceptionDetailInFaults>  
  <AffiliateApplicationName vt="8">SampleAffiliateApplication</AffiliateApplicationName>  
  <DisableLocationOnFailure vt="11">0</DisableLocationOnFailure>  
  <SuspendMessageOnFailure vt="11">0</SuspendMessageOnFailure>  
  <BindingType vt="8">netNamedPipeBinding</BindingType>  
  <UserName vt="8">Hello</UserName>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <EndpointBehaviorConfiguration vt="8"><behavior name="EndpointBehavior" /></EndpointBehaviorConfiguration>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 El siguiente fragmento de código muestra la creación de una ubicación de recepción WCF-Custom:  
  
```  
// Use BizTalk Explorer object model to create new WCF-Custom receive location   
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
  <BindingConfiguration vt=""8""><binding name=""netNamedPipeBinding""><security mode=""None"" /></binding></BindingConfiguration>  
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
  
// Add a new one-way receive port  
IReceivePort receivePort = application.AddNewReceivePort(false);  
receivePort.Name = "SampleReceivePort";  
// Add a new one-way receive location  
IReceiveLocation recieveLocation = receivePort.AddNewReceiveLocation();  
recieveLocation.Name = "SampleReceiveLocation";  
// Find a receive handler for WCF-Custom   
int i = 0;  
for(i=0; i < explorer.ReceiveHandlers.Count; ++i)   
{  
    if("WCF-Custom" == explorer.ReceiveHandlers[i].TransportType.Name)  
        break;  
}  
recieveLocation.ReceiveHandler = explorer.ReceiveHandlers[i];  
recieveLocation.Address = "net.pipe://mycomputer/samplePipeName";  
recieveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
recieveLocation.TransportType = explorer.ProtocolTypes["WCF-Custom"];  
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
 [Configurar el adaptador de WCF-Custom](../core/configuring-the-wcf-custom-adapter.md)   
 [Cómo crear una aplicación afiliada](../core/how-to-create-an-affiliate-application.md)   
 [\<comportamiento\> de \<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879)   
 [\<Enlaces\>](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<comportamiento\> de \<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095)