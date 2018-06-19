---
title: Interfaces de un envío asíncrono adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a214716-8f39-400d-a111-ba1b92a284b4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db156f5a95a088ae706bb2b1c801d8dee89cdece
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257764"
---
# <a name="interfaces-for-an-asynchronous-send-adapter"></a><span data-ttu-id="92498-102">Interfaces de un adaptador de envío asíncrono</span><span class="sxs-lookup"><span data-stu-id="92498-102">Interfaces for an Asynchronous Send Adapter</span></span>
<span data-ttu-id="92498-103">Los adaptadores que envían mensajes de uno en uno pueden enviar mensajes de forma sincrónica o asíncrona.</span><span class="sxs-lookup"><span data-stu-id="92498-103">Adapters sending messages one at a time may send messages either synchronously or asynchronously.</span></span> <span data-ttu-id="92498-104">Un adaptador envía mensajes de forma asíncrona cuando no bloquea el subproceso del proxy de transporte pero, en su lugar, utiliza un subproceso distinto al realizar operaciones de envío.</span><span class="sxs-lookup"><span data-stu-id="92498-104">An adapter sends messages asynchronously when it does not block the transport proxy thread but rather uses a separate thread while performing the send operations.</span></span> <span data-ttu-id="92498-105">Para poder enviar mensajes de forma asíncrona, un adaptador necesita implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="92498-105">To be able to send messages asynchronously, an adapter needs to implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="92498-106">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="92498-106">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="92498-107">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="92498-107">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="92498-108">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="92498-108">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="92498-109">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="92498-109">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="92498-110">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="92498-110">**IBTTransmitter**</span></span>  
  
 <span data-ttu-id="92498-111">Los siguientes pasos describen la secuencia de acciones que realiza un adaptador de envío para transmitir mensajes fuera del servidor a petición del motor de mensajería:</span><span class="sxs-lookup"><span data-stu-id="92498-111">The following steps describe the sequence of actions that the send adapter performs to transmit messages out of the server at the request of the Messaging Engine:</span></span>  
  
1.  <span data-ttu-id="92498-112">El motor de mensajería utiliza el proxy de transporte para pasar un mensaje saliente a un adaptador de envío mediante una llamada a la **TransmitMessage** método de la **IBTTransmitter** interfaz.</span><span class="sxs-lookup"><span data-stu-id="92498-112">The Messaging Engine uses the transport proxy to pass an outgoing message to a send adapter by calling the **TransmitMessage** method of the **IBTTransmitter** interface.</span></span>  
  
2.  <span data-ttu-id="92498-113">El adaptador devuelve inmediatamente desde **TransmitMessage** después de almacenar el mensaje que se enviará a alguna cola interna y devuelve `False` para **bDeleteMessage**.</span><span class="sxs-lookup"><span data-stu-id="92498-113">The adapter returns immediately from **TransmitMessage** after storing the message to be sent to some internal queue, and returns `False` for **bDeleteMessage**.</span></span> <span data-ttu-id="92498-114">Esto indica al motor de mensajería que el mensaje se transmitirá de forma asíncrona.</span><span class="sxs-lookup"><span data-stu-id="92498-114">This tells the Messaging Engine the message will be transmitted in an asynchronous manner.</span></span>  
  
3.  <span data-ttu-id="92498-115">El adaptador envía el mensaje mediante su propio grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="92498-115">The adapter sends the message using its own thread pool.</span></span>  
  
4.  <span data-ttu-id="92498-116">Cuando la operación de envío se completa, el adaptador elimina el mensaje original de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="92498-116">After the send operation completes, the adapter deletes the original message from the MessageBox database.</span></span> <span data-ttu-id="92498-117">Obtiene un lote desde el motor de mensajería mediante el **IBTTransportBatch.GetBatch** método de proxy de transporte y, a continuación, llama **DeleteMessage**.</span><span class="sxs-lookup"><span data-stu-id="92498-117">It obtains a batch from the Messaging Engine using the **IBTTransportBatch.GetBatch** method of the transport proxy, and then calls **DeleteMessage**.</span></span>  
  
     <span data-ttu-id="92498-118">La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío asíncrono.</span><span class="sxs-lookup"><span data-stu-id="92498-118">The following figure shows the object interactions involved in creating an asynchronous send adapter.</span></span>  
  
     ![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")  
<span data-ttu-id="92498-119">Flujo de trabajo para enviar un mensaje de forma asíncrona</span><span class="sxs-lookup"><span data-stu-id="92498-119">Workflow for sending a message asynchronously</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92498-120">Se recomienda que el adaptador realice un recuento de los mensajes cuyo procesamiento está en curso.</span><span class="sxs-lookup"><span data-stu-id="92498-120">We recommend that the adapter keep a count of the messages currently being processed.</span></span> <span data-ttu-id="92498-121">El adaptador debe bloquear el **Terminate** método hasta que llegue a cero el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="92498-121">The adapter should block the **Terminate** method until the message count has reached zero.</span></span> <span data-ttu-id="92498-122">En el caso de los adaptadores de envío, los mensajes cuyo proceso está en curso deberían controlarse de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="92498-122">For send adapters, messages that are being processed should be handled appropriately.</span></span> <span data-ttu-id="92498-123">Esto significa que cualquier mensaje entregado correctamente de forma asíncrona debe eliminarse de la cola privada de mensajes de la aplicación del adaptador para evitar que se envíe dos veces.</span><span class="sxs-lookup"><span data-stu-id="92498-123">This means that any message that was successfully delivered asynchronously should be deleted from the adapter's private application message queue to prevent messages from being sent twice.</span></span> <span data-ttu-id="92498-124">En general, después **Terminate** se llama el motor de mensajería no acepta solicitudes para publicar nuevos mensajes desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="92498-124">In general, after **Terminate** is called by the Messaging Engine it does not accept requests to publish new messages from the adapter.</span></span> <span data-ttu-id="92498-125">La excepción a esto son los mensajes de respuesta relacionados con los pares petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="92498-125">The exception to this is response messages related to solicit-response pairs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92498-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="92498-126">See Also</span></span>  
 <span data-ttu-id="92498-127">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="92498-127">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="92498-128">[Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="92498-128">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="92498-129">[Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="92498-129">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="92498-130">[Interfaces de un envío sincrónico adaptador](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="92498-130">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="92498-131">[Interfaces para un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="92498-131">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="92498-132">[Interfaces de un adaptador de envío asíncrono compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="92498-132">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="92498-133">[Interfaces para un adaptador de envío asincrónica transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="92498-133">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="92498-134">Interfaces para una petición-respuesta del adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="92498-134">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)