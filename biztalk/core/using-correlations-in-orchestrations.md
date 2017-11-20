---
title: Usar correlaciones en orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, orchestrations
- messages, correlation sets
- correlation sets
- orchestrations, messages
- messages, validating
ms.assetid: d919afa9-bada-406a-bf4b-7b46c831c6d5
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3be56c2171205bb49d2ff1f589c77ac309ea188
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-correlations-in-orchestrations"></a><span data-ttu-id="9f7c2-102">Usar correlaciones en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="9f7c2-102">Using Correlations in Orchestrations</span></span>
<span data-ttu-id="9f7c2-103">La correlación es el proceso de hacer coincidir un mensaje entrante con la instancia apropiada de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-103">Correlation is the process of matching an incoming message with the appropriate instance of an orchestration.</span></span> <span data-ttu-id="9f7c2-104">Por ejemplo, la orquestación envía un mensaje y recibe la respuesta o respuestas en la misma orquestación.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-104">For example, orchestration sends out of a message and receives the response or responses back into the same orchestration.</span></span> <span data-ttu-id="9f7c2-105">Hay tres patrones de intercambio de mensajes correlacionados:</span><span class="sxs-lookup"><span data-stu-id="9f7c2-105">There are three correlated messages exchange patterns:</span></span>  
  
-   <span data-ttu-id="9f7c2-106">Protocolo de enlace tradicional</span><span class="sxs-lookup"><span data-stu-id="9f7c2-106">Traditional handshake</span></span>  
  
-   <span data-ttu-id="9f7c2-107">Convoy secuencial</span><span class="sxs-lookup"><span data-stu-id="9f7c2-107">Sequential convoy</span></span>  
  
-   <span data-ttu-id="9f7c2-108">Convoy paralelo</span><span class="sxs-lookup"><span data-stu-id="9f7c2-108">Parallel convoy</span></span>  
  
 <span data-ttu-id="9f7c2-109">En el patrón de protocolo de enlace tradicional, existen protocolos de enlace entre los intercambios de los mensajes entre las orquestaciones o los procesos empresariales, y el protocolo de enlace se puede conseguir mediante la definición de conjuntos de correlaciones en las orquestaciones, donde un conjunto de correlaciones es una lista de propiedades promocionadas con valores específicos que se utiliza para enrutar mensajes a una instancia de orquestación específica.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-109">In the traditional handshake pattern, handshakes exist between the exchanges of the messages among the orchestrations or business processes, and you can achieve the handshakes by defining correlation sets in the orchestrations where a correlation set is a list of promoted properties with specific values that you use to route messages to a specific orchestration instance.</span></span>  
  
 <span data-ttu-id="9f7c2-110">Por ejemplo, si la orquestación está diseñada para emitir un pedido, recibir una factura y realizar el pago, debe asegurarse de que el mensaje de la factura se reciba en la misma instancia de orquestación desde la que se envió el correspondiente pedido, dado que se pueden procesar varios pedidos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-110">If, for example, your orchestration is designed to issue a purchase order, receive an invoice, and send out the payment, you need to be sure that the invoice message is received by the same orchestration instance that the corresponding purchase order was sent from since numbers of purchase orders may be processed at the time.</span></span> <span data-ttu-id="9f7c2-111">En este ejemplo, el número de identificación del pedido se puede usar como un parámetro del conjunto de correlaciones que permita correlacionar el mensaje del pedido y el mensaje de la factura.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-111">In this example, the purchase order identification number can be used as a parameter in the correlation set for correlating the purchase order message and the invoice message.</span></span> <span data-ttu-id="9f7c2-112">El siguiente escenario sigue este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9f7c2-112">The following is the scenario flow for this example,</span></span>  
  
1.  <span data-ttu-id="9f7c2-113">La Orquestación A envía el mensaje del pedido a la Orquestación B. El conjunto de correlaciones se inicializa antes de enviar el mensaje del pedido.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-113">The Orchestration A sends out the purchase order message to the Orchestration B. Before sending out the purchase order message, the correlation set is initialized.</span></span>  
  
2.  <span data-ttu-id="9f7c2-114">En la Orquestación B, donde se procesa el pedido y se genera y devuelve la factura, la primera forma Recepción sigue el mismo conjunto de correlaciones para recibir el mensaje del pedido.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-114">In the Orchestration B, in which processes the purchase order, generates and sends back the invoice, the first Receive shape follows the same correlation set to receive the purchase order message.</span></span>  
  
3.  <span data-ttu-id="9f7c2-115">Después de procesar el mensaje del pedido, también se sigue el mismo conjunto de correlaciones para devolver el mensaje de la factura.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-115">After processing the purchase order message, when sending back the invoice message to the Orchestration A, the same correlation set is also followed.</span></span>  
  
4.  <span data-ttu-id="9f7c2-116">En la forma Recepción de la Orquestación A que recibe el mensaje de la factura de la orquestación B también se sigue el mismo conjunto de correlaciones con el fin de garantizar que se recibe el mensaje de factura correlacionado basado en el conjunto de correlaciones predefinido.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-116">In the Orchestration A, at the Receive shape which receives the invoice message back from the orchestration B, the same correlation set is also followed to ensure that receiving the correlated invoice message based on the predefined correlation set.</span></span>  
  
 <span data-ttu-id="9f7c2-117">Los patrones de convoy secuencial y de convoy paralelo surgen cada vez que es necesario relacionar varios elementos individuales para lograr algo que el elemento individual por sí solo no puede.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-117">The sequential convoy and parallel convoy patterns exist in the world any time multiple single items must be related together in order to achieve something that the individual item cannot accomplish by itself.</span></span> <span data-ttu-id="9f7c2-118">Para obtener más información, consulte [trabajar con escenarios de convoyes](../core/working-with-convoy-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="9f7c2-118">For more information, see [Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md).</span></span>  
  
 <span data-ttu-id="9f7c2-119">Además de los patrones de intercambio de mensajes correlacionados, en la orquestación existen dos tipos de correlaciones:</span><span class="sxs-lookup"><span data-stu-id="9f7c2-119">In addition to the correlated message exchange patterns, there are two types of correlations in orchestration:</span></span>  
  
-   <span data-ttu-id="9f7c2-120">Correlación manual</span><span class="sxs-lookup"><span data-stu-id="9f7c2-120">Manual correlation</span></span>  
  
-   <span data-ttu-id="9f7c2-121">Correlación automática</span><span class="sxs-lookup"><span data-stu-id="9f7c2-121">Automatic correlation</span></span>  
  
 <span data-ttu-id="9f7c2-122">En el escenario de la correlación manual, configurará las orquestaciones manualmente para inicializar y seguir el conjunto de correlaciones que asociará los mensajes con las instancias adecuadas.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-122">In the manual correlation scenario, you manually configure the orchestrations to initialize and follow the correlation set to associate the messages with proper instances.</span></span> <span data-ttu-id="9f7c2-123">En el escenario de la correlación automática, el motor de mensajería correlacionará los mensajes y las instancias automáticamente, por ejemplo, al configurar el puerto Solicitud-respuesta o el puerto de autocorrelación en las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-123">In the automatic correlation scenario, the messaging engine will correlate the messages with the instances for you, for example, when you set up Request-Response port or Self-Correlating port in your orchestrations.</span></span>  
  
 <span data-ttu-id="9f7c2-124">Deberá usar la correlación siempre que la orquestación no disponga de una forma explícita de asociar un mensaje con una instancia, como en el caso de una recepción de activación, un puerto de solicitud-respuesta o un puerto de autocorrelación.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-124">You must use correlation whenever your orchestration does not have an explicit way of associating a message with an instance, such as an activate receive, a request-response, or a self-correlating port.</span></span>  
  
## <a name="examples-of-using-correlations"></a><span data-ttu-id="9f7c2-125">Ejemplos de uso de correlaciones</span><span class="sxs-lookup"><span data-stu-id="9f7c2-125">Examples of Using Correlations</span></span>  
  
-   [<span data-ttu-id="9f7c2-126">PartyResolution (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="9f7c2-126">PartyResolution (BizTalk Server Sample)</span></span>](../core/partyresolution-biztalk-server-sample.md)  
  
-   <span data-ttu-id="9f7c2-127">Descargue el ejemplo SDK "Correlacionar mensajes con instancias de orquestación" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="9f7c2-127">Download the SDK sample "Correlating Messages with Orchestration Instances" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="9f7c2-128">Descargue el ejemplo SDK "Parallel Convoy" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="9f7c2-128">Download the SDK sample "Parallel Convoy" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f7c2-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9f7c2-129">In This Section</span></span>  
  
-   [<span data-ttu-id="9f7c2-130">Conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="9f7c2-130">Correlation Sets</span></span>](../core/correlation-sets.md) 
  
-   [<span data-ttu-id="9f7c2-131">Tipos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="9f7c2-131">Correlation Types</span></span>](../core/correlation-types.md) 
  
-   [<span data-ttu-id="9f7c2-132">Cómo agregar y quitar conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="9f7c2-132">How to Add and Remove Correlation Sets</span></span>](../core/how-to-add-and-remove-correlation-sets.md) 
  
-   [<span data-ttu-id="9f7c2-133">Cómo configurar conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="9f7c2-133">How to Configure Correlation Sets</span></span>](../core/how-to-configure-correlation-sets.md)  
  
-   [<span data-ttu-id="9f7c2-134">Cómo configurar tipos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="9f7c2-134">How to Configure Correlation Types</span></span>](../core/how-to-configure-correlation-types.md)  
  
-   [<span data-ttu-id="9f7c2-135">Trabajar con escenarios de convoyes</span><span class="sxs-lookup"><span data-stu-id="9f7c2-135">Working with Convoy Scenarios</span></span>](../core/working-with-convoy-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="9f7c2-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f7c2-136">See Also</span></span>  
 [<span data-ttu-id="9f7c2-137">Puertos de enlace de uso directo de autocorrelación</span><span class="sxs-lookup"><span data-stu-id="9f7c2-137">How to Use Self-Correlating Direct Bound Ports</span></span>](../core/how-to-use-self-correlating-direct-bound-ports.md)