---
title: Uso de una actividad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e218e2a-27f8-4df2-a1e0-27392112d369
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13b56424e06bdb8fad043acd92c22a88ca19f478
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287188"
---
# <a name="using-an-activity"></a><span data-ttu-id="7c0a4-102">Utilizar una actividad</span><span class="sxs-lookup"><span data-stu-id="7c0a4-102">Using an Activity</span></span>
<span data-ttu-id="7c0a4-103">La manera más fácil de utilizar BAM es enviar datos o hitos explícitos mediante la API de BAM.</span><span class="sxs-lookup"><span data-stu-id="7c0a4-103">The simplest way to use BAM is to send explicit milestones or data using the BAM API.</span></span> <span data-ttu-id="7c0a4-104">Puede pensar en la actividad BAM como registro de una tabla SQL que mantiene en sincronización con la unidad de trabajo real.</span><span class="sxs-lookup"><span data-stu-id="7c0a4-104">You can think of the BAM activity as a record in a SQL table that you are keeping in synchronization with the actual unit of work.</span></span>  
  
-   <span data-ttu-id="7c0a4-105">Llame a `BeginActivity` para cada unidad de trabajo nueva.</span><span class="sxs-lookup"><span data-stu-id="7c0a4-105">Call `BeginActivity` for each new unit of work.</span></span>  
  
-   <span data-ttu-id="7c0a4-106">Llamar a `EndActivity` cuando el trabajo se complete y espere más eventos en el contexto de esta unidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7c0a4-106">Call `EndActivity` when the work is complete and you expect no more events in the context of this unit of work.</span></span>  
  
-   <span data-ttu-id="7c0a4-107">Llame a [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) en lugares críticos de la implementación, para enviar datos e hitos que le serán útiles al trabajador de la información.</span><span class="sxs-lookup"><span data-stu-id="7c0a4-107">Call [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) in critical places of the implementation, to send data and milestones that will be useful to the information worker.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7c0a4-108">La secuencia de eventos debe vaciarse antes de eliminarse.</span><span class="sxs-lookup"><span data-stu-id="7c0a4-108">The Event Stream must be flushed before disposing.</span></span> <span data-ttu-id="7c0a4-109">El objeto EventStream no efectúa un vaciado automático de los datos al eliminarse.</span><span class="sxs-lookup"><span data-stu-id="7c0a4-109">The EventStream object does not perform an automatic flush of the data when disposed.</span></span> <span data-ttu-id="7c0a4-110">Ello significa que el código que, por lo general, se escribiría, y en el cual se vacía la secuencia únicamente después de finalizar el procesamiento de las actividades, puede ocasionar la pérdida de datos en el caso de que se produzca una excepción antes que una llamada de vaciado.</span><span class="sxs-lookup"><span data-stu-id="7c0a4-110">This means that code you would typically write in which you flush the stream only after you have finished processing your activities can result in data loss if an exception occurs before a call to flush.</span></span>  
>   
>  <span data-ttu-id="7c0a4-111">Para evitar la pérdida de datos, recomendamos encapsular el procesamiento y efectuar el vaciado en un bloque try/finally como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="7c0a4-111">To avoid data loss, we recommend that you encapsulate the processing and flush in a try/finally block as shown in the pseudo code below:</span></span>  
  
```  
BufferedEventStream es = new BufferedEventStream(…)  
Try  
{  
   // Do the activity processing here.  
}  
Finally  
{  
   if (es != null ) es.Flush();  
}  
```  
  
 <span data-ttu-id="7c0a4-112">El código de ejemplo siguiente muestra cómo hacer uso de BeginActivity, UpdateActivity y EndActivity cuando la unidad de trabajo es un pedido.</span><span class="sxs-lookup"><span data-stu-id="7c0a4-112">The following example code shows how to do use BeginActivity, UpdateActivity, and EndActivity when the unit of work is a Purchase Order.</span></span> <span data-ttu-id="7c0a4-113">En el ejemplo, se supone que la variable de cadena **poid** identifica el pedido de compra actual en proceso:</span><span class="sxs-lookup"><span data-stu-id="7c0a4-113">In the example, we assume that the string variable **poid** identifies the current Purchase Order in process:</span></span>  
  
```  
using Microsoft.BizTalk.BAM.EventObservation;  
...   
EventStream es=new DirectEventStream(connectionString,1);  
...  
// At the beginning of the processing of a new work:  
//    Here poid is a string variable that has the current   
//    Purchase Order identifier (e.g. PO number)  
es.BeginActivity("PurchaseOrder",poid);  
es.UpdateActivity("PurchaseOrder",poid,  
    "POReceived",DateTime.UtcNow,  
    "POAmount",100,  
    "CustomerName",""Joe",  
    "CustomerCity","Seattle");  
...  
// few days later  
es.UpdateActivity("PurchaseOrder",poid,  
    "POApproved",DateTime.UtcNow,  
    "ProductName","Widget");  
...  
// and another few days later  
es. UpdateActivity("PurchaseOrder",poid,  
    "POShipped",DateTime.UtcNow);  
...  
// and finally  
es. UpdateActivity("PurchaseOrder",poid,  
    "Delivered",DateTime.UtcNow);  
es.EndActivity("PurchaseOrder",poid);  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c0a4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c0a4-114">See Also</span></span>  
 <span data-ttu-id="7c0a4-115">[Implementar actividades BAM con secuencias de eventos](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="7c0a4-115">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 <span data-ttu-id="7c0a4-116">[Continuación de actividad](../core/activity-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="7c0a4-116">[Activity Continuation](../core/activity-continuation.md) </span></span>  
 <span data-ttu-id="7c0a4-117">[Infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="7c0a4-117">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="7c0a4-118">API de BAM (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="7c0a4-118">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)