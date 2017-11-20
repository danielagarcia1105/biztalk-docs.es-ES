---
title: "Cómo copiar, cortar y pegar un Functoid | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 825847e4-87db-4b40-8e5d-5b5b1c79c6de
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9af3662fb866eb09c1dcb2516279ca097cc998f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-cut-and-paste-a-functoid"></a><span data-ttu-id="9634d-102">Cómo copiar, cortar y pegar un functoid</span><span class="sxs-lookup"><span data-stu-id="9634d-102">How to Copy, Cut, and Paste a Functoid</span></span>
<span data-ttu-id="9634d-103">La característica de copiar, cortar y pegar del Asignador de BizTalk permite la reutilización de functoids.</span><span class="sxs-lookup"><span data-stu-id="9634d-103">The copy/cut/paste feature in the BizTalk Mapper enables the reusability of functoids.</span></span> <span data-ttu-id="9634d-104">En una asignación, puede copiar y cortar uno o varios functoids de una página de cuadrícula y pegarlos en otra.</span><span class="sxs-lookup"><span data-stu-id="9634d-104">In a map, you can copy, cut, and paste one or more functoids from one grid page to another.</span></span> <span data-ttu-id="9634d-105">En este tema se proporcionan instrucciones detalladas para realizar estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="9634d-105">This topic provides step-by-step instructions to perform these operations.</span></span>  
  
 <span data-ttu-id="9634d-106">Puede usar la característica de copiar y pegar cuando desee reutilizar functoids.</span><span class="sxs-lookup"><span data-stu-id="9634d-106">You can use the copy/paste feature when you want to reuse functoids.</span></span> <span data-ttu-id="9634d-107">Y, cuando desee eliminar un functoid de la ubicación existente y moverlo a una nueva ubicación, puede usar la característica de cortar y pegar.</span><span class="sxs-lookup"><span data-stu-id="9634d-107">And, when you want to remove a functoid from the existing location and move it to a new location, you can use the cut/paste feature.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9634d-108">Cuando elige copiar un functoid, se copia el functoid, su etiqueta, los comentarios y las entradas de constantes junto con los índices de marcador.</span><span class="sxs-lookup"><span data-stu-id="9634d-108">When you choose to copy a functoid, the functoid, its label, comments, and the constant-inputs, along with the placeholder indices, are copied.</span></span> <span data-ttu-id="9634d-109">De forma similar, cuando elige cortar un functoid, se corta el functoid, su etiqueta, los comentarios y las entradas de constantes, junto con los índices de marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="9634d-109">Similarly, when you choose to cut a functoid, the functoid, its label, comments, constant-inputs, along with the placeholder indices, are cut.</span></span> <span data-ttu-id="9634d-110">Pero, al pegar la selección (después de elegir cortar), únicamente se conserva el functoid y los vínculos huérfanos se eliminan.</span><span class="sxs-lookup"><span data-stu-id="9634d-110">But, when you paste (after choosing to cut) the selection, only the functoid is retained and the orphaned links are deleted.</span></span> <span data-ttu-id="9634d-111">No se conservan la etiqueta, los comentarios, las entradas constantes y los índices de marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="9634d-111">The label, comments, constant inputs, and placeholder indices are not retained.</span></span>  
  
 <span data-ttu-id="9634d-112">Si únicamente selecciona un functoid, que está vinculado a otro functoid o a un nodo de esquema, solo se cortará o copiará el functoid, sin los vínculos.</span><span class="sxs-lookup"><span data-stu-id="9634d-112">If you select only a functoid, which is either linked to another functoid or a schema node, only the functoid will be cut or copied, without the links.</span></span> <span data-ttu-id="9634d-113">Si corta un functoid que está vinculado a otros functoids en la asignación o a los nodos de esquema, se eliminan los vínculos para el functoid que se corta.</span><span class="sxs-lookup"><span data-stu-id="9634d-113">If you cut a functoid that is linked to other functoids in the map or to the schema nodes, the links to the functoid that is cut are deleted.</span></span>  
  
 <span data-ttu-id="9634d-114">Puede copiar o cortar functoids de:</span><span class="sxs-lookup"><span data-stu-id="9634d-114">You can copy/cut functoids from:</span></span>  
  
-   <span data-ttu-id="9634d-115">Dentro de la misma página de cuadrícula de un mapa</span><span class="sxs-lookup"><span data-stu-id="9634d-115">Within the same grid page of a map</span></span>  
  
-   <span data-ttu-id="9634d-116">Una página de cuadrícula a las otras del mismo mapa</span><span class="sxs-lookup"><span data-stu-id="9634d-116">One grid page to the other in the same map</span></span>  
  
-   <span data-ttu-id="9634d-117">Una instancia de Visual Studio a otra</span><span class="sxs-lookup"><span data-stu-id="9634d-117">One instance of Visual Studio to another</span></span>  
  
 <span data-ttu-id="9634d-118">Las operaciones de cortar y pegar no se pueden deshacer o rehacer.</span><span class="sxs-lookup"><span data-stu-id="9634d-118">You can undo or redo the cut and paste operations.</span></span> <span data-ttu-id="9634d-119">Para obtener más información, consulte [cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md).</span><span class="sxs-lookup"><span data-stu-id="9634d-119">For more information, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9634d-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9634d-120">Prerequisites</span></span>  
 <span data-ttu-id="9634d-121">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9634d-121">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-and-paste-a-functoid"></a><span data-ttu-id="9634d-122">Procedimiento para copiar y pegar un functoid</span><span class="sxs-lookup"><span data-stu-id="9634d-122">To copy and paste a functoid</span></span>  
  
1.  <span data-ttu-id="9634d-123">En el Explorador de soluciones, abra el proyecto BizTalk y haga doble clic en el mapa para abrirlo en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9634d-123">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="9634d-124">Seleccione el functoid que desee copiar.</span><span class="sxs-lookup"><span data-stu-id="9634d-124">Select the functoid you want to copy.</span></span> <span data-ttu-id="9634d-125">Para seleccionar varios functoids, haga clic en un functoid, mantenga presionada la tecla CTRL y haga clic en los demás functoids.</span><span class="sxs-lookup"><span data-stu-id="9634d-125">To select multiple functoids, click one functoid, hold down the CTRL key, and then click the other functoids.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9634d-126">Puede usar la operación "seleccionar en la cinta" para seleccionar varios vínculos o functoids.</span><span class="sxs-lookup"><span data-stu-id="9634d-126">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="9634d-127">Para obtener más información, consulte [cómo seleccionar varios vínculos y Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span><span class="sxs-lookup"><span data-stu-id="9634d-127">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="9634d-128">Haga clic en la selección y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="9634d-128">Right-click the selection, and then click **Copy**.</span></span> <span data-ttu-id="9634d-129">Como alternativa, puede hacer clic en **copia** desde el Visual Studio **editar** menú o presione CTRL + C en el teclado.</span><span class="sxs-lookup"><span data-stu-id="9634d-129">Alternatively, you can either click **Copy** from the Visual Studio’s **Edit** menu or press CTRL+C on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9634d-130">Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="9634d-130">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="9634d-131">Coloque el cursor donde desee pegar el functoid.</span><span class="sxs-lookup"><span data-stu-id="9634d-131">Place the cursor where you wish to paste the functoid.</span></span>  
  
5.  <span data-ttu-id="9634d-132">Haga doble clic en la página de cuadrícula y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="9634d-132">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="9634d-133">Como alternativa, puede hacer clic en **pegar** desde el Visual Studio **editar** menú o presionar CTRL+V en el teclado.</span><span class="sxs-lookup"><span data-stu-id="9634d-133">Alternatively, you can either click **Paste** from the Visual Studio’s **Edit** menu or press CTRL+V on the keyboard.</span></span> <span data-ttu-id="9634d-134">Aparece una copia del functoid o grupo de functoids seleccionado en la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="9634d-134">A copy of the selected functoid or group of functoids appears at the new location.</span></span>  
  
### <a name="to-cut-and-paste-a-functoid"></a><span data-ttu-id="9634d-135">Procedimiento para cortar y pegar un functoid</span><span class="sxs-lookup"><span data-stu-id="9634d-135">To cut and paste a functoid</span></span>  
  
1.  <span data-ttu-id="9634d-136">En el Explorador de soluciones, abra el proyecto BizTalk y haga doble clic en el mapa para abrirlo en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9634d-136">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="9634d-137">Seleccione el functoid que desee cortar.</span><span class="sxs-lookup"><span data-stu-id="9634d-137">Select the functoid you want to cut.</span></span> <span data-ttu-id="9634d-138">Para seleccionar varios functoids, haga clic en un functoid, mantenga presionada la tecla CTRL y haga clic en los demás functoids.</span><span class="sxs-lookup"><span data-stu-id="9634d-138">To select multiple functoids, click one functoid, hold down the CTRL key, and then click the other functoids.</span></span>  
  
3.  <span data-ttu-id="9634d-139">Haga clic en la selección y, a continuación, haga clic en **cortar**.</span><span class="sxs-lookup"><span data-stu-id="9634d-139">Right-click the selection, and then click **Cut**.</span></span> <span data-ttu-id="9634d-140">Como alternativa, puede hacer clic en **cortar** desde el Visual Studio **editar** menú o presionar CTRL+X en el teclado.</span><span class="sxs-lookup"><span data-stu-id="9634d-140">Alternatively, you can either click **Cut** from the Visual Studio’s **Edit** menu or press CTRL+X on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9634d-141">Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="9634d-141">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="9634d-142">Coloque el cursor donde desee pegar el functoid.</span><span class="sxs-lookup"><span data-stu-id="9634d-142">Place the cursor where you wish to paste the functoid.</span></span>  
  
5.  <span data-ttu-id="9634d-143">Haga doble clic en la página de cuadrícula y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="9634d-143">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="9634d-144">Como alternativa, puede hacer clic en **pegar** desde el Visual Studio **editar** menú o presionar CTRL+V en el teclado.</span><span class="sxs-lookup"><span data-stu-id="9634d-144">Alternatively, you can either click **Paste** from the Visual Studio’s **Edit** menu or press CTRL+V on the keyboard.</span></span> <span data-ttu-id="9634d-145">El functoid o grupo de functoids seleccionado se elimina de la ubicación existente y aparece en la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="9634d-145">The selected functoid or group of functoids are deleted from the existing location and appear at the new location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9634d-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="9634d-146">See Also</span></span>  
 [<span data-ttu-id="9634d-147">Utilizar Functoids para crear asignaciones más complejas.</span><span class="sxs-lookup"><span data-stu-id="9634d-147">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)