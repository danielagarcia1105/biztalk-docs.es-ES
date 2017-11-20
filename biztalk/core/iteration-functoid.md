---
title: "El Functoid de iteración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Iteration functoids
- Greater Than or Equal To functoids
- And functoids
- Less Than or Equal To functoids
ms.assetid: 24d8911d-2282-4b07-910c-eb2e846dc1f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a491b8829f23296e77ba5a89d12985e8ccd32783
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="iteration-functoid"></a><span data-ttu-id="b3c76-102">Iteración (functoid)</span><span class="sxs-lookup"><span data-stu-id="b3c76-102">Iteration Functoid</span></span>
<span data-ttu-id="b3c76-103">El **iteración** functoid salidas el índice del registro actual en un bucle de la estructura, empezando por 1 para el primer registro, 2 para el segundo registro y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="b3c76-103">The **Iteration** functoid outputs the index of the current record in a looping structure, beginning at 1 for the first record, 2 for the second record, and so on.</span></span>  
  
 <span data-ttu-id="b3c76-104">La siguiente ilustración muestra un **iteración** functoid se combina con un **mayor o igual que** functoid, un **menor o igual a** functoid y un **y**  functoid para crear el equivalente de un **para** bucle.</span><span class="sxs-lookup"><span data-stu-id="b3c76-104">The following figure shows an **Iteration** functoid combined with a **Greater Than or Equal To** functoid, a **Less Than or Equal To** functoid, and an **And** functoid to create the equivalent of a **For** loop.</span></span>  
  
 <span data-ttu-id="b3c76-105">![Mapa que ilustra el uso del functoid de iteración](../core/media/iterationfunctoid.gif "iterationfunctoid")</span><span class="sxs-lookup"><span data-stu-id="b3c76-105">![Map illustrating the use of the iteration functoid](../core/media/iterationfunctoid.gif "iterationfunctoid")</span></span>  
<span data-ttu-id="b3c76-106">Asignación de functoid de iteración</span><span class="sxs-lookup"><span data-stu-id="b3c76-106">Iteration Functoid Map</span></span>  
  
 <span data-ttu-id="b3c76-107">Se asume que el **mayor o igual que** pruebas de functoid para valores mayores que o igual a 2 y el **menor o igual que** functoid comprueba para valores menor o igual a 4.</span><span class="sxs-lookup"><span data-stu-id="b3c76-107">Assume that the **Greater Than or Equal To** functoid tests for values greater than or equal to 2, and the **Less Than or Equal To** functoid tests for values less than or equal to 4.</span></span> <span data-ttu-id="b3c76-108">En ese caso, el **y** functoid devolverá **true** solo para los registros 2, 3 y 4.</span><span class="sxs-lookup"><span data-stu-id="b3c76-108">In that case, the **And** functoid will return **true** only for records 2, 3, and 4.</span></span> <span data-ttu-id="b3c76-109">Por lo tanto, la instancia de salida contendrá registra dos, tres y cuatro de los mensajes de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="b3c76-109">Thus, the output instance will contain records two, three, and four of the input instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c76-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3c76-110">See Also</span></span>  
 <span data-ttu-id="b3c76-111">[Cómo agregar Functoids de iteración a un mapa](../core/how-to-add-iteration-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="b3c76-111">[How to Add Iteration Functoids to a Map](../core/how-to-add-iteration-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="b3c76-112">[Functoids avanzados](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="b3c76-112">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="b3c76-113">[Functoid de índice](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="b3c76-113">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="b3c76-114">[Functoid de bucle](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="b3c76-114">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="b3c76-115">Functoid de número de registros</span><span class="sxs-lookup"><span data-stu-id="b3c76-115">Record Count Functoid</span></span>](../core/record-count-functoid.md)