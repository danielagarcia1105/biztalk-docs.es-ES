---
title: "Cómo insertar un registro, el elemento de campo o el nodo de atributo de campo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c26f2281-f1b8-4788-8593-8d6ad29a53f0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1341a0f2d89070d42620396a8c86d497b5d646ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-insert-a-record-field-element-or-field-attribute-node"></a><span data-ttu-id="2f2af-102">Cómo insertar un registro, el elemento de campo o el nodo de atributo de campo</span><span class="sxs-lookup"><span data-stu-id="2f2af-102">How to Insert a Record, Field Element, or Field Attribute Node</span></span>
<span data-ttu-id="2f2af-103">**Registro** nodos (incluyendo el **raíz** nodo), **atributo de campo** nodos, y **elemento de campo** nodos sean únicos en que puede cambiar el nombre para que sus nombres representan los nombres de los elementos reales, con nombre personalizado en un mensaje de instancia correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2f2af-103">**Record** nodes (including the **Root** node), **Field Attribute** nodes, and **Field Element** nodes are unique in that they can be renamed so that their names represent the names of the actual, custom-named elements in a corresponding instance message.</span></span> <span data-ttu-id="2f2af-104">Por ejemplo, si asigna el nombre un **registro** nodo FullName, en la ubicación correspondiente en un mensaje de instancia que se espera un elemento XML denominado FullName.</span><span class="sxs-lookup"><span data-stu-id="2f2af-104">For example, if you name a **Record** node FullName, at the corresponding location in an instance message an XML element named FullName is expected.</span></span> <span data-ttu-id="2f2af-105">Si ese **registro** nodo denominado FullName tiene un elemento secundario **atributo de campo** nodo con el nombre RequireFullMiddleName (con sus **Min Occurs** y **Max Occurs** propiedades establecidas en **1**), el **FullName** elemento en un mensaje de instancia correspondiente deberá tener un atributo denominado **RequireFullMiddleName** asociados a él.</span><span class="sxs-lookup"><span data-stu-id="2f2af-105">If that **Record** node named FullName has a child **Field Attribute** node named RequireFullMiddleName (with its **Min Occurs** and **Max Occurs** properties set to **1**), the **FullName** element in a corresponding instance message will need to have an attribute named **RequireFullMiddleName** associated with it.</span></span>  
  
 <span data-ttu-id="2f2af-106">Todos los **registro** nodos, al insertarlos inicialmente, se representan en el esquema XSD como con un **complexType** elemento, pero no con una posterior **secuencia**, **elección** , o **todos los** elemento.</span><span class="sxs-lookup"><span data-stu-id="2f2af-106">All **Record** nodes, when initially inserted, are represented in the XSD as with a **complexType** element, but not with a subsequent **sequence**, **choice**, or **all** element.</span></span> <span data-ttu-id="2f2af-107">Por este motivo, el **Group Order Type**, **Group Max Occurs**, y **Group Min Occurs** propiedades de la **registro** nodo no están disponibles para su modificación.</span><span class="sxs-lookup"><span data-stu-id="2f2af-107">For this reason, the **Group Order Type**, **Group Max Occurs**, and **Group Min Occurs** properties of the **Record** node are not available for modification.</span></span>  
  
 <span data-ttu-id="2f2af-108">Tan pronto como se agrega un elemento secundario **registro** o **elemento de campo** nodo a la **registro** nodo, un **secuencia** elemento se agrega a la XSD representación en el **complexType** elemento para que contenga este primer nodo secundario y la **Group Order Type** propiedad de la **registro** nodo muestra un valor de **secuencia**.</span><span class="sxs-lookup"><span data-stu-id="2f2af-108">As soon as you add a child **Record** or **Field Element** node to the **Record** node, a **sequence** element is added to the XSD representation within the **complexType** element to contain this first child node, and the **Group Order Type** property of the **Record** node shows a value of **Sequence**.</span></span> <span data-ttu-id="2f2af-109">En la mayoría de los casos, puede cambiar la **Group Order Type** propiedad de **secuencia** a **elección**y, en casos más limitados, desde **secuencia**  a **todos los**, con lo que cambiar el par de elementos que contiene los nodos secundarios correspondientes a cualquiera **complexType/choice** o **complexType/all**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2f2af-109">In most circumstances, you can change the **Group Order Type** property from **Sequence** to **Choice**, and in more limited circumstances, from **Sequence** to **All**, thereby changing the element pair that contains the corresponding child nodes to either **complexType/choice** or **complexType/all**, respectively.</span></span>  
  
 <span data-ttu-id="2f2af-110">**Atributo de campo** nodos no pueden tener los mismos nombres de nodo mientras estén en el mismo ámbito.</span><span class="sxs-lookup"><span data-stu-id="2f2af-110">**Field Attribute** nodes cannot have the same node names while in the same scope.</span></span>  
  
 <span data-ttu-id="2f2af-111">**Registro** y **elemento de campo** nodos pueden tener los mismos nombres de nodo mientras estén en el mismo ámbito solo si se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f2af-111">**Record** and **Field Element** nodes can have the same node names while in the same scope only if the following conditions are met:</span></span>  
  
-   <span data-ttu-id="2f2af-112">Tienen el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="2f2af-112">They have the same data type.</span></span>  
  
-   <span data-ttu-id="2f2af-113">No están en un **todos los grupos** nodo.</span><span class="sxs-lookup"><span data-stu-id="2f2af-113">They are not within an **All Group** node.</span></span>  
  
### <a name="to-insert-a-new-child-record-node-field-element-node-or-field-attribute-node-within-the-schema-node-or-an-existing-record-node"></a><span data-ttu-id="2f2af-114">Para insertar un nodo secundario Registro, Elemento de campo o Atributo de campo nuevo en el nodo Esquema o en un nodo Registro existente</span><span class="sxs-lookup"><span data-stu-id="2f2af-114">To insert a new child Record node, Field Element node, or Field Attribute node within the Schema node or an existing Record node</span></span>  
  
1.  <span data-ttu-id="2f2af-115">Seleccione el **esquema** nodo o una existente **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="2f2af-115">Select the **Schema** node or an existing **Record** node.</span></span>  
  
2.  <span data-ttu-id="2f2af-116">En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**, **elemento de campo secundario**, o  **Atributo de campo secundario**, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="2f2af-116">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Child Record**, **Child Field Element**, or **Child Field Attribute**, as appropriate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f2af-117">Un nodo secundario del tipo elegido se agrega después el último nodo del árbol de esquema (si se inserta en la **esquema** nodo) o después del último nodo secundario existente del seleccionado **registro** nodo (cuando Insertar dentro de una existente **registro** nodo).</span><span class="sxs-lookup"><span data-stu-id="2f2af-117">A child node of the chosen type is added after either the last node in the schema tree (when inserting within the **Schema** node) or after the last existing child node of the selected **Record** node (when inserting within an existing **Record** node).</span></span>  
  
3.  <span data-ttu-id="2f2af-118">Escriba un nombre para las filas recién insertadas **registro**, **elemento de campo**, o **atributo de campo** nodo y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="2f2af-118">Type a name for the newly inserted **Record**, **Field Element**, or **Field Attribute** node, and then press ENTER.</span></span>  
  
### <a name="to-insert-a-sibling-record-node-field-attribute-node-or-field-element-node-within-an-existing-record-node"></a><span data-ttu-id="2f2af-119">Para insertar en un nodo Registro existente un nodo Registro, Atributo de campo o Elemento de campo que esté en el mismo nivel</span><span class="sxs-lookup"><span data-stu-id="2f2af-119">To insert a sibling Record node, Field Attribute node, or Field Element node within an existing Record node</span></span>  
  
1.  <span data-ttu-id="2f2af-120">Seleccione cualquier nodo secundario de la **registro** en la que desea insertar el elemento relacionado del nodo **registro**, **atributo de campo**, o **elemento de campo** nodo.</span><span class="sxs-lookup"><span data-stu-id="2f2af-120">Select any child node of the **Record** node into which you want to insert the sibling **Record**, **Field Attribute**, or **Field Element** node.</span></span>  
  
2.  <span data-ttu-id="2f2af-121">En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **Registro hermano**, **atributo de campo hermano**, o **Elemento de campo hermano**, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="2f2af-121">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sibling Record**, **Sibling Field Attribute**, or **Sibling Field Element**, as appropriate.</span></span>  
  
     <span data-ttu-id="2f2af-122">Se inserta un nodo del tipo elegido que tiene el mismo nivel al final de los elementos del mismo nivel del nodo elegido.</span><span class="sxs-lookup"><span data-stu-id="2f2af-122">A sibling node of the chosen type is inserted at the end of the siblings of the selected node.</span></span>  
  
3.  <span data-ttu-id="2f2af-123">Escriba un nombre para las filas recién insertadas **registro**, **atributo de campo**, o **elemento de campo** nodo y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="2f2af-123">Type a name for the newly inserted **Record**, **Field Attribute**, or **Field Element** node, and then press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f2af-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f2af-124">See Also</span></span>  
 [<span data-ttu-id="2f2af-125">Insertar nodos en un esquema</span><span class="sxs-lookup"><span data-stu-id="2f2af-125">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)