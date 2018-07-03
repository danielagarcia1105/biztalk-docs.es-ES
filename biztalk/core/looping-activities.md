---
title: Actividades en bucle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], looping activities
- activities [BAM], orchestrations
- orchestrations, looping
- orchestrations, activities
ms.assetid: fb40fdd0-ac8f-486a-b3d0-9d2200a87cda
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18cf2b768deca72b281bc189431b01f5e63a4887
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005077"
---
# <a name="looping-activities"></a><span data-ttu-id="7a6b2-102">Actividades en bucle</span><span class="sxs-lookup"><span data-stu-id="7a6b2-102">Looping Activities</span></span>
<span data-ttu-id="7a6b2-103">Las actividades en bucle son acciones asociadas en bucle dentro de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-103">Looping activities refers to actions that loop within an orchestration.</span></span> <span data-ttu-id="7a6b2-104">Existe la posibilidad de capturar los eventos de acciones asociadas en bucle dentro de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-104">It is possible to capture the events from actions that loop within an orchestration.</span></span> <span data-ttu-id="7a6b2-105">Para hacerlo, se deberá crear otra actividad y asignar todos los hitos de actividad y datos nuevos del bucle.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-105">To do this, you create another activity and map all of the new activity milestones and data inside the loop.</span></span> <span data-ttu-id="7a6b2-106">Este procedimiento es necesario porque el procesamiento de datos del bucle tendrá lugar más de una vez por cada ejecución programada.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-106">This is necessary because the data processing in the loop will occur more than once per scheduled execution.</span></span> <span data-ttu-id="7a6b2-107">La siguiente ilustración muestra un ejemplo de esta situación.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-107">The following figure shows an example of this situation.</span></span>  
  
 <span data-ttu-id="7a6b2-108">![](../core/media/handlingloops2.gif "handlingloops2")</span><span class="sxs-lookup"><span data-stu-id="7a6b2-108">![](../core/media/handlingloops2.gif "handlingloops2")</span></span>  
  
 <span data-ttu-id="7a6b2-109">Como se muestra en la ilustración, si tiene un pedido de compra con varios elementos de línea que se procesan en un bucle, preguntas como "qué pedidos tienen precios de artículos de $100?"</span><span class="sxs-lookup"><span data-stu-id="7a6b2-109">As shown in the figure, if you have a Purchase Order with multiple Line Items that process in a loop, questions like "Which purchase orders have item prices of $100?"</span></span> <span data-ttu-id="7a6b2-110">son ambiguas.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-110">are ambiguous.</span></span> <span data-ttu-id="7a6b2-111">Las preguntas no ambiguas son:</span><span class="sxs-lookup"><span data-stu-id="7a6b2-111">Unambiguous questions are:</span></span>  
  
- <span data-ttu-id="7a6b2-112">¿Qué pedidos tienen elementos de línea con un precio de $100?</span><span class="sxs-lookup"><span data-stu-id="7a6b2-112">Which purchase orders have line items with a price of $100?</span></span>  
  
- <span data-ttu-id="7a6b2-113">¿Qué pedidos tienen precios Total/Mín./Máx. de $100?</span><span class="sxs-lookup"><span data-stu-id="7a6b2-113">Which purchase orders have Total/Min/Max item prices of $100?</span></span>  
  
  <span data-ttu-id="7a6b2-114">La creación de preguntas no ambiguas pasa por concebir los elementos de línea de pedido como elementos independientes del pedido.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-114">Creating unambiguous questions requires thinking of the line items as something separate from the purchase order.</span></span> <span data-ttu-id="7a6b2-115">En el Editor de perfiles de seguimiento, la actividad raíz (por ejemplo, un pedido de compra) se asigna a todas las acciones externas al bucle.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-115">In the Tracking Profile Editor, the root activity (for example, a purchase order) maps to all actions outside the loop.</span></span> <span data-ttu-id="7a6b2-116">La actividad secundaria (por ejemplo, el elemento de línea) se asigna a las acciones dentro del bucle.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-116">The child activity (for example, line item) maps to the actions inside the loop.</span></span>  
  
  <span data-ttu-id="7a6b2-117">Deberá utilizar un elemento de carga como ActivityID para la actividad raíz.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-117">You need to use a payload item as ActivityID for the root activity.</span></span> <span data-ttu-id="7a6b2-118">Tenga este elemento de carga disponible en algunos de los mensajes internos del bucle.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-118">Have this payload item available in some of the messages inside the loop.</span></span> <span data-ttu-id="7a6b2-119">Asigne la actividad al nodo Relación que se muestra bajo la actividad secundaria, y asígnele el mismo nombre que la actividad raíz.</span><span class="sxs-lookup"><span data-stu-id="7a6b2-119">Map the activity to the Relationship node that displays under the child activity and name it as the root activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a6b2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a6b2-120">See Also</span></span>  
 [<span data-ttu-id="7a6b2-121">Implementar actividades de BAM con secuencias de eventos</span><span class="sxs-lookup"><span data-stu-id="7a6b2-121">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)