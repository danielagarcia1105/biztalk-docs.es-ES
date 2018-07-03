---
title: Nodos opcionales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, BizTalk Mapper
- maps, testing
- testing, maps
- BizTalk Mapper, testing
- maps, optional nodes
ms.assetid: 7dcd203e-fb23-438a-87d1-42323acd87cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91fe82709df36b374d8744e2060798074835b891
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994093"
---
# <a name="optional-nodes"></a><span data-ttu-id="9b43b-102">Nodos opcionales</span><span class="sxs-lookup"><span data-stu-id="9b43b-102">Optional Nodes</span></span>
<span data-ttu-id="9b43b-103">La utilización de nodos opcionales generará una advertencia al probar la asignación.</span><span class="sxs-lookup"><span data-stu-id="9b43b-103">Using optional nodes will produce a warning when you test your map.</span></span> <span data-ttu-id="9b43b-104">Existen dos condiciones en las que un nodo de origen puede considerarse opcional:</span><span class="sxs-lookup"><span data-stu-id="9b43b-104">There are two conditions in which a source node may be considered optional:</span></span>  
  
- <span data-ttu-id="9b43b-105">El registro o el campo reales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="9b43b-105">The actual record or field is optional.</span></span>  
  
- <span data-ttu-id="9b43b-106">El registro o el campo de origen son necesarios, pero los primarios o más altos en la jerarquía son opcionales.</span><span class="sxs-lookup"><span data-stu-id="9b43b-106">The source record or field is required, but a parent, grandparent, and farther up the hierarchy is optional.</span></span>  
  
  <span data-ttu-id="9b43b-107">Puede encontrarse con esta situación cuando tenga registros y campos en un esquema de origen que sean opcionales, pero el esquema de destino requiera los registros o campos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9b43b-107">You may have situations when you have records and fields in a source schema that are optional, but the destination schema requires the corresponding records or fields.</span></span>  
  
  <span data-ttu-id="9b43b-108">En las dos condiciones posibles, probar la asignación generará una advertencia en el **salida** ventana.</span><span class="sxs-lookup"><span data-stu-id="9b43b-108">In both of the possible conditions, testing your map produces a warning in the **Output** window.</span></span> <span data-ttu-id="9b43b-109">Además, los datos de salida no incluirán el nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="9b43b-109">In addition, the output data will not include the target node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b43b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b43b-110">See Also</span></span>  
 [<span data-ttu-id="9b43b-111">Comprobación de asignaciones</span><span class="sxs-lookup"><span data-stu-id="9b43b-111">Testing Maps</span></span>](../core/testing-maps.md)