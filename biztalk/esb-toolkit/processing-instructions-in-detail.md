---
title: Instrucciones de procesamiento en detalle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed5d92fb-d53b-49a2-b2c7-8558708d6554
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d867737599369ad8ff07780080b16f5ce0f6f2fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005581"
---
# <a name="processing-instructions-in-detail"></a><span data-ttu-id="4a425-102">Instrucciones de procesamiento en detalle</span><span class="sxs-lookup"><span data-stu-id="4a425-102">Processing Instructions in Detail</span></span>
<span data-ttu-id="4a425-103">Este tema describe el formato y la estructura del esquema de propiedad del sistema-Properties.xsd, que define varias propiedades de contexto necesarias para el procesamiento de itinerarios.</span><span class="sxs-lookup"><span data-stu-id="4a425-103">This topic describes the format and structure of the System-Properties.xsd property schema, which defines several context properties required for itinerary processing.</span></span> <span data-ttu-id="4a425-104">Estas propiedades se promocionan cuando se recibe un mensaje y se procesan a través de canalizaciones de BizTalk Server; Dado que son propiedades promocionadas, son accesibles para los componentes de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4a425-104">These properties are promoted when a message is received and processed through BizTalk Server pipelines; because they are promoted properties, they are accessible to BizTalk Server components.</span></span> <span data-ttu-id="4a425-105">Las siguientes propiedades se definen en el esquema de propiedades del sistema-Properties.xsd:</span><span class="sxs-lookup"><span data-stu-id="4a425-105">The following properties are defined in the System-Properties.xsd property schema:</span></span>  
  
- <span data-ttu-id="4a425-106">**ItineraryHeader.**</span><span class="sxs-lookup"><span data-stu-id="4a425-106">**ItineraryHeader.**</span></span> <span data-ttu-id="4a425-107">Esta propiedad contiene toda la información de itinerarios y una lista de servicios de itinerario para invocar a través de una secuencia de pasos de itinerarios.</span><span class="sxs-lookup"><span data-stu-id="4a425-107">This property contains all the itinerary information and a list of itinerary services to be invoked through a sequence of itinerary steps.</span></span> <span data-ttu-id="4a425-108">La API de itinerario utiliza internamente esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="4a425-108">The Itinerary API uses this property internally.</span></span>  
  
- <span data-ttu-id="4a425-109">**ServiceName.**</span><span class="sxs-lookup"><span data-stu-id="4a425-109">**ServiceName.**</span></span> <span data-ttu-id="4a425-110">Esta propiedad contiene el nombre del servicio de itinerarios actual para procesar.</span><span class="sxs-lookup"><span data-stu-id="4a425-110">This property contains the name of the current itinerary service to process.</span></span>  
  
- <span data-ttu-id="4a425-111">**ServiceState.**</span><span class="sxs-lookup"><span data-stu-id="4a425-111">**ServiceState.**</span></span> <span data-ttu-id="4a425-112">Esta propiedad contiene el estado del servicio de itinerarios actual: **pendiente**, **completar**, o **Active**.</span><span class="sxs-lookup"><span data-stu-id="4a425-112">This property contains the state of the current itinerary service: **Pending**, **Complete**, or **Active**.</span></span> <span data-ttu-id="4a425-113">Todos los servicios de suscripción a un paso del itinerario que contiene un **ServiceState** valor **pendiente**.</span><span class="sxs-lookup"><span data-stu-id="4a425-113">All services subscribe to an itinerary step that contains a **ServiceState** value of **Pending**.</span></span>  
  
- <span data-ttu-id="4a425-114">**ServiceType.**</span><span class="sxs-lookup"><span data-stu-id="4a425-114">**ServiceType.**</span></span> <span data-ttu-id="4a425-115">Esta propiedad define el tipo del paso del itinerario (**mensajería** o **orquestación**).</span><span class="sxs-lookup"><span data-stu-id="4a425-115">This property defines the type of the itinerary step (**Messaging** or **Orchestration**).</span></span>  
  
- <span data-ttu-id="4a425-116">**IsRequestResponse.**</span><span class="sxs-lookup"><span data-stu-id="4a425-116">**IsRequestResponse.**</span></span> <span data-ttu-id="4a425-117">Esta propiedad define el tipo de mensajería (unidireccional o de solicitud-respuesta).</span><span class="sxs-lookup"><span data-stu-id="4a425-117">This property defines the messaging type (one-way or request-response).</span></span>  
  
  <span data-ttu-id="4a425-118">El servicio de itinerarios ejecuta pasos itinerarios en uno de dos maneras, dependiendo del valor de la **ServiceType** propiedad:</span><span class="sxs-lookup"><span data-stu-id="4a425-118">The Itinerary service executes itinerary steps in one of two ways, depending on the value of the **ServiceType** property:</span></span>  
  
- <span data-ttu-id="4a425-119">Los componentes de canalización itinerarios ejecutan todos los pasos de itinerarios con un **ServiceType** propiedad de **mensajería**.</span><span class="sxs-lookup"><span data-stu-id="4a425-119">Itinerary pipeline components execute all itinerary steps with a **ServiceType** property of **Messaging**.</span></span> <span data-ttu-id="4a425-120">Los desarrolladores pueden ampliar este proceso mediante una canalización personalizada y la API de itinerario.</span><span class="sxs-lookup"><span data-stu-id="4a425-120">Developers can extend this process using a custom pipeline and the Itinerary API.</span></span>  
  
- <span data-ttu-id="4a425-121">Cuando el **ServiceType** propiedad es **orquestación**, una orquestación, activada por una suscripción a las propiedades de contexto de itinerarios, ejecuta el paso del itinerario.</span><span class="sxs-lookup"><span data-stu-id="4a425-121">When the **ServiceType** property is **Orchestration**, an orchestration, activated by a subscription to itinerary context properties, executes the itinerary step.</span></span>  
  
  <span data-ttu-id="4a425-122">Cuando un servicio de itinerarios procesa un paso del itinerario, el servicio es responsable de avanzar el itinerario y enviar el mensaje con un nuevo contexto de itinerarios para un posterior procesamiento mediante la publicación-suscribirse funcionalidad de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4a425-122">When an Itinerary service processes an itinerary step, the service is responsible for advancing the itinerary and dispatching the message with a new itinerary context for further processing using the publish-subscribe functionality of BizTalk Server.</span></span> <span data-ttu-id="4a425-123">Un servicio de itinerarios tiene control total sobre el itinerario en el contexto del mensaje y se puede avanzar al paso adecuado según su lógica interna y el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4a425-123">An itinerary service has full control of the itinerary in the message context and can advance to the appropriate step based on its internal logic and the message content.</span></span>  
  
  <span data-ttu-id="4a425-124">El mecanismo de procesamiento de itinerarios admite la combinación de pasos de itinerarios de mensajería y orquestación dentro de un único itinerario.</span><span class="sxs-lookup"><span data-stu-id="4a425-124">The itinerary processing mechanism supports the combination of messaging and orchestration itinerary steps within a single itinerary.</span></span> <span data-ttu-id="4a425-125">Los desarrolladores también pueden definir servicios de itinerarios personalizados y configurar pasos de itinerarios personalizados.</span><span class="sxs-lookup"><span data-stu-id="4a425-125">Developers can also define custom itinerary services and configure custom itinerary steps.</span></span>  
  
  <span data-ttu-id="4a425-126">Para obtener más información acerca de los itinerarios, consulte [instalar y ejecutar el ejemplo de rampa de itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span><span class="sxs-lookup"><span data-stu-id="4a425-126">For more information about itineraries, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>  
  
  <span data-ttu-id="4a425-127">Para obtener más información sobre los servicios de itinerarios personalizados y pasos de itinerarios personalizados, consulte [creación de un servicio de itinerarios personalizado](../esb-toolkit/creating-a-custom-itinerary-service.md).</span><span class="sxs-lookup"><span data-stu-id="4a425-127">For more information about custom itinerary services and custom itinerary steps, see [Creating a Custom Itinerary Service](../esb-toolkit/creating-a-custom-itinerary-service.md).</span></span>