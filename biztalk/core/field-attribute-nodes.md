---
title: Nodos de atributo de campo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e964c07-53e5-473f-84f2-05af4796cbbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 701acadc9d1612cc5b05a05970fc2c1b92bfbb9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246036"
---
# <a name="field-attribute-nodes"></a>Nodos Atributo de campo

## <a name="overview"></a>Información general
En el Editor de BizTalk, utilice **atributo de campo** nodos para describir elementos de información que son de naturaleza simple, como cadenas y números. Además, se usan cuando la información en cuestión aparece como el valor de un atributo de una instancia real de un mensaje, frente a cuando aparece como el contenido de un elemento XML. Para obtener información adicional acerca de la información que se almacena como contenido del elemento, vea [nodos elemento de campo](../core/field-element-nodes.md).  
  
 Aunque el mayor uso directo de **atributo de campo** nodos son como nodos secundarios de **registro** nodos, también pueden usarse como nodos secundarios del **grupo de atributos** nodos. En el último caso, el **atributo de campo** nodos que son elementos secundarios de un **grupo de atributos** están disponibles como atributos de cualquier nodo **registro** nodo que incluya ese  **Grupo de atributos** nodo. Para obtener más información acerca de **grupo de atributos** nodos, consulte [nodos grupo de atributos](../core/attribute-group-nodes.md).  
  
> [!NOTE]
>  En el Editor de BizTalk, los elementos de atributo y elemento pueden ser representados por un **campo** nodo, aunque tienen diferentes iconos asociados a ellos en la vista de árbol de esquema, una representación XML diferente en la ventana XSD, y diferentes propiedades en la ventana Propiedades de Visual Studio.  
  
 Para un determinado elemento de información de un mensaje XML (donde por elemento de información se entiende un tipo simple discreto individual, como una cadena o un número), siempre surge la duda de si dicha información se debe representar como el atributo de un elemento o como un subelemento de ese elemento. Como regla general, la representación de un elemento de información como un atributo suele ser más apropiada si los valores posibles son discretos, el número de valores es reducido y los valores suelen modificar la semántica del propio elemento. La representación de un elemento de información como un subelemento suele ser en cambio más idónea si los valores posibles pueden repetir una variable varias veces, probablemente están comprendidos en un intervalo de valores más amplio, pueden ser largos (como las cadenas largas) y son uno de los diversos valores hermanos si el orden es relevante. Si va a crear un esquema para un tipo existente de XML de documento, la posibilidad de usar un **elemento de campo** nodo o un **atributo de campo** ya se ha realizado el nodo de un elemento determinado de información para usted, y debe usar el nodo que coincide con el código XML.  
  
> [!NOTE]
>  No pueden tener nodos raíz **campo** atributos. **Campo** atributos conectado a la **raíz** nodo no se guardan con el esquema.  
  
## <a name="xsd-representation"></a>Representación XSD  
 Cuando un **atributo de campo** nodo se inserta en un **registro** nodo, éste se inserta al final de cualquier otro nodo secundario en el **registro** nodo. Esto incluye la inserción después de la **secuencia**, **elección**, o **todos los** elemento que contiene los nodos sin atributos y después de cualquier nodo de atributo que anteriormente se encontraban Insertar. En el ejemplo siguiente se muestra un nuevo **atributo de campo** nodo, en negrita, insertado al final de un **registro** nodo (con nodos de nombre que deja clara su identidad).  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="FieldElement" type="xs:string" />  
            <xs:element name="EmptyNestedRecord">  
                <xs:complexType />  
            </xs:element>  
        </xs:sequence>  
        <xs:attribute name="ExistingFieldAttribute" type="xs:string" />  
  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a>Vea también  
-  [Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md)   
-  [Propiedades de nodo](../core/node-properties.md)   
-  **Propiedades de nodo de elemento de campo**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
-  [Cómo establecer propiedades de nodo](../core/how-to-set-node-properties.md)   
-  [Nodos de grupo de atributos](../core/attribute-group-nodes.md)