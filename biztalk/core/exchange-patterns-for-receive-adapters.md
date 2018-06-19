---
title: Patrones de intercambio para adaptadores de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e505559e-66be-4c32-a2a8-a242cba10000
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cf8f36bb128d82a6d6b2e143320f89408f26680
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246300"
---
# <a name="exchange-patterns-for-receive-adapters"></a><span data-ttu-id="d773a-102">Intercambiar patrones para adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="d773a-102">Exchange Patterns for Receive Adapters</span></span>
<span data-ttu-id="d773a-103">Recepción adaptadores de recepción de datos de "cable" y enviarla como un mensaje en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d773a-103">Receive adapters receive data from the "wire" and submit it as a message into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d773a-104">Este proceso de envío puede ser un patrón de intercambio de mensajes unidireccional o bidireccional.</span><span class="sxs-lookup"><span data-stu-id="d773a-104">This submittal process can be a one-way or a two-way message exchange pattern.</span></span>  
  
## <a name="one-way-submit"></a><span data-ttu-id="d773a-105">Envío unidireccional</span><span class="sxs-lookup"><span data-stu-id="d773a-105">One-Way Submit</span></span>  
 <span data-ttu-id="d773a-106">Para que un adaptador de recepción envíe un mensaje al motor de mensajería de BizTalk, primero será necesario crear un mensaje de BizTalk nuevo.</span><span class="sxs-lookup"><span data-stu-id="d773a-106">For a receive adapter to submit a message into the BizTalk Messaging Engine, it first needs to create a new BizTalk message.</span></span> <span data-ttu-id="d773a-107">El ejemplo de código del tema IBaseMessage muestra cómo se ha realizado.</span><span class="sxs-lookup"><span data-stu-id="d773a-107">The code sample in the IBaseMessage topic shows how this is done.</span></span> <span data-ttu-id="d773a-108">La secuencia que el adaptador define como cuerpo del mensaje debe ser normalmente una secuencia progresiva, lo que significa que no debe almacenar en caché los datos que se han leído previamente en la memoria.</span><span class="sxs-lookup"><span data-stu-id="d773a-108">The stream that the adapter sets as the message body should typically be a forward-only stream, meaning that it should not cache the data that it has previously read into memory.</span></span>  
  
 <span data-ttu-id="d773a-109">Antes de que el adaptador envía el mensaje al motor, debe escribir el **InboundTransportLocation** message (propiedad) contexto en el espacio de nombres del sistema en el mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d773a-109">Before the adapter submits the message into the engine, it must write the **InboundTransportLocation** message context property in the system namespace onto the BizTalk message.</span></span> <span data-ttu-id="d773a-110">Esto se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="d773a-110">This is illustrated in the following code fragment:</span></span>  
  
 `Assembly References:`  
  
 `Microsoft.XLANGs.BaseTypes.dll`  
  
 `Microsoft.BizTalk.Pipeline.dll`  
  
 `Microsoft.BizTalk.GlobalPropertySchemas.dll`  
  
```  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.XLANGs.BaseTypes;  
  
private static readonly PropertyBase InboundTransportLocationProp =   
new BTS.InboundTransportLocation();  
  
private void StampMsgCtxProps(  
IBaseMessage msg, string uri, string adapterType)  
{  
msg.Context.Write(  
 InboundTransportLocationProp.Name.Name,   
 InboundTransportLocationProperty.Name.Namespace,   
  uri);  
}  
```  
  
 <span data-ttu-id="d773a-111">Además, es posible que el adaptador defina sus propios esquemas de propiedades y escriba las propiedades del contexto del mensaje relacionadas con el extremo sobre el que se ha recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d773a-111">In addition, the adapter may define its own property schemas and write message context properties pertaining to the endpoint over which it received the message.</span></span> <span data-ttu-id="d773a-112">Por ejemplo, un adaptador de HTTP podría escribir los encabezados HTTP en el contexto del mensaje y un receptor SMTP podría escribir el asunto del correo electrónico en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d773a-112">For example, an HTTP adapter might write the HTTP headers to the message context, and an SMTP receiver might write the subject of the mail to the message context.</span></span> <span data-ttu-id="d773a-113">Esta información puede ser útil para componentes de nivel inferior, como componentes de canalización, programación de orquestación o un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="d773a-113">This information may be useful to downstream components such as pipeline components, orchestration schedules, or a send adapter.</span></span>  
  
 <span data-ttu-id="d773a-114">Una vez que se preparen los mensajes, se pueden enviar al motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="d773a-114">After the messages are prepared, they can be submitted into the Messaging Engine.</span></span> <span data-ttu-id="d773a-115">Para ver cómo un adaptador de recepción unidireccional puede enviar un mensaje al motor, vea el ejemplo de código [SubmitDirect (ejemplo de BizTalk Server)](../core/submitdirect-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="d773a-115">To see how a one-way receive adapter might submit a message into the engine, see the code sample [SubmitDirect (BizTalk Server Sample)](../core/submitdirect-biztalk-server-sample.md).</span></span>  
  
## <a name="request-response"></a><span data-ttu-id="d773a-116">Solicitudes y respuestas</span><span class="sxs-lookup"><span data-stu-id="d773a-116">Request-Response</span></span>  
 <span data-ttu-id="d773a-117">Los adaptadores de recepción bidireccionales se utilizan, por lo general, en puertos de recepción unidireccionales o bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="d773a-117">Two-way receive adapters are typically used on one-way or two-way receive ports.</span></span> <span data-ttu-id="d773a-118">El adaptador determina si la ubicación de recepción que proporciona el servicio es un puerto unidireccional o bidireccional inspeccionando el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bolsa de propiedades.</span><span class="sxs-lookup"><span data-stu-id="d773a-118">The adapter determines whether the receive location it is servicing is a one-way or two-way port by inspecting the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration property bag.</span></span> <span data-ttu-id="d773a-119">Este proceso se explica en la **IBTTransportConfig.AddReceiveEndpoint (método) (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="d773a-119">This process is explained in the **IBTTransportConfig.AddReceiveEndpoint Method (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="d773a-120">El diagrama de interacción de objetos muestra el proceso de realización de un intercambio de mensajes solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="d773a-120">The following object interaction diagram illustrates the process of performing a request-response message exchange.</span></span> <span data-ttu-id="d773a-121">El adaptador solicita un nuevo lote del proxy de transporte y pasa su referencia a la **IBTTransmitter** interfaz a través de la **SubmitRequestMessage** método.</span><span class="sxs-lookup"><span data-stu-id="d773a-121">The adapter requests a new batch from the transport proxy and passes in its reference to the **IBTTransmitter** interface through the **SubmitRequestMessage** method.</span></span> <span data-ttu-id="d773a-122">El motor de mensajería entrega el mensaje de respuesta en esta interfaz mediante la **TransmitMessage** método.</span><span class="sxs-lookup"><span data-stu-id="d773a-122">The Messaging Engine delivers the response message on this interface by using the **TransmitMessage** method.</span></span>  
  
 <span data-ttu-id="d773a-123">Puesto que el motor está procesando mensajes de forma asincrónica, es posible que suceda lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d773a-123">Because the engine is processing messages asynchronously, it is possible for the following to happen:</span></span>  
  
-   <span data-ttu-id="d773a-124">El **BatchComplete** devolución de llamada puede producirse antes de **realiza** ha devuelto.</span><span class="sxs-lookup"><span data-stu-id="d773a-124">The **BatchComplete** callback might occur before **Done** has returned.</span></span>  
  
-   <span data-ttu-id="d773a-125">Es posible que la llamada a TransmitMessage se realice antes que BatchComplete, e incluso antes que Done.</span><span class="sxs-lookup"><span data-stu-id="d773a-125">The call to TransmitMessage might be made before BatchComplete and even before Done.</span></span>  
  
 <span data-ttu-id="d773a-126">Aunque ambos escenarios son extraños, el adaptador debe protegerse contra esto.</span><span class="sxs-lookup"><span data-stu-id="d773a-126">While both of these scenarios are rare, the adapter should protect itself against this.</span></span>  
  
 <span data-ttu-id="d773a-127">Se recomienda que el mensaje de respuesta se transmita mediante una llamada asincrónica sin bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d773a-127">It is recommended that the response message is transmitted using an asynchronous non-blocking call.</span></span>  
  
 <span data-ttu-id="d773a-128">El proyecto BaseAdapter tiene una clase de utilidad, **StandardRequestResponseHandler**, que encapsula la semántica de solicitud-respuesta explicada en este tema.</span><span class="sxs-lookup"><span data-stu-id="d773a-128">The BaseAdapter project has a utility class, **StandardRequestResponseHandler**, that encapsulates the request-response semantics explained in this topic.</span></span>  
  
## <a name="request-response-message-time-outs"></a><span data-ttu-id="d773a-129">Tiempos de espera de mensaje de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="d773a-129">Request-Response Message Time-Outs</span></span>  
 <span data-ttu-id="d773a-130">Cuando un adaptador envía un mensaje de solicitud de la solicitud, es necesario especificar el tiempo de espera del mensaje de solicitud en el **IBTTransportBatch.SubmitRequestMessage (método) (COM)** API [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="d773a-130">When an adapter submits a request-request message, it needs to specify the time-out of the request message on the **IBTTransportBatch.SubmitRequestMessage Method (COM)** API [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="d773a-131">Se entregará un mensaje de respuesta al adaptador únicamente dentro del período de espera.</span><span class="sxs-lookup"><span data-stu-id="d773a-131">A response message will be delivered to the adapter only within this time-out period.</span></span> <span data-ttu-id="d773a-132">Después de que el tiempo de espera se agote, se entregará una confirmación negativa (NACK) al adaptador en lugar del mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d773a-132">After the time-out expires, a negative acknowledgment (NACK) will be delivered to the adapter instead of the response message.</span></span> <span data-ttu-id="d773a-133">Si el adaptador no especifica un valor de tiempo de espera, el motor utiliza el valor predeterminado de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="d773a-133">If the adapter does not specify a time-out value, the engine uses the default value of 20 minutes.</span></span>  
  
 <span data-ttu-id="d773a-134">El tiempo de espera predeterminado para mensajes de solicitud-respuesta puede controlarse mediante la utilización de la siguiente clave del Registro para adaptadores de recepción de tipo En curso:</span><span class="sxs-lookup"><span data-stu-id="d773a-134">The default time-out for request-response messages may be controlled by using the following registry key for in-process receive adapters:</span></span>  
  
 <span data-ttu-id="d773a-135">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="d773a-135">**DWORD**</span></span>  
  
 <span data-ttu-id="d773a-136">**\MessagingReqRespTTL HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {Guid de Host}**</span><span class="sxs-lookup"><span data-stu-id="d773a-136">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingReqRespTTL**</span></span>  
  
 <span data-ttu-id="d773a-137">La clave del Registro está en una ubicación diferente para adaptadores de recepción aislados:</span><span class="sxs-lookup"><span data-stu-id="d773a-137">The registry key is in a different location for isolated receive adapters:</span></span>  
  
 <span data-ttu-id="d773a-138">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="d773a-138">**DWORD**</span></span>  
  
 <span data-ttu-id="d773a-139">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**</span><span class="sxs-lookup"><span data-stu-id="d773a-139">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**</span></span>  
  
 <span data-ttu-id="d773a-140">NACK (confirmaciones negativas) son errores SOAP y existen dos modos de controlarlos.</span><span class="sxs-lookup"><span data-stu-id="d773a-140">NACKs (Negative ACKnowledgements) are SOAP faults and there are two ways to handle them.</span></span> <span data-ttu-id="d773a-141">Por lo general, el adaptador devuelve NACK al cliente y el cliente controla NACK.</span><span class="sxs-lookup"><span data-stu-id="d773a-141">Typically the adapter returns the NACK to the client and the client handles the NACK.</span></span> <span data-ttu-id="d773a-142">De forma alternativa, puede que la canalización de transmisión que controla el mensaje de respuesta se configure para cambiar el contenido del mensaje de respuesta mediante de la utilización de una asignación o de un componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="d773a-142">Alternatively the transmit pipeline handling the response message may be configured to change the contents of the response message, by using either a map or a custom pipeline component.</span></span>