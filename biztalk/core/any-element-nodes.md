---
title: Nodos cualquier elemento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7e30fcf-31bc-4d48-9bc7-0be90e927127
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c24eb75020f715245fc2b17f4bc1f81a7e34cd35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="any-element-nodes"></a><span data-ttu-id="1ad5d-102">Nodos Cualquier elemento</span><span class="sxs-lookup"><span data-stu-id="1ad5d-102">Any Element Nodes</span></span>
<span data-ttu-id="1ad5d-103">En el Editor de BizTalk, puede usar un **cualquier elemento** nodo para indicar una ubicación dentro de un mensaje de instancia donde pueden aparecer elementos desconocidos.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-103">In BizTalk Editor, you can use an **Any Element** node to indicate a location within an instance message where unknown elements may appear.</span></span> <span data-ttu-id="1ad5d-104">Esto es útil para situaciones en las que se sabe que puede aparecer algún elemento en una ubicación concreta de un mensaje de instancia, pero se desconoce el nombre del elemento o lo complicado que puede ser.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-104">This accommodates situations in which you know that some element might appear at a particular location within an instance message, but you do not know the name of the element, or how complicated it might be.</span></span> <span data-ttu-id="1ad5d-105">Si coloca un **cualquier elemento** nodo en la ubicación adecuada en el esquema, BizTalk puede procesar esas partes desconocidas de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-105">If you place an **Any Element** node at the appropriate location within the schema, BizTalk can process such unknown portions of a message.</span></span> <span data-ttu-id="1ad5d-106">El único requisito es que el XML correspondiente tenga un formato correcto.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-106">The only requirement is that the corresponding XML is well-formed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ad5d-107">En el Editor de BizTalk, el **cualquier elemento** nodo se representa con la cadena \<cualquier > en la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-107">In BizTalk Editor, the **Any Element** node is represented with the string \<Any> in the schema tree view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ad5d-108">Puede controlar el grado al que la parte desconocida del mensaje se valida como XML con formato correcto mediante la **Process Contents** propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-108">You can control the degree to which the unknown portion of the message is validated as well-formed XML by using the **Process Contents** property.</span></span> <span data-ttu-id="1ad5d-109">En muchos casos puede que necesite establecer el **Process Contents** propiedad **omitir** para el contenido de un mensaje de instancia en la ubicación de la **cualquier elemento** nodo que se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-109">In many cases you may need to set the **Process Contents** property to **Skip** for the contents of an instance message at the location of the **Any Element** node to be processed.</span></span> <span data-ttu-id="1ad5d-110">Conserva el valor predeterminado de **Strict** para el **Process Contents** propiedad impide que la validación de mensaje de instancia de paso.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-110">Retaining the default value of **Strict** for the **Process Contents** property will prevent instance message validation from passing.</span></span>  
> 
> <span data-ttu-id="1ad5d-111">Para obtener más información acerca de esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="1ad5d-111">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="xsd-representation"></a><span data-ttu-id="1ad5d-112">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="1ad5d-112">XSD representation</span></span>  
 <span data-ttu-id="1ad5d-113">Cuando un **cualquier elemento** nodo se agrega a un **registro** nodo, o a otro nodo en el que puede agregarse como un **grupo de secuencias**, **grupo de elecciones**, o **todos los grupos** nodo, una etiqueta XML se agrega a la definición de esquema XML correspondiente representación del lenguaje (XSD) del esquema.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-113">When an **Any Element** node is added to a **Record** node, or to another node to which it can be added such as a **Sequence Group**, **Choice Group**, or **All Group** node, a single XML tag is added to the corresponding XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="1ad5d-114">En el ejemplo siguiente, un nuevo **cualquier elemento** nodo, cuya representación XSD se muestra en negrita, se ha agregado a un archivo **registro** nodo que ya contiene un **delelementodecampo** nodo.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-114">In the following example, a new **Any Element** node, whose XSD representation is shown in bold type, has been added to an existing **Record** node that already contains a **Field Element** node.</span></span>  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
             <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:any />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="1ad5d-115">Suponiendo que la **Process Contents** propiedad de la **cualquier elemento** nodo se establece en **omitir**, en un mensaje de instancia regido por este fragmento de esquema, un **ExistingRecord** elemento debe contener un **ExistingFieldElement** elemento que contiene datos de cadena, seguido de los elementos individuales de complejidad arbitraria.</span><span class="sxs-lookup"><span data-stu-id="1ad5d-115">Assuming that the **Process Contents** property of the **Any Element** node is set to **Skip**, within an instance message governed by this schema fragment, an **ExistingRecord** element is expected to contain an **ExistingFieldElement** element containing string data, followed by any single element of arbitrary complexity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad5d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ad5d-116">See Also</span></span>  
 <span data-ttu-id="1ad5d-117">[Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="1ad5d-117">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="1ad5d-118">[Propiedades de nodo](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1ad5d-118">[Node Properties](../core/node-properties.md) </span></span>  
 <span data-ttu-id="1ad5d-119">[Cómo establecer propiedades de nodo](../core/how-to-set-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1ad5d-119">[How to Set Node Properties](../core/how-to-set-node-properties.md) </span></span>  
 [<span data-ttu-id="1ad5d-120">Los nodos de atributo</span><span class="sxs-lookup"><span data-stu-id="1ad5d-120">Any Attribute Nodes</span></span>](../core/any-attribute-nodes.md)