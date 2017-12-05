---
title: Cualquier atributo nodos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa2d25bc-3a8f-4fd9-acad-341b8e80c737
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82490a114149e3d4f71e3598900be5599c8a36e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="any-attribute-nodes"></a><span data-ttu-id="7e9af-102">Nodos Cualquier atributo</span><span class="sxs-lookup"><span data-stu-id="7e9af-102">Any Attribute Nodes</span></span>
<span data-ttu-id="7e9af-103">En el Editor de BizTalk, puede usar un **cualquier atributo** nodo para indicar un elemento (conocido) dentro de un mensaje de instancia para el que pueden aparecer cero o más atributos desconocidos.</span><span class="sxs-lookup"><span data-stu-id="7e9af-103">In BizTalk Editor, you can use an **Any Attribute** node to indicate a (known) element within an instance message for which zero or more unknown attributes may appear.</span></span> <span data-ttu-id="7e9af-104">Esto resulta útil para las situaciones en las que sabe que un elemento específico estará presente en una ubicación específica de un mensaje de instancia, pero no está seguro de qué atributos incluirá exactamente dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="7e9af-104">This accommodates situations in which you know that a particular element will be present at a particular location within an instance message, but you are not sure exactly what attributes that element might include.</span></span> <span data-ttu-id="7e9af-105">Si coloca un **cualquier atributo** nodo dentro de la **registro** nodo asociado con el elemento correspondiente, BizTalk puede procesar dicho elemento, con el único requisito que se va a que los atributos asociados son sintácticamente correcto (attributeName = "attributeValue").</span><span class="sxs-lookup"><span data-stu-id="7e9af-105">If you place an **Any Attribute** node within the **Record** node associated with the relevant element, BizTalk can process that element, with the only requirement being that any associated attributes are syntactically correct (attributeName="attributeValue").</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e9af-106">En el Editor de BizTalk, el **cualquier atributo** nodo se representa con la cadena \<AnyAttribute\> en la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="7e9af-106">In BizTalk Editor, the **Any Attribute** node is represented with the string \<AnyAttribute\> in the schema tree view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e9af-107">Puede controlar el grado al que la parte desconocida del mensaje se valida como XML con formato correcto mediante la **Process Contents** propiedad.</span><span class="sxs-lookup"><span data-stu-id="7e9af-107">You can control the degree to which the unknown portion of the message is validated as well-formed XML by using the **Process Contents** property.</span></span> <span data-ttu-id="7e9af-108">En muchos casos puede que necesite establecer el **Process Contents** propiedad **omitir** para el contenido de un mensaje de instancia en la ubicación de la **cualquier atributo** nodo que se va a procesar .</span><span class="sxs-lookup"><span data-stu-id="7e9af-108">In many cases you may need to set the **Process Contents** property to **Skip** for the contents of an instance message at the location of the **Any Attribute** node to be processed.</span></span> <span data-ttu-id="7e9af-109">Conserva el valor predeterminado de **Strict** para el **Process Contents** propiedad impide que la validación de mensaje de instancia de paso.</span><span class="sxs-lookup"><span data-stu-id="7e9af-109">Retaining the default value of **Strict** for the **Process Contents** property will prevent instance message validation from passing.</span></span>  
>
> <span data-ttu-id="7e9af-110">Para obtener más información acerca de esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="7e9af-110">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="xsd-representation"></a><span data-ttu-id="7e9af-111">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="7e9af-111">XSD representation</span></span>  
 <span data-ttu-id="7e9af-112">Cuando un **cualquier atributo** nodo se agrega a un **registro** nodo o a un **grupo de atributos** nodo, una etiqueta XML se agrega a la definición de esquema XML correspondiente lenguaje (XSD) representación del esquema.</span><span class="sxs-lookup"><span data-stu-id="7e9af-112">When an **Any Attribute** node is added to a **Record** node or to an **Attribute Group** node, a single XML tag is added to the corresponding XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="7e9af-113">En el ejemplo siguiente, un nuevo **cualquier atributo** nodo, cuya representación XSD se muestra en negrita, se ha agregado a un archivo **registro** nodo que ya contiene un **delelementodecampo** nodo.</span><span class="sxs-lookup"><span data-stu-id="7e9af-113">In the following example, a new **Any Attribute** node, whose XSD representation is shown in bold, has been added to an existing **Record** node that already contains a **Field Element** node.</span></span>  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
        <xs:anyAttribute />  
    </xs:complexType>  
</xs:element  
```  
  
 <span data-ttu-id="7e9af-114">En el ejemplo anterior, la representación XSD del nuevo **cualquier atributo** nodo agrega un **anyAttribute** elemento al final de la que contiene (**registro** nodo) **elemento** elemento, fuera la **secuencia** elemento y dentro del **complexType** elemento.</span><span class="sxs-lookup"><span data-stu-id="7e9af-114">In the preceding example, the XSD representation of the new **Any Attribute** node adds an **anyAttribute** element to the end of the containing (**Record** node) **element** element, outside the **sequence** element and within the **complexType** element.</span></span> <span data-ttu-id="7e9af-115">Aquí es donde todos los **atributo** elementos, excepto aquellos con un **grupo de atributos** nodo, se agregan a los que contiene **elemento** elementos.</span><span class="sxs-lookup"><span data-stu-id="7e9af-115">This is where all **attribute** elements, other than those with an **Attribute Group** node, are added to their containing **element** elements.</span></span>  
  
 <span data-ttu-id="7e9af-116">Ahora y suponiendo que el **Process Contents** propiedad de la **cualquier atributo** nodo se establece en **omitir**, en un mensaje de instancia regido por este fragmento de esquema, un  **ExistingRecord** el elemento y puede contener cualquier atributo siempre y cuando estén bien formadas con respecto a la sintaxis XML.</span><span class="sxs-lookup"><span data-stu-id="7e9af-116">Now, and assuming that the **Process Contents** property of the **Any Attribute** node is set to **Skip**, within an instance message governed by this schema fragment, an **ExistingRecord** element is expected, and it can contain any attributes so long as they are well-formed with respect to XML syntax.</span></span> <span data-ttu-id="7e9af-117">(Para que se ajuste al fragmento XSD en este ejemplo, también debe contener el **ExistingFieldElement** elemento también.)</span><span class="sxs-lookup"><span data-stu-id="7e9af-117">(To conform to the XSD fragment in this example, it must also contain the **ExistingFieldElement** element as well.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9af-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e9af-118">See Also</span></span>  
 <span data-ttu-id="7e9af-119">[Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="7e9af-119">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="7e9af-120">[Propiedades de nodo](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7e9af-120">[Node Properties](../core/node-properties.md) </span></span>  
 <span data-ttu-id="7e9af-121">[Cómo establecer propiedades de nodo](../core/how-to-set-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7e9af-121">[How to Set Node Properties](../core/how-to-set-node-properties.md) </span></span>  
 [<span data-ttu-id="7e9af-122">Nodos Cualquier elemento</span><span class="sxs-lookup"><span data-stu-id="7e9af-122">Any Element Nodes</span></span>](../core/any-element-nodes.md)