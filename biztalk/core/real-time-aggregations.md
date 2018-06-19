---
title: Agregaciones en tiempo real | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, aggregations
- aggregations [BAM], real-time data
ms.assetid: 0ef44641-e067-4108-b318-f4373ca8fa8f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1bc335c1c53fe106c460b7dcb5a27b803db97b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269084"
---
# <a name="real-time-aggregations"></a><span data-ttu-id="6c9d7-102">Agregaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="6c9d7-102">Real-Time Aggregations</span></span>
<span data-ttu-id="6c9d7-103">En algunos casos, fragmentos específicos de agregaciones multidimensionales están tan sujetos a limitaciones variables en el tiempo que sería conveniente tenerlas disponibles en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-103">In some cases, specific slices of the multidimensional aggregations are so time-sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="6c9d7-104">Por ejemplo, una empresa vende productos perecederos y el usuario desea tener disponible en tiempo real la agregación de la cantidad de productos en diferentes fases de entrega.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-104">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="6c9d7-105">Al mismo tiempo, también desea tener otras agregaciones, tal como la edad de los clientes, pero solo a finales de mes para el análisis de inteligencia empresarial.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-105">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
 <span data-ttu-id="6c9d7-106">BAM implementa la agregación en tiempo real (ATR) como una tabla que se mantiene mediante desencadenadores de las tablas de almacenamiento de actividad.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-106">BAM implements real-time aggregation (RTA) as a table maintained by triggers from the activity storage tables.</span></span> <span data-ttu-id="6c9d7-107">En caso de que su negocio trate con pedidos, la vista ATR tendría el aspecto de la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-107">In the case when your business deals with purchase orders (PO), the RTA view may look like the example in the following figure.</span></span>  
  
 ![](../core/media/bam-realtime-aggregations.gif "bam_realtime_aggregations")  
<span data-ttu-id="6c9d7-108">Agregaciones en tiempo real de BAM</span><span class="sxs-lookup"><span data-stu-id="6c9d7-108">BAM Real-time Aggregations</span></span>  
  
 <span data-ttu-id="6c9d7-109">En esta ilustración, si se recibe un pedido nuevo de 100 $ de Redmond, BAM agrega un aporte a las celdas en la fila correspondiente de {Redmond, InProcess} al realizar una operación como `Count=Count+1` y `Amount=Amount+$100`.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-109">In this figure, if a new PO of $100 from Redmond is received, BAM adds a contribution to the cells in the corresponding row for {Redmond, InProcess} by performing an operation like `Count=Count+1` and `Amount=Amount+$100`.</span></span>  
  
 <span data-ttu-id="6c9d7-110">Más adelante, si se envía el mismo pedido, BAM quita el aporte de la fila {Redmond, InProcess} y lo agrega a la fila {Redmond, Enviado}.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-110">Later, if the same order ships, then BAM removes this contribution from the row {Redmond, InProcess} and adds it to the row {Redmond, Shipped}.</span></span>  
  
 <span data-ttu-id="6c9d7-111">BAM conserva los datos en la agregación ATR para una ventana en línea en particular y luego los elimina.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-111">BAM maintains the data inside RTA for a given online window, and then deletes it.</span></span> <span data-ttu-id="6c9d7-112">Puede configurar la ventana en línea si cambia la fila correspondiente de la tabla **bam_Metadata_RealTimeAggregations**.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-112">You can configure the online window by changing the corresponding row of the table **bam_Metadata_RealTimeAggregations**.</span></span>  
  
 <span data-ttu-id="6c9d7-113">Las siguientes instrucciones también se aplican a las agregaciones en tiempo real:</span><span class="sxs-lookup"><span data-stu-id="6c9d7-113">The following statements also apply to real-time aggregations:</span></span>  
  
-   <span data-ttu-id="6c9d7-114">Las agregaciones en tiempo real afectan de manera significativa a la velocidad con la que BAM puede escribir datos.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-114">Real-time aggregations significantly affect the speed at which BAM can write data.</span></span> <span data-ttu-id="6c9d7-115">Por lo tanto, sólo debería definir como agregación ATR los sectores más importantes de la estructura de la agregación.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-115">Thus, you should only define the most important slices of the aggregation structure as RTA.</span></span>  
  
-   <span data-ttu-id="6c9d7-116">La limitación de los niveles de dimensión de agregaciones en tiempo real es 14.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-116">The limitation of the dimension levels for real-time aggregations is 14.</span></span> <span data-ttu-id="6c9d7-117">Por ejemplo, si crea una ubicación de la dimensión de datos de estado y ciudad, cuenta como dos niveles (estado y ciudad).</span><span class="sxs-lookup"><span data-stu-id="6c9d7-117">For example, if you create a Data Dimension Location for State and City, this counts as two levels (State and City).</span></span> <span data-ttu-id="6c9d7-118">Para dimensiones de progreso, el número de niveles es la profundidad del árbol, mientras que, para las dimensiones de tiempo, es el recuento de todas las subunidades.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-118">For Progress Dimensions the number of levels is the depth of the tree, and for Time Dimensions it is the count of all sub-units.</span></span> <span data-ttu-id="6c9d7-119">Por ejemplo, una dimensión de tiempo para año, mes, día y hora contará como cuatro niveles.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-119">For example, a Time Dimension for Year, Month, Day, Hour will count as four levels.</span></span>  
  
-   <span data-ttu-id="6c9d7-120">BAM no admite agregaciones en tiempo real de tipo **Min** y **Max**.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-120">BAM does not support real-time aggregations of type **Min** and **Max**.</span></span> <span data-ttu-id="6c9d7-121">Las agregaciones que admite BAM son **recuento**, **suma**, y **Media**.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-121">The aggregations that BAM supports are **Count**, **Sum**, and **Average**.</span></span>  
  
-   <span data-ttu-id="6c9d7-122">Siempre debe crear una dimensión de tiempo para ATR y usarla en todos los sectores de datos, ya que los datos de ATR representan la antigüedad en función de la marca de tiempo del servidor y no en función de los hitos específicos del negocio.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-122">You must always create a time dimension for RTA and always use it in all data slices, because the data in RTA is aged based on the server time stamp, and not on any specific business milestone.</span></span>  
  
-   <span data-ttu-id="6c9d7-123">No defina varias ATR que usan la misma actividad de BAM .</span><span class="sxs-lookup"><span data-stu-id="6c9d7-123">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="6c9d7-124">Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-124">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
 <span data-ttu-id="6c9d7-125">Las agregaciones en tiempo real afectan de manera significativa a la velocidad con la que BAM puede escribir datos.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-125">Real-time aggregations significantly affect the speed at which BAM can write data.</span></span> <span data-ttu-id="6c9d7-126">Por lo tanto, sólo debería definir como agregación ATR los sectores más importantes de la estructura de la agregación.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-126">Thus, you should only define the most important slices of the aggregation structure as RTA.</span></span>  
  
 <span data-ttu-id="6c9d7-127">La limitación de los niveles de dimensión de agregaciones en tiempo real es 14.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-127">The limitation of the dimension levels for real-time aggregations is 14.</span></span> <span data-ttu-id="6c9d7-128">Por ejemplo, si crea una ubicación de la dimensión de datos de estado y ciudad, cuenta como dos niveles (estado y ciudad).</span><span class="sxs-lookup"><span data-stu-id="6c9d7-128">For example, if you create a Data Dimension Location for State and City, this counts as two levels (State and City).</span></span> <span data-ttu-id="6c9d7-129">Para dimensiones de progreso, el número de niveles es la profundidad del árbol, mientras que, para las dimensiones de tiempo, es el recuento de todas las subunidades.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-129">For Progress Dimensions the number of levels is the depth of the tree, and for Time Dimensions it is the count of all sub-units.</span></span> <span data-ttu-id="6c9d7-130">Por ejemplo, una dimensión de tiempo para año, mes, día y hora contará como cuatro niveles.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-130">For example, a Time Dimension for Year, Month, Day, Hour will count as four levels.</span></span>  
  
 <span data-ttu-id="6c9d7-131">BAM no admite agregaciones en tiempo real de tipo **Min** y **Max**.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-131">BAM does not support real-time aggregations of type **Min** and **Max**.</span></span> <span data-ttu-id="6c9d7-132">Las agregaciones que admite BAM son **recuento**, **suma**, y **Media**.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-132">The aggregations that BAM supports are **Count**, **Sum**, and **Average**.</span></span>  
  
 <span data-ttu-id="6c9d7-133">No defina varias ATR que usan la misma actividad de BAM .</span><span class="sxs-lookup"><span data-stu-id="6c9d7-133">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="6c9d7-134">Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="6c9d7-134">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c9d7-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c9d7-135">See Also</span></span>  
 [<span data-ttu-id="6c9d7-136">¿Qué es una agregación?</span><span class="sxs-lookup"><span data-stu-id="6c9d7-136">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)