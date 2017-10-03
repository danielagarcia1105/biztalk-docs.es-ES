---
title: 'Paso 9: Validar y compilar el proyecto de mapa | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, maps
- message enrichment tutorial, maps
- maps, building
- maps, validating
ms.assetid: 10716b0b-702c-48bb-85a9-d58d8f33b68b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1eb4580a9c89534204e492aebdd21988a6ce0e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-9-validate-and-build-the-map-project"></a><span data-ttu-id="5817a-102">Paso 9: Validar y compilar el proyecto de mapa</span><span class="sxs-lookup"><span data-stu-id="5817a-102">Step 9: Validate and Build the Map Project</span></span>
<span data-ttu-id="5817a-103">En este paso, usará el **validar asignación** comando para determinar si la asignación contiene alguna incoherencia interna, u otros problemas que impedirían que se utilice eficazmente para esquemas de asignación.</span><span class="sxs-lookup"><span data-stu-id="5817a-103">In this step, you use the **Validate Map** command to determine if the map contains any internal inconsistencies, or has other issues that would prevent it from being used effectively for mapping schemas.</span></span> <span data-ttu-id="5817a-104">También se compile el proyecto para generar un ensamblado que contiene los recursos (esquemas y la asignación) que ha creado.</span><span class="sxs-lookup"><span data-stu-id="5817a-104">You also build the project to generate an assembly that contains the resources (schemas and the map) that you created.</span></span> <span data-ttu-id="5817a-105">Esto también garantiza que no hay ningún error de compilación en el trabajo que se han completado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="5817a-105">This also ensures that there are no compile errors in the work that you have completed so far.</span></span>  
  
### <a name="to-validate-the-map-project"></a><span data-ttu-id="5817a-106">Para validar el proyecto de mapa</span><span class="sxs-lookup"><span data-stu-id="5817a-106">To validate the map project</span></span>  
  
1.  <span data-ttu-id="5817a-107">En el Explorador de soluciones, haga clic en el **DoorbellMap.btm** asignar y, a continuación, haga clic en **validar asignación**.</span><span class="sxs-lookup"><span data-stu-id="5817a-107">In Solution Explorer, right-click the **DoorbellMap.btm** map, and then click **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="5817a-108">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="5817a-108">Ensure that a success message appears in the output window.</span></span> <span data-ttu-id="5817a-109">Algunas advertencias que se deba a que no va a asignar a todos los elementos disponibles en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="5817a-109">Some warnings may appear because you are not mapping to all available elements in the destination schema.</span></span>  
  
     <span data-ttu-id="5817a-110">Si no aparece ningún mensaje de correcto, solucione el proyecto de mapa.</span><span class="sxs-lookup"><span data-stu-id="5817a-110">If no success message appears, troubleshoot the map project.</span></span>  
  
### <a name="to-build-the-map-project"></a><span data-ttu-id="5817a-111">Para compilar el proyecto de mapa</span><span class="sxs-lookup"><span data-stu-id="5817a-111">To build the map project</span></span>  
  
-   <span data-ttu-id="5817a-112">En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="5817a-112">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Build**.</span></span> <span data-ttu-id="5817a-113">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="5817a-113">Ensure that a success message appears in the output window.</span></span>  
  
     <span data-ttu-id="5817a-114">Si no aparece ningún mensaje de correcto, solucione el proyecto de mapa.</span><span class="sxs-lookup"><span data-stu-id="5817a-114">If no success message appears, troubleshoot the map project.</span></span>  
  
 <span data-ttu-id="5817a-115">Continúe con [paso 10: crear una orquestación](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="5817a-115">Proceed to [Step 10: Create an Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5817a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5817a-116">See Also</span></span>  
 [<span data-ttu-id="5817a-117">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="5817a-117">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)