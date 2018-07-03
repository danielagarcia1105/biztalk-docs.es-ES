---
title: Orquestación de lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, acknowledgements
- acknowledgements, batching
- batch orchestration
- orchestrations, batch orchestration
- messages, batching
- batching, batch orchestration
- batching, messages
ms.assetid: b449d8d5-72a2-46c8-a2b1-380431175f4d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2271170d91990e5874168a18ed274c1502a93158
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971597"
---
# <a name="batch-orchestration"></a><span data-ttu-id="d765e-102">Orquestación del lote</span><span class="sxs-lookup"><span data-stu-id="d765e-102">Batch Orchestration</span></span>
<span data-ttu-id="d765e-103">Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) proporciona una orquestación (BatchOrchestration.dll) que puede usar para procesar lotes.</span><span class="sxs-lookup"><span data-stu-id="d765e-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) provides an orchestration (BatchOrchestration.dll) that you can use to process batches.</span></span> <span data-ttu-id="d765e-104">Esta orquestación puede procesar lotes de mensajes con codificación HL7 (2.X) o la confirmación (ACK).</span><span class="sxs-lookup"><span data-stu-id="d765e-104">This orchestration can process batches of HL7-encoded (2.X) messages and/or acknowledgments (ACKs).</span></span> <span data-ttu-id="d765e-105">La orquestación es nativo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orquestación agregada [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] de instalación para el conjunto de orquestaciones de BizTalk (como se muestra en las orquestaciones en el Explorador de BizTalk).</span><span class="sxs-lookup"><span data-stu-id="d765e-105">The orchestration is a native [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orchestration added by [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup to your set of BizTalk orchestrations (as listed under Orchestrations in BizTalk Explorer).</span></span>  
  
 <span data-ttu-id="d765e-106">La orquestación funciona con la activación por lotes, la terminación de lotes, y los mensajes de temporizador de lote que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] usa para controlar los lotes.</span><span class="sxs-lookup"><span data-stu-id="d765e-106">The orchestration works with batch activation, batch termination, and batch timer messages that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] uses to control batches.</span></span> <span data-ttu-id="d765e-107">La orquestación también funciona con el puerto de control de proceso por lotes, que es una recepción de puerto que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] programa de instalación instala para controlar los mensajes de control de proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="d765e-107">The orchestration also works with the batch control port, which is a receive port that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup installs to handle batch control messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d765e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="d765e-108">See Also</span></span>  
 <span data-ttu-id="d765e-109">[Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="d765e-109">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 [<span data-ttu-id="d765e-110">Acelerador de BizTalk para componentes de HL7</span><span class="sxs-lookup"><span data-stu-id="d765e-110">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)