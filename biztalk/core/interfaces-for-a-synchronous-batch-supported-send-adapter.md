---
title: Interfaces para un valor sincrónico compatible con lotes del adaptador de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b191c41-ca4f-4d2b-bd15-a93ad87a743d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d14e278869854535695babc9ff8796a833de7217
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968229"
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a><span data-ttu-id="21eee-102">Interfaces de un adaptador de envío sincrónico compatible con lotes</span><span class="sxs-lookup"><span data-stu-id="21eee-102">Interfaces for a Synchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="21eee-103">Los adaptadores compatibles con lotes pueden enviar mensajes de forma sincrónica o asincrónica y pueden realizar operaciones de envío de transacción.</span><span class="sxs-lookup"><span data-stu-id="21eee-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted send operations.</span></span> <span data-ttu-id="21eee-104">Para enviar lotes de mensajes, un adaptador de envío debe implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="21eee-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
- <span data-ttu-id="21eee-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="21eee-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="21eee-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="21eee-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="21eee-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="21eee-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="21eee-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="21eee-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="21eee-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="21eee-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="21eee-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="21eee-110">**IBTTransmitterBatch**</span></span>  
  
  <span data-ttu-id="21eee-111">Para el envío por lotes sincrónico, el motor de mensajería obtiene un lote del adaptador y agrega mensajes mediante para que se transmitan a ese lote.</span><span class="sxs-lookup"><span data-stu-id="21eee-111">For the synchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="21eee-112">El motor de mensajería agrega cada mensaje al lote y envía los mensajes solo cuando se llama a la **realiza** método en el lote.</span><span class="sxs-lookup"><span data-stu-id="21eee-112">The Messaging Engine adds each message to the batch and sends the messages only when it calls the **Done** method on the batch.</span></span> <span data-ttu-id="21eee-113">El adaptador devuelve `True` para **bDeleteMessage** para cada mensaje que intenta transmitir de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="21eee-113">The adapter returns `True` for **bDeleteMessage** for each message that it intends to transmit synchronously.</span></span> <span data-ttu-id="21eee-114">El adaptador debe guardar los datos de mensaje, en lugar de un puntero de mensaje, en su **TransmitMessage** implementación.</span><span class="sxs-lookup"><span data-stu-id="21eee-114">The adapter should save message data, as opposed to a message pointer, in its **TransmitMessage** implementation.</span></span> <span data-ttu-id="21eee-115">Esto es porque el puntero del mensaje ya no es válido tras `True` se devuelve y no deben usar o almacenar en caché para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="21eee-115">This is because the message pointer is no longer valid after `True` is returned, and should not be used or cached for later use.</span></span>  
  
  <span data-ttu-id="21eee-116">La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío sincrónico compatible con lotes.</span><span class="sxs-lookup"><span data-stu-id="21eee-116">The following figure shows the object interactions involved in creating a synchronous batch-supported send adapter.</span></span>  
  
  <span data-ttu-id="21eee-117">![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")</span><span class="sxs-lookup"><span data-stu-id="21eee-117">![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")</span></span>  
  <span data-ttu-id="21eee-118">Flujo de trabajo para enviar un mensaje de manera sincrónica</span><span class="sxs-lookup"><span data-stu-id="21eee-118">Workflow for submitting a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21eee-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="21eee-119">See Also</span></span>  
 <span data-ttu-id="21eee-120">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="21eee-120">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="21eee-121">[Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21eee-121">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="21eee-122">[Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21eee-122">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="21eee-123">[Interfaces para un valor sincrónico del adaptador de envío](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21eee-123">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="21eee-124">[Interfaces para asincrónico del adaptador de envío](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21eee-124">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="21eee-125">[Interfaces de un adaptador de envío asincrónico compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21eee-125">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="21eee-126">[Interfaces de un adaptador de envío asincrónico transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21eee-126">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="21eee-127">Interfaces de un adaptador de envío de petición-respuesta</span><span class="sxs-lookup"><span data-stu-id="21eee-127">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)