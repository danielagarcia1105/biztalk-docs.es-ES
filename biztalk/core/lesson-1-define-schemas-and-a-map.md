---
title: "Lección 1: Definir esquemas y una asignación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: enterprise application integration tutorial, creating solutions
ms.assetid: 4fe7720d-722e-4fa0-a556-477fc66ffa12
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce6411a7a4ffa80b72bad2d84766bf773bbfb42f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-1-define-schemas-and-a-map"></a><span data-ttu-id="7dfc2-102">Lección 1: Definir los esquemas y una asignación</span><span class="sxs-lookup"><span data-stu-id="7dfc2-102">Lesson 1: Define Schemas and a Map</span></span>
<span data-ttu-id="7dfc2-103">En esta lección creará y generará el primer proyecto de la solución de integración de aplicaciones empresariales (EAI).</span><span class="sxs-lookup"><span data-stu-id="7dfc2-103">In this lesson, you create and build the first project in the enterprise application integration (EAI) solution.</span></span> <span data-ttu-id="7dfc2-104">El primer proyecto contiene dos esquemas de mensaje y una asignación.</span><span class="sxs-lookup"><span data-stu-id="7dfc2-104">The project contains two message schemas, and a map.</span></span>  
  
 <span data-ttu-id="7dfc2-105">En la solución EAI, un sistema de almacén envía una solicitud de mensaje de reposición de inventario a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="7dfc2-105">In the EAI solution, a warehouse system sends a request message for inventory replenishment to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing.</span></span> <span data-ttu-id="7dfc2-106">En esta lección se crearán los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="7dfc2-106">In this lesson, you create the following items:</span></span>  
  
-   <span data-ttu-id="7dfc2-107">La solución EAI que contiene el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7dfc2-107">The EAI solution, to hold the project.</span></span>  
  
-   <span data-ttu-id="7dfc2-108">El proyecto que contiene los esquemas y la asignación.</span><span class="sxs-lookup"><span data-stu-id="7dfc2-108">The project, to hold the schemas and the map.</span></span>  
  
-   <span data-ttu-id="7dfc2-109">El esquema del mensaje que el almacén envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para solicitar la reposición de inventario.</span><span class="sxs-lookup"><span data-stu-id="7dfc2-109">The schema, for the message the warehouse sends to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to request inventory replenishment.</span></span>  
  
-   <span data-ttu-id="7dfc2-110">El esquema para el mensaje que el almacén está esperando cuando se rechaza una solicitud.</span><span class="sxs-lookup"><span data-stu-id="7dfc2-110">The schema, for the message that the warehouse is expecting when a request is rejected.</span></span>  
  
-   <span data-ttu-id="7dfc2-111">Una asignación para cambiar el formato de un mensaje de solicitud para crear un mensaje de declinación de solicitud.</span><span class="sxs-lookup"><span data-stu-id="7dfc2-111">A map, for reformatting a request message to create a request decline message.</span></span>  
  
 <span data-ttu-id="7dfc2-112">Por último, compile el proyecto antes de iniciar [lección 2: definir el proceso empresarial](../core/lesson-2-define-the-business-process.md).</span><span class="sxs-lookup"><span data-stu-id="7dfc2-112">Finally you build the project before starting [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md).</span></span> <span data-ttu-id="7dfc2-113">En la Lección 2, creará el proceso empresarial que enruta los mensajes y que evalúa el contenido del mensaje de solicitud de reposición de inventario con respecto a criterios de aprobación.</span><span class="sxs-lookup"><span data-stu-id="7dfc2-113">In Lesson 2, you create the business process that routes the messages and evaluates the contents of the inventory replenishment request message against approval criteria.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7dfc2-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7dfc2-114">In This Section</span></span>  
  
-   [<span data-ttu-id="7dfc2-115">Paso 1: Crear el proyecto EAISchemas</span><span class="sxs-lookup"><span data-stu-id="7dfc2-115">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
  
-   [<span data-ttu-id="7dfc2-116">Paso 2: Crear el esquema de solicitud de inventario</span><span class="sxs-lookup"><span data-stu-id="7dfc2-116">Step 2: Create the Inventory Request Schema</span></span>](../core/step-2-create-the-inventory-request-schema.md)  
  
-   [<span data-ttu-id="7dfc2-117">Paso 3: Crear el esquema de declinación de solicitud</span><span class="sxs-lookup"><span data-stu-id="7dfc2-117">Step 3: Create the Request Decline Schema</span></span>](../core/step-3-create-the-request-decline-schema.md)  
  
-   [<span data-ttu-id="7dfc2-118">Paso 4: Crear el mapa</span><span class="sxs-lookup"><span data-stu-id="7dfc2-118">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)  
  
-   [<span data-ttu-id="7dfc2-119">Paso 5: Generar el proyecto EAISchemas</span><span class="sxs-lookup"><span data-stu-id="7dfc2-119">Step 5: Build the EAISchemas Project</span></span>](../core/step-5-build-the-eaischemas-project.md)  
  
## <a name="see-also"></a><span data-ttu-id="7dfc2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dfc2-120">See Also</span></span>  
 <span data-ttu-id="7dfc2-121">[Antes de empezar el Tutorial](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="7dfc2-121">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="7dfc2-122">[Lección 2: Definir el proceso empresarial](../core/lesson-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="7dfc2-122">[Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="7dfc2-123">Lección 3: Implementar la solución</span><span class="sxs-lookup"><span data-stu-id="7dfc2-123">Lesson 3: Deploy the Solution</span></span>](../core/lesson-3-deploy-the-solution.md)