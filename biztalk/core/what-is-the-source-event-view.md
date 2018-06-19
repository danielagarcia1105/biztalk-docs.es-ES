---
title: ¿Qué es la vista Origen de eventos? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, Source Event view
- Source Event view [Tracking Profile Editor]
- message schemas, Tracking Profile Editor
- orchestrations, Tracking Profile Editor
- Tracking Profile Editor, message schemas
- Tracking Profile Editor, orchestrations
ms.assetid: 72e74780-8590-484b-899d-cdc3d2a908be
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2437d2effe2fa03078e7f92fdb06f378c9e7cac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289484"
---
# <a name="what-is-the-source-event-view"></a><span data-ttu-id="a1f68-103">¿Qué es la vista Origen de eventos?</span><span class="sxs-lookup"><span data-stu-id="a1f68-103">What Is the Source Event View?</span></span>
<span data-ttu-id="a1f68-104">La vista Origen de eventos es donde el Editor de perfiles de seguimiento (TPE) presenta las orquestaciones o los esquemas de mensajes seleccionados de los ensamblados o de las propiedades de contexto que se asignan a la definición de actividad.</span><span class="sxs-lookup"><span data-stu-id="a1f68-104">The Event Source View is where the Tracking Profile Editor (TPE) presents the orchestrations or message schemas selected from the assemblies or the context properties which you map to the activity definition.</span></span>  
  
 <span data-ttu-id="a1f68-105">La vista Origen de eventos se presenta en el panel derecho de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a1f68-105">The Source Event View is presented in the right pane of user interface.</span></span> <span data-ttu-id="a1f68-106">Los contenidos del panel varían en función del origen de datos que se seleccione.</span><span class="sxs-lookup"><span data-stu-id="a1f68-106">The contents of the pane vary based on the data source you selected.</span></span>  
  
## <a name="event-source-options"></a><span data-ttu-id="a1f68-107">Opciones de Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a1f68-107">Event source options</span></span>  
 <span data-ttu-id="a1f68-108">Dispone de cuatro opciones para orígenes de eventos: programaciones de orquestaciones, cargas de mensajería, propiedades de contexto y propiedades de mensajería.</span><span class="sxs-lookup"><span data-stu-id="a1f68-108">You have four options for event sources: orchestration schedules, messaging payloads, context properties, and messaging properties.</span></span>  
  
 <span data-ttu-id="a1f68-109">Las orquestaciones y cargas de mensajería requieren que seleccione un ensamblado desde el que se van a asignar sus elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="a1f68-109">Orchestrations and messaging payloads require that you select an assembly from which to map your data items.</span></span> <span data-ttu-id="a1f68-110">A continuación, se seleccionan las orquestaciones específicas o los esquemas de carga de mensajes de interés desde el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a1f68-110">You then select the specific orchestrations or message payload schemas of interest from the assembly.</span></span> <span data-ttu-id="a1f68-111">Para programaciones de orquestación, se proporciona una lista de las orquestaciones en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a1f68-111">For orchestration schedules you are given a list of the orchestrations in the assembly.</span></span> <span data-ttu-id="a1f68-112">Las cargas de mensajería permiten seleccionar una lista de los esquemas de carga de mensajería, mientras que las propiedades de contexto presentan una lista de esquemas del ensamblado y de esquemas de sistema que están disponibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="a1f68-112">Messaging payloads allow you to select from a list of messaging payload schemas, and context properties present a list of schemas in the assembly and in system schemas that are publicly available.</span></span>  
  
 <span data-ttu-id="a1f68-113">Al seleccionar propiedades de contexto, primero se proporciona una lista de nombres de propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="a1f68-113">When you select context properties, you are first given a list of context property names.</span></span> <span data-ttu-id="a1f68-114">Cuando selecciona la propiedad de contexto, el esquema relacionado de la propiedad de contexto se muestra en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="a1f68-114">When you select the context property, the related schema of the context property is shown in the right pane.</span></span> <span data-ttu-id="a1f68-115">A continuación, puede asignar la propiedad de contexto a su actividad si arrastra y coloca la propiedad en un nodo de actividad.</span><span class="sxs-lookup"><span data-stu-id="a1f68-115">You can then map the context property to your activity by dragging and dropping the property onto an activity node.</span></span>  
  
 <span data-ttu-id="a1f68-116">Al seleccionar propiedades de mensajería, se proporciona una lista de las propiedades de mensajería conocidas que se pueden asignar a la actividad.</span><span class="sxs-lookup"><span data-stu-id="a1f68-116">When you select messaging properties you are given a list of the known messaging properties that you can then map to the activity.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1f68-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a1f68-117">In This Section</span></span>  
  
-   [<span data-ttu-id="a1f68-118">Vista de programación de orquestación</span><span class="sxs-lookup"><span data-stu-id="a1f68-118">Orchestration Schedule View</span></span>](../core/orchestration-schedule-view.md)  
  
-   [<span data-ttu-id="a1f68-119">Vista carga de mensajería</span><span class="sxs-lookup"><span data-stu-id="a1f68-119">Messaging Payload View</span></span>](../core/messaging-payload-view.md)  
  
-   [<span data-ttu-id="a1f68-120">Vista propiedad de contexto</span><span class="sxs-lookup"><span data-stu-id="a1f68-120">Context Property View</span></span>](../core/context-property-view.md)  
  
-   [<span data-ttu-id="a1f68-121">Vista propiedad de mensajería</span><span class="sxs-lookup"><span data-stu-id="a1f68-121">Messaging Property View</span></span>](../core/messaging-property-view.md)