---
title: Grabar nodos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43af077d-5db8-43ca-8bd0-e3a9e3ebe2b0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4486b875693827c6fed74e9293bdb68b2c3dc3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268500"
---
# <a name="record-nodes"></a><span data-ttu-id="60811-102">Nodos Registro</span><span class="sxs-lookup"><span data-stu-id="60811-102">Record Nodes</span></span>
<span data-ttu-id="60811-103">En el Editor de BizTalk, use un **registro** nodo para representar una colección de información, los elementos individuales de los cuales pueden ser:</span><span class="sxs-lookup"><span data-stu-id="60811-103">In BizTalk Editor, you use a **Record** node to represent a collection of information, the individual items of which can be:</span></span>  
  
-   <span data-ttu-id="60811-104">Tipos simples de información, como cadenas y números, representados como nodos de campo secundarios.</span><span class="sxs-lookup"><span data-stu-id="60811-104">Simple types of information, such as strings and numbers, represented as child field nodes.</span></span> <span data-ttu-id="60811-105">Estos nodos de campo secundario pueden ser **elemento de campo** nodos o **atributo de campo** nodos.</span><span class="sxs-lookup"><span data-stu-id="60811-105">These child field nodes can be either **Field Element** nodes or **Field Attribute** nodes.</span></span> <span data-ttu-id="60811-106">Para obtener información adicional acerca de estos dos tipos de nodos de campo, vea [nodos elemento de campo](../core/field-element-nodes.md) y [nodos atributo de campo](../core/field-attribute-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="60811-106">For additional information about these two types of field nodes, see [Field Element Nodes](../core/field-element-nodes.md) and [Field Attribute Nodes](../core/field-attribute-nodes.md).</span></span>  
  
-   <span data-ttu-id="60811-107">Tipos complejos de información, representado como elemento secundario **registro** nodos o como un nodo de grupo (**grupo de secuencias** nodo, **grupo de elecciones** nodo, o **todos los grupos** nodo).</span><span class="sxs-lookup"><span data-stu-id="60811-107">Complex types of information, represented as child **Record** nodes or as a group node (**Sequence Group** node, **Choice Group** node, or **All Group** node).</span></span>  
  
-   <span data-ttu-id="60811-108">Cualquier tipo no examinado de información, representado como elemento secundario **cualquier elemento** o **cualquier atributo** nodos.</span><span class="sxs-lookup"><span data-stu-id="60811-108">Any unexamined type of information, represented as child **Any Element** or **Any Attribute** nodes.</span></span>  
  
-   <span data-ttu-id="60811-109">Grupos de atributos, representados por un **grupo de atributos** nodo.</span><span class="sxs-lookup"><span data-stu-id="60811-109">Groups of attributes represented by an **Attribute Group** node.</span></span>  
  
 <span data-ttu-id="60811-110">Al insertar un nuevo nodo secundario en un **registro** siempre se inserta el nodo, el nodo secundario al final de los nodos secundarios actuales.</span><span class="sxs-lookup"><span data-stu-id="60811-110">When you insert a new child node into a **Record** node, the child node is always inserted at the end of the current child nodes.</span></span> <span data-ttu-id="60811-111">Dentro de la representación de lenguaje de definición (XSD) de esquemas XML, se agregan nuevos elementos al final de las áreas correspondientes, lo que significa que los elementos sin atributos se agregan al final de los elementos dentro de la **secuencia**, **opción**, **todos los**, o **grupo** elemento y los elementos de atributo se agregan al final de otros elementos de atributo, que se producen después de la **secuencia** , **elección**, **todos los**, o **grupo** elemento.</span><span class="sxs-lookup"><span data-stu-id="60811-111">Within the XML Schema definition (XSD) language representation, new elements are added to the end of their corresponding areas, meaning that nonattribute elements are added to the end of the elements within the **sequence**, **choice**, **all**, or **group** element, and attribute elements are added to the end of any other attribute elements, all of which occur after the **sequence**, **choice**, **all**, or **group** element.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="60811-112">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="60811-112">XSD representation</span></span>  
 <span data-ttu-id="60811-113">Cuando se inserte por primera vez, la representación XSD de un nuevo **registro** nodo está formado solo tres líneas, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="60811-113">When first inserted, the XSD representation of a new **Record** node consists of only three lines, as shown in the following example.</span></span>  
  
```  
<xs:element name="Record">  
      <xs:complexType />  
</xs:element>  
```  
  
 <span data-ttu-id="60811-114">Cuando cualquier nodo secundario que no sea uno de los tres nodos de atributo (**atributo de campo**, **grupo de atributos**, y **cualquier atributo**) se agrega a un **registro** nodo, de forma predeterminada, se coloca dentro de un **secuencia** elemento dentro de la **complexType** elemento.</span><span class="sxs-lookup"><span data-stu-id="60811-114">When any child node other than one of the three attribute nodes (**Field Attribute**, **Attribute Group**, and **Any Attribute**) is added to a **Record** node, by default it is placed within a **sequence** element within the **complexType** element.</span></span> <span data-ttu-id="60811-115">El **secuencia** elemento se agrega al primer nodo secundario sin atributos se agrega y quita si se eliminan todos los nodos de elemento secundario sin atributos.</span><span class="sxs-lookup"><span data-stu-id="60811-115">The **sequence** element is added when the first nonattribute child node is added, and removed if all the nonattribute child nodes are deleted.</span></span> <span data-ttu-id="60811-116">Los tres tipos de nodos de atributo se agregan dentro de la **complexType** elemento, pero fuera y después **secuencia** elemento.</span><span class="sxs-lookup"><span data-stu-id="60811-116">All three types of attribute nodes are added within the **complexType** element, but outside and after any **sequence** element.</span></span>  
  
 <span data-ttu-id="60811-117">El **secuencia** en qué sin atributos se agregan nodos secundarios del elemento también puede ser un **elección** o **todos los** elemento si cambia el **Group Order Type (nodo Propiedad de todos los esquemas)** propiedad del nodo correspondiente en el árbol de esquema para **elección** o **todos los**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="60811-117">The **sequence** element within which nonattribute child nodes are added can also be a **choice** or **all** element if you change the **Group Order Type (Node Property of All Schemas)** property of the corresponding node in the schema tree to **Choice** or **All**, respectively.</span></span>  
  
 <span data-ttu-id="60811-118">En el ejemplo siguiente, la **registro** nodo ha sido shipTo cuyo nombre ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="60811-118">In the following example, the **Record** node has been renamed shipTo.</span></span> <span data-ttu-id="60811-119">Las ubicaciones dentro de la **registro** nodo donde se agregan nodos de atributo y sin atributos se muestran entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="60811-119">The locations within the **Record** node where attribute and nonattribute nodes are added are shown in brackets.</span></span>  
  
```  
<xs:element name="">  
    <xs:complexType>  
        <xs:sequence>  
            [Nonattribute child nodes of the record go here.]  
            [Always add new nonattribute child nodes to the end.]  
        </xs:sequence>  
            [Attribute child nodes of the record go here.]  
            [Always add new attribute child nodes to the end.]  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="60811-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="60811-120">See Also</span></span>  
-  [<span data-ttu-id="60811-121">Representación de esquemas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="60811-121">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="60811-122">Propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="60811-122">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="60811-123">**Registre las propiedades de nodo** y **Group Order Type (propiedad de nodo de todos los esquemas)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="60811-123">**Record Node Properties** and **Group Order Type (Node Property of All Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
-  [<span data-ttu-id="60811-124">Cómo establecer propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="60811-124">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)