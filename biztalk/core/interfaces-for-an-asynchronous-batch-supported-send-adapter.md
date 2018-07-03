---
title: Interfaces para asincrónico compatible con lotes del adaptador de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d38b8b87-508a-499b-86b2-846938050b44
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc579995821a97dc588b2221f8a7dd2e9cd1e136
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993021"
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="e6c3b-102">Interfaces de un adaptador de envío asíncrono compatible con lotes</span><span class="sxs-lookup"><span data-stu-id="e6c3b-102">Interfaces for an Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="e6c3b-103">Los adaptadores compatibles con lotes pueden enviar mensajes de forma sincrónica o asincrónica y pueden realizar envíos de transacción.</span><span class="sxs-lookup"><span data-stu-id="e6c3b-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted sends.</span></span> <span data-ttu-id="e6c3b-104">Para enviar lotes de mensajes, un adaptador de envío debe implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6c3b-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
- <span data-ttu-id="e6c3b-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="e6c3b-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="e6c3b-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="e6c3b-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="e6c3b-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="e6c3b-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="e6c3b-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="e6c3b-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="e6c3b-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="e6c3b-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="e6c3b-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="e6c3b-110">**IBTTransmitterBatch**</span></span>  
  
  <span data-ttu-id="e6c3b-111">Para el envío por lotes asíncrono, el motor de mensajería obtiene un lote del adaptador y agrega mensajes mediante para que se transmitan a ese lote.</span><span class="sxs-lookup"><span data-stu-id="e6c3b-111">For the asynchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="e6c3b-112">Los mensajes se envían solo cuando el motor de mensajería llama a la **realiza** método en el lote.</span><span class="sxs-lookup"><span data-stu-id="e6c3b-112">The messages are only sent when the Messaging Engine calls the **Done** method on the batch.</span></span> <span data-ttu-id="e6c3b-113">El adaptador devuelve `False` para cada mensaje que intenta transmitir de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="e6c3b-113">The adapter returns `False` for each message that it intends to transmit asynchronously.</span></span> <span data-ttu-id="e6c3b-114">A continuación, el adaptador obtiene un lote desde el proxy del adaptador y elimina aquellos mensajes que ha transmitido correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6c3b-114">The adapter then gets a batch from the adapter proxy and deletes those messages that it successfully transmitted.</span></span>  
  
  <span data-ttu-id="e6c3b-115">La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío asíncrono compatible con lotes.</span><span class="sxs-lookup"><span data-stu-id="e6c3b-115">The following figure shows the object interactions involved in creating an asynchronous batch-supported send adapter.</span></span>  
  
  <span data-ttu-id="e6c3b-116">![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")</span><span class="sxs-lookup"><span data-stu-id="e6c3b-116">![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")</span></span>  
  <span data-ttu-id="e6c3b-117">Flujo de trabajo para enviar un mensaje de forma asíncrona</span><span class="sxs-lookup"><span data-stu-id="e6c3b-117">Workflow for sending a message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6c3b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6c3b-118">See Also</span></span>  
 <span data-ttu-id="e6c3b-119">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e6c3b-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="e6c3b-120">[Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e6c3b-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="e6c3b-121">[Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e6c3b-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="e6c3b-122">[Interfaces para un valor sincrónico del adaptador de envío](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e6c3b-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="e6c3b-123">[Interfaces para asincrónico del adaptador de envío](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e6c3b-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="e6c3b-124">[Interfaces de un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e6c3b-124">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="e6c3b-125">[Interfaces de un adaptador de envío asincrónico transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e6c3b-125">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="e6c3b-126">Interfaces de un adaptador de envío de petición-respuesta</span><span class="sxs-lookup"><span data-stu-id="e6c3b-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)