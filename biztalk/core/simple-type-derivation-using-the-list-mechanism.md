---
title: "Derivación de tipo simple mediante el mecanismo de lista | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14f3c7b7-7585-4297-9177-2deaef8355f0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aafc6a540e9595f426858bc16fedfb1f8fe0bc8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation-using-the-list-mechanism"></a><span data-ttu-id="3f4a8-102">Derivación de tipo simple mediante el mecanismo de lista</span><span class="sxs-lookup"><span data-stu-id="3f4a8-102">Simple Type Derivation Using the List Mechanism</span></span>
<span data-ttu-id="3f4a8-103">Al derivar un nuevo tipo simple a partir de un tipo simple existente con el mecanismo de lista, se especifica que el valor de este atributo o elemento puede ser una lista de valores separados por espacios del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="3f4a8-103">When you derive a new simple type from an existing simple type by using the list mechanism, you are specifying that the value for this attribute or element can be a space-separated list of values of the specified type.</span></span> <span data-ttu-id="3f4a8-104">Por ejemplo, puede especificar que un valor de atributo o de elemento sea una lista de enteros separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="3f4a8-104">For example, you can specify that an attribute or element value is a space-separated list of integers.</span></span>  
  
 <span data-ttu-id="3f4a8-105">Para obtener información completa acerca de cómo derivar nuevos tipos simples mediante el mecanismo de lista, vea el sitio web de W3C.</span><span class="sxs-lookup"><span data-stu-id="3f4a8-105">For comprehensive information about deriving new simple types by using the list mechanism, refer to the W3C Web site.</span></span> <span data-ttu-id="3f4a8-106">Para obtener varios vínculos a este y otros sitios Web, vea [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).</span><span class="sxs-lookup"><span data-stu-id="3f4a8-106">For various links to this and other Web sites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="3f4a8-107">Para derivar un tipo simple como una lista de ese tipo, seleccione la correspondiente **elemento de campo** nodo o **atributo de campo** nodo en el árbol de esquema y, a continuación, en la ventana Propiedades, seleccione un tipo simple en la lista desplegable lista para la **Base Data Type** propiedad.</span><span class="sxs-lookup"><span data-stu-id="3f4a8-107">To derive a simple type as a list of that type, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="3f4a8-108">Tan pronto como seleccione un valor para esta propiedad, el **Derived By** propiedad cambiará automáticamente su valor predeterminado a **restricción**, que actúa como el valor predeterminado de derivación de tipo.</span><span class="sxs-lookup"><span data-stu-id="3f4a8-108">As soon as you select a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="3f4a8-109">Debe cambiar la **Derived By** propiedad de **restricción** a **lista**, lo que hace que la **Base Data Type** propiedad se va a cambiar como el **tipo de elemento de** propiedad (a propósito, la propiedad cuyo nombre ha cambiado se mueve a una posición diferente en la lista de propiedades debido al orden alfabético de las propiedades).</span><span class="sxs-lookup"><span data-stu-id="3f4a8-109">You must change the **Derived By** property from **Restriction** to **List**, which causes the **Base Data Type** property to be renamed as the **Item Type** property (incidentally, the renamed property moves to a different position in the property list due to the alphabetical sorting of the properties).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f4a8-110">Puede usar a la vez los mecanismos de restricción y de lista de modo; es decir, crear una derivación de tipo simple con nombre mediante el mecanismo de restricción y, a continuación, usar dicho tipo como el tipo de elemento de otra derivación de tipo simple mediante el mecanismo de lista.</span><span class="sxs-lookup"><span data-stu-id="3f4a8-110">You can use the restriction and list mechanisms together, creating a named simple type derivation by using the restriction mechanism, and then using that as the item type in another simple type derivation by using the list mechanism.</span></span> <span data-ttu-id="3f4a8-111">Esto puede producir, por ejemplo, un valor que esté restringido a ser una lista de cadenas separadas por espacios que pertenezcan a un conjunto enumerado concreto de cadenas.</span><span class="sxs-lookup"><span data-stu-id="3f4a8-111">This can result, for example, in a value that is constrained to be a list of space-separated strings belonging to a particular enumerated set of strings.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="3f4a8-112">El uso del mecanismo de lista para la derivación de tipo simple puede ser complicado cuando el tipo de elemento elegido permite espacios, como las cadenas,</span><span class="sxs-lookup"><span data-stu-id="3f4a8-112">Using the list mechanism for simple type derivation can be complicated when the item type you choose is one that itself allows spaces, such as strings.</span></span> <span data-ttu-id="3f4a8-113">ya que este mecanismo utiliza espacios para separar los valores del tipo permitido en la lista.</span><span class="sxs-lookup"><span data-stu-id="3f4a8-113">This is because the list mechanism uses spaces to separate values of the allowed type in the list.</span></span>  
  
 <span data-ttu-id="3f4a8-114">Cuando cambia un **elemento de campo** nodo o **atributo de campo** nodo tener un datos escriba a tener un tipo de base de datos (con lo que se inicie el proceso de derivación de tipo simple) y, a continuación, establezca el **Derived By** propiedad **lista**, puede observar el siguiente cambio en el fragmento correspondiente de la vista XSD:</span><span class="sxs-lookup"><span data-stu-id="3f4a8-114">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), and then set the **Derived By** property to **List**, you can observe the following change in the corresponding fragment in the XSD view:</span></span>  
  
-   <span data-ttu-id="3f4a8-115">Antes, con un recién insertado **elemento de campo** nodo denominado **ZipCodeList**.</span><span class="sxs-lookup"><span data-stu-id="3f4a8-115">Before, with a newly inserted **Field Element** node named **ZipCodeList**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   <span data-ttu-id="3f4a8-116">Después de establecer el **Base Data Type** propiedad a xs: Integer y establecer el **Derived By** propiedad **lista** (después del cual el **Base Data Type**se cambia el nombre de propiedad para que sea el **tipo de elemento de** propiedad).</span><span class="sxs-lookup"><span data-stu-id="3f4a8-116">After setting the **Base Data Type** property to xs:integer, and setting the **Derived By** property to **List** (after which the **Base Data Type** property is renamed to be the **Item Type** property).</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList">  
                    <xs:simpleType>  
               <xs:list itemType="xs:integer" />   
                       </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="3f4a8-117">En un esquema de la vida real, sería mejor definir primero y el nombre de una derivación de tipo simple del entero que restringe el número entero a cinco dígitos, y, a continuación, para derivar el **ZipCodeList** elemento de ese tipo, de forma eficaz limitando la lista para enteros que tienen cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="3f4a8-117">In a real-life schema, it would be better to first define and name a simple type derivation of integer that restricts the integer to five digits, and then to derive the **ZipCodeList** element from that type, effectively limiting the list to integers having five digits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4a8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f4a8-118">See Also</span></span>  
 [<span data-ttu-id="3f4a8-119">Derivación de tipo simple</span><span class="sxs-lookup"><span data-stu-id="3f4a8-119">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)