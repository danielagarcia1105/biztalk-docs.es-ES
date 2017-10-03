---
title: "Cómo configurar la forma acciones paralelas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Parallel Actions shape [Orchestration Designer], Terminate shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer], synchronizing data access
- Parallel Actions shape [Orchestration Designer]
- configuring [Orchestration Designer], Parallel Actions shapes
- Parallel Actions shape [Orchestration Designer], branching
- Parallel Actions shape [Orchestration Designer], about Parallel Actions shape
- Terminate shape [Orchestration Designer], Parallel Actions shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer], configuring
ms.assetid: 396d6182-f5dd-4aab-9edc-92efe236fd3e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 125d479a09eefb6771a884d2cddbfa98f34aeb36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-parallel-actions-shape"></a><span data-ttu-id="56d9b-102">Cómo configurar la forma Acciones paralelas</span><span class="sxs-lookup"><span data-stu-id="56d9b-102">How to Configure the Parallel Actions Shape</span></span>
![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")  
<span data-ttu-id="56d9b-103">Forma acciones paralela</span><span class="sxs-lookup"><span data-stu-id="56d9b-103">Parallel Actions shape</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="56d9b-104">Si coloca un **Terminate** forma dentro de un **acciones paralelas** forma así como la rama con la **Terminate** en que se ejecuta, la instancia se completa inmediatamente, sin tener en cuenta Si el resto de bifurcaciones ha terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="56d9b-104">If you place a **Terminate** shape inside a **Parallel Actions** shape, and the branch with the **Terminate** on it is run, the instance completes immediately, regardless of whether other branches have finished running.</span></span> <span data-ttu-id="56d9b-105">Según su diseño, los resultados podrían ser imprevisibles en este caso.</span><span class="sxs-lookup"><span data-stu-id="56d9b-105">Depending on your design, results might be unpredictable in this case.</span></span>  
  
## <a name="synchronization-of-data-access"></a><span data-ttu-id="56d9b-106">Sincronización de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="56d9b-106">Synchronization of data access</span></span>  
 <span data-ttu-id="56d9b-107">Es posible que más de una bifurcación de un **acciones paralelas** forma intentará tener acceso a los mismos datos.</span><span class="sxs-lookup"><span data-stu-id="56d9b-107">It is possible that more than one branch of a **Parallel Actions** shape will attempt to access the same data.</span></span> <span data-ttu-id="56d9b-108">Para evitar errores, coloque las formas que tienen acceso a los datos en el interior de ámbitos sincronizados.</span><span class="sxs-lookup"><span data-stu-id="56d9b-108">To avoid errors, place any shapes that access the data inside synchronized scopes.</span></span> <span data-ttu-id="56d9b-109">Puede especificar en las propiedades de un **ámbito** forma que se está sincronizado o no.</span><span class="sxs-lookup"><span data-stu-id="56d9b-109">You can specify in the properties of a **Scope** shape that it is synchronized or not synchronized.</span></span> <span data-ttu-id="56d9b-110">Para obtener más información, consulte [ámbitos](../core/scopes.md).</span><span class="sxs-lookup"><span data-stu-id="56d9b-110">For more information, see [Scopes](../core/scopes.md).</span></span>  
  
#### <a name="to-add-a-branch-to-a-parallel-actions-shape"></a><span data-ttu-id="56d9b-111">Para agregar una rama a una forma Acciones paralelas</span><span class="sxs-lookup"><span data-stu-id="56d9b-111">To add a branch to a Parallel Actions shape</span></span>  
  
1.  <span data-ttu-id="56d9b-112">Haga clic en el **acciones paralelas** forma y, a continuación, haga clic en **nueva rama paralela**.</span><span class="sxs-lookup"><span data-stu-id="56d9b-112">Right-click the **Parallel Actions** shape, and then click **New Parallel Branch**.</span></span>  
  
     <span data-ttu-id="56d9b-113">: "O":</span><span class="sxs-lookup"><span data-stu-id="56d9b-113">—Or—</span></span>  
  
2.  <span data-ttu-id="56d9b-114">Arrastre una nueva forma entre dos ramas existentes.</span><span class="sxs-lookup"><span data-stu-id="56d9b-114">Drag a new shape between two existing branches.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56d9b-115">Para quitar una rama de un **acciones paralelas** forma, haga clic en la rama que desee quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="56d9b-115">To remove a branch from a **Parallel Actions** shape, right-click the branch you want to remove, and then click **Delete**.</span></span>