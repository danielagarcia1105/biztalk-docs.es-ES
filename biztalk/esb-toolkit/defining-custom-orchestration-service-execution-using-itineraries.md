---
title: Definir orquestación personalizada de ejecución de servicio mediante itinerarios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6089169d-2fa1-4f81-afe1-db9d90a10382
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9336969db2c90168bf7c398276205043b06504ce
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007437"
---
# <a name="defining-custom-orchestration-service-execution-using-itineraries"></a><span data-ttu-id="b67d1-102">Definir orquestación personalizada de ejecución de servicio mediante itinerarios</span><span class="sxs-lookup"><span data-stu-id="b67d1-102">Defining Custom Orchestration Service Execution Using Itineraries</span></span>
<span data-ttu-id="b67d1-103">En este caso de uso, un mensaje enviado para su procesamiento contiene un encabezado SOAP itinerario que describe la lista de servicios para ejecutar así como sus requisitos de resolución.</span><span class="sxs-lookup"><span data-stu-id="b67d1-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="b67d1-104">El itinerario especifica uno o más orquestaciones personalizadas o procesos a través del cual el mensaje pasará durante el ciclo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="b67d1-104">The itinerary specifies one or more custom orchestrations or processes through which the message will pass during the processing cycle.</span></span> <span data-ttu-id="b67d1-105">Orquestaciones personalizadas tienen control total sobre el itinerario y otras propiedades personalizadas expuestas en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b67d1-105">Custom orchestrations have full control of the itinerary and other custom properties exposed in the message context.</span></span> <span data-ttu-id="b67d1-106">Si lo desea, el itinerario puede contener información de resolución dinámica que determina los requisitos de transformación y los puntos de conexión para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b67d1-106">Optionally, the itinerary can contain dynamic resolution information that determines transformation requirements and endpoints for the message.</span></span> <span data-ttu-id="b67d1-107">Figura 1 muestra una vista esquemática del proceso.</span><span class="sxs-lookup"><span data-stu-id="b67d1-107">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="b67d1-108">![Definir orquestación personalizada](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3-DefiningCustomOrchestration")</span><span class="sxs-lookup"><span data-stu-id="b67d1-108">![Defining Custom Orchestration](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3-DefiningCustomOrchestration")</span></span>  
  
 <span data-ttu-id="b67d1-109">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="b67d1-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="b67d1-110">**Definir la ejecución del servicio de orquestación personalizada mediante itinerarios**</span><span class="sxs-lookup"><span data-stu-id="b67d1-110">**Defining custom orchestration service execution using itineraries**</span></span>  
  
 <span data-ttu-id="b67d1-111">El ejemplo de itinerario en rampa que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="b67d1-111">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="b67d1-112">Muestra cómo crear itinerarios que contienen la resolución, enrutamiento y las instrucciones de invocación de servicio como una serie de pasos itinerarios que definen cómo el ESB y BizTalk Server procesará el mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="b67d1-112">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the ESB and BizTalk Server will process the input message.</span></span> <span data-ttu-id="b67d1-113">Unidireccional y se incluyen ejemplos de solicitudes y respuestas.</span><span class="sxs-lookup"><span data-stu-id="b67d1-113">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="b67d1-114">Para obtener más información, consulte [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b67d1-114">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>