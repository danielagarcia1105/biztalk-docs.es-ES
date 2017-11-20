---
title: "Cómo configurar la forma escuchar | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Listen shape [Orchestration Designer], about Listen shape
- Listen shape [Orchestration Designer], configuring
- Listen shape [Orchestration Designer]
- Listen shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Listen shapes
ms.assetid: 4765dc0a-a30e-4515-83bc-72b4f37268cf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd8f8bbcc08d41430b95a9d177aeb06a5288be4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-listen-shape"></a><span data-ttu-id="624bc-102">Cómo configurar la forma Escuchar</span><span class="sxs-lookup"><span data-stu-id="624bc-102">How to Configure the Listen Shape</span></span>
<span data-ttu-id="624bc-103">Las acciones de escucha permiten que las aplicaciones esperen uno de varios mensajes en uno o varios puertos o que detengan la espera después de un intervalo del tiempo de espera especificado y ramifiquen según los resultados.</span><span class="sxs-lookup"><span data-stu-id="624bc-103">Listen actions enable applications to wait for one of several messages on one or more ports, or to stop waiting after a specified time-out interval, and branch based upon the results.</span></span>  
  
 ![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")  
<span data-ttu-id="624bc-104">Forma Escuchar</span><span class="sxs-lookup"><span data-stu-id="624bc-104">Listen shape</span></span>  
  
 <span data-ttu-id="624bc-105">Puede agregar tantas ramas como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="624bc-105">You can add as many branches as you like.</span></span> <span data-ttu-id="624bc-106">Puede colocar cualquier otra forma bajo la inicial **recepción** o **retraso** forma.</span><span class="sxs-lookup"><span data-stu-id="624bc-106">You can place any other shape below the initial **Receive** or **Delay** shape.</span></span>  
  
 <span data-ttu-id="624bc-107">Es posible utilizar una activación de recepción en un **escuchar** forma.</span><span class="sxs-lookup"><span data-stu-id="624bc-107">It is possible to use an activation receive in a **Listen** shape.</span></span> <span data-ttu-id="624bc-108">Si una rama de la **escuchar** forma contiene una activación de recepción, todas las ramas deben contener recepciones de activación, y no puede usarse tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="624bc-108">If one branch of the **Listen** shape contains an activation receive, then all branches must contain activation receives, and no timeout can be used.</span></span> <span data-ttu-id="624bc-109">La recepción de activación debe ser la primera acción en cada rama.</span><span class="sxs-lookup"><span data-stu-id="624bc-109">The activation receive must be the first action in each branch.</span></span>  
  
 <span data-ttu-id="624bc-110">Puede usar el **escuchar** forma al flujo de orquestación de bifurcación en función de la aparición de uno o más eventos.</span><span class="sxs-lookup"><span data-stu-id="624bc-110">You can use the **Listen** shape to branch orchestration flow based on the occurrence of one or more events.</span></span> <span data-ttu-id="624bc-111">La primera forma en cada rama debe ser un **retraso** o un **recepción** forma.</span><span class="sxs-lookup"><span data-stu-id="624bc-111">The first shape in each branch must be either a **Delay** or a **Receive** shape.</span></span> <span data-ttu-id="624bc-112">La primera rama que cumpla su condición, la aparición de un tiempo de espera para un **retraso** forma o la recepción de un mensaje para un **recepción** forma, se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="624bc-112">The first branch that meets its condition—the occurrence of a time-out for a **Delay** shape or the receipt of a message for a **Receive** shape—will execute.</span></span> <span data-ttu-id="624bc-113">Puede agregar más ramas si lo necesita.</span><span class="sxs-lookup"><span data-stu-id="624bc-113">You can add additional branches if needed.</span></span>  
  
### <a name="to-configure-a-listen-shape"></a><span data-ttu-id="624bc-114">Para configurar una forma Escuchar</span><span class="sxs-lookup"><span data-stu-id="624bc-114">To configure a Listen shape</span></span>  
  
1.  <span data-ttu-id="624bc-115">Seleccione una rama.</span><span class="sxs-lookup"><span data-stu-id="624bc-115">Select a branch.</span></span>  
  
2.  <span data-ttu-id="624bc-116">En la ventana Propiedades, especifique la **tipo de rama** propiedad.</span><span class="sxs-lookup"><span data-stu-id="624bc-116">In the Properties window, specify the **Branch Type** property.</span></span>  
  
     <span data-ttu-id="624bc-117">: "O":</span><span class="sxs-lookup"><span data-stu-id="624bc-117">—Or—</span></span>  
  
     <span data-ttu-id="624bc-118">Arrastre un **retraso** o **recepción** forma en la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="624bc-118">Drag a **Delay** or **Receive** shape onto the branch.</span></span>  
  
### <a name="to-add-a-branch-to-a-listen-shape"></a><span data-ttu-id="624bc-119">Para agregar una rama a una forma Escuchar</span><span class="sxs-lookup"><span data-stu-id="624bc-119">To add a branch to a Listen shape</span></span>  
  
-   <span data-ttu-id="624bc-120">Haga clic en el **escuchar** forma y, a continuación, haga clic en **nueva rama escuchar**.</span><span class="sxs-lookup"><span data-stu-id="624bc-120">Right-click the **Listen** shape and then click **New Listen Branch**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="624bc-121">Para quitar una rama de un **escuchar** forma, haga clic en la rama que desee quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="624bc-121">To remove a branch from a **Listen** shape, right-click the branch you want to remove, and then click **Delete**.</span></span>