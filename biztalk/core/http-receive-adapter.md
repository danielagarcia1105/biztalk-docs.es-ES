---
title: Adaptador de recepción HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9008833c-5a02-4fb4-a43e-09ca28a21eff
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a21679c2000f85d8fa4ae32f4959b79bd8c55f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977061"
---
# <a name="http-receive-adapter"></a><span data-ttu-id="258d8-102">Adaptador de recepción HTTP</span><span class="sxs-lookup"><span data-stu-id="258d8-102">HTTP Receive Adapter</span></span>
<span data-ttu-id="258d8-103">La ubicación de recepción del adaptador de recepción HTTP es una dirección URL distinta configurada a través de la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="258d8-103">The receive location for the HTTP receive adapter is a distinct URL configured through the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="258d8-104">Puede configurar el adaptador de recepción HTTP para el envío asincrónico o sincrónico desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="258d8-104">You can configure the HTTP receive adapter for either asynchronous submission or synchronous submission from the client.</span></span> <span data-ttu-id="258d8-105">Los envíos asincrónicos unidireccionales, mientras que los envíos sincrónicos son bidireccionales o envíos de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="258d8-105">Asynchronous submissions are one-way submissions and synchronous submissions are two way or request-response submissions.</span></span>  
  
 <span data-ttu-id="258d8-106">Utilice la seguridad de IIS para la autenticación y autorización de solicitudes entrantes.</span><span class="sxs-lookup"><span data-stu-id="258d8-106">You use IIS security for authentication and authorization of incoming requests.</span></span>  
  
## <a name="http-get-and-http-post-requests"></a><span data-ttu-id="258d8-107">Solicitudes HTTP GET y HTTP POST</span><span class="sxs-lookup"><span data-stu-id="258d8-107">HTTP GET and HTTP POST Requests</span></span>  
 <span data-ttu-id="258d8-108">La recepción HTTP de adaptador puede recibir mensajes de dos maneras diferentes: mediante una solicitud HTTP POST o una solicitud HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="258d8-108">The HTTP receive adapter can receive messages in two different ways—by an HTTP POST request or an HTTP GET request.</span></span>  
  
 <span data-ttu-id="258d8-109">Cuando un adaptador de recepción HTTP obtiene mensajes con una solicitud HTTP POST, se produce esta secuencia de sucesos:</span><span class="sxs-lookup"><span data-stu-id="258d8-109">When an HTTP receive adapter gets messages on an HTTP POST request, the following sequence of events occurs:</span></span>  
  
1. <span data-ttu-id="258d8-110">La dirección URL configurada en BizTalk Server recibe un mensaje nuevo en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="258d8-110">The URL configured in BizTalk Server receives a new message on the receive location.</span></span>  
  
2. <span data-ttu-id="258d8-111">El adaptador de recepción crea un objeto de mensaje de BizTalk para poder enviar el mensaje al servidor.</span><span class="sxs-lookup"><span data-stu-id="258d8-111">The receive adapter creates a BizTalk Message object so that the message can be submitted to the server.</span></span>  
  
3. <span data-ttu-id="258d8-112">El adaptador de recepción crea el objeto de mensaje de BizTalk con solo una parte, la parte del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="258d8-112">The receive adapter creates the BizTalk Message object with only one part—the body part.</span></span>  
  
4. <span data-ttu-id="258d8-113">Una vez que se ha leído el mensaje y se ha enviado correctamente al servidor, el adaptador de recepción HTTP envía un código HTTP 202 al cliente para indicar que se aceptó la solicitud.</span><span class="sxs-lookup"><span data-stu-id="258d8-113">After the message has been read and successfully submitted to the server, the HTTP receive adapter sends an HTTP code 202 back to the client indicating that the request was accepted.</span></span>  
  
    <span data-ttu-id="258d8-114">Opcionalmente, el adaptador de recepción HTTP puede enviar un token de correlación de mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="258d8-114">Optionally, the HTTP receive adapter can send a message correlation token on the HTTP response.</span></span> <span data-ttu-id="258d8-115">Este token de correlación representa el mensaje en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="258d8-115">This correlation token represents the message within BizTalk Server.</span></span> <span data-ttu-id="258d8-116">Si la ubicación de recepción HTTP se encuentra en un puerto de solicitud-respuesta, el adaptador devuelve el código de recepción correcta 200 junto con el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="258d8-116">If the HTTP receive location is in a request-response port, the adapter returns success code 200 along with the response message.</span></span>  
  
   <span data-ttu-id="258d8-117">Cuando un adaptador de recepción HTTP procesa mensajes de una solicitud HTTP GET, el adaptador de recepción crea un objeto de mensaje de BizTalk y pone la cadena de consulta descodificada de la solicitud HTTP GET en la parte del cuerpo del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="258d8-117">When an HTTP receive adapter processes messages from an HTTP GET request, the receive adapter creates a BizTalk Message object and puts the decoded query string of the HTTP GET request into the BizTalk message body part.</span></span> <span data-ttu-id="258d8-118">El adaptador de HTTP selecciona la cadena de consulta que se pone en la parte del cuerpo del mensaje de BizTalk con el siguiente algoritmo:</span><span class="sxs-lookup"><span data-stu-id="258d8-118">The HTTP adapter selects the query string that is placed into the BizTalk message body part using the following algorithm:</span></span>  
  
-   <span data-ttu-id="258d8-119">Si el adaptador de recepción HTTP recibe una solicitud HTTP GET, divide la cadena de URI entrante en dos partes, utilizando el signo de interrogación (?) como delimitador.</span><span class="sxs-lookup"><span data-stu-id="258d8-119">If the HTTP receive adapter receives an HTTP GET request, it splits the incoming URI string into two parts, using the question mark (?) symbol as a delimiter.</span></span>  
  
-   <span data-ttu-id="258d8-120">La primera parte de la cadena URI, la parte antes del delimitador de signo de interrogación, se copia en el **InboundTransportLocation** propiedad en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="258d8-120">The first part of the URI string, the part before the question mark delimiter, is copied into the **InboundTransportLocation** property on the message context.</span></span> <span data-ttu-id="258d8-121">El **InboundTransportLocation** propiedad identifica la ubicación donde BizTalk Server recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="258d8-121">The **InboundTransportLocation** property uniquely identifies the location where BizTalk Server received the message.</span></span> <span data-ttu-id="258d8-122">El motor utiliza esta propiedad para determinar la ubicación de recepción que se debe ejecutar para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="258d8-122">The engine uses this property to determine which receive location to run for the message.</span></span>  
  
-   <span data-ttu-id="258d8-123">El adaptador de HTTP toma el resto de la cadena de URI (después del signo de interrogación) y la descodifica y copia en la parte del cuerpo del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="258d8-123">The HTTP adapter takes the rest of the URI string, the part after the question mark delimiter, and decodes and copies it into the BizTalk message body part.</span></span>  
  
-   <span data-ttu-id="258d8-124">Si el adaptador de recepción HTTP recibe una operación HTTP GET o HTTP POST vacía, se rechaza.</span><span class="sxs-lookup"><span data-stu-id="258d8-124">If an empty HTTP GET or HTTP POST operation is received by the HTTP receive adapter, it is rejected.</span></span>  
  
## <a name="http-receive-adapter-processing-of-a-get-request"></a><span data-ttu-id="258d8-125">Cómo procesa el adaptador de recepción HTTP una solicitud GET</span><span class="sxs-lookup"><span data-stu-id="258d8-125">HTTP Receive Adapter Processing of a GET Request</span></span>  
 <span data-ttu-id="258d8-126">A continuación se muestran algunos ejemplos de cómo procesa el adaptador de recepción HTTP los mensajes recibidos con solicitudes HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="258d8-126">The following are examples of how the HTTP receive adapter processes messages received by HTTP GET requests.</span></span> <span data-ttu-id="258d8-127">Estos mensajes asumen que el adaptador de recepción HTTP está configurado con las siguientes ubicaciones de recepción:</span><span class="sxs-lookup"><span data-stu-id="258d8-127">These examples assume that the HTTP receive adapter is configured with the following two receive locations:</span></span>  
  
```  
/vroot/BTSHTTPReceive.dll  
/vroot/BTSHTTPReceive.dll?LocationID=1  
```  
  
1.  <span data-ttu-id="258d8-128">Dada la siguiente solicitud HTTP GET para el cliente:</span><span class="sxs-lookup"><span data-stu-id="258d8-128">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1  
    ```  
  
     <span data-ttu-id="258d8-129">El adaptador de recepción HTTP actúa del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="258d8-129">The action taken by the HTTP receive adapter is as follows:</span></span>  
  
     <span data-ttu-id="258d8-130">Establecer el **InboundTransportLocation** propiedad en el contexto del mensaje igual a /vroot/BTSHTTPReceive.dll y la parte de cuerpo del objeto de mensaje de BizTalk igual a LocationID = 1.</span><span class="sxs-lookup"><span data-stu-id="258d8-130">Set the **InboundTransportLocation** property on the message context equal to /vroot/BTSHTTPReceive.dll, and the BizTalk Message object body part equal to LocationID=1.</span></span>  
  
2.  <span data-ttu-id="258d8-131">Dada la siguiente solicitud HTTP GET para el cliente:</span><span class="sxs-lookup"><span data-stu-id="258d8-131">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1&MyParam=My%20Value  
    ```  
  
     <span data-ttu-id="258d8-132">El adaptador de recepción HTTP actúa del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="258d8-132">The action taken by the HTTP receive adapter is as follows:</span></span>  
  
     <span data-ttu-id="258d8-133">Establecer el **InboundTransportLocation** propiedad igual a /vroot/BTSHTTPReceive.dll y el cuerpo del objeto de mensaje de BizTalk parte igual a LocationID = 1 & MyParam = My Value.</span><span class="sxs-lookup"><span data-stu-id="258d8-133">Set the **InboundTransportLocation** property equal to /vroot/BTSHTTPReceive.dll, and the BizTalk Message object body part equal to LocationID=1&MyParam=My Value.</span></span>  
  
3.  <span data-ttu-id="258d8-134">Dada la siguiente solicitud HTTP GET para el cliente:</span><span class="sxs-lookup"><span data-stu-id="258d8-134">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll  
    ```  
  
     <span data-ttu-id="258d8-135">Adaptador de recepción de la acción realizada por HTTP es + como sigue:</span><span class="sxs-lookup"><span data-stu-id="258d8-135">The action taken by the HTTP receive adapter is+ as follows:</span></span>  
  
     <span data-ttu-id="258d8-136">Rechace la solicitud debido al formato incorrecto de la solicitud HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="258d8-136">Reject the request due to incorrect formatting of the HTTP GET request.</span></span>  
  
## <a name="batching-support-for-the-http-receive-adapter"></a><span data-ttu-id="258d8-137">Compatibilidad del adaptador de recepción HTTP con el procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="258d8-137">Batching Support for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="258d8-138">El adaptador de recepción HTTP envía mensajes al servidor en lotes.</span><span class="sxs-lookup"><span data-stu-id="258d8-138">The HTTP receive adapter submits messages to the server in batches.</span></span> <span data-ttu-id="258d8-139">El tamaño del lote utilizado para enviar mensajes al servidor se puede configurar en el controlador de recepción del adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="258d8-139">The size of the batch used to submit messages to the server can be configured on the HTTP adapter receive handler.</span></span>  
  
## <a name="http-receive-adapter-support-for-suspending-failed-requests"></a><span data-ttu-id="258d8-140">Capacidad del adaptador de recepción HTTP para suspender solicitudes con errores</span><span class="sxs-lookup"><span data-stu-id="258d8-140">HTTP Receive Adapter Support for Suspending Failed Requests</span></span>  
 <span data-ttu-id="258d8-141">El adaptador de recepción HTTP de BizTalk Server tiene un valor de configuración, **suspender solicitudes con errores**, para controlar lo que ocurre con una solicitud HTTP si se produce un error de procesamiento entrante debido a un error de canalización de recepción, un error de asignación, o un Error de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="258d8-141">The BizTalk Server HTTP receive adapter has a configuration setting, **Suspend Failed Requests**, to control what happens with an HTTP request if it fails inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="258d8-142">Esta opción de configuración tiene dos valores posibles:</span><span class="sxs-lookup"><span data-stu-id="258d8-142">The setting has two possible values:</span></span>  
  
-   <span data-ttu-id="258d8-143">**Es False.**</span><span class="sxs-lookup"><span data-stu-id="258d8-143">**False.**</span></span> <span data-ttu-id="258d8-144">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="258d8-144">This is the default setting.</span></span> <span data-ttu-id="258d8-145">El adaptador de recepción HTTP descarta los mensajes que dan error en el procesamiento de entrada debido a un error de canalización de recepción, un error de asignación o un error de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="258d8-145">The HTTP receive adapter discards messages that fail inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="258d8-146">Además, se envía un código de estado de error 401 o 500 al cliente.</span><span class="sxs-lookup"><span data-stu-id="258d8-146">Additionally, an error status code 401 or 500 is sent to the client.</span></span> 
  
-   <span data-ttu-id="258d8-147">**Es true.**</span><span class="sxs-lookup"><span data-stu-id="258d8-147">**True.**</span></span> <span data-ttu-id="258d8-148">El adaptador de recepción HTTP suspende los mensajes que dan error en el procesamiento de entrada debido a un error de canalización de recepción, un error de asignación o un error de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="258d8-148">The HTTP receive adapter suspends messages that fail inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="258d8-149">Para unidireccional puertos de recepción un **aceptado** se envía el código de estado 202 al cliente.</span><span class="sxs-lookup"><span data-stu-id="258d8-149">For one-way receive ports an **Accepted** status code 202 is sent to the client.</span></span> <span data-ttu-id="258d8-150">Para bidireccional puertos de recepción un **Error** código de estado 500 se envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="258d8-150">For two-way receive ports an **Error** status code 500 is sent to the client.</span></span>  
  
## <a name="chunked-encoding-support-for-the-http-receive-adapter"></a><span data-ttu-id="258d8-151">Compatibilidad del adaptador de recepción HTTP con la codificación fragmentada</span><span class="sxs-lookup"><span data-stu-id="258d8-151">Chunked Encoding Support for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="258d8-152">El adaptador de recepción HTTP acepta solicitudes HTTP con mensajes que tienen el cuerpo con codificación fragmentada.</span><span class="sxs-lookup"><span data-stu-id="258d8-152">The HTTP receive adapter accepts HTTP requests with chunked encoded body messages.</span></span> <span data-ttu-id="258d8-153">El adaptador de recepción utiliza la codificación fragmentada para enviar mensajes de respuesta cuando el tamaño del cuerpo es superior a 4 KB.</span><span class="sxs-lookup"><span data-stu-id="258d8-153">The receive adapter uses chunked encoding to send response messages when the body size is larger than 4 KB.</span></span> <span data-ttu-id="258d8-154">La codificación fragmentada se puede desactivar estableciendo la clave del Registro DWORD se describe en [parámetros de ajuste y configuración del adaptador de HTTP](../core/http-adapter-configuration-and-tuning-parameters.md)</span><span class="sxs-lookup"><span data-stu-id="258d8-154">Chunked encoding can be turned off by setting the DWORD registry entry described in [HTTP Adapter Configuration and Tuning Parameters](../core/http-adapter-configuration-and-tuning-parameters.md)</span></span>  
  
## <a name="client-certificates-for-the-http-receive-adapter"></a><span data-ttu-id="258d8-155">Certificados de cliente para el adaptador de recepción HTTP</span><span class="sxs-lookup"><span data-stu-id="258d8-155">Client Certificates for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="258d8-156">Siempre que se utiliza una conexión segura con un certificado de cliente para la ubicación de recepción HTTP, el adaptador de recepción HTTP obtiene la huella digital del certificado de cliente de Microsoft Internet Information Services (IIS) y la agrega al contexto de todos los mensajes que se recibieron mediante HTTPS en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="258d8-156">Whenever a secure connection with a client certificate is used for the HTTP receive location, the HTTP receive adapter obtains the client certificate thumbprint from Microsoft Internet Information Services (IIS) and adds it to the message context of all messages that were received over HTTPS on that location.</span></span> <span data-ttu-id="258d8-157">El adaptador de recepción HTTP establece las siguientes propiedades del sistema:</span><span class="sxs-lookup"><span data-stu-id="258d8-157">The HTTP receive adapter sets the following system properties:</span></span>  
  
```  
SourcePartyEvidenceQualifier = "Certificate"  
SourcePartyEvidence = <certificate thumbprint>  
```  
  
## <a name="status-codes-returned-by-the-http-receive-adapter"></a><span data-ttu-id="258d8-158">Códigos de estado devueltos por el adaptador de recepción HTTP</span><span class="sxs-lookup"><span data-stu-id="258d8-158">Status Codes Returned by the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="258d8-159">La lista siguiente contiene los códigos de estado devueltos por el adaptador de recepción HTTP.</span><span class="sxs-lookup"><span data-stu-id="258d8-159">The following list contains status codes returned by the HTTP receive adapter.</span></span>  
  
-   <span data-ttu-id="258d8-160">**200 ACEPTAR.**</span><span class="sxs-lookup"><span data-stu-id="258d8-160">**200 OK.**</span></span> <span data-ttu-id="258d8-161">El adaptador procesó correctamente el mensaje de solicitud y generó una respuesta.</span><span class="sxs-lookup"><span data-stu-id="258d8-161">The adapter successfully processed the request message and generated a response.</span></span> <span data-ttu-id="258d8-162">El adaptador devuelve este código de estado en la respuesta HTTP del puerto de solicitud-respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="258d8-162">The adapter returns this status code on the HTTP response from the HTTP request-response port.</span></span>  
  
-   <span data-ttu-id="258d8-163">**Mensaje 202 aceptado.**</span><span class="sxs-lookup"><span data-stu-id="258d8-163">**202 Message Accepted.**</span></span> <span data-ttu-id="258d8-164">El adaptador envió correctamente el mensaje al servidor o una solicitud unidireccional está suspendida.</span><span class="sxs-lookup"><span data-stu-id="258d8-164">The adapter successfully submitted the message into the server or a one-way request is suspended.</span></span> <span data-ttu-id="258d8-165">El adaptador devuelve este código de estado en la respuesta HTTP del puerto de recepción HTTP unidireccional.</span><span class="sxs-lookup"><span data-stu-id="258d8-165">The adapter returns this status code on the HTTP response from a one way HTTP receive port.</span></span>  
  
-   <span data-ttu-id="258d8-166">**401 Acceso denegado.**</span><span class="sxs-lookup"><span data-stu-id="258d8-166">**401 Access Denied.**</span></span> <span data-ttu-id="258d8-167">La solicitud HTTP se recibe en un puerto de recepción que requiere autenticación y la comprobación de seguridad de ese mensaje da error.</span><span class="sxs-lookup"><span data-stu-id="258d8-167">The HTTP request is received on an authentication-required receive port and the security check for that message failed.</span></span> <span data-ttu-id="258d8-168">Por ejemplo, no se resolvió la entidad o no se descifró el mensaje.</span><span class="sxs-lookup"><span data-stu-id="258d8-168">For example, the party was not resolved or the message was not decrypted.</span></span>  
  
-   <span data-ttu-id="258d8-169">**Error de servidor interno 500.**</span><span class="sxs-lookup"><span data-stu-id="258d8-169">**500 Internal Server Error.**</span></span> <span data-ttu-id="258d8-170">Error general al procesar la solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="258d8-170">A general failure to process the HTTP request.</span></span> <span data-ttu-id="258d8-171">No se suspende el mensaje de BizTalk Server a menos que la opción de configuración **suspender solicitudes con errores** está establecido en **True** puerto de recepción para los dos sentidos.</span><span class="sxs-lookup"><span data-stu-id="258d8-171">The message is not suspended by BizTalk Server unless the configuration setting **Suspend Failed Requests** is set to **True** for a two-way receive port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="258d8-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="258d8-172">See Also</span></span>  
 [<span data-ttu-id="258d8-173">Adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="258d8-173">HTTP Adapter</span></span>](../core/http-adapter.md)