---
title: To-End Tutorial2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorial, about the tutorial
- tutorial
- tutorial, workflow
ms.assetid: 1aba93b9-6991-46ef-a3bc-3815a5ff473f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c4022595ed05cb779d11e09d66080024ac76654
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="d5b04-102">Tutorial de extremo a extremo</span><span class="sxs-lookup"><span data-stu-id="d5b04-102">End-to-End Tutorial</span></span>
<span data-ttu-id="d5b04-103">Este tutorial contiene los pasos detallados que explican cómo crear y configurar un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="d5b04-103">This tutorial contains detailed steps that describe how to create and set up a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] solution.</span></span> <span data-ttu-id="d5b04-104">El uso de módulos y lecciones [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] para crear el esquema, asigna las orquestaciones y los componentes de canalización con A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="d5b04-104">The modules and lessons use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] to create the schema, maps orchestrations, and pipeline components using A4SWIFT.</span></span>  
  
 <span data-ttu-id="d5b04-105">La siguiente ilustración muestra el flujo de trabajo de un escenario de uso común de motor de integración para una solución de A4SWIFT-to-end.</span><span class="sxs-lookup"><span data-stu-id="d5b04-105">The following figure shows the workflow of a common Integration Engine usage scenario for an end-to-end A4SWIFT solution.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-tut-wklw.gif "FSA_Tut_wklw")  
  
|<span data-ttu-id="d5b04-106">Clave de Tutorial de flujo de trabajo de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="d5b04-106">A4SWIFT Tutorial Workflow Key</span></span>|  
|-----------------------------------|  
|<span data-ttu-id="d5b04-107">**ASM** = ensamblador SWIFT</span><span class="sxs-lookup"><span data-stu-id="d5b04-107">**ASM** = SWIFT Assembler</span></span>|  
|<span data-ttu-id="d5b04-108">**DASM** = Desensamblador SWIFT</span><span class="sxs-lookup"><span data-stu-id="d5b04-108">**DASM** = SWIFT Disassembler</span></span>|  
|<span data-ttu-id="d5b04-109">**MTxxx** = tipo de mensaje de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="d5b04-109">**MTxxx** = A4SWIFT Message type</span></span>|  
|<span data-ttu-id="d5b04-110">**SIPN** = red IP segura SWIFT</span><span class="sxs-lookup"><span data-stu-id="d5b04-110">**SIPN** = SWIFT Secure IP Network</span></span>|  
  
 <span data-ttu-id="d5b04-111">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="d5b04-111">This section contains:</span></span>  
  
-   [<span data-ttu-id="d5b04-112">Módulo 1: Crear una solución sencilla</span><span class="sxs-lookup"><span data-stu-id="d5b04-112">Module 1: Creating a SWIFT Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/module-1-creating-a-swift-solution.md)  
  
-   [<span data-ttu-id="d5b04-113">Módulo 2: Agregar un nuevo proyecto de esquemas</span><span class="sxs-lookup"><span data-stu-id="d5b04-113">Module 2: Adding a New Schemas Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)  
  
-   [<span data-ttu-id="d5b04-114">Módulo 3: Agregar un proyecto de canalización</span><span class="sxs-lookup"><span data-stu-id="d5b04-114">Module 3: Adding a Pipeline Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)  
  
-   [<span data-ttu-id="d5b04-115">Módulo 4: Agregar un documento XML de recepción ubicación y el puerto de envío de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="d5b04-115">Module 4: Adding an XML Receive Location and Flat File Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)  
  
-   [<span data-ttu-id="d5b04-116">Módulo 5: Agregar un archivo plano ubicación de recepción y el puerto de envío de XML</span><span class="sxs-lookup"><span data-stu-id="d5b04-116">Module 5: Adding a Flat File Receive Location and XML Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)  
  
-   [<span data-ttu-id="d5b04-117">Módulo 6: Implementar las reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="d5b04-117">Module 6: Deploying the Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)  
  
-   [<span data-ttu-id="d5b04-118">Módulo 7: Probar una instancia de archivo sin formato válido</span><span class="sxs-lookup"><span data-stu-id="d5b04-118">Module 7: Testing a Valid Flat File Instance</span></span>](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md)