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
# <a name="activity-continuation"></a><span data-ttu-id="cf811-102">Continuación de actividad</span><span class="sxs-lookup"><span data-stu-id="cf811-102">Activity Continuation</span></span>
<span data-ttu-id="cf811-103">La actividad de BAM (a la que también se denomina la actividad de negocio) puede abarcar varias aplicaciones heterogéneas (por ejemplo, una canalización, dos orquestaciones, una aplicación de líneas de negocio y la otra canalización).</span><span class="sxs-lookup"><span data-stu-id="cf811-103">The BAM activity (also called the business activity) can span multiple heterogeneous applications (for example, a pipeline, two orchestrations, a line-of-business application, and then another pipeline).</span></span> <span data-ttu-id="cf811-104">La infraestructura de BAM puede correlacionar los eventos de varias aplicaciones con un poco de Ayuda del programador, concepto que se denomina "*continuación*," que se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="cf811-104">The BAM infrastructure can correlate the events from multiple applications with a little help from the developer – a concept called "*Continuation*," which is shown in the following figure.</span></span>  
  
 ![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")  

## <a name="applications"></a><span data-ttu-id="cf811-105">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="cf811-105">Applications</span></span>  
 <span data-ttu-id="cf811-106">La primera parte de la actividad ocurre en la aplicación de ventas, la segunda parte de la actividad ocurre en la aplicación de empaquetado y ensamblado y, por último, el progreso de entrega está disponible en la aplicación de envíos.</span><span class="sxs-lookup"><span data-stu-id="cf811-106">The first part of the activity happens in the Sales application, the second part of the activity happens in the Packaging & Assembly application, and finally, the delivery progress is available in the Shipping application.</span></span> <span data-ttu-id="cf811-107">Cada aplicación utiliza identificadores diferentes para la unidad de trabajo actual: número de pedido (PO), número de pedido de venta (SO) y el número de orden de envío (UPS) de la compra.</span><span class="sxs-lookup"><span data-stu-id="cf811-107">Each application uses different IDs for the current work unit: purchase order number (PO), sales order number (SO), and shipping order number (UPS).</span></span> <span data-ttu-id="cf811-108">Para correlacionar los eventos entre dos aplicaciones diferentes, es necesario:</span><span class="sxs-lookup"><span data-stu-id="cf811-108">To correlate the events between two different applications, you must:</span></span>  
  
-   <span data-ttu-id="cf811-109">Identificar el token de continuación, que es un conjunto único de datos que está disponible para las dos aplicaciones (por ejemplo, la parte del mensaje que se intercambia).</span><span class="sxs-lookup"><span data-stu-id="cf811-109">Identify the continuation token – a unique piece of data that is available to both applications (for example, the part of the message being exchanged).</span></span>  
  
-   <span data-ttu-id="cf811-110">Llamar a EnableContinuation en la primera aplicación y pase el token de continuación junto con el ActivityID actual.</span><span class="sxs-lookup"><span data-stu-id="cf811-110">Call EnableContinuation in the first application and pass the continuation token along with the current ActivityID.</span></span>  
  
-   <span data-ttu-id="cf811-111">No llame a BeginActivity en la segunda aplicación.</span><span class="sxs-lookup"><span data-stu-id="cf811-111">Do not call BeginActivity in the second application.</span></span>  
  
-   <span data-ttu-id="cf811-112">Activar todos los eventos posteriores en la segunda aplicación mediante el token de continuación en vez de ActivityID.</span><span class="sxs-lookup"><span data-stu-id="cf811-112">Fire all subsequent events in the second application by using the continuation token instead of ActivityID.</span></span>  
  
 <span data-ttu-id="cf811-113">En el ejemplo del código siguiente se ilustra el uso de continuación de actividad entre tres aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="cf811-113">The following code example illustrates the use of activity continuation among three applications:</span></span>  
  
 <span data-ttu-id="cf811-114">**Aplicación de pedidos de compra**</span><span class="sxs-lookup"><span data-stu-id="cf811-114">**Purchase Order Application**</span></span>  
  
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
  
 <span data-ttu-id="cf811-115">**Aplicación de procesamiento**</span><span class="sxs-lookup"><span data-stu-id="cf811-115">**Fulfillment Application**</span></span>  
  
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
  
 <span data-ttu-id="cf811-116">**Aplicación de envíos**</span><span class="sxs-lookup"><span data-stu-id="cf811-116">**Shipping Application**</span></span>  
  
```  
string upsID="UPS#97892"  
es.UpdateActivity("PurchaseOrder", upsID,  
"POShipped",DateTime.UtcNow);  
es.EndActivity("PurchaseOrder",upsID)  
  
```  
  
 <span data-ttu-id="cf811-117">Siga estas directrices para usar la continuación de actividad en su código:</span><span class="sxs-lookup"><span data-stu-id="cf811-117">Follow these guidelines to use activity continuation in your code:</span></span>  
  
-   <span data-ttu-id="cf811-118">Utilice la continuación únicamente cuando el usuario final tenga que tratar el trabajo de aplicaciones distintas como parte de la misma actividad.</span><span class="sxs-lookup"><span data-stu-id="cf811-118">Only use continuation when the end user must treat the work of different applications as part of the same activity.</span></span> <span data-ttu-id="cf811-119">Utilice actividades independientes para cada aplicación y cree una relación de actividad si el usuario final ve el trabajo en cada aplicación como actividades significativas.</span><span class="sxs-lookup"><span data-stu-id="cf811-119">Use separate activities for each application and create an activity relationship if the end user views the work in each applications as meaningful activities.</span></span>  
  
-   <span data-ttu-id="cf811-120">Si las unidades de trabajo de las aplicaciones no tienen una relación de uno a uno, puede utilizar relaciones de actividad pero no la continuación, por ejemplo cuando existen varios envíos para un pedido de venta.</span><span class="sxs-lookup"><span data-stu-id="cf811-120">If the work units in the applications do not have a one-to-one relationship, you can use activity relationships but not continuation, for example, when multiple shipments exist for a sales order.</span></span>  
  
-   <span data-ttu-id="cf811-121">Si se envían datos a BAM de forma sincrónica (mediante DirectEventStream) y el ActivityID se propaga a todos los componentes implicados, no es necesario que utilice la continuación.</span><span class="sxs-lookup"><span data-stu-id="cf811-121">If you send data to BAM synchronously (using DirectEventStream) and the ActivityID is propagated to all involved components, then you do not need to use continuation.</span></span>  
  
-   <span data-ttu-id="cf811-122">Si envía datos a BAM de forma asíncrona, (mediante BufferedEventStream o desde las orquestaciones), debe utilizar la continuación aunque se propague ActivityID a todos los componentes.</span><span class="sxs-lookup"><span data-stu-id="cf811-122">If you send data to BAM asynchronously (using BufferedEventStream or from orchestrations), then you must use continuation even if the ActivityID is propagated to all components.</span></span> <span data-ttu-id="cf811-123">En este caso, es necesario utilizar un ActivityID diferente en cada aplicación, y utilizar en ellos un prefijo de cadena única (por ejemplo, Nombre de aplicación).</span><span class="sxs-lookup"><span data-stu-id="cf811-123">In this case, you need to use a different ActivityID in each application by prefixing it with a unique string (for example, Application Name).</span></span> <span data-ttu-id="cf811-124">Este proceso resulta necesario porque puede que los datos de las distintas aplicaciones lleguen a BAM de forma aleatoria y BAM tenga que ocultar los eventos desordenados para garantizar resultados correctos en la consulta y la agregación.</span><span class="sxs-lookup"><span data-stu-id="cf811-124">This is necessary because the data from different applications may arrive to BAM in random order and BAM has to hide the out-of-order events to ensure correct query and aggregation results.</span></span>  
  
-   <span data-ttu-id="cf811-125">La continuación no requiere volver a escribir sus aplicaciones para intercambiar más datos.</span><span class="sxs-lookup"><span data-stu-id="cf811-125">Continuation does not require rewriting your applications to exchange more data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf811-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf811-126">See Also</span></span>  
  
 <span data-ttu-id="cf811-127">[Infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="cf811-127">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="cf811-128">[API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md) </span><span class="sxs-lookup"><span data-stu-id="cf811-128">[BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md) </span></span>  
 [<span data-ttu-id="cf811-129">BAM-to-End (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="cf811-129">BAM End-to-End (BizTalk Server Sample)</span></span>](../core/bam-end-to-end-biztalk-server-sample.md)