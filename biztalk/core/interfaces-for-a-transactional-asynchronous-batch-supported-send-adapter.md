---
title: "Interfaces para un adaptador de envío asincrónica transaccional compatible con lotes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5b2dbdf-e6ba-4b58-a0a5-fc78feaf5c35
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 948000883c092c8e247b1d4f41fb2bc7e2280e40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="da89f-102">Interfaces de un adaptador de envío asíncrono transaccional compatible con lotes</span><span class="sxs-lookup"><span data-stu-id="da89f-102">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="da89f-103">Un adaptador de envío puede crear y controlar transacciones cuando se necesite la transmisión transaccional de mensajes.</span><span class="sxs-lookup"><span data-stu-id="da89f-103">A send adapter can create and control transactions when transactional transmission of messages is required.</span></span> <span data-ttu-id="da89f-104">Para admitir el envío transaccional, un adaptador debe implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="da89f-104">To support transactional send, an adapter needs to implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="da89f-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="da89f-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="da89f-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="da89f-106">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="da89f-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="da89f-107">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="da89f-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="da89f-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="da89f-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="da89f-109">**IBTBatchTransmitter**</span></span>  
  
-   <span data-ttu-id="da89f-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="da89f-110">**IBTTransmitterBatch**</span></span>  
  
-   <span data-ttu-id="da89f-111">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="da89f-111">**IBTBatchCallBack**</span></span>  
  
 <span data-ttu-id="da89f-112">Un adaptador crea una transacción MSDTC y devuelve un puntero a ese objeto en la llamada a la **BeginBatch** método de la **IBTTransmitterBatch** interfaz.</span><span class="sxs-lookup"><span data-stu-id="da89f-112">An adapter creates an MSDTC transaction and returns a pointer to that object in the call to the **BeginBatch** method of the **IBTTransmitterBatch** interface.</span></span> <span data-ttu-id="da89f-113">El motor de mensajería llama a ese método para obtener un lote con el que envía mensajes salientes al adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="da89f-113">The Messaging Engine calls this method to obtain a batch with which it posts outgoing messages to the send adapter.</span></span> <span data-ttu-id="da89f-114">Cuando el adaptador finaliza la operación de envío y se confirma o revierte una transacción, notifica al motor de mensajería del resultado de la transacción mediante el uso de la **DTCCommitConfirm** método de la **IBTDTCCommitConfirm**  interfaz.</span><span class="sxs-lookup"><span data-stu-id="da89f-114">When the adapter finishes the send operation and commits or rolls back a transaction, it notifies the Messaging Engine of the result of the transaction by using the **DTCCommitConfirm** method of the **IBTDTCCommitConfirm** interface.</span></span>  
  
 <span data-ttu-id="da89f-115">En la siguiente ilustración se muestra la interacción entre el proxy de transporte y el adaptador de envío al realizar una operación de envío transaccional.</span><span class="sxs-lookup"><span data-stu-id="da89f-115">The following figure shows the interaction between the transport proxy and the send adapter when performing a transactional send operation.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")  
<span data-ttu-id="da89f-116">Flujo de trabajo para enviar un mensaje transaccional de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="da89f-116">Workflow for sending a transactional message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da89f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="da89f-117">See Also</span></span>  
 <span data-ttu-id="da89f-118">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="da89f-118">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="da89f-119">[Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="da89f-119">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="da89f-120">[Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="da89f-120">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="da89f-121">[Interfaces de un envío sincrónico adaptador](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="da89f-121">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="da89f-122">[Adaptador de envío de interfaces para una asincrónica](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="da89f-122">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="da89f-123">[Interfaces para un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="da89f-123">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="da89f-124">[Interfaces de un adaptador de envío asíncrono compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="da89f-124">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="da89f-125">Interfaces para una petición-respuesta del adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="da89f-125">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)