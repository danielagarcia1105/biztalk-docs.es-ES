---
title: Nodos de relación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definition files [BAM], relationships
- definition files [BAM], Tracking Profile Editor
- Relationship nodes [Tracking Profile Editor]
- activities [BAM], relationships
- activities [BAM], Tracking Profile Editor
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 74090133-24d1-4aba-a4fc-f12d19c881fb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f670c62b4e883b124d849ab61396f6f5216e7182
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268252"
---
# <a name="relationship-nodes"></a><span data-ttu-id="a29b1-102">Nodos de relación</span><span class="sxs-lookup"><span data-stu-id="a29b1-102">Relationship Nodes</span></span>
<span data-ttu-id="a29b1-103">Las carpetas de relación se utilizan siempre que un archivo de definición de actividad contenga más de una actividad.</span><span class="sxs-lookup"><span data-stu-id="a29b1-103">Relationship folders are used whenever an activity definition file contains more than one activity.</span></span> <span data-ttu-id="a29b1-104">Los nombres de las carpetas coinciden con el nombre de la actividad asociada.</span><span class="sxs-lookup"><span data-stu-id="a29b1-104">The names of the folders match the name of the associated activity.</span></span> <span data-ttu-id="a29b1-105">El vínculo se crea haciendo coincidir el nombre de la carpeta de relación con el Id. de la actividad relacionada, así como los valores de los elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="a29b1-105">You form the link by matching the name of the relationship folder to the activity ID of the related activity and by matching the values for the data items.</span></span> <span data-ttu-id="a29b1-106">Cada relación se define utilizando un nodo independiente.</span><span class="sxs-lookup"><span data-stu-id="a29b1-106">You define each relationship using a separate node.</span></span>  
  
## <a name="working-with-relationship-nodes"></a><span data-ttu-id="a29b1-107">Trabajar con nodos de relación</span><span class="sxs-lookup"><span data-stu-id="a29b1-107">Working with Relationship nodes</span></span>  
 <span data-ttu-id="a29b1-108">Para indicar el identificador de instancia único que enlaza el elemento de datos entre las actividades:</span><span class="sxs-lookup"><span data-stu-id="a29b1-108">To indicate the unique instance identifier that links the data item between activities:</span></span>  
  
-   <span data-ttu-id="a29b1-109">Asigne un elemento de datos al nodo ActivityId de la orquestación principal.</span><span class="sxs-lookup"><span data-stu-id="a29b1-109">Map a data item to the ActivityId node of the main orchestration.</span></span>  
  
-   <span data-ttu-id="a29b1-110">Arrastre y coloque un elemento de datos con el mismo nombre que aparece arriba en el nodo de relación de la actividad relacionada.</span><span class="sxs-lookup"><span data-stu-id="a29b1-110">Drag and drop a data item with the same name as above to the Relationship node in the related activity.</span></span> <span data-ttu-id="a29b1-111">El nodo de relación tiene el mismo nombre que el nodo de actividad de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="a29b1-111">The Relationship node has the same name as the Activity node of the main activity.</span></span>  
  
 <span data-ttu-id="a29b1-112">Por ejemplo, en el escenario de ejemplo, podría existir un proceso empresarial relacionado, aunque independiente, en una orquestación denominada RefinanceOrchestration.</span><span class="sxs-lookup"><span data-stu-id="a29b1-112">For example, in the sample scenario, there could be a related but separate business process represented in an orchestration called RefinanceOrchestration.</span></span> <span data-ttu-id="a29b1-113">La orquestación podría contener un nodo de actividad de LoanRefinance, un ActivityID de refinanciación y formas de orquestación como Recibir solicitud de evaluación.</span><span class="sxs-lookup"><span data-stu-id="a29b1-113">That orchestration could contain a LoanRefinance Activity node, a Refinance ActivityID, and orchestration shapes such as Receive Appraisal Request.</span></span> <span data-ttu-id="a29b1-114">Sin embargo, el nodo de relación y el Id. de relación podrían ser LoanID, lo que indicaría el vínculo con la actividad LoanProcess original.</span><span class="sxs-lookup"><span data-stu-id="a29b1-114">The Relationship node and relationship ID, however, could be LoanID, indicating the link to the original LoanProcess activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a29b1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a29b1-115">See Also</span></span>  
 [<span data-ttu-id="a29b1-116">Nodos de vista de actividad TPE</span><span class="sxs-lookup"><span data-stu-id="a29b1-116">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)