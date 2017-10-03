---
title: Procesamiento por lotes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching
- Messaging Engine, batching
- batching, batch size
- batching, about batching
- batching, configuring
- batching, Messaging Engine
ms.assetid: eadc177a-d395-4f99-8dab-aa706fd8ea00
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca31344e60daa88a37c21d0f90b6cf2d2a8aa5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="batching"></a><span data-ttu-id="d1414-102">Procesar por lotes</span><span class="sxs-lookup"><span data-stu-id="d1414-102">Batching</span></span>
<span data-ttu-id="d1414-103">*Procesamiento por lotes* es un procesamiento serializado de un conjunto de mensajes que permite optimizaciones con respecto a la base de datos de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="d1414-103">*Batching* is a serialized processing of a set of messages that allows for optimizations with respect to database round trips.</span></span> <span data-ttu-id="d1414-104">Un lote constituye una unidad de trabajo atómica, es decir, el resultado correcto o incorrecto se produce en todo el conjunto.</span><span class="sxs-lookup"><span data-stu-id="d1414-104">A batch is a unit of work that is atomic; that is, it either all succeeds or all fails.</span></span> <span data-ttu-id="d1414-105">Si una operación en lote se realiza correctamente pero se producen errores en otra operación, todas las operaciones que componen el lote quedan invalidadas y deben repetirse.</span><span class="sxs-lookup"><span data-stu-id="d1414-105">If one operation in a batch succeeds but another operation fails, all the operations that make up the batch are invalidated and must be repeated.</span></span>  
  
 <span data-ttu-id="d1414-106">BizTalk Server utiliza el procesamiento por lotes con los siguientes objetivos:</span><span class="sxs-lookup"><span data-stu-id="d1414-106">BizTalk Server uses batching to:</span></span>  
  
-   <span data-ttu-id="d1414-107">Amortizar el costo de las transacciones entre varios mensajes.</span><span class="sxs-lookup"><span data-stu-id="d1414-107">Amortize the cost of the transaction across many messages.</span></span>  
  
-   <span data-ttu-id="d1414-108">Aumentar la velocidad mediante la reducción del número interno de ciclos de ida y vuelta de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1414-108">Increase speed by reducing the internal number of database round trips.</span></span>  
  
-   <span data-ttu-id="d1414-109">Optimizar el empleo del grupo de subprocesos de BizTalk Server mediante la API asíncrona de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d1414-109">Make more efficient use of the BizTalk Server thread pool by using the BizTalk Server Asynchronous API.</span></span>  
  
## <a name="applying-batching"></a><span data-ttu-id="d1414-110">Aplicar el procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="d1414-110">Applying Batching</span></span>  
 <span data-ttu-id="d1414-111">El procesamiento por lotes se configura en las propiedades avanzadas de una ubicación de recepción y se activa de forma automática en el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="d1414-111">Batching is configured in the advanced properties for a receive location and is enabled automatically on the send port side.</span></span>  
  
## <a name="lowering-the-batch-size"></a><span data-ttu-id="d1414-112">Reducir el tamaño del lote</span><span class="sxs-lookup"><span data-stu-id="d1414-112">Lowering the Batch Size</span></span>  
 <span data-ttu-id="d1414-113">Debe reducir el tamaño de lote en las instancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1414-113">You should lower the batch size if in the following instances:</span></span>  
  
-   <span data-ttu-id="d1414-114">Al procesar mensajes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="d1414-114">When processing large messages</span></span>  
  
-   <span data-ttu-id="d1414-115">Cuando los ciclos de ida y vuelta de base de datos no forman el cuello de botella.</span><span class="sxs-lookup"><span data-stu-id="d1414-115">When database round trips are not your bottleneck</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1414-116">Tenga cuidado al cambiar la **LargeMessageThreshold** configuración.</span><span class="sxs-lookup"><span data-stu-id="d1414-116">Be careful when changing the **LargeMessageThreshold** setting.</span></span> <span data-ttu-id="d1414-117">El tamaño de lote multiplicado por el tamaño promedio del mensaje debe ser menor que el **LargeMessageThreshold** configuración a menos que el tamaño del lote es 1.</span><span class="sxs-lookup"><span data-stu-id="d1414-117">The batch size multiplied by the average message size should be less than the **LargeMessageThreshold** setting unless the batch size is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1414-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1414-118">See Also</span></span>  
 <span data-ttu-id="d1414-119">[El motor de mensajería](../core/the-messaging-engine.md) </span><span class="sxs-lookup"><span data-stu-id="d1414-119">[The Messaging Engine](../core/the-messaging-engine.md) </span></span>  
 <span data-ttu-id="d1414-120">[Mensajes por lotes para el proceso de recepción](../core/batching-messages-for-receive-processing.md) </span><span class="sxs-lookup"><span data-stu-id="d1414-120">[Batching Messages for Receive Processing](../core/batching-messages-for-receive-processing.md) </span></span>  
 [<span data-ttu-id="d1414-121">Procesamiento por lotes de mensajes para el procesamiento de envío</span><span class="sxs-lookup"><span data-stu-id="d1414-121">Batching Messages for Send Processing</span></span>](../core/batching-messages-for-send-processing.md)