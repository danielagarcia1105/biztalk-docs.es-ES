---
title: "Cómo deshacer o rehacer operaciones de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1cb3708e-a9c2-4795-aba0-9c6d9635e08c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8358fc1624346b90d98fd1f1707dd2bfb02446dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-undo-or-redo-user-operations"></a><span data-ttu-id="c838d-102">Deshacer o rehacer operaciones de usuario</span><span class="sxs-lookup"><span data-stu-id="c838d-102">How to Undo or Redo User Operations</span></span>
<span data-ttu-id="c838d-103">La compatibilidad para deshacer/rehacer es otra facilidad de uso proporcionada por el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c838d-103">The support for undo/redo is yet another usability aid provided by the BizTalk Mapper.</span></span> <span data-ttu-id="c838d-104">Si no está satisfecho con las modificaciones que ha realizado, o si ha hecho un cambio por error, puede deshacer para volver gradualmente al estado anterior "sin tocar" y continuar desde él.</span><span class="sxs-lookup"><span data-stu-id="c838d-104">If you are not satisfied with modifications you have made, or if you have made a change by mistake, you can use undo to gradually come back to an earlier "untouched" state, and resume from there.</span></span> <span data-ttu-id="c838d-105">Rehacer permite volver a aplicar las acciones de edición que se han deshecho.</span><span class="sxs-lookup"><span data-stu-id="c838d-105">Redo allows you to reapply the editing actions that have been undone.</span></span> <span data-ttu-id="c838d-106">En este tema se proporciona información acerca de las operaciones que se pueden deshacer o rehacer.</span><span class="sxs-lookup"><span data-stu-id="c838d-106">This topic provides information about the operations that you can undo/redo.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c838d-107">Solo puede deshacer una operación si ha realizado al menos una operación de edición en el mapa.</span><span class="sxs-lookup"><span data-stu-id="c838d-107">You can undo an operation only when you have performed at least one edit operation on the map.</span></span> <span data-ttu-id="c838d-108">Rehacer no está disponible a menos que haya utilizado el comando Deshacer.</span><span class="sxs-lookup"><span data-stu-id="c838d-108">Redo is unavailable unless you have used the undo command.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c838d-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c838d-109">Prerequisites</span></span>  
 <span data-ttu-id="c838d-110">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c838d-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="what-can-you-undoredo"></a><span data-ttu-id="c838d-111">¿Qué se puede deshacer/rehacer?</span><span class="sxs-lookup"><span data-stu-id="c838d-111">What can you undo/redo?</span></span>  
 <span data-ttu-id="c838d-112">Se pueden deshacer y rehacer todas las operaciones de edición.</span><span class="sxs-lookup"><span data-stu-id="c838d-112">You can undo/redo all editing operations.</span></span> <span data-ttu-id="c838d-113">Las operaciones que se pueden deshacer/rehacer son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c838d-113">The operations that can be undone/redone are as follows:</span></span>  
  
-   <span data-ttu-id="c838d-114">cortar/copiar/pegar functoids y/o vínculos</span><span class="sxs-lookup"><span data-stu-id="c838d-114">Cutting/copying/pasting functoids and/or link</span></span>  
  
     <span data-ttu-id="c838d-115">No se puede deshacer ni rehacer un número cualquiera de elementos (vínculos o functoids) con solo seleccionarlos y copiarlos.</span><span class="sxs-lookup"><span data-stu-id="c838d-115">You cannot undo or redo any number of items (links/functoids) by simply selecting and copying them.</span></span> <span data-ttu-id="c838d-116">La función Copiar no cambia nada en la asignación.</span><span class="sxs-lookup"><span data-stu-id="c838d-116">Copy function does not change anything on the map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c838d-117">Para obtener información acerca de cómo cortar, copiar y pegar un functoid, consulte [cómo copiar, cortar y pegar un Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="c838d-117">For information about how to cut/copy/paste a functoid, see [How to Copy, Cut, and Paste a Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md).</span></span> <span data-ttu-id="c838d-118">Para obtener más información acerca de cómo cortar/copiar/pegar functoid y un vínculo, vea [cómo copiar, cortar y pegar vínculos y Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span><span class="sxs-lookup"><span data-stu-id="c838d-118">For more information about how to cut/copy/paste functoid and link, see [How to Copy, Cut, and Paste Links and Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span></span>  
  
-   <span data-ttu-id="c838d-119">Vincular un nodo de origen a uno de destino o a un functoid, un functoid a otro functoid o un functoid a un nodo de destino</span><span class="sxs-lookup"><span data-stu-id="c838d-119">Linking a source node to a target node, or a source node to a functoid, a functoid to another functoid, or a functoid to a target node</span></span>  
  
-   <span data-ttu-id="c838d-120">Eliminar functoids y/o vínculos</span><span class="sxs-lookup"><span data-stu-id="c838d-120">Deleting functoids and/or links</span></span>  
  
-   <span data-ttu-id="c838d-121">Mover vínculos y functoids seleccionados a otra página de cuadrícula</span><span class="sxs-lookup"><span data-stu-id="c838d-121">Moving selected links and functoids to another grid page</span></span>  
  
-   <span data-ttu-id="c838d-122">Agregar, mover, reordenar o eliminar páginas de cuadrícula</span><span class="sxs-lookup"><span data-stu-id="c838d-122">Adding, moving, reordering, or deleting grid pages</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c838d-123">Para obtener información sobre cómo agregar, mover, reordenar o eliminar páginas de cuadrícula, vea [cómo reorganizar páginas de cuadrícula](../core/how-to-reorder-grid-pages.md).</span><span class="sxs-lookup"><span data-stu-id="c838d-123">For information on adding, moving, reordering, or deleting grid pages, see [How to Reorder Grid Pages](../core/how-to-reorder-grid-pages.md).</span></span>  
  
-   <span data-ttu-id="c838d-124">Seleccionar esquemas de origen y destino al crear un mapa</span><span class="sxs-lookup"><span data-stu-id="c838d-124">Selecting source and destination schemas while creating a map</span></span>  
  
-   <span data-ttu-id="c838d-125">Reemplazar el esquema de origen o destino</span><span class="sxs-lookup"><span data-stu-id="c838d-125">Replacing source/destination schema</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c838d-126">Para obtener información sobre cómo reemplazar el esquema de origen o destino, consulte [cómo reemplazar esquemas](../core/how-to-replace-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="c838d-126">For information on how to replace source/destination schema, see [How to Replace Schemas](../core/how-to-replace-schemas.md).</span></span>  
  
-   <span data-ttu-id="c838d-127">Configurar parámetros de entrada para functoids</span><span class="sxs-lookup"><span data-stu-id="c838d-127">Configuring input parameters for functoids</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c838d-128">Para obtener más información, consulte [cómo configurar parámetros de entrada del Functoid](../core/how-to-configure-functoid-input-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c838d-128">For more information, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
-   <span data-ttu-id="c838d-129">Configurar o editar etiquetas para vínculos</span><span class="sxs-lookup"><span data-stu-id="c838d-129">Setting/editing labels for links</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c838d-130">Para obtener más información, consulte [cómo etiquetar un vínculo](../core/how-to-label-a-link.md).</span><span class="sxs-lookup"><span data-stu-id="c838d-130">For more information, see [How to Label a Link](../core/how-to-label-a-link.md).</span></span>  
  
-   <span data-ttu-id="c838d-131">Configurar o editar etiquetas o comentarios para functoids</span><span class="sxs-lookup"><span data-stu-id="c838d-131">Setting/editing labels and/or comments for functoids</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c838d-132">Para obtener más información, consulte [cómo etiquetar y comentar un Functoid](../core/how-to-label-and-comment-a-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="c838d-132">For more information, see [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
-   <span data-ttu-id="c838d-133">Omitir espacios de nombres para las propiedades Vínculos y Prioridad de los tipos de scripts para la cuadrícula del Asignador.</span><span class="sxs-lookup"><span data-stu-id="c838d-133">Ignore Namespaces for Links and Script Type Precedence properties for Mapper grid.</span></span>  
  
-   <span data-ttu-id="c838d-134">Reemplazar un vínculo al arrastrar un extremo de un vínculo desde un nodo o functoid a otro nodo o functoid.</span><span class="sxs-lookup"><span data-stu-id="c838d-134">Replacing a link by dragging one end point of a link from a node or functoid to anther node or functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c838d-135">Para obtener más información, consulte [cómo crear vínculos](../core/how-to-create-links.md).</span><span class="sxs-lookup"><span data-stu-id="c838d-135">For more information, see [How to Create Links](../core/how-to-create-links.md).</span></span>  
  
-   <span data-ttu-id="c838d-136">Realizar varias modificaciones en el **configurar \<Functoid\> Functoid** cuadro de diálogo que se trata como una única operación.</span><span class="sxs-lookup"><span data-stu-id="c838d-136">Performing multiple modifications in the **Configure \<Functoid\> Functoid** dialog box, which is treated as a single operation.</span></span>  
  
-   <span data-ttu-id="c838d-137">Arrastrar functoids o vínculos en la cuadrícula del Asignador.</span><span class="sxs-lookup"><span data-stu-id="c838d-137">Dragging functoid(s) and/or link(s) within the Mapper grid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c838d-138">Para obtener más información, consulte [cómo mover una relación entre páginas de cuadrícula](../core/how-to-move-a-relationship-between-grid-pages.md).</span><span class="sxs-lookup"><span data-stu-id="c838d-138">For more information, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
## <a name="how-can-you-undoredo-any-operation"></a><span data-ttu-id="c838d-139">¿Cómo se puede deshacer o rehacer cualquier operación?</span><span class="sxs-lookup"><span data-stu-id="c838d-139">How can you undo/redo any operation?</span></span>  
 <span data-ttu-id="c838d-140">Se puede deshacer o rehacer una operación de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="c838d-140">You can undo/redo an operation in one of the following ways:</span></span>  
  
-   <span data-ttu-id="c838d-141">Desde el Visual Studio **editar** menú.</span><span class="sxs-lookup"><span data-stu-id="c838d-141">From the Visual Studio’s **Edit** menu.</span></span>  
  
-   <span data-ttu-id="c838d-142">Al hacer clic en los iconos de deshacer y rehacer de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="c838d-142">Clicking the undo and redo icons on the toolbar.</span></span>  
  
-   <span data-ttu-id="c838d-143">Al presionar CTRL+Z para deshacer y CTRL+Y para rehacer.</span><span class="sxs-lookup"><span data-stu-id="c838d-143">Pressing CTRL+Z for undo and CTRL+Y for redo.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c838d-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="c838d-144">See Also</span></span>  
 [<span data-ttu-id="c838d-145">Trabajar con páginas de cuadrícula</span><span class="sxs-lookup"><span data-stu-id="c838d-145">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)