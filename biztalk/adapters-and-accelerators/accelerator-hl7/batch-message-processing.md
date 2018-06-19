---
title: Procesamiento de mensajes por lotes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, batching
- batching, examples
- batching, batch types
ms.assetid: 264f91b5-3e33-4b87-9da3-866eaa464b0f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aad80bb8fe9a59163ee17e7862bece728fdc52b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204764"
---
# <a name="batch-message-processing"></a><span data-ttu-id="56c66-102">Procesamiento de mensajes por lotes</span><span class="sxs-lookup"><span data-stu-id="56c66-102">Batch Message Processing</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="56c66-103">Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) controla tres tipos de HL7 2.X escenarios de lote:</span><span class="sxs-lookup"><span data-stu-id="56c66-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) handles three types of HL7 2.X batch scenarios:</span></span>  
  
-   <span data-ttu-id="56c66-104">Escenario de fragmentados por lotes entrantes.</span><span class="sxs-lookup"><span data-stu-id="56c66-104">Fragmented inbound batch scenario.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="56c66-105">estos lotes se analiza en mensajes de salida independientes.</span><span class="sxs-lookup"><span data-stu-id="56c66-105"> parses these batches into separate output messages.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="56c66-106">envía la confirmación (ACK) para cada mensaje en un lote fragmentado.</span><span class="sxs-lookup"><span data-stu-id="56c66-106"> sends acknowledgments (ACKs) for each message in a fragmented batch.</span></span>  
  
-   <span data-ttu-id="56c66-107">Procesar por lotes en / lote escenario.</span><span class="sxs-lookup"><span data-stu-id="56c66-107">Batch in/batch out scenario.</span></span> <span data-ttu-id="56c66-108">Se trata de entrada que procesa por lotes [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no fragmentar, pero pasa a través y envía un lote intactos.</span><span class="sxs-lookup"><span data-stu-id="56c66-108">These are in-bound batches that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not fragment, but passes through and sends as an intact batch.</span></span> <span data-ttu-id="56c66-109">Si [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación para el lote, la confirmación incluye un identificador de versión.</span><span class="sxs-lookup"><span data-stu-id="56c66-109">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK for the batch, the ACK includes a version ID.</span></span>  
  
-   <span data-ttu-id="56c66-110">Escenario de lote crear.</span><span class="sxs-lookup"><span data-stu-id="56c66-110">Create-batch scenario.</span></span> <span data-ttu-id="56c66-111">En este escenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] combina separar los mensajes de entrada en un lote de salida.</span><span class="sxs-lookup"><span data-stu-id="56c66-111">In this scenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] combines separate input messages into an output batch.</span></span>  
  
 <span data-ttu-id="56c66-112">Puede dar formato a los lotes de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="56c66-112">You can format batches in either of two ways:</span></span>  
  
-   <span data-ttu-id="56c66-113">Con un encabezado de archivo y finalizador (FHS/FTS) y un lote encabezado y finalizador (BHS/BTS).</span><span class="sxs-lookup"><span data-stu-id="56c66-113">With a file header and trailer (FHS/FTS) and a batch header and trailer (BHS/BTS).</span></span>  
  
-   <span data-ttu-id="56c66-114">Con ningún archivo o proceso por lotes encabezados/finalizadores.</span><span class="sxs-lookup"><span data-stu-id="56c66-114">With no file or batch headers/trailers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56c66-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="56c66-115">See Also</span></span>  
 <span data-ttu-id="56c66-116">[Procesamiento por lotes de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="56c66-116">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
 <span data-ttu-id="56c66-117">[Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="56c66-117">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 <span data-ttu-id="56c66-118">[Parte 1: Escenario de fragmentados por lotes entrantes](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="56c66-118">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 <span data-ttu-id="56c66-119">[Parte 2: Lote / escenario de lote](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="56c66-119">[Part 2: Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span></span>  
 <span data-ttu-id="56c66-120">[Parte 3: Escenario de lote crear](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="56c66-120">[Part 3: Create-Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span></span>  
 [<span data-ttu-id="56c66-121">Procesamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="56c66-121">Message Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)