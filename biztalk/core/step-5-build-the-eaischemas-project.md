---
title: 'Paso 5: Generar el proyecto EAISchemas | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20cd368-7446-4861-8d71-5bc25ce408a2
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394d9df78f7064df8501ed43149bd26793533c47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278156"
---
# <a name="step-5-build-the-eaischemas-project"></a><span data-ttu-id="843f3-102">Paso 5: Generar el proyecto EAISchemas</span><span class="sxs-lookup"><span data-stu-id="843f3-102">Step 5: Build the EAISchemas Project</span></span>
<span data-ttu-id="843f3-103">![Paso 5 de 5](../core/media/step-5of5.gif "Step_5of5")</span><span class="sxs-lookup"><span data-stu-id="843f3-103">![Step 5 of 5](../core/media/step-5of5.gif "Step_5of5")</span></span>  
  
 <span data-ttu-id="843f3-104">**Tiempo en completarse:** 6 minutos</span><span class="sxs-lookup"><span data-stu-id="843f3-104">**Time to complete:** 6 minutes</span></span>  
  
 <span data-ttu-id="843f3-105">**Objetivo:** en este paso, compilará el proyecto EAISchemas.</span><span class="sxs-lookup"><span data-stu-id="843f3-105">**Objective:** In this step, you compile the EAISchemas project.</span></span>  
  
 <span data-ttu-id="843f3-106">**Propósito:** el aspecto más importante de Microsoft BizTalk Server y .NET Framework es que todos los artefactos de BizTalk Server, asignaciones, esquemas, orquestaciones y canalizaciones, se compilan en ensamblados. NET.</span><span class="sxs-lookup"><span data-stu-id="843f3-106">**Purpose:** The most important aspect of Microsoft BizTalk Server and the .NET Framework is that all BizTalk Server artifacts; maps, schemas, orchestrations, and pipelines, get compiled into .NET assemblies.</span></span> <span data-ttu-id="843f3-107">Las dos consecuencias más importantes de este diseño son que estos ensamblados deben tener nombres seguros y, a causa de ello, que siguen reglas de control de versiones .NET.</span><span class="sxs-lookup"><span data-stu-id="843f3-107">The two most important implications of this design are that these assemblies must have strong names, and because of that, they also follow .NET versioning rules.</span></span> <span data-ttu-id="843f3-108">La repercusión principal de esto es que un proyecto de BizTalk, una vez generado con una versión concreta de otro proyecto o ensamblado .NET (incluidos los proyectos de BizTalk), sigue utilizando esa versión hasta que se vuelve a generar con una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="843f3-108">The main implication of this is that a BizTalk project, once built against a particular version of another .NET project or assembly (including BizTalk projects), continues to use that version until it has been rebuilt against a newer version.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="843f3-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="843f3-109">Prerequisites</span></span>  
 <span data-ttu-id="843f3-110">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="843f3-110">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="843f3-111">Antes de comenzar este paso, debe completar los siguientes:</span><span class="sxs-lookup"><span data-stu-id="843f3-111">Before you begin this step you must complete the following steps:</span></span>  
  
    -   [<span data-ttu-id="843f3-112">Paso 1: Crear el proyecto EAISchemas</span><span class="sxs-lookup"><span data-stu-id="843f3-112">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
  
    -   [<span data-ttu-id="843f3-113">Paso 2: Crear el esquema de solicitud de inventario</span><span class="sxs-lookup"><span data-stu-id="843f3-113">Step 2: Create the Inventory Request Schema</span></span>](../core/step-2-create-the-inventory-request-schema.md) 
  
    -   [<span data-ttu-id="843f3-114">Paso 3: Crear el esquema de declinación de solicitud</span><span class="sxs-lookup"><span data-stu-id="843f3-114">Step 3: Create the Request Decline Schema</span></span>](../core/step-3-create-the-request-decline-schema.md)  
  
    -   [<span data-ttu-id="843f3-115">Paso 4: Crear el mapa</span><span class="sxs-lookup"><span data-stu-id="843f3-115">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)  
  
## <a name="procedures"></a><span data-ttu-id="843f3-116">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="843f3-116">Procedures</span></span>  
  
#### <a name="to-build-the-eaischemas-project"></a><span data-ttu-id="843f3-117">Para generar el proyecto EAISchemas</span><span class="sxs-lookup"><span data-stu-id="843f3-117">To build the EAISchemas project</span></span>  
  
1.  <span data-ttu-id="843f3-118">En el Explorador de soluciones, haga clic en **EAISchemas**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="843f3-118">In Solution Explorer, right-click **EAISchemas**, and then click **Build**.</span></span>  
  
     <span data-ttu-id="843f3-119">En la parte inferior de la pantalla debe aparecer:</span><span class="sxs-lookup"><span data-stu-id="843f3-119">The bottom of the screen should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="843f3-120">Síntesis</span><span class="sxs-lookup"><span data-stu-id="843f3-120">What did I just do?</span></span>  
 <span data-ttu-id="843f3-121">En este paso, ha generado el proyecto EAISchemas para crear un archivo de ensamblado (DLL).</span><span class="sxs-lookup"><span data-stu-id="843f3-121">In this step, you built the EAISchemas project to generate an assembly file (DLL).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="843f3-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="843f3-122">Next Steps</span></span>  
 <span data-ttu-id="843f3-123">Crear el proceso empresarial que se evalúa como el contenido del mensaje de solicitud de reposición de inventario con respecto a los criterios de aprobación en [lección 2: definir el proceso empresarial](../core/lesson-2-define-the-business-process.md).</span><span class="sxs-lookup"><span data-stu-id="843f3-123">You create the business process that evaluates the contents of the inventory replenishment request message against approval criteria in [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="843f3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="843f3-124">See Also</span></span>  
 <span data-ttu-id="843f3-125">[Paso 1: Crear el proyecto EAISchemas](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="843f3-125">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="843f3-126">[Paso 2: Crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="843f3-126">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="843f3-127">[Paso 3: Crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="843f3-127">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 [<span data-ttu-id="843f3-128">Paso 4: Crear el mapa</span><span class="sxs-lookup"><span data-stu-id="843f3-128">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)