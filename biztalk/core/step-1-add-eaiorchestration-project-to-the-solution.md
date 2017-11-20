---
title: "Paso 1: Agregar el proyecto EAIOrchestration a la solución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9aa0d9-2075-4c7e-8baf-1ecd2721859a
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3b8e2b9c197e01ed695311c67bc79cf5056c4d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a><span data-ttu-id="d0653-102">Paso 1: Agregar el proyecto EAIOrchestration a la solución</span><span class="sxs-lookup"><span data-stu-id="d0653-102">Step 1: Add EAIOrchestration Project to the Solution</span></span>
<span data-ttu-id="d0653-103">![Paso 1 de 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="d0653-103">![Step 1 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="d0653-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="d0653-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="d0653-105">**Objetivo:** en este paso, agregará un segundo proyecto a la solución EAI.</span><span class="sxs-lookup"><span data-stu-id="d0653-105">**Objective:** In this step, you add a second project to the EAI solution.</span></span> <span data-ttu-id="d0653-106">A continuación, agregará una orquestación al nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="d0653-106">Then you add an orchestration to the new project.</span></span>  
  
 <span data-ttu-id="d0653-107">**Propósito:** crear un proyecto independiente para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="d0653-107">**Purpose:** You create a separate project for the orchestration.</span></span> <span data-ttu-id="d0653-108">Esto resulta útil cuando varias personas trabajan en una misma solución.</span><span class="sxs-lookup"><span data-stu-id="d0653-108">This is helpful when you have several different people working on one solution.</span></span> <span data-ttu-id="d0653-109">La nueva orquestación se empleará para automatizar el proceso empresarial en esta lección.</span><span class="sxs-lookup"><span data-stu-id="d0653-109">You use the new orchestration to automate the business process in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d0653-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d0653-110">Prerequisites</span></span>  
 <span data-ttu-id="d0653-111">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="d0653-111">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="d0653-112">Antes de comenzar este paso debe completar [lección 1: definir esquemas y una asignación](../core/lesson-1-define-schemas-and-a-map.md).</span><span class="sxs-lookup"><span data-stu-id="d0653-112">Before you begin this step you must complete [Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d0653-113">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d0653-113">Procedures</span></span>  
 <span data-ttu-id="d0653-114">Si ha cerrado la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana, siga el procedimiento "para abrir el proyecto de Visual Studio" en [paso 2: crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md) para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="d0653-114">If you have closed the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, follow the procedure “To open the Visual Studio project” in [Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) to open it.</span></span>  
  
#### <a name="to-add-another-project-to-your-solution"></a><span data-ttu-id="d0653-115">Para agregar otro proyecto a la solución</span><span class="sxs-lookup"><span data-stu-id="d0653-115">To add another project to your solution</span></span>  
  
1.  <span data-ttu-id="d0653-116">Desde Visual Studio, en el **archivo** menú, elija **agregar**y, a continuación, haga clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d0653-116">From Visual Studio, on the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="d0653-117">En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d0653-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="d0653-118">Use</span><span class="sxs-lookup"><span data-stu-id="d0653-118">Use this</span></span>|<span data-ttu-id="d0653-119">Para</span><span class="sxs-lookup"><span data-stu-id="d0653-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0653-120">**Plantillas instaladas**</span><span class="sxs-lookup"><span data-stu-id="d0653-120">**Installed Templates**</span></span>|<span data-ttu-id="d0653-121">Haga clic en **proyectos de BizTalk**y, a continuación, haga clic en **proyecto vacío de servidor BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="d0653-121">Click **BizTalk Projects**, and then click **Empty BizTalk Server Project**.</span></span>|  
    |<span data-ttu-id="d0653-122">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="d0653-122">**Name**</span></span>|<span data-ttu-id="d0653-123">Type `EAIOrchestration`.</span><span class="sxs-lookup"><span data-stu-id="d0653-123">Type `EAIOrchestration`.</span></span>|  
    |<span data-ttu-id="d0653-124">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="d0653-124">**Location**</span></span>|<span data-ttu-id="d0653-125">Type `C:\BTSTutorials\EAISolution`.</span><span class="sxs-lookup"><span data-stu-id="d0653-125">Type `C:\BTSTutorials\EAISolution`.</span></span>|  
  
3.  <span data-ttu-id="d0653-126">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0653-126">Click **OK**.</span></span>  
  
#### <a name="to-add-an-orchestration"></a><span data-ttu-id="d0653-127">Para agregar una orquestación</span><span class="sxs-lookup"><span data-stu-id="d0653-127">To add an orchestration</span></span>  
  
1.  <span data-ttu-id="d0653-128">En el Explorador de soluciones, haga clic en **EAIOrchestration**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0653-128">In Solution Explorer, right-click **EAIOrchestration**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="d0653-129">En el **Agregar nuevo elemento - EAIOrchestration** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d0653-129">In the **Add New Item - EAIOrchestration** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="d0653-130">Use</span><span class="sxs-lookup"><span data-stu-id="d0653-130">Use this</span></span>|<span data-ttu-id="d0653-131">Para</span><span class="sxs-lookup"><span data-stu-id="d0653-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0653-132">**Plantillas instaladas**</span><span class="sxs-lookup"><span data-stu-id="d0653-132">**Installed Templates**</span></span>|<span data-ttu-id="d0653-133">Haga clic en **archivos de orquestación**y, a continuación, haga clic en **orquestación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="d0653-133">Click **Orchestration Files**, and then click **BizTalk Orchestration**.</span></span>|  
    |<span data-ttu-id="d0653-134">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="d0653-134">**Name**</span></span>|<span data-ttu-id="d0653-135">Tipo de **EAIProcess.odx**.</span><span class="sxs-lookup"><span data-stu-id="d0653-135">Type **EAIProcess.odx**.</span></span>|  
  
3.  <span data-ttu-id="d0653-136">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d0653-136">Click **Add**.</span></span>  
  
     <span data-ttu-id="d0653-137">Se abre el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="d0653-137">Orchestration Designer opens.</span></span> <span data-ttu-id="d0653-138">En la siguiente ilustración se muestra el Diseñador de orquestaciones con la orquestación EAIProcess.</span><span class="sxs-lookup"><span data-stu-id="d0653-138">The following figure shows Orchestration Designer with the EAIProcess orchestration.</span></span>  
  
     <span data-ttu-id="d0653-139">![Nueva orquestación](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span><span class="sxs-lookup"><span data-stu-id="d0653-139">![New orchestration](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="d0653-140">Síntesis</span><span class="sxs-lookup"><span data-stu-id="d0653-140">What did I just do?</span></span>  
 <span data-ttu-id="d0653-141">En este paso, ha agregado un segundo proyecto a la solución EAI.</span><span class="sxs-lookup"><span data-stu-id="d0653-141">In this step, you added a second project to the EAI solution.</span></span> <span data-ttu-id="d0653-142">A continuación, ha agregado una orquestación al nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="d0653-142">Then you added an orchestration to the new project.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d0653-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d0653-143">Next Steps</span></span>  
 <span data-ttu-id="d0653-144">Definir el proceso empresarial en [paso 2: definir el proceso empresarial](../core/step-2-define-the-business-process.md).</span><span class="sxs-lookup"><span data-stu-id="d0653-144">You define the business process in [Step 2: Define the Business Process](../core/step-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0653-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0653-145">See Also</span></span>  
 <span data-ttu-id="d0653-146">[Paso 2: Definir el proceso empresarial](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="d0653-146">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 <span data-ttu-id="d0653-147">[Paso 3: Agregar puertos a la orquestación](../core/step-3-add-ports-to-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="d0653-147">[Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md) </span></span>  
 [<span data-ttu-id="d0653-148">Paso 4: Crear el proyecto EAIOrchestration</span><span class="sxs-lookup"><span data-stu-id="d0653-148">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)