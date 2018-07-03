---
title: Adaptador de envío SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d65218d-516b-4e45-a824-272ef6ef298c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2051cff7fcffc0876bfc45ad59578d08d538265f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002941"
---
# <a name="soap-send-adapter"></a>Adaptador de envío SOAP
Puede utilizar el adaptador de envío SOAP para llamar a un servicio Web. El adaptador de envío SOAP lee el contexto de mensaje del objeto de mensaje de BizTalk para obtener el nombre de proxy, y después llama al proxy de servicio Web externo asociado.  
  
## <a name="client-authentication-for-the-soap-send-adapter"></a>Autenticación de cliente del adaptador de envío SOAP  
 La autenticación del adaptador de envío SOAP con el servidor de destino puede ser de los siguientes tipos:  
  
- **Anónimo.** La configuración predeterminada.  
  
- **Básico.** La conexión SOAP envía el nombre de usuario y la contraseña en texto sin formato.  
  
- **Síntesis.** la conexión SOAP envía el nombre de usuario y la contraseña en formato cifrado.  
  
- **Kerberos o NTLM.** La conexión SOAP no envía el nombre de usuario ni la contraseña. El adaptador de SOAP utiliza siempre las credenciales del proceso en el que se ejecuta el adaptador de envío SOAP para este tipo de autenticación.  
  
  Adicionalmente, el adaptador de envío SOAP puede proporcionar un certificado de Capa de sockets seguros (SSL) al servidor Web si el servidor lo necesita, o si simplemente lo admite.  
  
  Si habilitó Single Sign-On (SSO) empresarial, cuando el adaptador de envío SOAP recibe un mensaje con la solicitud para el **SSOTicket** propiedad, el adaptador se conecta a un servidor SSO para validar y canjear el vale. Una vez que el adaptador de SOAP ha validado el vale, éste se descifra, y las credenciales del sistema afiliado se recuperan del almacén de credenciales. El adaptador de SOAP utiliza entonces las credenciales para conectarse al sistema afiliado y, seguidamente, se procesa la solicitud.  
  
## <a name="client-certificates-for-the-soap-send-adapter"></a>Certificados de cliente para el adaptador de envío SOAP  
 El adaptador de envío SOAP puede establecer una conexión segura con servidores que admitan o requieran certificados de cliente. Si se especifica un certificado de cliente, el adaptador de envío SOAP utilizará el certificado para conectarse a los servidores que requieran o admitan certificados de cliente. Si no se especifica ningún certificado de cliente y el servidor de destino así lo requiere, el adaptador de envío SOAP no podrá enviar el mensaje y seguirá la lógica de reintentos estándar.  
  
 El adaptador de envío SOAP utilizará el certificado de cliente ubicado en el almacén personal de la cuenta en la que se esté ejecutando el proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El adaptador de SOAP especifica el certificado por su huella digital. Si, por cualquier motivo, el adaptador de envío SOAP no consigue cargar el certificado, el mensaje que se intentaba enviar quedará suspendido.  
  
## <a name="negative-acknowledgement-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapters"></a>Mensajes de confirmación negativa (NACK) generados para errores de transmisión por los adaptadores de HTTP o de SOAP  
 Cuando un mensaje se transmite con éxito, el motor de mensajería de BizTalk publica un mensaje de confirmación (ACK) asociado en la base de datos de cuadro de mensajes, siempre que estén habilitadas las notificaciones de entrega. Del mismo modo, cuando el motor de mensajería de BizTalk suspende un mensaje, o cuando el motor de orquestaciones suspende una orquestación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] publica un mensaje de confirmación negativa (NACK) asociado en la base de datos de cuadro de mensajes. El mensaje de confirmación negativa (NACK) contiene propiedades de contexto, y un cuerpo de mensaje que consiste en un error de SOAP. Si el mensaje NACK se genera debido a un error de transmisión de los adaptadores de HTTP o SOAP, el error de SOAP contendrá el **encabezados** elemento y el **cuerpo** elemento de la respuesta desde el Web de destino servidor. A continuación se ofrece un ejemplo de error de SOAP incluido en un mensaje de confirmación negativa (NACK) generado debido a un error en la transmisión SOAP:  
  
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
>  El **encabezados** elemento y el **cuerpo** tienen un límite de 48 KB. El **encabezados** elemento se redondea hacia el par de valor de encabezado más cercano sin exceder el límite. El **cuerpo** elemento se trunca a 48 KB.  
  
> [!NOTE]
>  Los mensajes de confirmación (ACK) y de confirmación negativa (NACK) se descartan cuando no hay suscripciones que coincidan. El motor de mensajería no suspende los mensajes de confirmación (ACK) ni los de confirmación negativa (NACK).  
  
 Para suscribirse a un mensaje de confirmación negativa (NACK), puede seguir uno de estos procedimientos:  
  
1. Crear un puerto de envío con un filtro para la propiedad de contexto de mensaje en cuestión. Consulte **las propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] para obtener una lista de propiedades de contexto de mensaje del sistema, incluidas aquéllas relativas a la confirmación de mensaje.  
  
2. Enviar desde un puerto de orquestación marcado con **notificación de entrega = transmitido**. Si un puerto de orquestación está marcado con **notificación de entrega = transmitido**, la orquestación espera hasta que recibe una confirmación o una confirmación NEGATIVA para el mensaje que se ha transmitido. Si se genera un mensaje de confirmación negativa, éste se dirige a la orquestación que, a su vez, emite una excepción de tipo DeliveryFailureException. La excepción DeliveryFailureException queda deserializada del error de SOAP contenido en el cuerpo del mensaje de confirmación negativa. Para recuperar la cadena de mensaje de excepción del error de SOAP devuelto a la orquestación, convierta la excepción DeliveryFailureException en SoapException y, a continuación, obtenga acceso a InnerXml desde la sección de detalles de SOAP. El siguiente ejemplo de código muestra cómo hacerlo:  
  
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
 [¿Qué es el adaptador de SOAP?](../core/what-is-the-soap-adapter.md)   
 [Recomendaciones de seguridad del adaptador de SOAP](../core/soap-adapter-security-recommendations.md)