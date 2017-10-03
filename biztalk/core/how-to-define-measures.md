---
title: "Cómo definir medidas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating measures
- aggregations [BAM], measures
- BAM views, measures
ms.assetid: fd3dfe6b-cc63-4306-8aad-a9d2a9af01e8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56fea736baaec3f259fc8831a7256e28eaabc9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-define-measures"></a><span data-ttu-id="4af66-102">Cómo definir medidas</span><span class="sxs-lookup"><span data-stu-id="4af66-102">How to Define Measures</span></span>
<span data-ttu-id="4af66-103">Una medida define cómo se calcula una actividad.</span><span class="sxs-lookup"><span data-stu-id="4af66-103">A measure defines how an activity is calculated.</span></span> <span data-ttu-id="4af66-104">Al crear una vista de BAM puede definir una medida para la actividad en ella.</span><span class="sxs-lookup"><span data-stu-id="4af66-104">When you create a BAM view you can define a measure for the activity in the view.</span></span> <span data-ttu-id="4af66-105">Por ejemplo, para una actividad de pedido puede calcular la cantidad total del pedido, el número de pedidos, la cantidad promedio de los pedidos, etc.</span><span class="sxs-lookup"><span data-stu-id="4af66-105">For example, for a purchase order activity, you can calculate the total PO amount, the number of POs, the average PO amount, and so on.</span></span>  
  
 <span data-ttu-id="4af66-106">Las medidas de BAM admitidas incluyen:</span><span class="sxs-lookup"><span data-stu-id="4af66-106">BAM supported measures include:</span></span>  
  
-   <span data-ttu-id="4af66-107">Sum</span><span class="sxs-lookup"><span data-stu-id="4af66-107">Sum</span></span>  
  
-   <span data-ttu-id="4af66-108">Count</span><span class="sxs-lookup"><span data-stu-id="4af66-108">Count</span></span>  
  
-   <span data-ttu-id="4af66-109">Promedio</span><span class="sxs-lookup"><span data-stu-id="4af66-109">Average</span></span>  
  
-   <span data-ttu-id="4af66-110">Mínima</span><span class="sxs-lookup"><span data-stu-id="4af66-110">Minimum</span></span>  
  
-   <span data-ttu-id="4af66-111">Máximo</span><span class="sxs-lookup"><span data-stu-id="4af66-111">Maximum</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4af66-112">Por el momento la característica Agregación en tiempo real (ATR) de BAM no admite las medidas Mínimo ni Máximo.</span><span class="sxs-lookup"><span data-stu-id="4af66-112">The BAM Real-time Aggregation (RTA) feature doesn't currently support Minimum and Maximum measures.</span></span> <span data-ttu-id="4af66-113">Puede utilizarlas, pero cuando marque la tabla dinámica de Excel como una ATR, Mínimo y Máximo se omitirán.</span><span class="sxs-lookup"><span data-stu-id="4af66-113">You can use those measures, but when you mark the Excel pivot table as an RTA, Minimum and Maximum are ignored.</span></span>  
  
### <a name="to-add-new-measures"></a><span data-ttu-id="4af66-114">Para agregar nuevas medidas</span><span class="sxs-lookup"><span data-stu-id="4af66-114">To add new measures</span></span>  
  
1.  <span data-ttu-id="4af66-115">En el Asistente para la vista de BAM, haga clic en **siguiente** hasta que vea el **nueva vista de SAE: agregación dimensiones y medidas** página.</span><span class="sxs-lookup"><span data-stu-id="4af66-115">In the BAM View wizard, click **Next** until you see the **New BAM View: Aggregation Dimensions and Measures** page.</span></span> <span data-ttu-id="4af66-116">Haga clic en **nuevas medidas**.</span><span class="sxs-lookup"><span data-stu-id="4af66-116">Click **New Measures**.</span></span>  
  
2.  <span data-ttu-id="4af66-117">Escriba un nombre para la medida.</span><span class="sxs-lookup"><span data-stu-id="4af66-117">Type a name for your measure.</span></span>  
  
3.  <span data-ttu-id="4af66-118">En la lista desplegable, seleccione la **elemento de datos Base**.</span><span class="sxs-lookup"><span data-stu-id="4af66-118">From the drop-down list, select the **Base data item**.</span></span>  
  
4.  <span data-ttu-id="4af66-119">Haga clic en el **tipo de agregación** que desea usar.</span><span class="sxs-lookup"><span data-stu-id="4af66-119">Click the **Aggregation type** you want to use.</span></span> <span data-ttu-id="4af66-120">Las opciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="4af66-120">The choices include:</span></span>  
  
    -   <span data-ttu-id="4af66-121">Sum</span><span class="sxs-lookup"><span data-stu-id="4af66-121">Sum</span></span>  
  
    -   <span data-ttu-id="4af66-122">Count</span><span class="sxs-lookup"><span data-stu-id="4af66-122">Count</span></span>  
  
    -   <span data-ttu-id="4af66-123">Promedio</span><span class="sxs-lookup"><span data-stu-id="4af66-123">Average</span></span>  
  
    -   <span data-ttu-id="4af66-124">Mínimo (no admitido para ATR).</span><span class="sxs-lookup"><span data-stu-id="4af66-124">Minimum (not supported for RTAs).</span></span>  
  
    -   <span data-ttu-id="4af66-125">Máximo (no admitido para ATR).</span><span class="sxs-lookup"><span data-stu-id="4af66-125">Maximum (not supported for RTAs)</span></span>  
  
5.  <span data-ttu-id="4af66-126">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4af66-126">Click **OK**.</span></span> <span data-ttu-id="4af66-127">Cuando termine de agregar dimensiones y medidas, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4af66-127">When you finish adding dimensions and measures, click **Next**.</span></span>  
  
6.  <span data-ttu-id="4af66-128">En el **nueva vista de SAE: resumen** página, revise la información relacionada con la nueva vista y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4af66-128">On the **New BAM View: Summary** page, review the information regarding your new view, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="4af66-129">Haga clic en **finalizar** para completar la **Asistente para vistas de BAM**.</span><span class="sxs-lookup"><span data-stu-id="4af66-129">Click **Finish** to complete the **BAM View Wizard**.</span></span>  
  
 <span data-ttu-id="4af66-130">Si agregó medidas y dimensiones a su vista de BAM, puede agregar esos elementos a la tabla dinámica en el libro de trabajo de Excel.</span><span class="sxs-lookup"><span data-stu-id="4af66-130">If you added measures and dimensions to your BAM view, you can add those items to the PivotTable in the Excel workbook.</span></span> <span data-ttu-id="4af66-131">Para obtener más información acerca de cómo crear una tabla dinámica, consulte [cómo utilizar la tabla dinámica](../core/how-to-use-the-pivottable.md).</span><span class="sxs-lookup"><span data-stu-id="4af66-131">For more information about creating a PivotTable, see [How to Use the PivotTable](../core/how-to-use-the-pivottable.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af66-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="4af66-132">See Also</span></span>  
 [<span data-ttu-id="4af66-133">Definir dimensiones</span><span class="sxs-lookup"><span data-stu-id="4af66-133">Defining Dimensions</span></span>](../core/defining-dimensions.md)