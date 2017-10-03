---
title: "Transformar y enrutar un mensaje a varios puntos de conexión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 544db12c-95fc-4321-b397-ec9e7410e37d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99e30c2d7b095d0b075b98a48f9263abd361b6cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transforming-and-routing-a-message-to-multiple-endpoints"></a><span data-ttu-id="1b181-102">Transformar y enrutar un mensaje a varios puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="1b181-102">Transforming and Routing a Message to Multiple Endpoints</span></span>
<span data-ttu-id="1b181-103">En este caso de uso, ESB realiza una transformación en un mensaje enviado a través del servicio Web de itinerario en rampa.</span><span class="sxs-lookup"><span data-stu-id="1b181-103">In this use case, the ESB performs a transformation on a message submitted through the Itinerary Web service on-ramp.</span></span> <span data-ttu-id="1b181-104">Una búsqueda de resolución dinámica determina el nombre de asignación y transforma el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="1b181-104">A dynamic resolution lookup determines the map name and transforms the inbound message.</span></span> <span data-ttu-id="1b181-105">Además, el itinerario especifica n número de puntos de conexión de destino que el servicio de itinerario resolverá dinámicamente y a la que enrutará el mensaje transformado.</span><span class="sxs-lookup"><span data-stu-id="1b181-105">Additionally, the itinerary specifies n number of target endpoints that the Itinerary service will dynamically resolve and to which it will route the transformed message.</span></span> <span data-ttu-id="1b181-106">Todas las operaciones se producen en la capa de mensajería, como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="1b181-106">All operations occur at the messaging layer, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="1b181-107">![Transformación de múltiples extremos](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3-TransformingMultipleEndpoints")</span><span class="sxs-lookup"><span data-stu-id="1b181-107">![Transforming Multiple Endpoints](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3-TransformingMultipleEndpoints")</span></span>  
  
 <span data-ttu-id="1b181-108">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="1b181-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="1b181-109">**Transformar y enrutar un mensaje a varios puntos de conexión**</span><span class="sxs-lookup"><span data-stu-id="1b181-109">**Transforming and routing a message to multiple endpoints**</span></span>  
  
 <span data-ttu-id="1b181-110">El ejemplo de resolución dinámica que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="1b181-110">The Dynamic Resolution sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="1b181-111">Muestra cómo utilizar componentes de canalización ESB, específicamente el componente de desensamblador de envío de ESB, para resolver la ubicación del extremo dinámicamente, establecer las propiedades de enrutamientos y resolver y ejecutar [!INCLUDE[prague](../includes/prague-md.md)] se asigna en el nivel de mensajería, sin usar un orquestación.</span><span class="sxs-lookup"><span data-stu-id="1b181-111">It shows how to use ESB pipeline components, specifically the ESB Dispatch Disassembler component, to dynamically resolve endpoint location, set routing properties, and resolve and execute [!INCLUDE[prague](../includes/prague-md.md)] maps at the messaging level, without using an orchestration.</span></span> <span data-ttu-id="1b181-112">También muestra los patrones de mensajería unidireccionales y bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="1b181-112">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
 <span data-ttu-id="1b181-113">Para obtener más información, consulte [instalar y ejecutar el ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) y [instalar y ejecutar el ejemplo de servicios Web varios](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span><span class="sxs-lookup"><span data-stu-id="1b181-113">For more information, see [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) and [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>