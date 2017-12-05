---
title: "Orquestación FRR | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, promoted properties
- orchestrations, message subscriptions
- promoted properties, messages
- FRR, orchestrations
- subscriptions, messages
- orchestrations, reconciliation time-out
- messages, message/response correlation
- message/response correlation
- promoted properties, FIN Response Reconciliation
- orchestrations, FRR
- outbound messages
- FIN Response Reconciliation, promoted properties
- direct bindings
- reconciliation time-out
- bindings, direct
- messages, subscriptions
- subscriptions, orchestrations
- messages, outbound
- MessageBox database
ms.assetid: ea8d31c2-ac3b-44ac-8064-d008da4f7f72
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f56b16f59b967ccd9e57d03d38f86e64795da477
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="frr-orchestration"></a><span data-ttu-id="3a730-102">Orquestación de FRR</span><span class="sxs-lookup"><span data-stu-id="3a730-102">FRR Orchestration</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-103">implementa FRR a través de la orquestación FRR.</span><span class="sxs-lookup"><span data-stu-id="3a730-103"> implements FRR through the FRR orchestration.</span></span> <span data-ttu-id="3a730-104">La orquestación determina si el Token de correlación de la respuesta FIN coincide con el identificador del mensaje del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="3a730-104">The orchestration determines whether the Correlation Token of the FIN response matches the message ID of the original message.</span></span> <span data-ttu-id="3a730-105">Procesa el mensaje en paralelo con las funciones de envío realizadas por el puerto de envío que envía el mensaje a AAS y con las funciones de recepción realizadas por la ubicación de recepción que recibe el mensaje de AAS.</span><span class="sxs-lookup"><span data-stu-id="3a730-105">It processes the message in parallel with the send functions performed by the send port that sends the message to SAA, and with the receive functions performed by the receive location that receives the message from SAA.</span></span>  
  
 <span data-ttu-id="3a730-106">En el nivel más alto, una instancia de la orquestación realiza el siguiente procesamiento:</span><span class="sxs-lookup"><span data-stu-id="3a730-106">At the highest level, an instance of the orchestration does the following processing:</span></span>  
  
1.  <span data-ttu-id="3a730-107">Las memorias caché una copia del mensaje saliente original enlazado para SAA escuchando en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3a730-107">Caches a copy of the original outbound message bound for SAA by listening on the MessageBox.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3a730-108">crea una instancia de la orquestación cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] enruta el mensaje original en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3a730-108"> creates an instance of the orchestration when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] routes the original message to the MessageBox.</span></span>  
  
2.  <span data-ttu-id="3a730-109">Espera a que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] para publicar una respuesta FIN de SAA en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3a730-109">Waits for [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to publish a FIN response from SAA to the MessageBox.</span></span>  
  
3.  <span data-ttu-id="3a730-110">Establece las propiedades de la copia del mensaje original, dependiendo de la naturaleza de la respuesta FIN promocionadas.</span><span class="sxs-lookup"><span data-stu-id="3a730-110">Sets promoted properties of the copy of the original message depending upon the nature of the FIN response.</span></span>  
  
4.  <span data-ttu-id="3a730-111">Publica el cuadro de mensajes de la copia del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="3a730-111">Publishes the copy of the original message back to the MessageBox.</span></span> <span data-ttu-id="3a730-112">Controladores personalizados, a continuación, pueden suscribirse para recuperar y procesar el mensaje según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3a730-112">Custom handlers can then subscribe to, retrieve, and handle the message as required.</span></span>  
  
## <a name="subscription-to-outbound-messages"></a><span data-ttu-id="3a730-113">Suscripción a los mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="3a730-113">Subscription to Outbound Messages</span></span>  
 <span data-ttu-id="3a730-114">La orquestación FRR se enlaza directamente al cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3a730-114">The FRR orchestration is directly bound to the MessageBox.</span></span> <span data-ttu-id="3a730-115">La orquestación FRR se suscribe a todos los mensajes salientes enlazados para la red SWIFT que no contienen errores de validación, si se suscribe a las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3a730-115">The FRR orchestration subscribes to all outbound messages bound for the SWIFT network that do not contain validation errors, by subscribing to the following properties:</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-116">_Failed == false (según lo establecido por el proceso de validación de SWIFT desensamblador)</span><span class="sxs-lookup"><span data-stu-id="3a730-116">_Failed==False (as set by the SWIFT Disassembler validation process)</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-117">_Swiftbound == true (según lo establecido por el proceso de configuración de SWIFT desensamblador)</span><span class="sxs-lookup"><span data-stu-id="3a730-117">_Swiftbound==True (as set by the SWIFT Disassembler configuration process)</span></span>  
  
## <a name="messageresponse-correlation"></a><span data-ttu-id="3a730-118">Correlación de mensaje de respuesta</span><span class="sxs-lookup"><span data-stu-id="3a730-118">Message/Response Correlation</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3a730-119">Correlaciona el mensaje de FIN de salida original al mensaje de respuesta entrante FINÉS comparando las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3a730-119"> correlates the original outbound FIN message to the inbound FIN response message by comparing the following properties:</span></span>  
  
-   <span data-ttu-id="3a730-120">La propiedad de contexto MQMD_CorrelID de la respuesta FIN</span><span class="sxs-lookup"><span data-stu-id="3a730-120">The MQMD_CorrelID context property of the FIN response</span></span>  
  
-   <span data-ttu-id="3a730-121">El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken propiedad MTXYY del mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="3a730-121">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken property of the outbound MTXYY message.</span></span> <span data-ttu-id="3a730-122">Esta propiedad se promociona la etapa de resolución de entidades de la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="3a730-122">This property is promoted by the party-resolution stage of the receive pipeline.</span></span>  
  
 <span data-ttu-id="3a730-123">Los valores de estas propiedades deben ser idénticos.</span><span class="sxs-lookup"><span data-stu-id="3a730-123">The values of these properties must be identical.</span></span> <span data-ttu-id="3a730-124">La fase de codificador de la canalización de envío para los mensajes enlazados para SWIFT establece la propiedad MQMD_MsgID del mensaje saliente en el valor de la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken propiedad.</span><span class="sxs-lookup"><span data-stu-id="3a730-124">The encoder stage of the send pipeline for messages bound for SWIFT sets the MQMD_MsgID property of the outgoing message to the value of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken property.</span></span> <span data-ttu-id="3a730-125">AAS establece la propiedad MQMD_CorrelID del mensaje de respuesta en el valor de MQMD_MsgID.</span><span class="sxs-lookup"><span data-stu-id="3a730-125">SAA sets the MQMD_CorrelID property of the response message to the value of MQMD_MsgID.</span></span>  
  
## <a name="setting-of-promoted-properties"></a><span data-ttu-id="3a730-126">Configuración de las propiedades promocionadas</span><span class="sxs-lookup"><span data-stu-id="3a730-126">Setting of Promoted Properties</span></span>  
 <span data-ttu-id="3a730-127">Después de recibir una respuesta FIN y correlacionar con la copia del mensaje original, la orquestación FRR establece las siguientes propiedades promocionadas de la copia del mensaje original según la naturaleza de la respuesta:</span><span class="sxs-lookup"><span data-stu-id="3a730-127">After receiving a FIN response and correlating it to the copy of the original message, the FRR orchestration sets the following promoted properties of the copy of the original message according to the nature of the response:</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-128">_FRRFailed en True si la respuesta fue una confirmación o False si la respuesta fue un NAK</span><span class="sxs-lookup"><span data-stu-id="3a730-128">_FRRFailed to True if the response was an ACK or False if the response was a NAK</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-129">_FRRFailedReason a uno de los valores siguientes, si la respuesta fue un NAK:</span><span class="sxs-lookup"><span data-stu-id="3a730-129">_FRRFailedReason to the one of the following values, if the response was a NAK:</span></span>  
  
    -   <span data-ttu-id="3a730-130">*\<ErrorCode\>*  (desde el campo 405 del mensaje de confirmación negativo MTS21_FIN_ACKNAK)</span><span class="sxs-lookup"><span data-stu-id="3a730-130">*\<ErrorCode\>* (from the 405 field of the MTS21_FIN_ACKNAK negative-acknowledgment message)</span></span>  
  
    -   <span data-ttu-id="3a730-131">TransportError (desde un mensaje de MQ Series PAN/NAN)</span><span class="sxs-lookup"><span data-stu-id="3a730-131">TransportError (from an MQ Series PAN/NAN message)</span></span>  
  
    -   <span data-ttu-id="3a730-132">DelayedNAK (de un mensaje MT015 (DIN))</span><span class="sxs-lookup"><span data-stu-id="3a730-132">DelayedNAK (from an MT015 (DNK) message)</span></span>  
  
    -   <span data-ttu-id="3a730-133">AbortReceived (desde un MT019 mensaje (anular la notificación))</span><span class="sxs-lookup"><span data-stu-id="3a730-133">AbortReceived (from an MT019 (Abort Notification) message)</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-134">_FRRFailedReason en tiempo de espera agotado si [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no recibió una respuesta dentro del período de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3a730-134">_FRRFailedReason to TimedOut if [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] did not receive a response within the timeout period.</span></span> <span data-ttu-id="3a730-135">Para obtener más información sobre el tiempo de espera de retraso FRR, vea la sección "Tiempo de espera de conciliación" más adelante o [establecer el tiempo de espera de retraso FRR](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md).</span><span class="sxs-lookup"><span data-stu-id="3a730-135">For more information about the FRR Delay Time-out, see the "Reconciliation Time-Out" section below or [Setting the FRR Delay Time-Out](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md).</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-136">_SendingServiceType a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="3a730-136">_SendingServiceType to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  
  
-   <span data-ttu-id="3a730-137">BTS. Operación para el valor que corresponde al tipo de mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3a730-137">BTS.Operation to the value corresponding to the type of message response.</span></span> <span data-ttu-id="3a730-138">Para obtener más información, consulte [crear los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="3a730-138">For more information, see [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-139">_FrrSendTransport para un mensaje de MQ Series PAN/NAN (confirmación de nivel de transporte MQ Series/NAK)</span><span class="sxs-lookup"><span data-stu-id="3a730-139">_FrrSendTransport for an MQ Series PAN/NAN message (MQ Series transport-level ACK/NAK)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-140">_FrrSend010NDW para un mensaje de MT010 (advertencia de no entrega)</span><span class="sxs-lookup"><span data-stu-id="3a730-140">_FrrSend010NDW for an MT010 message (Non-Delivery Warning)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-141">_FrrSend011Delivered para un mensaje de MT011 (notificación de entrega)</span><span class="sxs-lookup"><span data-stu-id="3a730-141">_FrrSend011Delivered for an MT011 message (Delivery Notification)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-142">_FrrSend012SenderACK para un mensaje de MT012 (notificación de remitente)</span><span class="sxs-lookup"><span data-stu-id="3a730-142">_FrrSend012SenderACK for an MT012 message (Sender Notification)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-143">_FrrSend015DNK para un mensaje de MT015 (DIN o retrasado NAK)</span><span class="sxs-lookup"><span data-stu-id="3a730-143">_FrrSend015DNK for an MT015 message (DNK, or Delayed NAK)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-144">_FrrSend019Abort para un mensaje de MT019 (anular la notificación)</span><span class="sxs-lookup"><span data-stu-id="3a730-144">_FrrSend019Abort for an MT019 message (Abort Notification)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-145">_FrrSendS21ACK para un mensaje de confirmación de MTS21_FIN_ACKNAK (confirmación de un mensaje FIN enviado por un LT)</span><span class="sxs-lookup"><span data-stu-id="3a730-145">_FrrSendS21ACK for an MTS21_FIN_ACKNAK acknowledgment message (ACK of a FIN message sent by an LT)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-146">_FrrSendS21NAK para un mensaje de confirmación negativo MTS21_FIN_ACKNAK (NAK de un mensaje FIN enviado por un LT)</span><span class="sxs-lookup"><span data-stu-id="3a730-146">_FrrSendS21NAK for an MTS21_FIN_ACKNAK negative-acknowledgment message (NAK of a FIN message sent by an LT)</span></span>  
  
## <a name="direct-binding"></a><span data-ttu-id="3a730-147">Enlace directo</span><span class="sxs-lookup"><span data-stu-id="3a730-147">Direct Binding</span></span>  
 <span data-ttu-id="3a730-148">Recibir entradas para la orquestación se definen mediante las suscripciones que hace que la orquestación en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3a730-148">Receive inputs for the orchestration are defined by subscriptions that the orchestration makes to the MessageBox.</span></span> <span data-ttu-id="3a730-149">Propiedades de contexto y los valores que se promueve la orquestación definen las salidas de envío de un mensaje que la orquestación se publica en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3a730-149">Context properties and values promoted by the orchestration define the send outputs for a message that the orchestration publishes to the MessageBox.</span></span> <span data-ttu-id="3a730-150">Debido a este enlace directo en el cuadro de mensajes, la orquestación está desacoplada entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3a730-150">Because of this direct binding to the MessageBox, the orchestration is decoupled from the following:</span></span>  
  
-   <span data-ttu-id="3a730-151">Físico ubicaciones de recepción que reciban mensajes de salida de la aplicación de back-end para el enrutamiento a AAS</span><span class="sxs-lookup"><span data-stu-id="3a730-151">The physical receive locations that receive outbound messages from the back-end application for routing to SAA</span></span>  
  
-   <span data-ttu-id="3a730-152">Mensajes de FIN: los puertos de envío que envía la salida [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] para SWIFT Alliance acceso (AAS)</span><span class="sxs-lookup"><span data-stu-id="3a730-152">The send ports that send outbound FIN messages from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the SWIFT Alliance Access (SAA)</span></span>  
  
-   <span data-ttu-id="3a730-153">Las ubicaciones de recepción que reciben los mensajes entrantes de respuesta FIN de SAA</span><span class="sxs-lookup"><span data-stu-id="3a730-153">The receive locations that receive incoming FIN response messages from SAA</span></span>  
  
-   <span data-ttu-id="3a730-154">Las colas de MQSeries físicas donde depositar AAS respuestas FINÉS</span><span class="sxs-lookup"><span data-stu-id="3a730-154">The physical MQSeries queues where FIN responses are deposited by SAA</span></span>  
  
## <a name="reconciliation-time-out"></a><span data-ttu-id="3a730-155">Tiempo de espera de conciliación</span><span class="sxs-lookup"><span data-stu-id="3a730-155">Reconciliation Time-Out</span></span>  
 <span data-ttu-id="3a730-156">Cuando [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] crea una nueva instancia de la orquestación FRR, iniciar la orquestación espera para las respuestas FIN.</span><span class="sxs-lookup"><span data-stu-id="3a730-156">When [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] creates a new instance of the FRR orchestration, the orchestration starts waiting for FIN responses.</span></span> <span data-ttu-id="3a730-157">En tiempo de ejecución, debe configurar la orquestación en tiempo de espera después de algún tiempo, por lo que no esperará la respuesta indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="3a730-157">At run time, you must configure the orchestration to time out after some duration, so that it will not wait for the response indefinitely.</span></span> <span data-ttu-id="3a730-158">Cuando la duración de tiempo de espera expira, la orquestación FRR promociona el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason propiedad y lo establece en tiempo de espera agotado.</span><span class="sxs-lookup"><span data-stu-id="3a730-158">When the time-out duration expires, the FRR orchestration promotes the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason property and sets it to TimedOut.</span></span> <span data-ttu-id="3a730-159">A continuación, publica mensajes de salida en el cuadro de mensajes y finaliza.</span><span class="sxs-lookup"><span data-stu-id="3a730-159">It then publishes messages out to the MessageBox, and terminates.</span></span> <span data-ttu-id="3a730-160">Si el tiempo de espera, el identificador de correlación ya no existe.</span><span class="sxs-lookup"><span data-stu-id="3a730-160">If you time out, the correlation ID is gone.</span></span>  
  
 <span data-ttu-id="3a730-161">Puede crear un controlador personalizado para procesar mensajes que ha superado el tiempo de espera (la copia del mensaje saliente original).</span><span class="sxs-lookup"><span data-stu-id="3a730-161">You can create a custom handler to process timed-out messages (the copy of the original outbound message).</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3a730-162">hacerlo mediante el uso de una forma escuchar en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="3a730-162"> would accomplish this by using a Listen shape in the orchestration.</span></span> <span data-ttu-id="3a730-163">Para obtener más información, consulte [establecer el tiempo de espera de retraso FRR](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md).</span><span class="sxs-lookup"><span data-stu-id="3a730-163">For more information, see [Setting the FRR Delay Time-Out](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md).</span></span>