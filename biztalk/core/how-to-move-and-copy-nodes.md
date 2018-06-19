---
title: Cómo mover y copiar nodos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4f1ec14-c607-4da3-9139-73a61963b819
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55901e9ba6b27d05dccce0e547df618123ab466
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254772"
---
# <a name="how-to-move-and-copy-nodes"></a><span data-ttu-id="e6cac-102">Cómo mover y copiar nodos</span><span class="sxs-lookup"><span data-stu-id="e6cac-102">How to Move and Copy Nodes</span></span>
<span data-ttu-id="e6cac-103">Es probable que en determinadas situaciones desee mover un nodo existente a otra ubicación en el árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="e6cac-103">You will probably encounter situations where you want to move an existing node to a different location in the schema tree.</span></span> <span data-ttu-id="e6cac-104">Asimismo, puede ahorrar tiempo si copia un nodo existente y luego lo pega en una ubicación diferente en el árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="e6cac-104">You might also be able to save time by making a copy of an existing node and then pasting it into a different location in the schema tree.</span></span> <span data-ttu-id="e6cac-105">Este tema proporciona instrucciones paso a paso para realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="e6cac-105">This topic provides step-by-step instructions for performing these tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6cac-106">El Editor de BizTalk es compatible con copiar y pegar nodos solo dentro de los esquemas, no entre los esquemas.</span><span class="sxs-lookup"><span data-stu-id="e6cac-106">BizTalk Editor supports copying and pasting nodes only within schemas, not between schemas.</span></span>  
  
### <a name="to-move-a-node-within-a-schema"></a><span data-ttu-id="e6cac-107">Para mover un nodo dentro de un esquema</span><span class="sxs-lookup"><span data-stu-id="e6cac-107">To move a node within a schema</span></span>  
  
1.  <span data-ttu-id="e6cac-108">Si es necesario, expanda el árbol de esquema para mostrar tanto el nodo que está moviendo como la ubicación a la que desea moverlo.</span><span class="sxs-lookup"><span data-stu-id="e6cac-108">If necessary, expand the schema tree to show both the node you are moving and the location to which you want to move it.</span></span> <span data-ttu-id="e6cac-109">Para obtener más información acerca de cómo expandir y contraer la vista de árbol de esquema, consulte [administrar la vista de árbol de esquema](../core/how-to-manage-the-schema-tree-view.md).</span><span class="sxs-lookup"><span data-stu-id="e6cac-109">For more information about expanding and collapsing the schema tree view, see [Managing the Schema Tree View](../core/how-to-manage-the-schema-tree-view.md).</span></span>  
  
2.  <span data-ttu-id="e6cac-110">Haga clic en el nodo que desea mover y, sin soltar el mouse, arrástrelo a otra ubicación del árbol.</span><span class="sxs-lookup"><span data-stu-id="e6cac-110">Click and hold the node that you want to move and drag it to another location in the tree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6cac-111">Cuando empiece a arrastrar el nodo arriba y abajo en el árbol de esquema, el puntero del mouse cambiará a una flecha arriba, abajo o de elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="e6cac-111">When you begin to drag the node up and down the schema tree, the mouse pointer changes to an Up, Down, or child arrow.</span></span> <span data-ttu-id="e6cac-112">Esta flecha indica la ubicación en la que se colocará el nodo al soltar el botón del mouse, que puede ser antes del nodo, después del nodo o como secundario del nodo.</span><span class="sxs-lookup"><span data-stu-id="e6cac-112">This arrow indicates where the node will be placed when you release the mouse button, either before the node, after the node, or as a child of the node.</span></span>  
  
#### <a name="to-copy-a-node-within-a-schema"></a><span data-ttu-id="e6cac-113">Para copiar un nodo dentro de un esquema</span><span class="sxs-lookup"><span data-stu-id="e6cac-113">To copy a node within a schema</span></span>  
  
1.  <span data-ttu-id="e6cac-114">Haga clic en el nodo que desea copiar y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="e6cac-114">Right-click the node that you want to copy, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="e6cac-115">Haga clic en el **registro** nodo o grupo en el que desea insertar el nodo copiado y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="e6cac-115">Right-click the **Record** node or group node into which you want to insert the copied node, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="e6cac-116">La copia del nodo copiado se coloca al final de los nodos secundarios de la **registro** nodo o grupo seleccionado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="e6cac-116">The copy of the copied node is placed at the end of the child nodes of the **Record** node or group node you selected in step 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6cac-117">Únicamente puede usar la funcionalidad de cortar, copiar y pegar dentro de un esquema individual;</span><span class="sxs-lookup"><span data-stu-id="e6cac-117">You may only use cut/copy/paste functionality within a single schema.</span></span> <span data-ttu-id="e6cac-118">es decir, no puede copiar nodos de un esquema a otro.</span><span class="sxs-lookup"><span data-stu-id="e6cac-118">In other words, you cannot copy nodes from one schema into another schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6cac-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6cac-119">See Also</span></span>  
 [<span data-ttu-id="e6cac-120">Trabajar con nodos existentes</span><span class="sxs-lookup"><span data-stu-id="e6cac-120">Working with Existing Nodes</span></span>](../core/working-with-existing-nodes.md)