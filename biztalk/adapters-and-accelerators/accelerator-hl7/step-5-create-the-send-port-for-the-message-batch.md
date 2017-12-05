---
title: "Paso 5: Crear el puerto de envío para el lote de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5db815df-5b76-4ba4-99ab-c7766b0c301a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5749166c8a9b34d5e5a04849c4179ac4427201c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="step-5-create-the-send-port-for-the-message-batch"></a><span data-ttu-id="57e55-102">Paso 5: Crear el puerto de envío para el lote de mensajes</span><span class="sxs-lookup"><span data-stu-id="57e55-102">Step 5: Create the Send Port for the Message Batch</span></span>
<span data-ttu-id="57e55-103">En este paso, creará un puerto de envío para entregar el lote de mensajes que cree para la entidad de destino.</span><span class="sxs-lookup"><span data-stu-id="57e55-103">In this step, you create a send port to deliver the message batch that you create to the destination party.</span></span> <span data-ttu-id="57e55-104">Se trata de un puerto unidireccional estático con un tipo de adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="57e55-104">This is a static one-way port with a FILE adapter type.</span></span> <span data-ttu-id="57e55-105">Designar una carpeta de archivos para el destino (\Tutorial_BatchMsgDrop) donde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se quitará el archivo por lotes de mensajes.</span><span class="sxs-lookup"><span data-stu-id="57e55-105">You designate a file folder for the destination (\Tutorial_BatchMsgDrop) where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will drop the message batch file.</span></span> <span data-ttu-id="57e55-106">Defina un filtro para el puerto que indica qué tipo de lotes de mensajes que enviará los puertos.</span><span class="sxs-lookup"><span data-stu-id="57e55-106">You define a filter for the port indicating what type of message batches the ports will send.</span></span> <span data-ttu-id="57e55-107">El filtro especifica el destino de Tutorial_BatchDest y el tipo de mensaje de OutboundBatch.</span><span class="sxs-lookup"><span data-stu-id="57e55-107">The filter specifies the destination of Tutorial_BatchDest and the message type of OutboundBatch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57e55-108">Cuando se ejecuta esta parte del tutorial, puede simplificar los resultados al detener el puerto de envío que se usa en la parte 2 del tutorial: el **Tutorial_BTAHL7Drop** puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="57e55-108">When running this part of the tutorial, you can simplify the results by stopping the send port used in Part 2 of the tutorial: the **Tutorial_BTAHL7Drop** send port.</span></span>  
  
### <a name="to-create-the-send-port-for-the-message-batch"></a><span data-ttu-id="57e55-109">Para crear el puerto de envío para el lote de mensajes</span><span class="sxs-lookup"><span data-stu-id="57e55-109">To create the send port for the message batch</span></span>  
  
1.  <span data-ttu-id="57e55-110">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="57e55-110">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="57e55-111">En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57e55-111">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="57e55-112">Use</span><span class="sxs-lookup"><span data-stu-id="57e55-112">Use this</span></span>|<span data-ttu-id="57e55-113">Para</span><span class="sxs-lookup"><span data-stu-id="57e55-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="57e55-114">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="57e55-114">**Name**</span></span>|<span data-ttu-id="57e55-115">Tipo de **Tutorial_BatchDest**.</span><span class="sxs-lookup"><span data-stu-id="57e55-115">Type **Tutorial_BatchDest**.</span></span>|  
    |<span data-ttu-id="57e55-116">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="57e55-116">**Type**</span></span>|<span data-ttu-id="57e55-117">Seleccione **archivo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="57e55-117">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="57e55-118">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="57e55-118">**Configure**</span></span>|<span data-ttu-id="57e55-119">Haga clic en **configurar** para abrir el cuadro de diálogo Propiedades de transporte de archivo.</span><span class="sxs-lookup"><span data-stu-id="57e55-119">Click **Configure** to open the FILE Transport Properties dialog box.</span></span>|  
  
3.  <span data-ttu-id="57e55-120">En el **propiedades de transporte de archivo** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57e55-120">In the **FILE Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="57e55-121">Use</span><span class="sxs-lookup"><span data-stu-id="57e55-121">Use this</span></span>|<span data-ttu-id="57e55-122">Para</span><span class="sxs-lookup"><span data-stu-id="57e55-122">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="57e55-123">**Carpeta de destino**</span><span class="sxs-lookup"><span data-stu-id="57e55-123">**Destination folder**</span></span>|<span data-ttu-id="57e55-124">Vaya a  **\<* unidad*:\>\Program BizTalk \<versión\> Acelerador para Tutorial\Tutorial_ HL7\SDK\End-to-End BatchMsgDrop **.</span><span class="sxs-lookup"><span data-stu-id="57e55-124">Browse to **\<*drive*:\>\Program Files\Microsoft  BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BatchMsgDrop**.</span></span> <span data-ttu-id="57e55-125">Se trata de la ruta de acceso a la ubicación en el sistema de archivos o un recurso compartido público al que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] escribirá el archivo que contiene el lote de mensajes.</span><span class="sxs-lookup"><span data-stu-id="57e55-125">This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file containing the message batch.</span></span>|  
    |<span data-ttu-id="57e55-126">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="57e55-126">**File name**</span></span>|<span data-ttu-id="57e55-127">Tipo de **%MessageID%.txt** (reemplazar la extensión .xml con la extensión .txt).</span><span class="sxs-lookup"><span data-stu-id="57e55-127">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
    |<span data-ttu-id="57e55-128">**Modo de copia**</span><span class="sxs-lookup"><span data-stu-id="57e55-128">**Copy mode**</span></span>|<span data-ttu-id="57e55-129">Seleccione **crear nuevos**.</span><span class="sxs-lookup"><span data-stu-id="57e55-129">Select **Create New**.</span></span>|  
  
4.  <span data-ttu-id="57e55-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="57e55-130">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="57e55-131">En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="57e55-131">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
6.  <span data-ttu-id="57e55-132">En el árbol de consola, haga clic en **filtros**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57e55-132">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="57e55-133">Use</span><span class="sxs-lookup"><span data-stu-id="57e55-133">Use this</span></span>|<span data-ttu-id="57e55-134">Para</span><span class="sxs-lookup"><span data-stu-id="57e55-134">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="57e55-135">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="57e55-135">**Property**</span></span>|<span data-ttu-id="57e55-136">Haga clic en el campo **propiedad**y, a continuación, seleccione **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="57e55-136">Click the field under **Property**, and then select **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** from the drop-down list.</span></span>|  
    |<span data-ttu-id="57e55-137">**Operador**</span><span class="sxs-lookup"><span data-stu-id="57e55-137">**Operator**</span></span>|<span data-ttu-id="57e55-138">Deje  **==**  como el operador.</span><span class="sxs-lookup"><span data-stu-id="57e55-138">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="57e55-139">**Valor**</span><span class="sxs-lookup"><span data-stu-id="57e55-139">**Value**</span></span>|<span data-ttu-id="57e55-140">Tipo de **Tutorial_BatchDest**.</span><span class="sxs-lookup"><span data-stu-id="57e55-140">Type **Tutorial_BatchDest**.</span></span>|  
    |<span data-ttu-id="57e55-141">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="57e55-141">**Group By**</span></span>|<span data-ttu-id="57e55-142">Seleccione **y** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="57e55-142">Select **And** from the drop-down list.</span></span>|  
    |<span data-ttu-id="57e55-143">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="57e55-143">**Property**</span></span>|<span data-ttu-id="57e55-144">Seleccione **BTAHL7Schemas.BTAHL7MessageType**.</span><span class="sxs-lookup"><span data-stu-id="57e55-144">Select **BTAHL7Schemas.BTAHL7MessageType**.</span></span>|  
    |<span data-ttu-id="57e55-145">**Operador**</span><span class="sxs-lookup"><span data-stu-id="57e55-145">**Operator**</span></span>|<span data-ttu-id="57e55-146">Deje  **==**  como el operador.</span><span class="sxs-lookup"><span data-stu-id="57e55-146">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="57e55-147">**Valor**</span><span class="sxs-lookup"><span data-stu-id="57e55-147">**Value**</span></span>|<span data-ttu-id="57e55-148">Tipo de **OutboundBatch**.</span><span class="sxs-lookup"><span data-stu-id="57e55-148">Type **OutboundBatch**.</span></span>|  
  
7.  <span data-ttu-id="57e55-149">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="57e55-149">Press **Enter**.</span></span> <span data-ttu-id="57e55-150">En el panel en la parte inferior del cuadro de diálogo, compruebe que escribió correctamente la expresión de filtro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="57e55-150">In the pane at the bottom of the dialog box, verify that you entered the filter expression correctly, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="57e55-151">En la consola de administración de BizTalk, seleccione **puertos de envío**, haga clic en **Tutorial_BatchDest**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="57e55-151">In the BizTalk Administration Console, select **Send Ports**, right-click **Tutorial_BatchDest**, and then click **Start**.</span></span>  
  
### <a name="to-associate-the-send-port-with-the-destination-party"></a><span data-ttu-id="57e55-152">Para asociar el puerto de envío a la entidad de destino</span><span class="sxs-lookup"><span data-stu-id="57e55-152">To associate the send port with the destination party</span></span>  
  
1.  <span data-ttu-id="57e55-153">En la consola de administración de BizTalk Server, expanda **partes**, haga clic en **Tutorial_BatchDest**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="57e55-153">In the BizTalk Server Administration Console, expand **Parties**, click **Tutorial_BatchDest**, and then right-click **Properties**.</span></span>  
  
2.  <span data-ttu-id="57e55-154">En el cuadro de diálogo Propiedades de la entidad, haga clic en **puertos de envío** en el árbol de consola.</span><span class="sxs-lookup"><span data-stu-id="57e55-154">In the Party Properties dialog box, click  **Send Ports** in the console tree.</span></span>  <span data-ttu-id="57e55-155">Seleccione **Tutorial_BatchDest** desde la lista desplegable y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="57e55-155">Select **Tutorial_BatchDest** from the drop-down list, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="57e55-156">Si se produce una infracción de simultaneidad mientras el **Tutorial_DestBatch** actualización de la entidad, haga clic en **Aceptar** y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="57e55-156">If a concurrency violation occurs while the **Tutorial_DestBatch** party was being updated, click **OK** and close the dialog box.</span></span> <span data-ttu-id="57e55-157">En la consola de administración, haga clic en **grupo de BizTalk**, haga clic en **actualizar**y, a continuación, repita los pasos 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="57e55-157">In the Administration Console, right-click **BizTalk Group**, click **Refresh**, and then repeat steps 1 and 2.</span></span>  
  
 <span data-ttu-id="57e55-158">Continúe con [paso 6: crear el puerto de envío para el lote de confirmación](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md).</span><span class="sxs-lookup"><span data-stu-id="57e55-158">Proceed to [Step 6: Create the Send Port for the Acknowledgment Batch](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md).</span></span>