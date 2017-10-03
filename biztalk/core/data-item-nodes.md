---
title: Nodos de elemento de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definition files [BAM], data items
- Data Item nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 95856bfa-90e3-49d9-b55b-5f1b35a23f78
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a968bf7533697922938eeb8953f17813c77147c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-item-nodes"></a><span data-ttu-id="4cbff-102">Nodos Elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4cbff-102">Data Item Nodes</span></span>
<span data-ttu-id="4cbff-103">Los nodos Elemento de datos existen en el archivo de definición de actividad que el programador importa desde el modelo de observación creado por el analista de negocios.</span><span class="sxs-lookup"><span data-stu-id="4cbff-103">Data Item nodes exist in the activity definition file that the developer imports from the created observation model created by the business analyst.</span></span> <span data-ttu-id="4cbff-104">El Editor de perfiles de seguimiento (TPE) les asigna un nombre en función de los elementos de datos de los que se efectúa un seguimiento, por ejemplo Nombre del cliente.</span><span class="sxs-lookup"><span data-stu-id="4cbff-104">The Tracking Profile Editor (TPE) names them for the data items they are tracking, such as Customer Name.</span></span> <span data-ttu-id="4cbff-105">A continuación, se descargan los elementos de datos, uno o varios, desde la vista Esquema de mensaje hasta el nodo que corresponda al nombre del cliente.</span><span class="sxs-lookup"><span data-stu-id="4cbff-105">You then drop one or more data items from the Message Schema View onto the node that corresponds to Customer Name.</span></span>  
  
## <a name="working-with-data-item-nodes"></a><span data-ttu-id="4cbff-106">Trabajar con nodos de elementos de datos</span><span class="sxs-lookup"><span data-stu-id="4cbff-106">Working with data item nodes</span></span>  
 <span data-ttu-id="4cbff-107">Al asignar nodos Elemento de datos, cuando el proceso empresarial abarque varios perfiles de seguimiento, solo deberá realizar el seguimiento de los elementos de datos una vez por cada proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="4cbff-107">When mapping Data Item nodes you should only track data items once per business process when that business process spans multiple tracking profiles.</span></span> <span data-ttu-id="4cbff-108">Si tiene una ruta condicional en la orquestación, puede seleccionar el elemento de datos de ambas rutas, pues solo se ejecutará una de ellas.</span><span class="sxs-lookup"><span data-stu-id="4cbff-108">If you have a conditional path in your orchestration, you can select the data item from both paths because only one will run.</span></span> <span data-ttu-id="4cbff-109">Sin embargo, no debe elegir una forma incluida en un bucle, a menos que los valores del elemento de datos sean distintos en cada repetición.</span><span class="sxs-lookup"><span data-stu-id="4cbff-109">However, you should not choose a shape inside a loop unless the values will be different for the data item with each iteration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cbff-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cbff-110">See Also</span></span>  
 <span data-ttu-id="4cbff-111">[Cómo asignar datos de elemento](../core/how-to-map-item-data.md) </span><span class="sxs-lookup"><span data-stu-id="4cbff-111">[How to Map Item Data](../core/how-to-map-item-data.md) </span></span>  
 [<span data-ttu-id="4cbff-112">Nodos de vista de actividad TPE</span><span class="sxs-lookup"><span data-stu-id="4cbff-112">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)