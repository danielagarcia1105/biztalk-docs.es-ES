---
title: Nodos opcionales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, BizTalk Mapper
- maps, testing
- testing, maps
- BizTalk Mapper, testing
- maps, optional nodes
ms.assetid: 7dcd203e-fb23-438a-87d1-42323acd87cc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96cf7d8b22ee8469a7e52dba7bbad899209c5274
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="optional-nodes"></a><span data-ttu-id="e1b3c-102">Nodos opcionales</span><span class="sxs-lookup"><span data-stu-id="e1b3c-102">Optional Nodes</span></span>
<span data-ttu-id="e1b3c-103">La utilización de nodos opcionales generará una advertencia al probar la asignación.</span><span class="sxs-lookup"><span data-stu-id="e1b3c-103">Using optional nodes will produce a warning when you test your map.</span></span> <span data-ttu-id="e1b3c-104">Existen dos condiciones en las que un nodo de origen puede considerarse opcional:</span><span class="sxs-lookup"><span data-stu-id="e1b3c-104">There are two conditions in which a source node may be considered optional:</span></span>  
  
-   <span data-ttu-id="e1b3c-105">El registro o el campo reales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="e1b3c-105">The actual record or field is optional.</span></span>  
  
-   <span data-ttu-id="e1b3c-106">El registro o el campo de origen son necesarios, pero los primarios o más altos en la jerarquía son opcionales.</span><span class="sxs-lookup"><span data-stu-id="e1b3c-106">The source record or field is required, but a parent, grandparent, and farther up the hierarchy is optional.</span></span>  
  
 <span data-ttu-id="e1b3c-107">Puede encontrarse con esta situación cuando tenga registros y campos en un esquema de origen que sean opcionales, pero el esquema de destino requiera los registros o campos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e1b3c-107">You may have situations when you have records and fields in a source schema that are optional, but the destination schema requires the corresponding records or fields.</span></span>  
  
 <span data-ttu-id="e1b3c-108">En las dos posibles condiciones, probar la asignación genera una advertencia en el **salida** ventana.</span><span class="sxs-lookup"><span data-stu-id="e1b3c-108">In both of the possible conditions, testing your map produces a warning in the **Output** window.</span></span> <span data-ttu-id="e1b3c-109">Además, los datos de salida no incluirán el nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="e1b3c-109">In addition, the output data will not include the target node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1b3c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1b3c-110">See Also</span></span>  
 [<span data-ttu-id="e1b3c-111">Probar las asignaciones</span><span class="sxs-lookup"><span data-stu-id="e1b3c-111">Testing Maps</span></span>](../core/testing-maps.md)