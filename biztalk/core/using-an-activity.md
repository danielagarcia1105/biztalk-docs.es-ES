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
# <a name="using-an-activity"></a>Utilizar una actividad
La manera más fácil de utilizar BAM es enviar datos o hitos explícitos mediante la API de BAM. Puede pensar en la actividad BAM como registro de una tabla SQL que mantiene en sincronización con la unidad de trabajo real.  
  
-   Llame a `BeginActivity` para cada unidad de trabajo nueva.  
  
-   Llamar a `EndActivity` cuando el trabajo se complete y espere más eventos en el contexto de esta unidad de trabajo.  
  
-   Llame a [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) en lugares críticos de la implementación, para enviar datos e hitos que le serán útiles al trabajador de la información.  
  
> [!IMPORTANT]
>  La secuencia de eventos debe vaciarse antes de eliminarse. El objeto EventStream no efectúa un vaciado automático de los datos al eliminarse. Ello significa que el código que, por lo general, se escribiría, y en el cual se vacía la secuencia únicamente después de finalizar el procesamiento de las actividades, puede ocasionar la pérdida de datos en el caso de que se produzca una excepción antes que una llamada de vaciado.  
>   
>  Para evitar la pérdida de datos, recomendamos encapsular el procesamiento y efectuar el vaciado en un bloque try/finally como se muestra en el código siguiente:  
  
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
  
 El código de ejemplo siguiente muestra cómo hacer uso de BeginActivity, UpdateActivity y EndActivity cuando la unidad de trabajo es un pedido. En el ejemplo, se supone que la variable de cadena **poid** identifica el pedido de compra actual en proceso:  
  
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
  
## <a name="see-also"></a>Vea también  
 [Implementar actividades BAM con secuencias de eventos](../core/implementing-bam-activities-with-event-streams.md)   
 [Continuación de actividad](../core/activity-continuation.md)   
 [Infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md)   
 [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md)