---
title: 'Módulo 3: Agregar un proyecto de canalización | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, creating pipelines
- projects, pipelines
- pipelines, adding to projects
ms.assetid: 38bf1629-df29-4bea-840b-60b354b06430
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85305614cec2757a91aa006238b3eb1ca4fbdbba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970661"
---
# <a name="module-3-adding-a-pipeline-project"></a><span data-ttu-id="e185d-102">Módulo 3: Agregar un proyecto de canalización</span><span class="sxs-lookup"><span data-stu-id="e185d-102">Module 3: Adding a Pipeline Project</span></span>
<span data-ttu-id="e185d-103">En este módulo, agregue un nuevo proyecto a la solución que contiene su envío personalizada y canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="e185d-103">In this module, you add a new project to your solution that contains your custom send and receive pipelines.</span></span> <span data-ttu-id="e185d-104">Puesto que está trabajando con los mensajes de SWIFT, que son archivos sin formato por naturaleza, no se puede utilizar las canalizaciones predeterminadas que se incluyen con Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e185d-104">Because you are working with SWIFT messages, which are flat file in nature, you cannot use the default pipelines that are included with Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span>  
  
 <span data-ttu-id="e185d-105">Los mensajes de SWIFT requieren niveles adicionales de validación de manera que Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] incluye componentes de ensamblador (ASM) para su uso con los mensajes de SWIFT y desensamblador personalizado (DASM).</span><span class="sxs-lookup"><span data-stu-id="e185d-105">SWIFT messages require additional levels of validation so Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes custom disassembler (DASM) and assembler (ASM) components for use with SWIFT messages.</span></span>  
  
 <span data-ttu-id="e185d-106">En este módulo, también se agregue una nueva canalización de proyecto, agregue de recepción y canalizaciones de envío y usar el SWIFT DASM y ASM.</span><span class="sxs-lookup"><span data-stu-id="e185d-106">In this module, you also add a new pipeline project, add receive and send pipelines, and use the SWIFT DASM and ASM.</span></span>  
  
 <span data-ttu-id="e185d-107">Seleccione la plantilla de proyecto de BizTalk expone las herramientas de BizTalk, como el asignador de BizTalk, dentro de Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="e185d-107">Selecting the BizTalk project template exposes the BizTalk tools, such as BizTalk Mapper, within the Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] development environment.</span></span>  
  
 <span data-ttu-id="e185d-108">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="e185d-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="e185d-109">Lección 1: Agregar un proyecto de canalizaciones a la solución</span><span class="sxs-lookup"><span data-stu-id="e185d-109">Lesson 1: Adding a Pipelines Project to the Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-adding-a-pipelines-project-to-the-solution.md)  
  
-   [<span data-ttu-id="e185d-110">Lección 2: Agregar referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="e185d-110">Lesson 2: Adding Project References</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)  
  
-   [<span data-ttu-id="e185d-111">Lección 3: Agregar una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="e185d-111">Lesson 3: Adding a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="e185d-112">Lección 4: Agregar el ensamblador y desensamblador de SWIFT al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="e185d-112">Lesson 4: Adding the SWIFT Assembler and Disassembler to the Toolbox</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)  
  
-   [<span data-ttu-id="e185d-113">Lección 5: Agregar el Desensamblador de SWIFT a una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="e185d-113">Lesson 5: Adding the SWIFT Disassembler to a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="e185d-114">Lección 6: Creación de una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="e185d-114">Lesson 6: Creating a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="e185d-115">Lección 7: Agregar el Desensamblador de SWIFT a una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="e185d-115">Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="e185d-116">Lección 8: Generación e implementación del ensamblado</span><span class="sxs-lookup"><span data-stu-id="e185d-116">Lesson 8: Building and Deploying the Assembly</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-8-building-and-deploying-the-assembly.md)