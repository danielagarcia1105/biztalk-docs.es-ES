---
title: Nodos de relación | Microsoft Docs
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
ms.openlocfilehash: 866a2e1367279c6a53eeb738f4800a647a0cd468
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001757"
---
# <a name="relationship-nodes"></a><span data-ttu-id="786c3-102">Nodos de relación</span><span class="sxs-lookup"><span data-stu-id="786c3-102">Relationship Nodes</span></span>
<span data-ttu-id="786c3-103">Las carpetas de relación se utilizan siempre que un archivo de definición de actividad contenga más de una actividad.</span><span class="sxs-lookup"><span data-stu-id="786c3-103">Relationship folders are used whenever an activity definition file contains more than one activity.</span></span> <span data-ttu-id="786c3-104">Los nombres de las carpetas coinciden con el nombre de la actividad asociada.</span><span class="sxs-lookup"><span data-stu-id="786c3-104">The names of the folders match the name of the associated activity.</span></span> <span data-ttu-id="786c3-105">El vínculo se crea haciendo coincidir el nombre de la carpeta de relación con el Id. de la actividad relacionada, así como los valores de los elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="786c3-105">You form the link by matching the name of the relationship folder to the activity ID of the related activity and by matching the values for the data items.</span></span> <span data-ttu-id="786c3-106">Cada relación se define utilizando un nodo independiente.</span><span class="sxs-lookup"><span data-stu-id="786c3-106">You define each relationship using a separate node.</span></span>  
  
## <a name="working-with-relationship-nodes"></a><span data-ttu-id="786c3-107">Trabajar con nodos de relación</span><span class="sxs-lookup"><span data-stu-id="786c3-107">Working with Relationship nodes</span></span>  
 <span data-ttu-id="786c3-108">Para indicar el identificador de instancia único que enlaza el elemento de datos entre las actividades:</span><span class="sxs-lookup"><span data-stu-id="786c3-108">To indicate the unique instance identifier that links the data item between activities:</span></span>  
  
- <span data-ttu-id="786c3-109">Asigne un elemento de datos al nodo ActivityId de la orquestación principal.</span><span class="sxs-lookup"><span data-stu-id="786c3-109">Map a data item to the ActivityId node of the main orchestration.</span></span>  
  
- <span data-ttu-id="786c3-110">Arrastre y coloque un elemento de datos con el mismo nombre que aparece arriba en el nodo de relación de la actividad relacionada.</span><span class="sxs-lookup"><span data-stu-id="786c3-110">Drag and drop a data item with the same name as above to the Relationship node in the related activity.</span></span> <span data-ttu-id="786c3-111">El nodo de relación tiene el mismo nombre que el nodo de actividad de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="786c3-111">The Relationship node has the same name as the Activity node of the main activity.</span></span>  
  
  <span data-ttu-id="786c3-112">Por ejemplo, en el escenario de ejemplo, podría existir un proceso empresarial relacionado, aunque independiente, en una orquestación denominada RefinanceOrchestration.</span><span class="sxs-lookup"><span data-stu-id="786c3-112">For example, in the sample scenario, there could be a related but separate business process represented in an orchestration called RefinanceOrchestration.</span></span> <span data-ttu-id="786c3-113">La orquestación podría contener un nodo de actividad de LoanRefinance, un ActivityID de refinanciación y formas de orquestación como Recibir solicitud de evaluación.</span><span class="sxs-lookup"><span data-stu-id="786c3-113">That orchestration could contain a LoanRefinance Activity node, a Refinance ActivityID, and orchestration shapes such as Receive Appraisal Request.</span></span> <span data-ttu-id="786c3-114">Sin embargo, el nodo de relación y el Id. de relación podrían ser LoanID, lo que indicaría el vínculo con la actividad LoanProcess original.</span><span class="sxs-lookup"><span data-stu-id="786c3-114">The Relationship node and relationship ID, however, could be LoanID, indicating the link to the original LoanProcess activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786c3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="786c3-115">See Also</span></span>  
 [<span data-ttu-id="786c3-116">Nodos Vista de actividad de TPE</span><span class="sxs-lookup"><span data-stu-id="786c3-116">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)