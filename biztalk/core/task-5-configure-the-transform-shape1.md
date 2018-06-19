---
title: 'Tarea 5: Configurar la transformación forma1 | Documentos de Microsoft'
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
ms.openlocfilehash: e76313ca87ad3138da83480b46a38a802d89ff15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278748"
---
# <a name="task-5-configure-the-transform-shape"></a><span data-ttu-id="a5ab7-102">Tarea 5: Configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="a5ab7-102">Task 5: Configure the Transform Shape</span></span>
<span data-ttu-id="a5ab7-103">Utilice el siguiente procedimiento para configurar la forma Transformación.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-103">Use the following procedure to configure the Transform shape.</span></span>  
  
### <a name="to-configure-the-transform-shape"></a><span data-ttu-id="a5ab7-104">Para configurar la forma Transformación</span><span class="sxs-lookup"><span data-stu-id="a5ab7-104">To configure the Transform shape</span></span>  
  
1.  <span data-ttu-id="a5ab7-105">Arrastre una forma Construir mensaje después de ReceiveBeginDocResponse.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-105">Drag a Construct Message shape after ReceiveBeginDocResponse.</span></span>  
  
    -   <span data-ttu-id="a5ab7-106">**Mensajes construidos:** EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="a5ab7-106">**Messages Constructed:** EditLineMsg</span></span>  
  
    -   <span data-ttu-id="a5ab7-107">**Nombre:** ConstructEditLineMessageWithData</span><span class="sxs-lookup"><span data-stu-id="a5ab7-107">**Name:** ConstructEditLineMessageWithData</span></span>  
  
     <span data-ttu-id="a5ab7-108">Pulse el botón derecho en el centro, seleccione **Insertar forma**y, a continuación, seleccione **transformar**.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-108">Right-click in the middle, select **Insert Shape**, and then select **Transform**.</span></span>  
  
     ![](../core/media/jde-insert-shape-transform.gif "JDE_insert_shape_transform")  
  
     <span data-ttu-id="a5ab7-109">Mediante la forma Transformación, asigne datos a partir de los datos que se envían a los datos enviados.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-109">Using Transform, map data from the data you are sending to the data that is sent.</span></span>  
  
     <span data-ttu-id="a5ab7-110">Para su entorno de trabajo, enviaría un documento (en lugar de BeginDoc) con todos los valores posibles, lo que le permite construir todos los mensajes posibles, BeginDoc, EditLine y EndDoc.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-110">For your work environment you would send a document (instead of BeginDoc) with all values possible allowing you to construct all possible messages, BeginDoc, EditLine, and EndDoc.</span></span> <span data-ttu-id="a5ab7-111">Para este ejemplo, no obstante, sólo hay datos codificados.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-111">For this example, however, there is only hard coded data.</span></span>  
  
2.  <span data-ttu-id="a5ab7-112">Haga doble clic en **Transform_1** para abrir.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-112">Double-click **Transform_1** to open.</span></span>  
  
    1.  <span data-ttu-id="a5ab7-113">Seleccione origen y haga clic en la fila agregar bajo **nombre de Variable** y seleccione **BeginDocResponseMsg**.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-113">Select Source and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
         ![](../core/media/jde-transform-source.gif "JDE_transform_source")  
  
    2.  <span data-ttu-id="a5ab7-114">Seleccione **destino** y haga clic en la fila agregar bajo **nombre de Variable**, seleccione **EditLineMsg**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-114">Select **Destination** and click in the Add row under **Variable Name**, select **EditLineMsg**, and click **OK**.</span></span>  
  
         ![](../core/media/jde-transform-destination.gif "JDE_transform_destination")  
  
3.  <span data-ttu-id="a5ab7-115">En el Explorador de soluciones, haga doble clic en **Transform_1.btm** para abrir la herramienta de asignación.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-115">In the Solution Explorer, double-click **Transform_1.btm** to open the mapping tool.</span></span> <span data-ttu-id="a5ab7-116">Vincule los cuatro siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="a5ab7-116">Link the following four items:</span></span>  
  
    -   <span data-ttu-id="a5ab7-117">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="a5ab7-117">mnCMJobNo</span></span>  
  
    -   <span data-ttu-id="a5ab7-118">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="a5ab7-118">szCMComputerID</span></span>  
  
    -   <span data-ttu-id="a5ab7-119">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="a5ab7-119">mnProcessID</span></span>  
  
    -   <span data-ttu-id="a5ab7-120">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="a5ab7-120">mnTransactionID</span></span>  
  
     ![](../core/media/jde-example-transformmapping.gif "JDE_example_transformmapping")  
  
     <span data-ttu-id="a5ab7-121">Para facilitar su uso, este ejemplo tiene valores codificados.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-121">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="a5ab7-122">Haga clic en el elemento del esquema de destino y establezca el siguiente valor.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-122">Click the item in the Destination Schema and set the following Value.</span></span>  
  
     ![](../core/media/jde-hardcoded-mapping-example.gif "JDE_hardcoded_mapping_example")  
  
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
  
4.  <span data-ttu-id="a5ab7-123">Arrastre una forma Construir mensaje después de ReceiveEditLine.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-123">Drag a Construct Message after ReceiveEditLine.</span></span>  
  
    -   <span data-ttu-id="a5ab7-124">**Mensajes construidos:** EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="a5ab7-124">**Messages Constructed:** EndDocMsg</span></span>  
  
    -   <span data-ttu-id="a5ab7-125">**Nombre:** ConstructEndDocMessageWithData</span><span class="sxs-lookup"><span data-stu-id="a5ab7-125">**Name:** ConstructEndDocMessageWithData</span></span>  
  
     <span data-ttu-id="a5ab7-126">Pulse el botón derecho en el medio y seleccione **Insertar forma**y, a continuación, seleccione **transformar**.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-126">Right-click in the middle and select **Insert Shape**, and then select **Transform**.</span></span>  
  
5.  <span data-ttu-id="a5ab7-127">Haga doble clic en **Transform_2** para abrir.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-127">Double-click **Transform_2** to open.</span></span>  
  
    1.  <span data-ttu-id="a5ab7-128">Seleccione **origen** y haga clic en la fila agregar bajo **nombre de Variable** y seleccione **BeginDocResponseMsg**.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-128">Select **Source** and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
    2.  <span data-ttu-id="a5ab7-129">Seleccione **destino** y haga clic en la fila agregar bajo **nombre de Variable**, seleccione **EndDocMsg**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-129">Select **Destination** and click in the Add row under **Variable Name**, select **EndDocMsg**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="a5ab7-130">En el Explorador de soluciones, haga doble clic en **Transform_2.btm** para abrir la herramienta de asignación.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-130">In the Solution Explorer, double-click **Transform_2.btm** to open the mapping tool.</span></span> <span data-ttu-id="a5ab7-131">Vincule los cuatro siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="a5ab7-131">Link the following four items:</span></span>  
  
    -   <span data-ttu-id="a5ab7-132">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="a5ab7-132">mnCMJobNo</span></span>  
  
    -   <span data-ttu-id="a5ab7-133">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="a5ab7-133">szCMComputerID</span></span>  
  
    -   <span data-ttu-id="a5ab7-134">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="a5ab7-134">mnProcessID</span></span>  
  
    -   <span data-ttu-id="a5ab7-135">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="a5ab7-135">mnTransactionID</span></span>  
  
     <span data-ttu-id="a5ab7-136">Para facilitar su uso, este ejemplo tiene valores codificados.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-136">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="a5ab7-137">Haga clic en el elemento del esquema de destino y establezca el siguiente valor.</span><span class="sxs-lookup"><span data-stu-id="a5ab7-137">Click the item in the Destination Schema and set the following Value.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
        [JDE://CSALES/B4200310]">  
       <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
       <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
       <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
    </ns0:F4211FSEndDoc>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a5ab7-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5ab7-138">See Also</span></span>  
 <span data-ttu-id="a5ab7-139">[Tarea 1: Crear los puertos](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="a5ab7-139">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="a5ab7-140">[Tarea 2: Crear los mensajes](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="a5ab7-140">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="a5ab7-141">[Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="a5ab7-141">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="a5ab7-142">Tarea 4: Configurar la forma construir mensaje</span><span class="sxs-lookup"><span data-stu-id="a5ab7-142">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape2.md)