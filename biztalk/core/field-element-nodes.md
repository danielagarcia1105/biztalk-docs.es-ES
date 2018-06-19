---
title: Nodos de elemento de campo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65b5e1f6-283f-4172-9bc2-f04a0ea6753d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74c3732ee315ad307f49760e367449216c3e01da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245988"
---
# <a name="field-element-nodes"></a>Nodos Elemento de campo

## <a name="overview"></a>Información general
En el Editor de BizTalk, utilice **elemento de campo** nodos para describir elementos de información que son de naturaleza simple, como cadenas y números. Además, se usan cuando la información en cuestión aparece como el contenido de un elemento XML en una instancia real de un mensaje, frente a cuando aparece como el valor de un atributo asociado con un elemento XML. Para obtener información adicional acerca de la información que se almacena como valores de atributo, vea [nodos atributo de campo](../core/field-attribute-nodes.md).  
  
> [!NOTE]
>  En el Editor de BizTalk, los elementos de atributo y elemento pueden ser representados por un **campo** nodo, aunque tienen diferentes iconos asociados con ellos en la vista de árbol de esquema, una representación XML diferente en la ventana XSD, y diferentes propiedades en la ventana Propiedades de Visual Studio.  
  
 Para un determinado elemento de información de un mensaje XML (donde por elemento de información se entiende un tipo simple discreto individual, como una cadena o un número), siempre surge la duda de si dicha información se debe representar como el atributo de un elemento o como un subelemento de ese elemento. Como regla general, la representación de un elemento de información como un atributo suele ser más apropiada si los valores posibles son discretos, el número de valores es reducido y los valores suelen modificar la semántica del propio elemento. La representación de un elemento de información como un subelemento suele ser en cambio más idónea si los valores posibles pueden repetir una variable varias veces, probablemente están comprendidos en un intervalo de valores más amplio, pueden ser largos (como las cadenas largas) y son uno de los diversos valores hermanos si el orden es relevante. Si está creando un esquema para un tipo existente de XML de documento, la posibilidad de usar un **elemento de campo** nodo o un **atributo de campo** ya se ha realizado el nodo de un elemento determinado de información para usted, y se debe usar el nodo que coincide con el código XML.  
  
## <a name="xsd-representation"></a>Representación XSD  
 Cuando un **elemento de campo** nodo se inserta en un **registro** nodo, se inserta al final de cualquier otro nodo secundario dentro de la **secuencia** elemento en el  **Registro** nodo. En el ejemplo siguiente se muestra un nuevo **elemento de campo** nodo, en negrita, insertado al final de la **secuencia** elemento en un **registro** nodo (con nombre que deja clara su identidad de nodos ).  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
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