---
title: Dimensión de rango numérico | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], Numeric Range dimension
- Numeric Range dimension [BAM]
ms.assetid: a874ce44-b034-498f-ba58-114028dbef2c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fb6d4c21e0a207cfeec3e592569ca0f48f3badf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263404"
---
# <a name="numeric-range-dimension"></a><span data-ttu-id="9c118-102">Dimensión de rango numérico</span><span class="sxs-lookup"><span data-stu-id="9c118-102">Numeric Range Dimension</span></span>
<span data-ttu-id="9c118-103">La dimensión de rango numérico permite clasificar las agregaciones según los nombres descriptivos de distintos rangos especificados.</span><span class="sxs-lookup"><span data-stu-id="9c118-103">The numeric range dimension allows aggregations to be categorized based on friendly names of given ranges.</span></span> <span data-ttu-id="9c118-104">Por ejemplo, un analista de negocios puede definir una dimensión de rango numérico llamada Tamaño de pedido de compra con los rangos Pequeño para pedidos de entre 0 y 100 USD, Mediano para pedidos de entre 100 y 1.000 USD, y Grande para pedidos de más de 1.000 USD.</span><span class="sxs-lookup"><span data-stu-id="9c118-104">For example, a business analyst can define a numeric range dimension named PO Size with the ranges Small for purchase orders between 0-$100, Medium for purchase orders between $100 to $1,000, and Large for purchase orders exceeding $1,000.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c118-105">Si una cantidad de pedido de compra no está en los intervalos definidos, por ejemplo, una cantidad de pedido de compra es menor que 0 y, a continuación, una fila "fuera del intervalo" se crearán automáticamente por BAM para dar cabida a los datos fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="9c118-105">If a purchase order amount is not in the defined ranges, for example, a purchase order amount is less than 0, and then an "Out of range" row will be automatically created by BAM to accommodate the out-of-range data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c118-106">No puede crear dos dimensiones de rango numérico que hagan referencia al mismo alias de datos.</span><span class="sxs-lookup"><span data-stu-id="9c118-106">You cannot create two numeric range dimensions that reference the same data alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c118-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c118-107">See Also</span></span>  
 <span data-ttu-id="9c118-108">[Cómo utilizar la tabla dinámica](../core/how-to-use-the-pivottable.md) </span><span class="sxs-lookup"><span data-stu-id="9c118-108">[How to Use the PivotTable](../core/how-to-use-the-pivottable.md) </span></span>  
 <span data-ttu-id="9c118-109">[Dimensión de progreso](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="9c118-109">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="9c118-110">[Dimensión de datos](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="9c118-110">[Data Dimension](../core/data-dimension.md) </span></span>  
 <span data-ttu-id="9c118-111">[Dimensión de tiempo](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="9c118-111">[Time Dimension](../core/time-dimension.md) </span></span>  
 [<span data-ttu-id="9c118-112">Definir dimensiones</span><span class="sxs-lookup"><span data-stu-id="9c118-112">Defining Dimensions</span></span>](../core/defining-dimensions.md)