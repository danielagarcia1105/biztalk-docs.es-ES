---
title: 'Paso 5: Modificar la orquestación de procesos privados de Contoso | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, orchestrations
- private process tutorial, modifying private process orchestration
ms.assetid: a5430db8-e5f0-48a6-abb9-e268d8ec2ec4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a222ee518cf0555de60094411df73bf5a5d486a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967762"
---
# <a name="step-5-modifying-the-contoso-private-process-orchestration"></a><span data-ttu-id="b783b-102">Paso 5: Modificar la orquestación de procesos privados de Contoso</span><span class="sxs-lookup"><span data-stu-id="b783b-102">Step 5: Modifying the Contoso Private Process Orchestration</span></span>
<span data-ttu-id="b783b-103">En este paso, modificará la orquestación de procesos privados para integrarse con el sistema de planeamiento de recursos empresariales (ERP) de Contoso.</span><span class="sxs-lookup"><span data-stu-id="b783b-103">In this step, you modify the private process orchestration to integrate with the Enterprise Resource Planning (ERP) system for Contoso.</span></span> <span data-ttu-id="b783b-104">El sistema ERP de Contoso usa esquemas definidos internamente para la disponibilidad y el precio del producto.</span><span class="sxs-lookup"><span data-stu-id="b783b-104">The ERP system for Contoso uses internally defined schemas for product price and availability.</span></span> <span data-ttu-id="b783b-105">Si personaliza el proceso privado para el 3A2 - precio y el proceso de interfaz de socio (PIP) disponibilidad, podrá integrar con el sistema ERP mediante el uso de información de esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="b783b-105">By customizing the private process for the 3A2 - Price and Availability Partner Interface Process (PIP), you will be able to integrate with the ERP system by using schema-mapping information.</span></span>  
  
### <a name="to-add-a-reference-to-the-contoso-priceandavailability-and-rnpips-assemblies"></a><span data-ttu-id="b783b-106">Para agregar una referencia a los ensamblados de Contoso PriceAndAvailability y Rnpip</span><span class="sxs-lookup"><span data-stu-id="b783b-106">To add a reference to the Contoso PriceAndAvailability and RNPIPs assemblies</span></span>  
  
1.  <span data-ttu-id="b783b-107">Con la solución de Contoso que se muestra en el Explorador de soluciones, haga clic en el **PrivateResponder** del proyecto y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="b783b-107">With the Contoso solution displayed in Solution Explorer, right-click the **PrivateResponder** project, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="b783b-108">En el cuadro de diálogo Agregar referencia, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="b783b-108">In the Add Reference dialog box, click **Browse**.</span></span> <span data-ttu-id="b783b-109">Mover a  *\<unidad\>*: \Program BizTalk \<versión\> Accelerator for RosettaNet\Bin carpeta y, a continuación, seleccione los ensamblados siguientes **:**</span><span class="sxs-lookup"><span data-stu-id="b783b-109">Move to *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin folder, and then select the following assemblies **:**</span></span>  
  
    -   <span data-ttu-id="b783b-110">Microsoft.Solutions.BTARN.CommonTypes.dll</span><span class="sxs-lookup"><span data-stu-id="b783b-110">Microsoft.Solutions.BTARN.CommonTypes.dll</span></span>  
  
    -   <span data-ttu-id="b783b-111">Microsoft.Solutions.BTARN.ConfigurationManager.dll</span><span class="sxs-lookup"><span data-stu-id="b783b-111">Microsoft.Solutions.BTARN.ConfigurationManager.dll</span></span>  
  
    -   <span data-ttu-id="b783b-112">Microsoft.Solutions.BTARN.GlobalSchemas.dll</span><span class="sxs-lookup"><span data-stu-id="b783b-112">Microsoft.Solutions.BTARN.GlobalSchemas.dll</span></span>  
  
    -   <span data-ttu-id="b783b-113">Microsoft.Solutions.BTARN.PublicResponder.dll</span><span class="sxs-lookup"><span data-stu-id="b783b-113">Microsoft.Solutions.BTARN.PublicResponder.dll</span></span>  
  
    -   <span data-ttu-id="b783b-114">Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll</span><span class="sxs-lookup"><span data-stu-id="b783b-114">Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll</span></span>  
  
    -   <span data-ttu-id="b783b-115">Microsoft.Solutions.BTARN.Shared.dll</span><span class="sxs-lookup"><span data-stu-id="b783b-115">Microsoft.Solutions.BTARN.Shared.dll</span></span>  
  
    -   <span data-ttu-id="b783b-116">Microsoft.Solutions.BTARN.XSDClasses.GlobalSchemas.dll</span><span class="sxs-lookup"><span data-stu-id="b783b-116">Microsoft.Solutions.BTARN.XSDClasses.GlobalSchemas.dll</span></span>  
  
3.  <span data-ttu-id="b783b-117">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b783b-117">Click **Add**.</span></span>  
  
4.  <span data-ttu-id="b783b-118">En el cuadro de diálogo Agregar referencia, haga clic en el **proyectos** ficha, seleccione la **ContosoPriceAndAvailability** y **HeaderHelper** proyectos y, a continuación, haga clic en  **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b783b-118">In the Add Reference dialog box, click the **Projects** tab, select the **ContosoPriceAndAvailability** and **HeaderHelper** projects, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="b783b-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b783b-119">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="b783b-120">En el cuadro de diálogo del entorno de desarrollo de Microsoft, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b783b-120">In the Microsoft Development Environment dialog box, click **OK**.</span></span>  
  
### <a name="to-create-new-message-types"></a><span data-ttu-id="b783b-121">Para crear nuevos tipos de mensaje</span><span class="sxs-lookup"><span data-stu-id="b783b-121">To create new message types</span></span>  
  
1.  <span data-ttu-id="b783b-122">En el Explorador de soluciones, haga doble clic en el **PrivateResponder** orquestación para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="b783b-122">In Solution Explorer, double-click the **PrivateResponder** orchestration to open it.</span></span>  
  
2.  <span data-ttu-id="b783b-123">En el Explorador de soluciones, haga clic en **Vista orquestación**.</span><span class="sxs-lookup"><span data-stu-id="b783b-123">In Solution Explorer, click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="b783b-124">En Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="b783b-124">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="b783b-125">En la ventana Propiedades, en la **identificador** , escriba **PIP3A2RequestMessage**.</span><span class="sxs-lookup"><span data-stu-id="b783b-125">In the Properties window, in the **Identifier** box, type **PIP3A2RequestMessage**.</span></span>  
  
5.  <span data-ttu-id="b783b-126">En el **tipo de mensaje** , haga clic en la flecha de lista desplegable, expanda **esquemas**y, a continuación, seleccione  **\<seleccionar del ensamblado mencionado\>**.</span><span class="sxs-lookup"><span data-stu-id="b783b-126">In the **Message Type** box, click the drop-down arrow, expand **Schemas**, and then select **\<Select from referenced assembly\>**.</span></span>  
  
6.  <span data-ttu-id="b783b-127">En el cuadro Seleccionar Typedialog de artefacto, seleccione **Microsoft.Solutions.BTARN.Schemas.RNPIPs** en el panel izquierdo, seleccione **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3** en el panel derecho, y a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b783b-127">In the Select Artifact Typedialog box, select **Microsoft.Solutions.BTARN.Schemas.RNPIPs** in the left pane, select **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3** in the right pane, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="b783b-128">Repita los pasos del 3 al 6 para crear todos los tipos de mensaje para la solución con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="b783b-128">Repeat steps 3 through 6 to create all the message types for the solution using the following information:</span></span>  
  
    |<span data-ttu-id="b783b-129">Identificador</span><span class="sxs-lookup"><span data-stu-id="b783b-129">Identifier</span></span>|<span data-ttu-id="b783b-130">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="b783b-130">Assembly</span></span>|<span data-ttu-id="b783b-131">Tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="b783b-131">Message Type</span></span>|  
    |----------------|--------------|------------------|  
    |<span data-ttu-id="b783b-132">PIP3A2ResponseMessage</span><span class="sxs-lookup"><span data-stu-id="b783b-132">PIP3A2ResponseMessage</span></span>|<span data-ttu-id="b783b-133">Microsoft.Solutions.BTARN.</span><span class="sxs-lookup"><span data-stu-id="b783b-133">Microsoft.Solutions.BTARN.</span></span><br /><span data-ttu-id="b783b-134">Schemas.RNPips</span><span class="sxs-lookup"><span data-stu-id="b783b-134">Schemas.RNPips</span></span>|<span data-ttu-id="b783b-135">_3A2PriceAndAvailability</span><span class="sxs-lookup"><span data-stu-id="b783b-135">_3A2PriceAndAvailability</span></span><br /><span data-ttu-id="b783b-136">ResponseMessageGuideline_v1_3</span><span class="sxs-lookup"><span data-stu-id="b783b-136">ResponseMessageGuideline_v1_3</span></span>|  
    |<span data-ttu-id="b783b-137">Contoso3A2ResponseMessage</span><span class="sxs-lookup"><span data-stu-id="b783b-137">Contoso3A2ResponseMessage</span></span>|<span data-ttu-id="b783b-138">ContosoPriceAndAvailability</span><span class="sxs-lookup"><span data-stu-id="b783b-138">ContosoPriceAndAvailability</span></span>|<span data-ttu-id="b783b-139">rootPriceResponse</span><span class="sxs-lookup"><span data-stu-id="b783b-139">rootPriceResponse</span></span>|  
    |<span data-ttu-id="b783b-140">Contoso3A2RequestMessage</span><span class="sxs-lookup"><span data-stu-id="b783b-140">Contoso3A2RequestMessage</span></span>|<span data-ttu-id="b783b-141">ContosoPriceAndAvailability</span><span class="sxs-lookup"><span data-stu-id="b783b-141">ContosoPriceAndAvailability</span></span>|<span data-ttu-id="b783b-142">rootPriceRequest</span><span class="sxs-lookup"><span data-stu-id="b783b-142">rootPriceRequest</span></span>|  
  
8.  <span data-ttu-id="b783b-143">Ha terminado de crear los tipos de mensaje para la solución.</span><span class="sxs-lookup"><span data-stu-id="b783b-143">You have finished creating the message types for the solution.</span></span>  
  
### <a name="to-create-new-variables"></a><span data-ttu-id="b783b-144">Para crear nuevas variables</span><span class="sxs-lookup"><span data-stu-id="b783b-144">To create new variables</span></span>  
  
1.  <span data-ttu-id="b783b-145">En Vista orquestación, haga clic en **Variables,** y, a continuación, haga clic en **nueva Variable**.</span><span class="sxs-lookup"><span data-stu-id="b783b-145">In Orchestration View, right-click **Variables,** and then click **New Variable**.</span></span>  
  
2.  <span data-ttu-id="b783b-146">En la ventana Propiedades, en la **identificador** , escriba **contosoResponseXML**.</span><span class="sxs-lookup"><span data-stu-id="b783b-146">In the Properties window, in the **Identifier** box, type **contosoResponseXML**.</span></span>  
  
3.  <span data-ttu-id="b783b-147">En el **tipo** cuadro, seleccione  **\<clase .NET\>**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b783b-147">In the **Type** box, select **\<.NET Class\>** from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="b783b-148">En el artefacto seleccione escriba cuadro de diálogo, en el panel izquierdo, bajo el **proyecto actual** y **referencias** nodos, seleccione **System.Xml**, seleccione  **XmlDocument** en la lista en el panel derecho y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b783b-148">In the Select Artifact Type dialog box, in the left pane, under the **Current Project** and **References** nodes, select **System.Xml**, select **XmlDocument** from the list in the right pane, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="b783b-149">En **Vista orquestación**, haga clic en **Variables**y, a continuación, haga clic en **nueva Variable**.</span><span class="sxs-lookup"><span data-stu-id="b783b-149">In **Orchestration View**, click **Variables**,and then click **New Variable**.</span></span>  
  
6.  <span data-ttu-id="b783b-150">En la ventana Propiedades, en la **identificador** , escriba **submitMessage**.</span><span class="sxs-lookup"><span data-stu-id="b783b-150">In the Properties window, in the **Identifier** box, type **submitMessage**.</span></span>  
  
7.  <span data-ttu-id="b783b-151">En el **tipo** cuadro, seleccione  **\<clase .NET\>**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b783b-151">In the **Type** box, select **\<.NET Class\>** from the drop-down list.</span></span>  
  
8.  <span data-ttu-id="b783b-152">En el cuadro de diálogo Seleccionar tipo de artefacto, en el panel izquierdo, expanda **proyecto actual** y **referencias** nodos, seleccione **Microsoft.Solutions.BTARN.Shared**, seleccione  **SubmitRNIF** en la lista en el panel derecho y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b783b-152">In the Select Artifact Type dialog box, in the left pane, expand **Current Project** and **References** nodes, select **Microsoft.Solutions.BTARN.Shared**, select **SubmitRNIF** from the list in the right pane, and then click **OK**.</span></span>  
  
### <a name="to-change-the-orchestration-filter-expression"></a><span data-ttu-id="b783b-153">Para modificar la expresión de filtro de orquestación</span><span class="sxs-lookup"><span data-stu-id="b783b-153">To change the orchestration filter expression</span></span>  
  
1.  <span data-ttu-id="b783b-154">En el Diseñador de orquestaciones, seleccione la **ReceiveFromPublicProcessResponder** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-154">In Orchestration Designer, select the **ReceiveFromPublicProcessResponder** shape.</span></span>  
  
2.  <span data-ttu-id="b783b-155">En la ventana Propiedades, en la **expresión de filtro** cuadro, haga clic en el cuadro de valor y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) para abrir el cuadro de diálogo Expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="b783b-155">In the Properties window, in the **Filter Expression** box, click the value box, and then click the ellipsis button (**...**) to open the Filter Expression dialog box.</span></span>  
  
3.  <span data-ttu-id="b783b-156">En el cuadro de diálogo Expresión de filtro, en la **Group By** sección, haga clic en el **o** valor en la primera línea y, a continuación, seleccione **AND** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b783b-156">In the Filter Expression dialog box, in the **Group By** section, click the **OR** value on the first line, and then select **AND** from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="b783b-157">En el cuadro de diálogo Expresión de filtro, haga clic en **haga clic aquí para agregar una nueva fila**y, a continuación, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b783b-157">In the Filter Expression dialog box, click **Click here to add a new row**, and then select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="b783b-158">En la misma fila, haga clic en **valor**y, a continuación, escriba en **"3A2"**.</span><span class="sxs-lookup"><span data-stu-id="b783b-158">In the same row, click **Value**, and then type in **"3A2"**.</span></span>  
  
6.  <span data-ttu-id="b783b-159">En la misma fila, haga clic en **AND** en el **Group By** cuadro y, a continuación, seleccione **o** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b783b-159">In the same row, click **AND** in the **Group By** box, and then select **OR** from the drop-down list.</span></span>  
  
7.  <span data-ttu-id="b783b-160">En el cuadro de diálogo Expresión de filtro, seleccione la fila que acaba de crear y, a continuación, haga clic en el botón de flecha arriba una vez para mover la fila de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="b783b-160">In the Filter Expression dialog box, select the row that you just created, and then click the up arrow button once to move the row up once.</span></span>  
  
8.  <span data-ttu-id="b783b-161">Haga clic en **haga clic aquí para agregar una nueva fila**y, a continuación, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b783b-161">Click **Click here to add a new row**, and then select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="b783b-162">En la misma fila, haga clic en **valor**y, a continuación, escriba en **"3A2"**.</span><span class="sxs-lookup"><span data-stu-id="b783b-162">In the same row, click **Value**, and then type in **"3A2"**.</span></span>  
  
10. <span data-ttu-id="b783b-163">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="b783b-163">Click OK.</span></span>  
  
### <a name="to-modify-the-business-process-workflow"></a><span data-ttu-id="b783b-164">Para modificar el flujo de trabajo del proceso de negocio</span><span class="sxs-lookup"><span data-stu-id="b783b-164">To modify the business process workflow</span></span>  
  
1.  <span data-ttu-id="b783b-165">Arrastre un **asignación de mensajes** forma del cuadro de herramientas a la superficie de diseño y colóquelo bajo el **ReceiveFromPublicProcessResponder** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-165">Drag a **Message Assignment** shape from the Toolbox to the design surface and drop it under the **ReceiveFromPublicProcessResponder** shape.</span></span> <span data-ttu-id="b783b-166">Seleccione el **ConstructMessage_1** forma a la que se creó y, en la **propiedades** ventana, en la **nombre** , escriba **ConstructPIP3A2RequestMessage** .</span><span class="sxs-lookup"><span data-stu-id="b783b-166">Select the **ConstructMessage_1** shape that was created and in the **Properties** window, in the **Name** box, type **ConstructPIP3A2RequestMessage**.</span></span>  
  
2.  <span data-ttu-id="b783b-167">Arrastre un **transformar** dar forma a la superficie de diseño y colóquelo bajo el **ConstructPIP3A2RequestMessage** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-167">Drag a **Transform** shape to the design surface and drop it under the **ConstructPIP3A2RequestMessage** shape.</span></span> <span data-ttu-id="b783b-168">Seleccione el **ConstructMessage_1** forma a la que se creó y, en la **propiedades** ventana, en la **nombre** , escriba **ConstructContoso3A2RequestMessage** .</span><span class="sxs-lookup"><span data-stu-id="b783b-168">Select the **ConstructMessage_1** shape that was created and in the **Properties** window, in the **Name** box, type **ConstructContoso3A2RequestMessage**.</span></span>  
  
3.  <span data-ttu-id="b783b-169">Arrastre un **enviar** dar forma a la superficie de diseño y colóquelo bajo el **ConstructContoso3A2RequestMessage** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-169">Drag a **Send** shape to the design surface and drop it under the **ConstructContoso3A2RequestMessage** shape.</span></span>  
  
4.  <span data-ttu-id="b783b-170">Arrastre un **recepción** dar forma a la superficie de diseño y colóquelo bajo el **Send_1** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-170">Drag a **Receive** shape to the design surface and drop it under the **Send_1** shape.</span></span>  
  
5.  <span data-ttu-id="b783b-171">En la superficie de diseño de orquestación, haga clic en un área vacía.</span><span class="sxs-lookup"><span data-stu-id="b783b-171">On the orchestration design surface, click an empty area.</span></span>  
  
6.  <span data-ttu-id="b783b-172">En la ventana Propiedades, seleccione la **tipo de transacción** propiedad y, a continuación, haga clic en **larga ejecución**.</span><span class="sxs-lookup"><span data-stu-id="b783b-172">In the Properties window, select the **Transaction Type** property, and then click **Long Running**.</span></span>  
  
7.  <span data-ttu-id="b783b-173">Arrastre un **ámbito** dar forma a la superficie de diseño y colóquelo bajo el **Receive_1** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-173">Drag a **Scope** shape to the design surface and drop it under the **Receive_1** shape.</span></span>  
  
8.  <span data-ttu-id="b783b-174">En la ventana Propiedades, de la **tipo de transacción** lista desplegable de propiedades, seleccione **atómica** para el **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-174">In the Properties window, from the **Transaction Type** property drop-down list, select **Atomic** for the **Scope** shape.</span></span>  
  
9. <span data-ttu-id="b783b-175">Arrastre un **reglas de llamada** dar forma a la superficie de diseño y colóquela en la etiqueta que dice **coloca una forma en el cuadro de herramientas aquí** dentro de la **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-175">Drag a **Call Rules** shape to the design surface and drop it on the label that says **Drop a shape from the toolbox here** inside the **Scope** shape.</span></span> <span data-ttu-id="b783b-176">En la ventana de propiedades para el **reglas de llamada** forma, en la **nombre** , escriba **Execute3A2Vocabulary**.</span><span class="sxs-lookup"><span data-stu-id="b783b-176">In the Properties window for the **Call Rules** shape, in the **Name** box, type **Execute3A2Vocabulary**.</span></span>  
  
10. <span data-ttu-id="b783b-177">Arrastre un **transformar** dar forma a la superficie de diseño y colóquelo bajo el **Scope_1** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-177">Drag a **Transform** shape to the design surface and drop it under the **Scope_1** shape.</span></span> <span data-ttu-id="b783b-178">Haga clic en el **ConstructMessage_1** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-178">Click the **ConstructMessage_1** shape.</span></span> <span data-ttu-id="b783b-179">En la ventana Propiedades, en la **nombre** , escriba **Construct3A2ResponseMessage**.</span><span class="sxs-lookup"><span data-stu-id="b783b-179">In the Properties window, in the **Name** box, type **Construct3A2ResponseMessage**.</span></span>  
  
11. <span data-ttu-id="b783b-180">Arrastre un **expresión** dar forma a la superficie de diseño y colóquelo bajo el **Construct3A2ResponseMessageTransform** forma.</span><span class="sxs-lookup"><span data-stu-id="b783b-180">Drag an **Expression** shape to the design surface and drop it under the **Construct3A2ResponseMessageTransform** shape.</span></span>  
  
12. <span data-ttu-id="b783b-181">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo**, haga clic en **guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b783b-181">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File**, click **Save All** to save the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b783b-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="b783b-182">See Also</span></span>  
 [<span data-ttu-id="b783b-183">Paso 6: Configuración de las formas de orquestación (Contoso)</span><span class="sxs-lookup"><span data-stu-id="b783b-183">Step 6: Configuring Orchestration Shapes (Contoso)</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)