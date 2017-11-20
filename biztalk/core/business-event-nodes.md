---
title: Nodos de eventos empresariales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events, Tracking Profile Editor
- events, date specific
- events, time specific
- Tracking Profile Editor, node descriptions
- Business Event nodes [Tracking Profile Editor]
- Tracking Profile Editor, events
ms.assetid: 177bc3c4-e762-42fe-80bc-edede5cd4fcd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44c3d06e553f129abb36eb53c4dde9c5ab9c25f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="business-event-nodes"></a><span data-ttu-id="2f83f-102">Nodos de eventos empresariales</span><span class="sxs-lookup"><span data-stu-id="2f83f-102">Business Event Nodes</span></span>
<span data-ttu-id="2f83f-103">Los nodos de hitos o eventos empresariales definen eventos que son específicos de la fecha o la hora.</span><span class="sxs-lookup"><span data-stu-id="2f83f-103">Business Event or milestone nodes define events that are date- or time-specific.</span></span> <span data-ttu-id="2f83f-104">Las carpetas de hito o evento empresarial predefinidas existen en la definición de actividad que importa del usuario empresarial final y no las puede eliminar sin tener que volver a importar el archivo de definición de actividad.</span><span class="sxs-lookup"><span data-stu-id="2f83f-104">Pre-defined business event and milestone folders exist in the activity definition you import from the business end user, and you cannot delete them without reimporting the activity definition file.</span></span>  
  
## <a name="working-with-business-event-nodes"></a><span data-ttu-id="2f83f-105">Trabajar con nodos de eventos empresariales</span><span class="sxs-lookup"><span data-stu-id="2f83f-105">Working with business event nodes</span></span>  
 <span data-ttu-id="2f83f-106">Puede arrastrar formas a la carpeta Eventos empresariales desde la orquestación para realizar el seguimiento de aquellos eventos a medida que se completa la ejecución de las formas.</span><span class="sxs-lookup"><span data-stu-id="2f83f-106">You can drag shapes from the orchestration into the Business Events folder to track those events as the execution of the shapes is completed.</span></span>  
  
 <span data-ttu-id="2f83f-107">TPE utiliza el nombre de la forma para el nombre de la carpeta de evento y esta carpeta tendrá un icono único.</span><span class="sxs-lookup"><span data-stu-id="2f83f-107">TPE uses the name of the shape for the name of the event folder, and this folder will have a unique icon.</span></span> <span data-ttu-id="2f83f-108">Por ejemplo, en el caso del ejemplo de proceso de préstamo, TPE los denomina según el evento, como Aprobado o Denegado.</span><span class="sxs-lookup"><span data-stu-id="2f83f-108">For example, in the sample loan-process scenario, TPE names them according to the event, such as Approved or Denied.</span></span> <span data-ttu-id="2f83f-109">solo debería realizar el seguimiento de eventos empresariales una vez por proceso empresarial cuando el proceso empresarial abarque varios perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2f83f-109">You should only track business events once per business process when that business process spans multiple tracking profiles.</span></span> <span data-ttu-id="2f83f-110">Si tiene una ruta condicional en su orquestación, puede seleccionar el evento empresarial de ambas rutas, ya que solo uno de ellos se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="2f83f-110">If you have a conditional path in your orchestration, you can select the business event from both paths, as only one will ever execute.</span></span> <span data-ttu-id="2f83f-111">No debería seleccionar una forma dentro de un bucle.</span><span class="sxs-lookup"><span data-stu-id="2f83f-111">You should not select a shape inside a loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f83f-112">Aunque no puede eliminar carpetas sin tener que volver a importar la definición de actividad, puede eliminar formas (eventos).</span><span class="sxs-lookup"><span data-stu-id="2f83f-112">While you cannot delete folders without reimporting the activity definition, you can delete shapes (events).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f83f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f83f-113">See Also</span></span>  
 [<span data-ttu-id="2f83f-114">Nodos de vista de actividad TPE</span><span class="sxs-lookup"><span data-stu-id="2f83f-114">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)