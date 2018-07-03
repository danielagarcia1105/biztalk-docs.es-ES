---
title: Enviar y recibir páginas ASPX | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, ASPX pages
- ASPX pages, initiator
- HTTP adapters
- connections, HTTP adapters
- connections, single-action
- ASPX pages, responder
- single-action connections
- RNIFSend.aspx
- connections, asynchronous
- ASPX pages, about ASPX pages
- double-action connections
- connections, synchronous
- connections, double-action
- ASPX pages
- HTTP adapters, connections
- asynchronous connections
- RNIFReceive.aspx
- synchronous connections
ms.assetid: 21e52390-35d8-44b1-a5cd-1cd60cfe6e61
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e688686e8bd787e22d7e5a246e0cce62f469649c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982053"
---
# <a name="send-and-receive-aspx-pages"></a><span data-ttu-id="23558-102">Enviar y recibir páginas ASPX</span><span class="sxs-lookup"><span data-stu-id="23558-102">Send and Receive ASPX Pages</span></span>
<span data-ttu-id="23558-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] páginas ASPX son las interfaces directas entre [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] e Internet.</span><span class="sxs-lookup"><span data-stu-id="23558-103">The Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX pages are the direct interfaces between [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] and the Internet.</span></span> <span data-ttu-id="23558-104">Las dos páginas ASPX son la página de recepción (RNIFReceive.aspx) y la página de envío (RNIFSend.aspx).</span><span class="sxs-lookup"><span data-stu-id="23558-104">The two ASPX pages are the receive page (RNIFReceive.aspx) and the send page (RNIFSend.aspx).</span></span> <span data-ttu-id="23558-105">Cada página ASPX es una extensión correspondiente [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalización.</span><span class="sxs-lookup"><span data-stu-id="23558-105">Each ASPX page is an extension to the corresponding [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipeline.</span></span> <span data-ttu-id="23558-106">La canalización requiere que la página ASPX para controlar los encabezados de RosettaNet Implementation Framework (RNIF).</span><span class="sxs-lookup"><span data-stu-id="23558-106">The pipeline requires the ASPX page to handle RosettaNet Implementation Framework (RNIF) headers.</span></span> <span data-ttu-id="23558-107">La canalización lleva a cabo la mayor parte del procesamiento; HTTP Sin embargo, cada página ASPX realiza el procesamiento de HTTP de los encabezados RNIF.</span><span class="sxs-lookup"><span data-stu-id="23558-107">The pipeline performs most of the HTTP processing; however, each ASPX page performs the HTTP processing of the RNIF headers.</span></span> <span data-ttu-id="23558-108">Las páginas de aumentan su funcionalidad en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="23558-108">The pages augment the functionality in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP adapter.</span></span>  
  
 <span data-ttu-id="23558-109">Cada página ASPX es un ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] sin interfaz de usuario de aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="23558-109">Each ASPX page is an ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web application with no user interface.</span></span> <span data-ttu-id="23558-110">Usa ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web de seguridad para garantizar una conexión segura con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="23558-110">They use ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web security to ensure a secure connection with external parties.</span></span> <span data-ttu-id="23558-111">Proporcionan una capa en el que puede implementar servicios de alta disponibilidad, escalabilidad y tolerancia a errores.</span><span class="sxs-lookup"><span data-stu-id="23558-111">They provide a layer in which you can implement fault tolerance, scalability, and highly available services.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="23558-112"> programa de instalación instala una página RNIFSend.aspx y una página de trabajo RNIFReceive.aspx en cada implementación de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23558-112"> setup installs an RNIFSend.aspx page and an RNIFReceive.aspx page on each deployment of [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="23558-113">Cuando el iniciador o el servicio de respuesta intercambia mensajes con el socio comercial, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] utiliza las páginas ASPX para enviar mensajes a o recibir mensajes de la dirección URL de socio.</span><span class="sxs-lookup"><span data-stu-id="23558-113">When the initiator or responder exchanges messages with the trading partner, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] uses the ASPX pages to send messages to, or receive messages from, the partner URL.</span></span> <span data-ttu-id="23558-114">Si usan el iniciador y el Respondedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], las dos páginas ASPX en el iniciador intercambian mensajes con las dos páginas ASPX en el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="23558-114">If both the initiator and the responder use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the two ASPX pages on the initiator exchange messages with the two ASPX pages on the responder.</span></span> <span data-ttu-id="23558-115">Para obtener más información, consulte el "cómo iniciador y Respondedor ASPX páginas interactúan" subsección siguiente.</span><span class="sxs-lookup"><span data-stu-id="23558-115">For more information, see the "How Initiator and Responder ASPX Pages Interact" subsection below.</span></span>  
  
## <a name="send-aspx-page"></a><span data-ttu-id="23558-116">Enviar página ASPX</span><span class="sxs-lookup"><span data-stu-id="23558-116">Send ASPX Page</span></span>  
 <span data-ttu-id="23558-117">La página RNIFSend.aspx recibe un mensaje desde el adaptador de HTTP de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="23558-117">The RNIFSend.aspx page receives a message from the BizTalk HTTP adapter.</span></span> <span data-ttu-id="23558-118">Crea y agrega los encabezados RNIF al mensaje y, a continuación, envía el mensaje al socio comercial a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="23558-118">It creates and adds RNIF headers to the message, and then sends the message to the partner over the Internet.</span></span> <span data-ttu-id="23558-119">El adaptador de HTTP llama RNIFSend.aspx con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="23558-119">The HTTP adapter calls RNIFSend.aspx with the following command:</span></span>  
  
```  
http://localhost:<port number>/RNIFSend.aspx?<query string>  
```  
  
 <span data-ttu-id="23558-120">La cadena de consulta incluye los siguientes datos que necesita la página de envío para enviar el mensaje al socio comercial y los datos que el asociado debe tener para procesar el mensaje:</span><span class="sxs-lookup"><span data-stu-id="23558-120">The query string includes the following data that the send page needs to send the message to the partner, and the data that the partner must have to process the message:</span></span>  
  
- <span data-ttu-id="23558-121">La dirección URL de socio comercial: http://www.\< *dirección*\>.com/RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="23558-121">The trading-partner URL: http://www.\<*address*\>.com/RNIFReceive.aspx</span></span>  
  
- <span data-ttu-id="23558-122">El tipo de respuesta: sincrónica o asincrónica</span><span class="sxs-lookup"><span data-stu-id="23558-122">The response type: sync or async</span></span>  
  
- <span data-ttu-id="23558-123">La versión RNIF: 1.1 o 2.0.</span><span class="sxs-lookup"><span data-stu-id="23558-123">The RNIF version: 1.1 or 2.0.</span></span>  
  
  <span data-ttu-id="23558-124">El adaptador de HTTP de BizTalk envía un mensaje MIME generado por el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalización de envío a la página del RNIFSend.aspx del iniciador.</span><span class="sxs-lookup"><span data-stu-id="23558-124">The BizTalk HTTP adapter sends a MIME message produced by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline to the initiator RNIFSend.aspx page.</span></span> <span data-ttu-id="23558-125">RNIFSend.aspx procesa el mensaje siguiente:</span><span class="sxs-lookup"><span data-stu-id="23558-125">RNIFSend.aspx processes the message as follows:</span></span>  
  
1.  <span data-ttu-id="23558-126">La página de envío realiza la validación en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="23558-126">The send page performs validation on the message.</span></span>  
  
2.  <span data-ttu-id="23558-127">La página de envío crea un encabezado de extensiones multipropósito de correo Internet (MIME) según el tipo de contenido, la longitud, el identificador y la versión MIME.</span><span class="sxs-lookup"><span data-stu-id="23558-127">The send page creates a Multipurpose Internet Mail Extensions (MIME) header based upon the content type, the length, the ID, and the MIME version.</span></span> <span data-ttu-id="23558-128">El encabezado MIME y límites MIME superiores e inferiores, lo agrega al mensaje.</span><span class="sxs-lookup"><span data-stu-id="23558-128">It adds the MIME header, and upper and lower MIME boundaries, to the message.</span></span>  
  
3.  <span data-ttu-id="23558-129">Para RNIF 2.01, la página de envío establece las propiedades del encabezado HTTP de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="23558-129">For RNIF 2.01, the send page sets properties of the HTTP header as follows:</span></span>  
  
    1.  <span data-ttu-id="23558-130">Establece la propiedad X-RN-Version a la versión especificada en la propiedad de versión de la configuración del proceso.</span><span class="sxs-lookup"><span data-stu-id="23558-130">It sets the X-RN-Version property to the version entered in the Version property of the process configuration settings.</span></span>  
  
    2.  <span data-ttu-id="23558-131">Establece la propiedad X-RN-ResponseType en sync o async, dependiendo del valor de la propiedad IsSynchronous en las opciones de configuración de proceso.</span><span class="sxs-lookup"><span data-stu-id="23558-131">It sets the X-RN-ResponseType property to either sync or async, depending upon the setting of the IsSynchronous property in the process configuration settings.</span></span>  
  
    3.  <span data-ttu-id="23558-132">Establece la propiedad Content-Length en el tamaño del mensaje completo.</span><span class="sxs-lookup"><span data-stu-id="23558-132">It sets the Content-Length property to the size of the full message.</span></span>  
  
4.  <span data-ttu-id="23558-133">Mediante una solicitud HTTP Post, la página de envío envía el mensaje a la dirección URL de destino del asociado, como se establece en la configuración de dirección URL de acción o señal en el acuerdo entre socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="23558-133">Using an HTTP Post, the send page sends the message to the partner's destination URL, as set in the Action URL or Signal URL settings in the trading partner agreement.</span></span>  
  
5.  <span data-ttu-id="23558-134">La página de envío espera a que la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="23558-134">The send page waits for the HTTP response.</span></span> <span data-ttu-id="23558-135">Cuando recibe la respuesta, lo enruta al adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="23558-135">When it receives the response, it routes it to the HTTP adapter.</span></span>  
  
6.  <span data-ttu-id="23558-136">Si la conexión es asincrónica, la página de envío cierra la conexión y su procesamiento está completo.</span><span class="sxs-lookup"><span data-stu-id="23558-136">If the connection is asynchronous, the send page closes the connection, and its processing is complete.</span></span>  
  
7.  <span data-ttu-id="23558-137">Si la conexión es sincrónica, la página de envío mantiene la conexión abierta para un mensaje devuelto.</span><span class="sxs-lookup"><span data-stu-id="23558-137">If the connection is synchronous, the send page keeps the connection open for a returned message.</span></span> <span data-ttu-id="23558-138">Después de recibir el mensaje, realiza el mismo proceso que una página de trabajo RNIFReceive.aspx realiza en un mensaje recibido, envía el mensaje recibido al adaptador de HTTP y, a continuación, cierra la conexión.</span><span class="sxs-lookup"><span data-stu-id="23558-138">After it receives the message, it performs the same processing that an RNIFReceive.aspx page performs on a received message, sends the received message to the HTTP adapter, and then closes the connection.</span></span>  
  
## <a name="receive-aspx-page"></a><span data-ttu-id="23558-139">Aparece la página ASPX</span><span class="sxs-lookup"><span data-stu-id="23558-139">Receive ASPX Page</span></span>  
 <span data-ttu-id="23558-140">La página de trabajo RNIFReceive.aspx recibe un mensaje HTTP del socio a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="23558-140">The RNIFReceive.aspx page receives an HTTP message from the partner over the Internet.</span></span> <span data-ttu-id="23558-141">Procesa, se valida y, a continuación, quita los encabezados RNIF y envía el mensaje al adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="23558-141">It processes, validates, and then removes the RNIF headers, and submits the message to the HTTP adapter.</span></span> <span data-ttu-id="23558-142">El mensaje recibido por la página de recepción debe ser compatible con el transporte HTTP de RNIF.</span><span class="sxs-lookup"><span data-stu-id="23558-142">The message received by the receive page must be RNIF HTTP transport-compliant.</span></span> <span data-ttu-id="23558-143">La página de recepción procesa los mensajes como sigue:</span><span class="sxs-lookup"><span data-stu-id="23558-143">The receive page processes messages as follows:</span></span>  
  
1.  <span data-ttu-id="23558-144">La página de trabajo RNIFReceive.aspx Respondedor recibe el mensaje del iniciador.</span><span class="sxs-lookup"><span data-stu-id="23558-144">The responder RNIFReceive.aspx page receives the message from the initiator.</span></span> <span data-ttu-id="23558-145">El mensaje contiene el encabezado MIME y los límites superiores e inferiores.</span><span class="sxs-lookup"><span data-stu-id="23558-145">The message contains the MIME header and upper and lower boundaries.</span></span>  
  
2.  <span data-ttu-id="23558-146">La página de recepción valida el encabezado MIME.</span><span class="sxs-lookup"><span data-stu-id="23558-146">The receive page validates the MIME header.</span></span>  
  
3.  <span data-ttu-id="23558-147">La página de recepción quita el encabezado MIME y los límites del mensaje.</span><span class="sxs-lookup"><span data-stu-id="23558-147">The receive page removes the MIME header and boundaries from the message.</span></span>  
  
4.  <span data-ttu-id="23558-148">La página de recepción envía el mensaje al adaptador de HTTP con la ubicación de recepción HTTP.</span><span class="sxs-lookup"><span data-stu-id="23558-148">The receive page posts the message to the HTTP adapter using the HTTP receive location.</span></span> <span data-ttu-id="23558-149">La página de recepción recibe una respuesta HTTP y devuelve la respuesta HTTP a la página de envío del iniciador.</span><span class="sxs-lookup"><span data-stu-id="23558-149">The receive page receives an HTTP response, and returns the HTTP response to the send page of the initiator.</span></span>  
  
5.  <span data-ttu-id="23558-150">Si la conexión es asincrónica, cierra la conexión en la página de recepción.</span><span class="sxs-lookup"><span data-stu-id="23558-150">If the connection is asynchronous, the receive page closes the connection.</span></span>  
  
6.  <span data-ttu-id="23558-151">Si la conexión es sincrónica, la página de recepción mantiene la conexión abierta, esperando un mensaje devuelto.</span><span class="sxs-lookup"><span data-stu-id="23558-151">If the connection is synchronous, the receive page keeps the connection open, waiting for a returned message.</span></span>  
  
7.  <span data-ttu-id="23558-152">Después de recibir el mensaje devuelto desde el adaptador de HTTP, la página recibir el mismo procesamiento que realiza una página RNIFSend.aspx realiza y envía el mensaje devuelto a la página de envío de iniciador.</span><span class="sxs-lookup"><span data-stu-id="23558-152">After it receives the returned message from the HTTP adapter, the receive page performs the same processing that an RNIFSend.aspx page does, and sends the returned message to the initiator send page.</span></span> <span data-ttu-id="23558-153">Después de recibir la respuesta HTTP, cierra la conexión.</span><span class="sxs-lookup"><span data-stu-id="23558-153">After it receives the HTTP response, it closes the connection.</span></span>  
  
## <a name="how-initiator-and-responder-aspx-pages-interact"></a><span data-ttu-id="23558-154">Cómo interactúan las páginas ASPX iniciador y Respondedor</span><span class="sxs-lookup"><span data-stu-id="23558-154">How Initiator and Responder ASPX Pages Interact</span></span>  
 <span data-ttu-id="23558-155">Si usan el iniciador y el Respondedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], las cuatro páginas ASPX en el iniciador y Respondedor interactúan de forma diferente dependiendo de si las conexiones son sincrónicas o asincrónicas, y si los mensajes son acción única o de doble acción .</span><span class="sxs-lookup"><span data-stu-id="23558-155">If both the initiator and the responder use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the four ASPX pages on the initiator and responder interact differently depending on whether the connections are asynchronous or synchronous, and whether the messages are single-action or double-action.</span></span> <span data-ttu-id="23558-156">Las siguientes subsecciones describen el conjunto completo de las interacciones.</span><span class="sxs-lookup"><span data-stu-id="23558-156">The following subsections describe the complete set of interactions.</span></span>  
  
 <span data-ttu-id="23558-157">**Doble acción asincrónica**</span><span class="sxs-lookup"><span data-stu-id="23558-157">**Double-Action Asynchronous**</span></span>  
  
 <span data-ttu-id="23558-158">Este escenario implica cuatro conexiones HTTP independientes, uno para cada paso:</span><span class="sxs-lookup"><span data-stu-id="23558-158">This scenario involves four separate HTTP connections, one for each step:</span></span>  
  
1. <span data-ttu-id="23558-159">Página de recepción de los envíos de página iniciador enviar la solicitud de acción del mensaje para el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="23558-159">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="23558-160">Los pasos 2 y 3 siguiente pueden producirse en el orden inverso, dependiendo de la carga del sistema.</span><span class="sxs-lookup"><span data-stu-id="23558-160">Steps 2 and 3 below may occur in the reverse order, depending upon system load.</span></span>  
  
2. <span data-ttu-id="23558-161">Página de recepción de los envíos de página de servicio de respuesta enviar una señal de solicitud de mensajes al iniciador.</span><span class="sxs-lookup"><span data-stu-id="23558-161">The responder send page sends a request signal message to the initiator receive page.</span></span>  
  
3. <span data-ttu-id="23558-162">Los envíos de página Respondedor enviar una respuesta de acción del mensaje para el iniciador reciben la página.</span><span class="sxs-lookup"><span data-stu-id="23558-162">The responder send page sends an action response message to the initiator receive page.</span></span>  
  
4. <span data-ttu-id="23558-163">Página de recepción de los envíos de página iniciador enviar una señal de respuesta de mensaje para el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="23558-163">The initiator send page sends a response signal message to the responder receive page.</span></span>  
  
   <span data-ttu-id="23558-164">**Acción única asincrónica**</span><span class="sxs-lookup"><span data-stu-id="23558-164">**Single-Action Asynchronous**</span></span>  
  
   <span data-ttu-id="23558-165">Este escenario implica dos conexiones HTTP independientes, uno para cada paso.</span><span class="sxs-lookup"><span data-stu-id="23558-165">This scenario involves two separate HTTP connections, one for each step.</span></span> <span data-ttu-id="23558-166">Tenga en cuenta que este escenario consta de los pasos 1 y 2 del escenario de doble acción asincrónico.</span><span class="sxs-lookup"><span data-stu-id="23558-166">Note that this scenario consists of step 1 and 2 of the double-action asynchronous scenario.</span></span>  
  
5. <span data-ttu-id="23558-167">Página de recepción de los envíos de página iniciador enviar la solicitud de acción del mensaje para el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="23558-167">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
6. <span data-ttu-id="23558-168">Página de recepción de los envíos de página de servicio de respuesta enviar una señal de solicitud de mensajes al iniciador.</span><span class="sxs-lookup"><span data-stu-id="23558-168">The responder send page sends a request signal message to the initiator receive page.</span></span>  
  
   <span data-ttu-id="23558-169">**Doble acción sincrónica**</span><span class="sxs-lookup"><span data-stu-id="23558-169">**Double-Action Synchronous**</span></span>  
  
   <span data-ttu-id="23558-170">Este escenario implica una conexión HTTP:</span><span class="sxs-lookup"><span data-stu-id="23558-170">This scenario involves one HTTP connection:</span></span>  
  
7. <span data-ttu-id="23558-171">Página de recepción de los envíos de página iniciador enviar la solicitud de acción del mensaje para el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="23558-171">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
8. <span data-ttu-id="23558-172">El Respondedor recibe página envía un mensaje de respuesta de acción (o una excepción, si hay un problema) a la página de envío de iniciador en la misma conexión que utilizó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="23558-172">The responder receive page sends an action response message (or an exception, if there is a problem) to the initiator send page on the same connection used in step 1.</span></span>  
  
   <span data-ttu-id="23558-173">**Acción única sincrónica**</span><span class="sxs-lookup"><span data-stu-id="23558-173">**Single-Action Synchronous**</span></span>  
  
   <span data-ttu-id="23558-174">Este escenario implica una conexión HTTP:</span><span class="sxs-lookup"><span data-stu-id="23558-174">This scenario involves one HTTP connection:</span></span>  
  
9. <span data-ttu-id="23558-175">Página de recepción de los envíos de página iniciador enviar la solicitud de acción del mensaje para el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="23558-175">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
10. <span data-ttu-id="23558-176">El Respondedor recibe página envía un mensaje de señal de solicitud (o una excepción, si hay un problema) a la página de envío de iniciador en la misma conexión.</span><span class="sxs-lookup"><span data-stu-id="23558-176">The responder receive page sends a request signal message (or an exception, if there is a problem) to the initiator send page on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23558-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="23558-177">See Also</span></span>  
 <span data-ttu-id="23558-178">[Procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="23558-178">[Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md) </span></span>  
 <span data-ttu-id="23558-179">[Canalización de recepción de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="23558-179">[BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span></span>  
 [<span data-ttu-id="23558-180">Canalización de envío de BTARN</span><span class="sxs-lookup"><span data-stu-id="23558-180">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)