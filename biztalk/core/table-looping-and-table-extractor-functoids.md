---
title: Bucle de tabla y Functoids de Extractor de tabla | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2907aada-f11a-485c-85c8-03092803ccf7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02d4433255ac00d51c88b45bd1a2b5205bd1c735
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="table-looping-and-table-extractor-functoids"></a><span data-ttu-id="1c0bd-102">Bucle de tabla y Functoids de Extractor de tabla</span><span class="sxs-lookup"><span data-stu-id="1c0bd-102">Table Looping and Table Extractor Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="1c0bd-103">Información general</span><span class="sxs-lookup"><span data-stu-id="1c0bd-103">Overview</span></span>
<span data-ttu-id="1c0bd-104">En una asignación, generalmente se tiene una estructura en el mensaje de instancia de salida para cada estructura del mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="1c0bd-104">In a map, you commonly have one structure in the output instance message for each structure in the input instance message.</span></span> <span data-ttu-id="1c0bd-105">No obstante, hay ocasiones en las que necesita que una estructura de instancia de entrada produzca múltiples estructuras de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="1c0bd-105">However, there are cases when you need an input instance structure to produce multiple output instance structures.</span></span> <span data-ttu-id="1c0bd-106">El bucle controlado por tablas permite crear asignaciones que generen esa serie de estructuras.</span><span class="sxs-lookup"><span data-stu-id="1c0bd-106">Table-driven looping enables you to create maps generating such multiple structures.</span></span>  
  
 <span data-ttu-id="1c0bd-107">Usos de bucle controlado por tablas el **bucle de tabla** functoid y **Extractor de tablas** functoid.</span><span class="sxs-lookup"><span data-stu-id="1c0bd-107">Table-driven looping uses the **Table Looping** functoid and the **Table Extractor** functoid.</span></span> <span data-ttu-id="1c0bd-108">El **bucle de tabla** el functoid tiene una tabla interna configurable.</span><span class="sxs-lookup"><span data-stu-id="1c0bd-108">The **Table Looping** functoid has an internal table you configure.</span></span> <span data-ttu-id="1c0bd-109">Para cada entrada de registro o campo, el **bucle de tabla** functoid genera las filas de la tabla, de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="1c0bd-109">For each input record or field, the **Table Looping** functoid outputs the rows of the table, one at a time.</span></span> <span data-ttu-id="1c0bd-110">Por ejemplo, si hay diez registros en el mensaje de instancia de entrada y dos filas en la tabla interna de la **bucle de tabla**, el functoid genera un total de veinte filas, dos para cada uno de los diez registros.</span><span class="sxs-lookup"><span data-stu-id="1c0bd-110">For example, if there are ten records in the input instance message and two rows in the internal table of the **Table Looping**, the functoid outputs a total of twenty rows, two for each of the ten records.</span></span> <span data-ttu-id="1c0bd-111">El **Extractor de tablas** functoid extrae el elemento deseado de una fila y lo pasa al mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="1c0bd-111">The **Table Extractor** functoid extracts the desired item from a row and passes it on to the output instance message.</span></span>  
  
 <span data-ttu-id="1c0bd-112">Para obtener más información, consulte el **referencia de Functoid de bucle de tabla** y **referencia de Functoid de Extractor de tabla** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="1c0bd-112">For more details, see the **Table Looping Functoid Reference** and **Table Extractor Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="1c0bd-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1c0bd-113">Next steps</span></span>
  
-   [<span data-ttu-id="1c0bd-114">Functoid de bucle de tabla</span><span class="sxs-lookup"><span data-stu-id="1c0bd-114">Table Looping Functoid</span></span>](../core/table-looping-functoid.md)  
  
-   [<span data-ttu-id="1c0bd-115">Functoid de Extractor de tablas</span><span class="sxs-lookup"><span data-stu-id="1c0bd-115">Table Extractor Functoid</span></span>](../core/table-extractor-functoid.md)  
  
-   [<span data-ttu-id="1c0bd-116">Configuración de bucle controlado por tablas</span><span class="sxs-lookup"><span data-stu-id="1c0bd-116">Table-Driven Looping Configuration</span></span>](../core/table-driven-looping-configuration.md)  
  
-   [<span data-ttu-id="1c0bd-117">Ejemplo de bucle controlado por tablas</span><span class="sxs-lookup"><span data-stu-id="1c0bd-117">Table-Driven Looping Example</span></span>](../core/table-driven-looping-example.md)