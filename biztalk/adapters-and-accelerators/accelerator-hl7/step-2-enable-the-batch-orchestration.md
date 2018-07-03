---
title: 'Paso 2: Habilitar la orquestación por lotes | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4badf807-f461-4d0a-a3b6-9f671e580d91
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b44dd71c44f2510b6ccd80a731dd21739ed7055
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996173"
---
# <a name="step-2-enable-the-batch-orchestration"></a><span data-ttu-id="b70bd-102">Paso 2: Habilitar la orquestación del lote</span><span class="sxs-lookup"><span data-stu-id="b70bd-102">Step 2: Enable the Batch Orchestration</span></span>
<span data-ttu-id="b70bd-103">La orquestación del lote controla el proceso por lotes de crear.</span><span class="sxs-lookup"><span data-stu-id="b70bd-103">The batch orchestration controls the create batch process.</span></span> <span data-ttu-id="b70bd-104">Mantiene las referencias de todos los mensajes que se incluirán en el lote, controla la transacción por lotes saliente, genera el mensaje de lote, enruta el lote saliente y procesa por lotes confirmación entrantes.</span><span class="sxs-lookup"><span data-stu-id="b70bd-104">It maintains references for all messages to be included in the batch, controls the outbound batch transaction, generates the batch message, routes the outgoing batch, and processes incoming acknowledgment batches.</span></span> <span data-ttu-id="b70bd-105">Deberá dar de alta la orquestación del lote para el proceso por lotes de crear para que funcione.</span><span class="sxs-lookup"><span data-stu-id="b70bd-105">You need to enlist the batch orchestration for the create batch process to work.</span></span>  
  
### <a name="to-enable-the-batch-orchestration"></a><span data-ttu-id="b70bd-106">Para habilitar la orquestación del lote</span><span class="sxs-lookup"><span data-stu-id="b70bd-106">To enable the batch orchestration</span></span>  
  
1. <span data-ttu-id="b70bd-107">En la consola de administración de BizTalk, haga clic en **orquestaciones**, haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b70bd-107">In the BizTalk Administration Console, click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="b70bd-108">En el cuadro de diálogo Propiedades de orquestación, en el árbol de consola, haga clic en **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="b70bd-108">In the Orchestration Properties dialog box, in the console tree, click **Bindings**.</span></span>  
  
3. <span data-ttu-id="b70bd-109">En el **enlaces** panel, para **Host**, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="b70bd-109">In the **Bindings** pane, for **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="b70bd-110">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b70bd-110">Click **OK**.</span></span>  
  
4. <span data-ttu-id="b70bd-111">En la consola de administración de BizTalk, haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, haga clic en **Enlist**.</span><span class="sxs-lookup"><span data-stu-id="b70bd-111">In the BizTalk Administration Console, right-click **BatchOrchestration.Orchestration_1**, and then click **Enlist**.</span></span>  
  
   <span data-ttu-id="b70bd-112">Continúe con [paso 3: crear y configurar una entidad de destino](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md).</span><span class="sxs-lookup"><span data-stu-id="b70bd-112">Proceed to [Step 3: Create and Configure a Destination Party](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md).</span></span>