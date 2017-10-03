---
title: "Continuación de actividad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- continuation tokens
- activities [BAM], code samples
- activities [BAM], continuation tokens
- continuations, activities [BAM]
- code samples, activities [BAM]
ms.assetid: 47d91ae6-77c1-4efb-940f-a7b3a325e5bd
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7568da0647ae9847c3de2d060d75a53466b9709
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="activity-continuation"></a>Continuación de actividad
La actividad de BAM (a la que también se denomina la actividad de negocio) puede abarcar varias aplicaciones heterogéneas (por ejemplo, una canalización, dos orquestaciones, una aplicación de líneas de negocio y la otra canalización). La infraestructura de BAM puede correlacionar los eventos de varias aplicaciones con un poco de Ayuda del programador, concepto que se denomina "*continuación*," que se muestra en la ilustración siguiente.  
  
 ![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")  

## <a name="applications"></a>Aplicaciones  
 La primera parte de la actividad ocurre en la aplicación de ventas, la segunda parte de la actividad ocurre en la aplicación de empaquetado y ensamblado y, por último, el progreso de entrega está disponible en la aplicación de envíos. Cada aplicación utiliza identificadores diferentes para la unidad de trabajo actual: número de pedido (PO), número de pedido de venta (SO) y el número de orden de envío (UPS) de la compra. Para correlacionar los eventos entre dos aplicaciones diferentes, es necesario:  
  
-   Identificar el token de continuación, que es un conjunto único de datos que está disponible para las dos aplicaciones (por ejemplo, la parte del mensaje que se intercambia).  
  
-   Llamar a EnableContinuation en la primera aplicación y pase el token de continuación junto con el ActivityID actual.  
  
-   No llame a BeginActivity en la segunda aplicación.  
  
-   Activar todos los eventos posteriores en la segunda aplicación mediante el token de continuación en vez de ActivityID.  
  
 En el ejemplo del código siguiente se ilustra el uso de continuación de actividad entre tres aplicaciones:  
  
 **Aplicación de pedidos de compra**  
  
```  
string oID="PO#123";  
string soID="SO#265";  
es.BeginActivity("PurchaseOrder",poID);  
es.UpdateActivity("PurchaseOrder",poID,  
    "POReceived",DateTime.UtcNow,  
    "POAmount",100,  
"CustomerCity","Seattle");  
es.EnableContinuation(  
   "PurchaseOrder",poId,soID);  
es.EndActivity("PurchaseOrder",poID);  
```  
  
 **Aplicación de procesamiento**  
  
```  
string soID="SO#265";  
string upsID="UPS#97892";  
es.UpdateActivity("PurchaseOrder",soID,  
    "POApproved",DateTime.UtcNow,  
    "ProductName","ProductA");  
es.EnableContinuation(  
   "PurchaseOrder",soID,upsID);  
es.EndActivity("PurchaseOrder",soID);  
```  
  
 **Aplicación de envíos**  
  
```  
string upsID="UPS#97892"  
es.UpdateActivity("PurchaseOrder", upsID,  
"POShipped",DateTime.UtcNow);  
es.EndActivity("PurchaseOrder",upsID)  
  
```  
  
 Siga estas directrices para usar la continuación de actividad en su código:  
  
-   Utilice la continuación únicamente cuando el usuario final tenga que tratar el trabajo de aplicaciones distintas como parte de la misma actividad. Utilice actividades independientes para cada aplicación y cree una relación de actividad si el usuario final ve el trabajo en cada aplicación como actividades significativas.  
  
-   Si las unidades de trabajo de las aplicaciones no tienen una relación de uno a uno, puede utilizar relaciones de actividad pero no la continuación, por ejemplo cuando existen varios envíos para un pedido de venta.  
  
-   Si se envían datos a BAM de forma sincrónica (mediante DirectEventStream) y el ActivityID se propaga a todos los componentes implicados, no es necesario que utilice la continuación.  
  
-   Si envía datos a BAM de forma asíncrona, (mediante BufferedEventStream o desde las orquestaciones), debe utilizar la continuación aunque se propague ActivityID a todos los componentes. En este caso, es necesario utilizar un ActivityID diferente en cada aplicación, y utilizar en ellos un prefijo de cadena única (por ejemplo, Nombre de aplicación). Este proceso resulta necesario porque puede que los datos de las distintas aplicaciones lleguen a BAM de forma aleatoria y BAM tenga que ocultar los eventos desordenados para garantizar resultados correctos en la consulta y la agregación.  
  
-   La continuación no requiere volver a escribir sus aplicaciones para intercambiar más datos.  
  
## <a name="see-also"></a>Vea también  
  
 [Infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md)   
 [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md)   
 [BAM-to-End (ejemplo de BizTalk Server)](../core/bam-end-to-end-biztalk-server-sample.md)