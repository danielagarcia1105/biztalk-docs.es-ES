---
title: Cómo copiar, cortar y pegar vínculos y Functoids | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80b4792a-5ff6-4603-96cd-b3d3d530c12f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eec0ddc164af936e1c3739e4da167753a6e58c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250372"
---
# <a name="how-to-copy-cut-and-paste-links-and-functoids"></a><span data-ttu-id="66af8-102">Cómo copiar, cortar y pegar vínculos y functoids</span><span class="sxs-lookup"><span data-stu-id="66af8-102">How to Copy, Cut, and Paste Links and Functoids</span></span>
<span data-ttu-id="66af8-103">La característica de copiar, cortar y pegar del Asignador de BizTalk permite la reutilización de una relación.</span><span class="sxs-lookup"><span data-stu-id="66af8-103">The copy/cut/paste feature in the BizTalk Mapper enables the reusability of a relationship.</span></span> <span data-ttu-id="66af8-104">En este tema se proporcionan instrucciones detalladas para copiar y cortar functoids y/o vínculos de una asignación, así como pegarlos en ella.</span><span class="sxs-lookup"><span data-stu-id="66af8-104">This topic provides step-by-step instructions to copy, cut, and paste functoids and/or links in a map.</span></span>  
  
 <span data-ttu-id="66af8-105">Puede usar la característica de copiar y pegar cuando desee reutilizar un conjunto de functoids y/o vínculos.</span><span class="sxs-lookup"><span data-stu-id="66af8-105">You can use the copy/paste feature when you want to reuse a set of functoids and/or links.</span></span> <span data-ttu-id="66af8-106">Y, cuando desee eliminar la selección de la ubicación existente y moverla a una nueva ubicación, puede usar la característica de cortar y pegar.</span><span class="sxs-lookup"><span data-stu-id="66af8-106">And, when you want to remove the selection from the existing location and move it to a new location, you can use the cut/paste feature.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="66af8-107">¿Cree que las características de cortar y pegar y la característica de mover son similares?</span><span class="sxs-lookup"><span data-stu-id="66af8-107">Do you feel cut/paste feature and the move feature are similar?</span></span> <span data-ttu-id="66af8-108">Hay una diferencia.</span><span class="sxs-lookup"><span data-stu-id="66af8-108">There is a difference.</span></span> <span data-ttu-id="66af8-109">Cuando selecciona cortar, solo los functoids o los vínculos de la selección se quitan de la página de cuadrícula de origen.</span><span class="sxs-lookup"><span data-stu-id="66af8-109">When you select cut, only the functoids and/or links in your selection are removed from the source grid page.</span></span> <span data-ttu-id="66af8-110">Pero, cuando selecciona mover, todos los functoids y los vínculos de la relación (independientemente de la selección), de forma recursiva, se eliminan de la página de cuadrícula de origen.</span><span class="sxs-lookup"><span data-stu-id="66af8-110">But, when you select move, all the functoids and links in the relationship (irrespective of the selection), recursively, are removed from the source grid page.</span></span> <span data-ttu-id="66af8-111">Para obtener más información acerca de cómo mover una relación, vea [cómo mover una relación entre páginas de cuadrícula](../core/how-to-move-a-relationship-between-grid-pages.md).</span><span class="sxs-lookup"><span data-stu-id="66af8-111">For more information about moving a relationship, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
 <span data-ttu-id="66af8-112">Cuando copia o corta un conjunto de functoids o vínculos, se conservan los functoids, las etiquetas, los comentarios y los valores constantes (junto con los marcadores correctos) asociados a ese conjunto.</span><span class="sxs-lookup"><span data-stu-id="66af8-112">When you copy/cut a set of functoids and/or links, the functoids, labels, comments, and the constant values (along with the correct place holders) associated with that set are retained.</span></span>  
  
 <span data-ttu-id="66af8-113">Solamente se pueden copiar y cortar estos elementos de asignación:</span><span class="sxs-lookup"><span data-stu-id="66af8-113">You can copy/cut only these map items:</span></span>  
  
-   <span data-ttu-id="66af8-114">Vínculo de origen al esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="66af8-114">Link from source to target schema.</span></span>  
  
-   <span data-ttu-id="66af8-115">Vínculo de functoid a nodo de esquema, únicamente si el “functoid” también se selecciona junto con el vínculo</span><span class="sxs-lookup"><span data-stu-id="66af8-115">Link from functoid to schema node, if and only if the “functoid” is also selected along with the link.</span></span>  
  
-   <span data-ttu-id="66af8-116">Vínculo de functoid a functoid, únicamente si ambos functoids se seleccionan junto con el vínculo.</span><span class="sxs-lookup"><span data-stu-id="66af8-116">Link from functoid to functoid, if and only if both the functoids are selected along with the link.</span></span>  
  
 <span data-ttu-id="66af8-117">Puede copiar y pegar functoids y/o vínculos de:</span><span class="sxs-lookup"><span data-stu-id="66af8-117">You can copy/cut functoids and/or links from:</span></span>  
  
-   <span data-ttu-id="66af8-118">Dentro de la misma página de cuadrícula de un mapa</span><span class="sxs-lookup"><span data-stu-id="66af8-118">Within the same grid page of a map</span></span>  
  
-   <span data-ttu-id="66af8-119">Una página de cuadrícula a las otras del mismo mapa</span><span class="sxs-lookup"><span data-stu-id="66af8-119">One grid page to the other in the same map</span></span>  
  
-   <span data-ttu-id="66af8-120">Una asignación a las otras de la misma instancia de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66af8-120">One map to the other in the same instance of Visual Studio</span></span>  
  
-   <span data-ttu-id="66af8-121">Entre diferentes instancias de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66af8-121">Across different instances of Visual Studio</span></span>  
  
 <span data-ttu-id="66af8-122">Las operaciones de cortar y pegar no se pueden deshacer o rehacer.</span><span class="sxs-lookup"><span data-stu-id="66af8-122">You can undo or redo the cut and paste operations.</span></span> <span data-ttu-id="66af8-123">Para obtener más información, consulte [cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md).</span><span class="sxs-lookup"><span data-stu-id="66af8-123">For more information, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
 <span data-ttu-id="66af8-124">Además de esto, debe tener en cuenta lo siguiente al pegar vínculos:</span><span class="sxs-lookup"><span data-stu-id="66af8-124">In addition to this, you must consider the following points while pasting links:</span></span>  
  
-   <span data-ttu-id="66af8-125">Un vínculo entre el esquema de origen y el de destino únicamente se puede pegar si la asignación actual, donde se pega el vínculo, contiene un nodo de origen, así como un nodo de destino cuya XPath es idéntica a la XPath de los nodos de origen y de destino del vínculo que se pega.</span><span class="sxs-lookup"><span data-stu-id="66af8-125">A link between the source and target schema can be pasted if and only if the current map, where the link is being pasted, contains a source node as well as a target node whose XPath is identical to the XPath of the source and target nodes for the link being pasted.</span></span>  
  
-   <span data-ttu-id="66af8-126">Un vínculo entre el esquema de origen y el de destino únicamente se puede pegar si no hay ningún vínculo existente entre el origen indicado y los nodos de destino.</span><span class="sxs-lookup"><span data-stu-id="66af8-126">A link between the source and target schema can be pasted if and only if there is no existing link between the aforesaid source and target nodes.</span></span>  
  
-   <span data-ttu-id="66af8-127">Un vínculo de un functoid a un esquema de destino únicamente se puede pegar si existe un nodo de destino cuya XPath sea la misma que la XPath del nodo de destino del vínculo que se pega.</span><span class="sxs-lookup"><span data-stu-id="66af8-127">A link from a functoid to target schema can be pasted if and only if there exists a target node whose XPath is same as the XPath of the target node of the link being pasted.</span></span>  
  
-   <span data-ttu-id="66af8-128">Un vínculo de un esquema de origen a un functoid únicamente se puede pegar si existe un nodo de origen cuya XPath sea la misma que la XPath del nodo de origen del vínculo que se pega.</span><span class="sxs-lookup"><span data-stu-id="66af8-128">A link from a source schema to a functoid can be pasted if and only if there exists a source node whose XPath is same as the XPath of the source node of the link being pasted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66af8-129">Cuando selecciona varios elementos (vínculos o functoids) de modo que algunos de ellos no se pueden cortar o copiar, al ejecutar el comando cortar o copiar, la barra de estado de Visual Studio muestra el mensaje de advertencia en el que se indica que no se pudieron cortar o copiar algunos de los elementos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="66af8-129">When you select multiple items (links and/or functoids) such that some of them cannot be cut/copied, then on executing the cut/copy command, the status bar in Visual Studio displays a warning message “Some of the selected items could not be cut/copied.”</span></span> <span data-ttu-id="66af8-130">El mensaje también muestra información relevante.</span><span class="sxs-lookup"><span data-stu-id="66af8-130">The message also displays relevant details.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="66af8-131">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="66af8-131">Prerequisites</span></span>  
 <span data-ttu-id="66af8-132">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="66af8-132">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-and-paste-a-relationship"></a><span data-ttu-id="66af8-133">Procedimiento para copiar y pegar una relación</span><span class="sxs-lookup"><span data-stu-id="66af8-133">To copy and paste a relationship</span></span>  
  
1.  <span data-ttu-id="66af8-134">En el Explorador de soluciones, abra el proyecto BizTalk y haga doble clic en el mapa para abrirlo en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="66af8-134">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="66af8-135">Seleccione los functoids y/o los vínculos que desee copiar.</span><span class="sxs-lookup"><span data-stu-id="66af8-135">Select the functoids and/or links you want to copy.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="66af8-136">Puede realizar una selección manteniendo presionada la tecla CTRL y seleccionando a continuación los functoids y/o vínculos que desee o bien arrastrando y soltando con el mouse por los vínculos para formar una selección rectangular.</span><span class="sxs-lookup"><span data-stu-id="66af8-136">You can select either by holding down the CTRL key, and then selecting the desired functoids and/or links or by dragging and dropping the mouse across the links to form a rectangular selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66af8-137">Puede usar la operación "seleccionar en la cinta" para seleccionar varios vínculos o functoids.</span><span class="sxs-lookup"><span data-stu-id="66af8-137">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="66af8-138">Para obtener más información, consulte [cómo seleccionar varios vínculos y Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span><span class="sxs-lookup"><span data-stu-id="66af8-138">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="66af8-139">Haga clic en la selección.</span><span class="sxs-lookup"><span data-stu-id="66af8-139">Right-click the selection.</span></span> <span data-ttu-id="66af8-140">y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="66af8-140">and then click **Copy**.</span></span> <span data-ttu-id="66af8-141">Como alternativa, puede presionar CTRL+C en el teclado.</span><span class="sxs-lookup"><span data-stu-id="66af8-141">Alternatively, you can press CTRL+C on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66af8-142">Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="66af8-142">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="66af8-143">Coloque el cursor donde desee pegar la selección.</span><span class="sxs-lookup"><span data-stu-id="66af8-143">Place the cursor where you wish to paste the selection.</span></span>  
  
5.  <span data-ttu-id="66af8-144">Haga doble clic en la página de cuadrícula y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="66af8-144">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="66af8-145">También puede seleccionar y presionar CTRL+V en el teclado.</span><span class="sxs-lookup"><span data-stu-id="66af8-145">Alternatively, you can select and press CTRL+V on the keyboard.</span></span> <span data-ttu-id="66af8-146">Aparece una copia de la selección en la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="66af8-146">A copy of the selection appears at the new location.</span></span>  
  
### <a name="to-cut-and-paste-a-relationship"></a><span data-ttu-id="66af8-147">Procedimiento para cortar y pegar una relación</span><span class="sxs-lookup"><span data-stu-id="66af8-147">To cut and paste a relationship</span></span>  
  
1.  <span data-ttu-id="66af8-148">En el Explorador de soluciones, abra el proyecto BizTalk y haga doble clic en el mapa para abrirlo en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="66af8-148">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="66af8-149">Seleccione los functoids y/o los vínculos que desee cortar.</span><span class="sxs-lookup"><span data-stu-id="66af8-149">Select the functoids and/or links you want to cut.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="66af8-150">Puede realizar una selección manteniendo presionada la tecla CTRL y seleccionando a continuación los functoids y/o vínculos que desee o bien arrastrando y soltando con el mouse por los vínculos para formar una selección rectangular.</span><span class="sxs-lookup"><span data-stu-id="66af8-150">You can select either by holding down the CTRL key, and then selecting the desired functoids and/or links or by dragging and dropping the mouse across the links to form a rectangular selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66af8-151">Puede usar la operación "seleccionar en la cinta" para seleccionar varios vínculos o functoids.</span><span class="sxs-lookup"><span data-stu-id="66af8-151">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="66af8-152">Para obtener más información, consulte [cómo seleccionar varios vínculos y Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span><span class="sxs-lookup"><span data-stu-id="66af8-152">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="66af8-153">Haga clic en la selección y, a continuación, haga clic en **cortar**.</span><span class="sxs-lookup"><span data-stu-id="66af8-153">Right-click the selection, and then click **Cut**.</span></span> <span data-ttu-id="66af8-154">Como alternativa, puede presionar CTRL+X en el teclado.</span><span class="sxs-lookup"><span data-stu-id="66af8-154">Alternatively, you can press CTRL+X on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66af8-155">Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="66af8-155">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="66af8-156">Coloque el cursor donde desee pegar la selección.</span><span class="sxs-lookup"><span data-stu-id="66af8-156">Place the cursor where you wish to paste the selection.</span></span>  
  
5.  <span data-ttu-id="66af8-157">Haga doble clic en la página de cuadrícula y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="66af8-157">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="66af8-158">También puede seleccionar y presionar CTRL+V en el teclado.</span><span class="sxs-lookup"><span data-stu-id="66af8-158">Alternatively, you can select and press CTRL+V on the keyboard.</span></span> <span data-ttu-id="66af8-159">La selección se elimina de la ubicación existente y aparece en la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="66af8-159">The selection is deleted from the existing location and appears at the new location.</span></span>