---
title: Trabajar con puertos de enlace directo en orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03a37ac0-5131-4d37-b60b-56763c460463
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e7b2b59ccdaa23271ee0707f19f4fd2cddc0508
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-direct-bound-ports-in-orchestrations"></a><span data-ttu-id="6c5e5-102">Trabajar con puertos de enlace directo en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="6c5e5-102">Working with Direct Bound Ports in Orchestrations</span></span>
<span data-ttu-id="6c5e5-103">Hay tres tipos de puertos de enlace directo: cuadro de mensajes, autocorrelación y orquestación de socio.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-103">There are three types of direct bound ports: MessageBox, self-correlating, and partner orchestration.</span></span>  
  
 <span data-ttu-id="6c5e5-104">Los puertos de enlace directo de cuadro de mensajes permiten patrones de diseño de publicación-suscripción.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-104">MessageBox direct bound ports allow for publish-subscribe design patterns.</span></span> <span data-ttu-id="6c5e5-105">Los mensajes que se envían por un puerto de enlace directo de cuadro de mensajes se publican en la base de datos de cuadro de mensajes, donde los destinatarios los toman según las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-105">Messages sent on a MessageBox direct bound port are published to the MessageBox database, where message recipients pick them up based on subscriptions.</span></span> <span data-ttu-id="6c5e5-106">Los puertos de recepción lógicos configurados como puertos de enlace directo de cuadro de mensajes obtienen los mensajes directamente desde la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-106">Logical receive ports configured as MessageBox direct bound ports get messages directly from the MessageBox database.</span></span> <span data-ttu-id="6c5e5-107">Para activar **recepción** formas, el cuadro de mensajes directa enlazado reciban puertos get los mensajes a través de suscripciones para el tipo de mensaje y la expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-107">For activating **Receive** shapes, the MessageBox direct bound receive ports get the messages through subscriptions to the message type and the filter expression.</span></span> <span data-ttu-id="6c5e5-108">Para no activar **recepción** formas, el cuadro de mensajes directa enlazado reciban puertos get los mensajes a través de suscripciones para el tipo de mensaje y el conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-108">For non-activating **Receive** shapes, the MessageBox direct bound receive ports get the messages through subscriptions to the message type and the correlation set.</span></span>  
  
 <span data-ttu-id="6c5e5-109">Los puertos de enlace directo de autocorrelación le ayudan a diseñar una comunicación asíncrona entre orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-109">Self-correlating direct bound ports assist you in designing asynchronous inter-orchestration communication.</span></span> <span data-ttu-id="6c5e5-110">Los mensajes que se envían a un puerto de enlace directo de autocorrelación se enrutan a la instancia de la orquestación que ha creado el extremo receptor del puerto de enlace directo de autocorrelación.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-110">Messages sent to a self-correlating direct bound port are routed to the instance of the orchestration that created the receiving end of the self-correlated direct bound port.</span></span>  
  
 <span data-ttu-id="6c5e5-111">Los puertos de enlace directo de orquestación de socio facilitan la comunicación entre orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-111">Partner orchestration direct bound ports provide for inter-orchestration communication.</span></span> <span data-ttu-id="6c5e5-112">Los mensajes que se envían por un puerto de enlace directo de orquestación de socio se pueden enviar a la orquestación de un destinatario específico, y los mensajes que se reciben en un puerto de enlace directo de orquestación de socio pueden recibirse desde la orquestación de un remitente específico.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-112">Messages sent on a partner orchestration direct bound port can be sent to an intended recipient orchestration, and messages received on a partner orchestration direct bound port can be received from an intended sender orchestration.</span></span>  
  
 <span data-ttu-id="6c5e5-113">Aunque con el enlace directo parece que el mensaje va directamente de una orquestación a otra, en realidad todos los mensajes que se envían a través de cualquier tipo de puerto lógico viajan siempre a través de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-113">Although with direct binding, the message appears to go directly from one orchestration to another, in fact any message sent through any type of logical port always travels through the MessageBox database.</span></span> <span data-ttu-id="6c5e5-114">Por añadidura, los puertos de enlace directo no son más que puertos lógicos, de modo que el enlace directo es tan solo una característica de configuración en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-114">Moreover, direct bound ports are only logical ports and therefore direct binding is only a design-time configuration feature.</span></span> <span data-ttu-id="6c5e5-115">Un puerto de enlace directo no se puede enlazar a un puerto físico y la configuración de enlace únicamente puede cambiarse en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="6c5e5-115">A direct bound port cannot be bound to a physical port, and you can only change the direct binding configuration at design time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c5e5-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6c5e5-116">In This Section</span></span>  
  
-   [<span data-ttu-id="6c5e5-117">Cómo usar el cuadro de mensajes directamente puertos de enlace</span><span class="sxs-lookup"><span data-stu-id="6c5e5-117">How to Use MessageBox Direct Bound Ports</span></span>](../core/how-to-use-messagebox-direct-bound-ports.md)  
  
-   [<span data-ttu-id="6c5e5-118">Puertos de enlace de uso directo de autocorrelación</span><span class="sxs-lookup"><span data-stu-id="6c5e5-118">How to Use Self-Correlating Direct Bound Ports</span></span>](../core/how-to-use-self-correlating-direct-bound-ports.md)  
  
-   [<span data-ttu-id="6c5e5-119">Cómo utilizar la orquestación de socio directo puertos de enlace</span><span class="sxs-lookup"><span data-stu-id="6c5e5-119">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)  
  
## <a name="see-also"></a><span data-ttu-id="6c5e5-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c5e5-120">See Also</span></span>  
 [<span data-ttu-id="6c5e5-121">Enlaces de puertos</span><span class="sxs-lookup"><span data-stu-id="6c5e5-121">Port Bindings</span></span>](../core/port-bindings.md)