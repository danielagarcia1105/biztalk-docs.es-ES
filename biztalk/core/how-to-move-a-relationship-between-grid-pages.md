---
title: Cómo mover una relación entre las páginas de cuadrícula | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.movetopage
ms.assetid: 185add4d-c876-44b6-b6e0-71c15a9b7c26
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5737adcb9159568bfea7c7cdde9dff8015b19706
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-a-relationship-between-grid-pages"></a><span data-ttu-id="e9d53-102">Mover una relación entre las páginas de cuadrícula</span><span class="sxs-lookup"><span data-stu-id="e9d53-102">How to Move a Relationship Between Grid Pages</span></span>
<span data-ttu-id="e9d53-103">Las asignaciones grandes incluyen numerosos conjuntos de functoids y vínculos, por lo cual pueden perjudicarle la identificación de los vínculos que unen varios functoids.</span><span class="sxs-lookup"><span data-stu-id="e9d53-103">Large maps include many sets of functoids and links, which can make it difficult for you to identify the links joining multiple functoids.</span></span> <span data-ttu-id="e9d53-104">En tal caso, es posible que desee mover un conjunto similar de functoids y vínculos a una página de cuadrícula diferente para que la asignación resulte más legible.</span><span class="sxs-lookup"><span data-stu-id="e9d53-104">In such a scenario, you might want to move a similar set of functoids and links to a different grid page to make the map more readable.</span></span> <span data-ttu-id="e9d53-105">En este tema se proporcionan instrucciones detalladas para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="e9d53-105">This topic provides step-by-step instructions to perform the operation.</span></span>  
  
 <span data-ttu-id="e9d53-106">Puede mover una relación de una página de cuadrícula a otra, en el mismo mapa solamente, de uno de los modos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9d53-106">You can move a relationship from one grid page to another, in the same map only, in one of the following ways:</span></span>  
  
-   <span data-ttu-id="e9d53-107">Mediante el **moverse a la página** cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="e9d53-107">Using the **Move to Page** dialog box</span></span>  
  
-   <span data-ttu-id="e9d53-108">Usando la función de arrastrar y colocar de los functoids (y vínculos) seleccionados en la cinta</span><span class="sxs-lookup"><span data-stu-id="e9d53-108">Using the drag-and-drop of the ribbon-selected functoid(s) (and links)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9d53-109">Puede mover uno o más functoids y sus vínculos.</span><span class="sxs-lookup"><span data-stu-id="e9d53-109">You can move one or more functoids and their links.</span></span> <span data-ttu-id="e9d53-110">Al mover una relación, se mantienen las etiquetas, comentarios y los valores constantes (junto con los marcadores de posición correctos) asociados con dicha relación.</span><span class="sxs-lookup"><span data-stu-id="e9d53-110">When you move a relationship, the labels, comments, and the constant values (along with the correct place holders) associated with that relationship are retained.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9d53-111">No se pueden arrastrar y colocar vínculos solamente a otra página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e9d53-111">You cannot drag-and-drop only links to another grid page.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e9d53-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e9d53-112">Prerequisites</span></span>  
 <span data-ttu-id="e9d53-113">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e9d53-113">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-move-a-relationship-using-move-to-page-dialog-box"></a><span data-ttu-id="e9d53-114">Procedimiento para mover una relación mediante el cuadro de diálogo Mover a página</span><span class="sxs-lookup"><span data-stu-id="e9d53-114">To move a relationship using Move To Page dialog box</span></span>  
  
1.  <span data-ttu-id="e9d53-115">En el mapa, seleccione la página de cuadrícula desde la que desea mover una relación.</span><span class="sxs-lookup"><span data-stu-id="e9d53-115">On the map, select the grid page from which you want to move a relationship.</span></span>  
  
2.  <span data-ttu-id="e9d53-116">Haga clic en un functoid o un vínculo en la relación que desea mover y, a continuación, haga clic en **moverse a la página**.</span><span class="sxs-lookup"><span data-stu-id="e9d53-116">Right-click a functoid or a link in the relationship you want to move and then click **Move to Page**.</span></span> <span data-ttu-id="e9d53-117">Se muestra un mensaje que indica que se van a mover todos los elementos de asignación seleccionados, junto con los vínculos y functoids relacionados.</span><span class="sxs-lookup"><span data-stu-id="e9d53-117">A message saying that all the selected map items(s), along with related links and functoids, will be moved is displayed.</span></span> <span data-ttu-id="e9d53-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e9d53-118">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e9d53-119">Para deshabilitar el mensaje emergente, en el menú de Visual Studio, vaya a **herramientas**, haga clic en **opciones**, haga clic en **el asignador de BizTalk**, haga clic en **General**, y, a continuación, desactive la **ir a la página** opción.</span><span class="sxs-lookup"><span data-stu-id="e9d53-119">To disable the message popup, in the Visual Studio menu, go to **Tools**, click **Options**, click **BizTalk Mapper**, click **General**, and then uncheck the **Move to page** option.</span></span> <span data-ttu-id="e9d53-120">Para obtener más información acerca de opciones generales, consulte [cómo personalizar la configuración General del asignador de BizTalk](../core/how-to-customize-general-settings-in-biztalk-mapper.md).</span><span class="sxs-lookup"><span data-stu-id="e9d53-120">For more information about general options, see [How to Customize General Settings in BizTalk Mapper](../core/how-to-customize-general-settings-in-biztalk-mapper.md).</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="e9d53-121">Como alternativa, puede presionar CTRL + M, CTRL + M para abrir la **moverse a la página** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e9d53-121">Alternatively, you can press CTRL+M, CTRL+M to open the **Move to Page** dialog box.</span></span> <span data-ttu-id="e9d53-122">Para obtener una lista de métodos abreviados del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="e9d53-122">For a list of Mapper shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="e9d53-123">![Mover la relación seleccionada a una nueva página](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")</span><span class="sxs-lookup"><span data-stu-id="e9d53-123">![Moving selected relationship to a new page](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")</span></span>  
  
3.  <span data-ttu-id="e9d53-124">En el **moverse a la página** cuadro de diálogo, seleccione la página de cuadrícula de destino al que desea mover la relación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e9d53-124">In the **Move to Page** dialog box, select the target grid page to which you want to move the relationship, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e9d53-125">También puede crear una nueva página seleccionando  **\*(Agregar nueva página)**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e9d53-125">You can also create a new page by selecting **\*(add new page)**, and then clicking **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e9d53-126">Como alternativa, puede presionar CTRL+M, CTRL+A para agregar una nueva página de cuadrícula en una asignación.</span><span class="sxs-lookup"><span data-stu-id="e9d53-126">Alternatively, you can press CTRL+M, CTRL+A to add a new grid page in a map.</span></span> <span data-ttu-id="e9d53-127">Para obtener una lista de métodos abreviados del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="e9d53-127">For a list of Mapper shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="e9d53-128">![Seleccione la página de cuadrícula de destino](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")</span><span class="sxs-lookup"><span data-stu-id="e9d53-128">![Selecting the target grid page](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")</span></span>  
  
     <span data-ttu-id="e9d53-129">El functoid/vínculo seleccionado, junto con los functoids y vínculos relacionados, se mueve a la nueva página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e9d53-129">The selected functoid/link, along with the related functoids and links, is moved to the new grid page.</span></span> <span data-ttu-id="e9d53-130">En la ilustración siguientes se muestra la relación seleccionada (que estaba en la página 3) movida a la página 1.</span><span class="sxs-lookup"><span data-stu-id="e9d53-130">The figure below shows the selected relationship (which was in Page 3) moved to Page 1.</span></span>  
  
     <span data-ttu-id="e9d53-131">![Relación seleccionada se mueve a una nueva página](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")</span><span class="sxs-lookup"><span data-stu-id="e9d53-131">![Selected relationship is moved to a new page](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")</span></span>  
  
### <a name="to-move-a-relationship-using-drag-and-drop"></a><span data-ttu-id="e9d53-132">Procedimiento para mover una relación mediante arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="e9d53-132">To move a relationship using drag-and-drop</span></span>  
  
1.  <span data-ttu-id="e9d53-133">En el mapa, seleccione la página de cuadrícula desde la que desea mover una relación.</span><span class="sxs-lookup"><span data-stu-id="e9d53-133">On the map, select the grid page from which you want to move a relationship.</span></span>  
  
2.  <span data-ttu-id="e9d53-134">Seleccione los functoids (y vínculos) que desee mover a otra página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e9d53-134">Select the functoid(s) (and link(s)) you want to move to another grid page.</span></span> <span data-ttu-id="e9d53-135">Este selecciona recursivamente todos los vínculos que conectan con los functoids de la selección.</span><span class="sxs-lookup"><span data-stu-id="e9d53-135">This recursively selects all links that connect to the functoids in the selection.</span></span>  
  
3.  <span data-ttu-id="e9d53-136">Arrastre la selección a la página (en la pestaña de páginas) donde desee mover la relación.</span><span class="sxs-lookup"><span data-stu-id="e9d53-136">Drag the selection to the page (on the page tab) where you want to move the relationship.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="e9d53-137">No suelte el mouse hasta que realice el paso 4.</span><span class="sxs-lookup"><span data-stu-id="e9d53-137">Do not release the mouse till you perform step 4.</span></span>  
  
4.  <span data-ttu-id="e9d53-138">Cuando la página de cuadrícula de destino pase a estar seleccionada (en la anterior figura, está seleccionada la Página 1), suelte la selección en una celda vacía de la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e9d53-138">When the target grid page comes into focus (in the above figure, Page 1 is in focus), drop the selection on an empty cell on the grid page.</span></span> <span data-ttu-id="e9d53-139">La relación seleccionada se moverá a la nueva página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e9d53-139">The selected relationship is moved to the new grid page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d53-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9d53-140">See Also</span></span>  
 [<span data-ttu-id="e9d53-141">Trabajar con páginas de cuadrícula</span><span class="sxs-lookup"><span data-stu-id="e9d53-141">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)