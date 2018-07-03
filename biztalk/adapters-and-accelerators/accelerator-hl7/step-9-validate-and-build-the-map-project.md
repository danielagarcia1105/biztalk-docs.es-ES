---
title: 'Paso 9: Validar y compilar el proyecto de asignación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, maps
- message enrichment tutorial, maps
- maps, building
- maps, validating
ms.assetid: 10716b0b-702c-48bb-85a9-d58d8f33b68b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb542ffd185cfa0f84c1e73ce17becfacdb709f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966653"
---
# <a name="step-9-validate-and-build-the-map-project"></a><span data-ttu-id="ef297-102">Paso 9: Validar y compilar el proyecto de mapa</span><span class="sxs-lookup"><span data-stu-id="ef297-102">Step 9: Validate and Build the Map Project</span></span>
<span data-ttu-id="ef297-103">En este paso, utilizará el **validar asignación** comando para determinar si el mapa contiene alguna incoherencia interna o tiene otros problemas que podría impedir que se utilice eficazmente para esquemas de asignación.</span><span class="sxs-lookup"><span data-stu-id="ef297-103">In this step, you use the **Validate Map** command to determine if the map contains any internal inconsistencies, or has other issues that would prevent it from being used effectively for mapping schemas.</span></span> <span data-ttu-id="ef297-104">También compilar el proyecto para generar un ensamblado que contiene los recursos (esquemas y la asignación) que ha creado.</span><span class="sxs-lookup"><span data-stu-id="ef297-104">You also build the project to generate an assembly that contains the resources (schemas and the map) that you created.</span></span> <span data-ttu-id="ef297-105">Esto también garantiza que no hay ningún error de compilación en el trabajo que se ha completado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="ef297-105">This also ensures that there are no compile errors in the work that you have completed so far.</span></span>  
  
### <a name="to-validate-the-map-project"></a><span data-ttu-id="ef297-106">Para validar el proyecto de mapa</span><span class="sxs-lookup"><span data-stu-id="ef297-106">To validate the map project</span></span>  
  
1.  <span data-ttu-id="ef297-107">En el Explorador de soluciones, haga clic en el **DoorbellMap.btm** asignar y, a continuación, haga clic en **validar asignación**.</span><span class="sxs-lookup"><span data-stu-id="ef297-107">In Solution Explorer, right-click the **DoorbellMap.btm** map, and then click **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="ef297-108">Asegúrese de que aparece un mensaje de éxito en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="ef297-108">Ensure that a success message appears in the output window.</span></span> <span data-ttu-id="ef297-109">Algunas advertencias que pueden aparecer porque no está asignando a todos los elementos disponibles en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="ef297-109">Some warnings may appear because you are not mapping to all available elements in the destination schema.</span></span>  
  
     <span data-ttu-id="ef297-110">Si no aparece ningún mensaje de éxito, solucione el proyecto de mapa.</span><span class="sxs-lookup"><span data-stu-id="ef297-110">If no success message appears, troubleshoot the map project.</span></span>  
  
### <a name="to-build-the-map-project"></a><span data-ttu-id="ef297-111">Para compilar el proyecto de mapa</span><span class="sxs-lookup"><span data-stu-id="ef297-111">To build the map project</span></span>  
  
- <span data-ttu-id="ef297-112">En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**y, a continuación, haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="ef297-112">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Build**.</span></span> <span data-ttu-id="ef297-113">Asegúrese de que aparece un mensaje de éxito en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="ef297-113">Ensure that a success message appears in the output window.</span></span>  
  
   <span data-ttu-id="ef297-114">Si no aparece ningún mensaje de éxito, solucione el proyecto de mapa.</span><span class="sxs-lookup"><span data-stu-id="ef297-114">If no success message appears, troubleshoot the map project.</span></span>  
  
  <span data-ttu-id="ef297-115">Continúe con [paso 10: crear una orquestación](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="ef297-115">Proceed to [Step 10: Create an Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef297-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef297-116">See Also</span></span>  
 [<span data-ttu-id="ef297-117">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="ef297-117">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)