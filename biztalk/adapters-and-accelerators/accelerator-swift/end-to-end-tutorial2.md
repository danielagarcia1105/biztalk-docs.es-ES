---
title: To-End Tutorial2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, about the tutorial
- tutorial
- tutorial, workflow
ms.assetid: 1aba93b9-6991-46ef-a3bc-3815a5ff473f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da298e0c69de7a351e64aa33ac48611700de3621
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980677"
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="dfd22-102">Tutorial de extremo a otro</span><span class="sxs-lookup"><span data-stu-id="dfd22-102">End-to-End Tutorial</span></span>
<span data-ttu-id="dfd22-103">Este tutorial contiene los pasos detallados que describen cómo crear y configurar Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="dfd22-103">This tutorial contains detailed steps that describe how to create and set up a Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] solution.</span></span> <span data-ttu-id="dfd22-104">Los módulos y lecciones utilizan Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] para crear el esquema, asigna las orquestaciones y componentes de canalización con A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="dfd22-104">The modules and lessons use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] to create the schema, maps orchestrations, and pipeline components using A4SWIFT.</span></span>  
  
 <span data-ttu-id="dfd22-105">La siguiente ilustración muestra el flujo de trabajo de un escenario de uso del motor de integración común para una solución de A4SWIFT-to-end.</span><span class="sxs-lookup"><span data-stu-id="dfd22-105">The following figure shows the workflow of a common Integration Engine usage scenario for an end-to-end A4SWIFT solution.</span></span>  
  
 <span data-ttu-id="dfd22-106">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-tut-wklw.gif "FSA_Tut_wklw")</span><span class="sxs-lookup"><span data-stu-id="dfd22-106">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-tut-wklw.gif "FSA_Tut_wklw")</span></span>  
  
|<span data-ttu-id="dfd22-107">Clave de Tutorial de flujo de trabajo de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="dfd22-107">A4SWIFT Tutorial Workflow Key</span></span>|  
|-----------------------------------|  
|<span data-ttu-id="dfd22-108">**ASM** = ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="dfd22-108">**ASM** = SWIFT Assembler</span></span>|  
|<span data-ttu-id="dfd22-109">**DASM** = Desensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="dfd22-109">**DASM** = SWIFT Disassembler</span></span>|  
|<span data-ttu-id="dfd22-110">**MTxxx** = tipo de mensaje de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="dfd22-110">**MTxxx** = A4SWIFT Message type</span></span>|  
|<span data-ttu-id="dfd22-111">**SIPN** = red IP segura SWIFT</span><span class="sxs-lookup"><span data-stu-id="dfd22-111">**SIPN** = SWIFT Secure IP Network</span></span>|  
  
 <span data-ttu-id="dfd22-112">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="dfd22-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="dfd22-113">Módulo 1: Creación de una solución de SWIFT</span><span class="sxs-lookup"><span data-stu-id="dfd22-113">Module 1: Creating a SWIFT Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/module-1-creating-a-swift-solution.md)  
  
-   [<span data-ttu-id="dfd22-114">Módulo 2: Agregar un nuevo proyecto de esquemas</span><span class="sxs-lookup"><span data-stu-id="dfd22-114">Module 2: Adding a New Schemas Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)  
  
-   [<span data-ttu-id="dfd22-115">Módulo 3: Agregar un proyecto de canalización</span><span class="sxs-lookup"><span data-stu-id="dfd22-115">Module 3: Adding a Pipeline Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)  
  
-   [<span data-ttu-id="dfd22-116">Módulo 4: Agregar una recepción de ubicación de XML y un puerto de envío de archivos planos</span><span class="sxs-lookup"><span data-stu-id="dfd22-116">Module 4: Adding an XML Receive Location and Flat File Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)  
  
-   [<span data-ttu-id="dfd22-117">Módulo 5: Agregar una ubicación de recepción y un puerto de envío de XML</span><span class="sxs-lookup"><span data-stu-id="dfd22-117">Module 5: Adding a Flat File Receive Location and XML Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)  
  
-   [<span data-ttu-id="dfd22-118">Módulo 6: Implementación de las reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="dfd22-118">Module 6: Deploying the Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)  
  
-   [<span data-ttu-id="dfd22-119">Módulo 7: Probar una instancia de archivo plano válida</span><span class="sxs-lookup"><span data-stu-id="dfd22-119">Module 7: Testing a Valid Flat File Instance</span></span>](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md)