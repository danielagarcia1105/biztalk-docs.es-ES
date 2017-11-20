---
title: Bucle condicional | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Looping functoids, conditional
- Equal functoids
- maps, conditional looping
ms.assetid: eb16efb8-b12c-47d6-afc9-579fc85ea59c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5452f6b8768442b95ac6bddde0e84ba07f68c85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="conditional-looping"></a><span data-ttu-id="03790-102">Bucle condicional</span><span class="sxs-lookup"><span data-stu-id="03790-102">Conditional Looping</span></span>
<span data-ttu-id="03790-103">Puede agregar condiciones a una **bucle** functoid vinculándose a la salida de un **bucle** functoid y un **lógicos** functoid en el mismo registro de destino.</span><span class="sxs-lookup"><span data-stu-id="03790-103">You can add conditions to a **Looping** functoid by linking the output of a **Looping** functoid and a **Logical** functoid to the same destination record.</span></span> <span data-ttu-id="03790-104">Los registros de destino solo se crean cuando se cumple la condición lógica.</span><span class="sxs-lookup"><span data-stu-id="03790-104">The destination records are created only when the logical condition is met.</span></span>  
  
## <a name="conditional-looping-map"></a><span data-ttu-id="03790-105">Asignación de bucle condicional</span><span class="sxs-lookup"><span data-stu-id="03790-105">Conditional Looping Map</span></span>  
 <span data-ttu-id="03790-106">![Mapa que ilustra el functoid de bucle condicional. ] (../core/media/loopingconditionalfunctoid.gif "loopingconditionalfunctoid")</span><span class="sxs-lookup"><span data-stu-id="03790-106">![Map illustrating conditional looping functoid.](../core/media/loopingconditionalfunctoid.gif "loopingconditionalfunctoid")</span></span>  
  
 <span data-ttu-id="03790-107">En la ilustración anterior, la primera **igual** functoid compara el **nombre** campo **FoodSurvey** con "Wendy Wheeler".</span><span class="sxs-lookup"><span data-stu-id="03790-107">In the preceding figure, the first **Equal** functoid compares the **Name** field under **FoodSurvey** to "Wendy Wheeler".</span></span> <span data-ttu-id="03790-108">El segundo **igual** functoid compara el **nombre** campo **FlowerSurvey** con "Kelly Focht".</span><span class="sxs-lookup"><span data-stu-id="03790-108">The second **Equal** functoid compares the **Name** field under **FlowerSurvey** to "Kelly Focht".</span></span> <span data-ttu-id="03790-109">Por lo tanto, la asignación crea el destino **dirección** registros solo para los dos nombres.</span><span class="sxs-lookup"><span data-stu-id="03790-109">Thus, the map creates the destination **Address** records only for the two names.</span></span> <span data-ttu-id="03790-110">Con los datos de ejemplo de la **bucle** ejemplo de functoid, podría aparecer el mensaje de instancia de salida como sigue.</span><span class="sxs-lookup"><span data-stu-id="03790-110">Using the sample data from the **Looping** functoid example, the output instance message would appear as follows.</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://ConditionalLoop.MasterAddresses">  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290">  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406">  
</ns0:MasterAddresses>  
```  
  
## <a name="see-also"></a><span data-ttu-id="03790-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="03790-111">See Also</span></span>  
 <span data-ttu-id="03790-112">[Cómo agregar Functoids a una asignación de bucle](../core/how-to-add-looping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="03790-112">[How to Add Looping Functoids to a Map](../core/how-to-add-looping-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="03790-113">[Functoids avanzados](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="03790-113">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="03790-114">[Functoid de índice](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="03790-114">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="03790-115">[Functoid de iteración](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="03790-115">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="03790-116">[Functoid de bucle](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="03790-116">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="03790-117">Functoid de número de registros</span><span class="sxs-lookup"><span data-stu-id="03790-117">Record Count Functoid</span></span>](../core/record-count-functoid.md)