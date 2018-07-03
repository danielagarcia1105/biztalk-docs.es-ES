---
title: Interfaces de un adaptador de envío asincrónico transaccional compatible con lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5b2dbdf-e6ba-4b58-a0a5-fc78feaf5c35
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c3ad79f09563b3e65ccfab64da5b9ec6ea3033c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982901"
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="8c7c1-102">Interfaces de un adaptador de envío asíncrono transaccional compatible con lotes</span><span class="sxs-lookup"><span data-stu-id="8c7c1-102">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="8c7c1-103">Un adaptador de envío puede crear y controlar transacciones cuando se necesite la transmisión transaccional de mensajes.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-103">A send adapter can create and control transactions when transactional transmission of messages is required.</span></span> <span data-ttu-id="8c7c1-104">Para admitir el envío transaccional, un adaptador debe implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="8c7c1-104">To support transactional send, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="8c7c1-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="8c7c1-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="8c7c1-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="8c7c1-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="8c7c1-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="8c7c1-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="8c7c1-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="8c7c1-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="8c7c1-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="8c7c1-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="8c7c1-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="8c7c1-110">**IBTTransmitterBatch**</span></span>  
  
- <span data-ttu-id="8c7c1-111">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="8c7c1-111">**IBTBatchCallBack**</span></span>  
  
  <span data-ttu-id="8c7c1-112">Un adaptador crea una transacción MSDTC y devuelve un puntero a ese objeto en la llamada a la **BeginBatch** método de la **IBTTransmitterBatch** interfaz.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-112">An adapter creates an MSDTC transaction and returns a pointer to that object in the call to the **BeginBatch** method of the **IBTTransmitterBatch** interface.</span></span> <span data-ttu-id="8c7c1-113">El motor de mensajería llama a ese método para obtener un lote con el que envía mensajes salientes al adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-113">The Messaging Engine calls this method to obtain a batch with which it posts outgoing messages to the send adapter.</span></span> <span data-ttu-id="8c7c1-114">Cuando el adaptador finalice la operación de envío y se confirma o revierte una transacción, notifica el motor de mensajería del resultado de la transacción mediante el uso de la **DTCCommitConfirm** método de la **IBTDTCCommitConfirm**  interfaz.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-114">When the adapter finishes the send operation and commits or rolls back a transaction, it notifies the Messaging Engine of the result of the transaction by using the **DTCCommitConfirm** method of the **IBTDTCCommitConfirm** interface.</span></span>  
  
  <span data-ttu-id="8c7c1-115">En la siguiente ilustración se muestra la interacción entre el proxy de transporte y el adaptador de envío al realizar una operación de envío transaccional.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-115">The following figure shows the interaction between the transport proxy and the send adapter when performing a transactional send operation.</span></span>  
  
  <span data-ttu-id="8c7c1-116">![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")</span><span class="sxs-lookup"><span data-stu-id="8c7c1-116">![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")</span></span>  
  <span data-ttu-id="8c7c1-117">Flujo de trabajo para enviar un mensaje transaccional de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="8c7c1-117">Workflow for sending a transactional message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c7c1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c7c1-118">See Also</span></span>  
 <span data-ttu-id="8c7c1-119">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="8c7c1-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="8c7c1-120">[Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="8c7c1-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="8c7c1-121">[Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="8c7c1-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="8c7c1-122">[Interfaces para un valor sincrónico del adaptador de envío](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="8c7c1-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="8c7c1-123">[Interfaces para asincrónico del adaptador de envío](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="8c7c1-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="8c7c1-124">[Interfaces de un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="8c7c1-124">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="8c7c1-125">[Interfaces de un adaptador de envío asincrónico compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="8c7c1-125">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="8c7c1-126">Interfaces de un adaptador de envío de petición-respuesta</span><span class="sxs-lookup"><span data-stu-id="8c7c1-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)