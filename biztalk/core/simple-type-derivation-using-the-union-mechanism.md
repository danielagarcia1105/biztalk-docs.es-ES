---
title: Derivación de tipo simple mediante el mecanismo de unión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e51ae390-78f5-4fb9-9163-2a8023aea1ec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1414fa506f824415de8e8449e8b2b27befd2fc76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270380"
---
# <a name="simple-type-derivation-using-the-union-mechanism"></a><span data-ttu-id="bd5b2-102">Derivación de tipo simple mediante el mecanismo de unión</span><span class="sxs-lookup"><span data-stu-id="bd5b2-102">Simple Type Derivation Using the Union Mechanism</span></span>
<span data-ttu-id="bd5b2-103">Al derivar un nuevo tipo simple a partir de un tipo simple existente con el mecanismo de unión, se especifica que el valor de este atributo o elemento puede ser de más de un tipo, según una lista de tipos que proporcione.</span><span class="sxs-lookup"><span data-stu-id="bd5b2-103">When you derive a new simple type from an existing simple type by using the union mechanism, you are specifying that the value for this attribute or element can be of more than one type, according to a list of types that you specify.</span></span> <span data-ttu-id="bd5b2-104">Por ejemplo, puede especificar que un valor de atributo o elemento es una fecha, una hora o un valor de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="bd5b2-104">For example, you can specify that an attribute or element value is either a date, a time, or a date/time value.</span></span>  
  
 <span data-ttu-id="bd5b2-105">Para obtener información completa acerca de cómo derivar nuevos tipos simples mediante el mecanismo de unión, consulte el sitio Web de W3C.</span><span class="sxs-lookup"><span data-stu-id="bd5b2-105">For comprehensive information about deriving new simple types by using the union mechanism, refer to the W3C website.</span></span> <span data-ttu-id="bd5b2-106">Para obtener varios vínculos a este y otros sitios Web, vea [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).</span><span class="sxs-lookup"><span data-stu-id="bd5b2-106">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="bd5b2-107">Para derivar un tipo simple como una unión de varios tipos posibles, seleccione la correspondiente **elemento de campo** nodo o **atributo de campo** nodo en el árbol de esquema y, a continuación, en la ventana Propiedades, seleccione un tipo simple de la lista desplegable para la **Base Data Type** propiedad.</span><span class="sxs-lookup"><span data-stu-id="bd5b2-107">To derive a simple type as a union of several possible types, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="bd5b2-108">Tan pronto como haya seleccionado un valor para esta propiedad, el **Derived By** propiedad cambiará automáticamente su valor predeterminado a **restricción**, que actúa como el valor predeterminado de derivación de tipo.</span><span class="sxs-lookup"><span data-stu-id="bd5b2-108">As soon as you have selected a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="bd5b2-109">Debe cambiar la **Derived By** propiedad de **restricción** a **unión**, lo que hace que la **Base Data Type** propiedad se va a cambiar como el **tipos de miembro** propiedad (a propósito, la propiedad cuyo nombre ha cambiado se mueve a una posición diferente en la lista de propiedades debido al orden alfabético de las propiedades).</span><span class="sxs-lookup"><span data-stu-id="bd5b2-109">You must change the **Derived By** property from **Restriction** to **Union**, which causes the **Base Data Type** property to be renamed as the **Member Types** property (incidentally, the renamed property moves to a different position in the property list due to the alphabetical sorting of the properties).</span></span>  
  
 <span data-ttu-id="bd5b2-110">Por último, puede usar las casillas de verificación en la **tipos de miembro** lista de comprobación de lista desplegable para seleccionar tipos adicionales para permitir que los valores correspondientes en mensajes de instancia.</span><span class="sxs-lookup"><span data-stu-id="bd5b2-110">Finally, you can use the check boxes in the **Member Types** drop-down checklist to select additional types to allow for corresponding values in instance messages.</span></span>  
  
 <span data-ttu-id="bd5b2-111">Cuando cambia un **elemento de campo** nodo o **atributo de campo** nodo tener un datos escriba a tener un tipo de base de datos (con lo que se inicie el proceso de derivación de tipo simple) y, a continuación, establezca el **Derived By** propiedad **unión**, puede observar el siguiente cambio en el fragmento correspondiente de la vista XSD.</span><span class="sxs-lookup"><span data-stu-id="bd5b2-111">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), and then set the **Derived By** property to **Union**, you can observe the following change in the corresponding fragment in the XSD view.</span></span>  
  
-   <span data-ttu-id="bd5b2-112">Antes, con un recién insertado **elemento de campo** nodo denominado **DatesAndOrTimes**.</span><span class="sxs-lookup"><span data-stu-id="bd5b2-112">Before, with a newly inserted **Field Element** node named **DatesAndOrTimes**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   <span data-ttu-id="bd5b2-113">Después de establecer el **Base Data Type** propiedad a **xs: Date**y estableciendo el **Derived By** propiedad a **unión** (después del cual el  **Base Data Type** se cambia el nombre de propiedad para que sea el **tipos de miembro** propiedad) y, a continuación, seleccionar también **xs: DateTime** y **xs: Time** como adicional permite tipos en el **tipos de miembro** lista de comprobación de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bd5b2-113">After setting the **Base Data Type** property to **xs:date**, and setting the **Derived By** property to **Union** (after which the **Base Data Type** property is renamed to be the **Member Types** property), and then also selecting **xs:datetime** and **xs:time** as additional allowed types in the **Member Types** drop-down checklist.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bd5b2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd5b2-114">See Also</span></span>  
 [<span data-ttu-id="bd5b2-115">Derivación de tipo simple</span><span class="sxs-lookup"><span data-stu-id="bd5b2-115">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)