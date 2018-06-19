---
title: Derivación de tipo simple mediante el mecanismo de restricción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4ca712e-9563-4917-9bfc-1033a36773e8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dda4b8ad64f1edf262446f1633eda109ba7074ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271732"
---
# <a name="simple-type-derivation-using-the-restriction-mechanism"></a><span data-ttu-id="ebc06-102">Derivación de tipo simple mediante el mecanismo de restricción</span><span class="sxs-lookup"><span data-stu-id="ebc06-102">Simple Type Derivation Using the Restriction Mechanism</span></span>

## <a name="overview"></a><span data-ttu-id="ebc06-103">Información general</span><span class="sxs-lookup"><span data-stu-id="ebc06-103">Overview</span></span>
<span data-ttu-id="ebc06-104">Al derivar un nuevo tipo simple a partir de un tipo simple existente con el mecanismo de restricción, normalmente se restringen los valores permitidos en un mensaje de instancia para ese atributo o valor de elemento a un subconjunto de los valores permitidos por el tipo simple base.</span><span class="sxs-lookup"><span data-stu-id="ebc06-104">When you derive a new simple type from an existing simple type by using the restriction mechanism, you are typically restricting the values allowed in an instance message for that attribute or element value to a subset of those values allowed by the base simple type.</span></span> <span data-ttu-id="ebc06-105">Por ejemplo, puede restringir un tipo string para que sea una de las distintas cadenas enumeradas.</span><span class="sxs-lookup"><span data-stu-id="ebc06-105">For example, you can restrict a string type to be one of several enumerated strings.</span></span>  
  
 <span data-ttu-id="ebc06-106">Para obtener información completa acerca de cómo derivar nuevos tipos simples mediante el mecanismo de restricción, consulte el sitio Web de W3C.</span><span class="sxs-lookup"><span data-stu-id="ebc06-106">For comprehensive information about deriving new simple types by using the restriction mechanism, refer to the W3C website.</span></span> <span data-ttu-id="ebc06-107">Para obtener varios vínculos a este y otros sitios Web, vea [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).</span><span class="sxs-lookup"><span data-stu-id="ebc06-107">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
## <a name="field-element-and-field-attribute"></a><span data-ttu-id="ebc06-108">Elemento de campo y atributo de campo</span><span class="sxs-lookup"><span data-stu-id="ebc06-108">Field Element and Field Attribute</span></span>
 <span data-ttu-id="ebc06-109">Para derivar un tipo simple mediante una restricción, seleccione la correspondiente **elemento de campo** nodo o **atributo de campo** nodo en el árbol de esquema y, a continuación, en la ventana Propiedades, seleccione un tipo simple en la lista desplegable lista para la **Base Data Type** propiedad.</span><span class="sxs-lookup"><span data-stu-id="ebc06-109">To derive a simple type by using restriction, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="ebc06-110">Tan pronto como haya seleccionado un valor para esta propiedad, el **Derived By** propiedad cambiará automáticamente su valor predeterminado a **restricción**, que actúa como el valor predeterminado de derivación de tipo.</span><span class="sxs-lookup"><span data-stu-id="ebc06-110">As soon as you have selected a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="ebc06-111">Además, una nueva categoría de propiedades denominada **restricción**, disponible en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="ebc06-111">Also, a whole new category of properties, called **Restriction**, becomes available in the Properties window.</span></span>  
  
 <span data-ttu-id="ebc06-112">Según el tipo de datos base seleccionado, podrá configurar distintas propiedades de esta nueva categoría.</span><span class="sxs-lookup"><span data-stu-id="ebc06-112">Depending on the base data type you select, different properties are available to be set in this new category.</span></span> <span data-ttu-id="ebc06-113">Por ejemplo, si el tipo de base de datos es numérico, las propiedades **MaxFacet Type** (cuando **MaxFacet Value** está establecido), **MaxFacet Value**, **MinFacet Type** (cuando **MinFacet Value** está establecido), y **MinFacet Value** están disponibles para definir un intervalo exclusivo o inclusivo de valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="ebc06-113">For example, if the base data type is numeric, the properties **MaxFacet Type** (when **MaxFacet Value** is set), **MaxFacet Value**, **MinFacet Type** (when **MinFacet Value** is set), and **MinFacet Value** are available for defining an inclusive or exclusive range of allowed values.</span></span> <span data-ttu-id="ebc06-114">Si el tipo de datos base es un tipo de cadena, la **longitud**, **longitud máxima**, y **longitud mínima** propiedades están disponibles para restringir la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="ebc06-114">If the base data type is a string type, the **Length**, **Maximum Length**, and **Minimum Length** properties are available for constraining the length of the string.</span></span>  
  
 <span data-ttu-id="ebc06-115">Para obtener más información acerca de las distintas propiedades de restricción de nodos de campo, vea la **propiedades de nodo de elemento de campo** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="ebc06-115">For more information about the various restriction properties of field nodes, see the **Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="ebc06-116">Cuando cambia un **elemento de campo** nodo o **atributo de campo** nodo de tener un tipo de datos a tener un tipo de base de datos (con lo que se inicie el proceso de derivación de tipo simple), deje el  **Derived por** propiedad establecida en **restricción**y proporcionar una restricción de enumeración basada en los valores de cadena permitidos, puede observar los cambios siguientes en el fragmento correspondiente de la vista XSD:</span><span class="sxs-lookup"><span data-stu-id="ebc06-116">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), leave the **Derived By** property set to **Restriction**, and provide an enumeration-based restriction to the allowed string values, you can observe the following changes in the corresponding fragment in the XSD view:</span></span>  
  
-   <span data-ttu-id="ebc06-117">Antes, con un recién insertado **elemento de campo** nodo denominado **WestCoastStates**.</span><span class="sxs-lookup"><span data-stu-id="ebc06-117">Before, with a newly inserted **Field Element** node named **WestCoastStates**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   <span data-ttu-id="ebc06-118">Después de establecer el **Base Data Type** propiedad en "xs: String" y deja el valor predeterminado de derivación de **restricción** para el **Derived By** propiedad.</span><span class="sxs-lookup"><span data-stu-id="ebc06-118">After setting the **Base Data Type** property to "xs:string", and leaving the derivation default of **Restriction** for the **Derived By** property.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" >  
                    <xs:simpleType>  
                        <xs:restriction base="xs:string" />  
                    </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   <span data-ttu-id="ebc06-119">Después de establecer el **enumeración** propiedad en la categoría de restricción a los nombres de los tres estados de la costa oeste de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="ebc06-119">After setting the **Enumeration** property in the Restriction category to the names of the three states on the west coast of the continental United States.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates">  
                    <xs:simpleType>  
                        <xs:restriction base="xs:string" />  
                            <xs:enumeration value="Washington" />  
                            <xs:enumeration value="Oregon" />  
                            <xs:enumeration value="California" />  
                        </xs:restriction>  
                    </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ebc06-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebc06-120">See Also</span></span>  
 [<span data-ttu-id="ebc06-121">Derivación de tipo simple</span><span class="sxs-lookup"><span data-stu-id="ebc06-121">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)