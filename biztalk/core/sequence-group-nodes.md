---
title: Nodos de grupo de secuencias | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 139c3daa-a682-4bf7-bbb7-b5694ced0431
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2465ad10e6598a4b9e1afa88190de4c1711c1f86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sequence-group-nodes"></a><span data-ttu-id="ca9ce-102">Nodos Grupo de secuencias</span><span class="sxs-lookup"><span data-stu-id="ca9ce-102">Sequence Group Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="ca9ce-103">Información general</span><span class="sxs-lookup"><span data-stu-id="ca9ce-103">Overview</span></span>
<span data-ttu-id="ca9ce-104">En el Editor de BizTalk, puede insertar un **grupo de secuencias** nodo para contener otros nodos que deben aparecer en un mensaje de instancia en el mismo orden en que aparecen en la **grupo de secuencias** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca9ce-104">In BizTalk Editor, you can insert a **Sequence Group** node to contain other nodes that must appear in an instance message in the same order in which they appear within the **Sequence Group** node.</span></span> <span data-ttu-id="ca9ce-105">Los nodos contenidos deben ser nodos que se correspondan con elementos XML, pero no pueden ser nodos que se correspondan con atributos XML.</span><span class="sxs-lookup"><span data-stu-id="ca9ce-105">The contained nodes must be nodes that correspond to XML elements, but cannot be nodes that correspond to XML attributes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca9ce-106">En el Editor de BizTalk, el **grupo de secuencias** nodo se representa de forma predeterminada con la cadena \<secuencia > en la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="ca9ce-106">In BizTalk Editor, the **Sequence Group** node is represented by default with the string \<Sequence> in the schema tree view.</span></span> <span data-ttu-id="ca9ce-107">Si establece una referencia a un **grupo de secuencias** nodo, por ejemplo, x, se representa como \<Group: x > en la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="ca9ce-107">If you set a reference to a **Sequence Group** node, such as x, it is represented as \<Group:x> in the schema tree view.</span></span>  
  
 <span data-ttu-id="ca9ce-108">Puede que desee agregar un **grupo de secuencias** para declarar un grupo de elementos globales.</span><span class="sxs-lookup"><span data-stu-id="ca9ce-108">You may want to add a **Sequence Group** to declare a global element group.</span></span>  
  
 <span data-ttu-id="ca9ce-109">Puede que necesite crear un esquema para XML como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="ca9ce-109">You may need to create a schema for XML as follows.</span></span>  
  
```  
<Root>  
    <Record1>  
        <GroupItem1/>  
        <GroupItem2/>  
        <NotAGroupItem>  
    </Record1>  
    <Record2>  
        <GroupItem1/>  
        <GroupItem2/>  
    </Record2>  
</Root>  
  
```  
  
 <span data-ttu-id="ca9ce-110">Ya que existen GroupItem1 y GroupItem2 en ambos casos, puede declarar un grupo de secuencias globales que sea un secundario tanto de Record1 como de Record2.</span><span class="sxs-lookup"><span data-stu-id="ca9ce-110">Because GroupItem1 and GroupItem2 exist in both cases, you may declare a global sequence group that is a child of both Record1 and Record2.</span></span> <span data-ttu-id="ca9ce-111">Para obtener instrucciones paso a paso sobre cómo declarar un grupo de secuencias globales, consulte [crear referencias a otro nodo o tipo](../core/how-to-create-references-to-another-node-or-type.md).</span><span class="sxs-lookup"><span data-stu-id="ca9ce-111">For step-by-step instructions about how to declare a global sequence group, see [Creating References to Another Node or Type](../core/how-to-create-references-to-another-node-or-type.md).</span></span>  
  
 <span data-ttu-id="ca9ce-112">Un usuario puede cambiar el grupo oculto para que sea un **grupo de elecciones** nodo o un **todos los grupos** nodo (por lo que no es necesariamente un **grupo de secuencias** nodo) cambiando el  **Tipo de orden de grupo** propiedad.</span><span class="sxs-lookup"><span data-stu-id="ca9ce-112">A user can change the hidden group to be a **Choice Group** node or an **All Group** node (so it is not necessarily a **Sequence Group** node) by changing the **Group Order Type** property.</span></span> <span data-ttu-id="ca9ce-113">Para obtener más información acerca de esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="ca9ce-113">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="xsd-representation"></a><span data-ttu-id="ca9ce-114">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="ca9ce-114">XSD representation</span></span>  
 <span data-ttu-id="ca9ce-115">Cuando un **grupo de secuencias** nodo se inserta en un **registro** nodo, se inserta al final de cualquier otro nodo secundario dentro de la **secuencia**, **opción**, o **todos los** elemento en el **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca9ce-115">When a **Sequence Group** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence**, **choice**, or **all** element in the **Record** node.</span></span> <span data-ttu-id="ca9ce-116">En el ejemplo siguiente se muestra un nuevo **grupo de secuencias** nodo, en negrita, insertado al final de la **secuencia** elemento en un **registro** nodo (con nodos de nombre que deja clara su identidad).</span><span class="sxs-lookup"><span data-stu-id="ca9ce-116">The following example shows a new **Sequence Group** node, in bold type, inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca9ce-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca9ce-117">See Also</span></span>  
-  [<span data-ttu-id="ca9ce-118">Representación de esquemas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ca9ce-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="ca9ce-119">Propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="ca9ce-119">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="ca9ce-120">**Propiedades de nodo de grupo de secuencias**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="ca9ce-120">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
-  [<span data-ttu-id="ca9ce-121">Cómo establecer propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="ca9ce-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)