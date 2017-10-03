---
title: Nodos Continuation y ContinuationID | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- continuation tokens
- Continuation nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- BAM, correlating activities
- activities, linking
- activities, continuation tokens
- ContinuationID nodes [Tracking Profile Editor]
ms.assetid: aa050660-66f7-4084-b6bf-b9319ce625af
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa8956721d4a44b51b8d2c7776560aaa878f864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="continuation-and-continuationid-nodes"></a><span data-ttu-id="e69ad-102">Nodos Continuation y ContinuationID</span><span class="sxs-lookup"><span data-stu-id="e69ad-102">Continuation and ContinuationID Nodes</span></span>
<span data-ttu-id="e69ad-103">Las continuaciones proporcionan a la infraestructura de BAM la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="e69ad-103">Continuations provide guidance to the BAM infrastructure about the following information:</span></span>  
  
-   <span data-ttu-id="e69ad-104">El orden en que se espera que se produzcan los eventos</span><span class="sxs-lookup"><span data-stu-id="e69ad-104">The order in which events are expected to occur</span></span>  
  
-   <span data-ttu-id="e69ad-105">Un medio para controlar cualquier cambio en el Id. único con el que se correlacionan los elementos de evento</span><span class="sxs-lookup"><span data-stu-id="e69ad-105">A way to handle any change in the unique ID to which event items are correlated</span></span>  
  
 <span data-ttu-id="e69ad-106">Dicho de otra forma, las continuaciones definen la transferencia de esta información entre colaboradores de una actividad.</span><span class="sxs-lookup"><span data-stu-id="e69ad-106">To state this another way, continuations define the transfer of this information between contributors to an activity.</span></span> <span data-ttu-id="e69ad-107">Se producirá una transferencia en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e69ad-107">A transfer occurs in the following situations:</span></span>  
  
-   <span data-ttu-id="e69ad-108">Si existe un cambio de ActivityID entre la hora de inicio y la hora de fin de una actividad.</span><span class="sxs-lookup"><span data-stu-id="e69ad-108">There is a change in the ActivityID between the time an activity begins and ends.</span></span> <span data-ttu-id="e69ad-109">Por ejemplo, si existen dos mensajes relacionados, como un número de pedido y un número de pedido de venta.</span><span class="sxs-lookup"><span data-stu-id="e69ad-109">For example, you have two related messages such as a Purchase Order number and Sales Order number.</span></span> <span data-ttu-id="e69ad-110">Cada uno de ellos tiene asignado un número exclusivo, por ejemplo 123456 para el número de pedido y 987654 para el número del pedido de venta.</span><span class="sxs-lookup"><span data-stu-id="e69ad-110">Each has a unique number assigned to it, such as 123456 for the Purchase Order number and 987654 for Sales Order number.</span></span> <span data-ttu-id="e69ad-111">En este caso, se utilizará una continuación para equiparar los identificadores únicos del pedido y del pedido de venta, de modo que los eventos puedan correlacionarse con la actividad que tienen en común, independientemente del identificador único que esté asociado a los eventos entrantes.</span><span class="sxs-lookup"><span data-stu-id="e69ad-111">You would use a continuation to equate the unique identifiers for the Purchase Order and the Sales Order so that events can be correlated to the common activity regardless of which unique identifier is associated with the incoming events.</span></span>  
  
-   <span data-ttu-id="e69ad-112">Existe una transición de un entorno en tiempo de ejecución a otro.</span><span class="sxs-lookup"><span data-stu-id="e69ad-112">You have a transition from one run-time environment to another.</span></span> <span data-ttu-id="e69ad-113">Por ejemplo, en un escenario donde haya una aplicación que proporciona un pedido de compra a una canalización de mensajería de BizTalk Server, que, a continuación, se invoca una orquestación y la orquestación, a continuación, pasa el control a una aplicación que envía un aviso de envío, se tienen dos transiciones de entorno: desde una canalización de mensajería a un una orquestación y desde una orquestación a una canalización de mensajería.</span><span class="sxs-lookup"><span data-stu-id="e69ad-113">For example, in a scenario where you have an application that supplies a purchase order to a BizTalk Server messaging pipeline, which then invokes an orchestration, and the orchestration then passes control to an application that sends a shipping notice, you have two environment transitions: from a messaging pipeline to a an orchestration and from an orchestration to a messaging pipeline.</span></span>  
  
 <span data-ttu-id="e69ad-114">Un punto importante que hay que recordar al seleccionar una propiedad para usarla en la continuación es que las propiedades deben asignarse desde el mismo contexto.</span><span class="sxs-lookup"><span data-stu-id="e69ad-114">An important point to remember when selecting a property to use for your continuation is that the properties must be mapped from the same context.</span></span>  
  
 <span data-ttu-id="e69ad-115">Por ejemplo, si tiene las propiedades Message.InterchangeID y servicecontext.InterchangeID será como si pudiera usar InterchangeID para crear la continuación.</span><span class="sxs-lookup"><span data-stu-id="e69ad-115">For example, if you have the propertiesy Message.InterchangeID and servicecontext.InterchangeID it might appear that you could use the InterchangeID to create your continuation.</span></span> <span data-ttu-id="e69ad-116">Si los mensajes se originan en diferentes contextos, no puede usar InterchangeID (ni otra propiedad) para crear una continuación confiable.</span><span class="sxs-lookup"><span data-stu-id="e69ad-116">If the messages come from different contexts you cannot use the InterchangeID (or other property) to reliably create a continuation.</span></span>  
  
## <a name="working-with-continuation-nodes"></a><span data-ttu-id="e69ad-117">Trabajar con nodos de continuación</span><span class="sxs-lookup"><span data-stu-id="e69ad-117">Working with Continuation nodes</span></span>  
 <span data-ttu-id="e69ad-118">El nodo de continuación contiene elementos de datos que indican un identificador único de instancia, también se denomina un *token de continuación*.</span><span class="sxs-lookup"><span data-stu-id="e69ad-118">The Continuation node contains data items that indicate a unique instance ID, also called a *continuation token*.</span></span> <span data-ttu-id="e69ad-119">Con el token de continuación, los programadores pueden vincular a otras actividades que usan el nodo ContinuationID.</span><span class="sxs-lookup"><span data-stu-id="e69ad-119">By using the continuation token, developers can link to other activities using the ContinuationID node.</span></span>  
  
 <span data-ttu-id="e69ad-120">Existen tres escenarios básicos en los que se utilizan los nodos de continuación y de ContinuationID:</span><span class="sxs-lookup"><span data-stu-id="e69ad-120">There are three basic scenarios in which Continuation and ContinuationID nodes are used:</span></span>  
  
-   <span data-ttu-id="e69ad-121">De orquestación a orquestación</span><span class="sxs-lookup"><span data-stu-id="e69ad-121">Orchestration to orchestration</span></span>  
  
-   <span data-ttu-id="e69ad-122">De orquestación a solución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e69ad-122">Orchestration to BizTalk solution</span></span>  
  
-   <span data-ttu-id="e69ad-123">De solución de BizTalk a orquestación</span><span class="sxs-lookup"><span data-stu-id="e69ad-123">BizTalk solution to orchestration</span></span>  
  
 <span data-ttu-id="e69ad-124">En el escenario de orquestaciones, el TPE debe definir un nodo de continuación y un nodo de ContinuationID, y ambos nodos deberán tener el mismo nombre para que BAM pueda correlacionar las actividades.</span><span class="sxs-lookup"><span data-stu-id="e69ad-124">In the orchestration scenario the TPE must define a Continuation node, and a ContinuationID node, and the nodes must have the same name in order for BAM to correlate the activities.</span></span>  
  
 <span data-ttu-id="e69ad-125">El escenario de orquestación a solución de BizTalk permite utilizar el TPE para definir un nodo de continuación, y el programador crea una solución que utiliza la API de la BAM para controlar la parte de destino de la continuación.</span><span class="sxs-lookup"><span data-stu-id="e69ad-125">In the orchestration to BizTalk solution scenario, you use the TPE to define a Continuation node and the developer creates a solution that uses the BAM API to handle the destination portion of the continuation..</span></span>  
  
 <span data-ttu-id="e69ad-126">En escenarios de solución de BizTalk a orquestación, el programador utiliza la API de BAM para proporcionar el origen del par de continuación, y el nodo de ContinuationID se define utilizando el TPE.</span><span class="sxs-lookup"><span data-stu-id="e69ad-126">In the BizTalk solution to orchestration, the developer uses the BAM API to supply the origination of the continuation pair and you use TPE to define a ContinuationID node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e69ad-127">Los puertos bidireccionales pueden funcionar en cualquier dirección, lo que significa que la intercepción de los datos que pasan a través de los puertos requerirá la habilitación de una continuación, dependiendo del comportamiento de la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e69ad-127">Two-way ports can operate in either direction, which means that interception of data that passes through the ports can, depending on the behavior of the BizTalk solution, require enabling of a continuation.</span></span> <span data-ttu-id="e69ad-128">Por ejemplo, si la activación registra “PortEndTime” para la activación de un puerto de mensajería de BizTalk Server en cualquier dirección (si lo nombres de elemento son, por ejemplo, “MessageReceived” y “MessageSent,” en ese orden), deberá crear una continuación entre ellos.</span><span class="sxs-lookup"><span data-stu-id="e69ad-128">For example, if the activity records “PortEndTime” for activation of a BizTalk Server messaging port in either direction (if the item names are, for example, “MessageReceived” and “MessageSent,” in that order), you need to create a continuation between them.</span></span> <span data-ttu-id="e69ad-129">Se requerirá una continuación siempre que exista más de una secuencia de eventos que colabore en una actividad de BAM, y existen diversas secuencias de eventos por punto de implementación (como mensajería de entrada de BTS, mensajería de salida de BTS, orquestación, aplicaciones personalizadas y servicios Web).</span><span class="sxs-lookup"><span data-stu-id="e69ad-129">A continuation is required any time more than one event stream contributes to a BAM activity, and there are distinct event streams per implementation touch point (such as BTS Messaging in, BTS Messaging out, Orchestration, custom applications, and Web services).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69ad-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e69ad-130">See Also</span></span>  
 <span data-ttu-id="e69ad-131">[Cómo crear una continuación](../core/how-to-create-a-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="e69ad-131">[How to Create a Continuation](../core/how-to-create-a-continuation.md) </span></span>  
 [<span data-ttu-id="e69ad-132">Nodos de vista de actividad TPE</span><span class="sxs-lookup"><span data-stu-id="e69ad-132">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)