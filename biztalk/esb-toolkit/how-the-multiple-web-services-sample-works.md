---
title: Cómo los varios servicios Web funciona de ejemplo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16680ca7-16cc-47df-8c39-a3311d468a46
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b3d9faf350654be69015ea940b6b4f034d4de74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294164"
---
# <a name="how-the-multiple-web-services-sample-works"></a><span data-ttu-id="a0f01-102">Cómo el varios servicios Web de ejemplo funciona</span><span class="sxs-lookup"><span data-stu-id="a0f01-102">How the Multiple Web Services Sample Works</span></span>
<span data-ttu-id="a0f01-103">El ejemplo de varios servicios Web utiliza dos técnicas independientes para llamar a varios servicios Web en serie mientras todavía se puede devolver un resultado correcto al llamador original.</span><span class="sxs-lookup"><span data-stu-id="a0f01-103">The Multiple Web Services sample uses two separate techniques to call multiple Web services in serial while still being able to return a proper result to the original caller.</span></span> <span data-ttu-id="a0f01-104">Un método utiliza un componente de canalización personalizado en la canalización de respuesta, y el otro método usa un personalizado bidireccional enrutamiento basado en la orquestación itinerario servicio que omite el requisito de una invocación de fuera de rampa para completar una llamada de solicitud/respuesta a un sitio Web servicio.</span><span class="sxs-lookup"><span data-stu-id="a0f01-104">One method uses a custom pipeline component in the response pipeline, and the other method uses a custom two-way routing orchestration-based itinerary service that bypasses the requirement of an off-ramp invocation to complete a request/response call to a Web service.</span></span>  
  
 <span data-ttu-id="a0f01-105">El método de componente de canalización personalizada utiliza el componente de canalización de reenvío.</span><span class="sxs-lookup"><span data-stu-id="a0f01-105">The custom pipeline component method uses the Forwarder Pipeline component.</span></span> <span data-ttu-id="a0f01-106">Este componente condicionalmente promociona propiedades para impedir que Microsoft BizTalk enrutar el mensaje a la canalización de envío de la pendiente hasta que se procesen todos los servicios de itinerarios.</span><span class="sxs-lookup"><span data-stu-id="a0f01-106">This component conditionally promotes properties to keep Microsoft BizTalk from routing the message back to the send pipeline of the on-ramp until all the itinerary services are processed.</span></span>  
  
 <span data-ttu-id="a0f01-107">El método de servicio personalizado basado en la orquestación utiliza la orquestación TwoWayRouting contenida en ESB. MultipleWebServices.Orchestrations el proyecto en el \Source\Samples\MultipleWebSerivces\Source\ESB. Carpeta MultipleWebServices.Orchestrations.</span><span class="sxs-lookup"><span data-stu-id="a0f01-107">The custom orchestration-based service method uses the TwoWayRouting orchestration contained in the ESB.MultipleWebServices.Orchestrations project in the \Source\Samples\MultipleWebSerivces\Source\ESB.MultipleWebServices.Orchestrations folder.</span></span> <span data-ttu-id="a0f01-108">Este servicio procesa un solucionador asociado para determinar la dirección del extremo de un servicio Web bidireccional.</span><span class="sxs-lookup"><span data-stu-id="a0f01-108">This service processes an associated resolver to determine the endpoint address of a two-way Web service.</span></span> <span data-ttu-id="a0f01-109">A continuación, configura un puerto de envío dinámico Solict respuesta denominado RoutingPort para enviar el mensaje al servicio Web y devolver el resultado a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a0f01-109">It then configures a Dynamic Solict-Response Send Port named RoutingPort to send the message to the Web service and return the result to the orchestration.</span></span> <span data-ttu-id="a0f01-110">La orquestación, a continuación, hace avanzar el itinerario y devuelve el mensaje resultante en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a0f01-110">The orchestration then advances the itinerary and returns the resulting message to the MessageBox.</span></span>  
  
 <span data-ttu-id="a0f01-111">Los itinerarios incluidos con el ejemplo utilice uno o ambos de estos métodos para asegurarse de que se mantiene el flujo de mensajes siguiendo el itinerario.</span><span class="sxs-lookup"><span data-stu-id="a0f01-111">The itineraries included with the sample use one or both of these methods to ensure message flow following the itinerary is maintained.</span></span> <span data-ttu-id="a0f01-112">Para obtener más información, consulte [el ejemplo de itinerarios al servicios varias Web](../esb-toolkit/the-sample-multiple-web-services-itineraries.md).</span><span class="sxs-lookup"><span data-stu-id="a0f01-112">For more information, see [The Sample Multiple Web Services Itineraries](../esb-toolkit/the-sample-multiple-web-services-itineraries.md).</span></span>