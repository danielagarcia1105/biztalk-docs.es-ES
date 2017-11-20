---
title: Crear y modificar el proceso privado para Contoso | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private processes, creating
- configuring, private processes
- private processes, configuring
- private process tutorial, creating private processes
- creating, private processes
- private process tutorial, configuring private processes
ms.assetid: 0690aaef-cd9e-46aa-8bd5-22744d5aec4c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9b1749c941e78963abd4768afbb5ce0668ee3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-modifying-the-private-process-for-contoso"></a><span data-ttu-id="7a589-102">Crear y modificar el proceso privado de Contoso</span><span class="sxs-lookup"><span data-stu-id="7a589-102">Creating and Modifying the Private Process for Contoso</span></span>
<span data-ttu-id="7a589-103">Se pueden realizar tareas adicionales con mensajes de RosettaNet al implementar la solución personalizando el proceso privado dentro de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a589-103">You can perform additional tasks with RosettaNet-based messages when implementing your solution by customizing the private process within [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="7a589-104">Esta sección muestra cómo personalizar el proceso privado mediante el motor de reglas de negocios (BRE) para crear directivas y el Editor de BizTalk para personalizar la orquestación de procesos privados.</span><span class="sxs-lookup"><span data-stu-id="7a589-104">This section demonstrates how to customize the private process by using the Business Rule Engine (BRE) to create policies and BizTalk Editor to customize the private process orchestration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a589-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7a589-105">In This Section</span></span>  
  
-   [<span data-ttu-id="7a589-106">Paso 1: Agregar un proyecto de BizTalk existente a la solución existente de Contoso</span><span class="sxs-lookup"><span data-stu-id="7a589-106">Step 1: Adding an Existing BizTalk Project to the Existing Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution.md)  
  
-   [<span data-ttu-id="7a589-107">Paso 2: Definir y publicar el vocabulario de Contoso</span><span class="sxs-lookup"><span data-stu-id="7a589-107">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)  
  
-   [<span data-ttu-id="7a589-108">Paso 3: Definir, publicar e implementar la directiva empresarial de Contoso</span><span class="sxs-lookup"><span data-stu-id="7a589-108">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)  
  
-   [<span data-ttu-id="7a589-109">Paso 4: Crear el proyecto HeaderHelper</span><span class="sxs-lookup"><span data-stu-id="7a589-109">Step 4: Creating the HeaderHelper Project</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)  
  
-   [<span data-ttu-id="7a589-110">Paso 5: Modificar la orquestación de procesos privados de Contoso</span><span class="sxs-lookup"><span data-stu-id="7a589-110">Step 5: Modifying the Contoso Private Process Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)  
  
-   [<span data-ttu-id="7a589-111">Paso 6: Configurar formas de orquestación (Contoso)</span><span class="sxs-lookup"><span data-stu-id="7a589-111">Step 6: Configuring Orchestration Shapes (Contoso)</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)  
  
-   [<span data-ttu-id="7a589-112">Paso 7: Crear y configurar puertos</span><span class="sxs-lookup"><span data-stu-id="7a589-112">Step 7: Creating and Configuring Ports</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md)  
  
-   [<span data-ttu-id="7a589-113">Paso 8: Crear e implementar la orquestación de Contoso</span><span class="sxs-lookup"><span data-stu-id="7a589-113">Step 8: Building and Deploying the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)  
  
-   [<span data-ttu-id="7a589-114">Paso 9: Iniciar la orquestación de Contoso</span><span class="sxs-lookup"><span data-stu-id="7a589-114">Step 9: Starting the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)