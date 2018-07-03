---
title: Interfaces de un envío sincrónico adaptador | Microsoft Docs
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
ms.openlocfilehash: 1602d19bc5b97231a25f5449f5837fce153c037d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008845"
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a><span data-ttu-id="1e89b-102">Interfaces de un adaptador de envío sincrónico</span><span class="sxs-lookup"><span data-stu-id="1e89b-102">Interfaces for a Synchronous Send Adapter</span></span>
<span data-ttu-id="1e89b-103">Un adaptador envía mensajes de manera sincrónica cuando bloquea el subproceso de llamada del motor de mensajería entrante mientras realiza su operación de envío.</span><span class="sxs-lookup"><span data-stu-id="1e89b-103">An adapter sends messages synchronously when it blocks the incoming Messaging Engine calling thread while performing its send operation.</span></span> <span data-ttu-id="1e89b-104">Para poder enviar mensajes de manera sincrónica, un adaptador necesita implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="1e89b-104">To be able to send messages synchronously, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="1e89b-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="1e89b-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="1e89b-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="1e89b-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="1e89b-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="1e89b-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="1e89b-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="1e89b-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="1e89b-109">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="1e89b-109">**IBTTransmitter**</span></span>  
  
  <span data-ttu-id="1e89b-110">En un envío sincrónico, el adaptador envía el mensaje mientras bloquea **TransmitMessage**, y después devuelve transmisión correcta `True.`</span><span class="sxs-lookup"><span data-stu-id="1e89b-110">In a synchronous send, the adapter sends the message while blocking **TransmitMessage**, and after successful transmission returns `True.`</span></span>  
  
  <span data-ttu-id="1e89b-111">La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío sincrónico.</span><span class="sxs-lookup"><span data-stu-id="1e89b-111">The following figure shows the object interactions involved in creating a synchronous send adapter.</span></span>  
  
  <span data-ttu-id="1e89b-112">![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")</span><span class="sxs-lookup"><span data-stu-id="1e89b-112">![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")</span></span>  
  <span data-ttu-id="1e89b-113">Flujo de trabajo para enviar un mensaje de forma sincrónica</span><span class="sxs-lookup"><span data-stu-id="1e89b-113">Workflow for sending a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e89b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e89b-114">See Also</span></span>  
 <span data-ttu-id="1e89b-115">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="1e89b-115">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="1e89b-116">[Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1e89b-116">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="1e89b-117">[Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1e89b-117">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="1e89b-118">[Interfaces para asincrónico del adaptador de envío](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1e89b-118">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="1e89b-119">[Interfaces de un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1e89b-119">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="1e89b-120">[Interfaces de un adaptador de envío asincrónico compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1e89b-120">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="1e89b-121">[Interfaces de un adaptador de envío asincrónico transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1e89b-121">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="1e89b-122">Interfaces de un adaptador de envío de petición-respuesta</span><span class="sxs-lookup"><span data-stu-id="1e89b-122">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)