---
title: Mediante el enrutamiento basado en itinerario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d5b5d13-cbf2-4f3c-8a1a-3bb852f048a0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0e0dad0f49e07c0941614dd0130d0e77c459ab
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848988"
---
# <a name="using-itinerary-based-routing"></a><span data-ttu-id="e8798-102">Usar el enrutamiento basado en itinerario</span><span class="sxs-lookup"><span data-stu-id="e8798-102">Using Itinerary-Based Routing</span></span>
<span data-ttu-id="e8798-103">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona el enrutamiento de mensajes basado en itinerario al implementar el patrón de lista de distribución para habilitar escenarios cuando la secuencia de procesamiento de los pasos para un mensaje determinado no se conoce en tiempo de diseño y puede variar para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="e8798-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides itinerary-based message routing by implementing the Routing Slip pattern to enable scenarios when the sequence of processing steps for a particular message is not known at design time and may vary for each message.</span></span> <span data-ttu-id="e8798-104">La implementación de este patrón utiliza una lista de distribución para representar una colección de estos pasos en formato XML y determina los pasos que se necesitan para que se produzca durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e8798-104">The implementation of this pattern uses a routing slip to represent a collection of these steps in XML format and determines which steps need to occur during at run time.</span></span> <span data-ttu-id="e8798-105">Un estado de la lista de distribución, con frecuencia se denomina "itinerario ESB", es un conjunto ordenado de instrucciones declarativas que definen los pasos que se deben ejecutar para un mensaje, tal y como está siendo procesado por [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes y el tiempo de ejecución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e8798-105">A state of the routing slip, frequently referred to as an "ESB itinerary," is an ordered set of declarative instructions that define the steps that must be executed for a message as it is being processed by [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] components and the BizTalk Server runtime.</span></span> <span data-ttu-id="e8798-106">Una instrucción de procesamiento determinado especificada en itinerario ESB está asociada con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componente, que también se conoce como el "servicio itinerario ESB".</span><span class="sxs-lookup"><span data-stu-id="e8798-106">A particular processing instruction specified in ESB itinerary is associated with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] component, which is also referred to as the "ESB itinerary service."</span></span> <span data-ttu-id="e8798-107">El propósito del servicio itinerario de ESB es que se va a ejecutar las instrucciones de procesamiento como actualizar el estado de la lista de distribución para indicar la próxima pendiente de instrucción.</span><span class="sxs-lookup"><span data-stu-id="e8798-107">The purpose of the ESB itinerary service is to execute the processing instructions and to update the state of the routing slip to indicate the next pending instruction.</span></span>  
  
 <span data-ttu-id="e8798-108">Esta sección describen las características de procesamiento basado en itinerario de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8798-108">This section describes the itinerary-based processing features of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="e8798-109">Incluye los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8798-109">It contains the following topics:</span></span>  
  
-   [<span data-ttu-id="e8798-110">Administración de itinerarios de ESB</span><span class="sxs-lookup"><span data-stu-id="e8798-110">ESB Itinerary Management</span></span>](../esb-toolkit/esb-itinerary-management.md)  
  
-   [<span data-ttu-id="e8798-111">Con rampas y sin rampas</span><span class="sxs-lookup"><span data-stu-id="e8798-111">On-Ramps and Off-Ramps</span></span>](../esb-toolkit/on-ramps-and-off-ramps.md)  
  
-   [<span data-ttu-id="e8798-112">Elegir entre mensajería y servicios de itinerario de orquestación</span><span class="sxs-lookup"><span data-stu-id="e8798-112">Choosing Between Messaging and Orchestration Itinerary Services</span></span>](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  
  
-   [<span data-ttu-id="e8798-113">Uso de un componente de canalización para seleccionar un itinerario existente</span><span class="sxs-lookup"><span data-stu-id="e8798-113">Using a Pipeline Component to Select an Existing Itinerary</span></span>](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  
  
-   [<span data-ttu-id="e8798-114">Uso de un componente de canalización para leer un itinerario</span><span class="sxs-lookup"><span data-stu-id="e8798-114">Using a Pipeline Component to Read an Itinerary</span></span>](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  
  
-   [<span data-ttu-id="e8798-115">Uso de un componente de canalización para almacenar en caché un itinerario para petición-respuesta</span><span class="sxs-lookup"><span data-stu-id="e8798-115">Using a Pipeline Component to Cache an Itinerary for Solicit-Response</span></span>](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  
  
-   [<span data-ttu-id="e8798-116">Crear suscriptores de itinerarios</span><span class="sxs-lookup"><span data-stu-id="e8798-116">Creating Itinerary Subscribers</span></span>](../esb-toolkit/creating-itinerary-subscribers.md)  
  
-   [<span data-ttu-id="e8798-117">Ejecución de un servicio de itinerarios</span><span class="sxs-lookup"><span data-stu-id="e8798-117">Executing an Itinerary Service</span></span>](../esb-toolkit/executing-an-itinerary-service.md)  
  
-   <span data-ttu-id="e8798-118">HYPERLINK "http://msdn.microsoft.com/library/ee236752(BTS.10).aspx" [artefactos de enrutamientos basados en itinerario](../esb-toolkit/itinerary-based-routing-artifacts.md)</span><span class="sxs-lookup"><span data-stu-id="e8798-118">HYPERLINK "http://msdn.microsoft.com/library/ee236752(BTS.10).aspx" [Itinerary-Based Routing Artifacts](../esb-toolkit/itinerary-based-routing-artifacts.md)</span></span>