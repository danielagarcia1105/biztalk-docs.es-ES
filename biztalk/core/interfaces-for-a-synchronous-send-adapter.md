---
title: Interfaces de un envío sincrónico adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e1b397a-3a35-4447-8522-d8a5f39a42d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1012b52bf5c6ab564cc219926b97445e43f60dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256916"
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a><span data-ttu-id="ae7fc-102">Interfaces de un adaptador de envío sincrónico</span><span class="sxs-lookup"><span data-stu-id="ae7fc-102">Interfaces for a Synchronous Send Adapter</span></span>
<span data-ttu-id="ae7fc-103">Un adaptador envía mensajes de manera sincrónica cuando bloquea el subproceso de llamada del motor de mensajería entrante mientras realiza su operación de envío.</span><span class="sxs-lookup"><span data-stu-id="ae7fc-103">An adapter sends messages synchronously when it blocks the incoming Messaging Engine calling thread while performing its send operation.</span></span> <span data-ttu-id="ae7fc-104">Para poder enviar mensajes de manera sincrónica, un adaptador necesita implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="ae7fc-104">To be able to send messages synchronously, an adapter needs to implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="ae7fc-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="ae7fc-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="ae7fc-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="ae7fc-106">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="ae7fc-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="ae7fc-107">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="ae7fc-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="ae7fc-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="ae7fc-109">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="ae7fc-109">**IBTTransmitter**</span></span>  
  
 <span data-ttu-id="ae7fc-110">En un envío sincrónico, el adaptador envía el mensaje mientras bloquea **TransmitMessage**, y después devuelve transmisión correcta`True.`</span><span class="sxs-lookup"><span data-stu-id="ae7fc-110">In a synchronous send, the adapter sends the message while blocking **TransmitMessage**, and after successful transmission returns `True.`</span></span>  
  
 <span data-ttu-id="ae7fc-111">La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío sincrónico.</span><span class="sxs-lookup"><span data-stu-id="ae7fc-111">The following figure shows the object interactions involved in creating a synchronous send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")  
<span data-ttu-id="ae7fc-112">Flujo de trabajo para enviar un mensaje de forma sincrónica</span><span class="sxs-lookup"><span data-stu-id="ae7fc-112">Workflow for sending a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7fc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae7fc-113">See Also</span></span>  
 <span data-ttu-id="ae7fc-114">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="ae7fc-114">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="ae7fc-115">[Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ae7fc-115">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="ae7fc-116">[Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ae7fc-116">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="ae7fc-117">[Adaptador de envío de interfaces para una asincrónica](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ae7fc-117">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="ae7fc-118">[Interfaces para un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ae7fc-118">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="ae7fc-119">[Interfaces de un adaptador de envío asíncrono compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ae7fc-119">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="ae7fc-120">[Interfaces para un adaptador de envío asincrónica transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ae7fc-120">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="ae7fc-121">Interfaces para una petición-respuesta del adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="ae7fc-121">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)