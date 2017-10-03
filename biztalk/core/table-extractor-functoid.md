---
title: Functoid de Extractor de tabla | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Extractor functoids
- Table Extractor functoids, about Table Extractor functoids
ms.assetid: cb5f6f15-f4e1-46d3-846e-6e2664699b62
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 837762dcf1bd0814494f05712eb7d616cdfa7180
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="table-extractor-functoid"></a><span data-ttu-id="ba452-102">Functoid de Extractor de tablas</span><span class="sxs-lookup"><span data-stu-id="ba452-102">Table Extractor Functoid</span></span>
<span data-ttu-id="ba452-103">El **Extractor de tablas** functoid determina qué datos se deben extraer de cada fila de la cuadrícula de bucle como el **bucle de tabla** functoid presenta las filas.</span><span class="sxs-lookup"><span data-stu-id="ba452-103">The **Table Extractor** functoid determines which data to extract from each row of the looping grid as the **Table Looping** functoid presents the rows.</span></span> <span data-ttu-id="ba452-104">Se necesita una **Extractor de tablas** functoid para cada campo de salida.</span><span class="sxs-lookup"><span data-stu-id="ba452-104">You need one **Table Extractor** functoid for each output field.</span></span> <span data-ttu-id="ba452-105">Por ejemplo, suponga que el mensaje de instancia de entrada tuviera una dirección en un formato único, pero el mensaje de instancia de salida necesitara la dirección en dos formatos y cada uno de ellos etiquetado.</span><span class="sxs-lookup"><span data-stu-id="ba452-105">For example, suppose your input instance message had an address in a single format, but your output instance message needed the address in two formats with each format tagged.</span></span> <span data-ttu-id="ba452-106">A continuación, debe generar un **Extractor de tablas** functoid para la etiqueta y para cada elemento de la dirección.</span><span class="sxs-lookup"><span data-stu-id="ba452-106">Then you would need a **Table Extractor** functoid for the tag and for each element of the address.</span></span> <span data-ttu-id="ba452-107">Para obtener más información acerca de cómo configurar el **Extractor de tablas** functoid, consulte [configuración de bucle de Table-Driven](../core/table-driven-looping-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="ba452-107">For more information about configuring the **Table Extractor** functoid, see [Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md).</span></span> <span data-ttu-id="ba452-108">Consulte también [Table-Driven bucle ejemplo](../core/table-driven-looping-example.md).</span><span class="sxs-lookup"><span data-stu-id="ba452-108">Also see [Table-Driven Looping Example](../core/table-driven-looping-example.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba452-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba452-109">See Also</span></span>  
 <span data-ttu-id="ba452-110">[Functoid de bucle de tabla](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="ba452-110">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="ba452-111">[Cómo agregar el bucle de tabla y Functoids de Extractor de tabla a un mapa](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="ba452-111">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="ba452-112">[Functoids avanzados](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="ba452-112">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="ba452-113">[Functoid de índice](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="ba452-113">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="ba452-114">[Functoid de iteración](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="ba452-114">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="ba452-115">[Functoid de bucle](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="ba452-115">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="ba452-116">Functoid de número de registros</span><span class="sxs-lookup"><span data-stu-id="ba452-116">Record Count Functoid</span></span>](../core/record-count-functoid.md)