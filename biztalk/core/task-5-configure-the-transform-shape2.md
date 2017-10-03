---
title: "Tarea 5: Configurar la transformación Shape2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e92874e-9021-4cf6-bab6-d4173308c469
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 596afdecc38f25ef92dbeb368197d9c71adaffc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="task-5-configure-the-transform-shape"></a><span data-ttu-id="891ed-102">Tarea 5: Configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="891ed-102">Task 5: Configure the Transform Shape</span></span>
<span data-ttu-id="891ed-103">Utilice el siguiente procedimiento para configurar la forma Transformación.</span><span class="sxs-lookup"><span data-stu-id="891ed-103">Use the following procedure to configure the Transform shape.</span></span>  
  
### <a name="to-configure-the-transform-shape"></a><span data-ttu-id="891ed-104">Para configurar la forma Transformación</span><span class="sxs-lookup"><span data-stu-id="891ed-104">To configure the Transform shape</span></span>  
  
1.  <span data-ttu-id="891ed-105">Arrastre una forma Construir mensaje después de ReceiveBeginDocResponse.</span><span class="sxs-lookup"><span data-stu-id="891ed-105">Drag a Construct Message shape after ReceiveBeginDocResponse.</span></span>  
  
    -   <span data-ttu-id="891ed-106">**Mensajes construidos:** EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="891ed-106">**Messages Constructed:** EditLineMsg</span></span>  
  
    -   <span data-ttu-id="891ed-107">**Nombre:** ConstructEditLineMessageWithData</span><span class="sxs-lookup"><span data-stu-id="891ed-107">**Name:** ConstructEditLineMessageWithData</span></span>  
  
    1.  <span data-ttu-id="891ed-108">Pulse el botón derecho en el centro, seleccione **Insertar forma**y, a continuación, seleccione **transformar**.</span><span class="sxs-lookup"><span data-stu-id="891ed-108">Right-click in the middle, select **Insert Shape**, and then select **Transform**.</span></span>  
  
         <span data-ttu-id="891ed-109">![Insertar forma transformación](../core/media/insert-shape-transform.gif "insert_shape_transform")</span><span class="sxs-lookup"><span data-stu-id="891ed-109">![Insert Shape Transform](../core/media/insert-shape-transform.gif "insert_shape_transform")</span></span>  
  
    2.  <span data-ttu-id="891ed-110">Mediante la forma Transformación, asigne datos a partir de los datos que se envían a los datos enviados.</span><span class="sxs-lookup"><span data-stu-id="891ed-110">Using Transform, map data from the data you are sending to the data that is sent.</span></span>  
  
     <span data-ttu-id="891ed-111">Para su entorno de trabajo, enviaría un documento (en lugar de BeginDoc) con todos los valores posibles, lo que le permite construir todos los mensajes posibles, BeginDoc, EditLine y EndDoc.</span><span class="sxs-lookup"><span data-stu-id="891ed-111">For your work environment you would send a document (instead of BeginDoc) with all values possible allowing you to construct all possible messages, BeginDoc, EditLine, and EndDoc.</span></span> <span data-ttu-id="891ed-112">Para este ejemplo, no obstante, sólo hay datos codificados.</span><span class="sxs-lookup"><span data-stu-id="891ed-112">For this example, however, there is only hard coded data.</span></span>  
  
2.  <span data-ttu-id="891ed-113">Haga doble clic en la forma Transform_1 para abrirla.</span><span class="sxs-lookup"><span data-stu-id="891ed-113">Double-click Transform_1 to open.</span></span>  
  
    1.  <span data-ttu-id="891ed-114">Seleccione origen y haga clic en la fila agregar bajo **nombre de Variable** y seleccione **BeginDocResponseMsg**.</span><span class="sxs-lookup"><span data-stu-id="891ed-114">Select Source and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
         <span data-ttu-id="891ed-115">![Transformar origen](../core/media/transform-source.gif "transform_source")</span><span class="sxs-lookup"><span data-stu-id="891ed-115">![Transform Source](../core/media/transform-source.gif "transform_source")</span></span>  
  
    2.  <span data-ttu-id="891ed-116">Seleccione **destino** y haga clic en la fila agregar bajo **nombre de Variable**, seleccione **EditLineMsg**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="891ed-116">Select **Destination** and click in the Add row under **Variable Name**, select **EditLineMsg**, and click **OK**.</span></span>  
  
         <span data-ttu-id="891ed-117">![Destino de la transformación](../core/media/transform-destination.gif "transform_destination")</span><span class="sxs-lookup"><span data-stu-id="891ed-117">![Transform Destination](../core/media/transform-destination.gif "transform_destination")</span></span>  
  
3.  <span data-ttu-id="891ed-118">En el Explorador de soluciones, haga doble clic en **Transform_1.btm** para abrir la herramienta de asignación.</span><span class="sxs-lookup"><span data-stu-id="891ed-118">In the Solution Explorer, double-click **Transform_1.btm** to open the mapping tool.</span></span> <span data-ttu-id="891ed-119">Vincule los cuatro siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="891ed-119">Link the following four items:</span></span>  
  
    -   <span data-ttu-id="891ed-120">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="891ed-120">mnCMJobNo</span></span>  
  
    -   <span data-ttu-id="891ed-121">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="891ed-121">szCMComputerID</span></span>  
  
    -   <span data-ttu-id="891ed-122">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="891ed-122">mnProcessID</span></span>  
  
    -   <span data-ttu-id="891ed-123">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="891ed-123">mnTransactionID</span></span>  
  
     <span data-ttu-id="891ed-124">![Ejemplo de asignación de transformación](../core/media/example-transformmapping.gif "example_transformmapping")</span><span class="sxs-lookup"><span data-stu-id="891ed-124">![Example Transform Mapping](../core/media/example-transformmapping.gif "example_transformmapping")</span></span>  
  
     <span data-ttu-id="891ed-125">Para facilitar su uso, este ejemplo tiene valores codificados.</span><span class="sxs-lookup"><span data-stu-id="891ed-125">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="891ed-126">Haga clic en el elemento del esquema de destino y establezca el siguiente valor.</span><span class="sxs-lookup"><span data-stu-id="891ed-126">Click the item in the Destination Schema and set the following Value.</span></span>  
  
     <span data-ttu-id="891ed-127">![Asignación](../core/media/hardcoded-mapping-example.gif "hardcoded_mapping_example")</span><span class="sxs-lookup"><span data-stu-id="891ed-127">![Hard Coded Mapping](../core/media/hardcoded-mapping-example.gif "hardcoded_mapping_example")</span></span>  
  
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
  
4.  <span data-ttu-id="891ed-128">Arrastre una forma Construir mensaje después de ReceiveEditLine.</span><span class="sxs-lookup"><span data-stu-id="891ed-128">Drag a Construct Message after ReceiveEditLine.</span></span>  
  
    -   <span data-ttu-id="891ed-129">**Mensajes construidos:** EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="891ed-129">**Messages Constructed:** EndDocMsg</span></span>  
  
    -   <span data-ttu-id="891ed-130">**Nombre:** ConstructEndDocMessageWithData</span><span class="sxs-lookup"><span data-stu-id="891ed-130">**Name:** ConstructEndDocMessageWithData</span></span>  
  
         <span data-ttu-id="891ed-131">Pulse el botón derecho en el medio y seleccione **Insertar forma**y, a continuación, seleccione **transformar**.</span><span class="sxs-lookup"><span data-stu-id="891ed-131">Right-click in the middle and select **Insert Shape**, and then select **Transform**.</span></span>  
  
5.  <span data-ttu-id="891ed-132">Haga doble clic en la forma Transform_2 para abrirla.</span><span class="sxs-lookup"><span data-stu-id="891ed-132">Double-click Transform_2 to open.</span></span>  
  
    1.  <span data-ttu-id="891ed-133">Seleccione **origen** y haga clic en la fila agregar bajo **nombre de Variable** y seleccione **BeginDocResponseMsg**.</span><span class="sxs-lookup"><span data-stu-id="891ed-133">Select **Source** and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
    2.  <span data-ttu-id="891ed-134">Seleccione **destino** y haga clic en la fila agregar bajo **nombre de Variable**, seleccione **EndDocMsg**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="891ed-134">Select **Destination** and click in the Add row under **Variable Name**, select **EndDocMsg**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="891ed-135">En el Explorador de soluciones, haga doble clic en **Transform_2.btm** para abrir la herramienta de asignación.</span><span class="sxs-lookup"><span data-stu-id="891ed-135">In the Solution Explorer, double-click **Transform_2.btm** to open the mapping tool.</span></span> <span data-ttu-id="891ed-136">Vincule los cuatro siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="891ed-136">Link the following four items:</span></span>  
  
    -   <span data-ttu-id="891ed-137">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="891ed-137">mnCMJobNo</span></span>  
  
    -   <span data-ttu-id="891ed-138">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="891ed-138">szCMComputerID</span></span>  
  
    -   <span data-ttu-id="891ed-139">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="891ed-139">mnProcessID</span></span>  
  
    -   <span data-ttu-id="891ed-140">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="891ed-140">mnTransactionID</span></span>  
  
     <span data-ttu-id="891ed-141">Para facilitar su uso, este ejemplo tiene valores codificados.</span><span class="sxs-lookup"><span data-stu-id="891ed-141">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="891ed-142">Haga clic en el elemento del esquema de destino y establezca el siguiente valor.</span><span class="sxs-lookup"><span data-stu-id="891ed-142">Click the item in the Destination Schema and set the following Value.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
        [JDE://CSALES/B4200310]">  
       <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
       <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
       <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
    </ns0:F4211FSEndDoc>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="891ed-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="891ed-143">See Also</span></span>  
 <span data-ttu-id="891ed-144">[Tarea 1: Crear los puertos](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="891ed-144">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="891ed-145">[Tarea 2: Crear los mensajes](../core/task-2-create-the-messages2.md) </span><span class="sxs-lookup"><span data-stu-id="891ed-145">[Task 2: Create the Messages](../core/task-2-create-the-messages2.md) </span></span>  
 <span data-ttu-id="891ed-146">[Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes2.md) </span><span class="sxs-lookup"><span data-stu-id="891ed-146">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes2.md) </span></span>  
 [<span data-ttu-id="891ed-147">Tarea 4: Configurar la forma construir mensaje</span><span class="sxs-lookup"><span data-stu-id="891ed-147">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape1.md)