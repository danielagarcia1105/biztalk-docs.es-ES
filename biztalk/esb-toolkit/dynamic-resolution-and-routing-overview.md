---
title: "Resolución dinámica e Introducción al enrutamiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 341b8389530ac85fdc459816f5691f3b814fbd56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-resolution-and-routing-overview"></a><span data-ttu-id="9a893-102">Resolución dinámica e Introducción al enrutamiento</span><span class="sxs-lookup"><span data-stu-id="9a893-102">Dynamic Resolution and Routing Overview</span></span>
<span data-ttu-id="9a893-103">Las clases de resolución de ESB admiten la resolución de tiempo de ejecución de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a893-103">The ESB Resolver classes support run-time resolution of the following:</span></span>  
  
-   <span data-ttu-id="9a893-104">Puntos de conexión de entrega de mensajes</span><span class="sxs-lookup"><span data-stu-id="9a893-104">Message delivery endpoints</span></span>  
  
-   <span data-ttu-id="9a893-105">Mapas de transformación</span><span class="sxs-lookup"><span data-stu-id="9a893-105">Maps for transformation</span></span>  
  
-   <span data-ttu-id="9a893-106">Configuración de extremo</span><span class="sxs-lookup"><span data-stu-id="9a893-106">Endpoint configuration</span></span>  
  
-   <span data-ttu-id="9a893-107">Metadatos de servicio personalizado</span><span class="sxs-lookup"><span data-stu-id="9a893-107">Custom service metadata</span></span>  
  
-   <span data-ttu-id="9a893-108">Itinerarios de servidor</span><span class="sxs-lookup"><span data-stu-id="9a893-108">Server-side itineraries</span></span>  
  
 <span data-ttu-id="9a893-109">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] utiliza cadenas de conexión de resolución para tratar de resolución de asignaciones y los puntos de conexión cuando llegan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="9a893-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses resolver connection strings to attempt resolution of maps and endpoints when messages arrive.</span></span> <span data-ttu-id="9a893-110">Estas cadenas de conexiones que existan en el encabezado SOAP itinerario de mensajes cuando llegan, o se puede establecer en una canalización personalizada mediante uno de los siguientes componentes de canalización: Selector de itinerario de ESB, ESB distribuidor o distribuidor de ESB desensamblar.</span><span class="sxs-lookup"><span data-stu-id="9a893-110">These connections strings may exist in the itinerary SOAP header of messages when they arrive, or they may be set in a custom pipeline using one of the following pipeline components: ESB Itinerary Selector, ESB Dispatcher, or ESB Dispatcher Disassemble.</span></span> <span data-ttu-id="9a893-111">Se produce una resolución más adelante en el ciclo de vida de procesamiento mediante las capacidades de resolución de "just-in-time" (JIT) de la resolución de ESB y componentes del marco de proveedores de adaptador.</span><span class="sxs-lookup"><span data-stu-id="9a893-111">Resolution occurs later in the processing life cycle using the "just-in-time" (JIT) resolution capabilities of the ESB Resolver and Adapter Provider Framework components.</span></span>  
  
 <span data-ttu-id="9a893-112">Por ejemplo, si el agente de transformación dinámica recibe un mensaje que debe asignar, pero aún no se ha determinado el nombre de asignación, intentará utilizar al Solucionador asociado para realizar la resolución.</span><span class="sxs-lookup"><span data-stu-id="9a893-112">For example, if the dynamic transformation agent receives a message that it must map, but the map name has not yet been determined, it will attempt to use the associated resolver to perform the resolution.</span></span> <span data-ttu-id="9a893-113">Si se produce un error en la resolución JIT, que se clasifican como un error, el sistema genera un mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="9a893-113">If JIT resolution fails, which is classed as an error, the system generates an exception message.</span></span>  
  
 <span data-ttu-id="9a893-114">La resolución y el marco de proveedores de adaptador pueden consultar los siguientes almacenes de datos o los mecanismos de resolución:</span><span class="sxs-lookup"><span data-stu-id="9a893-114">The Resolver and Adapter Provider Framework can query the following data stores or resolution mechanisms:</span></span>  
  
-   <span data-ttu-id="9a893-115">Mapas codificados de forma rígida o puntos de conexión, en el que no producía mayúscula resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="9a893-115">Hard-coded maps or endpoints, in which case dynamic resolution does not occur</span></span>  
  
-   <span data-ttu-id="9a893-116">Una directiva del motor de reglas de negocios (BRE)</span><span class="sxs-lookup"><span data-stu-id="9a893-116">A Business Rules Engine (BRE) policy</span></span>  
  
-   <span data-ttu-id="9a893-117">Un ensamblado personalizado que implementa la **IResolveProvider** (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a893-117">A custom assembly implementing the **IResolveProvider** interface</span></span>  
  
-   <span data-ttu-id="9a893-118">Una consulta de XPath en el mensaje</span><span class="sxs-lookup"><span data-stu-id="9a893-118">An XPath query over the message</span></span>  
  
-   <span data-ttu-id="9a893-119">Una búsqueda de Universal Description, Discovery e Integration (UDDI)</span><span class="sxs-lookup"><span data-stu-id="9a893-119">A Universal Description, Discovery, and Integration (UDDI) lookup</span></span>