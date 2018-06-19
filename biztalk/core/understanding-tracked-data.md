---
title: Descripción de los datos sometidos a seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- instances, viewing
- service instances, viewing
- viewing, suspended instances
- messages, viewing
- viewing, service details
- viewing, orchestration details
- viewing, message details
- orchestrations, viewing
- suspended instances
- instances, suspended
ms.assetid: dcc3fbd5-cd2c-4780-a577-0ccd521cf5eb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed30934ca154c8b6921682112b12d016c57f92be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286588"
---
# <a name="understanding-tracked-data"></a><span data-ttu-id="07954-102">Descripción de los datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="07954-102">Understanding Tracked Data</span></span>
<span data-ttu-id="07954-103">Cuando se ejecuta una consulta de seguimiento, la información supervisada aparece en la lista de resultados, en la parte inferior de la ventana Resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="07954-103">When you run a tracking query, the tracked information appears in the results list at the bottom of the Query Results window.</span></span>  
  
## <a name="viewing-message-details"></a><span data-ttu-id="07954-104">Ver detalles de mensajes</span><span class="sxs-lookup"><span data-stu-id="07954-104">Viewing message details</span></span>  
 <span data-ttu-id="07954-105">Puede realizar un seguimiento de las propiedades del mensaje.</span><span class="sxs-lookup"><span data-stu-id="07954-105">You can track message properties.</span></span> <span data-ttu-id="07954-106">También es posible guardar los cuerpos de mensajes de los que se ha hecho un seguimiento mediante herramientas que no son de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="07954-106">You can also save tracked message bodies to a file and view them using non-Microsoft tools.</span></span>  
  
-   <span data-ttu-id="07954-107">Haga clic con el botón secundario en cualquier mensaje al que hace referencia la instancia de servicio y seleccione Detalles de mensajes.</span><span class="sxs-lookup"><span data-stu-id="07954-107">You can right-click any message referenced by a service instance and select Message details.</span></span>  
  
-   <span data-ttu-id="07954-108">Si el mensaje ya se ha procesado pero se ha realizado un seguimiento, porque estaba activado el seguimiento, puede guardarlo en el disco duro y examinarlo.</span><span class="sxs-lookup"><span data-stu-id="07954-108">If the message is already processed but it was tracked—because you had tracking turned on—you can save it to your hard disk and examine it.</span></span>  
  
-   <span data-ttu-id="07954-109">Puede adjuntarlo a la instancia de orquestación y utilizar el depurador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="07954-109">You can attach to the orchestration instance and use the Orchestration Debugger.</span></span>  
  
## <a name="viewing-service-events"></a><span data-ttu-id="07954-110">Ver eventos de servicio</span><span class="sxs-lookup"><span data-stu-id="07954-110">Viewing service events</span></span>  
 <span data-ttu-id="07954-111">Cuando un servicio suspendido aparece en el registro de eventos, puede investigar un servicio mediante la **flujo de mensajes**, **depurador de orquestaciones**, **mostrar eventos de mensajes controlados**, **Mostrar instancias de servicio Live**, opciones de la **contexto** menú.</span><span class="sxs-lookup"><span data-stu-id="07954-111">When a suspended service appears in the event log, you can investigate a service by using the **Message Flow**, **Orchestration Debugger**, **Show Tracked Message Events**, **Show Live Service Instances**, options from the **Context** menu.</span></span>  
  
## <a name="viewing-orchestration-events"></a><span data-ttu-id="07954-112">Ver eventos de orquestación</span><span class="sxs-lookup"><span data-stu-id="07954-112">Viewing orchestration events</span></span>  
 <span data-ttu-id="07954-113">Utilice el depurador de orquestaciones para ver la ruta que la instancia de mensaje tomó a través de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="07954-113">Use the Orchestration Debugger to view the path a message instance has taken through an orchestration.</span></span> <span data-ttu-id="07954-114">A medida que se desplaza, la imagen que se representa de la orquestación muestra el progreso del mensaje y le permite colocar puntos de interrupción en la orquestación para la depuración.</span><span class="sxs-lookup"><span data-stu-id="07954-114">As you step through, a rendered image of the orchestration shows the progress of the message, and allows you to place breakpoints in the orchestration for debugging purposes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07954-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="07954-115">In This Section</span></span>  
  
-   [<span data-ttu-id="07954-116">¿Qué es el seguimiento de mensajes?</span><span class="sxs-lookup"><span data-stu-id="07954-116">What is Message Tracking?</span></span>](../core/what-is-message-tracking.md)  
  
-   [<span data-ttu-id="07954-117">¿Qué es el seguimiento de eventos?</span><span class="sxs-lookup"><span data-stu-id="07954-117">What is Event Tracking?</span></span>](../core/what-is-event-tracking.md)