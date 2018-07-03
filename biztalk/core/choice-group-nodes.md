---
title: Los nodos del grupo de elecciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 466b525d-4d8c-4b8e-830d-eee27845c0dc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 226a0197f1f66313de994269039107b47ed03b9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002061"
---
# <a name="choice-group-nodes"></a><span data-ttu-id="8347d-102">Nodos Grupos de elecciones</span><span class="sxs-lookup"><span data-stu-id="8347d-102">Choice Group Nodes</span></span>
<span data-ttu-id="8347d-103">En el Editor de BizTalk, puede insertar un **grupo de elecciones** nodo contenga otros nodos (o subárboles completos de nodos), solo uno de los cuales puede aparecer en un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="8347d-103">In BizTalk Editor, you can insert a **Choice Group** node to contain other nodes (or entire subtrees of nodes), only one of which can appear in an instance message.</span></span> <span data-ttu-id="8347d-104">Un determinado mensaje de instancia, si es válido, solo tendrá presente una de las elecciones.</span><span class="sxs-lookup"><span data-stu-id="8347d-104">A given instance message, if valid, will have only one of the choices present.</span></span> <span data-ttu-id="8347d-105">Los nodos contenidos deben ser nodos que se correspondan con elementos XML, pero no pueden ser nodos que se correspondan con atributos XML.</span><span class="sxs-lookup"><span data-stu-id="8347d-105">The contained nodes must be nodes that correspond to XML elements, but cannot be nodes that correspond to XML attributes.</span></span>  

> [!NOTE]
>  <span data-ttu-id="8347d-106">En el Editor de BizTalk, el **grupo de elecciones** nodo se representa con la cadena \<elección\> en la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="8347d-106">In BizTalk Editor, the **Choice Group** node is represented with the string \<Choice\> in the schema tree view.</span></span> <span data-ttu-id="8347d-107">Si establece una referencia a un **grupo de elecciones** nodo, por ejemplo, x, se representa como \<Group: x\> en la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="8347d-107">If you set a reference to a **Choice Group** node, such as x, it is represented as \<Group:x\> in the schema tree view.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="8347d-108">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="8347d-108">XSD representation</span></span>  
 <span data-ttu-id="8347d-109">Cuando un **grupo de elecciones** nodo se inserta en un **registro** nodo, éste se inserta al final de cualquier otro nodo secundario dentro de la **secuencia**, **elección**, o **todas** elemento en el **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="8347d-109">When a **Choice Group** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence**, **choice**, or **all** element in the **Record** node.</span></span> <span data-ttu-id="8347d-110">En el ejemplo siguiente se muestra, en negrita, cómo una nueva **grupo de elecciones** nodo se representa en el lenguaje de definición (XSD) del esquema XML como un **elección** elemento insertado al final de la **secuencia**  elemento en un **registro** nodo (con nodos con el nombre que deja clara su identidad).</span><span class="sxs-lookup"><span data-stu-id="8347d-110">The following example shows, in bold type, how a new **Choice Group** node is represented in the XML Schema definition (XSD) language as a **choice** element inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  

```  

 <span data-ttu-id="8347d-111">De forma predeterminada, el **elección** elemento tiene un **minOccurs** valor de cero (0), lo que indica que necesita realizar ninguna de las opciones de atributo.</span><span class="sxs-lookup"><span data-stu-id="8347d-111">By default, the **choice** element is given a **minOccurs** attribute value of zero (0), indicating that none of the choices need occur.</span></span> <span data-ttu-id="8347d-112">Puede cambiar este valor en la ventana Propiedades de Visual Studio cuando el **grupo de elecciones** nodo está seleccionado en la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="8347d-112">You can change this value in the Visual Studio Properties window when the **Choice Group** node is selected in the schema tree view.</span></span>  

 <span data-ttu-id="8347d-113">El ejemplo siguiente muestra el mismo **elección** elemento con el esquema XSD **elemento** elementos que corresponden a dos subordinado **registro** nodos.</span><span class="sxs-lookup"><span data-stu-id="8347d-113">The following example shows the same **choice** element with the XSD **element** elements corresponding to two subordinate **Record** nodes.</span></span>  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:choice minOccurs="1" maxOccurs="1">  
                <xs:element name="usAddress">  
                    <xs:complexType>  
                        <xs:sequence>  
                        </xs:sequence>  
                    </xs:complexType>  
                </xs:element>  
                <xs:element name="foreignAddress">  
                    <xs:complexType>  
                        <xs:sequence>  
                        </xs:sequence>  
                    </xs:complexType>  
                </xs:element>  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  

 <span data-ttu-id="8347d-114">En este ejemplo, dos relacionado **registro** nodos se utilizan para describir el hecho de que un mensaje de instancia o tendrá un registro con información de dirección de Estados Unidos o en un registro con información de dirección en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="8347d-114">In this example, two sibling **Record** nodes are used to describe the fact that an instance message will either have a record with United States address information in it, or a record with worldwide address information in it.</span></span> <span data-ttu-id="8347d-115">Además, el **minOccurs** y **maxOccurs** propiedades de la **grupo de elecciones** nodo han establecido en uno (1) en la ventana Propiedades de Visual Studio, lo que produce el *minOccurs* y *maxOccurs* los atributos de la **elección** que se va a establecer en uno (1) en la representación XSD del elemento.</span><span class="sxs-lookup"><span data-stu-id="8347d-115">Further, the **minOccurs** and **maxOccurs** properties of the **Choice Group** node have both been set to one (1) in the Visual Studio Properties window, resulting in the *minOccurs* and *maxOccurs* attributes of the **choice** element being set to one (1) in the XSD representation.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8347d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8347d-116">See Also</span></span>  
- [<span data-ttu-id="8347d-117">Representación de esquemas en BizTalk</span><span class="sxs-lookup"><span data-stu-id="8347d-117">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="8347d-118">Propiedades de los nodos</span><span class="sxs-lookup"><span data-stu-id="8347d-118">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="8347d-119">**Propiedades de nodo de grupo de secuencias** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="8347d-119">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>     
- [<span data-ttu-id="8347d-120">Cómo establecer las propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="8347d-120">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
