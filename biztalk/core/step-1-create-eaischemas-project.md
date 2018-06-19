---
title: 'Paso 1: Crear el proyecto EAISchemas | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a14ee61-fa27-4f03-997e-42c34a77afee
caps.latest.revision: 55
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e73da569196d564cd9bb0886c8c7f97d94fe9614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277660"
---
# <a name="step-1-create-eaischemas-project"></a><span data-ttu-id="4cb91-102">Paso 1: Crear el proyecto EAISchemas</span><span class="sxs-lookup"><span data-stu-id="4cb91-102">Step 1: Create EAISchemas Project</span></span>
<span data-ttu-id="4cb91-103">![Paso 1 de 5](../core/media/step-1of5.gif "Step_1of5")</span><span class="sxs-lookup"><span data-stu-id="4cb91-103">![Step 1 of 5](../core/media/step-1of5.gif "Step_1of5")</span></span>  
  
 <span data-ttu-id="4cb91-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="4cb91-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="4cb91-105">**Objetivo:** en este paso, creará un nuevo [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solución y un proyecto.</span><span class="sxs-lookup"><span data-stu-id="4cb91-105">**Objective:** In this step, you create a new [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solution and a project.</span></span>  
  
 <span data-ttu-id="4cb91-106">**Propósito:** usar el sistema de proyectos de BizTalk para crear parte o la totalidad de un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] aplicación o solución empresarial.</span><span class="sxs-lookup"><span data-stu-id="4cb91-106">**Purpose:** You use the BizTalk project system to create part or all of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] application or business solution.</span></span> <span data-ttu-id="4cb91-107">El elemento principal de una solución de este tipo es un proyecto de BizTalk, es decir, una colección de elementos como, por ejemplo, esquemas, orquestaciones, tipos de mensajes Web, clases, canalizaciones, asignaciones y referencias, que se pueden crear y generar en un ensamblado antes de implementarlo.</span><span class="sxs-lookup"><span data-stu-id="4cb91-107">The core element of any such solution is a BizTalk project—a collection of items, such as schemas, orchestrations, Web message types, classes, pipelines, maps, and references that you can build and generate into an assembly before deploying it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4cb91-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4cb91-108">Prerequisites</span></span>  
 <span data-ttu-id="4cb91-109">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="4cb91-109">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="4cb91-110">Antes de comenzar este paso debe completar los pasos descritos en [antes de empezar el Tutorial](../core/before-you-begin-the-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="4cb91-110">Before you begin this step you must complete the steps in [Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="4cb91-111">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="4cb91-111">Procedures</span></span>  
  
#### <a name="to-create-a-new-visual-studio-solutionproject"></a><span data-ttu-id="4cb91-112">Para crear un nuevo proyecto/solución de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4cb91-112">To create a new Visual Studio solution/project</span></span>  
  
1.  <span data-ttu-id="4cb91-113">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="4cb91-113">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="4cb91-114">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4cb91-114">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="4cb91-115">En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cb91-115">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="4cb91-116">Use</span><span class="sxs-lookup"><span data-stu-id="4cb91-116">Use this</span></span>|<span data-ttu-id="4cb91-117">Para</span><span class="sxs-lookup"><span data-stu-id="4cb91-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4cb91-118">**Plantillas instaladas**</span><span class="sxs-lookup"><span data-stu-id="4cb91-118">**Installed Templates**</span></span>|<span data-ttu-id="4cb91-119">Haga clic en **proyectos de BizTalk**, a continuación, haga clic en **proyecto vacío de servidor BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="4cb91-119">Click **BizTalk Projects**, then click **Empty BizTalk Server Project**.</span></span>|  
    |<span data-ttu-id="4cb91-120">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="4cb91-120">**Name**</span></span>|<span data-ttu-id="4cb91-121">Tipo de **EAISchemas**.</span><span class="sxs-lookup"><span data-stu-id="4cb91-121">Type **EAISchemas**.</span></span>|  
    |<span data-ttu-id="4cb91-122">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="4cb91-122">**Location**</span></span>|<span data-ttu-id="4cb91-123">Tipo de **C:\tutorial\Lessons**.</span><span class="sxs-lookup"><span data-stu-id="4cb91-123">Type **C:\tutorial\Lessons**.</span></span>|  
    |<span data-ttu-id="4cb91-124">**Nombre de solución**</span><span class="sxs-lookup"><span data-stu-id="4cb91-124">**Solution Name**</span></span>|<span data-ttu-id="4cb91-125">Tipo de **EAISolution**.</span><span class="sxs-lookup"><span data-stu-id="4cb91-125">Type **EAISolution**.</span></span>|  
    |<span data-ttu-id="4cb91-126">**Crear directorio para la solución**</span><span class="sxs-lookup"><span data-stu-id="4cb91-126">**Create directory for solution**</span></span>|<span data-ttu-id="4cb91-127">(se selecciona)</span><span class="sxs-lookup"><span data-stu-id="4cb91-127">(selected)</span></span>|  
  
4.  <span data-ttu-id="4cb91-128">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4cb91-128">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="4cb91-129">En el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="4cb91-129">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="4cb91-130">Síntesis</span><span class="sxs-lookup"><span data-stu-id="4cb91-130">What did I just do?</span></span>  
 <span data-ttu-id="4cb91-131">En este paso, abrió un nuevo proyecto y una solución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cb91-131">In this step, you opened a new project and a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4cb91-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4cb91-132">Next Steps</span></span>  
 <span data-ttu-id="4cb91-133">Creará el esquema para el mensaje de solicitud de reposición de inventario.</span><span class="sxs-lookup"><span data-stu-id="4cb91-133">You create the schema for the inventory replenishment request message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb91-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cb91-134">See Also</span></span>  
 <span data-ttu-id="4cb91-135">[Antes de empezar el Tutorial](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="4cb91-135">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="4cb91-136">[Paso 2: Crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="4cb91-136">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="4cb91-137">[Paso 3: Crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="4cb91-137">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="4cb91-138">[Paso 4: Crear el mapa](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="4cb91-138">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="4cb91-139">[Paso 5: Generar el proyecto EAISchemas](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="4cb91-139">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 <span data-ttu-id="4cb91-140">[Herramientas de desarrollo](../core/developer-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4cb91-140">[Developer Tools](../core/developer-tools.md) </span></span>  
 [<span data-ttu-id="4cb91-141">Trabajar con proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4cb91-141">Working with BizTalk Projects</span></span>](../core/working-with-biztalk-projects.md)