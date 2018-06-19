---
title: Cómo cambiar el tamaño del selector de esquema y expandir y contraer los árboles de esquema | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 267ea17d-54fe-4031-a044-719606489f24
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972be8ca5f412c39e1eb6fa2c81ccd9a21e65a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254820"
---
# <a name="how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees"></a><span data-ttu-id="169ab-102">Cómo cambiar el tamaño del selector de esquema y expandir y contraer los árboles de esquema</span><span class="sxs-lookup"><span data-stu-id="169ab-102">How to resize the schema picker, and expand and collapse the schema trees</span></span>
<span data-ttu-id="169ab-103">Al desarrollar asignaciones de BizTalk, es probable que necesite expandir y contraer los árboles de esquema de origen y de destino para mostrar u ocultar los diversos nodos de esquema.</span><span class="sxs-lookup"><span data-stu-id="169ab-103">When developing BizTalk maps, you are likely to need to expand and collapse the source and destination schema trees to expose or to hide the various schema nodes.</span></span> <span data-ttu-id="169ab-104">Este tema proporciona instrucciones paso a paso para cambiar el tamaño del selector de esquema y para expandir y contraer el árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="169ab-104">This topic provides step-by-step instructions to resize the schema picker, and to expand and collapse the schema tree.</span></span>  

## <a name="resize-the-schema-picker"></a><span data-ttu-id="169ab-105">Cambiar el tamaño del selector de esquema</span><span class="sxs-lookup"><span data-stu-id="169ab-105">Resize the schema picker</span></span>

<span data-ttu-id="169ab-106">Cuando se crea un mapa, agrega un esquema de origen y un esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="169ab-106">When you create a map, you add a source schema, and a destination schema.</span></span> <span data-ttu-id="169ab-107">Al agregar o reemplazar un esquema, se abre la ventana del selector de tipos de BizTalk y seleccione el esquema.</span><span class="sxs-lookup"><span data-stu-id="169ab-107">When you add or replace a schema, the BizTalk Type Picker window opens, and you select your schema.</span></span> 

<span data-ttu-id="169ab-108">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , puede cambiar el tamaño de esta ventana de selector de tipos.</span><span class="sxs-lookup"><span data-stu-id="169ab-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize this Type Picker window.</span></span> <span data-ttu-id="169ab-109">Esta característica permite ver el nombre completo del esquema.</span><span class="sxs-lookup"><span data-stu-id="169ab-109">This feature allows you to see the full name of your schema.</span></span>

1. <span data-ttu-id="169ab-110">En el mapa, seleccione **Abrir esquema de destino**, o **Abrir esquema de origen**.</span><span class="sxs-lookup"><span data-stu-id="169ab-110">In your map, select **Open Destination Schema**, or **Open Source Schema**.</span></span>
2. <span data-ttu-id="169ab-111">En el **selector de tipos de BizTalk** ventana, arrastre la esquina inferior derecha esquina para aumentar o disminuir el tamaño de la ventana.</span><span class="sxs-lookup"><span data-stu-id="169ab-111">In the **BizTalk Type Picker** window, drag the bottom-right corner to increase or decrease the window size.</span></span>
  
## <a name="expand-all-or-part-of-a-schema-tree"></a><span data-ttu-id="169ab-112">Expandir todo o parte de un árbol de esquema</span><span class="sxs-lookup"><span data-stu-id="169ab-112">Expand all or part of a schema tree</span></span>  
  
1.  <span data-ttu-id="169ab-113">Seleccione el nodo en el que desea expandir completamente el árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="169ab-113">Select the node under which you want to completely expand the schema tree.</span></span>  
  
     <span data-ttu-id="169ab-114">El nodo seleccionado debe tener junto a él un icono más (+) o menos (-).</span><span class="sxs-lookup"><span data-stu-id="169ab-114">The selected node must be a node with a plus (+) or minus (-) icon next to it.</span></span>  
  
2.  <span data-ttu-id="169ab-115">En el **BizTalk** menú, o en el menú contextual para ese nodo, haga clic en **Expandir nodo de árbol**.</span><span class="sxs-lookup"><span data-stu-id="169ab-115">On the **BizTalk** menu, or on the shortcut menu for that node, click **Expand Tree Node**.</span></span> <span data-ttu-id="169ab-116">Todos los nodos situados por debajo del nodo seleccionado se expandirán completamente.</span><span class="sxs-lookup"><span data-stu-id="169ab-116">All nodes below the selected node are completely expanded.</span></span>  
  
     <span data-ttu-id="169ab-117">Si el árbol de esquema debajo del nodo seleccionado ya está completamente expandido, el **Expandir nodo de árbol** elemento de menú está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="169ab-117">If the schema tree below the selected node is already completely expanded, the **Expand Tree Node** menu item is disabled.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="169ab-118">Como alternativa, puede presionar CTRL+M, E para expandir los nodos del árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="169ab-118">Alternatively you can press CTRL+M, E to expand the schema tree nodes.</span></span> <span data-ttu-id="169ab-119">Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="169ab-119">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="169ab-120">En un esquema grande y complejo, al hacer clic en **Expandir nodo de árbol** en un nodo que contenga tipos complejos, algunos nodos en el esquema pueden permanecer en el estado contraído.</span><span class="sxs-lookup"><span data-stu-id="169ab-120">In a large and complex schema, when you click **Expand Tree Node** on a node that contains complex types, some nodes in the schema may remain in the collapsed state.</span></span> <span data-ttu-id="169ab-121">Esto se debe a que el proceso recursivo expande solo el primer caso de un tipo complejo determinado.</span><span class="sxs-lookup"><span data-stu-id="169ab-121">This is because the recursive process expands only the first occurrence of a given complex type.</span></span> <span data-ttu-id="169ab-122">Deberá expandir manualmente los casos posteriores del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="169ab-122">You must manually expand later occurrences of the same type.</span></span> <span data-ttu-id="169ab-123">Este comportamiento está diseñado para optimizar el rendimiento a la hora de expandir nodos en esquemas grandes y complejos.</span><span class="sxs-lookup"><span data-stu-id="169ab-123">This behavior is designed to optimize performance when expanding nodes in large and complex schemas.</span></span>  
  
## <a name="collapse-all-or-part-of-a-schema-tree"></a><span data-ttu-id="169ab-124">Contraer todo o parte de un árbol de esquema</span><span class="sxs-lookup"><span data-stu-id="169ab-124">Collapse all or part of a schema tree</span></span>  
  
1.  <span data-ttu-id="169ab-125">Seleccione el nodo en el que desea contraer completamente el árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="169ab-125">Select the node under which you want to completely collapse the schema tree.</span></span>  
  
     <span data-ttu-id="169ab-126">El nodo seleccionado debe tener junto a él un icono más (+) o menos (-).</span><span class="sxs-lookup"><span data-stu-id="169ab-126">The selected node must be a node with a plus (+) or minus (-) icon next to it.</span></span>  
  
2.  <span data-ttu-id="169ab-127">En el **BizTalk** menú, o en el menú contextual para ese nodo, haga clic en **Contraer nodo de árbol**.</span><span class="sxs-lookup"><span data-stu-id="169ab-127">On the **BizTalk** menu, or on the shortcut menu for that node, click **Collapse Tree Node**.</span></span>  
  
     <span data-ttu-id="169ab-128">Todos los nodos situados por debajo del nodo seleccionado se contraerán completamente.</span><span class="sxs-lookup"><span data-stu-id="169ab-128">All nodes below the selected node are completely collapsed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="169ab-129">Como alternativa, puede presionar CTRL+M, C para contraer los nodos del árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="169ab-129">Alternatively you can press CTRL+M, C to collapse the schema tree nodes.</span></span> <span data-ttu-id="169ab-130">Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="169ab-130">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="169ab-131">Si el árbol de esquema debajo del nodo seleccionado ya está contraído, el **Contraer nodo de árbol** elemento de menú está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="169ab-131">If the schema tree below the selected node is already collapsed, the **Collapse Tree Node** menu item is disabled.</span></span>  
  
 <span data-ttu-id="169ab-132">Esta operación no recordará la configuración individual de expansión o contracción de los nodos situados por debajo del nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="169ab-132">This operation will not remember the individual expand and collapse settings of the nodes below the selected node.</span></span> <span data-ttu-id="169ab-133">Cuando vuelva a expandir un nodo contraído, la configuración previa se pierde y debe expandir el árbol de esquema situado por debajo de ese punto nodo por nodo, o bien expandirlo por completo.</span><span class="sxs-lookup"><span data-stu-id="169ab-133">When you re-expand the collapsed node, previous settings are lost, and you must expand the schema tree below that point node-by-node, or expand it entirely.</span></span>  
  
### <a name="expand-a-node"></a><span data-ttu-id="169ab-134">Expanda un nodo</span><span class="sxs-lookup"><span data-stu-id="169ab-134">Expand a node</span></span>
  
-   <span data-ttu-id="169ab-135">Haga clic en el icono más (+) que se encuentra junto al nodo que desea expandir.</span><span class="sxs-lookup"><span data-stu-id="169ab-135">Click the plus (+) icon next to the node you want to expand.</span></span>  
  
 <span data-ttu-id="169ab-136">Se expande el nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="169ab-136">The selected node is expanded.</span></span> <span data-ttu-id="169ab-137">El hecho de que sus nodos descendentes se expandan o contraigan dependerá de cómo se contrajo el nodo seleccionado y de su configuración de expansión y contracción previa.</span><span class="sxs-lookup"><span data-stu-id="169ab-137">Whether or not its descendent nodes are expanded or collapsed depends on how the selected node was collapsed and their previous expand and collapse settings.</span></span>  
  
### <a name="collapse-a-node"></a><span data-ttu-id="169ab-138">Contraer un nodo</span><span class="sxs-lookup"><span data-stu-id="169ab-138">Collapse a node</span></span>
  
-   <span data-ttu-id="169ab-139">Haga clic en el icono menos (-) que se encuentra junto al nodo que desea contraer.</span><span class="sxs-lookup"><span data-stu-id="169ab-139">Click the minus (-) icon next to the node you want to collapse.</span></span>  
  
 <span data-ttu-id="169ab-140">Se contrae el nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="169ab-140">The selected node is collapsed.</span></span>  
  
 <span data-ttu-id="169ab-141">Esta operación se recuerde la individual de expansión y contraer la configuración de los nodos situados por debajo del nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="169ab-141">This operation will remember the individual expand and collapse settings of the nodes below the selected node.</span></span> <span data-ttu-id="169ab-142">Cuando vuelva a expandir mediante el icono más (+) un nodo contraído, la configuración individual previa no se pierde y el árbol de esquema situado por debajo de ese punto recupera su estado previo.</span><span class="sxs-lookup"><span data-stu-id="169ab-142">When you re-expand the collapsed node by using the plus (+) icon, the previous individual settings are not lost, and the schema tree below that point returns to its previous state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169ab-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="169ab-143">See Also</span></span>  
 [<span data-ttu-id="169ab-144">Con el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="169ab-144">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)