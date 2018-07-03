---
title: Las agregaciones del Portal de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, pivot tables
- BAM, data analysis
- pivot tables [BAM portal]
- BAM portal, charts
- data, analysis [BAM]
- data, OLAP cubes
- aggregations [BAM], BAM portal
- charts, BAM portal
- BAM portal, aggregations
ms.assetid: 1c689563-714b-4573-9c18-a5b0efe97fb8
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14496535f12171be1d391ebe88312a9730c36953
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986949"
---
# <a name="aggregations-in-the-bam-portal"></a><span data-ttu-id="a3b7c-102">Agregaciones en el portal de BAM</span><span class="sxs-lookup"><span data-stu-id="a3b7c-102">Aggregations in the BAM Portal</span></span>
<span data-ttu-id="a3b7c-103">Las agregaciones son tablas de datos precalculados que puede usar para realizar el procesamiento analítico con un cubo OLAP.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-103">Aggregations are tables of precalculated data you can use for analytical processing with an OLAP cube.</span></span> <span data-ttu-id="a3b7c-104">Las agregaciones facilitan la realización de consultas eficaces en un contexto de bases de datos multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-104">Aggregations facilitate the efficient querying of multidimensional databases.</span></span> <span data-ttu-id="a3b7c-105">Al crear e implementar el modelo de observación (la definición de alto nivel de los datos económicos) mediante el complemento BAM para Excel, se crean agregaciones que puede usar para evaluar rápidamente las colecciones de datos que hacen referencia a los indicadores clave de rendimiento (KPI).</span><span class="sxs-lookup"><span data-stu-id="a3b7c-105">When you create and deploy your observation model (the high-level definition of your business data) using the BAM Add-In for Excel, you create aggregations that you can use to quickly evaluate collections of data relating your Key Performance Indicators (KPIs).</span></span>  
  
## <a name="types-of-aggregations"></a><span data-ttu-id="a3b7c-106">Tipos de agregaciones</span><span class="sxs-lookup"><span data-stu-id="a3b7c-106">Types of aggregations</span></span>  
 <span data-ttu-id="a3b7c-107">Las agregaciones pueden ser programadas o en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-107">Aggregations can be either scheduled or real-time.</span></span> <span data-ttu-id="a3b7c-108">Las agregaciones programadas son cubos OLAP que representan una instantánea de sus datos económicos en el momento que determine.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-108">Scheduled aggregations are OLAP cubes, which represent a snapshot of your business data at a time you specify.</span></span> <span data-ttu-id="a3b7c-109">Las agregaciones en tiempo real permiten ver los datos económicos de su negocio en función de los factores desencadenantes que determine. De esta manera, el sistema de BAM le notifica mediante una alerta en cuanto se alcanza el indicador clave de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-109">Real-time aggregations allow a view of your business data based on trigger points that you specify, allowing the BAM system to notify you through an alert as soon as a KPI has been reached.</span></span>  
  
## <a name="pivottable-view"></a><span data-ttu-id="a3b7c-110">Vista de tabla dinámica</span><span class="sxs-lookup"><span data-stu-id="a3b7c-110">PivotTable View</span></span>  
 <span data-ttu-id="a3b7c-111">El área Vista de tabla dinámica muestra el informe de tabla dinámica que se diseña mediante el complemento de BAM para Excel.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-111">The PivotTable View area displays the PivotTable report that you design using the BAM Add-In for Excel.</span></span> <span data-ttu-id="a3b7c-112">Office Web Components permite manipular el informe de PivotTable para presentar la vista de los datos que mejor se ajuste a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-112">The Office Web Components allow you to manipulate the PivotTable report to present the view of the data that best fits your needs..</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3b7c-113">Al ver un informe de tabla dinámica, es posible que algunas filas contengan datos nulos tanto en las agregaciones en tiempo real (ATR) como en las agregaciones precalculadas (una implementación OLAP) si se han alcanzado los hitos de la actividad pero no se han utilizado en una dimensión de progreso.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-113">When viewing a PivotTable report it is possible that some rows could contain null data in both real-time aggregations (RTAs) and precalculated aggregations (an OLAP implementation) if the milestones in the activity have been reached but are not used in the progress dimension.</span></span> <span data-ttu-id="a3b7c-114">Asimismo, se pueden encontrar filas con datos nulos si se usa la dimensión de tiempo en un contexto de dimensión de progreso y está delimitada con relación a un hito, como "confirmado" en lugar de "recibido".</span><span class="sxs-lookup"><span data-stu-id="a3b7c-114">It is also possible to encounter rows with null data if the time dimension is used in the context of a progress dimension and is anchored to a milestone such as "acknowledged" instead of "received."</span></span> <span data-ttu-id="a3b7c-115">En este caso, se recibe una instancia de actividad y se desencadena el hito recibido, pero la actividad todavía no ha desencadenado el hito de confirmación y aparecerá el valor cero en la fila de la dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-115">In this case an activity instance is received and triggers the received milestone, but the activity has not yet triggered the acknowledge milestone and a zero will appear in the time dimension row.</span></span>  <span data-ttu-id="a3b7c-116">Para evitar esta situación, vincule la dimensión de tiempo con el hito recibido.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-116">To avoid this situation, link the time dimension up to the received milestone.</span></span>  
  
 <span data-ttu-id="a3b7c-117">![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")</span><span class="sxs-lookup"><span data-stu-id="a3b7c-117">![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")</span></span>  
  
 <span data-ttu-id="a3b7c-118">Recuerde estas consideraciones cuando utilice Office Web Components en el portal de BAM para modificar su informe de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-118">Keep these points in mind when using the Office Web Components in the BAM portal to modify your PivotTable report:</span></span>  
  
- <span data-ttu-id="a3b7c-119">Los informes de tabla dinámica en Excel incluyen un campo Página, donde puede ubicar una dimensión de intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-119">PivotTable reports in Excel include a Page field where you can put a time slice dimension.</span></span> <span data-ttu-id="a3b7c-120">Los Office Web Components que utiliza el portal de BAM no incluyen un campo Página.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-120">The Office Web Components used by the BAM portal do not include a Page field.</span></span> <span data-ttu-id="a3b7c-121">Si su informe de tabla dinámica de Excel usa el campo Página para cualquier dimensión, los datos de este campo no se muestran en su informe de tabla dinámica en el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-121">If your Excel PivotTable report uses the Page field for any dimensions, the data for this field is not displayed in your PivotTable report in the BAM portal.</span></span>  
  
- <span data-ttu-id="a3b7c-122">Office Web Components muestra los datos en el marco Contenido del portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-122">The Office Web Components display data in the content frame of the BAM portal.</span></span> <span data-ttu-id="a3b7c-123">Debido a las limitaciones espaciales de este marco, al agregar dimensiones desde la lista de campos al área de las columnas, podría provocar que la tabla dinámica desplazara parcial o totalmente los nombres de las dimensiones fuera de la vista.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-123">Because of the space limitations of this frame, adding dimensions from the field list to the columns area can cause the display of the PivotTable to move dimension names partly or wholly out of view.</span></span>  
  
  <span data-ttu-id="a3b7c-124">Para obtener más información acerca de las tablas dinámicas, consulte "PivotTable Terminology demystified terminología" en [ http://go.microsoft.com/fwlink/?LinkId=55416 ](http://go.microsoft.com/fwlink/?LinkId=55416).</span><span class="sxs-lookup"><span data-stu-id="a3b7c-124">For more information about PivotTables, see "PivotTable terminology demystified" at [http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416).</span></span>  
  
## <a name="chart-view"></a><span data-ttu-id="a3b7c-125">Vista de gráfico</span><span class="sxs-lookup"><span data-stu-id="a3b7c-125">Chart View</span></span>  
 <span data-ttu-id="a3b7c-126">El área Vista de diagrama muestra la agregación gráficamente.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-126">The Chart View area displays the aggregation in a graphical manner.</span></span> <span data-ttu-id="a3b7c-127">Office Web Components permite manipular los detalles de la agregación mediante la Vista de diagrama para ajustar los datos registrados según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-127">The Office Web Components allow you to manipulate the details of the aggregation through the chart view to adjust the reported data as needed.</span></span> <span data-ttu-id="a3b7c-128">Si arrastra y coloca los elementos de datos de la lista de campos de diagrama para ajustar la agregación, el informe de tabla dinámica de la agregación se actualiza automáticamente para reflejar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-128">When you adjust the aggregation by dragging and dropping data items from the Chart Field list, the PivotTable report for the aggregation is automatically updated to reflect your changes.</span></span> <span data-ttu-id="a3b7c-129">Puede obtener detalles de la tabla dinámica para crear una alerta en la vista Agregación nueva.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-129">You can drill through the PivotTable to create an alert on the new aggregation view.</span></span>  
  
 <span data-ttu-id="a3b7c-130">![](../core/media/aggregationchartview.gif "AggregationChartView")</span><span class="sxs-lookup"><span data-stu-id="a3b7c-130">![](../core/media/aggregationchartview.gif "AggregationChartView")</span></span>  
  
## <a name="more"></a><span data-ttu-id="a3b7c-131">Más</span><span class="sxs-lookup"><span data-stu-id="a3b7c-131">More</span></span>  
  
-   [<span data-ttu-id="a3b7c-132">Cómo establecer una alerta</span><span class="sxs-lookup"><span data-stu-id="a3b7c-132">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="a3b7c-133">Cómo ver los resultados de una búsqueda de actividad</span><span class="sxs-lookup"><span data-stu-id="a3b7c-133">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
-   [<span data-ttu-id="a3b7c-134">Cómo modificar una agregación</span><span class="sxs-lookup"><span data-stu-id="a3b7c-134">How to Modify an Aggregation</span></span>](../core/how-to-modify-an-aggregation.md)  
  
## <a name="see-also"></a><span data-ttu-id="a3b7c-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3b7c-135">See Also</span></span>  
 [<span data-ttu-id="a3b7c-136">¿Qué es una agregación?</span><span class="sxs-lookup"><span data-stu-id="a3b7c-136">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)