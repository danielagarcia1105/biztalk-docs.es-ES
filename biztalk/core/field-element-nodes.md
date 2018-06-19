---
title: Nodos de elemento de campo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65b5e1f6-283f-4172-9bc2-f04a0ea6753d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74c3732ee315ad307f49760e367449216c3e01da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245988"
---
# <a name="field-element-nodes"></a><span data-ttu-id="4716a-102">Nodos Elemento de campo</span><span class="sxs-lookup"><span data-stu-id="4716a-102">Field Element Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="4716a-103">Información general</span><span class="sxs-lookup"><span data-stu-id="4716a-103">Overview</span></span>
<span data-ttu-id="4716a-104">En el Editor de BizTalk, utilice **elemento de campo** nodos para describir elementos de información que son de naturaleza simple, como cadenas y números.</span><span class="sxs-lookup"><span data-stu-id="4716a-104">In BizTalk Editor, you use **Field Element** nodes to describe items of information that are simple in nature, such as strings and numbers.</span></span> <span data-ttu-id="4716a-105">Además, se usan cuando la información en cuestión aparece como el contenido de un elemento XML en una instancia real de un mensaje, frente a cuando aparece como el valor de un atributo asociado con un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="4716a-105">Further, they are used when the information in question appears as the content of an XML element in an actual instance of a message, as opposed to appearing as the value of an attribute associated with an XML element.</span></span> <span data-ttu-id="4716a-106">Para obtener información adicional acerca de la información que se almacena como valores de atributo, vea [nodos atributo de campo](../core/field-attribute-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="4716a-106">For additional information about information that is stored as attribute values, see [Field Attribute Nodes](../core/field-attribute-nodes.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4716a-107">En el Editor de BizTalk, los elementos de atributo y elemento pueden ser representados por un **campo** nodo, aunque tienen diferentes iconos asociados con ellos en la vista de árbol de esquema, una representación XML diferente en la ventana XSD, y diferentes propiedades en la ventana Propiedades de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4716a-107">In BizTalk Editor, both the element and attribute elements can be represented by a **Field** node, although they have different icons associated with them in the schema tree view, a different XML representation in the XSD window, and different properties in the Visual Studio Properties window.</span></span>  
  
 <span data-ttu-id="4716a-108">Para un determinado elemento de información de un mensaje XML (donde por elemento de información se entiende un tipo simple discreto individual, como una cadena o un número), siempre surge la duda de si dicha información se debe representar como el atributo de un elemento o como un subelemento de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="4716a-108">For any given item of information in an XML message, where item of information means a single discrete simple type, such as a string or number, there is always a question regarding whether that information should be represented as the attribute of an element, or as a subelement of that element.</span></span> <span data-ttu-id="4716a-109">Como regla general, la representación de un elemento de información como un atributo suele ser más apropiada si los valores posibles son discretos, el número de valores es reducido y los valores suelen modificar la semántica del propio elemento.</span><span class="sxs-lookup"><span data-stu-id="4716a-109">As a general rule, representing an item of information as an attribute tends to be more appropriate when the possible values are discrete, few in number, and tend to modify the semantics of the element itself.</span></span> <span data-ttu-id="4716a-110">La representación de un elemento de información como un subelemento suele ser en cambio más idónea si los valores posibles pueden repetir una variable varias veces, probablemente están comprendidos en un intervalo de valores más amplio, pueden ser largos (como las cadenas largas) y son uno de los diversos valores hermanos si el orden es relevante.</span><span class="sxs-lookup"><span data-stu-id="4716a-110">Representing an item of information as a subelement tends to be more appropriate when the possible values can repeat a variable number of times, are likely to have more widely ranging values, might be long, as in long strings, and are one of several sibling values where their order is relevant.</span></span> <span data-ttu-id="4716a-111">Si está creando un esquema para un tipo existente de XML de documento, la posibilidad de usar un **elemento de campo** nodo o un **atributo de campo** ya se ha realizado el nodo de un elemento determinado de información para usted, y se debe usar el nodo que coincide con el código XML.</span><span class="sxs-lookup"><span data-stu-id="4716a-111">If you are just creating a schema for an existing type of XML document, your choice of using a **Field Element** node or a **Field Attribute** node for a particular item of information has already been made for you, and you must use the node that matches the XML.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="4716a-112">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="4716a-112">XSD representation</span></span>  
 <span data-ttu-id="4716a-113">Cuando un **elemento de campo** nodo se inserta en un **registro** nodo, se inserta al final de cualquier otro nodo secundario dentro de la **secuencia** elemento en el  **Registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="4716a-113">When a **Field Element** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence** element in the **Record** node.</span></span> <span data-ttu-id="4716a-114">En el ejemplo siguiente se muestra un nuevo **elemento de campo** nodo, en negrita, insertado al final de la **secuencia** elemento en un **registro** nodo (con nombre que deja clara su identidad de nodos ).</span><span class="sxs-lookup"><span data-stu-id="4716a-114">The following example shows a new **Field Element** node, in bold, inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:element name="EmptyNestedRecord">  
                <xs:complexType />  
            </xs:element>  
  
        </xs:sequence>  
        <xs:attribute name="ExistingFieldAttribute" type="xs:string" />  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="4716a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4716a-115">See Also</span></span>  
-  [<span data-ttu-id="4716a-116">Representación de esquemas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4716a-116">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="4716a-117">Propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="4716a-117">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="4716a-118">**Propiedades de nodo de elemento de campo**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4716a-118">**Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
-  [<span data-ttu-id="4716a-119">Cómo establecer propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="4716a-119">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)