---
title: Esquema de propiedades de adaptadores WCF y propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 02/09/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2093745e-86c0-4276-a7cc-a0187391ca4a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04bb48f54347eabeb886d91fa245bae18c34de55
ms.sourcegitcommit: 50798e04fdcaf5dce5288aa18608e2a981b162fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2018
ms.locfileid: "29139300"
---
# <a name="wcf-adapters-property-schema-and-properties"></a>Propiedades y esquema de propiedades de adaptadores de WCF
Obtenga información acerca de las propiedades promocionadas en el esquema de propiedades del adaptador WCF. Los adaptadores de WCF asignan valores a las propiedades que puede utilizar en su aplicación. El adaptador de WCF también proporciona un mecanismo para leer pero no promociona las propiedades personalizadas en el contexto de mensaje de BizTalk y un mecanismo para promocionar las propiedades personalizadas en el contexto de mensaje de BizTalk. Para obtener más información, consulte [encabezados SOAP con servicios de WCF publican](../core/soap-headers-with-published-wcf-services.md).  

## <a name="promoted-properties"></a>Propiedades promocionadas  
**Namespace:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties  

#### <a name="action"></a>Acción
Especifique el **SOAPAction** campo de encabezado para los mensajes salientes. Puede especificar este valor de dos maneras diferentes: el formato de acción única y el formato de asignación de acciones. Si establece esta propiedad en el formato de acción única: por ejemplo, http://contoso.com/Svc/Op1: el **SOAPAction** encabezado mensajes salientes siempre se establece en el valor especificado en esta propiedad.

Si establece esta propiedad en el formato de asignación de acción, la salida **SOAPAction** encabezado viene determinado por la **BTS. Operación** propiedad de contexto. Por ejemplo, si esta propiedad se establece en el siguiente formato XML y **BTS. Operación** propiedad está establecida en Op1, el adaptador de envío WCF usa `http://contoso.com/Svc/Op1` para los salientes **SOAPAction** encabezado.

```
<BtsActionMapping>
<Operation Name="Op1" Action="http://contoso.com/Svc/Op1">
<Operation Name="Op2" Action="http://contoso.com/Svc/Op2">
</BtsActionMapping>
```

Si los mensajes salientes proceden de un puerto de orquestación, las instancias de orquestación establecen dinámicamente la **BTS. Operación** propiedad con el nombre de la operación del puerto. Si los mensajes salientes se enrutan con enrutamiento por contenidos, puede establecer el **BTS. Operación** propiedad en componentes de canalización.
Esta propiedad se promociona automáticamente a partir de los mensajes entrantes con el formato de acción única.

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: WCF todos los adaptadores de envío

#### <a name="affiliateapplicationname"></a>AffiliateApplicationName
Especificar la aplicación afiliada que se utilizará para el inicio de sesión único empresarial (SSO). Esta propiedad es necesaria si la **UseSSO** propiedad está establecida en **True**. 

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: WCF todos los adaptadores de envío *excepto* el adaptador WCF-NetNamedPipe

#### <a name="algorithmsuite"></a>AlgorithmSuite
Especificar el cifrado de mensajes y los algoritmos de encapsulado de claves. Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).

Para obtener más información acerca de los valores aplicables para la **AlgorithmSuite** propiedad, vea la **algorithmsuite** propiedad en la **cuadro de diálogo de propiedades de transporte de WCF-NetTcp, envío, Seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

Tipo: cadena  
Valor predeterminado: **Basic256**  
Se aplica a: 

- Adaptador de WCF-BasicHttp
- Adaptador de WCF-NetMsmq
- Adaptador de WCF-NetTcp
- Adaptador de WCF-WSHttp

#### <a name="bindingconfiguration"></a>BindingConfiguration
Especificar una cadena XML con el **\<enlace\>** elemento que se va a configurar los distintos tipos de enlaces predefinidos proporcionados por Windows Communication Foundation (WCF). Para obtener más información sobre el enlace proporcionado por el sistema y el enlace personalizado, vea los temas correspondientes en la sección Vea también.

Ejemplo:

```
<binding name="wsHttpBinding" transactionFlow="true">
<security><message clientCredentialType="UserName"></security>
</binding>
```

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: adaptador de WCF-Custom, adaptador de WCF-CustomIsolated

#### <a name="bindingtype"></a>BindingType
Especifique qué tipo de enlace utilizar para el extremo. Para obtener más información acerca de los valores aplicables para el **BindingType** propiedad, vea la **BindingType** propiedad en la **cuadro de diálogo de propiedades de transporte WCF-Custom, envío, enlace** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: adaptador de WCF-Custom, adaptador de WCF-CustomIsolated

#### <a name="clientcertificate"></a>ClientCertificate
Especificar la huella digital del certificado X.509 para la autenticación de este puerto de envío en servicios. Esta propiedad es necesaria si la **ClientCredentialsType** propiedad está establecida en **certificado**. El certificado que se usará para esta propiedad debe estar instalado en el **mi** almacenar en la **usuario actual** ubicación.

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: 

- Adaptador de envío WCF-BasicHttp
- Adaptador de envío WCF-WSHttp
- Adaptador de envío WCF-NetTcp
- Adaptador de envío WCF-NetMsmq

#### <a name="closetimeout"></a>CloseTimeout
Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de cierre del canal.

Tipo: cadena  
Valor predeterminado: 00:01:00  
Se aplica a: todos los adaptadores WCF *excepto* WCF-Custom y WCF-CustomIsolated

#### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue
Especifique el URI completo con el **net.msmq** esquema para la ubicación de la cola de mensajes no enviados por aplicación, donde se colocan los mensajes que han expirado o cuya transferencia o entrega ha fallado. Por ejemplo, net.msmq://localhost/deadLetterQueueName. La cola de mensajes con problemas de entrega es una cola en el administrador de cola de la aplicación de envío para mensajes caducados que no se han podido entregar. Esta propiedad es necesaria si la **DeadLetterQueue** propiedad está establecida en **personalizado**.

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: adaptador de envío WCF-NetMsmq

#### <a name="deadletterqueue"></a>DeadLetterQueue
Especificar la cola de mensajes con problemas de entrega a la que se transferirán los mensajes que no se han podido entregar a la aplicación. Para obtener más información sobre los mensajes entregados a la cola de mensajes no enviados, consulte el **enlace de cuadro de diálogo de propiedades de transporte WCF-NetMsmq, envío,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

Tipo: cadena  
Valor predeterminado: **sistema**  
Se aplica a: adaptador de envío WCF-NetMsmq

#### <a name="disablelocationonfailure"></a>DisableLocationOnFailure
Especificar si se va a deshabilitar la ubicación de recepción cuyo procesamiento de entrada no se puede realizar correctamente debido a un error de canalización de recepción o de enrutamiento. Puede que desee establecer esta propiedad en **True** cuando recibe se pueden deshabilitar ubicaciones y denegación de servicio (DoS) no constituye un problema.

Por ejemplo:  
- Adaptador de WCF-Custom: cuando el **BindingType** propiedad está establecida en **netMsmqBinding**.
- Adaptador de WCF-Custom: cuando el **BindingType** propiedad está establecida en **customBinding**y el **BindingConfiguration** está configurado para usar canales personalizados que se basan en los transportes en cola como MSMQ.
- Adaptador de WCF-CustomIsolated: cuando el **BindingType** propiedad está establecida en **customBinding**y el **BindingConfiguration** está configurado para usar canales personalizados que se basan en transportes en cola como MSMQ
- Adaptador de WCF-NetMsmq

Tipo: booleano  
Valor predeterminado: **False**  
Se aplica a:  
- Adaptador de recepción de WCF-NetMsmq
- Adaptador de recepción de WCF-Custom
- Adaptador de recepción WCF-CustomIsolated

#### <a name="enabletransaction"></a>EnableTransaction
El efecto de esta propiedad varía dependiendo del adaptador de WCF. Para obtener más información acerca de esta propiedad, vea los temas "Cómo..." para cada adaptador WCF en [adaptadores de WCF](../core/wcf-adapters.md).

Tipo: booleano  
Se aplica a: 

- Adaptador de WCF-WSHttp
- Adaptador de WCF-NetTcp
- Adaptador de WCF-NetNamedPipe
- Adaptador de WCF-NetMsmq

#### <a name="endpointbehaviorconfiguration"></a>EndpointBehaviorConfiguration
Especificar una cadena XML con el **\<comportamiento\>** elemento de la **\<endpointBehaviors\>** elemento que se va a configurar las opciones de comportamiento de un Punto de conexión WCF. Para obtener más información sobre la **\<endpointBehaviors\>** elemento, vea el tema correspondiente en la sección Vea también.

Ejemplo: 
```
<behavior name="sampleBehavior"><callbackTimeouts/></behavior>
```

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: adaptador de envío WCF-Custom

#### <a name="establishsecuritycontext"></a>EstablishSecurityContext
Especificar si el canal de seguridad establece una sesión segura. Una sesión segura establece un token de contexto de seguridad (SCR) antes de intercambiar los mensajes de la aplicación.

Tipo: booleano  
Valor predeterminado: True  
Aplicar a: adaptador de WCF-WSHttp

#### <a name="fromaddress"></a>FromAddress
Indicar la dirección de extremo de origen a través de la que se envían los mensajes WCF entrantes. La propiedad se promociona automáticamente desde los mensajes entrantes.

Tipo: cadena  
Se aplica a: todos los adaptadores WCF *excepto* adaptador de envío WCF-NetMsmq
  
#### <a name="headers"></a>Encabezados
Especificar las referencias de extremo utilizadas para proporcionar información de dirección adicional más allá del URI. Cuando se utiliza esta propiedad, esta propiedad debe tener la \< **encabezados** \> elemento como el elemento raíz. Todos los encabezados de dirección deben colocarse dentro de la \< **encabezados** \> elemento. Esta propiedad se promociona automáticamente para los mensajes entrantes.

Ejemplo:
```
<headers>
<Region xmlns="Uri">"String"</Region>
<Member xmlns="Uri">"String"</Member> 
</headers>
```

Tipo: cadena  
Se aplica a: todos los adaptadores WCF
  
#### <a name="identity"></a>Identidad
Especificar la identidad del servicio que proporciona una ubicación de recepción o espera un puerto de envío. Los valores que se pueden especificar para el **identidad** propiedad difieren según la configuración de seguridad. Esta configuración permite a los clientes autenticar servicios. En el proceso de negociación entre los clientes y los servicios, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad de los servicios coincide con los valores de los clientes.

Ejemplo:
```
<identity>
<userPrincipalName value="username@contoso.com"/>
</identity>
```

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: todos los adaptadores WCF

#### <a name="inboundbodylocation"></a>InboundBodyLocation
Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF entrantes. Para obtener más información sobre cómo usar el **InboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).

Tipo: cadena  
Valor predeterminado: UseBodyElement  

    Applicable values are:  
        - UseBodyElement: Use the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part. If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.
        - UseEnvelope: Create the BizTalk message body part from the entire SOAP **Envelope** of an incoming message.
        - UseBodyPath: Use the body path expression in the **InboundBodyPathExpression** property to create the BizTalk message body part. The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message. This property is valid only for solicit-response ports.  

Se aplica a: todos los adaptadores WCF *excepto* envío WCF-NetMsmq  

#### <a name="inboundbodypathexpression"></a>InboundBodyPathExpression
Especificar la expresión de ruta de cuerpo para identificar una parte específica de un mensaje entrante utilizada para crear la parte del cuerpo del mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del mensaje SOAP **cuerpo** nodo de un mensaje entrante. Si esta expresión de ruta de cuerpo devuelve varios nodos, solo se elegirá el primero de ellos para la parte del cuerpo del mensaje de BizTalk. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**. Para obtener más información sobre cómo usar el **InboundBodyPathExpression** propiedad, vea [propiedades y esquema de propiedades de adaptadores de WCF](../core/wcf-adapters-property-schema-and-properties.md).

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: todos los adaptadores WCF *excepto* adaptador de envío WCF-NetMsmq

#### <a name="inboundheaders"></a>InboundHeaders
Use la **InboundHeaders** propiedad para tener acceso a los encabezados SOAP de mensajes WCF entrantes. Los adaptadores de WCF copian todos los valores de encabezado SOAP en mensajes entrantes a esta propiedad, que incluyen encabezados SOAP y encabezados SOAP estándares que la infraestructura WCF usa para WS-Addressing, WS-Security y WS-AtomicTransaction. El valor contenido en la propiedad de contexto es una cadena que contiene los datos XML con la \< **encabezados** \> elemento raíz y los encabezados SOAP entrantes se copian como elementos secundarios de la \< **encabezados** \> elemento. Para obtener más información acerca de cómo los encabezados SOAP de acceso con los adaptadores de WCF, vea el ejemplo de SDK Using Custom SOAP Headers with the WCF Adapters de [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).

Tipo: cadena  
Se aplica a: todos los adaptadores WCF *excepto* adaptador de envío WCF-NetMsmq

#### <a name="inboundnodeencoding"></a>InboundNodeEncoding
Especifique el tipo de codificación que WCF adaptador de recepción utiliza para descodificar el nodo identificado por la expresión de ruta de acceso de cuerpo especificada en **InboundBodyPathExpression**. Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**.

Tipo: cadena  
Valor predeterminado: XML  

    Applicable values are:  
        - Base64: Base64 encoding
        - Hex: Hexadecimal encoding
        - String: Text encoding - UTF-8
        - XML: The WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in **InboundBodyPathExpression**.  

Se aplica a: todos los adaptadores WCF *excepto* adaptador de envío WCF-NetMsmq

#### <a name="isfault"></a>IsFault
Indicar si los mensajes de error SOAP se han recibido. La propiedad se promociona automáticamente desde los mensajes entrantes. 

**Nota**  
El **IsFault** propiedad no se puede usar para comprobar los mensajes recibidos para los errores de transporte, como el error HTTP 404 (archivo o directorio no encontrado).

Tipo: booleano  
Se aplica a: todos los adaptadores WCF *excepto* adaptador de envío WCF-NetMsmq

#### <a name="leasetimeout"></a>LeaseTimeout
Especificar la duración máxima de una conexión agrupada activa. Después de transcurrir el tiempo especificado, la conexión se cierra cuando se atiende la solicitud actual.

El adaptador de WCF-NetTcp usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) clase para comunicarse con un punto de conexión. Cuando se usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) en escenarios con equilibrio de carga, considere la posibilidad de reducir el tiempo de espera de concesión predeterminado. Para obtener más información acerca del equilibrio de carga cuando se usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087), vea el tema correspondiente en la sección Vea también.

Tipo: cadena  
Valor predeterminado: 00:05:00  
Se aplica a: adaptador de recepción de WCF-NetTcp  

#### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls
Especificar el número de llamadas concurrentes en una instancia de servicio única. Las llamadas que superan el límite se ponen en cola. Establecer este valor como 0 es equivalente a establecerlo como **Int32.MaxValue**. 

**Nota**  
No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento. 

Tipo: entero  
Valor predeterminado: 200  
Se aplica a: WCF todos los adaptadores de recepción *excepto* los adaptadores de WCF-Custom y WCF-CustomIsolated

#### <a name="maxconnections"></a>MaxConnections
Especificar el número máximo de conexiones que el agente de escucha puede tener esperando la aceptación de la aplicación. Cuando se supera este valor de cuota, se interrumpen las nuevas conexiones entrantes en lugar de esperar la aceptación. 

**Nota**  
Ya que esta es una propiedad de controlador de adaptador, éste no puede configurarse en componentes de canalización y orquestaciones. 

**Nota**  
No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento. 

Tipo: entero  
Valor predeterminado: 10  
Se aplica a: adaptador de WCF-NetNamedPipe, adaptador de WCF-NetTcp  

#### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize
Especificar el tamaño máximo, en bytes, para mensajes (con encabezados incluidos) que se pueden recibir a través de la red. El tamaño de los mensajes se limita mediante la cantidad de memoria asignada a cada mensaje. Puede usar esta propiedad para limitar la exposición a ataques por denegación de servicio (DoS).

Tipo: entero  
Valor predeterminado: 65536  
Se aplica a: 
- Adaptador de WCF-BasicHttp
- Adaptador de WCF-WSHttp
- Adaptador de WCF-NetTcp
- Adaptador de WCF-NetNamedPipe
- Adaptador de recepción de WCF-NetMsmq

#### <a name="messageclientcredentialtype"></a>MessageClientCredentialType
Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación de cliente mediante la seguridad basada en mensajes.

Los valores aplicables son distintos para cada adaptador de WCF. Para obtener más información sobre la **MessageClientCredentialType** propiedad, vea los temas sobre cada adaptador de WCF en [adaptadores de WCF](../core/wcf-adapters.md).

Tipo: cadena  
Se aplica a: 
- Adaptador de WCF-BasicHttp
- Adaptador de WCF-WSHttp
- Adaptador de WCF-NetTcp
- Adaptador de WCF-NetNamedPipe

#### <a name="messageencoding"></a>MessageEncoding
Especificar el codificador que se usa para codificar el mensaje SOAP.

Tipo: cadena  
Valor predeterminado: texto  

    Applicable values: 
        - Text: Use a text message encoder
        - Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder  

Se aplica a: adaptador de WCF-BasicHttp, adaptador de WCF-WSHttp


#### <a name="msmqauthenticationmode"></a>MsmqAuthenticationMode
Especificar cómo el transporte de MSMQ debe autenticar el mensaje.

Tipo: cadena  
Valor predeterminado: **WindowsDomain**  
    Para obtener más información acerca de los valores aplicables para la **MsmqAuthenticationMode** propiedad, vea la **MsmqAuthenticationMode** propiedad en la **propiedades de transporte de WCF-NetMsmq Cuadro de diálogo cuadro, envío, seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
Se aplica a: adaptador de WCF-NetMsmq  

#### <a name="msmqencryptionalgorithm"></a>MsmqEncryptionAlgorithm
Especificar el algoritmo que se usará para el cifrado de mensajes a través de la red al transferir mensajes entre los administradores de cola de mensajes. Esta propiedad está disponible solo si el **MsmqProtectionLevel** propiedad está establecida en **EncryptAndSign**.

Tipo: cadena  
Valor predeterminado: **RC4Stream**  

    Applicable values are: RC4Stream, AES

Se aplica a: adaptador de WCF-NetMsmq  

#### <a name="msmqprotectionlevel"></a>MsmqProtectionLevel
Especificar el modo en que los mensajes están protegidos en el nivel de transporte de MSMQ.

Tipo: cadena  
Valor predeterminado: **inicio de sesión**  

    Applicable values are:
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed. To use this protection level, you must enable **Active Directory Integration** for **MSMQ**  

Se aplica a: adaptador de WCF-NetMsmq  

#### <a name="msmqsecurehashalgorithm"></a>MsmqSecureHashAlgorithm
Especificar el algoritmo hash que se usará para calcular la síntesis del mensaje. Esta propiedad no está disponible si la **MsmqProtectionLevel** propiedad está establecida en **ninguno**.

Tipo: cadena  
Valor predeterminado: **SHA1**  

    Applicable values are: MD5, SHA1, SHA25, SHA512  

Se aplica a: adaptador de WCF-NetMsmq  

#### <a name="negotiateservicecredential"></a>NegotiateServiceCredential
Especificar si la credencial de servicio se suministra en este cliente fuera de banda o se obtiene del servicio en el cliente a través de un proceso de negociación. Dicha negociación es precursora del intercambio de mensajes habitual.

Si el **MessageClientCredentialType** propiedad es igual a **ninguno**, **nombre de usuario**, o **certificado**, establecer esta propiedad como  **False** implica que el certificado de servicio está disponible en el cliente fuera de banda y que el cliente necesita especificar el certificado de servicio. Este modo es interoperable con pilas SOAP que implementan WS-Trust y WS-SecureConversation.

Si el **MessageClientCredentialType** propiedad está establecida en **Windows**, establecer esta propiedad en **False** especifica la autenticación basada en Kerberos. Esto significa que el cliente y el servicio deben formar parte del mismo dominio de Kerberos. Este modo puede interoperar con pilas de SOAP que implementan el perfil de token de Kerberos (como se define en OASIS WSS TC), así como WS-Trust y WS-SecureConversation.

Cuando esta propiedad es **True**, hace que una negociación .NET SOAP que tuneliza el intercambio de SPNego mediante mensajes SOAP.

Tipo: booleano  
Valor predeterminado: True  
Se aplica a: adaptador de WCF-WSHttp  

#### <a name="opentimeout"></a>OpenTimeout
Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de apertura del canal. 

**Nota**  
No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento. 

Tipo: cadena  
Valor predeterminado: 00:01:00  
Se aplica a: todos los adaptadores WCF *excepto* los adaptadores de WCF-Custom y WCF-CustomIsolated

#### <a name="orderedprocessing"></a>OrderedProcessing
Especifica si los mensajes se procesan en serie. Cuando esta propiedad está activada, esta ubicación de recepción permite la entrega de mensajes ordenada cuando se utiliza junto con un puerto de envío de orquestación o mensajería de BizTalk que tiene el **entrega ordenada** opción establecida en `True`. Para obtener más información sobre la **entrega ordenada** opción, vea los temas correspondientes en la sección Vea también.

Esta propiedad es aplicable en los siguientes casos:
- Adaptador de WCF-Custom: cuando el **BindingType** propiedad está establecida en **netMsmqBinding**
- Adaptador de WCF-Custom: cuando el **BindingType** propiedad está establecida en **customBinding**y el **BindingConfiguration** está configurado para usar canales personalizados que se basan en transportes compatibles con la entrega ordenada como MSMQ.
- Adaptador de WCF-CustomIsolated: cuando el **BindingType** propiedad está establecida en **customBinding**y el **BindingConfiguration** está configurado para usar canales personalizados que se basan en transportes compatibles con la entrega ordenada.
- Adaptador de WCF-NetMsmq

Tipo: cadena  
Valor predeterminado: **False**  
Se aplica a: 
- Adaptador de recepción de WCF-NetMsmq
- Adaptador de recepción de WCF-Custom
- Adaptador de recepción WCF-CustomIsolated

#### <a name="outboundbodylocation"></a>OutboundBodyLocation
Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF salientes. Para obtener más información sobre cómo usar el **OutboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).

Tipo: cadena  
Valor predeterminado: UseBodyElement  

    Applicable values are:
        - UseBodyElement: Use the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message
        - **UseTem****plate**: Use the template supplied in the OutboundXMLTemplate property to create the content of the SOAP **Body** element for an outgoing message

Se aplica a: todos los adaptadores WCF *excepto* adaptador de recepción de WCF-NetMsmq

#### <a name="outboundcustomheaders"></a>OutboundCustomHeaders
Especificar encabezados SOAP personalizados para mensajes salientes. Cuando se utiliza esta propiedad, la propiedad debe tener la \< **encabezados** \> elemento como el elemento raíz. Todos los encabezados SOAP personalizados deben colocarse dentro de la \< **encabezados** \> elemento. Si el valor del encabezado SOAP personalizado es una cadena vacía, debe asignar \< **encabezados**\>\</**encabezados** \> o \< **encabezados** \> a esta propiedad. Para obtener más información acerca de cómo usar encabezados SOAP con los adaptadores WCF, vea el ejemplo de SDK Using Custom SOAP Headers with the WCF Adapters de [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).

Tipo: cadena  
Se aplica a: todos los adaptadores WCF *excepto* adaptador de recepción de WCF-NetMsmq

#### <a name="outboundxmltemplate"></a>OutboundXmlTemplate
Especifique la plantilla con formato XML para el contenido del mensaje SOAP **cuerpo** elemento de un mensaje saliente. Esta propiedad es necesaria si la **OutboundBodyLocation** propiedad está establecida en **UseTemplate**. Para obtener más información sobre cómo usar el **OutboundXMLTemplate** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: todos los adaptadores WCF *excepto* adaptador de recepción de WCF-NetMsmq

#### <a name="password"></a>Contraseña
Especifique la contraseña que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**.

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: WCF todos los adaptadores de envío *excepto* el adaptador WCF-NetNamedPipe  

#### <a name="propagatefaultmessage"></a>PropagateFaultMessage
Especificar si se enrutan o se suspenden mensajes que generan errores en el procesamiento de salida. Esta propiedad sólo es válida para puertos de petición-respuesta. 

**Nota**  
No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento.

Tipo: booleano  
Valor predeterminado: **True**  

    Applicable values are:  
        - True: Route the message that fails outbound processing to a subscribing application (such as another receive port or orchestration schedule)
        - False: Suspend failed messages and generate a negative acknowledgment (NACK)

Se aplica a: WCF todos los adaptadores de envío *excepto* el adaptador WCF-NetMsmq
  
#### <a name="proxyaddress"></a>ProxyAddress
Especificar la dirección del servidor proxy. Use la **https** o **http** esquema según la configuración de seguridad. Esta dirección puede ir seguida de dos puntos y el número de puerto. La propiedad es obligatoria si la **ProxyToUse** propiedad está establecida en **UserSpecified** (por ejemplo, http://127.0.0.1:8080)

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: adaptador de envío WCF-BasicHttp, adaptador de envío WCF-WSHttp  

#### <a name="proxypassword"></a>ProxyPassword
Especifique la contraseña que se utilizará para el servidor proxy especificado en el **ProxyAddress** propiedad.

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: adaptador de envío WCF-BasicHttp, adaptador de envío WCF-WSHttp

#### <a name="proxytouse"></a>ProxyToUse
Especificar el servidor de proxy que se va a utilizar para el tráfico HTTP saliente.

Tipo: cadena  
Valor predeterminado: **ninguno**  

    Applicable values are:  
        - None: Do not use a proxy server for this send port
        - Default: Use the proxy settings in the send handler hosting this send port
        - UserSpecified: Use the proxy server specified in the **ProxyAddress** property

Se aplica a: adaptador de envío WCF-BasicHttp, adaptador de envío WCF-WSHttp  

#### <a name="proxyusername"></a>ProxyUsername
Especifique el nombre de usuario que se utilizará para el servidor proxy especificado en el **ProxyAddress** propiedad. La propiedad es obligatoria si la **ProxyToUse** propiedad está establecida en **UserSpecified**.

Para obtener más información acerca de esta propiedad, vea [cómo configurar un puerto de envío WCF-WSHttp](../core/how-to-configure-a-wcf-wshttp-send-port.md) y [cómo configurar un puerto de envío WCF-BasicHttp](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f).

Tipo: cadena  
Se aplica a: adaptador de envío WCF-BasicHttp, adaptador de envío WCF-WSHttp

#### <a name="replytoaddress"></a>ReplyToAddress
Indicar la dirección de extremo de respuesta para los mensajes WCF salientes que corresponden a los mensajes entrantes recibidos a través de las ubicaciones de recepción de solicitud-respuesta. La propiedad se promociona automáticamente desde los mensajes entrantes.

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: todos los adaptadores WCF *excepto* el adaptador WCF-NetMsmq

#### <a name="securitymode"></a>SecurityMode
Especificar el tipo de seguridad que se usa. Los valores aplicables son distintos para cada adaptador de WCF. Para obtener más información sobre la **SecurityMode** propiedad, vea los temas sobre cada adaptador de WCF en [adaptadores de WCF](../core/wcf-adapters.md). 

**Nota**  
No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento.

Tipo: cadena  
Se aplica a: todos los adaptadores WCF *excepto* los adaptadores de WCF-Custom y WCF-CustomIsolated

#### <a name="sendtimeout"></a>SendTimeout
Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de envío. Este valor especifica un marco temporal para que se complete toda la interacción, incluso si el remitente envía un mensaje de gran tamaño.

Tipo: cadena  
Valor predeterminado: 00:01:00  
Se aplica a: todos los adaptadores WCF *excepto* los adaptadores de WCF-Custom y WCF-CustomIsolated

#### <a name="servicebehaviorconfiguration"></a>ServiceBehaviorConfiguration
Especificar una cadena XML con el **\<comportamiento\>** elemento de la **\<serviceBehaviors\>** elemento que se va a configurar las opciones de comportamiento de WCF servicio. Para obtener más información sobre la **\<serviceBehaviors\>** elemento, vea el tema correspondiente en la sección Vea también.

Ejemplo:

```
<behavior name="SampleServiceBehavior">
<serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
<serviceCredentials>
<serviceCertificate findValue="539d9ab3089bb6dc187fa7dbb382cf01f8d78f5f" storeLocation="CurrentUser" x509FindType="FindByThumbprint"/>
</serviceCredentials>
<serviceMetadata httpGetEnabled="true"/>
</behavior>
```

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: adaptador, adaptador de WCF-CustomIsolated de recepción WCF-Custom

#### <a name="servicecertificate"></a>ServiceCertificate
Si esta propiedad se usa para ubicaciones de recepción, especifique la huella digital del certificado X.509 para las ubicaciones de recepción que los clientes utilizan para autenticar el servicio. El certificado que se usará para esta propiedad debe estar instalado en el **mi** almacenar en la **usuario actual** ubicación.

Si esta propiedad se usar para puertos de envío, especifique la huella digital del certificado X.509 para autenticar el servicio al que este puerto de envío envía los mensajes. El certificado que se usará para esta propiedad debe estar instalado en el **otras personas** almacenar en la **equipo Local** ubicación.

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: 
- Adaptador de WCF-BasicHttp
- Adaptador de WCF-NetMsmq
- Adaptador de WCF-WSHttp
- Adaptador de recepción WCF-NetTcp

#### <a name="suspendmessageonfailure"></a>SuspendMessageOnFailure
Especificar si se va a suspender el mensaje de solicitud cuyo procesamiento de entrada no se puede realizar correctamente debido a un error de canalización de recepción o de enrutamiento.

Tipo: booleano  
Valor predeterminado: True  
Se aplica a: WCF todos los adaptadores de recepción  

#### <a name="textencoding"></a>TextEncoding
Especifique la codificación que se usará para emitir los mensajes en el enlace del juego de caracteres cuando la **MessageEncoding** propiedad está establecida en **texto**. 

**Nota**  
No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento. 

Tipo: cadena  
Valor predeterminado: utf-8  

    Applicable values are:  
        - unicodeFFF: Unicode BigEndian encoding
        - utf-16: 16-bit encoding
        - utf-8: 8-bit encoding

Se aplica a: adaptador de WCF-BasicHttp, adaptador de WCF-WSHttp
  
#### <a name="timetolive"></a>TimeToLive
Especificar el período de validez de los mensajes antes de que caduquen y se coloquen en la cola de mensajes con problemas de entrega. Esta propiedad se define para garantizar que los mensajes con limitaciones temporales no se conviertan en obsoletos antes de que un puerto de envío los procese. Se dice que los mensajes que se encuentren en una cola y no hayan sido consumidos por este puerto de envío en el intervalo especificado caducarán. Los mensajes caducados se envían a una cola especial denominada cola de mensajes con problemas de entrega. La ubicación de la cola de mensajes no enviados se establece con el **DeadLetterQueue** propiedad.

Tipo: cadena  
Valor predeterminado: 1.00:00:00  
Se aplica a: adaptador de envío WCF-NetMsmq

#### <a name="to"></a>A
Especificar la dirección de extremo de destino para mensajes WCF salientes que envían los puertos de envío WCF.

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: WCF todos los adaptadores de envío  

#### <a name="transactionprotocol"></a>TransactionProtocol
Especificar el protocolo de transacción que se usará con este enlace. Esta propiedad es necesaria si la **EnableTransaction** propiedad está establecida en **True**.

Tipo: cadena  
Valor predeterminado: OleTransaction  

    Applicable values are: OleTransaction, WS-AtomicTransaction

Se aplica a: adaptador de WCF-NetNamedPipe, adaptador de WCF-NetTcp  

#### <a name="transportclientcredentialtype"></a>TransportClientCredentialType
Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación del puerto de envío. Los valores aplicables son distintos para cada adaptador de WCF. Para obtener más información sobre la **TransportClientCredentialType** propiedad, vea los temas sobre cada adaptador de WCF en [adaptadores de WCF](../core/wcf-adapters.md).

Tipo: cadena  
Se aplica a: adaptador de WCF-Basic, el adaptador WCF-NetTcp, el adaptador WCF-WSHttp  

#### <a name="transportprotectionlevel"></a>TransportProtectionLevel
Especificar la seguridad en el nivel de transporte TCP. Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere. El cifrado proporciona privacidad de nivel de datos durante el transporte.

Tipo: cadena  
Valor predeterminado: **EncryptAndSign**  

    Applicable values are:  
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed

Se aplica a: adaptador de WCF-NetTcp, adaptador de WCF-NetNamedPipe  

#### <a name="username"></a>UserName
Especifique el nombre de usuario que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**. No tiene que usar el formato dominio\usuario para esta propiedad.

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: WCF todos los adaptadores de envío *excepto* el adaptador WCF-NetNamedPipe

#### <a name="usesourcejournal"></a>UseSourceJournal
Especificar si se deben almacenar copias de mensajes procesados por este puerto de envío en la cola de diario de origen.

Tipo: booleano  
Valor predeterminado: False  
Se aplica a: adaptador de envío WCF-NetMsmq  

#### <a name="usesso"></a>UseSSO
Especificar si se utiliza el inicio de sesión único (SSO) para recuperar credenciales de cliente para la autenticación con el servidor de destino. 

**Nota**  
No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento. 

Tipo: booleano  
Valor predeterminado: False  
Se aplica a: WCF todos los adaptadores de envío *excepto* el adaptador WCF-NetNamedPipe

#### <a name="referencedbindings"></a>ReferencedBindings
Especificar las configuraciones de enlace al que hace referencia el **bindingConfiguration** atributo de la **\<emisor\>** (elemento) para el  **wsFederationHttpBinding** y **customBinding**, lo que indica el Token de seguridad servicio (STS) que emite tokens de seguridad. Para obtener más información sobre la **\<emisor\>** elemento, vea el tema "\<emisor\>" en [http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476).

La información de enlace, como la **\<emisor\>** (elemento) para la **wsFederationHttpBinding** y **customBinding** puede ser configurar a través de la **BindingConfiguration** propiedad de los adaptadores de WCF-Custom y WCF-CustomIsolated. Todas las configuraciones de enlace que se hace referencia para esta propiedad se deben colocar en el formulario de la [ \<enlaces\> ](http://go.microsoft.com/fwlink/?LinkID=80878) elemento. 

**Nota**  
El **bindingConfiguration** atributo de la **\<emisor\>** el elemento debe hacer referencia a un nombre de enlace válido en esta propiedad. 

**Nota**  
El **\<emisor\>** elemento en las configuraciones de enlace que se hace referencia también puede hacer referencia a una configuración de enlace diferentes en esta propiedad si esta cadena de referencia no tiene una dependencia circular. 

Ejemplo: 

```
WCF.BindingConfiguration = @"<wsFederationHttpBinding>
<binding name=""sampleBinding"">
<security mode=""Message"">
<message issuedKeyType=""AsymmetricKey"">
<issuer address=""http://www.contoso.com/samplests"" binding=""wsFederationHttpBinding"" bindingConfiguration=""**contosoSTSBinding**""/>
</message>
</security>
</binding>
</wsFederationHttpBinding>";
WCF.ReferencedBinding =@"<bindings>
<wsFederationHttpBinding>
<binding name=""**contosoSTSBinding**"">
<security mode=""Message"">
<message negotiateServiceCredential=""false"">
<issuer address=""http://northwind.com/samplests"" bindingConfiguration=""**northwindBinding**"" binding=""wsHttpBinding"">
</issuer>
</message>
</security>
</binding>
</wsFederationHttpBinding>
<wsHttpBinding>
<binding name=""**northwindBinding**"">
<security mode=""Message"">
<message clientCredentialType=""Certificate""/>
</security>
</binding>
</wsHttpBinding>
</bindings>" 
``` 

**Nota**  
**ReferencedBinding** no debe contener la configuración de enlace utilizada en el **BindingConfiguration** propiedad.

Tipo: cadena  
Valor predeterminado: una cadena vacía  
Se aplica a: adaptador de WCF-Custom, adaptador de WCF-CustomIsolated
  
## <a name="see-also"></a>Vea también  
 [Adaptadores de WCF](../core/wcf-adapters.md)   
 [\<comportamiento\> de \<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879)   
 [\<enlaces\>](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<comportamiento\> de \<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095)   
 [Entrega ordenada de mensajes](../core/ordered-delivery-of-messages.md)   
 [Equilibrio de carga](http://go.microsoft.com/fwlink/?LinkId=81089)
