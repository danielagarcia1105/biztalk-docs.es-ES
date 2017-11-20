---
title: "Patrones de mediación de servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfda54db-75fa-4bc2-9f48-11d8b3cde65b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af76e6c123a3a273bc2e100b1008f40523762695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="service-mediation-patterns"></a><span data-ttu-id="f08be-102">Patrones de mediación de servicio</span><span class="sxs-lookup"><span data-stu-id="f08be-102">Service Mediation Patterns</span></span>
## <a name="vetovetro"></a><span data-ttu-id="f08be-103">UN VETO/VETRO</span><span class="sxs-lookup"><span data-stu-id="f08be-103">VETO/VETRO</span></span>  
 <span data-ttu-id="f08be-104">El patrón VETRO es un patrón compuesto común que combina varias acciones realizadas en un mensaje cuando se recibe.</span><span class="sxs-lookup"><span data-stu-id="f08be-104">The VETRO pattern is a common composite pattern that combines multiple actions taken on a message when it is received.</span></span> <span data-ttu-id="f08be-105">El término VETRO es el acrónimo de validación, enriquecimiento, transformación, ruta, Operate.</span><span class="sxs-lookup"><span data-stu-id="f08be-105">The term VETRO is an acronym that stands for Validate, Enrich, Transform, Route, Operate.</span></span> <span data-ttu-id="f08be-106">En el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], estas acciones pueden administrarse como fases individuales en la canalización asociada con la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="f08be-106">In the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], these actions can be handled as individual stages in the pipeline associated with the receive location.</span></span> <span data-ttu-id="f08be-107">Para obtener más información acerca de cómo se puede implementar cada una de estas fases, vea tareas de desarrollo y escenarios clave.</span><span class="sxs-lookup"><span data-stu-id="f08be-107">For more information about how each of these stages can be implemented, see Key Scenarios and Development Tasks.</span></span>  
  
## <a name="request-response"></a><span data-ttu-id="f08be-108">Solicitudes y respuestas</span><span class="sxs-lookup"><span data-stu-id="f08be-108">Request-Response</span></span>  
 <span data-ttu-id="f08be-109">El patrón de solicitud-respuesta define una solución en la que un servicio o usuario envía una solicitud de mensaje y espera un mensaje de respuesta de vuelta desde el servicio de destino.</span><span class="sxs-lookup"><span data-stu-id="f08be-109">The Request-Response pattern defines a solution in which a service or party sends a request message and expects a reply message in return from the destination service.</span></span> <span data-ttu-id="f08be-110">Para obtener una descripción detallada de este patrón, vea [respuesta-solicitud](http://go.microsoft.com/fwlink/?LinkId=186849) ([http://go.microsoft.com/fwlink/?LinkId=186849](http://go.microsoft.com/fwlink/?LinkId=186849)) en el sitio de patrones de integración empresarial.</span><span class="sxs-lookup"><span data-stu-id="f08be-110">For a detailed description of this pattern, see [Request-Reply](http://go.microsoft.com/fwlink/?LinkId=186849) ([http://go.microsoft.com/fwlink/?LinkId=186849](http://go.microsoft.com/fwlink/?LinkId=186849)) on the Enterprise Integration Patterns site.</span></span>  
  
 <span data-ttu-id="f08be-111">Para obtener más información sobre cómo implementar este patrón, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="f08be-111">For more information about how to implement this pattern, see the following resources:</span></span>  
  
-   [<span data-ttu-id="f08be-112">Cómo: transformar un mensaje y una ruta a un extremo de servicio mediante un patrón de intercambio de mensajes de solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="f08be-112">How to: Transform a Message and Route to a Service Endpoint Using a Request-Response Message Exchange Pattern</span></span>](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
-   [<span data-ttu-id="f08be-113">Instalar y ejecutar el ejemplo en rampa itinerario</span><span class="sxs-lookup"><span data-stu-id="f08be-113">Installing and Running the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)