---
title: 'Paso 3: Probar el lote en lote escenario | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c487d39d-b2be-41d4-963e-d0ee9ba169fb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d84c34eb3019f83ecd28f30425a93708affcecb2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a><span data-ttu-id="46d17-102">Paso 3: Probar el lote / escenario de lote</span><span class="sxs-lookup"><span data-stu-id="46d17-102">Step 3: Test the Batch In/Batch Out Scenario</span></span>
<span data-ttu-id="46d17-103">En este paso, comprobará que el lote en / lote Out tutorial quitar por una instancia de prueba del lote en / lote mensaje en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="46d17-103">In this step, you test the Batch In/Batch Out tutorial by dropping a test instance of the batch in/batch out message into a folder.</span></span> <span data-ttu-id="46d17-104">El puerto de envío que configuró enviará el mensaje, el puerto de recepción recibirá y la canalización de recepción lo procesará y lo coloque en la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="46d17-104">The send port that you set up will send the message, the receive port will receive it, and the receive pipeline will process it and drop it into the destination folder.</span></span>  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a><span data-ttu-id="46d17-105">Para probar el lote en / escenario de lote</span><span class="sxs-lookup"><span data-stu-id="46d17-105">To test the Batch In/Batch Out scenario</span></span>  
  
1.  <span data-ttu-id="46d17-106">Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\<* unidad*\>: \Batching Tutorial\Instances** carpeta.</span><span class="sxs-lookup"><span data-stu-id="46d17-106">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\Batching Tutorial\Instances** folder.</span></span>  
  
2.  <span data-ttu-id="46d17-107">Haga clic en **BatchInBatchOut.txt**y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="46d17-107">Right click **BatchInBatchOut.txt**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="46d17-108">Vaya a la  **\<* unidad*\>: \Program BizTalk \<versión\> Acelerador para Tutorial\Tutorial_ HL7\SDK\End-to-End BTAHL7PickUp ** carpeta.</span><span class="sxs-lookup"><span data-stu-id="46d17-108">Browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp** folder.</span></span>  
  
4.  <span data-ttu-id="46d17-109">Haga clic en la carpeta y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="46d17-109">Right-click the folder, and then click **Paste**.</span></span>  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a><span data-ttu-id="46d17-110">Para comprobar los resultados del lote en / lote tutorial</span><span class="sxs-lookup"><span data-stu-id="46d17-110">To verify the results of the Batch In/Batch Out Tutorial</span></span>  
  
-   <span data-ttu-id="46d17-111">Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\<* unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\ Carpeta Tutorial\Tutorial_BTAHL7Drop ** SDK\End-to-End.</span><span class="sxs-lookup"><span data-stu-id="46d17-111">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop** folder.</span></span> <span data-ttu-id="46d17-112">Tras un breve período, debe ver la instancia del mensaje por lotes y una confirmación procesada, aparecen en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="46d17-112">After a short period, you should see the processed instance of the batch message, and an acknowledgment, appear in the folder.</span></span> <span data-ttu-id="46d17-113">Si no aparecen, compruebe el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="46d17-113">If they do not appear, check the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer for an error message.</span></span> <span data-ttu-id="46d17-114">Cada archivo debe tener un nombre diferente en el formulario \< *Guid*\>.txt.</span><span class="sxs-lookup"><span data-stu-id="46d17-114">Each file should have a different name in the form \<*Guid*\>.txt.</span></span>  
  
     <span data-ttu-id="46d17-115">El primer mensaje debe ser el lote que consta de dos mensajes.</span><span class="sxs-lookup"><span data-stu-id="46d17-115">The first message should be the batch consisting of two messages.</span></span> <span data-ttu-id="46d17-116">Acelerador de BizTalk para HL7 (BTAHL7) se incluyen estos dos mensajes secuencialmente en el archivo .txt.</span><span class="sxs-lookup"><span data-stu-id="46d17-116">BizTalk Accelerator for HL7 (BTAHL7) has included these two messages sequentially in the .txt file.</span></span> <span data-ttu-id="46d17-117">Este lote no contiene etiquetas BHS/BTS y FHS/FT.</span><span class="sxs-lookup"><span data-stu-id="46d17-117">This batch does not contain FHS/FTS and BHS/BTS tags.</span></span> <span data-ttu-id="46d17-118">Un lote debe contener cualquier todas las etiquetas FHS/FT y BHS/BTS o como este mensaje por lotes, no FHS/FT y sin etiquetas BHS/BTS.</span><span class="sxs-lookup"><span data-stu-id="46d17-118">A batch must contain either all FHS/FTS and BHS/BTS tags, or like this batch message, no FHS/FTS and no BHS/BTS tags.</span></span>  
  
    |<span data-ttu-id="46d17-119">MSH.9</span><span class="sxs-lookup"><span data-stu-id="46d17-119">MSH.9</span></span>|<span data-ttu-id="46d17-120">MSH.10</span><span class="sxs-lookup"><span data-stu-id="46d17-120">MSH.10</span></span>|<span data-ttu-id="46d17-121">MSH.3</span><span class="sxs-lookup"><span data-stu-id="46d17-121">MSH.3</span></span>|<span data-ttu-id="46d17-122">MSH.5</span><span class="sxs-lookup"><span data-stu-id="46d17-122">MSH.5</span></span>|  
    |-----------|------------|-----------|-----------|  
    |<span data-ttu-id="46d17-123">ADT ^ A03</span><span class="sxs-lookup"><span data-stu-id="46d17-123">ADT^A03</span></span>|<span data-ttu-id="46d17-124">000001</span><span class="sxs-lookup"><span data-stu-id="46d17-124">000001</span></span>|<span data-ttu-id="46d17-125">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="46d17-125">Tutorial_BatchSource</span></span>|<span data-ttu-id="46d17-126">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="46d17-126">MESA_IS</span></span>|  
    |<span data-ttu-id="46d17-127">ADT ^ A03</span><span class="sxs-lookup"><span data-stu-id="46d17-127">ADT^A03</span></span>|<span data-ttu-id="46d17-128">000002</span><span class="sxs-lookup"><span data-stu-id="46d17-128">000002</span></span>|<span data-ttu-id="46d17-129">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="46d17-129">Tutorial_BatchSource</span></span>|<span data-ttu-id="46d17-130">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="46d17-130">MESA_IS</span></span>|  
  
     <span data-ttu-id="46d17-131">El segundo mensaje debe ser una confirmación de aplicación único enviada como respuesta al mensaje por lotes, con los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="46d17-131">The second message should be a single application acknowledgment sent in response to the batch message, with the following fields:</span></span>  
  
    |<span data-ttu-id="46d17-132">MSH.9</span><span class="sxs-lookup"><span data-stu-id="46d17-132">MSH.9</span></span>|<span data-ttu-id="46d17-133">MSH.3</span><span class="sxs-lookup"><span data-stu-id="46d17-133">MSH.3</span></span>|<span data-ttu-id="46d17-134">MSH.5</span><span class="sxs-lookup"><span data-stu-id="46d17-134">MSH.5</span></span>|<span data-ttu-id="46d17-135">MSA.1</span><span class="sxs-lookup"><span data-stu-id="46d17-135">MSA.1</span></span>|<span data-ttu-id="46d17-136">MSA.2</span><span class="sxs-lookup"><span data-stu-id="46d17-136">MSA.2</span></span>|  
    |-----------|-----------|-----------|-----------|-----------|  
    |<span data-ttu-id="46d17-137">CONFIRMACIÓN ^ A03 ^ CONFIRMACIÓN</span><span class="sxs-lookup"><span data-stu-id="46d17-137">ACK^A03^ACK</span></span>|<span data-ttu-id="46d17-138">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="46d17-138">MESA_IS</span></span>|<span data-ttu-id="46d17-139">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="46d17-139">Tutorial_BatchSource</span></span>|<span data-ttu-id="46d17-140">AA</span><span class="sxs-lookup"><span data-stu-id="46d17-140">AA</span></span>|<span data-ttu-id="46d17-141">000001</span><span class="sxs-lookup"><span data-stu-id="46d17-141">000001</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46d17-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="46d17-142">See Also</span></span>  
 <span data-ttu-id="46d17-143">[Parte 1: Escenario de fragmentados por lotes entrantes](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="46d17-143">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 [<span data-ttu-id="46d17-144">Parte 3: Escenario de creación de lote</span><span class="sxs-lookup"><span data-stu-id="46d17-144">Part 3: Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)