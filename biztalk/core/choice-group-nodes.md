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
# <a name="choice-group-nodes"></a>Nodos Grupos de elecciones
En el Editor de BizTalk, puede insertar un **grupo de elecciones** nodo contenga otros nodos (o subárboles completos de nodos), solo uno de los cuales puede aparecer en un mensaje de instancia. Un determinado mensaje de instancia, si es válido, solo tendrá presente una de las elecciones. Los nodos contenidos deben ser nodos que se correspondan con elementos XML, pero no pueden ser nodos que se correspondan con atributos XML.  

> [!NOTE]
>  En el Editor de BizTalk, el **grupo de elecciones** nodo se representa con la cadena \<elección\> en la vista de árbol de esquema. Si establece una referencia a un **grupo de elecciones** nodo, por ejemplo, x, se representa como \<Group: x\> en la vista de árbol de esquema.  

## <a name="xsd-representation"></a>Representación XSD  
 Cuando un **grupo de elecciones** nodo se inserta en un **registro** nodo, éste se inserta al final de cualquier otro nodo secundario dentro de la **secuencia**, **elección**, o **todas** elemento en el **registro** nodo. En el ejemplo siguiente se muestra, en negrita, cómo una nueva **grupo de elecciones** nodo se representa en el lenguaje de definición (XSD) del esquema XML como un **elección** elemento insertado al final de la **secuencia**  elemento en un **registro** nodo (con nodos con el nombre que deja clara su identidad).  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  

```  

 De forma predeterminada, el **elección** elemento tiene un **minOccurs** valor de cero (0), lo que indica que necesita realizar ninguna de las opciones de atributo. Puede cambiar este valor en la ventana Propiedades de Visual Studio cuando el **grupo de elecciones** nodo está seleccionado en la vista de árbol de esquema.  

 El ejemplo siguiente muestra el mismo **elección** elemento con el esquema XSD **elemento** elementos que corresponden a dos subordinado **registro** nodos.  

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

 En este ejemplo, dos relacionado **registro** nodos se utilizan para describir el hecho de que un mensaje de instancia o tendrá un registro con información de dirección de Estados Unidos o en un registro con información de dirección en todo el mundo. Además, el **minOccurs** y **maxOccurs** propiedades de la **grupo de elecciones** nodo han establecido en uno (1) en la ventana Propiedades de Visual Studio, lo que produce el *minOccurs* y *maxOccurs* los atributos de la **elección** que se va a establecer en uno (1) en la representación XSD del elemento.  

## <a name="see-also"></a>Vea también  
- [Representación de esquemas en BizTalk](../core/biztalk-representation-of-schemas.md)   
- [Propiedades de los nodos](../core/node-properties.md)   
- **Propiedades de nodo de grupo de secuencias** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]     
- [Cómo establecer las propiedades de nodo](../core/how-to-set-node-properties.md)
