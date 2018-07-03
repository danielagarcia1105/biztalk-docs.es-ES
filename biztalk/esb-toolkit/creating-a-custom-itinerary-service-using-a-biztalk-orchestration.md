---
title: Creación de un servicio de itinerarios personalizado mediante una orquestación de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd7ed38-02a3-41b1-9990-754d5539f15e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa36acc84358a8e91a0b9daaa4370270fb5860b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988541"
---
# <a name="creating-a-custom-itinerary-service-using-a-biztalk-orchestration"></a><span data-ttu-id="795d0-102">Creación de un servicio de itinerarios personalizado mediante una orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="795d0-102">Creating a Custom Itinerary Service Using a BizTalk Orchestration</span></span>
<span data-ttu-id="795d0-103">El marco de itinerarios que forma parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite la ejecución de pasos de itinerarios mediante orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="795d0-103">The itinerary framework that is part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports execution of itinerary steps using orchestrations.</span></span> <span data-ttu-id="795d0-104">Puede implementar un servicio de itinerarios personalizado como una orquestación de Microsoft BizTalk Server según sus requisitos funcionales, que pueden incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="795d0-104">You can implement a custom itinerary service as a Microsoft BizTalk Server orchestration based on your functional requirements, which may include the following:</span></span>  
  
- <span data-ttu-id="795d0-105">Varias invocaciones de servicio (tal como lo demuestra el [instalar y ejecutar el ejemplo de dispersión y recopilación](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))</span><span class="sxs-lookup"><span data-stu-id="795d0-105">Multiple service invocations (as demonstrated by the [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))</span></span>  
  
- <span data-ttu-id="795d0-106">Correlación de mediación y mensaje de protocolo (por ejemplo, HTTP-MQSeries)</span><span class="sxs-lookup"><span data-stu-id="795d0-106">Protocol mediation and message correlation (for example, HTTP-MQSeries)</span></span>  
  
- <span data-ttu-id="795d0-107">Decisiones de enrutamiento complejas basan en enriquecimiento de mensajes de datos externos de orígenes</span><span class="sxs-lookup"><span data-stu-id="795d0-107">Complex routing decisions based on message enrichment from external data sources</span></span>  
  
- <span data-ttu-id="795d0-108">Lógica de procesamiento empresarial</span><span class="sxs-lookup"><span data-stu-id="795d0-108">Business processing logic</span></span>  
  
  <span data-ttu-id="795d0-109">Cada servicio de itinerarios implementado mediante una orquestación de BizTalk Server es responsable de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="795d0-109">Every itinerary service implemented using a BizTalk Server orchestration is responsible for the following:</span></span>  
  
- <span data-ttu-id="795d0-110">Errores y excepciones con el marco de control de excepciones de ESB o controladores de excepción personalizada opcional que admiten el reenvío (itinerarios unidireccionales)</span><span class="sxs-lookup"><span data-stu-id="795d0-110">Exception and error handling using the ESB Exception Handling Framework or optional custom exception handlers that support resubmission (one-way itineraries)</span></span>  
  
- <span data-ttu-id="795d0-111">Avanzar el itinerario y la publicación de mensajes salientes a través de BizTalk Server para que puedan ejecutar el siguiente paso de servicio de itinerarios</span><span class="sxs-lookup"><span data-stu-id="795d0-111">Advancing the itinerary and publishing outbound messages through BizTalk Server so that the next itinerary service step can execute</span></span>  
  
#### <a name="to-create-a-custom-itinerary-service-using-a-biztalk-server-orchestration"></a><span data-ttu-id="795d0-112">Para crear un servicio de itinerarios personalizado mediante una orquestación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="795d0-112">To create a custom itinerary service using a BizTalk Server orchestration</span></span>  
  
1. <span data-ttu-id="795d0-113">Crear nuevo proyecto de BizTalk Server que contiene una nueva orquestación; Por ejemplo, MyCustomeItineraryService.odx.</span><span class="sxs-lookup"><span data-stu-id="795d0-113">Create new BizTalk Server project containing a new orchestration; for example, MyCustomeItineraryService.odx.</span></span>  
  
2. <span data-ttu-id="795d0-114">Agregue referencias a los ensamblados siguientes:</span><span class="sxs-lookup"><span data-stu-id="795d0-114">Add references to the following assemblies:</span></span>  
  
   -   <span data-ttu-id="795d0-115">**Microsoft.Practices.ESB.Itinerary**</span><span class="sxs-lookup"><span data-stu-id="795d0-115">**Microsoft.Practices.ESB.Itinerary**</span></span>  
  
   -   <span data-ttu-id="795d0-116">**Microsoft.Practices.ESB.Itinerary.Schemas**</span><span class="sxs-lookup"><span data-stu-id="795d0-116">**Microsoft.Practices.ESB.Itinerary.Schemas**</span></span>  
  
   -   <span data-ttu-id="795d0-117">**Microsoft.Practices.ESB.ExceptionHandling**</span><span class="sxs-lookup"><span data-stu-id="795d0-117">**Microsoft.Practices.ESB.ExceptionHandling**</span></span>  
  
   -   <span data-ttu-id="795d0-118">**Microsoft.Practices.ESB.ExceptionHandling.Faults**</span><span class="sxs-lookup"><span data-stu-id="795d0-118">**Microsoft.Practices.ESB.ExceptionHandling.Faults**</span></span>  
  
3. <span data-ttu-id="795d0-119">Definir un enlace directo lógico puerto de recepción y una forma recepción activada en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="795d0-119">Define a logical direct-bound receive port and an activated receive shape in the orchestration.</span></span>  
  
4. <span data-ttu-id="795d0-120">Definir un filtro de suscripción para activar la orquestación desde el contexto del mensaje itinerarios para que la orquestación ejecuta la **MyCustomItineraryService** paso.</span><span class="sxs-lookup"><span data-stu-id="795d0-120">Define a subscription filter to activate the orchestration from the message itinerary context so that the orchestration executes the **MyCustomItineraryService** step.</span></span> <span data-ttu-id="795d0-121">El código siguiente muestra un ejemplo de un filtro adecuado.</span><span class="sxs-lookup"><span data-stu-id="795d0-121">The following code shows an example of a suitable filter.</span></span>  
  
   ```csharp  
   (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName   
       == "MyCustomItineraryService")   
   && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
   && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
       == "Orchestration")  
   ```  
  
5. <span data-ttu-id="795d0-122">Definir una orquestación de tipo **Microsoft.Practices.ESB.Itinerary.ItineraryStep**.</span><span class="sxs-lookup"><span data-stu-id="795d0-122">Define an orchestration of type **Microsoft.Practices.ESB.Itinerary.ItineraryStep**.</span></span> <span data-ttu-id="795d0-123">Agregue una actividad de expresión a la orquestación que rellena esta variable, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="795d0-123">Add an expression activity to the orchestration that populates this variable, as shown in the following code.</span></span>  
  
   ```csharp  
   // Retrieve the current itinerary step.  
   itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
   step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
   itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
   step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  
   ```  
  
6. <span data-ttu-id="795d0-124">Agregue su implementación personalizada para el itinerario que crea el mensaje de salida para los siguientes pasos itinerarios; Por ejemplo, OutboundMsg.</span><span class="sxs-lookup"><span data-stu-id="795d0-124">Add your custom implementation to the itinerary that creates the outbound message for the next itinerary steps; for example, OutboundMsg.</span></span>  
  
7. <span data-ttu-id="795d0-125">Pase el itinerario mediante la siguiente actividad de expresión que usa el contexto del mensaje del mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="795d0-125">Advance the itinerary using the following expression activity that uses the message context from inbound message.</span></span>  
  
   ```csharp  
   OutboundMessage(*) = InboundMessage(*);   
   itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
   ```  
  
8. <span data-ttu-id="795d0-126">Enviar el mensaje saliente con el itinerario actualizado a través de un puerto de envío de enlace directo para activar el servicio de itinerarios siguiente.</span><span class="sxs-lookup"><span data-stu-id="795d0-126">Send the outbound message with the updated itinerary through a direct-bound send port to activate the next itinerary service.</span></span>  
  
   <span data-ttu-id="795d0-127">Para obtener más información acerca de cómo implementar un servicio de itinerarios personalizado mediante las orquestaciones de BizTalk Server, consulte [instalar y ejecutar el ejemplo de rampa de itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) y [instalar y ejecutar la dispersión y recopilación Ejemplo](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).</span><span class="sxs-lookup"><span data-stu-id="795d0-127">For more information about implementing a custom itinerary service using BizTalk Server orchestrations, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) and [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).</span></span>