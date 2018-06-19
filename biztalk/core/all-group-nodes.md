---
title: Todos los nodos de grupo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e28d98c-746a-44d8-bed2-ba539b8432aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f51d6420b7d754ffb8706e2bc729a02df00b4338
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230652"
---
# <a name="all-group-nodes"></a><span data-ttu-id="bfae1-102">Nodos Todos los grupos</span><span class="sxs-lookup"><span data-stu-id="bfae1-102">All Group Nodes</span></span>
<span data-ttu-id="bfae1-103">En el Editor de BizTalk, puede insertar un **todos los grupos** nodo para contener otros nodos que va a aparecer cero o una vez, en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="bfae1-103">In BizTalk Editor, you can insert an **All Group** node to contain other nodes that will appear zero or one time, in any order.</span></span> <span data-ttu-id="bfae1-104">En el lenguaje de definición (XSD) de esquemas XML, el **todos los grupos** tiene más limitaciones de uso que **secuencia** y **elección** grupos, que se traduce en algunos casos poco frecuentes en El Editor de BizTalk donde podrá crear un **todos los grupos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bfae1-104">In XML Schema definition (XSD) language, the **All group** has more usage limitations than **Sequence** and **Choice** groups, which translates to few situations within BizTalk Editor where you will be able to create an **All Group** node.</span></span>  
  
 <span data-ttu-id="bfae1-105">Para usar un **todos los grupos** nodo en el Editor de BizTalk, tiene que seguir algunos pasos adicionales: la manera más fácil de crear un **todos los grupos** nodo consiste en cambiar el valor de la **Group Order Type** propiedad del elemento primario **registro** nodo **todos los**.</span><span class="sxs-lookup"><span data-stu-id="bfae1-105">To use an **All Group** node in BizTalk Editor, you need to follow some extra steps: The easiest way to create an **All Group** node is to change the value of the **Group Order Type** property of the parent **Record** node to **All**.</span></span> <span data-ttu-id="bfae1-106">Esto garantiza que todos los nodos subordinados de la **registro** nodo contenidas en el **todos los grupos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bfae1-106">This ensures that all of the subordinate nodes of the **Record** node are contained within the **All Group** node.</span></span>  <span data-ttu-id="bfae1-107">Vea **Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="bfae1-107">See **Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="bfae1-108">Otra manera de usar un **todos los grupos** en el Editor de BizTalk comienza por insertar un nuevo **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="bfae1-108">Another way to use an **All Group** node in BizTalk Editor begins with inserting a new **Record** node.</span></span> <span data-ttu-id="bfae1-109">Después de insertar el nuevo **registro** nodo, cambiar su **tipo de contenido** propiedad **ComplexContent**.</span><span class="sxs-lookup"><span data-stu-id="bfae1-109">After inserting the new **Record** node, change its **Content Type** property to **ComplexContent**.</span></span> <span data-ttu-id="bfae1-110">A continuación, puede insertar un **todos los grupos** nodo como un elemento secundario de la **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="bfae1-110">Then you can insert an **All Group** node as a child of the **Record** node.</span></span> <span data-ttu-id="bfae1-111">Esto es necesario porque el **todos los grupos** sólo puede insertar cuando existe herencia.</span><span class="sxs-lookup"><span data-stu-id="bfae1-111">This is required because the **All Group** can only be inserted when inheritance is involved.</span></span> <span data-ttu-id="bfae1-112">Mediante la especificación de que la que contiene **registro** nodo incluye contenido complejo, su tipo de datos se basará en el tipo de datos **xs: anyType**, derivado mediante extension.</span><span class="sxs-lookup"><span data-stu-id="bfae1-112">By specifying that the containing **Record** node contains complex content, its data type becomes based on the data type **xs:anyType**, derived by extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfae1-113">En el Editor de BizTalk, el **todos los grupos** nodo se representa con la cadena \<todos > en la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="bfae1-113">In BizTalk Editor, the **All Group** node is represented with the string \<All> in the schema tree view.</span></span> <span data-ttu-id="bfae1-114">Si establece una referencia a un **todos los grupos** nodo, como a x, se representa como \<Group: x > en la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="bfae1-114">If you set a reference to an **All Group** node, such as to x, it is represented as \<Group:x> in the schema tree view.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="bfae1-115">Representación XSD</span><span class="sxs-lookup"><span data-stu-id="bfae1-115">XSD representation</span></span>  
 <span data-ttu-id="bfae1-116">Un **todos los grupos** nodo se pueden insertar en una **registro** nodo, pero solo si es el nodo secundario sin atributos sólo de ese **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="bfae1-116">An **All Group** node can be inserted into a **Record** node, but only if it is the only non-attribute child node of that **Record** node.</span></span> <span data-ttu-id="bfae1-117">En el ejemplo siguiente se muestra, en los pasos, cómo una nueva **todos los grupos** nodo se representa en el lenguaje de definición (XSD) de esquemas XML como un **todos los** elemento como los pasos en el Editor de BizTalk se llevan a cabo (con nodos denominados que deja clara su identidad).</span><span class="sxs-lookup"><span data-stu-id="bfae1-117">The following example shows, in steps, how a new **All Group** node is represented in the XML Schema definition (XSD) language as an **all** element as the steps in BizTalk Editor are performed (with nodes named to clarify their identity).</span></span>  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  
  
 <span data-ttu-id="bfae1-118">Después de agregar un nuevo registro, como se muestra en el fragmento XSD anterior, su **tipo de contenido** propiedad se cambia a **ComplexContent**, da lugar a las siguientes modificaciones de XSD.</span><span class="sxs-lookup"><span data-stu-id="bfae1-118">After adding a new record as shown in the preceding XSD fragment, its **Content Type** property is changed to **ComplexContent**, resulting in the following XSD modifications.</span></span>  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
             <xs:extension base="xs:anyType" />  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="bfae1-119">Ahora el **todos los grupos** se puede insertar el nodo como un elemento secundario del nuevo registro, como se muestra en el siguiente fragmento XSD.</span><span class="sxs-lookup"><span data-stu-id="bfae1-119">Now the **All Group** node can be inserted as a child of the new record, as shown in the following XSD fragment.</span></span>  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
            <xs:extension base="xs:anyType">  
                <xs:all />   
             </xs:extension>  
          </xs:complexContent>  
     </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="bfae1-120">Por último, puede insertar los nodos correspondientes como elementos secundarios del nuevo **todos los grupos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bfae1-120">Finally, you can insert appropriate nodes as children of the new **All Group** node.</span></span> <span data-ttu-id="bfae1-121">El ejemplo siguiente muestra un **registro** nodo y un **elemento de campo** nodo insertado como nodos secundarios del nuevo **todos los grupos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bfae1-121">The following example shows a **Record** node and a **Field Element** node inserted as child nodes of the new **All Group** node.</span></span>  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
            <xs:extension base="xs:anyType">  
                <xs:all>  
                    <xs:element name="RecordChildOfAllGroup">  
                        <xs:complexType />  
                    </xs:element>  
                    <xs:element name="FieldElementChildOfAllGroup" type="xs:string" />  
                </xs:all>  
            </xs:extension>  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfae1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfae1-122">See Also</span></span>  
-  [<span data-ttu-id="bfae1-123">Representación de esquemas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bfae1-123">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="bfae1-124">Propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="bfae1-124">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="bfae1-125">**Propiedades de nodo de grupo de secuencias**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="bfae1-125">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span> 
-  [<span data-ttu-id="bfae1-126">Cómo establecer propiedades de nodo</span><span class="sxs-lookup"><span data-stu-id="bfae1-126">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)