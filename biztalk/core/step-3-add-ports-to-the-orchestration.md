---
title: 'Paso 3: Agregar puertos a la orquestación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245df16e-d327-4c79-be85-004134d5ea6f
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b42c91be94663f1061d3bbda31267db21988157
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968621"
---
# <a name="step-3-add-ports-to-the-orchestration"></a><span data-ttu-id="804eb-102">Paso 3: Agregar puertos a la orquestación</span><span class="sxs-lookup"><span data-stu-id="804eb-102">Step 3: Add Ports to the Orchestration</span></span>
<span data-ttu-id="804eb-103">![Paso 3 de 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="804eb-103">![Step 3 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="804eb-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="804eb-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="804eb-105">**Objetivo:** en este paso, se agregará tres puertos a la orquestación EAIProcess y configurarlos.</span><span class="sxs-lookup"><span data-stu-id="804eb-105">**Objective:** In this step, you add three ports to the EAIProcess orchestration and configure them.</span></span>  
  
 <span data-ttu-id="804eb-106">**Propósito:** los puertos especifican cómo la orquestación enviará mensajes a y recibir mensajes de otros procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="804eb-106">**Purpose:** Ports specify how your orchestration will send messages to and receive messages from other business processes.</span></span> <span data-ttu-id="804eb-107">Cada puerto tiene un tipo, una dirección y un enlace, que en combinación determinan la dirección de la comunicación, el patrón de comunicación, la ubicación de destino a la que se envía el mensaje, la ubicación de origen desde la que se recibe el mensaje y cómo tiene lugar la comunicación.</span><span class="sxs-lookup"><span data-stu-id="804eb-107">Each port has a type, a direction, and a binding, which together determine the direction of communication, the pattern of communication, the location to or from which the message is sent or received, and how the communication takes place.</span></span> <span data-ttu-id="804eb-108">los tres puertos que va a crear y configurar en este paso desempeñan las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="804eb-108">The three ports you create and configure in this step fulfill the following roles:</span></span>  
  
- <span data-ttu-id="804eb-109">**ReceiveRequestPort** recibe mensajes de solicitud de reposición de inventario del almacén.</span><span class="sxs-lookup"><span data-stu-id="804eb-109">**ReceiveRequestPort** receives inventory replenishment request messages from the warehouse.</span></span>  
  
- <span data-ttu-id="804eb-110">**SendToERP** reenvía los mensajes de solicitud al sistema ERP.</span><span class="sxs-lookup"><span data-stu-id="804eb-110">**SendToERP** forwards the request messages to the ERP system.</span></span>  
  
- <span data-ttu-id="804eb-111">**SendDeclinePort** envía mensajes al almacén de solicitud.</span><span class="sxs-lookup"><span data-stu-id="804eb-111">**SendDeclinePort** sends request decline messages back to the warehouse.</span></span>  
  
  <span data-ttu-id="804eb-112">Para obtener más información, consulte [mediante puertos en orquestaciones](../core/using-ports-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="804eb-112">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="804eb-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="804eb-113">Prerequisites</span></span>  
 <span data-ttu-id="804eb-114">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="804eb-114">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="804eb-115">Antes de comenzar este paso debe completar [paso 2: definir el proceso empresarial](../core/step-2-define-the-business-process.md).</span><span class="sxs-lookup"><span data-stu-id="804eb-115">Before you begin this step you must complete [Step 2: Define the Business Process](../core/step-2-define-the-business-process.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="804eb-116">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="804eb-116">Procedures</span></span>  
  
#### <a name="to-create-and-configure-receiverequestport"></a><span data-ttu-id="804eb-117">Para crear y configurar ReceiveRequestPort</span><span class="sxs-lookup"><span data-stu-id="804eb-117">To create and configure ReceiveRequestPort</span></span>  
  
1.  <span data-ttu-id="804eb-118">En el Explorador de soluciones, haga doble clic en **EAIProcess.odx**.</span><span class="sxs-lookup"><span data-stu-id="804eb-118">In Solution Explorer, double-click **EAIProcess.odx**.</span></span>  
  
2.  <span data-ttu-id="804eb-119">En el Diseñador de orquestaciones, en la orquestación del cuadro de herramientas, arrastre el **puerto** forma a la izquierda **superficie para el puerto**, en paralelo a la **ReceiveRequest** forma.</span><span class="sxs-lookup"><span data-stu-id="804eb-119">In Orchestration Designer, from the orchestration Toolbox, drag the **Port** shape to the left-side **Port Surface**, parallel to the **ReceiveRequest** shape.</span></span> <span data-ttu-id="804eb-120">El Asistente para configuración de puertos se inicia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="804eb-120">The Port Configuration Wizard starts automatically.</span></span>  
  
3.  <span data-ttu-id="804eb-121">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="804eb-121">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="804eb-122">En el **propiedades de puerto** página, haga lo siguiente y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="804eb-122">On the **Port Properties** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="804eb-123">Use</span><span class="sxs-lookup"><span data-stu-id="804eb-123">Use this</span></span>|<span data-ttu-id="804eb-124">Para</span><span class="sxs-lookup"><span data-stu-id="804eb-124">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="804eb-125">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="804eb-125">**Name**</span></span>|<span data-ttu-id="804eb-126">Tipo **ReceiveRequestPort**.</span><span class="sxs-lookup"><span data-stu-id="804eb-126">Type **ReceiveRequestPort**.</span></span>|  
  
5.  <span data-ttu-id="804eb-127">En el **seleccione un tipo de puerto** página, haga lo siguiente y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="804eb-127">On the **Select a Port Type** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="804eb-128">Use</span><span class="sxs-lookup"><span data-stu-id="804eb-128">Use this</span></span>|<span data-ttu-id="804eb-129">Para</span><span class="sxs-lookup"><span data-stu-id="804eb-129">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="804eb-130">**Seleccione el tipo de puerto que se utilizará para este puerto**</span><span class="sxs-lookup"><span data-stu-id="804eb-130">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="804eb-131">Seleccione el **crear un nuevo tipo de puerto** opción.</span><span class="sxs-lookup"><span data-stu-id="804eb-131">Select the **Create a new Port Type** option.</span></span>|  
    |<span data-ttu-id="804eb-132">**Nombre del tipo de puerto:**</span><span class="sxs-lookup"><span data-stu-id="804eb-132">**Port Type Name:**</span></span>|<span data-ttu-id="804eb-133">Tipo **ReceiveRequestPortType**.</span><span class="sxs-lookup"><span data-stu-id="804eb-133">Type **ReceiveRequestPortType**.</span></span>|  
    |<span data-ttu-id="804eb-134">**Patrón de comunicación**</span><span class="sxs-lookup"><span data-stu-id="804eb-134">**Communication Pattern**</span></span>|<span data-ttu-id="804eb-135">Seleccione **unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="804eb-135">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="804eb-136">**Restricciones de acceso**</span><span class="sxs-lookup"><span data-stu-id="804eb-136">**Access Restrictions**</span></span>|<span data-ttu-id="804eb-137">Seleccione **interno: limitado a este proyecto**.</span><span class="sxs-lookup"><span data-stu-id="804eb-137">Select **Internal - limited to this project**.</span></span>|  
  
6.  <span data-ttu-id="804eb-138">En el **enlace de puerto** página, haga lo siguiente y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="804eb-138">On the **Port Binding** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="804eb-139">Use</span><span class="sxs-lookup"><span data-stu-id="804eb-139">Use this</span></span>|<span data-ttu-id="804eb-140">Para</span><span class="sxs-lookup"><span data-stu-id="804eb-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="804eb-141">**Dirección de puerto de comunicación**</span><span class="sxs-lookup"><span data-stu-id="804eb-141">**Port direction of communication**</span></span>|<span data-ttu-id="804eb-142">Seleccione **siempre recibiré los mensajes en este puerto**.</span><span class="sxs-lookup"><span data-stu-id="804eb-142">Select **I'll always be receiving messages on this port**.</span></span>|  
    |<span data-ttu-id="804eb-143">**Enlace de puerto**</span><span class="sxs-lookup"><span data-stu-id="804eb-143">**Port binding**</span></span>|<span data-ttu-id="804eb-144">En Seleccione **especificar más tarde**.</span><span class="sxs-lookup"><span data-stu-id="804eb-144">From select **Specify later**.</span></span>|  
  
7.  <span data-ttu-id="804eb-145">En el **completar el Asistente para puertos** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="804eb-145">On the **Completing the Port Wizard** page, click **Finish**.</span></span>  
  
#### <a name="to-create-and-configure-senddeclineport"></a><span data-ttu-id="804eb-146">Para crear y configurar SendDeclinePort</span><span class="sxs-lookup"><span data-stu-id="804eb-146">To create and configure SendDeclinePort</span></span>  
  
1.  <span data-ttu-id="804eb-147">En el cuadro de herramientas de orquestaciones, arrastre el **puerto** forma a la izquierda **superficie para el puerto**, en paralelo a la **SendRequestDecline** forma.</span><span class="sxs-lookup"><span data-stu-id="804eb-147">From the orchestration Toolbox, drag the **Port** shape to the left-side **Port Surface**, parallel to the **SendRequestDecline** shape.</span></span>  
  
2.  <span data-ttu-id="804eb-148">Use la información de la tabla siguiente para crear el **SendDeclinePort** puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="804eb-148">Use the information in the following table to create the **SendDeclinePort** send port.</span></span>  
  
    |<span data-ttu-id="804eb-149">Property</span><span class="sxs-lookup"><span data-stu-id="804eb-149">Property</span></span>|<span data-ttu-id="804eb-150">Valor</span><span class="sxs-lookup"><span data-stu-id="804eb-150">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="804eb-151">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="804eb-151">**Name**</span></span>|<span data-ttu-id="804eb-152">Tipo **SendDeclinePort**.</span><span class="sxs-lookup"><span data-stu-id="804eb-152">Type **SendDeclinePort**.</span></span>|  
    |<span data-ttu-id="804eb-153">**Seleccione el tipo de puerto que se utilizará para este puerto**</span><span class="sxs-lookup"><span data-stu-id="804eb-153">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="804eb-154">Seleccione **crear un nuevo tipo de puerto**.</span><span class="sxs-lookup"><span data-stu-id="804eb-154">Select **Create a new Port Type**.</span></span>|  
    |<span data-ttu-id="804eb-155">**Nombre de tipo de puerto**</span><span class="sxs-lookup"><span data-stu-id="804eb-155">**Port Type Name**</span></span>|<span data-ttu-id="804eb-156">Tipo **SendDeclinePortType**.</span><span class="sxs-lookup"><span data-stu-id="804eb-156">Type **SendDeclinePortType**.</span></span>|  
    |<span data-ttu-id="804eb-157">**Patrón de comunicación**</span><span class="sxs-lookup"><span data-stu-id="804eb-157">**Communication Pattern**</span></span>|<span data-ttu-id="804eb-158">Seleccione **unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="804eb-158">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="804eb-159">**Restricciones de acceso**</span><span class="sxs-lookup"><span data-stu-id="804eb-159">**Access Restrictions**</span></span>|<span data-ttu-id="804eb-160">Seleccione **interno: limitado a este proyecto**.</span><span class="sxs-lookup"><span data-stu-id="804eb-160">Select **Internal - limited to this project**.</span></span>|  
    |<span data-ttu-id="804eb-161">**Dirección de puerto de comunicación**</span><span class="sxs-lookup"><span data-stu-id="804eb-161">**Port direction of communication**</span></span>|<span data-ttu-id="804eb-162">En la lista desplegable, seleccione **siempre enviaré los mensajes en este puerto**.</span><span class="sxs-lookup"><span data-stu-id="804eb-162">From the drop-down list, select **I'll always be sending messages on this port**.</span></span>|  
    |<span data-ttu-id="804eb-163">**Enlaces de puerto**</span><span class="sxs-lookup"><span data-stu-id="804eb-163">**Port bindings**</span></span>|<span data-ttu-id="804eb-164">En la lista desplegable, seleccione **especificar más tarde**.</span><span class="sxs-lookup"><span data-stu-id="804eb-164">From the drop-down list, select **Specify later**.</span></span>|  
  
#### <a name="to-create-and-configure-sendtoerpport"></a><span data-ttu-id="804eb-165">Para crear y configurar SendToERPPort</span><span class="sxs-lookup"><span data-stu-id="804eb-165">To create and configure SendToERPPort</span></span>  
  
1.  <span data-ttu-id="804eb-166">En el cuadro de herramientas de orquestaciones, arrastre el **puerto** forma a la derecha **superficie para el puerto**, en paralelo a la **SendToERP** forma.</span><span class="sxs-lookup"><span data-stu-id="804eb-166">From the orchestration Toolbox, drag the **Port** shape to the right-side **Port Surface**, parallel to the **SendToERP** shape.</span></span>  
  
2.  <span data-ttu-id="804eb-167">Use la información de la tabla siguiente para completar el Asistente para configuración de puerto para el **SendToERP** puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="804eb-167">Use the information in the following table to complete the Port Configuration Wizard for the **SendToERP** send port.</span></span>  
  
    |<span data-ttu-id="804eb-168">Property</span><span class="sxs-lookup"><span data-stu-id="804eb-168">Property</span></span>|<span data-ttu-id="804eb-169">Valor</span><span class="sxs-lookup"><span data-stu-id="804eb-169">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="804eb-170">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="804eb-170">**Name**</span></span>|<span data-ttu-id="804eb-171">Tipo **SendToERPPort**.</span><span class="sxs-lookup"><span data-stu-id="804eb-171">Type **SendToERPPort**.</span></span>|  
    |<span data-ttu-id="804eb-172">**Seleccione el tipo de puerto que se utilizará para este puerto**</span><span class="sxs-lookup"><span data-stu-id="804eb-172">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="804eb-173">Seleccione **crear un nuevo tipo de puerto**.</span><span class="sxs-lookup"><span data-stu-id="804eb-173">Select **Create a new Port Type**.</span></span>|  
    |<span data-ttu-id="804eb-174">**Nombre de tipo de puerto**</span><span class="sxs-lookup"><span data-stu-id="804eb-174">**Port Type Name**</span></span>|<span data-ttu-id="804eb-175">Tipo **SendToERPPortType**.</span><span class="sxs-lookup"><span data-stu-id="804eb-175">Type **SendToERPPortType**.</span></span>|  
    |<span data-ttu-id="804eb-176">**Patrón de comunicación**</span><span class="sxs-lookup"><span data-stu-id="804eb-176">**Communication Pattern**</span></span>|<span data-ttu-id="804eb-177">Seleccione el **unidireccional** opción.</span><span class="sxs-lookup"><span data-stu-id="804eb-177">Select the **One-Way** option.</span></span>|  
    |<span data-ttu-id="804eb-178">**Restricciones de acceso**</span><span class="sxs-lookup"><span data-stu-id="804eb-178">**Access Restrictions**</span></span>|<span data-ttu-id="804eb-179">Seleccione el **interno: limitado a este proyecto** opción.</span><span class="sxs-lookup"><span data-stu-id="804eb-179">Select the **Internal - limited to this project** option.</span></span>|  
    |<span data-ttu-id="804eb-180">**Dirección de puerto de comunicación**</span><span class="sxs-lookup"><span data-stu-id="804eb-180">**Port direction of communication**</span></span>|<span data-ttu-id="804eb-181">En la lista desplegable, seleccione **siempre enviaré los mensajes en este puerto**.</span><span class="sxs-lookup"><span data-stu-id="804eb-181">From the drop-down list, select **I'll always be sending messages on this port**.</span></span>|  
    |<span data-ttu-id="804eb-182">**Enlace de puerto**</span><span class="sxs-lookup"><span data-stu-id="804eb-182">**Port binding**</span></span>|<span data-ttu-id="804eb-183">En la lista desplegable, seleccione **especificar más tarde**.</span><span class="sxs-lookup"><span data-stu-id="804eb-183">From the drop-down list, select **Specify later**.</span></span>|  
  
#### <a name="to-connect-the-ports-to-the-action-shapes"></a><span data-ttu-id="804eb-184">Para conectar los puertos a las formas de acción</span><span class="sxs-lookup"><span data-stu-id="804eb-184">To connect the ports to the action shapes</span></span>  
  
-   <span data-ttu-id="804eb-185">En el Diseñador de orquestaciones, en la superficie de diseño, arrastre el indicador con forma de flecha verde de cada puerto hasta el indicador verde correspondiente de la forma de acción:</span><span class="sxs-lookup"><span data-stu-id="804eb-185">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for each port to the corresponding green handle of the action shape:</span></span>  
  
    |<span data-ttu-id="804eb-186">Conectar el puerto</span><span class="sxs-lookup"><span data-stu-id="804eb-186">Connect this port</span></span>|<span data-ttu-id="804eb-187">A la forma de acción</span><span class="sxs-lookup"><span data-stu-id="804eb-187">To this action shape</span></span>|  
    |-----------------------|--------------------------|  
    |<span data-ttu-id="804eb-188">**ReceiveReqPort**</span><span class="sxs-lookup"><span data-stu-id="804eb-188">**ReceiveReqPort**</span></span>|<span data-ttu-id="804eb-189">**Receive_Request**</span><span class="sxs-lookup"><span data-stu-id="804eb-189">**Receive_Request**</span></span>|  
    |<span data-ttu-id="804eb-190">**SendDeclinePort**</span><span class="sxs-lookup"><span data-stu-id="804eb-190">**SendDeclinePort**</span></span>|<span data-ttu-id="804eb-191">**Send_ReqDenied**</span><span class="sxs-lookup"><span data-stu-id="804eb-191">**Send_ReqDenied**</span></span>|  
    |<span data-ttu-id="804eb-192">**SendToERP**</span><span class="sxs-lookup"><span data-stu-id="804eb-192">**SendToERP**</span></span>|<span data-ttu-id="804eb-193">**Send_ReqToERP**</span><span class="sxs-lookup"><span data-stu-id="804eb-193">**Send_ReqToERP**</span></span>|  
  
     <span data-ttu-id="804eb-194">En la siguiente ilustración se muestra la orquestación EAIProcess con todos los puertos conectados.</span><span class="sxs-lookup"><span data-stu-id="804eb-194">The following figure shows the EAIProcess orchestration with all of the ports connected.</span></span>  
  
     <span data-ttu-id="804eb-195">![Orquestación de EAIProcess con puertos conectados. ](../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")</span><span class="sxs-lookup"><span data-stu-id="804eb-195">![EAIProcess orchestration with connected ports.](../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="804eb-196">Síntesis</span><span class="sxs-lookup"><span data-stu-id="804eb-196">What did I just do?</span></span>  
 <span data-ttu-id="804eb-197">En este paso, ha agregado tres puertos a la orquestación EAIProcess y los ha configurado.</span><span class="sxs-lookup"><span data-stu-id="804eb-197">In this step, you added three ports to the EAIProcess orchestration and configured them.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="804eb-198">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="804eb-198">Next Steps</span></span>  
 <span data-ttu-id="804eb-199">Compile el proyecto [paso 4: generar el proyecto EAIOrchestration](../core/step-4-build-the-eaiorchestration-project.md).</span><span class="sxs-lookup"><span data-stu-id="804eb-199">You build the project in [Step 4: Build the EAIOrchestration Project](../core/step-4-build-the-eaiorchestration-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="804eb-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="804eb-200">See Also</span></span>  
 <span data-ttu-id="804eb-201">[Paso 1: Agregar el proyecto EAIOrchestration a la solución](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span><span class="sxs-lookup"><span data-stu-id="804eb-201">[Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span></span>  
 <span data-ttu-id="804eb-202">[Paso 2: Definir el proceso empresarial](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="804eb-202">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="804eb-203">Paso 4: Generar el proyecto EAIOrchestration</span><span class="sxs-lookup"><span data-stu-id="804eb-203">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)