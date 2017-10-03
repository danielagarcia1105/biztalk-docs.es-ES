---
title: "Utilizar una orquestación como un suscriptor de servicio itinerarios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 278564f1-de9f-4fbf-8c7f-09b3e607c28b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f496884d0aed8d5f351f681ca8cfe59e05684240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a><span data-ttu-id="15be0-102">Utilizar una orquestación como un suscriptor de servicio itinerarios</span><span class="sxs-lookup"><span data-stu-id="15be0-102">Using an Orchestration as an Itinerary Service Subscriber</span></span>
<span data-ttu-id="15be0-103">Las orquestaciones también pueden actuar como servicios itinerarios.</span><span class="sxs-lookup"><span data-stu-id="15be0-103">Orchestrations can also act as itinerary services.</span></span> <span data-ttu-id="15be0-104">Para participar en un itinerario, primero debe diseñar la orquestación como enlace directo; Para ello, utilice una suscripción de filtro similar a la que el puerto de envío en el tema anterior, [mediante un puerto de envío como un suscriptor de servicio de itinerario](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="15be0-104">To participate in an itinerary, you must first design the orchestration as direct-bound; to do this, use a filter subscription similar to that of the send port in the previous topic, [Using a Send Port as an Itinerary Service Subscriber](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md).</span></span> <span data-ttu-id="15be0-105">La figura 1 muestra un ejemplo de una expresión de filtro para una orquestación adecuada recoger los mensajes que cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="15be0-105">Figure 1 shows an example of a filter expression for a suitable orchestration to pick up any message that meets the following conditions:</span></span>  
  
-   <span data-ttu-id="15be0-106">**ServiceName = Microsoft.Practices.ESB.Services.Transform**</span><span class="sxs-lookup"><span data-stu-id="15be0-106">**ServiceName = Microsoft.Practices.ESB.Services.Transform**</span></span>  
  
-   <span data-ttu-id="15be0-107">**ServiceState = pendiente**</span><span class="sxs-lookup"><span data-stu-id="15be0-107">**ServiceState = Pending**</span></span>  
  
-   <span data-ttu-id="15be0-108">**ServiceType = orquestación**</span><span class="sxs-lookup"><span data-stu-id="15be0-108">**ServiceType = Orchestration**</span></span>  
  
 <span data-ttu-id="15be0-109">![Orquestación](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span><span class="sxs-lookup"><span data-stu-id="15be0-109">![Orchestration](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span></span>  
  
 <span data-ttu-id="15be0-110">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="15be0-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="15be0-111">**Expresión de filtro de ejemplo para una orquestación que vaya a participar en un itinerario como suscriptor**</span><span class="sxs-lookup"><span data-stu-id="15be0-111">**Example filter expression for an orchestration that will participate in an itinerary as a subscriber**</span></span>  
  
 <span data-ttu-id="15be0-112">Cuando llegan los mensajes de Microsoft BizTalk Server a través de ESB en rampa, el paso de validación en la canalización ESB escribe los valores de propiedad para las propiedades del filtro en las propiedades de contexto de BizTalk del mensaje entrante; Esto promueve al contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="15be0-112">When messages arrive in Microsoft BizTalk Server through an ESB on-ramp, the validation step in the ESB pipeline writes the property values for the filter properties into the BizTalk context properties of the incoming message; this promotes them to the message context.</span></span> <span data-ttu-id="15be0-113">El servicio itinerario siempre establece la **ServiceName** propiedad para el servicio activo actualmente en el nombre del servicio para procesar a continuación y con un **ServiceState** el valor de propiedad  **Pendiente**.</span><span class="sxs-lookup"><span data-stu-id="15be0-113">The itinerary service always sets the **ServiceName** property for the currently active service to the name of the service to process next, and with a **ServiceState** property value of **Pending**.</span></span> <span data-ttu-id="15be0-114">Para una suscripción, debe establecer al menos los primeros tres de las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="15be0-114">For a subscription, you must set at least the first three of the following properties:</span></span>  
  
-   <span data-ttu-id="15be0-115">**ServiceName.**</span><span class="sxs-lookup"><span data-stu-id="15be0-115">**ServiceName.**</span></span> <span data-ttu-id="15be0-116">Este es el nombre del servicio, tal como se almacena en el itinerario ESB y puede ser cualquier nombre.</span><span class="sxs-lookup"><span data-stu-id="15be0-116">This is the name of the service, as stored in the ESB itinerary, and can be any name.</span></span> <span data-ttu-id="15be0-117">El itinerario utiliza este nombre para identificar qué servicio para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="15be0-117">The itinerary uses this name to identify which service to execute.</span></span>  
  
-   <span data-ttu-id="15be0-118">**ServiceState.**</span><span class="sxs-lookup"><span data-stu-id="15be0-118">**ServiceState.**</span></span> <span data-ttu-id="15be0-119">Este es el estado del paso actual servicio itinerarios para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="15be0-119">This is the state of the current itinerary service step to execute.</span></span> <span data-ttu-id="15be0-120">El paso de servicio actual (para procesar a continuación) siempre tendrá el valor **pendiente**, establecer cualquier ESB itinerarios componente de canalización, el componente de canalización de Selector de itinerario de ESB, o el código que llama el **por adelantado**  método de la API de itinerario.</span><span class="sxs-lookup"><span data-stu-id="15be0-120">The current service step (for processing next) will always have the value **Pending**, set by either the ESB itinerary pipeline component, the ESB Itinerary Selector pipeline component, or code that calls the **Advance** method of the itinerary API.</span></span>  
  
-   <span data-ttu-id="15be0-121">**ServiceType.**</span><span class="sxs-lookup"><span data-stu-id="15be0-121">**ServiceType.**</span></span> <span data-ttu-id="15be0-122">Esta propiedad define el tipo de servicio, que indica si se origina desde la orquestación o el subsistema de mensajería de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="15be0-122">This property defines the type of service, indicating whether it originates from the orchestration or the messaging subsystem in BizTalk.</span></span>  
  
-   <span data-ttu-id="15be0-123">**IsRequestResponse.**</span><span class="sxs-lookup"><span data-stu-id="15be0-123">**IsRequestResponse.**</span></span> <span data-ttu-id="15be0-124">Esta propiedad opcional debe tener el mismo valor que el **IsRequestResponse** propiedad del servicio.</span><span class="sxs-lookup"><span data-stu-id="15be0-124">This optional property must have the same value as the **IsRequestResponse** property of the service.</span></span>