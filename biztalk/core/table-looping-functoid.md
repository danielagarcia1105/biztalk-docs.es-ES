---
title: Functoid de bucle de tabla | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Looping functoids, about Table Looping functoids
ms.assetid: 6189a789-afe7-4e72-a778-2b0374db8f69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c5e5f2967fb48bfe896c26246db1630266812f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="table-looping-functoid"></a><span data-ttu-id="410b6-102">Functoid de bucle de tabla</span><span class="sxs-lookup"><span data-stu-id="410b6-102">Table Looping Functoid</span></span>
<span data-ttu-id="410b6-103">El **bucle de tabla** functoid le permite crear una tabla de valores de salida que se usará al crear el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="410b6-103">The **Table Looping** functoid enables you to create a table of output values to use in creating the output instance message.</span></span> <span data-ttu-id="410b6-104">Los datos de la tabla pueden constar de vínculos y constantes.</span><span class="sxs-lookup"><span data-stu-id="410b6-104">The data in the table can consist of links and constants.</span></span> <span data-ttu-id="410b6-105">El primer parámetro de entrada a la **bucle de tabla** functoid configura el ámbito o cuántos bucles realizará el registro.</span><span class="sxs-lookup"><span data-stu-id="410b6-105">The first input parameter to the **Table Looping** functoid configures the scope, or how many times the records will loop.</span></span> <span data-ttu-id="410b6-106">El segundo parámetro de entrada el **bucle de tabla** functoid determina cuántas columnas se encuentran en la tabla y las restantes entradas definen posibles valores de celdas de la tabla, sin ningún orden determinado.</span><span class="sxs-lookup"><span data-stu-id="410b6-106">The second input parameter for the **Table Looping** functoid determines how many columns are in the table, and the remaining inputs define possible cell values for the table, in no particular order.</span></span> <span data-ttu-id="410b6-107">Para obtener más información sobre cómo trabajar con estas propiedades, vea [configuración de bucle de Table-Driven](../core/table-driven-looping-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="410b6-107">For more information about working with these properties, see [Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md).</span></span> <span data-ttu-id="410b6-108">Consulte también [Table-Driven bucle ejemplo](../core/table-driven-looping-example.md).</span><span class="sxs-lookup"><span data-stu-id="410b6-108">Also see [Table-Driven Looping Example](../core/table-driven-looping-example.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="410b6-109">El **bucle de tabla** functoid se repite con el registro de bucle está conectado a.</span><span class="sxs-lookup"><span data-stu-id="410b6-109">The **Table Looping** functoid repeats with the looping record it is connected to.</span></span> <span data-ttu-id="410b6-110">Dentro de cada iteración, recorre una vez cada fila en la cuadrícula de bucle de tabla y produce múltiples bucles de salida.</span><span class="sxs-lookup"><span data-stu-id="410b6-110">Within each iteration, it loops once per row in the table looping grid, producing multiple output loops.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="410b6-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="410b6-111">See Also</span></span>  
 <span data-ttu-id="410b6-112">[Functoid de Extractor de tablas](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="410b6-112">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="410b6-113">[Cómo agregar el bucle de tabla y Functoids de Extractor de tabla a un mapa](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="410b6-113">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="410b6-114">[Functoids avanzados](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="410b6-114">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="410b6-115">[Functoid de índice](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="410b6-115">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="410b6-116">[Functoid de iteración](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="410b6-116">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="410b6-117">[Functoid de bucle](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="410b6-117">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="410b6-118">Functoid de número de registros</span><span class="sxs-lookup"><span data-stu-id="410b6-118">Record Count Functoid</span></span>](../core/record-count-functoid.md)