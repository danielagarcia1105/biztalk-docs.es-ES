---
title: Creación y modificación del proceso privado de Contoso | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, creating
- configuring, private processes
- private processes, configuring
- private process tutorial, creating private processes
- creating, private processes
- private process tutorial, configuring private processes
ms.assetid: 0690aaef-cd9e-46aa-8bd5-22744d5aec4c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 544dce433b439cae937b1328690f099b5b6ca592
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012157"
---
# <a name="creating-and-modifying-the-private-process-for-contoso"></a><span data-ttu-id="37a29-102">Creación y modificación del proceso privado de Contoso</span><span class="sxs-lookup"><span data-stu-id="37a29-102">Creating and Modifying the Private Process for Contoso</span></span>
<span data-ttu-id="37a29-103">Puede realizar tareas adicionales con los mensajes de RosettaNet al implementar la solución mediante la personalización del proceso privado dentro de Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37a29-103">You can perform additional tasks with RosettaNet-based messages when implementing your solution by customizing the private process within Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="37a29-104">Esta sección muestra cómo personalizar el proceso privado mediante el motor de reglas de negocios (BRE) para crear directivas y el Editor de BizTalk para personalizar la orquestación de procesos privado.</span><span class="sxs-lookup"><span data-stu-id="37a29-104">This section demonstrates how to customize the private process by using the Business Rule Engine (BRE) to create policies and BizTalk Editor to customize the private process orchestration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37a29-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="37a29-105">In This Section</span></span>  
  
-   [<span data-ttu-id="37a29-106">Paso 1: Agregar un proyecto de BizTalk existente a la solución de Contoso existente</span><span class="sxs-lookup"><span data-stu-id="37a29-106">Step 1: Adding an Existing BizTalk Project to the Existing Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution.md)  
  
-   [<span data-ttu-id="37a29-107">Paso 2: Definición y publicación del vocabulario de Contoso</span><span class="sxs-lookup"><span data-stu-id="37a29-107">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)  
  
-   [<span data-ttu-id="37a29-108">Paso 3: Definición, publicación e implementación de la directiva empresarial de Contoso</span><span class="sxs-lookup"><span data-stu-id="37a29-108">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)  
  
-   [<span data-ttu-id="37a29-109">Paso 4: Creación del proyecto HeaderHelper</span><span class="sxs-lookup"><span data-stu-id="37a29-109">Step 4: Creating the HeaderHelper Project</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)  
  
-   [<span data-ttu-id="37a29-110">Paso 5: Modificación de la orquestación de procesos privados de Contoso</span><span class="sxs-lookup"><span data-stu-id="37a29-110">Step 5: Modifying the Contoso Private Process Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)  
  
-   [<span data-ttu-id="37a29-111">Paso 6: Configuración de las formas de orquestación (Contoso)</span><span class="sxs-lookup"><span data-stu-id="37a29-111">Step 6: Configuring Orchestration Shapes (Contoso)</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)  
  
-   [<span data-ttu-id="37a29-112">Paso 7: Creación y configuración de puertos</span><span class="sxs-lookup"><span data-stu-id="37a29-112">Step 7: Creating and Configuring Ports</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md)  
  
-   [<span data-ttu-id="37a29-113">Paso 8: Creación e implementación de la orquestación de Contoso</span><span class="sxs-lookup"><span data-stu-id="37a29-113">Step 8: Building and Deploying the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)  
  
-   [<span data-ttu-id="37a29-114">Paso 9: Inicio de la orquestación de Contoso</span><span class="sxs-lookup"><span data-stu-id="37a29-114">Step 9: Starting the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)