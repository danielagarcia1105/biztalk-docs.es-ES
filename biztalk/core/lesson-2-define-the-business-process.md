---
title: 'Lección 2: Definir el proceso empresarial | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial, defining business processes
ms.assetid: 644aa049-4dd7-4392-b97f-31b1f29e12bd
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a2a9512fe847fdf50957456ec3d3eeff087c33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262052"
---
# <a name="lesson-2-define-the-business-process"></a><span data-ttu-id="04309-102">Lección 2: Definir el proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="04309-102">Lesson 2: Define the Business Process</span></span>
<span data-ttu-id="04309-103">En esta lección, creará el segundo proyecto de la solución Integration(EAI) de aplicación de empresa.</span><span class="sxs-lookup"><span data-stu-id="04309-103">In this lesson, you create the second project in the Enterprise Application Integration(EAI) solution.</span></span> <span data-ttu-id="04309-104">Este proyecto contiene una orquestación.</span><span class="sxs-lookup"><span data-stu-id="04309-104">This project contains an orchestration.</span></span>  
  
 <span data-ttu-id="04309-105">En el escenario EAI, la aplicación de almacén envía un mensaje de reposición de inventario para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="04309-105">In the EAI scenario, the warehouse application sends an inventory replenishment message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="04309-106">utiliza la orquestación que ha creado para automatizar el proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="04309-106"> uses the orchestration you create to automate the business process.</span></span> <span data-ttu-id="04309-107">La orquestación proporciona el flujo de trabajo, las acciones y las expresiones para mover los mensajes por el sistema y procesar su contenido.</span><span class="sxs-lookup"><span data-stu-id="04309-107">The orchestration provides the workflow, actions, and expressions to move messages through the system and process their contents.</span></span>  
  
 <span data-ttu-id="04309-108">Por último, compile el proyecto antes de iniciar [lección 3: implementar la solución](../core/lesson-3-deploy-the-solution.md).</span><span class="sxs-lookup"><span data-stu-id="04309-108">Finally you build the project before starting [Lesson 3: Deploy the Solution](../core/lesson-3-deploy-the-solution.md).</span></span>  
  
 <span data-ttu-id="04309-109">Para obtener más información, consulte [crear orquestaciones utilizando Diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md).</span><span class="sxs-lookup"><span data-stu-id="04309-109">For more information, see [Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04309-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="04309-110">In This Section</span></span>  
  
-   [<span data-ttu-id="04309-111">Paso 1: Agregar el proyecto EAIOrchestration a la solución</span><span class="sxs-lookup"><span data-stu-id="04309-111">Step 1: Add EAIOrchestration Project to the Solution</span></span>](../core/step-1-add-eaiorchestration-project-to-the-solution.md)  
  
-   [<span data-ttu-id="04309-112">Paso 2: Definir el proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="04309-112">Step 2: Define the Business Process</span></span>](../core/step-2-define-the-business-process.md)  
  
-   [<span data-ttu-id="04309-113">Paso 3: Agregar puertos a la orquestación</span><span class="sxs-lookup"><span data-stu-id="04309-113">Step 3: Add Ports to the Orchestration</span></span>](../core/step-3-add-ports-to-the-orchestration.md)  
  
-   [<span data-ttu-id="04309-114">Paso 4: Crear el proyecto EAIOrchestration</span><span class="sxs-lookup"><span data-stu-id="04309-114">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)  
  
## <a name="see-also"></a><span data-ttu-id="04309-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="04309-115">See Also</span></span>  
 <span data-ttu-id="04309-116">[Antes de empezar el Tutorial](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="04309-116">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="04309-117">[Lección 1: Definir los esquemas y un mapa](../core/lesson-1-define-schemas-and-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="04309-117">[Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md) </span></span>  
 [<span data-ttu-id="04309-118">Lección 3: Implementar la solución</span><span class="sxs-lookup"><span data-stu-id="04309-118">Lesson 3: Deploy the Solution</span></span>](../core/lesson-3-deploy-the-solution.md)