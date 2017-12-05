---
title: "Implementar el patrón de dispersión y recopilación de varias invocaciones de servicio Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 912512a4-9649-40df-bb82-b8f4b85c8ca6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2682418922c17fd4c6fbe8a6bffbac51051f7841
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="implementing-the-scatter-gather-pattern-for-multiple-web-service-invocations"></a><span data-ttu-id="c43a5-102">Implementar el patrón de dispersión y recopilación de varias invocaciones de servicio Web</span><span class="sxs-lookup"><span data-stu-id="c43a5-102">Implementing the Scatter-Gather Pattern for Multiple Web Service Invocations</span></span>
<span data-ttu-id="c43a5-103">En este caso de uso, un mensaje contiene un paso de servicio itinerarios que especifica más de un servicio externo que debe tener acceso BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c43a5-103">In this use case, a message contains an itinerary service step that specifies more than one external service that BizTalk Server should access.</span></span> <span data-ttu-id="c43a5-104">Resolución dinámica usa para determinar las ubicaciones de servicio y los puntos de conexión y cualquier BizTalk Service opcional que se asigna para transformar los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="c43a5-104">It uses dynamic resolution to determine service locations and endpoints and any optional BizTalk Service maps for transforming the returned data.</span></span> <span data-ttu-id="c43a5-105">La orquestación que implementa este servicio lleva a cabo la transformación y las invocaciones de y todas las invocaciones del servicio se producen de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="c43a5-105">The orchestration implementing this service performs the transformation and invocations, and all service invocations occur asynchronously.</span></span> <span data-ttu-id="c43a5-106">Después de completar todas las invocaciones de servicio, el servicio itinerario agrega las respuestas en un único mensaje de respuesta y envía el mensaje al cliente a través de un punto de conexión asignado dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="c43a5-106">After all service invocations complete, the itinerary service aggregates the responses into a single response message and sends the message to the client through a dynamically assigned endpoint.</span></span> <span data-ttu-id="c43a5-107">La figura 1 muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="c43a5-107">Figure 1 illustrates this use case.</span></span>  
  
 <span data-ttu-id="c43a5-108">![Implementación de dispersión recopilar patrón](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3-ImplementingScatter")</span><span class="sxs-lookup"><span data-stu-id="c43a5-108">![Implementing Scatter Gather Pattern](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3-ImplementingScatter")</span></span>  
  
 <span data-ttu-id="c43a5-109">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="c43a5-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="c43a5-110">**Implementar el patrón de dispersión y recopilación para varias invocaciones de servicio Web**</span><span class="sxs-lookup"><span data-stu-id="c43a5-110">**Implementing the Scatter-Gather pattern for multiple Web service invocations**</span></span>  
  
 <span data-ttu-id="c43a5-111">El ejemplo de dispersión y recopilación que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="c43a5-111">The Scatter-Gather sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span>  
  
 <span data-ttu-id="c43a5-112">Para obtener más información, consulte [instalar y ejecutar el ejemplo de dispersión y recopilación](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).</span><span class="sxs-lookup"><span data-stu-id="c43a5-112">For more information, see [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).</span></span>