---
title: Patrones de intercambio para adaptadores de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ad65fb5-640d-4bd2-aabe-946210f58a22
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4cef519e4648814e1636daac7b60a42addf5111
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978373"
---
# <a name="exchange-patterns-for-send-adapters"></a><span data-ttu-id="fad5a-102">Patrones de intercambio para adaptadores de envío</span><span class="sxs-lookup"><span data-stu-id="fad5a-102">Exchange Patterns for Send Adapters</span></span>
<span data-ttu-id="fad5a-103">Los adaptadores de envío son mensajes entregados desde el motor de mensajería de BizTalk cuya transmisión debe efectuarse a través de la red.</span><span class="sxs-lookup"><span data-stu-id="fad5a-103">Send adapters are delivered messages from the BizTalk Messaging Engine to be transmitted over the wire.</span></span> <span data-ttu-id="fad5a-104">Estos mensajes pueden enviarse mediante un patrón de intercambio de mensajes bidireccional o unidireccional.</span><span class="sxs-lookup"><span data-stu-id="fad5a-104">These messages may be sent by using a one-way or two-way message exchange pattern.</span></span> <span data-ttu-id="fad5a-105">Un adaptador que controla este patrón de intercambio de mensajes bidireccional se conoce como adaptador de petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="fad5a-105">An adapter that handles this two-way message exchange pattern is called a Solicit-Response adapter.</span></span>  

## <a name="blocking-vs-non-blocking-transmissions"></a><span data-ttu-id="fad5a-106">Bloqueo de vs. Transmisiones de no bloqueo</span><span class="sxs-lookup"><span data-stu-id="fad5a-106">Blocking vs. Non-Blocking Transmissions</span></span>  
 <span data-ttu-id="fad5a-107">El motor de mensajería entrega mensajes al adaptador de envío mediante el uso del **IBTTransmitter.TransmitMessage** método o la **IBTTransmitterBatch.TransmitMessage** método, dependiendo de si el adaptador es compatible con lotes.</span><span class="sxs-lookup"><span data-stu-id="fad5a-107">The Messaging Engine delivers messages to the send adapter by using either the **IBTTransmitter.TransmitMessage** method or the **IBTTransmitterBatch.TransmitMessage** method, depending on whether the adapter is batch-aware.</span></span> <span data-ttu-id="fad5a-108">Ambas versiones del método tienen un valor de devolución booleano que indica el modo en el que el adaptador efectúa la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fad5a-108">Both versions of the method have a Boolean return value that indicates how the adapter transmitted the message.</span></span> <span data-ttu-id="fad5a-109">Si el adaptador devuelve `true`, completamente envió el mensaje antes de devolver.</span><span class="sxs-lookup"><span data-stu-id="fad5a-109">If the adapter returns `true`, it has completely sent the message before returning.</span></span> <span data-ttu-id="fad5a-110">En este caso, el motor de mensajería elimina el mensaje de la base de datos de cuadro de mensajes en nombre del adaptador.</span><span class="sxs-lookup"><span data-stu-id="fad5a-110">In this case the Messaging Engine deletes the message from the MessageBox database on behalf of the adapter.</span></span> <span data-ttu-id="fad5a-111">Si el adaptador devuelve `false`, se inicia la transmisión del mensaje y devuelve antes de completar la transmisión.</span><span class="sxs-lookup"><span data-stu-id="fad5a-111">If the adapter returns `false`, it started message transmission and returned before the transmission completed.</span></span> <span data-ttu-id="fad5a-112">En este caso, el adaptador no es solo responsable de la eliminación del mensaje de la cola de aplicación correspondiente, sino también del control de errores de transmisión que requiere volver a intentar la transmisión o suspensión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fad5a-112">In this case, the adapter is responsible not only for deleting the message from its application queue but also for handling transmission failures that require the message to be retried for transmission or suspended.</span></span>  

 <span data-ttu-id="fad5a-113">El adaptador devuelve `false` es una llamada de no bloqueo, lo que significa que el **TransmitMessage** código de implementación no bloquea el subproceso de llamada del motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="fad5a-113">The adapter returning `false` is a nonblocking call, meaning that the **TransmitMessage** implementation code does not block the calling thread of the Messaging Engine.</span></span> <span data-ttu-id="fad5a-114">El adaptador tan solo agrega el mensaje a una cola en memoria, preparado para su transmisión y, seguidamente, efectúa su devolución.</span><span class="sxs-lookup"><span data-stu-id="fad5a-114">The adapter simply adds the message to an in-memory queue ready to be transmitted and then returns.</span></span> <span data-ttu-id="fad5a-115">El adaptador debería tener su propio grupo de subprocesos para efectuar la entrega de la cola en memoria, la transmisión del mensaje y, a continuación, la notificación al motor de la salida de la transmisión.</span><span class="sxs-lookup"><span data-stu-id="fad5a-115">The adapter should have its own thread pool that services the in-memory queue, transmits the message, and then notifies the engine of the outcome of the transmission.</span></span>  

 <span data-ttu-id="fad5a-116">Por lo general, los subprocesos del motor de mensajería están más enlazados a la CPU que los subprocesos que se utilizan para enviar datos a través de la red.</span><span class="sxs-lookup"><span data-stu-id="fad5a-116">The Messaging Engine’s threads are typically more CPU bound than the threads used to send data over the wire.</span></span> <span data-ttu-id="fad5a-117">La combinación de estos dos tipos de subprocesos tiene un impacto negativo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fad5a-117">Mixing these two types of threads has a negative impact on performance.</span></span> <span data-ttu-id="fad5a-118">Los envíos de no bloqueo permiten separar estos dos tipos de subprocesos y mejorar considerablemente el rendimiento con respecto a las llamadas de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fad5a-118">Non-blocking sends enable the decoupling of these two types of threads and yield a significant performance improvement over blocking calls.</span></span>  

 <span data-ttu-id="fad5a-119">En el siguiente diagrama, se muestra el grupo de subprocesos del adaptador que, posiblemente, las operaciones E/S tiendan a enlazar.</span><span class="sxs-lookup"><span data-stu-id="fad5a-119">The following diagram shows the adapter's thread pool which can tend to be bound by I/O operations.</span></span> <span data-ttu-id="fad5a-120">El enlace del grupo de subprocesos del motor de mensajería de BizTalk Server está más relacionado con el procesamiento de la CPU.</span><span class="sxs-lookup"><span data-stu-id="fad5a-120">The BizTalk Server Messaging Engine's thread pool is more bound by the CPU processing.</span></span> <span data-ttu-id="fad5a-121">El sistema funciona de forma más eficaz al conservar dos grupos de subprocesos distintos sin mezclar el mismo tipo de subproceso.</span><span class="sxs-lookup"><span data-stu-id="fad5a-121">By keeping two different thread pools and not mixing the same type of threads the system can operate more efficiently.</span></span>  

 <span data-ttu-id="fad5a-122">![](../core/media/io-cpu-bound-threadpools.gif "Io_cpu_bound_threadpools")</span><span class="sxs-lookup"><span data-stu-id="fad5a-122">![](../core/media/io-cpu-bound-threadpools.gif "Io_cpu_bound_threadpools")</span></span>  

 <span data-ttu-id="fad5a-123">**Consejo de rendimiento:** para optimizar el rendimiento, enviar adaptadores deben ser sin bloqueo y con lotes.</span><span class="sxs-lookup"><span data-stu-id="fad5a-123">**Performance Tip:** For the best performance, send adapters should be nonblocking and batch aware.</span></span> <span data-ttu-id="fad5a-124">Cuando se cambia el carácter de bloqueo y la incompatibilidad con lotes del adaptador de archivo de BizTalk al carácter de no bloqueo y de compatibilidad con lotes, se obtiene una mejora del rendimiento en tres aspectos.</span><span class="sxs-lookup"><span data-stu-id="fad5a-124">When the BizTalk File adapter was changed from blocking and non-batch aware to nonblocking and batch aware, a threefold performance gain was realized.</span></span>  

 <span data-ttu-id="fad5a-125">**Sugerencia de solución de problemas:** transmite el bloqueo puede causar una degradación del rendimiento de una instancia de host completo.</span><span class="sxs-lookup"><span data-stu-id="fad5a-125">**Troubleshooting Tip:** Blocking transmits can cause a performance degradation of an entire host instance.</span></span> <span data-ttu-id="fad5a-126">Si el adaptador efectúa un bloqueo excesivo **TransmitMessage** impedirá que los subprocesos del motor de entrega de mensajes a otros adaptadores.</span><span class="sxs-lookup"><span data-stu-id="fad5a-126">If the adapter does excessive blocking in **TransmitMessage** it will prevent engine threads from delivering messages to other adapters.</span></span>  

## <a name="non-batched-sends"></a><span data-ttu-id="fad5a-127">Envíos no compatibles con lotes</span><span class="sxs-lookup"><span data-stu-id="fad5a-127">Non-Batched Sends</span></span>  
 <span data-ttu-id="fad5a-128">Los adaptadores que no son compatibles con lotes deberían implementar **IBTTransmitter** tal como se detalla en [Interfaces para un adaptador de envío asincrónico](../core/interfaces-for-an-asynchronous-send-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="fad5a-128">Adapters that are not batch aware should implement **IBTTransmitter** as detailed in [Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md).</span></span> <span data-ttu-id="fad5a-129">Para cada mensaje que el adaptador necesita transmitir el motor de mensajería llama **IBTTransmitter.TransmitMessage**.</span><span class="sxs-lookup"><span data-stu-id="fad5a-129">For each message that the adapter needs to transmit the Messaging Engine calls **IBTTransmitter.TransmitMessage**.</span></span> <span data-ttu-id="fad5a-130">En el diagrama de interacción de objetos que se muestra a continuación, se ilustra el enfoque habitual para la transmisión de mensajes, que consta de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fad5a-130">The object interaction diagram below details the typical approach for transmitting messages, which consists of the following steps:</span></span>  

1. <span data-ttu-id="fad5a-131">El motor entrega el mensaje al adaptador.</span><span class="sxs-lookup"><span data-stu-id="fad5a-131">The engine delivers the message to the adapter.</span></span>  

2. <span data-ttu-id="fad5a-132">El adaptador coloca el mensaje en una cola en memoria, preparado para su transmisión.</span><span class="sxs-lookup"><span data-stu-id="fad5a-132">The adapter enqueues the message to an in-memory queue ready to be transmitted.</span></span>  

3. <span data-ttu-id="fad5a-133">Un subproceso del grupo de subprocesos del adaptador quita el mensaje de la cola, lee la configuración que le corresponde a éste y lo transmite a través de la red.</span><span class="sxs-lookup"><span data-stu-id="fad5a-133">A thread from the adapter's thread pool dequeues the message from the queue, reads the configuration for the message, and transmits the message over the wire.</span></span>  

4. <span data-ttu-id="fad5a-134">El adaptador obtiene un nuevo lote del motor.</span><span class="sxs-lookup"><span data-stu-id="fad5a-134">The adapter gets a new batch from the engine.</span></span>  

5. <span data-ttu-id="fad5a-135">El adaptador llama a **DeleteMessage** en el lote, pasa el mensaje recién transmitido.</span><span class="sxs-lookup"><span data-stu-id="fad5a-135">The adapter calls **DeleteMessage** on the batch, passing in the message that it has just transmitted.</span></span>  

6. <span data-ttu-id="fad5a-136">El adaptador llama a **realiza** en el lote.</span><span class="sxs-lookup"><span data-stu-id="fad5a-136">The adapter calls **Done** on the batch.</span></span>  

7. <span data-ttu-id="fad5a-137">El motor procesa el lote y elimina el mensaje de la cola de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad5a-137">The engine processes the batch and deletes the message from the application queue.</span></span>  

8. <span data-ttu-id="fad5a-138">El motor llama al adaptador para notificarle el resultado de la **DeleteMessage** operación.</span><span class="sxs-lookup"><span data-stu-id="fad5a-138">The engine calls back the adapter to notify it of the outcome of the **DeleteMessage** operation.</span></span>  

   <span data-ttu-id="fad5a-139">![](../core/media/deleting-from-message-queue.gif "Deleting_from_message_queue")</span><span class="sxs-lookup"><span data-stu-id="fad5a-139">![](../core/media/deleting-from-message-queue.gif "Deleting_from_message_queue")</span></span>  

   <span data-ttu-id="fad5a-140">El diagrama de interacción de objetos anterior muestra la eliminación que lleva a cabo el adaptador de un solo mensaje de la cola de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad5a-140">The preceding object interaction diagram shows the adapter deleting a single message from the application queue.</span></span> <span data-ttu-id="fad5a-141">Idealmente, el adaptador procesa por lotes operaciones de mensaje, lo que se opone al funcionamiento con un solo mensaje cada vez.</span><span class="sxs-lookup"><span data-stu-id="fad5a-141">Ideally the adapter batches up message operations as opposed to operating on a single message at a time.</span></span>  

## <a name="batched-sends"></a><span data-ttu-id="fad5a-142">Envíos compatibles con lotes</span><span class="sxs-lookup"><span data-stu-id="fad5a-142">Batched Sends</span></span>  
 <span data-ttu-id="fad5a-143">Los adaptadores que son compatibles con lotes deberían implementar **IBTBatchTransmitter** y **IBTTransmitterBatch** tal como se detalla en [Interfaces de adaptadores de envío de](../core/interfaces-for-send-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="fad5a-143">Adapters that are batch aware should implement **IBTBatchTransmitter** and **IBTTransmitterBatch** as detailed in [Interfaces for Send Adapters](../core/interfaces-for-send-adapters.md).</span></span> <span data-ttu-id="fad5a-144">Cuando el motor tiene mensajes para el adaptador los transmita, el motor Obtiene un nuevo lote del adaptador mediante una llamada a **IBTBatchTransmitter.GetBatch**.</span><span class="sxs-lookup"><span data-stu-id="fad5a-144">When the engine has messages for the adapter to transmit, the engine gets a new batch from the adapter by calling **IBTBatchTransmitter.GetBatch**.</span></span> <span data-ttu-id="fad5a-145">El adaptador devuelve un nuevo objeto de lote que implementa **IBTTransmitterBatch**.</span><span class="sxs-lookup"><span data-stu-id="fad5a-145">The adapter returns a new batch object that implements **IBTTransmitterBatch**.</span></span> <span data-ttu-id="fad5a-146">El motor, a continuación, inicia el lote mediante una llamada **IBTTransmitterBatch.BeginBatch**.</span><span class="sxs-lookup"><span data-stu-id="fad5a-146">The engine then starts the batch by calling **IBTTransmitterBatch.BeginBatch**.</span></span> <span data-ttu-id="fad5a-147">La API dispone de un parámetro de salida que permite que el adaptador especifique el número máximo de mensajes que se aceptará en el lote.</span><span class="sxs-lookup"><span data-stu-id="fad5a-147">This API has an out parameter that allows the adapter to specify the maximum number of messages that it will accept on the batch.</span></span> <span data-ttu-id="fad5a-148">De forma opcional, el adaptador puede devolver una transacción de DTC.</span><span class="sxs-lookup"><span data-stu-id="fad5a-148">The adapter may optionally return a DTC transaction.</span></span> <span data-ttu-id="fad5a-149">El motor llama **IBTTransmitterBatch.TransmitMessage** una vez para cada mensaje saliente a agregarse al lote.</span><span class="sxs-lookup"><span data-stu-id="fad5a-149">The engine then calls **IBTTransmitterBatch.TransmitMessage** once for each outgoing message to be added to the batch.</span></span> <span data-ttu-id="fad5a-150">El número de veces que se efectúa esta llamada es superior a 0 pero inferior o igual al tamaño máximo del lote, tal y como lo indica el adaptador.</span><span class="sxs-lookup"><span data-stu-id="fad5a-150">The number of times this is called is greater than zero but less than or equal to the maximum size of the batch as indicated by the adapter.</span></span> <span data-ttu-id="fad5a-151">Todos los mensajes se han agregado al lote, el adaptador llama a **IBTTransmitterBatch.Done**.</span><span class="sxs-lookup"><span data-stu-id="fad5a-151">When all the messages have been added to the batch, the adapter calls **IBTTransmitterBatch.Done**.</span></span> <span data-ttu-id="fad5a-152">En este punto, por lo general, el adaptador coloca todos los mensajes del lote en la cola en memoria correspondiente.</span><span class="sxs-lookup"><span data-stu-id="fad5a-152">At this point the adapter typically enqueues all the messages in the batch to its in-memory queue.</span></span> <span data-ttu-id="fad5a-153">El adaptador transmite los mensajes a partir de uno o varios subprocesos de su propio grupo de subprocesos, como en el caso de adaptadores no compatibles con lotes.</span><span class="sxs-lookup"><span data-stu-id="fad5a-153">The adapter transmits the messages from a thread or threads in its own thread pool as in the case of non-batch-aware adapters.</span></span> <span data-ttu-id="fad5a-154">Después, el adaptador notifica al motor del resultado de la transmisión.</span><span class="sxs-lookup"><span data-stu-id="fad5a-154">The adapter then notifies the engine of the outcome of the transmission.</span></span>  

 <span data-ttu-id="fad5a-155">En el diagrama de interacción de objetos que se muestra a continuación, se ilustra la transmisión que efectúa un adaptador de envío por lotes de dos mensajes.</span><span class="sxs-lookup"><span data-stu-id="fad5a-155">The following object interaction diagram illustrates the transmission of two messages by a batched send adapter.</span></span>  

 <span data-ttu-id="fad5a-156">![](../core/media/batchedsends.gif "BatchedSends")</span><span class="sxs-lookup"><span data-stu-id="fad5a-156">![](../core/media/batchedsends.gif "BatchedSends")</span></span>  

## <a name="handling-transmission-failures"></a><span data-ttu-id="fad5a-157">Controlar errores de transmisión</span><span class="sxs-lookup"><span data-stu-id="fad5a-157">Handling Transmission Failures</span></span>  
 <span data-ttu-id="fad5a-158">En la ilustración siguiente, se ilustra la semántica recomendada para los errores de transmisión.</span><span class="sxs-lookup"><span data-stu-id="fad5a-158">The recommended semantics for transmission failures are illustrated in the figure below.</span></span> <span data-ttu-id="fad5a-159">Se trata únicamente de recomendaciones que no impone el motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="fad5a-159">These are only recommendations and are not enforced by the Messaging Engine.</span></span> <span data-ttu-id="fad5a-160">Se puede desarrollar un adaptador que difiera de estas directrices si hay razones válidas para ello, aunque se debe tener especial cuidado en ese caso.</span><span class="sxs-lookup"><span data-stu-id="fad5a-160">You can develop an adapter that deviates from these guidelines if there are valid reasons for doing so but you should be careful in this case.</span></span> <span data-ttu-id="fad5a-161">Por ejemplo, en términos generales, un adaptador siempre debe mover mensajes al transporte de reserva una vez agotados todos los reintentos.</span><span class="sxs-lookup"><span data-stu-id="fad5a-161">For example, in general an adapter should always move messages to the backup transport after all retries have been exhausted.</span></span>  

 <span data-ttu-id="fad5a-162">Lo más habitual es que un transporte necesite efectuar un número de reintentos superior al que establece la configuración.</span><span class="sxs-lookup"><span data-stu-id="fad5a-162">More commonly a transport may need to use more retries than are configured.</span></span> <span data-ttu-id="fad5a-163">Aunque esta situación es ligeramente distinta, se considera aceptable porque se aumenta la capacidad de recuperación de la capa de transporte.</span><span class="sxs-lookup"><span data-stu-id="fad5a-163">While this is slightly different it is considered acceptable because the resilience of the transport layer is being increased.</span></span> <span data-ttu-id="fad5a-164">En general, las API que expone el motor de mensajería están diseñadas para ofrecer al adaptador el control máximo allí donde sea posible.</span><span class="sxs-lookup"><span data-stu-id="fad5a-164">In general the APIs exposed by the Messaging Engine are designed to give the adapter maximum control where possible.</span></span> <span data-ttu-id="fad5a-165">Este control conlleva un nivel más alto de responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="fad5a-165">With this control comes a greater level of responsibility.</span></span>  

 <span data-ttu-id="fad5a-166">![](../core/media/handlingerrors.gif "HandlingErrors")</span><span class="sxs-lookup"><span data-stu-id="fad5a-166">![](../core/media/handlingerrors.gif "HandlingErrors")</span></span>  

 <span data-ttu-id="fad5a-167">El adaptador determina el número de reintentos disponibles en un mensaje mediante la comprobación de la propiedad de contexto del sistema **RetryCount**.</span><span class="sxs-lookup"><span data-stu-id="fad5a-167">The adapter determines the number of retries available on a message by checking the system context property **RetryCount**.</span></span> <span data-ttu-id="fad5a-168">El adaptador llama a la **reenviar** API una vez para cada reintento intento y pasa el mensaje que se va a reenviar.</span><span class="sxs-lookup"><span data-stu-id="fad5a-168">The adapter calls the **Resubmit** API once for each retry attempt and passes in the message to be resubmitted.</span></span> <span data-ttu-id="fad5a-169">Además del mensaje, pasa la marca de tiempo que indica el momento en el que debe volver a entregarse el mensaje al adaptador.</span><span class="sxs-lookup"><span data-stu-id="fad5a-169">Along with the message it passes the time stamp indicating when the engine should deliver the message back to the adapter.</span></span> <span data-ttu-id="fad5a-170">Este valor debe ser normalmente la hora actual más el valor de **RetryInterval**.</span><span class="sxs-lookup"><span data-stu-id="fad5a-170">This value should typically be the current time plus the value of **RetryInterval**.</span></span> <span data-ttu-id="fad5a-171">**RetryInterval** es una propiedad de contexto de sistema cuyas unidades son minutos.</span><span class="sxs-lookup"><span data-stu-id="fad5a-171">**RetryInterval** is a system context property whose units are minutes.</span></span> <span data-ttu-id="fad5a-172">Tanto el **RetryCount** y **RetryInterval** en el contexto del mensaje son los valores que se configuran en el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="fad5a-172">Both the **RetryCount** and **RetryInterval** in the message context are the values that are configured on the send port.</span></span> <span data-ttu-id="fad5a-173">Consideremos una implementación escalada horizontalmente con instancias del mismo host de BizTalk implementadas en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="fad5a-173">Consider a scaled-out deployment with instances of the same BizTalk Host deployed on multiple computers.</span></span> <span data-ttu-id="fad5a-174">Si el mensaje se entrega una vez agotado el intervalo de reintentos, podrá entregarse a cualquiera de las instancias de host de cualquiera de los equipos en los que aquéllas están configuradas para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="fad5a-174">If the message is delivered after the retry interval has expired, the message may be delivered to the any one of the host instances on any of the computers where they are configured to run.</span></span> <span data-ttu-id="fad5a-175">Por ello, el adaptador no debería conservar ningún estado asociado con un mensaje que se deba utilizar en el reintento, ya que no hay garantía de que la misma instancia del adaptador se haga responsable, posteriormente, de la transmisión.</span><span class="sxs-lookup"><span data-stu-id="fad5a-175">For this reason the adapter should not hold any state associated with a message to be used on the retry attempt because there is no guarantee that same instance of the adapter will be responsible for the transmission at a later time.</span></span>  

 <span data-ttu-id="fad5a-176">El adaptador solo debe intentar mover el mensaje al transporte de reserva después de que el recuento de reintentos sea inferior o igual a cero.</span><span class="sxs-lookup"><span data-stu-id="fad5a-176">The adapter should only attempt to move the message to the backup transport after the retry count is less than or equal to zero.</span></span> <span data-ttu-id="fad5a-177">Si no hay ningún transporte de reserva configurado para el puerto, el intento de mover el mensaje a dicho transporte no se llevará a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="fad5a-177">An attempt to move the message to the backup transport will fail if there is no backup transport configured for the port.</span></span> <span data-ttu-id="fad5a-178">En este caso, el mensaje debería suspenderse.</span><span class="sxs-lookup"><span data-stu-id="fad5a-178">In this case the message should be suspended.</span></span>  

 <span data-ttu-id="fad5a-179">El código siguiente muestra cómo determinar el intervalo y el recuento de reintentos a partir del contexto del mensaje, así como el reenvío o el movimiento siguiente al transporte de reserva.</span><span class="sxs-lookup"><span data-stu-id="fad5a-179">The following code fragment illustrates how to determine the retry count and interval from the message context, and the subsequent resubmit or move to the backup transport.</span></span>  

```  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  
 …  
// RetryCount and RetyInterval are system context properties...  
private static readonly PropertyBase RetryCountProperty =   
 new BTS.RetryCount();  
private static readonly PropertyBase RetryIntervalProperty =   
 new BTS.RetryInterval();  

public void HandleRetry(IBaseMessage msg, IBTTransportBatch batch)  
{  
int retryCount = 0;  
int retryInterval = 0;  

// Get the RetryCount and RetryInterval off the msg ctx...  
 GetMessageRetryState(msg, out retryCount, out retryInterval);  

// If we have retries available resubmit, else move to   
 // backup transport...  
 if ( retryCount > 0 )  
batch.Resubmit(  
 msg, DateTime.Now.AddMinutes(retryInterval));  
else  
batch.MoveToNextTransport(msg);  
}  

public void GetMessageRetryState(  
 IBaseMessage msg,   
 out int retryCount,   
 out int retryInterval )  
{  
retryCount = 0;  
retryInterval = 0;  

object obj =  msg.Context.Read(  
RetryCountProperty.Name.Name,    
RetryCountProperty.Name.Namespace);   

if ( null != obj )  
retryCount = (int)obj;  

obj =  msg.Context.Read(  
RetryIntervalProperty.Name.Name,    
RetryIntervalProperty.Name.Namespace);   

if ( null != obj )  
retryInterval = (int)obj;  
}  
```  

## <a name="throwing-an-exception-from-transmitmessage"></a><span data-ttu-id="fad5a-180">Lanzar una excepción desde TransmitMessage</span><span class="sxs-lookup"><span data-stu-id="fad5a-180">Throwing an Exception from TransmitMessage</span></span>  
 <span data-ttu-id="fad5a-181">Si el adaptador inicia una excepción en cualquiera de las API **IBTTransmitter.TransmitMessage**, **IBTTransmitterBatch.TransmitMessage**, **IBTTransmitterBatch.Done**, el motor tratará la transmisión de los mensajes implicados como errores de transmisión y toma las medidas oportunas para el mensaje, como se detalla en [cómo controlar errores de los adaptadores](../core/how-to-handle-adapter-failures.md).</span><span class="sxs-lookup"><span data-stu-id="fad5a-181">If the adapter throws an exception on any of the APIs **IBTTransmitter.TransmitMessage**, **IBTTransmitterBatch.TransmitMessage**, **IBTTransmitterBatch.Done**, the engine treats the transmission of the messages involved as transmission failures and takes the appropriate action for the message, as detailed in [How to Handle Adapter Failures](../core/how-to-handle-adapter-failures.md).</span></span>  

 <span data-ttu-id="fad5a-182">En el caso de los adaptadores de envío compatibles con lotes, el lanzamiento de una excepción en la API TransmitMessage tiene como resultado la eliminación de la totalidad del lote y la puesta en práctica de las acciones de errores de transmisión predeterminadas para todos los mensajes de ese lote.</span><span class="sxs-lookup"><span data-stu-id="fad5a-182">For batch-aware send adapters, throwing an exception on the TransmitMessage API results in the entire batch being cleared and the default transmit failure actions being performed for all messages in that batch.</span></span>  

## <a name="solicit-response"></a><span data-ttu-id="fad5a-183">Petición-Respuesta</span><span class="sxs-lookup"><span data-stu-id="fad5a-183">Solicit-Response</span></span>  
 <span data-ttu-id="fad5a-184">Los adaptadores de envío bidireccionales admiten, por lo general, tanto transmisiones bidireccionales como unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="fad5a-184">Two-way send adapters typically support both one-way and two-way transmissions.</span></span> <span data-ttu-id="fad5a-185">El adaptador de envío determina si el mensaje debe transmitirse como un envío unidireccional o bidireccional inspeccionando la **IsSolicitResponse** propiedad de contexto del sistema en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fad5a-185">The send adapter determines whether the message should be transmitted as a one-way or two-way send by inspecting the **IsSolicitResponse** system context property in the message context.</span></span>  

 <span data-ttu-id="fad5a-186">En el siguiente fragmento de código se muestra este caso:</span><span class="sxs-lookup"><span data-stu-id="fad5a-186">The following code fragment demonstrates this:</span></span>  

```  
private bool portIsTwoWay = false;  
private static readonly PropertyBase IsSolicitResponseProperty= new BTS.IsSolicitResponse();  

...  

 // Port is one way or two way...  
 object obj =  this.message.Context.Read(  
 IsSolicitResponseProperty.Name.Name,    
 IsSolicitResponseProperty.Name.Namespace);   

if ( null != obj )  
 this.portIsTwoWay = (bool)obj;  
```  

 <span data-ttu-id="fad5a-187">Durante una transmisión de petición-respuesta, el adaptador transmite el mensaje de petición.</span><span class="sxs-lookup"><span data-stu-id="fad5a-187">During a solicit-response transmission the adapter transmits the solicit message.</span></span> <span data-ttu-id="fad5a-188">Una vez completado lo anterior, envía la respuesta asociada y le ordena al motor de mensajería que elimine el mensaje de petición original de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fad5a-188">After this completed it submits the associated response and tells the Messaging Engine to delete the original solicit message from the MessageBox database.</span></span> <span data-ttu-id="fad5a-189">La acción de eliminar el mensaje de la cola de la aplicación debe efectuarse en el mismo lote de proxy de transporte que el envío del mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fad5a-189">The action of deleting the message from the application queue should be performed in the same transport proxy batch as the submission of the response message.</span></span> <span data-ttu-id="fad5a-190">Con ello, se asegura el carácter atómico de la eliminación y el envío de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="fad5a-190">This ensures atomicity of the deletion and submission of the response.</span></span> <span data-ttu-id="fad5a-191">Para obtener una atomicidad completa, el adaptador debe utilizar una transacción de DTC en cuyo contexto se encuentren el mensaje de petición a un recurso compatible con transacciones, el envío del mensaje de respuesta y la eliminación del mensaje de petición.</span><span class="sxs-lookup"><span data-stu-id="fad5a-191">For complete atomicity the adapter should use a DTC transaction whereby the transmission of the solicit message to a transaction-aware resource, submission of the response message, and deletion of the solicit message are all in the context of the same DTC transaction.</span></span> <span data-ttu-id="fad5a-192">Como siempre, se recomienda que el mensaje de petición se transmita mediante un envío de no bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fad5a-192">As always, we recommend that the solicit message is transmitted using a non-blocking send.</span></span>  

 <span data-ttu-id="fad5a-193">En el siguiente fragmento de código se muestran los aspectos principales de un envío bidireccional.</span><span class="sxs-lookup"><span data-stu-id="fad5a-193">The following code fragment illustrates the main aspects of a two-way send.</span></span> <span data-ttu-id="fad5a-194">Cuando el motor llama **IBTTransmitter.TransmitMessage** el adaptador coloca el mensaje que se transmite a una cola en memoria.</span><span class="sxs-lookup"><span data-stu-id="fad5a-194">When the engine calls **IBTTransmitter.TransmitMessage** the adapter enqueues the message to be transmitted to an in-memory queue.</span></span> <span data-ttu-id="fad5a-195">El adaptador devuelve `false` para indicar que está realizando un envío de no bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fad5a-195">The adapter returns `false` to indicate that it is performing a non-blocking send.</span></span> <span data-ttu-id="fad5a-196">Grupo de subprocesos del adaptador (**WorkerThreadThunk**) de servicios de la cola en memoria y extrae un mensaje para entregarlo a un método auxiliar.</span><span class="sxs-lookup"><span data-stu-id="fad5a-196">The adapter's thread pool (**WorkerThreadThunk**) services the in-memory queue and dequeues a message to hand it off to a helper method.</span></span> <span data-ttu-id="fad5a-197">Este método es el responsable del envío del mensaje de petición y de la recepción del mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fad5a-197">This method is responsible for sending the solicit message and receiving the response message.</span></span> <span data-ttu-id="fad5a-198">(La implementación de este método auxiliar excede el alcance de este tema.) El mensaje de respuesta se envía al motor y el mensaje de petición se elimina de la cola de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad5a-198">(The implementation of this helper method is outside the scope of this topic.) The response message is submitted into the engine, and the solicit message is deleted from the application queue.</span></span>  

```  
using System.Collections;  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  

     static private Queue _transmitQueue = new Queue();  
  static private IBTTransportProxy _transportProxy = null;   
// IBTTransmitter...  
 public bool TransmitMessage(IBaseMessage msg)  
{  
// Add message to the transmit queue...  
lock(_transmitQueue.SyncRoot)  
 {  
_transmitQueue.Enqueue(msg);  
 }  

 return false;  
}  

 // Threadpool worker thread...   
private void WorkerThreadThunk()  
{  
try  
{  
 IBaseMessage solicitMsg = null;  

 lock(_transmitQueue.SyncRoot)  
 {  
 solicitMsg =   
 (IBaseMessage)_transmitQueue.Dequeue();  
}  

 IBaseMessage responseMsg = SendSolicitResponse(   
 solicitMsg );  
Callback cb = new Callback();  

IBTTransportBatch batch = _transportProxy.GetBatch(  
 cb, null);  
batch.SubmitResponseMessage( solicitMsg, responseMsg );  
batch.DeleteMessage( solicitMsg );  
batch.Done(null);  
}  
catch(Exception)  
{  
// Handle failure....  
}  
}  

static private IBaseMessage SendSolicitResponse(  
 IBaseMessage solicitMsg )  
{  
// Helper method to send solicit message and receive   
 // response message...  
IBaseMessage responseMsg = null;  
return responseMsg;  
}  
```  

## <a name="dynamic-sends"></a><span data-ttu-id="fad5a-199">Envíos dinámicos</span><span class="sxs-lookup"><span data-stu-id="fad5a-199">Dynamic Sends</span></span>  
 <span data-ttu-id="fad5a-200">Los puertos de envío dinámico no tienen una configuración de adaptador asociada a ellos.</span><span class="sxs-lookup"><span data-stu-id="fad5a-200">Dynamic send ports do not have adapter configuration associated with them.</span></span> <span data-ttu-id="fad5a-201">En lugar de ello, utilizan la configuración del controlador para cualquier propiedad predeterminada que necesite el adaptador para transmitir mensajes en un puerto dinámico.</span><span class="sxs-lookup"><span data-stu-id="fad5a-201">Instead they use handler configuration for any default properties that the adapter needs to transmit messages on a dynamic port.</span></span> <span data-ttu-id="fad5a-202">Por ejemplo, es posible que un adaptador de HTTP necesite utilizar un proxy y tenga que proporcionar credenciales.</span><span class="sxs-lookup"><span data-stu-id="fad5a-202">For example, an HTTP adapter may need to use a proxy and need to provide credentials.</span></span> <span data-ttu-id="fad5a-203">El nombre de usuario, la contraseña y el puerto pueden especificarse en la configuración del controlador que el adaptador guarda en la caché en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fad5a-203">The user name, password, and port could be specified in the handler configuration that the adapter caches at run time.</span></span>  

 <span data-ttu-id="fad5a-204">Para el motor determine el transporte que se enviarán a través de, un mensaje dinámico el **OutboundTransportLocation** tiene como prefijo el alias del adaptador.</span><span class="sxs-lookup"><span data-stu-id="fad5a-204">For the engine to determine the transport that a dynamic message is to be sent over, the **OutboundTransportLocation** is prefixed with the adapter's alias.</span></span> <span data-ttu-id="fad5a-205">Un adaptador puede registrar uno o varios alias con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en tiempo de instalación.</span><span class="sxs-lookup"><span data-stu-id="fad5a-205">An adapter can register one or more aliases with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] at install time.</span></span> <span data-ttu-id="fad5a-206">El motor analiza la **OutboundTransportLocation** en tiempo de ejecución para encontrar una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="fad5a-206">The engine parses the **OutboundTransportLocation** at run time to find a match.</span></span> <span data-ttu-id="fad5a-207">El adaptador es responsable de control de la **OutboundTransportLocation** con o sin el alias antepuesto a él.</span><span class="sxs-lookup"><span data-stu-id="fad5a-207">The adapter is responsible for handling the **OutboundTransportLocation** with or without the alias prepended to it.</span></span> <span data-ttu-id="fad5a-208">En la tabla siguiente se muestran algunos ejemplos de alias registrados para adaptadores de BizTalk predeterminados.</span><span class="sxs-lookup"><span data-stu-id="fad5a-208">The following table shows some examples of aliases registered for out-of-the-box BizTalk adapters.</span></span>  


| <span data-ttu-id="fad5a-209">Alias de adaptador</span><span class="sxs-lookup"><span data-stu-id="fad5a-209">Adapter alias</span></span> | <span data-ttu-id="fad5a-210">Adaptador</span><span class="sxs-lookup"><span data-stu-id="fad5a-210">Adapter</span></span> |   <span data-ttu-id="fad5a-211">Ejemplo de OutboundTransportLocation</span><span class="sxs-lookup"><span data-stu-id="fad5a-211">OutboundTransportLocation example</span></span>    |
|---------------|---------|----------------------------------------|
|    <span data-ttu-id="fad5a-212">HTTP://</span><span class="sxs-lookup"><span data-stu-id="fad5a-212">HTTP://</span></span>    |  <span data-ttu-id="fad5a-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="fad5a-213">HTTP</span></span>   |     <span data-ttu-id="fad5a-214">http://www.</span><span class="sxs-lookup"><span data-stu-id="fad5a-214">http://www.</span></span> <span data-ttu-id="fad5a-215">MyCompany.com/bar</span><span class="sxs-lookup"><span data-stu-id="fad5a-215">MyCompany.com/bar</span></span>      |
|   <span data-ttu-id="fad5a-216">HTTPS://</span><span class="sxs-lookup"><span data-stu-id="fad5a-216">HTTPS://</span></span>    |  <span data-ttu-id="fad5a-217">HTTP</span><span class="sxs-lookup"><span data-stu-id="fad5a-217">HTTP</span></span>   |     <span data-ttu-id="fad5a-218">https://www.</span><span class="sxs-lookup"><span data-stu-id="fad5a-218">https://www.</span></span> <span data-ttu-id="fad5a-219">MyCompany.com/bar</span><span class="sxs-lookup"><span data-stu-id="fad5a-219">MyCompany.com/bar</span></span>     |
|    <span data-ttu-id="fad5a-220">mailto:</span><span class="sxs-lookup"><span data-stu-id="fad5a-220">mailto:</span></span>    |  <span data-ttu-id="fad5a-221">SMTP</span><span class="sxs-lookup"><span data-stu-id="fad5a-221">SMTP</span></span>   |      mailto:A.User@MyCompany.com       |
|    <span data-ttu-id="fad5a-222">FILE://</span><span class="sxs-lookup"><span data-stu-id="fad5a-222">FILE://</span></span>    |  <span data-ttu-id="fad5a-223">FILE</span><span class="sxs-lookup"><span data-stu-id="fad5a-223">FILE</span></span>   | <span data-ttu-id="fad5a-224">FILE://C:\ MyCompany \\%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="fad5a-224">FILE://C:\ MyCompany \\%MessageID%.xml</span></span> |

