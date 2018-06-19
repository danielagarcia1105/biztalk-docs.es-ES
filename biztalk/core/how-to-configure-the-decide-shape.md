---
title: Cómo configurar la forma decidir | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Decide shape [Orchestration Designer]
- Decide shape [Orchestration Designer], configuring
- Decide shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Decide shapes
ms.assetid: 70910861-3834-49e7-ab1e-d62730ea2a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22368134e2c1a0d8deb277e186792158a7c2dd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248692"
---
# <a name="how-to-configure-the-decide-shape"></a><span data-ttu-id="772b8-102">Cómo configurar la forma Decidir</span><span class="sxs-lookup"><span data-stu-id="772b8-102">How to Configure the Decide Shape</span></span>
![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")  
<span data-ttu-id="772b8-103">Forma Decidir</span><span class="sxs-lookup"><span data-stu-id="772b8-103">Decide shape</span></span>  
  
 <span data-ttu-id="772b8-104">Cada rama de un **decidir** forma, excepto el **else** crear una bifurcación, tiene una regla asociados con él.</span><span class="sxs-lookup"><span data-stu-id="772b8-104">Each branch of a **Decide** shape, except the **else** branch, has a rule associated with it.</span></span> <span data-ttu-id="772b8-105">Puede usar el Editor de expresiones de BizTalk para crear una expresión booleana en la regla que se evalúa para la ejecución de esa rama.</span><span class="sxs-lookup"><span data-stu-id="772b8-105">You can use BizTalk Expression Editor to create a Boolean expression in the rule that is evaluated for the execution of that branch.</span></span> <span data-ttu-id="772b8-106">Dado que la **else** bifurcación implica la negación de la expresión booleana de la rama anterior, no tiene una expresión asociada con él.</span><span class="sxs-lookup"><span data-stu-id="772b8-106">Because the **else** branch implies the negation of the Boolean expression in the previous branch, it does not have an expression associated with it.</span></span>  
  
 <span data-ttu-id="772b8-107">Debajo de la regla o **else** cláusula, una rama de un **decidir** forma puede contener formas adicionales, como cualquier otra parte de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="772b8-107">Below the rule or **else** clause, a branch of a **Decide** shape can contain additional shapes, just like any other part of the orchestration.</span></span>  
  
### <a name="to-configure-a-decide-shape"></a><span data-ttu-id="772b8-108">Para configurar una forma Decidir</span><span class="sxs-lookup"><span data-stu-id="772b8-108">To configure a Decide shape</span></span>  
  
1.  <span data-ttu-id="772b8-109">Si el Editor de expresiones de BizTalk no está visible, haga clic en la regla y haga clic en **Editar expresión booleana**, o en la ventana Propiedades, haga clic en el **puntos suspensivos** (**...** ) botón la **expresión** propiedad.</span><span class="sxs-lookup"><span data-stu-id="772b8-109">If BizTalk Expression Editor is not visible, right-click the rule and click **Edit Boolean Expression**, or in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="772b8-110">En el Editor de expresiones de BizTalk, cree una expresión booleana para cada rama, excepto la **Else** bifurcación.</span><span class="sxs-lookup"><span data-stu-id="772b8-110">In BizTalk Expression Editor, create a Boolean expression for each branch except the **Else** branch.</span></span> <span data-ttu-id="772b8-111">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="772b8-111">For example,</span></span>  
  
    ```  
    myMessage.Total > 1000  
    myObject.IsValid()  
    myMessage.VIP == true  
    ```  
  
### <a name="to-add-a-branch-to-a-decide-shape"></a><span data-ttu-id="772b8-112">Para agregar una rama a una forma Decidir</span><span class="sxs-lookup"><span data-stu-id="772b8-112">To add a branch to a Decide shape</span></span>  
  
1.  <span data-ttu-id="772b8-113">Haga clic en el **decidir** forma y, a continuación, haga clic en **nueva rama de reglas**.</span><span class="sxs-lookup"><span data-stu-id="772b8-113">Right-click the **Decide** shape, and then click **New Rule Branch**.</span></span>  
  
     <span data-ttu-id="772b8-114">: "O":</span><span class="sxs-lookup"><span data-stu-id="772b8-114">—Or—</span></span>  
  
2.  <span data-ttu-id="772b8-115">Arrastre una nueva forma entre dos ramas existentes.</span><span class="sxs-lookup"><span data-stu-id="772b8-115">Drag a new shape between two existing branches.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="772b8-116">Para quitar una rama de un **decidir** forma, haga clic en la rama que desee quitar y, a continuación, haga clic en **eliminar**, o seleccione la rama de reglas y presione la **eliminar** clave.</span><span class="sxs-lookup"><span data-stu-id="772b8-116">To remove a branch from a **Decide** shape, right-click the branch you want to remove, and then click **Delete**, or select the rule branch and press the **DELETE** key.</span></span>