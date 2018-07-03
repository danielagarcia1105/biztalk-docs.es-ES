---
title: 'Paso 2: Definir el proceso empresarial | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b37bd9f1-5ee2-434d-950a-cf12967b6fc2
caps.latest.revision: 49
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 850b8b98764bc782dc62c6ebe792ace2d80ef0a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998109"
---
# <a name="step-2-define-the-business-process"></a><span data-ttu-id="6ae77-102">Paso 2: Definir el proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="6ae77-102">Step 2: Define the Business Process</span></span>
<span data-ttu-id="6ae77-103">![Paso 2 de 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="6ae77-103">![Step 2 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="6ae77-104">**Tiempo en completarse:** 8 minutos</span><span class="sxs-lookup"><span data-stu-id="6ae77-104">**Time to complete:** 8 minutes</span></span>  
  
 <span data-ttu-id="6ae77-105">**Objetivo:** en este paso, utilice el Diseñador de orquestaciones para definir el proceso de negocio.</span><span class="sxs-lookup"><span data-stu-id="6ae77-105">**Objective:** In this step, you use Orchestration Designer to define your business process.</span></span>  
  
 <span data-ttu-id="6ae77-106">**Propósito:** el flujo de trabajo de la orquestación representa y automatiza el proceso de negocio de su compañía para aprobar solicitudes de reposición de inventario.</span><span class="sxs-lookup"><span data-stu-id="6ae77-106">**Purpose:** The workflow of the orchestration represents and automates your company's business process for approving inventory replenishment requests.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6ae77-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6ae77-107">Prerequisites</span></span>  
 <span data-ttu-id="6ae77-108">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="6ae77-108">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="6ae77-109">Antes de comenzar este paso debe completar [paso 1: agregar el proyecto EAIOrchestration a la solución](../core/step-1-add-eaiorchestration-project-to-the-solution.md).</span><span class="sxs-lookup"><span data-stu-id="6ae77-109">Before you begin this step you must complete [Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="6ae77-110">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6ae77-110">Procedures</span></span>  
 <span data-ttu-id="6ae77-111">El primer paso para desarrollar una orquestación consiste en usar formas de acción para representar el proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="6ae77-111">The first step for developing an orchestration is to use action shapes to represent the business process.</span></span>  
  
#### <a name="to-create-the-eai-business-process-workflow"></a><span data-ttu-id="6ae77-112">Para crear el flujo de trabajo del proceso empresarial EAI</span><span class="sxs-lookup"><span data-stu-id="6ae77-112">To create the EAI business process workflow</span></span>  
  
1. <span data-ttu-id="6ae77-113">Desde Visual Studio, en el Explorador de soluciones, haga doble clic en **EAIProcess.odx** para abrir la orquestación.</span><span class="sxs-lookup"><span data-stu-id="6ae77-113">From Visual Studio, in Solution Explorer, double-click **EAIProcess.odx** to open the orchestration.</span></span>  
  
2. <span data-ttu-id="6ae77-114">En el Diseñador de orquestaciones, en la orquestación del cuadro de herramientas, arrastre el **recepción** dar forma y colóquela entre el **comenzar** (círculo verde) y **final** formas (Octógono rojo).</span><span class="sxs-lookup"><span data-stu-id="6ae77-114">In Orchestration Designer, from the orchestration Toolbox, drag the **Receive** shape, and drop it between the **Begin** (green circle) and **End** (red octagon) shapes.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6ae77-115">Si no está abierto, en el cuadro de herramientas del **vista** menú, haga clic en **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-115">If the Toolbox is not open, in the **View** menu, click **Toolbox**.</span></span> <span data-ttu-id="6ae77-116">Para anclarlo en la pantalla, haga clic en el icono de chincheta.</span><span class="sxs-lookup"><span data-stu-id="6ae77-116">To anchor it on the screen, click the thumbtack icon.</span></span>  
  
3. <span data-ttu-id="6ae77-117">En el cuadro de herramientas, arrastre el **decidir** forma por debajo de la forma recepción.</span><span class="sxs-lookup"><span data-stu-id="6ae77-117">From the toolbox, drag the **Decide** shape beneath the Receive shape.</span></span>  
  
4. <span data-ttu-id="6ae77-118">En el cuadro de herramientas, arrastre el **transformar** forma a la rama izquierda de la forma decidir.</span><span class="sxs-lookup"><span data-stu-id="6ae77-118">From the toolbox, drag the **Transform** shape to the left branch of the Decide shape.</span></span> <span data-ttu-id="6ae77-119">La forma Transformación está anidada dentro de la forma de Construir mensaje.</span><span class="sxs-lookup"><span data-stu-id="6ae77-119">The Transform shape is nested inside the Construct Message shape.</span></span>  
  
5. <span data-ttu-id="6ae77-120">En el cuadro de herramientas, arrastre el **enviar** forma por debajo de la forma transformación.</span><span class="sxs-lookup"><span data-stu-id="6ae77-120">From the toolbox, drag the **Send** shape beneath the Transform shape.</span></span>  
  
6. <span data-ttu-id="6ae77-121">En el cuadro de herramientas, arrastre el **enviar** forma a la rama derecha de la forma decidir.</span><span class="sxs-lookup"><span data-stu-id="6ae77-121">From the toolbox, drag the **Send** shape to the right branch of the Decide shape.</span></span>  <span data-ttu-id="6ae77-122">Una vez agregadas las formas de acción, la orquestación tiene el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-122">The orchestration looks like the following after you added the action shapes:</span></span>  
  
    <span data-ttu-id="6ae77-123">![Proceso EAI](../core/media/eaiprocess.gif "EAIProcess")</span><span class="sxs-lookup"><span data-stu-id="6ae77-123">![EAI process](../core/media/eaiprocess.gif "EAIProcess")</span></span>  
  
   <span data-ttu-id="6ae77-124">El paso siguiente es definir las variables de mensaje.</span><span class="sxs-lookup"><span data-stu-id="6ae77-124">The next step is to define message variables.</span></span>  <span data-ttu-id="6ae77-125">Hay varias formas de acción que tienen una propiedad de mensaje que es necesario especificar.</span><span class="sxs-lookup"><span data-stu-id="6ae77-125">Several action shapes have a message property that needs to be specified.</span></span>  
  
#### <a name="to-define-message-variables"></a><span data-ttu-id="6ae77-126">Para definir variables de mensaje</span><span class="sxs-lookup"><span data-stu-id="6ae77-126">To define message variables</span></span>  
  
1.  <span data-ttu-id="6ae77-127">En Visual Studio, haga clic en el **vista** menú, haga clic en **Other Windows**y, a continuación, haga clic en **Vista orquestación**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-127">From Visual Studio, click the **View** menu, click **Other Windows**, and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="6ae77-128">Desde la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-128">From Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="6ae77-129">En la ventana Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-129">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="6ae77-130">Use</span><span class="sxs-lookup"><span data-stu-id="6ae77-130">Use this</span></span>|<span data-ttu-id="6ae77-131">Para</span><span class="sxs-lookup"><span data-stu-id="6ae77-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ae77-132">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="6ae77-132">**Identifier**</span></span>|<span data-ttu-id="6ae77-133">Tipo **RequestMessage**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-133">Type **RequestMessage**.</span></span>|  
    |<span data-ttu-id="6ae77-134">**Tipo de mensaje**</span><span class="sxs-lookup"><span data-stu-id="6ae77-134">**Message Type**</span></span>|<span data-ttu-id="6ae77-135">Haga clic en **esquemas**y, a continuación, haga clic en  **\<seleccionar del ensamblado mencionado... \>**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-135">Click **Schemas**, and then click **\<Select from referenced assembly …\>**.</span></span> <span data-ttu-id="6ae77-136">En la ventana Seleccionar tipo de artefacto, haga clic en **EAISchemas**y, a continuación, haga clic en **solicitar**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-136">From the Select Artifact Type window, click **EAISchemas**, and then click **Request**.</span></span> <span data-ttu-id="6ae77-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-137">Click **OK**</span></span>|  
  
4.  <span data-ttu-id="6ae77-138">Desde la Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-138">From Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
5.  <span data-ttu-id="6ae77-139">En la ventana Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-139">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="6ae77-140">Use</span><span class="sxs-lookup"><span data-stu-id="6ae77-140">Use this</span></span>|<span data-ttu-id="6ae77-141">Para</span><span class="sxs-lookup"><span data-stu-id="6ae77-141">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ae77-142">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="6ae77-142">**Identifier**</span></span>|<span data-ttu-id="6ae77-143">Tipo **RequestDeclineMessage**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-143">Type **RequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="6ae77-144">**Tipo de mensaje**</span><span class="sxs-lookup"><span data-stu-id="6ae77-144">**Message Type**</span></span>|<span data-ttu-id="6ae77-145">Haga clic en **esquemas**y, a continuación, haga clic en  **\<seleccionar del ensamblado mencionado... \>**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-145">Click **Schemas**, and then click **\<Select from referenced assembly …\>**.</span></span> <span data-ttu-id="6ae77-146">En la ventana Seleccionar tipo de artefacto, haga clic en **EAISchemas**y, a continuación, haga clic en **RequestDecline**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-146">From the Select Artifact Type window, click **EAISchemas**, and then click **RequestDecline**.</span></span> <span data-ttu-id="6ae77-147">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-147">Click **OK**</span></span>|  
  
#### <a name="to-configure-the-properties-of-the-shapes"></a><span data-ttu-id="6ae77-148">Para configurar las propiedades de las formas</span><span class="sxs-lookup"><span data-stu-id="6ae77-148">To configure the properties of the shapes</span></span>  
  
1.  <span data-ttu-id="6ae77-149">En la superficie de diseño, haga clic en el **recepción** forma para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="6ae77-149">On the design surface, click the **Receive** shape to select it.</span></span>  
  
2.  <span data-ttu-id="6ae77-150">En la ventana Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-150">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="6ae77-151">Use</span><span class="sxs-lookup"><span data-stu-id="6ae77-151">Use this</span></span>|<span data-ttu-id="6ae77-152">Para</span><span class="sxs-lookup"><span data-stu-id="6ae77-152">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ae77-153">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6ae77-153">**Name**</span></span>|<span data-ttu-id="6ae77-154">Tipo **ReceiveRequest**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-154">Type **ReceiveRequest**.</span></span>|  
    |<span data-ttu-id="6ae77-155">**de mensaje**</span><span class="sxs-lookup"><span data-stu-id="6ae77-155">**Message**</span></span>|<span data-ttu-id="6ae77-156">Seleccione **RequestMessage**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-156">Select **RequestMessage**.</span></span>|  
    |<span data-ttu-id="6ae77-157">**Activate**</span><span class="sxs-lookup"><span data-stu-id="6ae77-157">**Activate**</span></span>|<span data-ttu-id="6ae77-158">En la lista desplegable, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-158">From the drop-down list, select **True**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="6ae77-159">Si no está abierta, en la ventana de propiedades el **vista** menú, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-159">If the Property window is not open, in the **View** menu, click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="6ae77-160">En la superficie de diseño, haga clic en el **decidir** forma.</span><span class="sxs-lookup"><span data-stu-id="6ae77-160">On the design surface, click the **Decide** shape.</span></span>  
  
4.  <span data-ttu-id="6ae77-161">En la ventana Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-161">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="6ae77-162">Use</span><span class="sxs-lookup"><span data-stu-id="6ae77-162">Use this</span></span>|<span data-ttu-id="6ae77-163">Para</span><span class="sxs-lookup"><span data-stu-id="6ae77-163">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ae77-164">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6ae77-164">**Name**</span></span>|<span data-ttu-id="6ae77-165">Tipo **CheckGrandTotal**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-165">Type **CheckGrandTotal**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="6ae77-166">Si no está abierta, en la ventana de propiedades el **vista** menú, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-166">If the Property window is not open, in the **View** menu, click **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="6ae77-167">En la superficie de diseño, haga clic en el **Rule_1** forma.</span><span class="sxs-lookup"><span data-stu-id="6ae77-167">On the design surface, click the **Rule_1** shape.</span></span>  
  
6.  <span data-ttu-id="6ae77-168">En la ventana Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-168">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="6ae77-169">Use</span><span class="sxs-lookup"><span data-stu-id="6ae77-169">Use this</span></span>|<span data-ttu-id="6ae77-170">Para</span><span class="sxs-lookup"><span data-stu-id="6ae77-170">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ae77-171">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6ae77-171">**Name**</span></span>|<span data-ttu-id="6ae77-172">Tipo **DeclineRule**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-172">Type **DeclineRule**.</span></span>|  
    |<span data-ttu-id="6ae77-173">**Expresión**</span><span class="sxs-lookup"><span data-stu-id="6ae77-173">**Expression**</span></span>|<span data-ttu-id="6ae77-174">Haga clic en el botón de puntos suspensivos (**...** ) y, a continuación, escriba `RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`.</span><span class="sxs-lookup"><span data-stu-id="6ae77-174">Click the ellipses (**…**), and then type `RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`.</span></span> <span data-ttu-id="6ae77-175">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-175">Click **OK**.</span></span>|  
  
7.  <span data-ttu-id="6ae77-176">En la superficie de diseño, haga clic en el **ConstructMessage_1** forma.</span><span class="sxs-lookup"><span data-stu-id="6ae77-176">On the design surface, click the **ConstructMessage_1** shape.</span></span>  
  
8.  <span data-ttu-id="6ae77-177">En la ventana Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-177">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="6ae77-178">Use</span><span class="sxs-lookup"><span data-stu-id="6ae77-178">Use this</span></span>|<span data-ttu-id="6ae77-179">Para</span><span class="sxs-lookup"><span data-stu-id="6ae77-179">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ae77-180">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6ae77-180">**Name**</span></span>|<span data-ttu-id="6ae77-181">Tipo **ConstructRequestDeclineMessage**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-181">Type **ConstructRequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="6ae77-182">**Mensajes construidos**</span><span class="sxs-lookup"><span data-stu-id="6ae77-182">**Messages Constructed**</span></span>|<span data-ttu-id="6ae77-183">Seleccione **RequestDeclineMessage**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-183">Select **RequestDeclineMessage**.</span></span>|  
  
9. <span data-ttu-id="6ae77-184">En la superficie de diseño, haga clic en el **Transform_1** forma.</span><span class="sxs-lookup"><span data-stu-id="6ae77-184">On the design surface, click the **Transform_1** shape.</span></span>  
  
10. <span data-ttu-id="6ae77-185">En la ventana Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-185">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="6ae77-186">Use</span><span class="sxs-lookup"><span data-stu-id="6ae77-186">Use this</span></span>|<span data-ttu-id="6ae77-187">Para</span><span class="sxs-lookup"><span data-stu-id="6ae77-187">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ae77-188">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6ae77-188">**Name**</span></span>|<span data-ttu-id="6ae77-189">Tipo **TransformRequestToRequestDeclineMessage**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-189">Type **TransformRequestToRequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="6ae77-190">**Nombre de asignación**</span><span class="sxs-lookup"><span data-stu-id="6ae77-190">**Map Name**</span></span>|<span data-ttu-id="6ae77-191">Haga clic en **...** .</span><span class="sxs-lookup"><span data-stu-id="6ae77-191">Click **…**.</span></span> <span data-ttu-id="6ae77-192">En Configuración de Transformación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-192">From Transform Configuration, do the following:</span></span><br /><br /> <span data-ttu-id="6ae77-193">Escriba la información de configuración:</span><span class="sxs-lookup"><span data-stu-id="6ae77-193">Enter the configuration information:</span></span><br /><br /> <span data-ttu-id="6ae77-194">-Haga clic en **mapa existente**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-194">- Click **Existing Map**.</span></span><br /><br /> <span data-ttu-id="6ae77-195">Asignación válida:</span><span class="sxs-lookup"><span data-stu-id="6ae77-195">Fully Qualified Map Name:</span></span><br /><br /> <span data-ttu-id="6ae77-196">-Seleccione  **\<seleccionar del ensamblado mencionado\>**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-196">- Select **\<Select from referenced assembly\>**.</span></span>  <span data-ttu-id="6ae77-197">En el panel izquierdo, seleccione **EAISchemas**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-197">From the left pane, select **EAISchemas**.</span></span>  <span data-ttu-id="6ae77-198">En el panel derecho, seleccione EAISchemas.MapToReqDecline.</span><span class="sxs-lookup"><span data-stu-id="6ae77-198">From the right pane, select EAISchemas.MapToReqDecline.</span></span>  <span data-ttu-id="6ae77-199">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-199">Click **OK**.</span></span><br /><br /> <span data-ttu-id="6ae77-200">Source</span><span class="sxs-lookup"><span data-stu-id="6ae77-200">Source</span></span><br /><br /> <span data-ttu-id="6ae77-201">-RequestMessage</span><span class="sxs-lookup"><span data-stu-id="6ae77-201">- RequestMessage</span></span><br /><br /> <span data-ttu-id="6ae77-202">Destino</span><span class="sxs-lookup"><span data-stu-id="6ae77-202">Destination</span></span><br /><br /> <span data-ttu-id="6ae77-203">-RequestDeclineMessage</span><span class="sxs-lookup"><span data-stu-id="6ae77-203">- RequestDeclineMessage</span></span>|  
  
11. <span data-ttu-id="6ae77-204">En la superficie de diseño, haga clic en el **Send_1** forma.</span><span class="sxs-lookup"><span data-stu-id="6ae77-204">On the design surface, click the **Send_1** shape.</span></span>  
  
12. <span data-ttu-id="6ae77-205">En la ventana Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-205">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="6ae77-206">Use</span><span class="sxs-lookup"><span data-stu-id="6ae77-206">Use this</span></span>|<span data-ttu-id="6ae77-207">Para</span><span class="sxs-lookup"><span data-stu-id="6ae77-207">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ae77-208">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6ae77-208">**Name**</span></span>|<span data-ttu-id="6ae77-209">Tipo **SendRequestDecline**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-209">Type **SendRequestDecline**.</span></span>|  
    |<span data-ttu-id="6ae77-210">**de mensaje**</span><span class="sxs-lookup"><span data-stu-id="6ae77-210">**Message**</span></span>|<span data-ttu-id="6ae77-211">Seleccione **RequestDeclineMessage**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-211">Select **RequestDeclineMessage**.</span></span>|  
  
13. <span data-ttu-id="6ae77-212">En la superficie de diseño, haga clic en el **Send_2** forma.</span><span class="sxs-lookup"><span data-stu-id="6ae77-212">On the design surface, click the **Send_2** shape.</span></span>  
  
14. <span data-ttu-id="6ae77-213">En la ventana Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae77-213">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="6ae77-214">Use</span><span class="sxs-lookup"><span data-stu-id="6ae77-214">Use this</span></span>|<span data-ttu-id="6ae77-215">Para</span><span class="sxs-lookup"><span data-stu-id="6ae77-215">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ae77-216">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6ae77-216">**Name**</span></span>|<span data-ttu-id="6ae77-217">Tipo **SendRequestToERP**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-217">Type **SendRequestToERP**.</span></span>|  
    |<span data-ttu-id="6ae77-218">**de mensaje**</span><span class="sxs-lookup"><span data-stu-id="6ae77-218">**Message**</span></span>|<span data-ttu-id="6ae77-219">Seleccione **RequestMessage**.</span><span class="sxs-lookup"><span data-stu-id="6ae77-219">Select **RequestMessage**.</span></span>|  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="6ae77-220">Síntesis</span><span class="sxs-lookup"><span data-stu-id="6ae77-220">What did I just do?</span></span>  
 <span data-ttu-id="6ae77-221">En este paso, ha utilizado el Diseñador de orquestaciones para definir el proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="6ae77-221">In this step, you used Orchestration Designer to define your business process.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6ae77-222">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6ae77-222">Next Steps</span></span>  
 <span data-ttu-id="6ae77-223">Agregar puertos lógicos a la orquestación en [paso 3: agregar puertos a la orquestación](../core/step-3-add-ports-to-the-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="6ae77-223">You add logical ports to the orchestration in [Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae77-224">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ae77-224">See Also</span></span>  
 <span data-ttu-id="6ae77-225">[Paso 1: Agregar el proyecto EAIOrchestration a la solución](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span><span class="sxs-lookup"><span data-stu-id="6ae77-225">[Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span></span>  
 <span data-ttu-id="6ae77-226">[Paso 3: Agregar puertos a la orquestación](../core/step-3-add-ports-to-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="6ae77-226">[Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md) </span></span>  
 [<span data-ttu-id="6ae77-227">Paso 4: Generar el proyecto EAIOrchestration</span><span class="sxs-lookup"><span data-stu-id="6ae77-227">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)