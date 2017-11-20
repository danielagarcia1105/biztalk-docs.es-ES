---
title: Anidar los registros posicionales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e205e9d-f740-4177-b45a-5e1baadae99a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c278d3ac794c560d8cd886605c1d04c097793564
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="nested-positional-records"></a><span data-ttu-id="8b869-102">Registros posicionales anidados</span><span class="sxs-lookup"><span data-stu-id="8b869-102">Nested Positional Records</span></span>
<span data-ttu-id="8b869-103">Se permiten registros posicionales anidados si la **Max Occurs** propiedad de los registros secundarios está establecida en un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="8b869-103">Nested positional records are allowed if the **Max Occurs** property of child records is set to a positive integer.</span></span> <span data-ttu-id="8b869-104">El cálculo automático del campo podrá controlar la nueva profundidad.</span><span class="sxs-lookup"><span data-stu-id="8b869-104">Field autocalculation should be able to handle the new depth.</span></span> <span data-ttu-id="8b869-105">Sin embargo, existe una modificación en cuanto al modo en que éste se comporta.</span><span class="sxs-lookup"><span data-stu-id="8b869-105">However, there is a modification to the way this behaves.</span></span> <span data-ttu-id="8b869-106">En concreto, como se pueden usar delimitadores nulos, el cálculo automático de las posiciones de los campos solo funcionará si se cumple una de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="8b869-106">Specifically, because of the possibility for null delimiters, autocalculation of field positions will function only if one of the following conditions is met:</span></span>  
  
-   <span data-ttu-id="8b869-107">El nodo seleccionado tiene un nodo primario que está delimitado por infijos.</span><span class="sxs-lookup"><span data-stu-id="8b869-107">The selected node has a parent that is infix delimited.</span></span>  
  
-   <span data-ttu-id="8b869-108">El nodo seleccionado tiene una posición inicial especificada.</span><span class="sxs-lookup"><span data-stu-id="8b869-108">The selected node has a specified starting position.</span></span>  
  
 <span data-ttu-id="8b869-109">Tenga en cuenta que hay una diferencia entre los registros posicionales anidados y los registros posicionales cuyo elemento primario es un contenedor delimitado en el que el delimitador es un valor null.</span><span class="sxs-lookup"><span data-stu-id="8b869-109">Note that there is a distinction between nested positional records and positional records whose parent is a delimited container where the delimiter is null.</span></span> <span data-ttu-id="8b869-110">Para que las estructuras sean verdaderamente de tipo posicional anidado, no debe existir ninguna ambigüedad al determinar la longitud.</span><span class="sxs-lookup"><span data-stu-id="8b869-110">For structures to be truly nested positionally, there must not be any ambiguity in determining their length.</span></span> <span data-ttu-id="8b869-111">Por ejemplo, un nodo de bucle delimitado puede contener un registro posicional de repetición que aparezca de 0 a N veces.</span><span class="sxs-lookup"><span data-stu-id="8b869-111">For example, a delimited loop node can contain a repeating positional record that occurs 0 to N times.</span></span> <span data-ttu-id="8b869-112">Sin embargo, para que ese nodo de bucle sea en sí mismo posicional y probablemente también para que contenga campos como pares en el registro posicional de repetición, la aparición del registro posicional de repetición debe ser determinista (un entero positivo).</span><span class="sxs-lookup"><span data-stu-id="8b869-112">However, for that loop node itself to be positional, and possibly also contain fields as peers to the repeating positional record, the occurrence of the repeating positional record must be deterministic (a positive integer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b869-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b869-113">See Also</span></span>  
 [<span data-ttu-id="8b869-114">Consideraciones del registro posicional</span><span class="sxs-lookup"><span data-stu-id="8b869-114">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)