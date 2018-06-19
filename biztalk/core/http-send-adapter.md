---
title: Adaptador de envío HTTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e69308b4-421f-4d7c-b9bb-ee086df03272
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce8bfdfd380fac422f79ba175ae075a94f313dec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257980"
---
# <a name="http-send-adapter"></a>Adaptador de envío HTTP
El adaptador de envío HTTP obtiene mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los remite a una URL de destino como resultado de una solicitud HTTP POST. El adaptador de envío HTTP recoge el contenido del mensaje en el cuerpo del objeto de mensaje de BizTalk. El adaptador de envío HTTP no tiene en cuenta las partes restantes del objeto de mensaje de BizTalk.  
  
 Una vez que el adaptador envía el mensaje a la URL de destino y el motor de mensajería de BizTalk recibe el código de estado de HTTP satisfactorio, el adaptador de envío HTTP elimina el mensaje de la base de datos de cuadro de mensajes.  
  
 La redirección de mensajes de HTTP está permitida, y puede configurarse en el puerto de envío.  
  
 El adaptador de envío HTTP se ejecuta en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como aplicación nativa de BizTalk. Permite el envío unidireccional de mensajes, así como la transmisión de petición-respuesta. La ubicación de envío del adaptador de envío HTTP es una URL distintiva que se configura a través del puerto de envío. Esta URL exclusiva puede incluir cadenas de consulta anexas a la dirección URL base.  
  
## <a name="batching-support-for-the-http-send-adapter"></a>Compatibilidad de procesamiento por lotes del adaptador de envío HTTP  
 El adaptador de envío HTTP no admite operaciones de procesamiento por lotes.  
  
## <a name="chunked-encoding-support-for-the-http-send-adapter"></a>Compatibilidad de codificación fragmentada del adaptador de envío HTTP  
 Si el **Habilitar codificación fragmentada** está habilitada la opción de configuración, a continuación, el adaptador de envío HTTP envía mensajes de solicitud utilizando la codificación fragmentada si el tamaño de la solicitud supera los 8 KB. Cuando se utiliza el servidor proxy de HTTP, el adaptador de envío HTTP no utiliza la codificación fragmentada, y siempre almacena los datos antes de enviarlos. El **Habilitar codificación fragmentada** opción de configuración está habilitada de forma predeterminada.  
  
 Cuando el adaptador de envío reciba un mensaje de respuesta, podrá aceptar mensajes de respuesta en cuyo cuerpo de mensaje se utilice una codificación fragmentada.  
  
## <a name="client-authentication-for-the-http-send-adapter"></a>Autenticación de cliente del adaptador de envío HTTP  
 La autenticación del adaptador de envío HTTP con el servidor de destino puede ser de los siguientes tipos:  
  
-   **Anónimo.** El adaptador de HTTP no envía las credenciales al conectarse al servidor de destino. Si el servidor de destino permite la autenticación anónima, se utilizarán las credenciales de la cuenta anónima configurada en el servidor de destino.  
  
-   **Básica.** El adaptador de HTTP envía el nombre de usuario y la contraseña a través de una conexión HTTP de texto sin formato.  
  
-   **Síntesis.** El adaptador de envío HTTP envía las contraseñas en un formato cifrado a través de la conexión de HTTP.  
  
-   **Kerberos.** No se envía el nombre de usuario ni la contraseña a través de la conexión de HTTP. El adaptador de envío HTTP utiliza las credenciales del proceso en el que se ejecuta el adaptador de envío HTTP para este tipo de autenticación.  
  
 Como opción adicional, el adaptador de envío HTTP puede proporcionar un certificado de Capa de sockets seguros (SSL) al servidor Web si el servidor lo necesita, o si simplemente lo admite.  
  
## <a name="client-certificates-for-the-http-send-adapter"></a>Certificados de cliente para el adaptador de envío HTTP  
 El adaptador de envío HTTP puede establecer una conexión segura con servidores que admitan o requieran certificados de cliente. Si se especifica un certificado de cliente, el adaptador de envío HTTP utilizará el certificado para conectarse a los servidores que requieran o admitan certificados de cliente. Si no se especifica ningún certificado de cliente y el servidor de destino así lo requiere, el adaptador de envío HTTP no podrá enviar el mensaje y seguirá la lógica de reintentos estándar.  
  
 El adaptador de envío HTTP usará el certificado de cliente ubicado en el almacén personal de la cuenta bajo la que se esté ejecutando el proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El certificado se especifica mediante la huella digital. Si, por cualquier motivo, el adaptador de envío HTTP no consigue cargar el certificado, el mensaje que se intentaba enviar quedará suspendido.  
  
## <a name="single-sign-on-support-for-the-http-adapter"></a>Compatibilidad de inicio de sesión único (SSO) con el adaptador de HTTP  
 El inicio de sesión único (SSO) empresarial puede configurarse, a través de la consola de administración de BizTalk, para su uso con la ubicación de recepción de HTTP o con el puerto de envío. En este tema se describe el funcionamiento de SSO con el adaptador de HTTP.  
  
 **Ubicación de recepción de compatibilidad de inicio de sesión único para HTTP**  
  
 Cuando los servicios de Microsoft Internet Information Server (IIS) reciben una solicitud  de HTTP procedente de un cliente Web, IIS se encarga de autenticar al usuario. La extensión de Interfaz de programación de aplicaciones para servidores de Internet (ISAPI) actúa como usuario de Microsoft Windows y, a continuación, llama al almacén de credenciales de SSO para obtener un vale cifrado. Este vale se almacena como el **SSOTicket** propiedad en el contexto del mensaje.  
  
 En un escenario de paso, el motor de mensajería de BizTalk dirige el mensaje a la base de datos de cuadros de mensajes. Cuando el adaptador recibe el mensaje de la base de datos de cuadro de mensajes, el adaptador HTTP llama el **ISSOTicket.RedeemTicket (método)** con el vale cifrado y el nombre de la aplicación para recuperar las credenciales de back-end de la Almacén de SSO. Seguidamente, el adaptador de HTTP utiliza las credenciales externas para conectarse al sistema de servidor y procesar la solicitud. Para obtener más información sobre las aplicaciones afiliadas, vea [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).  
  
 En escenarios en los que una orquestación llama al adaptador, el motor de mensajería de BizTalk envía este mensaje a la base de datos de cuadro de mensajes. La orquestación debe asegurarse de que tanto el **SSOTicket** propiedad de contexto y la **Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID** son propiedad de contexto del mensaje que contiene el vale mantiene. Cuando el adaptador recibe este mensaje de la base de datos de cuadro de mensajes, el adaptador llama **RedeemTicket** con el vale cifrado para recuperar las credenciales de back-end del almacén de SSO. El usuario que diseñe la programación deberá copiar específicamente esta propiedad en el mensaje.  
  
 **Compatibilidad de inicio de sesión único para los adaptadores de envío HTTP**  
  
 Si está habilitado el SSO, cuando un puerto de envío HTTP recibe un mensaje con el **seguro** propiedad, llama al servidor SSO para validar y canjear el vale para una aplicación afiliada. La aplicación de administración, los administradores afiliados o los administradores de SSO de la aplicación afiliada pueden llamar a SSO para canjear un vale. SSO se encarga entonces de descifrar el vale y de obtener las credenciales de servidor. Los escenario de paso a través y de orquestación son los mismos que para el puerto de envío de HTTP.  
  
 De forma predeterminada, el SSO está deshabilitado en el puerto de envío de HTTP. Para obtener más información acerca de cómo habilitar SSO para el puerto de envío HTTP, consulte [configurar un puerto de envío HTTP](../core/configuring-an-http-send-port.md).  
  
> [!NOTE]
>  El inicio de sesión único (SSO) sólo podrá utilizarse con la autenticación básica o implícita.  
  
 Para implementar correctamente la compatibilidad del inicio de sesión único en el adaptador de envío y de recepción HTTP, deberán cumplirse las condiciones siguientes:  
  
-   Debe especificar la misma cuenta de usuario en los siguientes lugares:  
  
    -   La identidad del grupo de aplicaciones (IIS 7.0) o identidad de aplicaciones COM+ de host del directorio IIS virtual al que supervisa el adaptador de recepción HTTP. Para obtener más información acerca de cómo configurar IIS para HTTP ubicaciones de recepción, consulte [cómo configurar IIS para una ubicación de recepción HTTP](../core/how-to-configure-iis-for-an-http-receive-location.md).  
  
    -   Las credenciales de inicio de sesión para la instancia de host aislado que se ejecuta el adaptador de HTTP. Para obtener información sobre cómo configurar las credenciales de inicio de sesión para una instancia de host, consulte [cómo modificar propiedades de instancia de Host](../core/how-to-modify-host-instance-properties.md).  
  
-   El host aislado que esté utilizando el adaptador de HTTP deberá configurarse con la opción Autenticación de confianza. Para obtener información acerca de cómo configurar un host como autenticación de confianza, consulte [cómo modificar propiedades de Host](../core/how-to-modify-host-properties.md).  
  
## <a name="negative-acknowledgment-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapter"></a>Mensajes de confirmación negativa (NACK) generados por los adaptadores HTTP o SOAP para errores de transmisión  
 Cuando un mensaje se transmite correctamente, el motor de mensajería de BizTalk publica un mensaje de confirmación asociado (ACK) al cuadro de mensajes, siempre que estén habilitadas las notificaciones. Del mismo modo, cuando el motor de mensajería de BizTalk suspende un mensaje, o cuando el motor de orquestación suspende una orquestación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] publica un mensaje de confirmación negativa (NACK) asociado al cuadro de mensajes. El mensaje de confirmación negativa (NACK) contiene propiedades de contexto y un cuerpo de mensaje que contiene un error de SOAP. Si el mensaje de confirmación negativa se genera debido a un error de transmisión del adaptador HTTP o SOAP, el error de SOAP contendrá los elementos Headers y Body de la respuesta procedente del servidor Web de destino. A continuación, se incluye el ejemplo de un error de SOAP incluido en un mensaje de confirmación negativa que se ha generado debido a un error en la transmisión HTTP:  
  
```  
<SOAP:Envelope xmlns:SOAP="http://schemas.xmlsoap.org/soap/envelope/" SOAP:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
   <SOAP:Body>  
      <SOAP:Fault>  
         <faultcode>Microsoft BizTalk Server Negative Acknowledgment</faultcode>   
         <faultstring>An error occurred while processing the message, refer to the details section for more information</faultstring>   
         <faultactor>http://localhost/receivestandard.asp</faultactor>   
         <detail>  
            <ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
            <NAckID>{4E646707-03AA-4493-95C7-A64B09E2987D}</NAckID>  
            <ErrorCode>0x80131600</ErrorCode>  
            <ErrorCategory>0</ErrorCategory>  
            <ErrorDescription>The remote server returned an error: (404) Not Found.</ErrorDescription>  
            <ErrorDetail>  
            <HttpErrorDetail xmlns="http://schema.microsoft.com/BizTalk/2006/HttpErrorDetails.xsd">  
               <Headers>Server: Microsoft-IIS/5.1 Date: Wed, 21 Apr 2005 00:27:47 GMT X-Powered-By: ASP.NET Connection: close Content-Type: text/html Content-Length: 67 </Headers>  
               <Body>We could not locate the page you requested. Please check the URL.</Body>  
            </HttpErrorDetail>  
            </ErrorDetail>  
            </ns0:NACK>  
         </detail>  
      </SOAP:Fault>  
   </SOAP:Body>  
</SOAP:Envelope>  
```  
  
> [!NOTE]
>  Los elementos Headers y Body tienen un límite de 48 KB. El elemento Headers se redondea hacia el par de valores de encabezado entero que esté más cercano sin exceder dicho límite. El elemento Body se trunca a 48 KB.  
  
> [!NOTE]
>  Los mensajes de confirmación (ACK) y de confirmación negativa (NACK) se descartan cuando no hay suscripciones que coincidan. El motor de mensajería de BizTalk no suspende los mensajes de confirmación y de confirmación negativa.  
  
 Para suscribirse a un mensaje de confirmación negativa (NACK), puede seguir uno de estos procedimientos:  
  
-   Crear un puerto de envío con un filtro para la propiedad de contexto de mensaje en cuestión. Vea **propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] para obtener una lista de propiedades de contexto del mensaje de sistema, incluidas aquéllas relativas a la confirmación del mensaje.  
  
-   Enviar desde un puerto de orquestación marcado con **notificación de entrega = transmitido**. Si un puerto de orquestación está marcado con **notificación de entrega = transmitido**, la orquestación espera hasta que recibe una confirmación o una confirmación NEGATIVA para el mensaje que se ha transmitido. Si se genera un mensaje de confirmación negativa, éste se dirige a la orquestación que, a su vez, emite una excepción de tipo DeliveryFailureException. La excepción DeliveryFailureException queda deserializada del error de SOAP contenido en el cuerpo del mensaje de confirmación negativa. Para recuperar la cadena de mensaje de excepción del error de SOAP devuelto a la orquestación, convierta la excepción DeliveryFailureException en SoapException y, a continuación, obtenga acceso a InnerXml desde la sección de detalles de SOAP. El siguiente ejemplo de código muestra cómo hacerlo:  
  
    ```  
    // Cast the DeliveryFailureException to a SoapException…  
    System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
    System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
    //e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
    //object type created in an Exception handler  
  
    ```  
  
     El ejemplo de código que figura sobre estas líneas devuelve un fragmento XML similar al siguiente.  
  
    ```  
    <ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
    <NAckID>{4E646707-03AA-4493-95C7-A64B09E2987D}</NAckID>  
    <ErrorCode>0x80131600</ErrorCode>  
    <ErrorCategory>0</ErrorCategory>  
    <ErrorDescription>The remote server returned an error: (404) Not Found.</ErrorDescription>  
    <ErrorDetail>  
    <HttpErrorDetail xmlns="http://schema.microsoft.com/BizTalk/2006/HttpErrorDetails.xsd">  
       <Headers>Server: Microsoft-IIS/5.1 Date: Wed, 21 Apr 2005 00:27:47 GMT X-Powered-By: ASP.NET Connection: close Content-Type: text/html Content-Length: 67 </Headers>  
       <Body>We could not locate the page you requested. Please check the URL.</Body>  
    </HttpErrorDetail>  
    </ErrorDetail>  
    </ns0:NACK>  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Adaptador de HTTP](../core/http-adapter.md)  
**Objetos COM de SSO**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]