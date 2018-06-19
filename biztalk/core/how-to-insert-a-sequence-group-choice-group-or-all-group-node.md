---
title: Cómo insertar un grupo de secuencias, grupo de elecciones o nodo de todos los grupos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19aee400-1369-4310-b1b4-1bfeb2643236
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e498eb5ec8e7aa1398cfb58732f978faa9d0b415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254844"
---
# <a name="how-to-insert-a-sequence-group-choice-group-or-all-group-node"></a><span data-ttu-id="8e6fc-102">Cómo insertar un grupo de secuencias, grupo de elecciones o nodo de todos los grupos</span><span class="sxs-lookup"><span data-stu-id="8e6fc-102">How to Insert a Sequence Group, Choice Group, or All Group Node</span></span>
<span data-ttu-id="8e6fc-103">El Editor de BizTalk admite tres tipos de nodos de grupo para los elementos: **grupo de secuencias**, **grupo de elecciones**, y **todos los grupos**.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-103">BizTalk Editor supports three types of group nodes for elements: **Sequence Group**, **Choice Group**, and **All Group**.</span></span> <span data-ttu-id="8e6fc-104">Estos tipos de nodos de grupo establecen distintas restricciones en los nodos secundarios del grupo de los mensajes de instancia correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-104">These different types of group nodes establish different constraints on the child nodes of the group in corresponding instance messages.</span></span> <span data-ttu-id="8e6fc-105">Para obtener información acerca de las restricciones de estos tipos de nodos de grupo, consulte directamente la información disponible en Internet sobre el lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="8e6fc-105">For information about the constraints of these different types of groups, you should refer directly to information about the XML Schema definition (XSD) language on the Web.</span></span> <span data-ttu-id="8e6fc-106">Para obtener vínculos a esta información, consulte [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).</span><span class="sxs-lookup"><span data-stu-id="8e6fc-106">For links to this information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="8e6fc-107">El Editor de BizTalk también admite un nodo de grupo para los atributos, los **grupo de atributos** nodo.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-107">BizTalk Editor also supports a group node for attributes, the **Attribute Group** node.</span></span> <span data-ttu-id="8e6fc-108">Este tipo de nodo permite un conjunto de atributos que debe definirse una vez y, a continuación, puede asociar con más de un **registro** nodo dentro del esquema.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-108">This type of node allows a set of attributes to be defined once, and then be associated with more than one **Record** node within the schema.</span></span>  
  
 <span data-ttu-id="8e6fc-109">Cuando se genera el esquema, la estructura **registro** nodos se supone que contienen secuencias ordenadas de nodos secundarios de forma predeterminada y se representan mediante el uso de **secuencia** elementos en la representación XSD del el esquema.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-109">When you build structure into your schema, **Record** nodes are assumed to contain ordered sequences of child nodes by default, and are represented by using **sequence** elements in the XSD representation of the schema.</span></span> <span data-ttu-id="8e6fc-110">Puede cambiar el tipo de un nodo de grupo cambiando su **Order Type** propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-110">You can change the type of a group node by changing its **Order Type** property.</span></span>  
  
### <a name="to-insert-a-sequence-group-node-or-a-choice-group-node"></a><span data-ttu-id="8e6fc-111">Para insertar un nodo Grupo de secuencias o Grupo de elecciones</span><span class="sxs-lookup"><span data-stu-id="8e6fc-111">To insert a Sequence Group node or a Choice Group node</span></span>  
  
1.  <span data-ttu-id="8e6fc-112">En la vista de árbol de esquema, seleccione la **registro** nodo en el que desea insertar el **grupo de secuencias** nodo o la **grupo de elecciones** nodo.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-112">In the schema tree view, select the **Record** node in which you want to insert the **Sequence Group** node or the **Choice Group** node.</span></span>  
  
2.  <span data-ttu-id="8e6fc-113">En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **grupo de secuencias** o **grupo de elecciones**, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-113">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sequence Group** or **Choice Group**, as appropriate.</span></span>  
  
### <a name="to-insert-an-all-group-node"></a><span data-ttu-id="8e6fc-114">Para insertar un nodo Todos los grupos</span><span class="sxs-lookup"><span data-stu-id="8e6fc-114">To insert an All Group node</span></span>  
  
1.  <span data-ttu-id="8e6fc-115">En la vista de árbol de esquema, seleccione la nueva **registro** nodo en el que desea insertar el **todos los grupos** nodo.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-115">In the schema tree view, select the new **Record** node in which you want to insert the **All Group** node.</span></span>  
  
2.  <span data-ttu-id="8e6fc-116">En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **todos los grupos**.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-116">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **All Group**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e6fc-117">El **todos los grupos** opción sólo está disponible en el menú BizTalk (o contextual) cuando el elemento primario relevante **registro** nodo cumple las restricciones que XSD impone el uso de la **todoslos**elemento.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-117">The **All Group** choice is only available on the BizTalk (or shortcut) menu when the relevant parent **Record** node meets the constraints that XSD imposes on the use of the **all** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e6fc-118">El **todos los grupos** opción requiere que el **registro** nodo tiene un tipo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-118">The **All Group** choice requires that the **Record** node have a base data type.</span></span> <span data-ttu-id="8e6fc-119">Es una forma rápida de dar el nodo de un tipo de datos establecer su **tipo de contenido** a **complejos**.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-119">A quick way to give the node a data type is to set its **Content Type** to **Complex**.</span></span>  
  
### <a name="to-insert-an-attribute-group-node"></a><span data-ttu-id="8e6fc-120">Para insertar un nodo Grupo de atributos</span><span class="sxs-lookup"><span data-stu-id="8e6fc-120">To insert an Attribute Group node</span></span>  
  
1.  <span data-ttu-id="8e6fc-121">En la vista de árbol de esquema, seleccione la **registro** nodo en el que desea insertar el **grupo de atributos** nodo.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-121">In the schema tree view, select the **Record** node in which you want to insert the **Attribute Group** node.</span></span>  
  
2.  <span data-ttu-id="8e6fc-122">En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **grupo de atributos**.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-122">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Attribute Group**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e6fc-123">Si desea cambiar el nombre de las filas recién insertadas **grupo de atributos** nodo, escriba el nuevo nombre en su **Group Reference** propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e6fc-123">If you want to change the name of the newly inserted **Attribute Group** node, type the new name in its **Group Reference** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e6fc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e6fc-124">See Also</span></span>  
 [<span data-ttu-id="8e6fc-125">Insertar nodos en un esquema</span><span class="sxs-lookup"><span data-stu-id="8e6fc-125">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)