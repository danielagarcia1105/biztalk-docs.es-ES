---
title: Separar tipo de transporte y procesamiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transport types, decoupling processing
- processing, decoupling transport types
- transport types
- transport types, service solutions
- service solution tutorial, MQSeries adapters
- processing, service solutions
- service solution tutorial, decoupling transport type and processing
- correlations, MQSeries adapters
- MQSeries adapters, correlations
- MQSeries adapters, service solutions
ms.assetid: 0b2c733a-e2c7-42ff-a733-f712fde38f7e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b14522c6bbf9393bc22f632c4db5eeb5e4a22a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="decoupling-transport-type-and-processing"></a><span data-ttu-id="6f9b1-102">Separar tipo de transporte y procesamiento</span><span class="sxs-lookup"><span data-stu-id="6f9b1-102">Decoupling Transport Type and Processing</span></span>
<span data-ttu-id="6f9b1-103">En una solución orientada a servicios, existe a menudo una línea que delimita claramente el procesamiento empresarial y los detalles de la transmisión y recepción de mensajes.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-103">In a service oriented solution, a clear line often exists between the business processing and the specifics of transmitting and receiving messages.</span></span> <span data-ttu-id="6f9b1-104">Esto le permite cambiar por separado el proceso empresarial o la parte de mensajería de la solución.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-104">This enables you to change the business process or the messaging part of the solution independently.</span></span>  
  
 <span data-ttu-id="6f9b1-105">La solución orientada a servicios infringe este principio de diseño en un lugar.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-105">The service oriented solution violates this design principle in one place.</span></span> <span data-ttu-id="6f9b1-106">En esta sección se describen la situación, las alternativas posibles y la estructura seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-106">This section describes the situation, the possible alternatives, and the selected structure.</span></span>  
  
## <a name="correlation-and-the-mqseries-adapter"></a><span data-ttu-id="6f9b1-107">Correlación y adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="6f9b1-107">Correlation and the MQSeries Adapter</span></span>  
 <span data-ttu-id="6f9b1-108">Para utilizar el adaptador de MQSeries, no puede utilizar los identificadores de correlación estándar de servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-108">In order to use the MQSeries adapter, you cannot use the standard BizTalk Server correlation identifiers.</span></span> <span data-ttu-id="6f9b1-109">Ello se debe a que el identificador de correlación va a un sistema de servidor IBM que tiene su propio sistema de identificadores de correlación.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-109">This is because the correlation identifier goes to an IBM back-end system that has its own system of correlation identifiers.</span></span> <span data-ttu-id="6f9b1-110">En su lugar, debe utilizar el **MQSeries.MQMD Correlid** y **MQSeries.MQMD MSGID** propiedades.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-110">Instead, you must use the **MQSeries.MQMD_CorrelId** and **MQSeries.MQMD_MsgID** properties.</span></span> <span data-ttu-id="6f9b1-111">Al utilizar estas propiedades, puede incluir información específica de transporte en la orquestación y, por tanto, en el proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-111">Using these properties potentially puts transport-specific information in the orchestration and, thus, in the business process.</span></span>  
  
 <span data-ttu-id="6f9b1-112">Una forma de controlar esta dependencia sería utilizar el identificador de correlación del servidor BizTalk Server y utilizar un componente de canalización personalizado para traducir el identificador de correlación para MQSeries.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-112">One way to handle this dependency would be to use the BizTalk Server correlation identifier and use a custom pipeline component to translate the correlation identifier for MQSeries.</span></span> <span data-ttu-id="6f9b1-113">Esto agrega complejidad al escenario.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-113">This adds complexity to the scenario.</span></span> <span data-ttu-id="6f9b1-114">Además, si cambia el transporte, se deben cambiar dos componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-114">In addition, if the transport changes, two pipeline components must be changed.</span></span> <span data-ttu-id="6f9b1-115">Y, en última instancia, reubica la dependencia (en el componente de canalización) en vez de resolverla.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-115">And, ultimately, it relocates the dependency (in the pipeline component) rather than resolving it.</span></span>  
  
 <span data-ttu-id="6f9b1-116">Otra opción sería aislar el control de la correlación específica de MQSeries en una orquestación independiente y llamar a esa orquestación.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-116">Another option would be to isolate the MQSeries-specific correlation handling to a separate orchestration and call that orchestration.</span></span> <span data-ttu-id="6f9b1-117">Esto conservaría la independencia del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-117">This would preserve the independence of the business process.</span></span> <span data-ttu-id="6f9b1-118">Sin embargo, esto incluye una dependencia en tiempo de compilación entre las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-118">However, this introduces a compile-time dependency between the orchestrations.</span></span> <span data-ttu-id="6f9b1-119">Modificar el transporte requiere volver a compilar ambas orquestaciones (como, por ejemplo, al pasar del código auxiliar a la versión del adaptador de la solución).</span><span class="sxs-lookup"><span data-stu-id="6f9b1-119">Modifying the transport requires recompiling both orchestrations (as, for example, in going from the stub to the adapter version of the solution).</span></span> <span data-ttu-id="6f9b1-120">La llamada también agrega a la respuesta tiempo para la solución.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-120">The call also adds to the response time for the solution.</span></span>  
  
 <span data-ttu-id="6f9b1-121">Dadas la complejidad adicional y la posible disminución del rendimiento, parece que lo más fácil es utilizar la correlación de MQSeries directamente en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="6f9b1-121">Given the additional complexity and possible decrease in performance, it seemed simplest to use the MQSeries correlation directly in the orchestration.</span></span>  
  
 <span data-ttu-id="6f9b1-122">Para obtener más información acerca del adaptador y correlaciones en orquestaciones, consulte [MQSCorrelationSetOrchestration (ejemplo de BizTalk Server)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="6f9b1-122">For more information about the adapter and correlations in orchestrations, see [MQSCorrelationSetOrchestration (BizTalk Server Sample)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f9b1-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f9b1-123">See Also</span></span>  
 <span data-ttu-id="6f9b1-124">[Aspectos destacados de la implementación del servicio en la solución orientada a servicios](../core/implementation-highlights-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="6f9b1-124">[Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="6f9b1-125">MQSCorrelationSetOrchestration (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="6f9b1-125">MQSCorrelationSetOrchestration (BizTalk Server Sample)</span></span>](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)