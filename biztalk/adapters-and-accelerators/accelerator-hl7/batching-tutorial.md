---
title: Tutorial de procesamiento por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching tutorial
- tutorials, batching tutorial
- batching tutorial, about the tutorial
- batching, tutorial
ms.assetid: e9010638-74cf-47cd-8cc9-9d6fd08a1b8d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 790303ac2026cbbce2fdb1c436e3dc8c7e9ff7f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980093"
---
# <a name="batching-tutorial"></a><span data-ttu-id="98778-102">Tutorial de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="98778-102">Batching Tutorial</span></span>
<span data-ttu-id="98778-103">Este tutorial proporciona procedimientos paso a paso para usar Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para recibir y enviar los mensajes procesados por lotes.</span><span class="sxs-lookup"><span data-stu-id="98778-103">This tutorial provides step-by-step procedures for using Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to receive and send batched messages.</span></span> <span data-ttu-id="98778-104">Procesamiento por lotes implica la recepción o el envío de un grupo de mensajes individuales (o las confirmaciones) como un solo mensaje compuesto.</span><span class="sxs-lookup"><span data-stu-id="98778-104">Batching involves receiving and/or sending a group of individual messages (or acknowledgments) as a single composite message.</span></span>  
  
 <span data-ttu-id="98778-105">BTAHL7 admite los siguientes tres escenarios de procesamiento por lotes de mensajes:</span><span class="sxs-lookup"><span data-stu-id="98778-105">BTAHL7 supports the following three message batching scenarios:</span></span>  
  
- <span data-ttu-id="98778-106">**Lote de entrada fragmentado**.</span><span class="sxs-lookup"><span data-stu-id="98778-106">**Fragmented inbound batch**.</span></span> <span data-ttu-id="98778-107">En este escenario, BTAHL7 recibe un lote de mensajes de HL7 y, a continuación, enruta los mensajes individuales para el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="98778-107">In this scenario, BTAHL7 receives an HL7 message batch, and then routes the individual messages to the destination system.</span></span>  
  
- <span data-ttu-id="98778-108">**Procesar por lotes en o salida**. BTAHL7 recibe un lote de mensajes HL7, comprueba los mensajes individuales dentro del lote y, a continuación, enruta el lote de mensajes en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="98778-108">**Batch in/batch out**. BTAHL7 receives an HL7 message batch, verifies the individual messages within the batch, and then routes the message batch to the destination system.</span></span>  
  
- <span data-ttu-id="98778-109">**Creación de lote (o el procesamiento por lotes saliente)**.</span><span class="sxs-lookup"><span data-stu-id="98778-109">**Create batch (or outbound batching)**.</span></span> <span data-ttu-id="98778-110">BTAHL7 recibe los mensajes individuales y crea los lotes antes de enrutarlos al sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="98778-110">BTAHL7 receives individual messages and batches them before routing them to the destination system.</span></span>  
  
  <span data-ttu-id="98778-111">Este tutorial incluye elementos para cada uno de los tres escenarios de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="98778-111">This tutorial includes parts for each of the three batching scenarios.</span></span> <span data-ttu-id="98778-112">Use las tres partes del tutorial en el orden indicado; parte 1 contiene pasos de requisitos previos para la parte 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="98778-112">Use the three parts of the tutorial in the order provided; part 1 contains prerequisite steps for part 2 and part 3.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98778-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="98778-113">In This Section</span></span>  
  
-   [<span data-ttu-id="98778-114">Preparación para usar el tutorial de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="98778-114">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)  
  
-   [<span data-ttu-id="98778-115">Parte 1: Escenario de lote de entrada fragmentado</span><span class="sxs-lookup"><span data-stu-id="98778-115">Part 1: Fragmented Inbound Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)  
  
-   [<span data-ttu-id="98778-116">Parte 2: Escenario de lote de entrada o salida</span><span class="sxs-lookup"><span data-stu-id="98778-116">Part 2: Batch In/Batch Out Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)  
  
-   [<span data-ttu-id="98778-117">Parte 3: Escenario de creación de lote</span><span class="sxs-lookup"><span data-stu-id="98778-117">Part 3: Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)