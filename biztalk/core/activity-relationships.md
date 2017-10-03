---
title: Las relaciones de actividad | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: activities [BAM], relationships
ms.assetid: da7c7205-18c6-44df-af03-3140214c84e6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3709ad02ed082595665c68485502847b52e5a1d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="activity-relationships"></a><span data-ttu-id="84ebc-102">Relaciones de actividades</span><span class="sxs-lookup"><span data-stu-id="84ebc-102">Activity Relationships</span></span>
<span data-ttu-id="84ebc-103">Las relaciones entre actividades existen cuando una actividad está relacionada con una o más actividades.</span><span class="sxs-lookup"><span data-stu-id="84ebc-103">An activity relationship exists when an activity relates to one or more other activities.</span></span> <span data-ttu-id="84ebc-104">Por ejemplo, cuando se tienen varias actividades de envío relacionadas con una sola actividad de pedido, o una actividad de envío que contiene elementos procedentes de dos actividades de pedido.</span><span class="sxs-lookup"><span data-stu-id="84ebc-104">An example of this is having multiple Shipment activities related to a single Purchase Order activity, or one Shipment activity containing items from two Purchase Order activities.</span></span>  
  
 <span data-ttu-id="84ebc-105">Para indicar que dos actividades están relacionadas, deberá conocer ambos nombres y tener los ActivityID correspondientes en memoria para llamar a AddRelatedActivity.</span><span class="sxs-lookup"><span data-stu-id="84ebc-105">To indicate that two activities are related, you need to know both names and have the corresponding ActivityIDs in memory in order to call AddRelatedActivity.</span></span> <span data-ttu-id="84ebc-106">Esta API crea el vínculo entre los registros de actividad correspondientes.</span><span class="sxs-lookup"><span data-stu-id="84ebc-106">This API creates the link between the corresponding activity records.</span></span>  
  
 <span data-ttu-id="84ebc-107">En la siguiente ilustración, las líneas de código resaltadas muestran cómo establecer una relación entre la instancia de actividad de pedido n.º 123 y las actividades de envío n.º 1549, 1550 y 1551.</span><span class="sxs-lookup"><span data-stu-id="84ebc-107">In the following figure, the highlighted lines of code show how you make a relationship between Purchase Order activity instance #123, and Shipment activities #1549, 1550, and 1551.</span></span>  
  
 ![](../core/media/activity-relationships-example.gif "activity_relationships_example")  
  
 <span data-ttu-id="84ebc-108">El usuario final de negocios consulta una página Web que muestra el historial de un pedido.</span><span class="sxs-lookup"><span data-stu-id="84ebc-108">The business end user looks at one Web page that shows the history of a purchase order.</span></span> <span data-ttu-id="84ebc-109">Puede indicar a las 10 A.M.</span><span class="sxs-lookup"><span data-stu-id="84ebc-109">It may indicate that at 10 A.M.</span></span> <span data-ttu-id="84ebc-110">llega, los dos días más tarde recibe la aprobación y la página proporciona un vínculo a los documentos en cuestión.</span><span class="sxs-lookup"><span data-stu-id="84ebc-110">it arrives, two days later it receives approval, and the page provides a link to the actual documents.</span></span> <span data-ttu-id="84ebc-111">Debido al código mostrado en la ilustración anterior, la página también proporcionará hipervínculos que lleven al usuario empresarial final hasta las páginas Web de envío correspondientes.</span><span class="sxs-lookup"><span data-stu-id="84ebc-111">Because of the code in the previous figure, the page will also provide hyperlinks that take the business end user to the corresponding shipment Web pages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84ebc-112">Todas las llamadas a `AddRelatedActivity` deberán producirse entre `BeginActivity` y `EndActivity`.</span><span class="sxs-lookup"><span data-stu-id="84ebc-112">All calls to `AddRelatedActivity` should happen between `BeginActivity` and `EndActivity`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ebc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="84ebc-113">See Also</span></span>  
  
 <span data-ttu-id="84ebc-114">[Continuación de actividad](../core/activity-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="84ebc-114">[Activity Continuation](../core/activity-continuation.md) </span></span>  
 <span data-ttu-id="84ebc-115">[Infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="84ebc-115">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="84ebc-116">[API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md) </span><span class="sxs-lookup"><span data-stu-id="84ebc-116">[BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md) </span></span>  
 [<span data-ttu-id="84ebc-117">API de BAM en una expresión de orquestación (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="84ebc-117">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)