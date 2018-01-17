---
title: "Paso 6: Crear el puerto de envío para el lote de confirmación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2a0f1ee-e060-4fb9-923e-ebe8168777d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 958746634776e9b01c32ff2425122312bc7a841c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="step-6-create-the-send-port-for-the-acknowledgment-batch"></a><span data-ttu-id="ff4c7-102">Paso 6: Crear el puerto de envío para el lote de confirmación</span><span class="sxs-lookup"><span data-stu-id="ff4c7-102">Step 6: Create the Send Port for the Acknowledgment Batch</span></span>
<span data-ttu-id="ff4c7-103">En este paso, creará un puerto de envío para entregar el lote de confirmación que cree para la entidad de origen.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-103">In this step, you create a send port to deliver the acknowledgment batch that you create to the source party.</span></span> <span data-ttu-id="ff4c7-104">Se trata de un puerto unidireccional estático con un tipo de adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-104">This is a static one-way port with a FILE adapter type.</span></span> <span data-ttu-id="ff4c7-105">Designar una carpeta de archivos para el origen (\Tutorial_BatchACKDrop), donde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se quitará el archivo por lotes de confirmación.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-105">You designate a file folder for the source (\Tutorial_BatchACKDrop), where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will drop the acknowledgment batch file.</span></span> <span data-ttu-id="ff4c7-106">Defina un filtro para el puerto que indica qué tipo de lotes de confirmación que enviará los puertos.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-106">You define a filter for the port indicating what type of acknowledgment batches the ports will send.</span></span> <span data-ttu-id="ff4c7-107">El filtro especifica el origen de Tutorial_BatchSource y el tipo de mensaje de OutboundBatch.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-107">The filter specifies the source of Tutorial_BatchSource and the message type of OutboundBatch.</span></span>  
  
### <a name="to-create-the-send-port-for-the-acknowledgment-batch"></a><span data-ttu-id="ff4c7-108">Para crear el puerto de envío para el lote de confirmación</span><span class="sxs-lookup"><span data-stu-id="ff4c7-108">To create the send port for the acknowledgment batch</span></span>  
  
1.  <span data-ttu-id="ff4c7-109">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-109">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="ff4c7-110">En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4c7-110">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="ff4c7-111">Use</span><span class="sxs-lookup"><span data-stu-id="ff4c7-111">Use this</span></span>|<span data-ttu-id="ff4c7-112">Para</span><span class="sxs-lookup"><span data-stu-id="ff4c7-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ff4c7-113">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-113">**Name**</span></span>|<span data-ttu-id="ff4c7-114">Tipo de **Tutorial_BatchSource**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-114">Type **Tutorial_BatchSource**.</span></span>|  
    |<span data-ttu-id="ff4c7-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-115">**Type**</span></span>|<span data-ttu-id="ff4c7-116">Seleccione **archivo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-116">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ff4c7-117">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-117">**Configure**</span></span>|<span data-ttu-id="ff4c7-118">Haga clic en **configurar** para abrir el cuadro de diálogo Propiedades de transporte de archivo.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-118">Click **Configure** to open the FILE Transport Properties dialog box.</span></span>|  
  
3.  <span data-ttu-id="ff4c7-119">En el cuadro de diálogo Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4c7-119">In the FILE Transport Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="ff4c7-120">Use</span><span class="sxs-lookup"><span data-stu-id="ff4c7-120">Use this</span></span>|<span data-ttu-id="ff4c7-121">Para</span><span class="sxs-lookup"><span data-stu-id="ff4c7-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ff4c7-122">**Carpeta de destino**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-122">**Destination folder**</span></span>|<span data-ttu-id="ff4c7-123">Vaya a  **\< *unidad*:\>\Program BizTalk \<versión\> Acelerador para HL7\SDK\End-to-End Tutorial\Tutorial_BatchACKDrop**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-123">Browse to **\<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BatchACKDrop**.</span></span> <span data-ttu-id="ff4c7-124">Se trata de la ruta de acceso a la ubicación en el sistema de archivos o un recurso compartido público al que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] escribirá el archivo que contiene el lote de confirmación.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-124">This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file containing the acknowledgment batch.</span></span>|  
    |<span data-ttu-id="ff4c7-125">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-125">**File name**</span></span>|<span data-ttu-id="ff4c7-126">Tipo de **%MessageID%.txt** (reemplazar la extensión .xml con la extensión .txt).</span><span class="sxs-lookup"><span data-stu-id="ff4c7-126">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
    |<span data-ttu-id="ff4c7-127">**Modo de copia**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-127">**Copy mode**</span></span>|<span data-ttu-id="ff4c7-128">Seleccione **crear nuevos**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-128">Select **Create New**.</span></span>|  
  
4.  <span data-ttu-id="ff4c7-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-129">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="ff4c7-130">En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-130">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
6.  <span data-ttu-id="ff4c7-131">En el árbol de consola, haga clic en **filtros**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4c7-131">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="ff4c7-132">Use</span><span class="sxs-lookup"><span data-stu-id="ff4c7-132">Use this</span></span>|<span data-ttu-id="ff4c7-133">Para</span><span class="sxs-lookup"><span data-stu-id="ff4c7-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ff4c7-134">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-134">**Property**</span></span>|<span data-ttu-id="ff4c7-135">Haga clic en el campo **propiedad**y, a continuación, seleccione **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-135">Click the field under **Property**, and then select **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ff4c7-136">**Operador**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-136">**Operator**</span></span>|<span data-ttu-id="ff4c7-137">Deje  **==**  como el operador.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-137">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="ff4c7-138">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-138">**Value**</span></span>|<span data-ttu-id="ff4c7-139">Tipo de **Tutorial_BatchSource**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-139">Type **Tutorial_BatchSource**.</span></span>|  
    |<span data-ttu-id="ff4c7-140">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-140">**Group By**</span></span>|<span data-ttu-id="ff4c7-141">Seleccione **y** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-141">Select **And** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ff4c7-142">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-142">**Property**</span></span>|<span data-ttu-id="ff4c7-143">Seleccione **BTAHL7Schemas.BTAHL7MessageType**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-143">Select **BTAHL7Schemas.BTAHL7MessageType**.</span></span>|  
    |<span data-ttu-id="ff4c7-144">**Operador**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-144">**Operator**</span></span>|<span data-ttu-id="ff4c7-145">Deje  **==**  como el operador.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-145">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="ff4c7-146">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-146">**Value**</span></span>|<span data-ttu-id="ff4c7-147">Tipo de **OutboundBatch**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-147">Type **OutboundBatch**.</span></span>|  
  
7.  <span data-ttu-id="ff4c7-148">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-148">Press **Enter**.</span></span> <span data-ttu-id="ff4c7-149">En el panel en la parte inferior del cuadro de diálogo, compruebe que escribió correctamente la expresión de filtro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-149">In the pane at the bottom of the dialog box, verify that you entered the filter expression correctly, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="ff4c7-150">En la consola de administración de BizTalk, seleccione **puertos de envío**, haga clic en **Tutorial_BatchSource**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-150">In the BizTalk Administration Console, select **Send Ports**, right-click **Tutorial_BatchSource**, and then click **Start**.</span></span>  
  
### <a name="to-associate-the-send-port-with-the-source-party"></a><span data-ttu-id="ff4c7-151">Para asociar el puerto de envío a la entidad de origen</span><span class="sxs-lookup"><span data-stu-id="ff4c7-151">To associate the send port with the source party</span></span>  
  
1.  <span data-ttu-id="ff4c7-152">En la consola de administración de BizTalk, haga clic en **partes**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-152">In the BizTalk Administration Console, click **Parties**.</span></span> <span data-ttu-id="ff4c7-153">Haga clic en **Tutorial_BatchSource**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-153">Right-click **Tutorial_BatchSource**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ff4c7-154">En el cuadro de diálogo Propiedades de la entidad, haga clic en **puertos de envío** en el árbol de consola.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-154">In the Party Properties dialog box, click **Send Ports** in the console tree.</span></span> <span data-ttu-id="ff4c7-155">Para **puertos de envío**, seleccione **Tutorial_BatchSource** desde la lista desplegable y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff4c7-155">For **Send Ports**, select **Tutorial_BatchSource** from the drop-down list, and then click **OK**.</span></span>  
  
 <span data-ttu-id="ff4c7-156">Continúe con [paso 7: iniciar la orquestación y reiniciar el servidor BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="ff4c7-156">Proceed to [Step 7: Start the Orchestration and Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md).</span></span>