---
title: Las actividades en bucle | Documentos de Microsoft
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
ms.openlocfilehash: 6f66382a27ed564da0c41257e8abe95accba5e2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262084"
---
# <a name="looping-activities"></a><span data-ttu-id="fe78a-102">Actividades en bucle</span><span class="sxs-lookup"><span data-stu-id="fe78a-102">Looping Activities</span></span>
<span data-ttu-id="fe78a-103">Las actividades en bucle son acciones asociadas en bucle dentro de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="fe78a-103">Looping activities refers to actions that loop within an orchestration.</span></span> <span data-ttu-id="fe78a-104">Existe la posibilidad de capturar los eventos de acciones asociadas en bucle dentro de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="fe78a-104">It is possible to capture the events from actions that loop within an orchestration.</span></span> <span data-ttu-id="fe78a-105">Para hacerlo, se deberá crear otra actividad y asignar todos los hitos de actividad y datos nuevos del bucle.</span><span class="sxs-lookup"><span data-stu-id="fe78a-105">To do this, you create another activity and map all of the new activity milestones and data inside the loop.</span></span> <span data-ttu-id="fe78a-106">Este procedimiento es necesario porque el procesamiento de datos del bucle tendrá lugar más de una vez por cada ejecución programada.</span><span class="sxs-lookup"><span data-stu-id="fe78a-106">This is necessary because the data processing in the loop will occur more than once per scheduled execution.</span></span> <span data-ttu-id="fe78a-107">La siguiente ilustración muestra un ejemplo de esta situación.</span><span class="sxs-lookup"><span data-stu-id="fe78a-107">The following figure shows an example of this situation.</span></span>  
  
 ![](../core/media/handlingloops2.gif "handlingloops2")  
  
 <span data-ttu-id="fe78a-108">Como se muestra en la ilustración, si tiene un pedido de compra con varios elementos de línea que se procesan en un bucle, preguntas como "qué pedidos tienen precios de $100?"</span><span class="sxs-lookup"><span data-stu-id="fe78a-108">As shown in the figure, if you have a Purchase Order with multiple Line Items that process in a loop, questions like "Which purchase orders have item prices of $100?"</span></span> <span data-ttu-id="fe78a-109">son ambiguas.</span><span class="sxs-lookup"><span data-stu-id="fe78a-109">are ambiguous.</span></span> <span data-ttu-id="fe78a-110">Las preguntas no ambiguas son:</span><span class="sxs-lookup"><span data-stu-id="fe78a-110">Unambiguous questions are:</span></span>  
  
-   <span data-ttu-id="fe78a-111">¿Qué pedidos tienen elementos de línea con un precio de $100?</span><span class="sxs-lookup"><span data-stu-id="fe78a-111">Which purchase orders have line items with a price of $100?</span></span>  
  
-   <span data-ttu-id="fe78a-112">¿Qué pedidos tienen precios Total/Mín./Máx. de $100?</span><span class="sxs-lookup"><span data-stu-id="fe78a-112">Which purchase orders have Total/Min/Max item prices of $100?</span></span>  
  
 <span data-ttu-id="fe78a-113">La creación de preguntas no ambiguas pasa por concebir los elementos de línea de pedido como elementos independientes del pedido.</span><span class="sxs-lookup"><span data-stu-id="fe78a-113">Creating unambiguous questions requires thinking of the line items as something separate from the purchase order.</span></span> <span data-ttu-id="fe78a-114">En el Editor de perfiles de seguimiento, la actividad raíz (por ejemplo, un pedido de compra) se asigna a todas las acciones externas al bucle.</span><span class="sxs-lookup"><span data-stu-id="fe78a-114">In the Tracking Profile Editor, the root activity (for example, a purchase order) maps to all actions outside the loop.</span></span> <span data-ttu-id="fe78a-115">La actividad secundaria (por ejemplo, el elemento de línea) se asigna a las acciones dentro del bucle.</span><span class="sxs-lookup"><span data-stu-id="fe78a-115">The child activity (for example, line item) maps to the actions inside the loop.</span></span>  
  
 <span data-ttu-id="fe78a-116">Deberá utilizar un elemento de carga como ActivityID para la actividad raíz.</span><span class="sxs-lookup"><span data-stu-id="fe78a-116">You need to use a payload item as ActivityID for the root activity.</span></span> <span data-ttu-id="fe78a-117">Tenga este elemento de carga disponible en algunos de los mensajes internos del bucle.</span><span class="sxs-lookup"><span data-stu-id="fe78a-117">Have this payload item available in some of the messages inside the loop.</span></span> <span data-ttu-id="fe78a-118">Asigne la actividad al nodo Relación que se muestra bajo la actividad secundaria, y asígnele el mismo nombre que la actividad raíz.</span><span class="sxs-lookup"><span data-stu-id="fe78a-118">Map the activity to the Relationship node that displays under the child activity and name it as the root activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe78a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe78a-119">See Also</span></span>  
 [<span data-ttu-id="fe78a-120">Implementar actividades BAM con secuencias de eventos</span><span class="sxs-lookup"><span data-stu-id="fe78a-120">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)