---
title: Nodos de grupo de atributos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea02fae8-4e03-486a-8d9d-185ae230d3a0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04db816f1209b7cd503b9a162cdd2a030ba86292
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="attribute-group-nodes"></a><span data-ttu-id="2cc69-102">Nodos Grupo de atributos</span><span class="sxs-lookup"><span data-stu-id="2cc69-102">Attribute Group Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="2cc69-103">Información general</span><span class="sxs-lookup"><span data-stu-id="2cc69-103">Overview</span></span>
<span data-ttu-id="2cc69-104">En el Editor de BizTalk, puede agregar un **grupo de atributos** nodo a un **registro** nodo o a otro **grupo de atributos** nodo contenga un grupo de atributos que se esperan que use en más que uno **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="2cc69-104">In BizTalk Editor, you can add an **Attribute Group** node to a **Record** node or to another **Attribute Group** node to contain a group of attributes that you expect to use in more than one **Record** node.</span></span> <span data-ttu-id="2cc69-105">Agregar un **grupo de atributos** nodo a otro **grupo de atributos** nodo logra anidamiento de grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="2cc69-105">Adding an **Attribute Group** node to another **Attribute Group** node achieves attribute group nesting.</span></span> <span data-ttu-id="2cc69-106">Esto le permite definir un grupo de atributos en un lugar que se puede usar en varios **registro** o **grupo de atributos** nodos.</span><span class="sxs-lookup"><span data-stu-id="2cc69-106">This allows you to define a group of attributes in one place that can be used in multiple **Record** or **Attribute Group** nodes.</span></span> <span data-ttu-id="2cc69-107">Cualquier modificación que se realice posteriormente en el grupo de atributos se propagará a todos los nodos que tengan asociado dicho grupo de atributos,</span><span class="sxs-lookup"><span data-stu-id="2cc69-107">Subsequent modifications to the attribute group will propagate to all of the nodes with which that attribute group is associated.</span></span> <span data-ttu-id="2cc69-108">con independencia del contexto de nodo en el que se realicen las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="2cc69-108">This is true regardless of the node context in which the modifications are made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cc69-109">En el Editor de BizTalk, el **AttributeGroup** nodo se representa de forma predeterminada con la cadena \<AttribGroup:attribGroup*N*> en la vista de árbol de esquema, donde *N*es un número de progresión continua.</span><span class="sxs-lookup"><span data-stu-id="2cc69-109">In BizTalk Editor, the **AttributeGroup** node is represented by default with the string \<AttribGroup:attribGroup*N*> in the schema tree view, where *N* is a monotonically increasing numeral.</span></span> <span data-ttu-id="2cc69-110">Puede cambiar la attribGroup*N* parte de su nombre, escriba un nuevo nombre único en su **Group Reference** propiedad.</span><span class="sxs-lookup"><span data-stu-id="2cc69-110">You can change the attribGroup*N* portion of its name by typing a new unique name in its **Group Reference** property.</span></span>  
  
 <span data-ttu-id="2cc69-111">Al crear inicialmente un **grupo de atributos** nodo, se inserta en uno de los **registro** o **grupo de atributos** nodos en el que se usará y, opcionalmente, cambiar su nombre en su **Group Reference** propiedad.</span><span class="sxs-lookup"><span data-stu-id="2cc69-111">When initially creating an **Attribute Group** node, you simply insert it into one of the **Record** or **Attribute Group** nodes in which it will be used, and optionally change its name in its **Group Reference** property.</span></span> <span data-ttu-id="2cc69-112">Hay dos maneras de utilizar el mismo grupo de atributos en otro **registro** o **grupo de atributos** nodo:</span><span class="sxs-lookup"><span data-stu-id="2cc69-112">There are two ways to use the same attribute group in another **Record** or **Attribute Group** node:</span></span>  
  
-   <span data-ttu-id="2cc69-113">Puede copiar existente **grupo de atributos** nodo y, a continuación, péguelo en ese otro **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="2cc69-113">You can copy the existing **Attribute Group** node and then paste it into that other **Record** node.</span></span>  
  
-   <span data-ttu-id="2cc69-114">Puede insertar un nuevo **grupo de atributos** nodo en que otras **registro** nodo y, después, establezca el **Group Reference** propiedad del nuevo **delgrupodeatributos** nodo que se va a hacer referencia a una existente **grupo de atributos** nodo.</span><span class="sxs-lookup"><span data-stu-id="2cc69-114">You can insert a new **Attribute Group** node into that other **Record** node, and then set the **Group Reference** property of the new **Attribute Group** node to reference an existing **Attribute Group** node.</span></span>  
  
 <span data-ttu-id="2cc69-115">A partir de ahí, puede modificar el **grupo de atributos** nodo: por ejemplo, al agregar o eliminar un **atributo de campo** nodo, en el contexto de cualquier **registro** o  **Grupo de atributos** nodo en el que haya pegado.</span><span class="sxs-lookup"><span data-stu-id="2cc69-115">Thereafter, you can modify the **Attribute Group** node—for example, by adding or deleting a **Field Attribute** node—in the context of any **Record** or **Attribute Group** node into which you pasted it.</span></span> <span data-ttu-id="2cc69-116">Que el cambio se propagará a todos los demás **registro** o **grupo de atributos** nodos al que está asociado el grupo de atributos.</span><span class="sxs-lookup"><span data-stu-id="2cc69-116">That change will propagate to all other **Record** or **Attribute Group** nodes with which the attribute group is associated.</span></span>  
  
 <span data-ttu-id="2cc69-117">Tendría sentido agregar un **grupo de atributos** nodo sin tener que agregar al menos un nodo relevante, donde se incluyen los nodos pertinentes **atributo de campo** nodos, **cualquier atributo**nodos y (anidada) **grupo de atributos** nodos.</span><span class="sxs-lookup"><span data-stu-id="2cc69-117">It would be pointless to add an **Attribute Group** node without adding at least one relevant node to it, where relevant nodes include **Field Attribute** nodes, **Any Attribute** nodes, and (nested) **Attribute Group** nodes.</span></span> <span data-ttu-id="2cc69-118">De hecho, un grupo de atributos que solo contiene un único atributo está en cierto modo mal concebido, salvo si planea agregar más atributos en el futuro.</span><span class="sxs-lookup"><span data-stu-id="2cc69-118">In fact, an attribute group that contains only a single attribute is somewhat ill-conceived, unless you are making a point of planning for the addition of more attributes in the future.</span></span>  
  
 <span data-ttu-id="2cc69-119">**Grupo de atributos** nodos pueden anidarse, lo que permite mayores posibilidades respecto a cómo se pueden construir y combinar grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="2cc69-119">**Attribute Group** nodes can be nested, allowing more possibilities in how groups of attributes can be constructed and combined.</span></span> <span data-ttu-id="2cc69-120">**Grupo de atributos** nodos también pueden contener el **cualquier atributo** nodo, lo que permite un grupo de atributos para que contenga las capacidades de carácter comodín con respecto a las instancias de atributo puede dar cabida a.</span><span class="sxs-lookup"><span data-stu-id="2cc69-120">**Attribute Group** nodes can also contain the **Any Attribute** node, allowing an attribute group to contain wildcard character capabilities with respect to the attribute instances it can accommodate.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="2cc69-121">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="2cc69-121">XSD representation</span></span>  
 <span data-ttu-id="2cc69-122">Cuando un **grupo de atributos** nodo se agrega primero a un **registro** nodo o a otro **grupo de atributos** nodo, dos áreas distintas de la definición de esquema XML (XSD) correspondiente representación de idioma del esquema se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="2cc69-122">When an **Attribute Group** node is first added to a **Record** node or to another **Attribute Group** node, two distinct areas of the corresponding XML Schema definition (XSD) language representation of the schema are affected.</span></span> <span data-ttu-id="2cc69-123">En el ejemplo siguiente, un nuevo **grupo de atributos** nodo, en negrita, se ha agregado a un archivo **registro** nodo que ya contiene otra **elemento de campo** nodo.</span><span class="sxs-lookup"><span data-stu-id="2cc69-123">In the following example, a new **Attribute Group** node, in bold, has been added to an existing **Record** node that already contains an existing **Field Element** node.</span></span>  
  
```  
        ...  
        <xs:element name="ExistingRecord">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ExistingFieldElement" type="xs:string" />  
                </xs:sequence>  
                <xs:attributeGroup ref="attrGroup0" />  
            </xs:complexType>  
        </xs:element>  
        ...   
    <xs:attributeGroup name="attrGroup0" />  
</xs:schema>  
```  
  
 <span data-ttu-id="2cc69-124">Tenga en cuenta cómo el **attributeGroup** elemento dentro de la representación XSD de la **registro** global hace referencia a nodo **attributeGroup** elemento que se agrega como un elemento secundario de la **esquema** elemento.</span><span class="sxs-lookup"><span data-stu-id="2cc69-124">Note how the **attributeGroup** element within the XSD representation of the **Record** node references a global **attributeGroup** element that is added as a child of the **schema** element.</span></span> <span data-ttu-id="2cc69-125">Esta definición global del grupo de atributos en la representación XSD del esquema permite hacer referencia al grupo de atributos en varias ubicaciones del esquema.</span><span class="sxs-lookup"><span data-stu-id="2cc69-125">This global definition of the attribute group within the XSD representation of the schema allows the attribute group to be referenced in multiple locations throughout the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cc69-126">Nombres de grupo de atributos predeterminados que se proporcionan de forma automática tienen el formato attrGroup*N*, donde *N* es un número de progresión continua.</span><span class="sxs-lookup"><span data-stu-id="2cc69-126">Default attribute group names that are supplied automatically have the form attrGroup*N*, where *N* is a monotonically increasing numeral.</span></span> <span data-ttu-id="2cc69-127">Puede cambiar el nombre de un grupo de atributos al proporcionar un nombre nuevo y único en su **Group Reference** propiedad.</span><span class="sxs-lookup"><span data-stu-id="2cc69-127">You can rename an attribute group by providing a new, unique name in its **Group Reference** property.</span></span> <span data-ttu-id="2cc69-128">No se puede cambiar el nombre de un grupo de atributos, en la posición actual, en el árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="2cc69-128">An attribute group cannot be renamed in place within the schema tree.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc69-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cc69-129">See Also</span></span>  
-  [<span data-ttu-id="2cc69-130">Representación de esquemas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2cc69-130">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="2cc69-131">Propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="2cc69-131">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="2cc69-132">**Propiedades de nodo de grupo de secuencias**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="2cc69-132">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
-  [<span data-ttu-id="2cc69-133">Cómo establecer propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="2cc69-133">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)   
-  [<span data-ttu-id="2cc69-134">Nodos de atributo de campo</span><span class="sxs-lookup"><span data-stu-id="2cc69-134">Field Attribute Nodes</span></span>](../core/field-attribute-nodes.md)   
-  [<span data-ttu-id="2cc69-135">Los nodos de atributo</span><span class="sxs-lookup"><span data-stu-id="2cc69-135">Any Attribute Nodes</span></span>](../core/any-attribute-nodes.md)