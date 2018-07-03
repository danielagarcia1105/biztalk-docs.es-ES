---
title: Información general del enrutamiento y resolución dinámica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab7ea6f4ddd37be8d8c2c6629d2449c2d9df5f81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018770"
---
# <a name="dynamic-resolution-and-routing-overview"></a><span data-ttu-id="5a441-102">Información general del enrutamiento y resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="5a441-102">Dynamic Resolution and Routing Overview</span></span>
<span data-ttu-id="5a441-103">Las clases de solucionador de ESB admiten la resolución de tiempo de ejecución de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5a441-103">The ESB Resolver classes support run-time resolution of the following:</span></span>  

- <span data-ttu-id="5a441-104">Puntos de conexión de entrega de mensajes</span><span class="sxs-lookup"><span data-stu-id="5a441-104">Message delivery endpoints</span></span>  

- <span data-ttu-id="5a441-105">Mapas para transformación</span><span class="sxs-lookup"><span data-stu-id="5a441-105">Maps for transformation</span></span>  

- <span data-ttu-id="5a441-106">Configuración de extremo</span><span class="sxs-lookup"><span data-stu-id="5a441-106">Endpoint configuration</span></span>  

- <span data-ttu-id="5a441-107">Metadatos del servicio personalizado</span><span class="sxs-lookup"><span data-stu-id="5a441-107">Custom service metadata</span></span>  

- <span data-ttu-id="5a441-108">Itinerarios del lado servidor</span><span class="sxs-lookup"><span data-stu-id="5a441-108">Server-side itineraries</span></span>  

  <span data-ttu-id="5a441-109">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] utiliza cadenas de conexión de resolución para tratar de resolución de asignaciones y los puntos de conexión cuando llegan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5a441-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses resolver connection strings to attempt resolution of maps and endpoints when messages arrive.</span></span> <span data-ttu-id="5a441-110">Estas cadenas de conexiones puedan existir en el encabezado SOAP itinerario de mensajes cuando llegan, o se puede establecer en una canalización personalizada mediante uno de los siguientes componentes de canalización: Selector de itinerarios de ESB, distribuidor de ESB o desensamblar distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="5a441-110">These connections strings may exist in the itinerary SOAP header of messages when they arrive, or they may be set in a custom pipeline using one of the following pipeline components: ESB Itinerary Selector, ESB Dispatcher, or ESB Dispatcher Disassemble.</span></span> <span data-ttu-id="5a441-111">La resolución tiene lugar más adelante en el ciclo de vida de procesamiento mediante las funciones de resolución "just-in-time" (JIT) de los componentes de marco de proveedores de adaptador y resolución de ESB.</span><span class="sxs-lookup"><span data-stu-id="5a441-111">Resolution occurs later in the processing life cycle using the "just-in-time" (JIT) resolution capabilities of the ESB Resolver and Adapter Provider Framework components.</span></span>  

  <span data-ttu-id="5a441-112">Por ejemplo, si el agente de la transformación dinámica recibe un mensaje que debe asignar, pero aún no se ha determinado el nombre del mapa, se intentará utilizar al Solucionador asociado para realizar la resolución.</span><span class="sxs-lookup"><span data-stu-id="5a441-112">For example, if the dynamic transformation agent receives a message that it must map, but the map name has not yet been determined, it will attempt to use the associated resolver to perform the resolution.</span></span> <span data-ttu-id="5a441-113">Si se produce un error en la resolución JIT, que se clasifica como un error, el sistema genera un mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="5a441-113">If JIT resolution fails, which is classed as an error, the system generates an exception message.</span></span>  

  <span data-ttu-id="5a441-114">El marco de proveedores de adaptador y la resolución pueden consultar los siguientes almacenes de datos o los mecanismos de resolución:</span><span class="sxs-lookup"><span data-stu-id="5a441-114">The Resolver and Adapter Provider Framework can query the following data stores or resolution mechanisms:</span></span>  

- <span data-ttu-id="5a441-115">Mapas codificados de forma rígida o puntos de conexión, en el que no producen case resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="5a441-115">Hard-coded maps or endpoints, in which case dynamic resolution does not occur</span></span>  

- <span data-ttu-id="5a441-116">Una directiva del motor de reglas de negocios (BRE)</span><span class="sxs-lookup"><span data-stu-id="5a441-116">A Business Rules Engine (BRE) policy</span></span>  

- <span data-ttu-id="5a441-117">Un ensamblado personalizado que implementa el **IResolveProvider** interfaz</span><span class="sxs-lookup"><span data-stu-id="5a441-117">A custom assembly implementing the **IResolveProvider** interface</span></span>  

- <span data-ttu-id="5a441-118">Una consulta XPath en el mensaje</span><span class="sxs-lookup"><span data-stu-id="5a441-118">An XPath query over the message</span></span>  

- <span data-ttu-id="5a441-119">Una búsqueda Universal Description, Discovery and Integration (UDDI)</span><span class="sxs-lookup"><span data-stu-id="5a441-119">A Universal Description, Discovery, and Integration (UDDI) lookup</span></span>
