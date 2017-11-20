---
title: Nodos de atributo de campo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e964c07-53e5-473f-84f2-05af4796cbbe
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 701acadc9d1612cc5b05a05970fc2c1b92bfbb9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="field-attribute-nodes"></a><span data-ttu-id="457cf-102">Nodos Atributo de campo</span><span class="sxs-lookup"><span data-stu-id="457cf-102">Field Attribute Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="457cf-103">Información general</span><span class="sxs-lookup"><span data-stu-id="457cf-103">Overview</span></span>
<span data-ttu-id="457cf-104">En el Editor de BizTalk, utilice **atributo de campo** nodos para describir elementos de información que son de naturaleza simple, como cadenas y números.</span><span class="sxs-lookup"><span data-stu-id="457cf-104">In BizTalk Editor, you use **Field Attribute** nodes to describe items of information that are simple in nature, such as strings and numbers.</span></span> <span data-ttu-id="457cf-105">Además, se usan cuando la información en cuestión aparece como el valor de un atributo de una instancia real de un mensaje, frente a cuando aparece como el contenido de un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="457cf-105">Further, they are used when the information in question appears as the value of an attribute in an actual instance of a message, as opposed to appearing as the content of an XML element.</span></span> <span data-ttu-id="457cf-106">Para obtener información adicional acerca de la información que se almacena como contenido del elemento, vea [nodos elemento de campo](../core/field-element-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="457cf-106">For additional information about information that is stored as element content, see [Field Element Nodes](../core/field-element-nodes.md).</span></span>  
  
 <span data-ttu-id="457cf-107">Aunque el mayor uso directo de **atributo de campo** nodos son como nodos secundarios de **registro** nodos, también pueden usarse como nodos secundarios del **grupo de atributos** nodos.</span><span class="sxs-lookup"><span data-stu-id="457cf-107">Although the most straightforward use of **Field Attribute** nodes is as child nodes of **Record** nodes, they can also be used as child nodes of **Attribute Group** nodes.</span></span> <span data-ttu-id="457cf-108">En el último caso, el **atributo de campo** nodos que son elementos secundarios de un **grupo de atributos** están disponibles como atributos de cualquier nodo **registro** nodo que incluya ese  **Grupo de atributos** nodo.</span><span class="sxs-lookup"><span data-stu-id="457cf-108">In the latter case, the **Field Attribute** nodes that are children of an **Attribute Group** node are available as attributes of any **Record** node that includes that **Attribute Group** node.</span></span> <span data-ttu-id="457cf-109">Para obtener más información acerca de **grupo de atributos** nodos, consulte [nodos grupo de atributos](../core/attribute-group-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="457cf-109">For more information about **Attribute Group** nodes, see [Attribute Group Nodes](../core/attribute-group-nodes.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="457cf-110">En el Editor de BizTalk, los elementos de atributo y elemento pueden ser representados por un **campo** nodo, aunque tienen diferentes iconos asociados a ellos en la vista de árbol de esquema, una representación XML diferente en la ventana XSD, y diferentes propiedades en la ventana Propiedades de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="457cf-110">In BizTalk Editor, both the element and attribute elements can be represented by a **Field** node, though they have different icons associated with them in the schema tree view, a different XML representation in the XSD window, and different properties in the Visual Studio Properties window.</span></span>  
  
 <span data-ttu-id="457cf-111">Para un determinado elemento de información de un mensaje XML (donde por elemento de información se entiende un tipo simple discreto individual, como una cadena o un número), siempre surge la duda de si dicha información se debe representar como el atributo de un elemento o como un subelemento de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="457cf-111">For any given item of information in an XML message, where item of information means a single discrete simple type, such as a string or number, there is always a question regarding whether that information should be represented as the attribute of an element, or as a subelement of that element.</span></span> <span data-ttu-id="457cf-112">Como regla general, la representación de un elemento de información como un atributo suele ser más apropiada si los valores posibles son discretos, el número de valores es reducido y los valores suelen modificar la semántica del propio elemento.</span><span class="sxs-lookup"><span data-stu-id="457cf-112">As a general rule, representing an item of information as an attribute tends to be more appropriate when the possible values are discrete, few in number, and tend to modify the semantics of the element itself.</span></span> <span data-ttu-id="457cf-113">La representación de un elemento de información como un subelemento suele ser en cambio más idónea si los valores posibles pueden repetir una variable varias veces, probablemente están comprendidos en un intervalo de valores más amplio, pueden ser largos (como las cadenas largas) y son uno de los diversos valores hermanos si el orden es relevante.</span><span class="sxs-lookup"><span data-stu-id="457cf-113">Representing an item of information as a subelement tends to be more appropriate when the possible values can repeat a variable number of times, are likely to have more widely ranging values, might be long, as in long strings, and are one of several sibling values where their order is relevant.</span></span> <span data-ttu-id="457cf-114">Si va a crear un esquema para un tipo existente de XML de documento, la posibilidad de usar un **elemento de campo** nodo o un **atributo de campo** ya se ha realizado el nodo de un elemento determinado de información para usted, y debe usar el nodo que coincide con el código XML.</span><span class="sxs-lookup"><span data-stu-id="457cf-114">If you are creating a schema for an existing type of XML document, your choice of using a **Field Element** node or a **Field Attribute** node for a particular item of information has already been made for you, and you must use the node that matches the XML.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="457cf-115">No pueden tener nodos raíz **campo** atributos.</span><span class="sxs-lookup"><span data-stu-id="457cf-115">Root nodes may not have **Field** attributes.</span></span> <span data-ttu-id="457cf-116">**Campo** atributos conectado a la **raíz** nodo no se guardan con el esquema.</span><span class="sxs-lookup"><span data-stu-id="457cf-116">**Field** attributes attached to the **Root** node are not saved with the schema.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="457cf-117">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="457cf-117">XSD representation</span></span>  
 <span data-ttu-id="457cf-118">Cuando un **atributo de campo** nodo se inserta en un **registro** nodo, éste se inserta al final de cualquier otro nodo secundario en el **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="457cf-118">When a **Field Attribute** node is inserted into a **Record** node, it is inserted at the end of any other child nodes in the **Record** node.</span></span> <span data-ttu-id="457cf-119">Esto incluye la inserción después de la **secuencia**, **elección**, o **todos los** elemento que contiene los nodos sin atributos y después de cualquier nodo de atributo que anteriormente se encontraban Insertar.</span><span class="sxs-lookup"><span data-stu-id="457cf-119">This includes being inserted after the **sequence**, **choice**, or **all** element containing any nonattribute nodes, and after any attribute nodes that were previously inserted.</span></span> <span data-ttu-id="457cf-120">En el ejemplo siguiente se muestra un nuevo **atributo de campo** nodo, en negrita, insertado al final de un **registro** nodo (con nodos de nombre que deja clara su identidad).</span><span class="sxs-lookup"><span data-stu-id="457cf-120">The following example shows a new **Field Attribute** node, in bold, inserted at the end of a **Record** node (with nodes named to clarify their identity).</span></span>  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="FieldElement" type="xs:string" />  
            <xs:element name="EmptyNestedRecord">  
                <xs:complexType />  
            </xs:element>  
        </xs:sequence>  
        <xs:attribute name="ExistingFieldAttribute" type="xs:string" />  
  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="457cf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="457cf-121">See Also</span></span>  
-  [<span data-ttu-id="457cf-122">Representación de esquemas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="457cf-122">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="457cf-123">Propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="457cf-123">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="457cf-124">**Propiedades de nodo de elemento de campo**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="457cf-124">**Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
-  [<span data-ttu-id="457cf-125">Cómo establecer propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="457cf-125">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)   
-  [<span data-ttu-id="457cf-126">Nodos de grupo de atributos</span><span class="sxs-lookup"><span data-stu-id="457cf-126">Attribute Group Nodes</span></span>](../core/attribute-group-nodes.md)