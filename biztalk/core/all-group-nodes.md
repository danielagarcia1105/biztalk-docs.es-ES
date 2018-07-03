---
title: Todos los nodos de grupo | Microsoft Docs
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
ms.openlocfilehash: 084b12f16e72507a7d5568bdee022925eca52c0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989237"
---
# <a name="all-group-nodes"></a>Nodos Todos los grupos
En el Editor de BizTalk, puede insertar un **todos los grupos** nodo contenga otros nodos que va a aparecer cero o una vez, en cualquier orden. En el lenguaje de definición (XSD) del esquema XML, el **todos los grupos** tiene más limitaciones de uso que **secuencia** y **elección** grupos, lo que se traduce en pocas situaciones dentro de Editor de BizTalk, donde podrá crear un **todos los grupos** nodo.  

 Para usar un **todos los grupos** nodo en el Editor de BizTalk, deberá seguir algunos pasos adicionales: la manera más fácil de crear un **todos los grupos** nodo consiste en cambiar el valor de la **Group Order Type** propiedad del elemento primario **registro** nodo **todas**. Esto garantiza que todos los nodos subordinados de la **registro** nodo están dentro del **todos los grupos** nodo.  Consulte **Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

 Otra forma de usar un **todos los grupos** nodo en el Editor de BizTalk comienza por insertar un nuevo **registro** nodo. Después de insertar el nuevo **registro** nodo, cambio su **tipo de contenido** propiedad **ComplexContent**. A continuación, puede insertar un **todos los grupos** nodo como un elemento secundario de la **registro** nodo. Esto es necesario porque el **todos los grupos** solo se pueden insertar cuando existe herencia. Si especifica que la que contiene **registro** nodo incluye contenido complejo, su tipo de datos se convierte en según el tipo de datos **xs: anyType**, derivados por extensión.  

> [!NOTE]
>  En el Editor de BizTalk, el **todos los grupos** nodo se representa con la cadena \<todas > en la vista de árbol de esquema. Si establece una referencia a un **todos los grupos** nodo, por ejemplo a x, se representa como \<Group: x > en la vista de árbol de esquema.  

## <a name="xsd-representation"></a>Representación XSD  
 Un **todos los grupos** nodo se puede insertar en una **registro** nodo, pero sólo si es el nodo secundario sin atributos sólo eso **registro** nodo. En el ejemplo siguiente se muestra, en pasos, cómo una nueva **todos los grupos** nodo se representa en el lenguaje de definición (XSD) del esquema XML como un **todas** se realizan como los pasos en el Editor de BizTalk (con nodos con nombre para que quede clara su identidad).  

```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  

 Después de agregar un nuevo registro, como se muestra en el fragmento XSD anterior, su **tipo de contenido** propiedad cambia a **ComplexContent**, lo que en las siguientes modificaciones de XSD.  

```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
             <xs:extension base="xs:anyType" />  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  

 Ahora el **todos los grupos** nodo se puede insertar como un elemento secundario del nuevo registro, como se muestra en el siguiente fragmento XSD.  

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

 Por último, puede insertar los nodos correspondientes como secundarios del nuevo **todos los grupos** nodo. El ejemplo siguiente se muestra un **registro** nodo y un **elemento de campo** nodo insertado como nodos secundarios del nuevo **todos los grupos** nodo.  

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

## <a name="see-also"></a>Vea también  
- [Representación de esquemas en BizTalk](../core/biztalk-representation-of-schemas.md)   
- [Propiedades de los nodos](../core/node-properties.md)   
- **Propiedades de nodo de grupo de secuencias** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] 
- [Cómo establecer las propiedades de nodo](../core/how-to-set-node-properties.md)
