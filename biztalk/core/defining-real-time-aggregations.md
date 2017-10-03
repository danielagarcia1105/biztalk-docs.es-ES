---
title: "Definición de agregaciones en tiempo real | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- real-time data, aggregating
- aggregations [BAM], real-time data
ms.assetid: cb3d7124-1663-4af2-9540-4171cc51568a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2b2df32149f67a002a5a6281b6f1abd848523a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="defining-real-time-aggregations"></a><span data-ttu-id="72b7f-102">Definición de agregaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="72b7f-102">Defining Real-Time Aggregations</span></span>
<span data-ttu-id="72b7f-103">A veces, las agregaciones multidimensionales tienen sectores con tales limitaciones temporales que conviene tenerlos disponibles en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="72b7f-103">In some cases, specific slices of the multi-dimensional aggregations are so time- sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="72b7f-104">Por ejemplo, una empresa vende productos perecederos y el usuario desea tener disponible en tiempo real la agregación de la cantidad de productos en diferentes fases de entrega.</span><span class="sxs-lookup"><span data-stu-id="72b7f-104">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="72b7f-105">Al mismo tiempo, también desea tener otras agregaciones, tal como la edad de los clientes, pero solo a finales de mes para el análisis de inteligencia empresarial.</span><span class="sxs-lookup"><span data-stu-id="72b7f-105">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
-   <span data-ttu-id="72b7f-106">Mediante el **tabla dinámica** barra de herramientas, marque la tabla dinámica seleccionada como una agregación en tiempo real (ATR), si es aplicable.</span><span class="sxs-lookup"><span data-stu-id="72b7f-106">Using the **PivotTable** toolbar, mark the selected PivotTable as a real-time aggregation (RTA), if applicable.</span></span> <span data-ttu-id="72b7f-107">El tipo de datos de la tabla dinámica debe determinar si necesita verla en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="72b7f-107">The type of data contained in the PivotTable should determine whether it needs to be viewed in real time.</span></span> <span data-ttu-id="72b7f-108">Por ejemplo, si un informe somete a seguimiento los pedidos por web cada hora, puede ser necesario verlo en tiempo real. En cambio, esto no será necesario para un informe que somete a seguimiento los totales de ventas diarios.</span><span class="sxs-lookup"><span data-stu-id="72b7f-108">For example, a report that tracks hourly Web orders might need to viewed in real time, whereas a report that tracks daily sales totals would not be viewed in real time.</span></span>  
  
     ![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")  
<span data-ttu-id="72b7f-109">Botón ATR</span><span class="sxs-lookup"><span data-stu-id="72b7f-109">RTA button</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="72b7f-110">No defina varias ATR que usan la misma actividad de BAM .</span><span class="sxs-lookup"><span data-stu-id="72b7f-110">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="72b7f-111">Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="72b7f-111">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
 <span data-ttu-id="72b7f-112">Para obtener más información acerca de las tablas dinámicas, consulte la Ayuda en pantalla de Excel.</span><span class="sxs-lookup"><span data-stu-id="72b7f-112">For more information about Pivot tables, see Excel online help.</span></span> <span data-ttu-id="72b7f-113">Una vez creada la tabla dinámica, podrá ver sus datos de BAM activos.</span><span class="sxs-lookup"><span data-stu-id="72b7f-113">After you create your Pivot table, you can view your live BAM data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b7f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="72b7f-114">See Also</span></span>  
 <span data-ttu-id="72b7f-115">[Ver datos de BAM en vivo](../core/viewing-live-bam-data.md) </span><span class="sxs-lookup"><span data-stu-id="72b7f-115">[Viewing Live BAM Data](../core/viewing-live-bam-data.md) </span></span>  
 <span data-ttu-id="72b7f-116">[Dimensión de progreso](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="72b7f-116">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="72b7f-117">[Dimensión de datos](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="72b7f-117">[Data Dimension](../core/data-dimension.md) </span></span>  
 <span data-ttu-id="72b7f-118">[Dimensión de tiempo](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="72b7f-118">[Time Dimension](../core/time-dimension.md) </span></span>  
 <span data-ttu-id="72b7f-119">[Dimensión de rango numérico](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="72b7f-119">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 [<span data-ttu-id="72b7f-120">Definir dimensiones</span><span class="sxs-lookup"><span data-stu-id="72b7f-120">Defining Dimensions</span></span>](../core/defining-dimensions.md)