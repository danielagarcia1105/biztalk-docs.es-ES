---
title: "Interfaces para una asincrónica compatible con lotes del adaptador de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d38b8b87-508a-499b-86b2-846938050b44
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4af0a5c116c19c4cb1fa728cc016144594f42f13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="14f93-102">Interfaces de un adaptador de envío asíncrono compatible con lotes</span><span class="sxs-lookup"><span data-stu-id="14f93-102">Interfaces for an Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="14f93-103">Los adaptadores compatibles con lotes pueden enviar mensajes de forma sincrónica o asincrónica y pueden realizar envíos de transacción.</span><span class="sxs-lookup"><span data-stu-id="14f93-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted sends.</span></span> <span data-ttu-id="14f93-104">Para enviar lotes de mensajes, un adaptador de envío debe implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="14f93-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="14f93-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="14f93-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="14f93-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="14f93-106">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="14f93-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="14f93-107">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="14f93-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="14f93-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="14f93-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="14f93-109">**IBTBatchTransmitter**</span></span>  
  
-   <span data-ttu-id="14f93-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="14f93-110">**IBTTransmitterBatch**</span></span>  
  
 <span data-ttu-id="14f93-111">Para el envío por lotes asíncrono, el motor de mensajería obtiene un lote del adaptador y agrega mensajes mediante para que se transmitan a ese lote.</span><span class="sxs-lookup"><span data-stu-id="14f93-111">For the asynchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="14f93-112">Los mensajes se envían sólo cuando el motor de mensajería llama el **realiza** método en el lote.</span><span class="sxs-lookup"><span data-stu-id="14f93-112">The messages are only sent when the Messaging Engine calls the **Done** method on the batch.</span></span> <span data-ttu-id="14f93-113">El adaptador devuelve `False` para cada mensaje que intenta transmitir de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="14f93-113">The adapter returns `False` for each message that it intends to transmit asynchronously.</span></span> <span data-ttu-id="14f93-114">A continuación, el adaptador obtiene un lote desde el proxy del adaptador y elimina aquellos mensajes que ha transmitido correctamente.</span><span class="sxs-lookup"><span data-stu-id="14f93-114">The adapter then gets a batch from the adapter proxy and deletes those messages that it successfully transmitted.</span></span>  
  
 <span data-ttu-id="14f93-115">La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío asíncrono compatible con lotes.</span><span class="sxs-lookup"><span data-stu-id="14f93-115">The following figure shows the object interactions involved in creating an asynchronous batch-supported send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")  
<span data-ttu-id="14f93-116">Flujo de trabajo para enviar un mensaje de forma asíncrona</span><span class="sxs-lookup"><span data-stu-id="14f93-116">Workflow for sending a message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f93-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="14f93-117">See Also</span></span>  
 <span data-ttu-id="14f93-118">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="14f93-118">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="14f93-119">[Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="14f93-119">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="14f93-120">[Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="14f93-120">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="14f93-121">[Interfaces de un envío sincrónico adaptador](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="14f93-121">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="14f93-122">[Adaptador de envío de interfaces para una asincrónica](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="14f93-122">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="14f93-123">[Interfaces para un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="14f93-123">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="14f93-124">[Interfaces para un adaptador de envío asincrónica transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="14f93-124">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="14f93-125">Interfaces para una petición-respuesta del adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="14f93-125">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)