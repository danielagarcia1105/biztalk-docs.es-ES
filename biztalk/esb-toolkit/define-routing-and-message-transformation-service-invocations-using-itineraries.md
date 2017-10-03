---
title: "Definir enrutamiento y las invocaciones de servicio de transformación con itinerarios de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6f2448e-a5a7-496c-86d3-47f12e6f1251
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 975c830f73e0de362b25f312a8d41c4b15368cfd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="defining-routing-and-message-transformation-service-invocations-using-itineraries"></a><span data-ttu-id="5ebbd-102">Enrutamiento de definición e invocaciones de servicio de transformación de mensaje mediante itinerarios</span><span class="sxs-lookup"><span data-stu-id="5ebbd-102">Defining Routing and Message Transformation Service Invocations Using Itineraries</span></span>
<span data-ttu-id="5ebbd-103">En este caso de uso, un mensaje enviado para su procesamiento contiene un encabezado SOAP itinerario que describe la lista de servicios para ejecutar así como sus requisitos de resolución.</span><span class="sxs-lookup"><span data-stu-id="5ebbd-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="5ebbd-104">En concreto, un servicio de enrutamiento y la transformación se definen, cada uno de ellos opcionalmente que requieren resolución a través de una búsqueda de Universal Description, Discovery y Integration (UDDI), directiva del motor de reglas de negocios, XML Path Language (XPath) o STATIC.</span><span class="sxs-lookup"><span data-stu-id="5ebbd-104">Specifically, a transformation and routing service are defined, each optionally requiring resolution through a Universal Description, Discovery, and Integration (UDDI), Business Rules Engine Policy, XML Path Language (XPath), or STATIC lookup.</span></span> <span data-ttu-id="5ebbd-105">Este caso de uso puede ampliarse mediante la adición de otros servicios para el itinerario en el momento de publicación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="5ebbd-105">This use case can be extended by adding other services to the itinerary at the time of message publication.</span></span>  
  
 <span data-ttu-id="5ebbd-106">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona dos tipos de itinerario en pendientes: aquellos que admiten la comunicación unidireccional y aquellos que admiten escenarios de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="5ebbd-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides two types of itinerary on-ramps: those that support one-way communication and those that support request-response scenarios.</span></span> <span data-ttu-id="5ebbd-107">Dado que el mecanismo de resolución dinámica puede usar información en el itinerario para buscar los puntos de conexión o enlazar dinámicamente a los puntos de conexión, no hay ningún requisito para Microsoft BizTalk Server para que contenga los detalles de ruta de punto de conexión concreto.</span><span class="sxs-lookup"><span data-stu-id="5ebbd-107">Because the dynamic resolution mechanism can use information in the itinerary to look up endpoints or bind dynamically to endpoints, there is no requirement for Microsoft BizTalk Server to contain specific endpoint routing details.</span></span> <span data-ttu-id="5ebbd-108">Figura 1 muestra una vista esquemática del proceso.</span><span class="sxs-lookup"><span data-stu-id="5ebbd-108">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="5ebbd-109">![Definición de invocación de servicio de enrutamiento](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3-DefiningRoutingServiceInvocation")</span><span class="sxs-lookup"><span data-stu-id="5ebbd-109">![Defining Routing service Invocation](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3-DefiningRoutingServiceInvocation")</span></span>  
  
 <span data-ttu-id="5ebbd-110">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="5ebbd-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="5ebbd-111">**Definir mensajes y enrutamiento invocaciones de servicio de transformación con itinerarios**</span><span class="sxs-lookup"><span data-stu-id="5ebbd-111">**Defining routing and message transformation service invocations using itineraries**</span></span>  
  
 <span data-ttu-id="5ebbd-112">El ejemplo de itinerario en rampa que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="5ebbd-112">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="5ebbd-113">Muestra cómo crear itinerarios que contienen la resolución, el enrutamiento, y las instrucciones de invocación de servicio como una serie de pasos itinerarios que definen cómo el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] y BizTalk Server procesará el mensaje mediante la publicación-suscribirse funcionalidad de Servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5ebbd-113">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and BizTalk Server will process the message using the publish-subscribe functionality of BizTalk Server.</span></span> <span data-ttu-id="5ebbd-114">Unidireccional y se incluyen ejemplos de solicitudes y respuestas.</span><span class="sxs-lookup"><span data-stu-id="5ebbd-114">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="5ebbd-115">Para obtener más información, consulte [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5ebbd-115">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>