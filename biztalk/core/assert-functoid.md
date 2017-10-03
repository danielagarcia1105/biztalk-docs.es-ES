---
title: "Functoid de aserción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e91dac06-f909-4fb2-8c87-828a3dfe2c27
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03237c27e0e35642be197b549c8b0102d9350702
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="assert-functoid"></a><span data-ttu-id="3fdb5-102">Functoid de aserción</span><span class="sxs-lookup"><span data-stu-id="3fdb5-102">Assert Functoid</span></span>

## <a name="overview"></a><span data-ttu-id="3fdb5-103">Información general</span><span class="sxs-lookup"><span data-stu-id="3fdb5-103">Overview</span></span>
<span data-ttu-id="3fdb5-104">El **Assert** functoid muestra un valor de cadena o produce una excepción basada en un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="3fdb5-104">The **Assert** functoid either outputs a string value or throws an exception based on a Boolean value.</span></span> <span data-ttu-id="3fdb5-105">Si este functoid se combina con uno o varios de los **lógicos** functoids, puede probar eficazmente suposiciones acerca de las condiciones de la asignación.</span><span class="sxs-lookup"><span data-stu-id="3fdb5-105">If you combine this functoid with one or more of the **Logical** functoids, you can effectively test assumptions about conditions in your map.</span></span> <span data-ttu-id="3fdb5-106">Por ejemplo, si tiene un mapa que espera cantidades de pedido de compra nunca a superar un umbral determinado, puede probar el valor de orden de compra mediante el **Greater Than** functoid y, a continuación, conéctese a la **Assert**functoid.</span><span class="sxs-lookup"><span data-stu-id="3fdb5-106">For example, if you have a map that expects purchase order amounts never to exceed a certain threshold, you can test the purchase order value by using the **Greater Than** functoid and then connect it to the **Assert** functoid.</span></span> <span data-ttu-id="3fdb5-107">Si el functoid lógico devuelve **True**, **Assert** functoid iniciará una excepción utilizando una cadena que proporcione.</span><span class="sxs-lookup"><span data-stu-id="3fdb5-107">If the logical functoid returns **True**, the **Assert** functoid will throw an exception using a string you provide.</span></span>  
  
 <span data-ttu-id="3fdb5-108">![Functoid de aserción](../core/media/assertfunctoid.gif "AssertFunctoid")</span><span class="sxs-lookup"><span data-stu-id="3fdb5-108">![Assert Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fdb5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fdb5-109">See Also</span></span>  
 <span data-ttu-id="3fdb5-110">**Referencia de Functoid de aserción** y **referencia a Functoids lógicos**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="3fdb5-110">**Assert Functoid Reference** and **Logical Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>