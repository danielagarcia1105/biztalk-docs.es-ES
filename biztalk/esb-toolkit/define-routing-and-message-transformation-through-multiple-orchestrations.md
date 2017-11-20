---
title: "Definir enrutamiento y transformación a través de varias orquestaciones mediante itinerarios de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63141b83-798e-40d0-908d-6b7649923e69
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c5a87b06700794dca6c4aae9588c3068b98d995
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="defining-routing-and-message-transformation-through-multiple-orchestrations-using-itineraries"></a><span data-ttu-id="77189-102">Definición de enrutamiento y transformación de mensajes a través de varias orquestaciones mediante itinerarios</span><span class="sxs-lookup"><span data-stu-id="77189-102">Defining Routing and Message Transformation Through Multiple Orchestrations Using Itineraries</span></span>
<span data-ttu-id="77189-103">En este caso de uso, un mensaje enviado para su procesamiento contiene un encabezado SOAP itinerario que describe la lista de servicios para ejecutar así como sus requisitos de resolución.</span><span class="sxs-lookup"><span data-stu-id="77189-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="77189-104">El itinerario especifica una o varias orquestaciones de Microsoft BizTalk Server a través del cual el mensaje pasará durante el ciclo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="77189-104">The itinerary specifies one or more Microsoft BizTalk Server orchestrations through which the message will pass during the processing cycle.</span></span> <span data-ttu-id="77189-105">Si lo desea, el itinerario puede contener información de enrutamiento dinámico que se usa para determinar los puntos de conexión o requisitos de transformación para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="77189-105">Optionally, the itinerary can contain dynamic routing information used to determine endpoints or transformation requirements for the message.</span></span> <span data-ttu-id="77189-106">Figura 1 muestra una vista esquemática del proceso.</span><span class="sxs-lookup"><span data-stu-id="77189-106">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="77189-107">![Definir enrutamiento de múltiples orquestaciones](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3-DefiningRoutingMultipleOrchestrations")</span><span class="sxs-lookup"><span data-stu-id="77189-107">![Defining Routing Multiple Orchestrations](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3-DefiningRoutingMultipleOrchestrations")</span></span>  
  
 <span data-ttu-id="77189-108">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="77189-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="77189-109">**Definir la transformación de mensajes y enrutamiento a través de varias orquestaciones mediante itinerarios**</span><span class="sxs-lookup"><span data-stu-id="77189-109">**Defining routing and message transformation through multiple orchestrations using itineraries**</span></span>  
  
 <span data-ttu-id="77189-110">El ejemplo de itinerario en rampa que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="77189-110">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="77189-111">Muestra cómo crear itinerarios que contienen la resolución, el enrutamiento, y las instrucciones de invocación de servicio como una serie de pasos itinerarios que definen cómo el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] y BizTalk Server procesará el mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="77189-111">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and BizTalk Server will process the input message.</span></span> <span data-ttu-id="77189-112">Unidireccional y se incluyen ejemplos de solicitudes y respuestas.</span><span class="sxs-lookup"><span data-stu-id="77189-112">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="77189-113">Para obtener más información, consulte [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span><span class="sxs-lookup"><span data-stu-id="77189-113">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>