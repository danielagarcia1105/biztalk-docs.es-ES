---
title: "Cómo crear referencias a otro nodo o tipo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c60be9ad-01a9-40e7-b43b-8c3d09bbb32f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 643f39b9a42e2566f77371096d7305f56e11a328
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-references-to-another-node-or-type"></a><span data-ttu-id="b80d2-102">Crear referencias a otro nodo o tipo</span><span class="sxs-lookup"><span data-stu-id="b80d2-102">Create References to Another Node or Type</span></span>
<span data-ttu-id="b80d2-103">Puede usar nodos globales para crear tipos de datos reutilizables, fragmentos de estructura, que puede usar en todo el esquema siempre que esa estructura sea la adecuada.</span><span class="sxs-lookup"><span data-stu-id="b80d2-103">You can use global nodes to create reusable data types—fragments of structure—that you can use throughout the schema wherever that structure is appropriate.</span></span> <span data-ttu-id="b80d2-104">Solo puede usar los nodos que son elementos secundarios directos de la **esquema** nodo para crear tipos globales.</span><span class="sxs-lookup"><span data-stu-id="b80d2-104">You can only use nodes that are direct children of the **Schema** node to create global types.</span></span>  
  
 <span data-ttu-id="b80d2-105">También puede crear referencias cíclicas con los tipos de datos de nodos que no sean descendientes directos de la **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="b80d2-105">You can also create cyclical references using the data types of nodes that are not direct descendants of the **Schema** node.</span></span> <span data-ttu-id="b80d2-106">Esto resulta útil para representar estructuras recursivas en los esquemas.</span><span class="sxs-lookup"><span data-stu-id="b80d2-106">This is useful for representing recursive structures in schemas.</span></span>  
  
 <span data-ttu-id="b80d2-107">Este tema proporciona instrucciones paso a paso para varios tipos de nodos globales y sobre cómo hacer referencia a ellos para utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="b80d2-107">This topic provides step-by-step instructions for various types of global nodes and how to refer to them to use them.</span></span>  
  
 <span data-ttu-id="b80d2-108">**Crear declaraciones globales**</span><span class="sxs-lookup"><span data-stu-id="b80d2-108">**Creating Global Declarations**</span></span>  
  
 <span data-ttu-id="b80d2-109">Se pueden crear tipos globales mediante registros, campos o atributos.</span><span class="sxs-lookup"><span data-stu-id="b80d2-109">You can create global types using records, fields or attributes.</span></span> <span data-ttu-id="b80d2-110">Los tipos globales creados a partir de registros solo se pueden usar en registros; los tipos creados a partir de campos solo se pueden utilizar en campos; y los tipos de atributos, solo en atributos.</span><span class="sxs-lookup"><span data-stu-id="b80d2-110">Global types created from records may only be used in records, types created from fields only in fields, attribute types only in attributes.</span></span> <span data-ttu-id="b80d2-111">Los siguientes procedimientos describen cómo definir y utilizar declaraciones globales.</span><span class="sxs-lookup"><span data-stu-id="b80d2-111">The following procedures describe how to define and use global declarations.</span></span>  
  
## <a name="create-a-global-declaration-from-a-node"></a><span data-ttu-id="b80d2-112">Crear una declaración global a partir de un nodo</span><span class="sxs-lookup"><span data-stu-id="b80d2-112">Create a global declaration from a node</span></span>  
  
1.  <span data-ttu-id="b80d2-113">Seleccione el **registro** , **atributo de campo**, o **elemento de campo** nodo cuyo tipo desea que esté disponible globalmente.</span><span class="sxs-lookup"><span data-stu-id="b80d2-113">Select the **Record** , **Field Attribute**,or **Field Element** node whose type you want to make globally available.</span></span>  
  
2.  <span data-ttu-id="b80d2-114">En el **propiedades** ventana, escriba un nombre en el **Data Structure Type** lista que se usará como el nombre del tipo complejo global y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b80d2-114">In the **Properties** window, type a name in the **Data Structure Type** list that will be used as the global name for the complex type, and then press ENTER.</span></span>  
  
## <a name="create-a-globally-defined-sequence-group-node-choice-group-node-or-all-group-node"></a><span data-ttu-id="b80d2-115">Crear un nodo grupo de secuencia definido globalmente, el nodo grupo de elecciones o el nodo todos los grupos</span><span class="sxs-lookup"><span data-stu-id="b80d2-115">Create a globally defined Sequence Group node, Choice Group node, or All Group node</span></span>  
  
1.  <span data-ttu-id="b80d2-116">Seleccione el **registro** nodo en el que desea insertar el nodo de grupo definido globalmente.</span><span class="sxs-lookup"><span data-stu-id="b80d2-116">Select the **Record** node into which you want to insert the globally defined group node.</span></span>  
  
2.  <span data-ttu-id="b80d2-117">En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **grupo de secuencias**, **grupo de elecciones**, o **todos los Grupo**, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="b80d2-117">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sequence Group**, **Choice Group**, or **All Group**, as appropriate.</span></span>  
  
3.  <span data-ttu-id="b80d2-118">Cree una estructura en el grupo que acaba de insertar.</span><span class="sxs-lookup"><span data-stu-id="b80d2-118">Create a structure in the newly inserted group.</span></span> <span data-ttu-id="b80d2-119">Por ejemplo, insertar **registro** o **elemento de campo** nodos para expresar la estructura de los datos dentro del nodo de grupo.</span><span class="sxs-lookup"><span data-stu-id="b80d2-119">For example, insert **Record** or **Field Element** nodes to express the structure of the data within the group node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b80d2-120">Grupo de secuencias, **grupo de elecciones**, y **todos los grupos** nodos solo pueden contener nodos que corresponden a elementos XML y, por tanto, no pueden contener **atributo de campo** nodos.</span><span class="sxs-lookup"><span data-stu-id="b80d2-120">Sequence Group, **Choice Group**, and **All Group** nodes can only contain nodes that correspond to XML elements and therefore cannot contain **Field Attribute** nodes.</span></span>  
  
4.  <span data-ttu-id="b80d2-121">Seleccione el nodo de grupo insertado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="b80d2-121">Select the group node inserted in step 2.</span></span>  
  
5.  <span data-ttu-id="b80d2-122">En la ventana Propiedades, haga clic en **Group Reference**, escriba un nombre en el campo de valor y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b80d2-122">In the Properties window, click **Group Reference**, type a name into the value field, and then press ENTER.</span></span>  
  
     <span data-ttu-id="b80d2-123">Al proporcionar un nombre en el **Group Reference** propiedad, ha definido globalmente nodo de grupo, después del cual puede asociar otros nodos de grupo con este tipo definido globalmente (estructura).</span><span class="sxs-lookup"><span data-stu-id="b80d2-123">By providing a name in the **Group Reference** property, you have globally defined group node, after which you can associate other group nodes with this globally defined type (structure).</span></span>  
  
## <a name="create-a-globally-defined-attribute-group-node"></a><span data-ttu-id="b80d2-124">Crear un nodo de grupo de atributos definido globalmente</span><span class="sxs-lookup"><span data-stu-id="b80d2-124">Create a globally defined Attribute Group node</span></span>  
  
1.  <span data-ttu-id="b80d2-125">Seleccione el **registro** nodo en el que desea insertar definido globalmente **grupo de atributos** nodo.</span><span class="sxs-lookup"><span data-stu-id="b80d2-125">Select the **Record** node into which you want to insert the globally defined **Attribute Group** node.</span></span>  
  
2.  <span data-ttu-id="b80d2-126">En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **grupo de atributos**.</span><span class="sxs-lookup"><span data-stu-id="b80d2-126">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Attribute Group**.</span></span>  
  
     <span data-ttu-id="b80d2-127">Esto agrega un **grupo de atributos** nodo al final de los nodos secundarios en seleccionado **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="b80d2-127">This adds an **Attribute Group** node to the end of the child nodes in the selected **Record** node.</span></span>  
  
3.  <span data-ttu-id="b80d2-128">Agregar adecuado **atributo de campo** o **grupo de atributos** nodos para su **grupo de atributos**.</span><span class="sxs-lookup"><span data-stu-id="b80d2-128">Add the appropriate **Field Attribute** or **Attribute Group** nodes to your **Attribute Group**.</span></span>  
  
4.  <span data-ttu-id="b80d2-129">Opcionalmente, si desea cambiar el nombre de la **grupo de atributos** nodo, seleccione el **grupo de atributos** nodo y cambie su **Group Reference** propiedad a un nuevo nombre de su elección.</span><span class="sxs-lookup"><span data-stu-id="b80d2-129">Optionally, if you want to rename the **Attribute Group** node, select the **Attribute Group** node and change its **Group Reference** property to a new name of your choosing.</span></span>  
  
     <span data-ttu-id="b80d2-130">Los grupos de atributos son siempre globales y se hace referencia a ellos a partir del punto de uso.</span><span class="sxs-lookup"><span data-stu-id="b80d2-130">Attribute groups are always global and referenced from their point of use.</span></span>  
  
## <a name="use-a-type-or-group-that-has-been-globally-defined"></a><span data-ttu-id="b80d2-131">Usar un tipo o un grupo definido globalmente</span><span class="sxs-lookup"><span data-stu-id="b80d2-131">Use a type or group that has been globally defined</span></span>  
  
1.  <span data-ttu-id="b80d2-132">Seleccione el nodo para el que desea utilizar un tipo definido globalmente.</span><span class="sxs-lookup"><span data-stu-id="b80d2-132">Select the node for which you want to use a globally defined type.</span></span>  
  
2.  <span data-ttu-id="b80d2-133">En la ventana Propiedades, seleccione el tipo definido globalmente en la lista desplegable de la **Data Structure Type** propiedad (**registro** nodos), **tipo de datos** propiedad ( **Elemento de campo** y **atributo de campo** nodos), o **Group Reference** (**grupo de secuencias**, **grupo de elecciones**, **Todos los grupos**, y **grupo de atributos** nodos).</span><span class="sxs-lookup"><span data-stu-id="b80d2-133">In the Properties window, select the globally defined type from the drop-down list for the **Data Structure Type** property (**Record** nodes), **Data Type** property (**Field Element** and **Field Attribute** nodes), or **Group Reference** (**Sequence Group**, **Choice Group**, **All Group**, and **Attribute Group** nodes).</span></span> <span data-ttu-id="b80d2-134">Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="b80d2-134">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="b80d2-135">Los cambios posteriores al tipo o grupo definido globalmente se pueden hacer en cualquiera de las ubicaciones del esquema en las que aparece.</span><span class="sxs-lookup"><span data-stu-id="b80d2-135">Subsequent changes to the globally defined type or group can be made in any of the schema locations in which it appears.</span></span> <span data-ttu-id="b80d2-136">Estos cambios se aplicarán a todas las ubicaciones (igual que si los realizase en las ubicaciones arbitrarias individuales).</span><span class="sxs-lookup"><span data-stu-id="b80d2-136">These changes will be applied in all such locations as you make them in the single, arbitrary location.</span></span>  
  
 <span data-ttu-id="b80d2-137">Tras crear un declaración global, no se puede eliminar en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="b80d2-137">After you have created a global declaration, you cannot delete it in a single step.</span></span> <span data-ttu-id="b80d2-138">Sin embargo, puede eliminar mediante el **limpiar tipos de datos globales** cuadro de diálogo cuando se guarda el esquema, mediante el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="b80d2-138">However, you can delete it by using the **Cleanup Global DataTypes** dialog box when the schema is saved, using the following procedure.</span></span>  
  
## <a name="delete-a-global-declaration"></a><span data-ttu-id="b80d2-139">Eliminar una declaración global</span><span class="sxs-lookup"><span data-stu-id="b80d2-139">Delete a global declaration</span></span>  
  
1.  <span data-ttu-id="b80d2-140">Elimine todos los nodos en los que se use este tipo o grupo global, o bien, especifique un tipo o grupo diferente para usarlo en todos estos nodos, o alguna combinación de los mismos.</span><span class="sxs-lookup"><span data-stu-id="b80d2-140">Delete all of the nodes where this global type or group is used, or specify a different type or group to be used in all of those nodes, or some combination thereof.</span></span> <span data-ttu-id="b80d2-141">Para obtener instrucciones paso a paso para eliminar un nodo, vea [eliminar nodos](../core/how-to-delete-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="b80d2-141">For step-by-step instructions for deleting a node, see [Deleting Nodes](../core/how-to-delete-nodes.md).</span></span>  
  
2.  <span data-ttu-id="b80d2-142">Al guardar su especificación, el **limpiar tipos de datos globales** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b80d2-142">Upon saving your specification, the **Cleanup Global DataTypes** dialog box appears.</span></span> <span data-ttu-id="b80d2-143">Seleccione la declaración global que desea eliminar completamente de su especificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b80d2-143">Select the global declaration you want to completely delete from your specification, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b80d2-144">El **limpiar tipos de datos globales** aparece el cuadro de diálogo cada vez que guarde un esquema con tipos de datos no usados.</span><span class="sxs-lookup"><span data-stu-id="b80d2-144">The **Cleanup Global DataTypes** dialog box appears every time you save a schema with unused data types.</span></span> <span data-ttu-id="b80d2-145">Si no se muestra este cuadro de diálogo, se utilizan todos los tipos de datos en alguna parte del esquema o no se ha modificado el esquema desde que se abrió (en este último caso, todavía podría incluir tipos de datos no usados que se guardaron anteriormente).</span><span class="sxs-lookup"><span data-stu-id="b80d2-145">If this dialog box does not appear, either all data types are used somewhere in the schema or the schema has not been modified since it was opened (in the latter case, it might still contain unused data types that were previously retained.</span></span>  
  
## <a name="create-cyclical-references-to-another-node"></a><span data-ttu-id="b80d2-146">Crear referencias cíclicas a otro nodo</span><span class="sxs-lookup"><span data-stu-id="b80d2-146">Create Cyclical References to Another Node</span></span>  
 <span data-ttu-id="b80d2-147">Puede crear referencias cíclicas a un nodo para representar elementos de esquema recursivos.</span><span class="sxs-lookup"><span data-stu-id="b80d2-147">You can create cyclical references to a node to represent recursive schema elements.</span></span> <span data-ttu-id="b80d2-148">Para hacerlo, se crea un nodo cuyo tipo está definido por un registro envolvente.</span><span class="sxs-lookup"><span data-stu-id="b80d2-148">You do this by creating a node whose type is defined by an enclosing record.</span></span> <span data-ttu-id="b80d2-149">Por ejemplo, suponga un mensaje de instancia que está envuelto por un número arbitrario de sobres con la misma estructura.</span><span class="sxs-lookup"><span data-stu-id="b80d2-149">For example, consider an instance message that is wrapped in an arbitrary number of envelopes having the same structure.</span></span> <span data-ttu-id="b80d2-150">Con las referencias cíclicas, puede crear un esquema que defina tales mensajes de instancia.</span><span class="sxs-lookup"><span data-stu-id="b80d2-150">Using cyclical references, you can create a schema that defines such instance messages.</span></span>  
  
### <a name="create-a-cyclical-reference"></a><span data-ttu-id="b80d2-151">Crear una referencia cíclica</span><span class="sxs-lookup"><span data-stu-id="b80d2-151">Create a cyclical reference</span></span>  
  
1.  <span data-ttu-id="b80d2-152">Seleccione un **registro** nodo para el que desea crear una referencia recursiva.</span><span class="sxs-lookup"><span data-stu-id="b80d2-152">Select a **Record** node for which you want to create a recursive reference.</span></span> <span data-ttu-id="b80d2-153">Éste es el nodo que representa la parte superior de la estructura recursiva.</span><span class="sxs-lookup"><span data-stu-id="b80d2-153">This is the node representing the top of the recursive structure.</span></span>  
  
2.  <span data-ttu-id="b80d2-154">En la ventana Propiedades, compruebe que la **Data Structure Type** tiene un valor.</span><span class="sxs-lookup"><span data-stu-id="b80d2-154">In the Properties window, verify that the **Data Structure Type** has a value.</span></span>  
  
     <span data-ttu-id="b80d2-155">Comprobar que la **registro** nodo tiene un conjunto con nombre tipo asociado con él es necesario porque estructuras recursivas se definen cuando un tipo se incluye a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="b80d2-155">Verifying that the **Record** node has a named type associated with it is necessary because recursive structures are defined when a type contains itself.</span></span> <span data-ttu-id="b80d2-156">Los tipos solo pueden incluirse a sí mismos mediante el uso anidado de tipos globales con nombre.</span><span class="sxs-lookup"><span data-stu-id="b80d2-156">Types can only contain themselves through nested use of named global types.</span></span>  
  
3.  <span data-ttu-id="b80d2-157">Seleccione un elemento secundario **registro** nodo o insertar un elemento secundario **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="b80d2-157">Select a child **Record** node or insert a child **Record** node.</span></span>  
  
4.  <span data-ttu-id="b80d2-158">Para el elemento secundario **registro** nodo, en la ventana Propiedades, en la **Data Structure Type** , seleccione la estructura de datos identificada en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="b80d2-158">For the child **Record** node, in the Properties window, in the **Data Structure Type** list, select the data structure identified in step 2.</span></span>  
  
> [!IMPORTANT]
>  - <span data-ttu-id="b80d2-159">El **Min Occurs** propiedad para el nodo repetido debe establecerse en cero (**0**).</span><span class="sxs-lookup"><span data-stu-id="b80d2-159">The **Min Occurs** property for the repeating node must be set to zero (**0**).</span></span> <span data-ttu-id="b80d2-160">Si se establece en uno (**1**) produce un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="b80d2-160">Setting it to one (**1**) causes an infinite loop.</span></span>  
>
>  - <span data-ttu-id="b80d2-161">Si importa un esquema que incluya un elemento recursivo, el Editor de BizTalk no comprueba automáticamente que el elemento recursivo sea válido.</span><span class="sxs-lookup"><span data-stu-id="b80d2-161">If you import a schema that contains a recursive element, BizTalk Editor does not automatically check to ensure that the recursive element is valid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80d2-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="b80d2-162">See Also</span></span>  
 [<span data-ttu-id="b80d2-163">Administrar los nodos de un esquema</span><span class="sxs-lookup"><span data-stu-id="b80d2-163">Managing the Nodes Within a Schema</span></span>](../core/managing-the-nodes-within-a-schema.md)