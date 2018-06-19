---
title: 'Módulo 3: Agregar un proyecto de canalización | Documentos de Microsoft'
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
ms.openlocfilehash: 2d14e0f334514fd35a7f8de963f7fb457e3fbbd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208164"
---
# <a name="module-3-adding-a-pipeline-project"></a><span data-ttu-id="59bc1-102">Módulo 3: Agregar un proyecto de canalización</span><span class="sxs-lookup"><span data-stu-id="59bc1-102">Module 3: Adding a Pipeline Project</span></span>
<span data-ttu-id="59bc1-103">En este módulo, agregue un nuevo proyecto a la solución que contiene su envío personalizada y canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="59bc1-103">In this module, you add a new project to your solution that contains your custom send and receive pipelines.</span></span> <span data-ttu-id="59bc1-104">Dado que está trabajando con los mensajes de SWIFT, que son los archivos planos de la naturaleza, no se puede utilizar las canalizaciones predeterminadas que se incluyen con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59bc1-104">Because you are working with SWIFT messages, which are flat file in nature, you cannot use the default pipelines that are included with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span>  
  
 <span data-ttu-id="59bc1-105">Los mensajes de SWIFT requieren niveles adicionales de validación, por lo que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] incluye componentes de ensamblador (ASM) para su uso con los mensajes de SWIFT y desensamblador personalizado (DASM).</span><span class="sxs-lookup"><span data-stu-id="59bc1-105">SWIFT messages require additional levels of validation so [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes custom disassembler (DASM) and assembler (ASM) components for use with SWIFT messages.</span></span>  
  
 <span data-ttu-id="59bc1-106">En este módulo, también se agregará una nueva canalización de proyecto de equipo y agregar de recepción y canalizaciones de envío y use el SWIFT DASM y ASM.</span><span class="sxs-lookup"><span data-stu-id="59bc1-106">In this module, you also add a new pipeline project, add receive and send pipelines, and use the SWIFT DASM and ASM.</span></span>  
  
 <span data-ttu-id="59bc1-107">Al seleccionar la plantilla de proyecto de BizTalk expone las herramientas de BizTalk, como el asignador de BizTalk, en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="59bc1-107">Selecting the BizTalk project template exposes the BizTalk tools, such as BizTalk Mapper, within the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] development environment.</span></span>  
  
 <span data-ttu-id="59bc1-108">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="59bc1-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="59bc1-109">Lección 1: Agregar un proyecto de canalizaciones a la solución</span><span class="sxs-lookup"><span data-stu-id="59bc1-109">Lesson 1: Adding a Pipelines Project to the Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-adding-a-pipelines-project-to-the-solution.md)  
  
-   [<span data-ttu-id="59bc1-110">Lección 2: Agregar referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="59bc1-110">Lesson 2: Adding Project References</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)  
  
-   [<span data-ttu-id="59bc1-111">Lección 3: Agregar una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="59bc1-111">Lesson 3: Adding a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="59bc1-112">Lección 4: Agregar el SWIFT ensamblador y desensamblador al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="59bc1-112">Lesson 4: Adding the SWIFT Assembler and Disassembler to the Toolbox</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)  
  
-   [<span data-ttu-id="59bc1-113">Lección 5: Agregar el Desensamblador SWIFT a una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="59bc1-113">Lesson 5: Adding the SWIFT Disassembler to a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="59bc1-114">Lección 6: Crear una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="59bc1-114">Lesson 6: Creating a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="59bc1-115">Lección 7: Agregar el ensamblador SWIFT a una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="59bc1-115">Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="59bc1-116">Lección 8: Crear e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="59bc1-116">Lesson 8: Building and Deploying the Assembly</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-8-building-and-deploying-the-assembly.md)