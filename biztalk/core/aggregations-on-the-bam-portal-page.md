---
title: Las agregaciones en el Portal de BAM página | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], alerts
- aggregations [BAM], viewing results
- alerts, aggregations
- Aggregations page [BAM portal]
- BAM portal, aggregations
ms.assetid: 6bc1a6f2-9e9a-4db6-aaa1-188ed2f2641f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a61df22bf5d07bd1b4d955f2baf884459de52998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230068"
---
# <a name="aggregations-on-the-bam-portal-page"></a><span data-ttu-id="31c05-102">Agregaciones en la página del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="31c05-102">Aggregations on the BAM Portal Page</span></span>
<span data-ttu-id="31c05-103">Los usuarios empresariales finales y los analistas empresariales utilizan la página del portal de BAM cuando necesitan presentar datos agregados, que son resúmenes precalculados de conjuntos de datos que contienen características representativas de ese conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="31c05-103">Business end users, developers, and business analysts use the BAM portal page when they need to present aggregated data, which are precalculated summaries of a data set that convey representative characteristics of that data set.</span></span> <span data-ttu-id="31c05-104">La página Agregaciones del portal de BAM le permite mostrar datos agregados en forma de diagrama gráfico e informe de tabla dinámica existente.</span><span class="sxs-lookup"><span data-stu-id="31c05-104">The Aggregations page of the BAM portal allows you to display aggregated data in the form of a graphical chart and accompanying PivotTable report.</span></span>  
  
## <a name="the-aggregations-page"></a><span data-ttu-id="31c05-105">Agregaciones (página)</span><span class="sxs-lookup"><span data-stu-id="31c05-105">The Aggregations page</span></span>  
 <span data-ttu-id="31c05-106">La página Agregaciones muestra los resultados de una actividad que expresa de forma conjunta el estado del proceso o del negocio en general.</span><span class="sxs-lookup"><span data-stu-id="31c05-106">The Aggregations page displays the results of an activity that collectively convey the health of the process or of the overall business.</span></span> <span data-ttu-id="31c05-107">Por ejemplo, puede que un usuario desee ver un gráfico circular básico que muestre un desglose de 1.000 facturas recibidas en lo que respecta a la fase de procesamiento que se ha alcanzado con cada factura (400 en “evaluación”, 400 rechazadas, 100 pagadas y 100 en “asignación de recursos”).</span><span class="sxs-lookup"><span data-stu-id="31c05-107">For example, a user may want to see a simple pie chart that shows a breakdown of the 1,000 invoices received in terms of what stage of processing has been reached by each invoice (400 still in "evaluation," 400 rejected, 100 paid, and 100 still in "fund allocation").</span></span>  
  
### <a name="creating-alerts-for-aggregations"></a><span data-ttu-id="31c05-108">Crear alertas para agregaciones</span><span class="sxs-lookup"><span data-stu-id="31c05-108">Creating alerts for aggregations</span></span>  
 <span data-ttu-id="31c05-109">Puede crear agregaciones como base para crear una alerta (“Notifíqueme si alguna vez hay más de 500 facturas en la fase de "evaluación" del proceso”).</span><span class="sxs-lookup"><span data-stu-id="31c05-109">You can use aggregations as the basis for creating an alert ("Notify me if there are ever more than 500 invoices in the "evaluation" stage of the process).</span></span> <span data-ttu-id="31c05-110">Para ello, haga clic en cualquier celda de tabla dinámica y seleccione **establecer alerta**, o haga clic en una celda y haga clic en el **establecer alerta** situado a la derecha del informe de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="31c05-110">To do this, you right-click any PivotTable cell and select **Set Alert**, or you click a cell and click the **Set Alert** button to the right of the PivotTable report.</span></span> <span data-ttu-id="31c05-111">Para obtener más información acerca de cómo crear una alerta, consulte [cómo establecer una alerta](../core/how-to-set-an-alert.md).</span><span class="sxs-lookup"><span data-stu-id="31c05-111">For more information about creating an alert, see [How to Set an Alert](../core/how-to-set-an-alert.md).</span></span>  
  
### <a name="viewing-individual-results-of-aggregations"></a><span data-ttu-id="31c05-112">Ver resultados individuales de agregaciones</span><span class="sxs-lookup"><span data-stu-id="31c05-112">Viewing individual results of aggregations</span></span>  
 <span data-ttu-id="31c05-113">También puede seleccionar cualquier cantidad agregada (por ejemplo, 400 facturas que aún estén en “evaluación”) y ver los resultados individuales para la agregación.</span><span class="sxs-lookup"><span data-stu-id="31c05-113">You can also select any aggregate amount (for example, 400 invoices still in "evaluation") and see the individual results for the aggregation.</span></span> <span data-ttu-id="31c05-114">Acceso a los resultados individuales haciendo clic en cualquier celda de tabla dinámica y seleccione **mostrar resultados**.</span><span class="sxs-lookup"><span data-stu-id="31c05-114">You access the individual results by right-clicking any PivotTable cell and selecting **Show Results**.</span></span> <span data-ttu-id="31c05-115">Como resultado, se le envía a la página Búsqueda de actividad económica, donde la propia búsqueda se genera automáticamente y se muestran los resultados (en este ejemplo, un registro para cada una de las 400 facturas).</span><span class="sxs-lookup"><span data-stu-id="31c05-115">In response to this action, you are sent to the Activity Search page, the search itself is automatically constructed, and the results are displayed (in this example, one record for each of the 400 invoices).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31c05-116">Algunas vistas de BAM no tienen agregaciones asociadas, por lo que puede que no exista información a la que obtener acceso en función de cómo se creó la vista.</span><span class="sxs-lookup"><span data-stu-id="31c05-116">Some BAM views do not have aggregations associated with them, and so there may be no information to access depending on how the view was created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c05-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="31c05-117">See Also</span></span>  
 <span data-ttu-id="31c05-118">[Portal de BAM](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="31c05-118">[BAM Portal](../core/bam-portal.md) </span></span>  
 <span data-ttu-id="31c05-119">[Búsqueda de actividad en el Portal de BAM página](../core/activity-search-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="31c05-119">[Activity Search on the BAM Portal Page](../core/activity-search-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="31c05-120">Alert Manager en el Portal de BAM de página</span><span class="sxs-lookup"><span data-stu-id="31c05-120">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)