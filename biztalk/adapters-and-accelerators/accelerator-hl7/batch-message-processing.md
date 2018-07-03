---
title: Procesamiento de mensajes por lotes | Microsoft Docs
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
ms.openlocfilehash: 75cde12720ac67d74396c22282bddaf53e015960
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972373"
---
# <a name="batch-message-processing"></a><span data-ttu-id="d739a-102">Procesamiento de mensajes por lotes</span><span class="sxs-lookup"><span data-stu-id="d739a-102">Batch Message Processing</span></span>
<span data-ttu-id="d739a-103">Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) controla tres tipos de HL7 2.X escenarios de batch:</span><span class="sxs-lookup"><span data-stu-id="d739a-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) handles three types of HL7 2.X batch scenarios:</span></span>  
  
- <span data-ttu-id="d739a-104">Escenario de lote de entrada fragmentado.</span><span class="sxs-lookup"><span data-stu-id="d739a-104">Fragmented inbound batch scenario.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="d739a-105"> analiza estos lotes en los mensajes de salida independientes.</span><span class="sxs-lookup"><span data-stu-id="d739a-105"> parses these batches into separate output messages.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="d739a-106"> envía la confirmación (ACK) para cada mensaje en un lote fragmentado.</span><span class="sxs-lookup"><span data-stu-id="d739a-106"> sends acknowledgments (ACKs) for each message in a fragmented batch.</span></span>  
  
- <span data-ttu-id="d739a-107">Procesar por lotes en / lote escenario.</span><span class="sxs-lookup"><span data-stu-id="d739a-107">Batch in/batch out scenario.</span></span> <span data-ttu-id="d739a-108">Se trata de en enlace procesa por lotes que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no fragmentar, pero pasa y envía como un lote intacto.</span><span class="sxs-lookup"><span data-stu-id="d739a-108">These are in-bound batches that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not fragment, but passes through and sends as an intact batch.</span></span> <span data-ttu-id="d739a-109">Si [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación para el lote, la confirmación incluye un identificador de versión.</span><span class="sxs-lookup"><span data-stu-id="d739a-109">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK for the batch, the ACK includes a version ID.</span></span>  
  
- <span data-ttu-id="d739a-110">Escenario de creación de lote.</span><span class="sxs-lookup"><span data-stu-id="d739a-110">Create-batch scenario.</span></span> <span data-ttu-id="d739a-111">En este escenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] combina distintos mensajes de entrada en un lote de salida.</span><span class="sxs-lookup"><span data-stu-id="d739a-111">In this scenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] combines separate input messages into an output batch.</span></span>  
  
  <span data-ttu-id="d739a-112">Puede dar formato a los lotes de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="d739a-112">You can format batches in either of two ways:</span></span>  
  
- <span data-ttu-id="d739a-113">Con un encabezado de archivo y finalizador (FHS/FTS) y un lote encabezado y finalizador (BHS/BTS).</span><span class="sxs-lookup"><span data-stu-id="d739a-113">With a file header and trailer (FHS/FTS) and a batch header and trailer (BHS/BTS).</span></span>  
  
- <span data-ttu-id="d739a-114">Con ningún archivo o proceso por lotes encabezados/finalizadores.</span><span class="sxs-lookup"><span data-stu-id="d739a-114">With no file or batch headers/trailers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d739a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d739a-115">See Also</span></span>  
 <span data-ttu-id="d739a-116">[Mensaje de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="d739a-116">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
 <span data-ttu-id="d739a-117">[Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="d739a-117">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 <span data-ttu-id="d739a-118">[Parte 1: Escenario de lote de entrada fragmentado](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d739a-118">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 <span data-ttu-id="d739a-119">[Parte 2: Proceso por lotes en / escenario de lote](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d739a-119">[Part 2: Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span></span>  
 <span data-ttu-id="d739a-120">[Parte 3: Escenario de creación de lote](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d739a-120">[Part 3: Create-Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span></span>  
 [<span data-ttu-id="d739a-121">Procesamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="d739a-121">Message Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)