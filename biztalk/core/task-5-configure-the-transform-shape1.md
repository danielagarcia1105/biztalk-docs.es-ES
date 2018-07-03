---
title: 'Tarea 5: Configurar la transformación de forma1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a73fd2-0f34-4681-8aed-7d54d69c86d3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e5b690774061e95fb34a070e19890d3a2a4eb0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003069"
---
# <a name="task-5-configure-the-transform-shape"></a><span data-ttu-id="66a9a-102">Tarea 5: Configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="66a9a-102">Task 5: Configure the Transform Shape</span></span>
<span data-ttu-id="66a9a-103">Utilice el siguiente procedimiento para configurar la forma Transformación.</span><span class="sxs-lookup"><span data-stu-id="66a9a-103">Use the following procedure to configure the Transform shape.</span></span>  
  
### <a name="to-configure-the-transform-shape"></a><span data-ttu-id="66a9a-104">Para configurar la forma Transformación</span><span class="sxs-lookup"><span data-stu-id="66a9a-104">To configure the Transform shape</span></span>  
  
1. <span data-ttu-id="66a9a-105">Arrastre una forma Construir mensaje después de ReceiveBeginDocResponse.</span><span class="sxs-lookup"><span data-stu-id="66a9a-105">Drag a Construct Message shape after ReceiveBeginDocResponse.</span></span>  
  
   - <span data-ttu-id="66a9a-106">**Mensajes construidos:** EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="66a9a-106">**Messages Constructed:** EditLineMsg</span></span>  
  
   - <span data-ttu-id="66a9a-107">**Nombre:** ConstructEditLineMessageWithData</span><span class="sxs-lookup"><span data-stu-id="66a9a-107">**Name:** ConstructEditLineMessageWithData</span></span>  
  
     <span data-ttu-id="66a9a-108">Haga clic en la parte central, seleccione **Insertar forma**y, a continuación, seleccione **transformar**.</span><span class="sxs-lookup"><span data-stu-id="66a9a-108">Right-click in the middle, select **Insert Shape**, and then select **Transform**.</span></span>  
  
     <span data-ttu-id="66a9a-109">![](../core/media/jde-insert-shape-transform.gif "JDE_insert_shape_transform")</span><span class="sxs-lookup"><span data-stu-id="66a9a-109">![](../core/media/jde-insert-shape-transform.gif "JDE_insert_shape_transform")</span></span>  
  
     <span data-ttu-id="66a9a-110">Mediante la forma Transformación, asigne datos a partir de los datos que se envían a los datos enviados.</span><span class="sxs-lookup"><span data-stu-id="66a9a-110">Using Transform, map data from the data you are sending to the data that is sent.</span></span>  
  
     <span data-ttu-id="66a9a-111">Para su entorno de trabajo, enviaría un documento (en lugar de BeginDoc) con todos los valores posibles, lo que le permite construir todos los mensajes posibles, BeginDoc, EditLine y EndDoc.</span><span class="sxs-lookup"><span data-stu-id="66a9a-111">For your work environment you would send a document (instead of BeginDoc) with all values possible allowing you to construct all possible messages, BeginDoc, EditLine, and EndDoc.</span></span> <span data-ttu-id="66a9a-112">Para este ejemplo, no obstante, sólo hay datos codificados.</span><span class="sxs-lookup"><span data-stu-id="66a9a-112">For this example, however, there is only hard coded data.</span></span>  
  
2. <span data-ttu-id="66a9a-113">Haga doble clic en **Transform_1** para abrir.</span><span class="sxs-lookup"><span data-stu-id="66a9a-113">Double-click **Transform_1** to open.</span></span>  
  
   1.  <span data-ttu-id="66a9a-114">Seleccione origen y haga clic en la fila agregar bajo **nombre de Variable** y seleccione **BeginDocResponseMsg**.</span><span class="sxs-lookup"><span data-stu-id="66a9a-114">Select Source and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
        <span data-ttu-id="66a9a-115">![](../core/media/jde-transform-source.gif "JDE_transform_source")</span><span class="sxs-lookup"><span data-stu-id="66a9a-115">![](../core/media/jde-transform-source.gif "JDE_transform_source")</span></span>  
  
   2.  <span data-ttu-id="66a9a-116">Seleccione **destino** y haga clic en la fila agregar bajo **nombre de Variable**, seleccione **EditLineMsg**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="66a9a-116">Select **Destination** and click in the Add row under **Variable Name**, select **EditLineMsg**, and click **OK**.</span></span>  
  
        <span data-ttu-id="66a9a-117">![](../core/media/jde-transform-destination.gif "JDE_transform_destination")</span><span class="sxs-lookup"><span data-stu-id="66a9a-117">![](../core/media/jde-transform-destination.gif "JDE_transform_destination")</span></span>  
  
3. <span data-ttu-id="66a9a-118">En el Explorador de soluciones, haga doble clic en **Transform_1.btm** para abrir la herramienta de asignación.</span><span class="sxs-lookup"><span data-stu-id="66a9a-118">In the Solution Explorer, double-click **Transform_1.btm** to open the mapping tool.</span></span> <span data-ttu-id="66a9a-119">Vincule los cuatro siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="66a9a-119">Link the following four items:</span></span>  
  
   - <span data-ttu-id="66a9a-120">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="66a9a-120">mnCMJobNo</span></span>  
  
   - <span data-ttu-id="66a9a-121">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="66a9a-121">szCMComputerID</span></span>  
  
   - <span data-ttu-id="66a9a-122">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="66a9a-122">mnProcessID</span></span>  
  
   - <span data-ttu-id="66a9a-123">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="66a9a-123">mnTransactionID</span></span>  
  
     <span data-ttu-id="66a9a-124">![](../core/media/jde-example-transformmapping.gif "JDE_example_transformmapping")</span><span class="sxs-lookup"><span data-stu-id="66a9a-124">![](../core/media/jde-example-transformmapping.gif "JDE_example_transformmapping")</span></span>  
  
     <span data-ttu-id="66a9a-125">Para facilitar su uso, este ejemplo tiene valores codificados.</span><span class="sxs-lookup"><span data-stu-id="66a9a-125">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="66a9a-126">Haga clic en el elemento del esquema de destino y establezca el siguiente valor.</span><span class="sxs-lookup"><span data-stu-id="66a9a-126">Click the item in the Destination Schema and set the following Value.</span></span>  
  
     <span data-ttu-id="66a9a-127">![](../core/media/jde-hardcoded-mapping-example.gif "JDE_hardcoded_mapping_example")</span><span class="sxs-lookup"><span data-stu-id="66a9a-127">![](../core/media/jde-hardcoded-mapping-example.gif "JDE_hardcoded_mapping_example")</span></span>  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:F4211FSEditLine xmlns:ns0="http://schemas.microsoft.com/  
         [JDE://CSALES/B4200310]">  
      <ns0:cCMLineAction>A</ns0:cCMLineAction>  
      <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
      <ns0:cCMWriteToWFFlag>2</ns0:cCMWriteToWFFlag>  
      <ns0:szItemNo>210</ns0:szItemNo>  
      <ns0:mnQtyOrdered>1</ns0:mnQtyOrdered>  
      <ns0:cSalesTaxableYN>N</ns0:cSalesTaxableYN>  
      <ns0:szTransactionUOM>EA</ns0:szTransactionUOM>  
      <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
      <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
   </ns0:F4211FSEditLine>  
   ```  
  
4. <span data-ttu-id="66a9a-128">Arrastre una forma Construir mensaje después de ReceiveEditLine.</span><span class="sxs-lookup"><span data-stu-id="66a9a-128">Drag a Construct Message after ReceiveEditLine.</span></span>  
  
   - <span data-ttu-id="66a9a-129">**Mensajes construidos:** EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="66a9a-129">**Messages Constructed:** EndDocMsg</span></span>  
  
   - <span data-ttu-id="66a9a-130">**Nombre:** ConstructEndDocMessageWithData</span><span class="sxs-lookup"><span data-stu-id="66a9a-130">**Name:** ConstructEndDocMessageWithData</span></span>  
  
     <span data-ttu-id="66a9a-131">Haga clic en el medio y seleccione **Insertar forma**y, a continuación, seleccione **transformar**.</span><span class="sxs-lookup"><span data-stu-id="66a9a-131">Right-click in the middle and select **Insert Shape**, and then select **Transform**.</span></span>  
  
5. <span data-ttu-id="66a9a-132">Haga doble clic en **Transform_2** para abrir.</span><span class="sxs-lookup"><span data-stu-id="66a9a-132">Double-click **Transform_2** to open.</span></span>  
  
   1.  <span data-ttu-id="66a9a-133">Seleccione **origen** y haga clic en la fila agregar bajo **nombre de Variable** y seleccione **BeginDocResponseMsg**.</span><span class="sxs-lookup"><span data-stu-id="66a9a-133">Select **Source** and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
   2.  <span data-ttu-id="66a9a-134">Seleccione **destino** y haga clic en la fila agregar bajo **nombre de Variable**, seleccione **EndDocMsg**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="66a9a-134">Select **Destination** and click in the Add row under **Variable Name**, select **EndDocMsg**, and click **OK**.</span></span>  
  
6. <span data-ttu-id="66a9a-135">En el Explorador de soluciones, haga doble clic en **Transform_2.btm** para abrir la herramienta de asignación.</span><span class="sxs-lookup"><span data-stu-id="66a9a-135">In the Solution Explorer, double-click **Transform_2.btm** to open the mapping tool.</span></span> <span data-ttu-id="66a9a-136">Vincule los cuatro siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="66a9a-136">Link the following four items:</span></span>  
  
   - <span data-ttu-id="66a9a-137">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="66a9a-137">mnCMJobNo</span></span>  
  
   - <span data-ttu-id="66a9a-138">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="66a9a-138">szCMComputerID</span></span>  
  
   - <span data-ttu-id="66a9a-139">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="66a9a-139">mnProcessID</span></span>  
  
   - <span data-ttu-id="66a9a-140">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="66a9a-140">mnTransactionID</span></span>  
  
     <span data-ttu-id="66a9a-141">Para facilitar su uso, este ejemplo tiene valores codificados.</span><span class="sxs-lookup"><span data-stu-id="66a9a-141">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="66a9a-142">Haga clic en el elemento del esquema de destino y establezca el siguiente valor.</span><span class="sxs-lookup"><span data-stu-id="66a9a-142">Click the item in the Destination Schema and set the following Value.</span></span>  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
       [JDE://CSALES/B4200310]">  
      <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
      <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
      <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
   </ns0:F4211FSEndDoc>  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="66a9a-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="66a9a-143">See Also</span></span>  
 <span data-ttu-id="66a9a-144">[Tarea 1: Creación de los puertos](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="66a9a-144">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="66a9a-145">[Tarea 2: Creación de los mensajes](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="66a9a-145">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="66a9a-146">[Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="66a9a-146">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="66a9a-147">Tarea 4: Configurar la forma Construir mensaje</span><span class="sxs-lookup"><span data-stu-id="66a9a-147">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape2.md)