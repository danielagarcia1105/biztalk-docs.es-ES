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
# <a name="soap-send-adapter"></a><span data-ttu-id="fa401-102">Adaptador de envío SOAP</span><span class="sxs-lookup"><span data-stu-id="fa401-102">SOAP Send Adapter</span></span>
<span data-ttu-id="fa401-103">Puede utilizar el adaptador de envío SOAP para llamar a un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="fa401-103">You use the SOAP send adapter to call a Web service.</span></span> <span data-ttu-id="fa401-104">El adaptador de envío SOAP lee el contexto de mensaje del objeto de mensaje de BizTalk para obtener el nombre de proxy, y después llama al proxy de servicio Web externo asociado.</span><span class="sxs-lookup"><span data-stu-id="fa401-104">The SOAP send adapter reads the message context on the BizTalk Message object to get the proxy name and calls the associated external Web service proxy.</span></span>  
  
## <a name="client-authentication-for-the-soap-send-adapter"></a><span data-ttu-id="fa401-105">Autenticación de cliente del adaptador de envío SOAP</span><span class="sxs-lookup"><span data-stu-id="fa401-105">Client Authentication for the SOAP Send Adapter</span></span>  
 <span data-ttu-id="fa401-106">La autenticación del adaptador de envío SOAP con el servidor de destino puede ser de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="fa401-106">The SOAP send adapter authenticates with the destination server by using one of the following authentication types:</span></span>  
  
- <span data-ttu-id="fa401-107">**Anónimo.**</span><span class="sxs-lookup"><span data-stu-id="fa401-107">**Anonymous.**</span></span> <span data-ttu-id="fa401-108">La configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fa401-108">The default setting.</span></span>  
  
- <span data-ttu-id="fa401-109">**Básico.**</span><span class="sxs-lookup"><span data-stu-id="fa401-109">**Basic.**</span></span> <span data-ttu-id="fa401-110">La conexión SOAP envía el nombre de usuario y la contraseña en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="fa401-110">The SOAP connection sends the user name and password in plain text.</span></span>  
  
- <span data-ttu-id="fa401-111">**Síntesis.**</span><span class="sxs-lookup"><span data-stu-id="fa401-111">**Digest.**</span></span> <span data-ttu-id="fa401-112">la conexión SOAP envía el nombre de usuario y la contraseña en formato cifrado.</span><span class="sxs-lookup"><span data-stu-id="fa401-112">The SOAP connection sends the user name and password in an encrypted format.</span></span>  
  
- <span data-ttu-id="fa401-113">**Kerberos o NTLM.**</span><span class="sxs-lookup"><span data-stu-id="fa401-113">**Kerberos or NTLM.**</span></span> <span data-ttu-id="fa401-114">La conexión SOAP no envía el nombre de usuario ni la contraseña.</span><span class="sxs-lookup"><span data-stu-id="fa401-114">Neither the user name nor the password is sent over a SOAP connection.</span></span> <span data-ttu-id="fa401-115">El adaptador de SOAP utiliza siempre las credenciales del proceso en el que se ejecuta el adaptador de envío SOAP para este tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="fa401-115">The SOAP adapter always uses the credentials of the process under which the SOAP send adapter runs for this authentication type.</span></span>  
  
  <span data-ttu-id="fa401-116">Adicionalmente, el adaptador de envío SOAP puede proporcionar un certificado de Capa de sockets seguros (SSL) al servidor Web si el servidor lo necesita, o si simplemente lo admite.</span><span class="sxs-lookup"><span data-stu-id="fa401-116">Additionally, the SOAP send adapter can provide a client Secure Sockets Layer (SSL) certificate to the Web server if the server requires or accepts it.</span></span>  
  
  <span data-ttu-id="fa401-117">Si habilitó Single Sign-On (SSO) empresarial, cuando el adaptador de envío SOAP recibe un mensaje con la solicitud para el **SSOTicket** propiedad, el adaptador se conecta a un servidor SSO para validar y canjear el vale.</span><span class="sxs-lookup"><span data-stu-id="fa401-117">If you enabled Enterprise Single Sign-On (SSO), when the SOAP send adapter receives a message with the request to the **SSOTicket** property, the adapter connects to an SSO server to validate and redeem the ticket.</span></span> <span data-ttu-id="fa401-118">Una vez que el adaptador de SOAP ha validado el vale, éste se descifra, y las credenciales del sistema afiliado se recuperan del almacén de credenciales.</span><span class="sxs-lookup"><span data-stu-id="fa401-118">After the SOAP adapter validates the ticket, it is decrypted and the credentials for the affiliate system are retrieved from the credential store.</span></span> <span data-ttu-id="fa401-119">El adaptador de SOAP utiliza entonces las credenciales para conectarse al sistema afiliado y, seguidamente, se procesa la solicitud.</span><span class="sxs-lookup"><span data-stu-id="fa401-119">The SOAP adapter then uses the credentials to connect to the affiliate system, and the SOAP request is processed.</span></span>  
  
## <a name="client-certificates-for-the-soap-send-adapter"></a><span data-ttu-id="fa401-120">Certificados de cliente para el adaptador de envío SOAP</span><span class="sxs-lookup"><span data-stu-id="fa401-120">Client Certificates for the SOAP Send Adapter</span></span>  
 <span data-ttu-id="fa401-121">El adaptador de envío SOAP puede establecer una conexión segura con servidores que admitan o requieran certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="fa401-121">The SOAP send adapter can establish a secure connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="fa401-122">Si se especifica un certificado de cliente, el adaptador de envío SOAP utilizará el certificado para conectarse a los servidores que requieran o admitan certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="fa401-122">If you specify a client certificate, the SOAP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="fa401-123">Si no se especifica ningún certificado de cliente y el servidor de destino así lo requiere, el adaptador de envío SOAP no podrá enviar el mensaje y seguirá la lógica de reintentos estándar.</span><span class="sxs-lookup"><span data-stu-id="fa401-123">If you do not specify a client certificate and the destination server requires client certificates, the SOAP send adapter fails to send the message and follows the standard retry logic.</span></span>  
  
 <span data-ttu-id="fa401-124">El adaptador de envío SOAP utilizará el certificado de cliente ubicado en el almacén personal de la cuenta en la que se esté ejecutando el proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa401-124">The SOAP send adapter uses the client certificate from the Personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="fa401-125">El adaptador de SOAP especifica el certificado por su huella digital.</span><span class="sxs-lookup"><span data-stu-id="fa401-125">The SOAP adapter specifies the certificate by its thumbprint.</span></span> <span data-ttu-id="fa401-126">Si, por cualquier motivo, el adaptador de envío SOAP no consigue cargar el certificado, el mensaje que se intentaba enviar quedará suspendido.</span><span class="sxs-lookup"><span data-stu-id="fa401-126">If the SOAP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  
  
## <a name="negative-acknowledgement-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapters"></a><span data-ttu-id="fa401-127">Mensajes de confirmación negativa (NACK) generados para errores de transmisión por los adaptadores de HTTP o de SOAP</span><span class="sxs-lookup"><span data-stu-id="fa401-127">Negative Acknowledgement (NACK) Messages Generated for Failed Transmissions by the HTTP or SOAP Adapters</span></span>  
 <span data-ttu-id="fa401-128">Cuando un mensaje se transmite con éxito, el motor de mensajería de BizTalk publica un mensaje de confirmación (ACK) asociado en la base de datos de cuadro de mensajes, siempre que estén habilitadas las notificaciones de entrega.</span><span class="sxs-lookup"><span data-stu-id="fa401-128">When a message is successfully transmitted, the BizTalk Messaging Engine publishes an associated Acknowledgement (ACK) message to the MessageBox database if delivery notifications are enabled.</span></span> <span data-ttu-id="fa401-129">Del mismo modo, cuando el motor de mensajería de BizTalk suspende un mensaje, o cuando el motor de orquestaciones suspende una orquestación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] publica un mensaje de confirmación negativa (NACK) asociado en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fa401-129">Likewise, when a message is suspended by the BizTalk Messaging Engine or an orchestration is suspended by the orchestration engine, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] publishes an associated Negative Acknowledgement (NACK) message to the MessageBox.</span></span> <span data-ttu-id="fa401-130">El mensaje de confirmación negativa (NACK) contiene propiedades de contexto, y un cuerpo de mensaje que consiste en un error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="fa401-130">The NACK message contains context properties and a message body part consisting of a SOAP fault.</span></span> <span data-ttu-id="fa401-131">Si el mensaje NACK se genera debido a un error de transmisión de los adaptadores de HTTP o SOAP, el error de SOAP contendrá el **encabezados** elemento y el **cuerpo** elemento de la respuesta desde el Web de destino servidor.</span><span class="sxs-lookup"><span data-stu-id="fa401-131">If the NACK message is generated due to a failed transmission from the HTTP or SOAP adapters, the SOAP fault contains the **Headers** element and the **Body** element of the response from the destination Web server.</span></span> <span data-ttu-id="fa401-132">A continuación se ofrece un ejemplo de error de SOAP incluido en un mensaje de confirmación negativa (NACK) generado debido a un error en la transmisión SOAP:</span><span class="sxs-lookup"><span data-stu-id="fa401-132">The following is an example of the SOAP fault in a NACK generated for a failed SOAP transmission:</span></span>  
  
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
>  <span data-ttu-id="fa401-133">El **encabezados** elemento y el **cuerpo** tienen un límite de 48 KB.</span><span class="sxs-lookup"><span data-stu-id="fa401-133">The **Headers** element and the **Body** element are limited to 48 KB.</span></span> <span data-ttu-id="fa401-134">El **encabezados** elemento se redondea hacia el par de valor de encabezado más cercano sin exceder el límite.</span><span class="sxs-lookup"><span data-stu-id="fa401-134">The **Headers** element is rounded to the nearest complete header value pair without exceeding the limit.</span></span> <span data-ttu-id="fa401-135">El **cuerpo** elemento se trunca a 48 KB.</span><span class="sxs-lookup"><span data-stu-id="fa401-135">The **Body** element is truncated to 48 KB.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa401-136">Los mensajes de confirmación (ACK) y de confirmación negativa (NACK) se descartan cuando no hay suscripciones que coincidan.</span><span class="sxs-lookup"><span data-stu-id="fa401-136">NACK and ACK messages are discarded if there are no matching subscriptions for them.</span></span> <span data-ttu-id="fa401-137">El motor de mensajería no suspende los mensajes de confirmación (ACK) ni los de confirmación negativa (NACK).</span><span class="sxs-lookup"><span data-stu-id="fa401-137">NACK and ACK messages are not suspended by the Messaging Engine.</span></span>  
  
 <span data-ttu-id="fa401-138">Para suscribirse a un mensaje de confirmación negativa (NACK), puede seguir uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="fa401-138">To subscribe to a NACK message, you can do one of the following:</span></span>  
  
1. <span data-ttu-id="fa401-139">Crear un puerto de envío con un filtro para la propiedad de contexto de mensaje en cuestión.</span><span class="sxs-lookup"><span data-stu-id="fa401-139">Create a send port with a filter for the appropriate message context property.</span></span> <span data-ttu-id="fa401-140">Consulte **las propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] para obtener una lista de propiedades de contexto de mensaje del sistema, incluidas aquéllas relativas a la confirmación de mensaje.</span><span class="sxs-lookup"><span data-stu-id="fa401-140">See **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] for a listing of system message context properties including those related to message acknowledgment.</span></span>  
  
2. <span data-ttu-id="fa401-141">Enviar desde un puerto de orquestación marcado con **notificación de entrega = transmitido**.</span><span class="sxs-lookup"><span data-stu-id="fa401-141">Send from an orchestration port marked with **Delivery Notification = Transmitted**.</span></span> <span data-ttu-id="fa401-142">Si un puerto de orquestación está marcado con **notificación de entrega = transmitido**, la orquestación espera hasta que recibe una confirmación o una confirmación NEGATIVA para el mensaje que se ha transmitido.</span><span class="sxs-lookup"><span data-stu-id="fa401-142">If an orchestration port is marked with **Delivery Notification = Transmitted**, the orchestration will wait until it receives either an ACK or a NACK for the message that was transmitted.</span></span> <span data-ttu-id="fa401-143">Si se genera un mensaje de confirmación negativa, éste se dirige a la orquestación que, a su vez, emite una excepción de tipo DeliveryFailureException.</span><span class="sxs-lookup"><span data-stu-id="fa401-143">If a NACK is generated then it will be routed to the orchestration and the orchestration will throw a DeliveryFailureException.</span></span> <span data-ttu-id="fa401-144">La excepción DeliveryFailureException queda deserializada del error de SOAP contenido en el cuerpo del mensaje de confirmación negativa.</span><span class="sxs-lookup"><span data-stu-id="fa401-144">The DeliveryFailureException is deserialized from the SOAP fault that is contained within the NACK message body.</span></span> <span data-ttu-id="fa401-145">Para recuperar la cadena de mensaje de excepción del error de SOAP devuelto a la orquestación, convierta la excepción DeliveryFailureException en SoapException y, a continuación, obtenga acceso a InnerXml desde la sección de detalles de SOAP.</span><span class="sxs-lookup"><span data-stu-id="fa401-145">To retrieve the exception message string from the SOAP fault that is returned to the orchestration, cast the DeliveryFailureException to a SoapException and then access the InnerXml from the SOAP Detail section.</span></span> <span data-ttu-id="fa401-146">El siguiente ejemplo de código muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="fa401-146">The following code sample demonstrates how to do this:</span></span>  
  
   ```  
   // Cast the DeliveryFailureException to a SoapException…  
   System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
   System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
   //e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
   //object type created in an Exception handler  
   ```  
  
    <span data-ttu-id="fa401-147">El ejemplo de código que figura sobre estas líneas devuelve un fragmento XML similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="fa401-147">The code sample above will return an XML fragment similar to the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fa401-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa401-148">See Also</span></span>  
 <span data-ttu-id="fa401-149">[¿Qué es el adaptador de SOAP?](../core/what-is-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fa401-149">[What Is the SOAP Adapter?](../core/what-is-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="fa401-150">Recomendaciones de seguridad del adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="fa401-150">SOAP Adapter Security Recommendations</span></span>](../core/soap-adapter-security-recommendations.md)