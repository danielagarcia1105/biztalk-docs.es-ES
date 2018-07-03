---
title: Registrar los nodos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43af077d-5db8-43ca-8bd0-e3a9e3ebe2b0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ec23dcf604e1bd454ba7e69a57c250cf3b1872f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982349"
---
# <a name="record-nodes"></a>Nodos Registro
En el Editor de BizTalk, utiliza un **registro** nodo para representar una colección de información, los elementos individuales de los cuales pueden ser:  

- Tipos simples de información, como cadenas y números, representados como nodos de campo secundarios. Estos nodos de campo secundarios pueden ser **elemento de campo** nodos o **atributo de campo** nodos. Para obtener más información acerca de estos dos tipos de nodos de campo, vea [nodos elemento de campo](../core/field-element-nodes.md) y [nodos atributo de campo](../core/field-attribute-nodes.md).  

- Tipos complejos de información, representado como elemento secundario **registro** nodos o como un nodo de grupo (**grupo Sequence** nodo, **grupo de elecciones** nodo, o **todos los grupos** nodo).  

- Cualquier tipo no examinado de información, representado como elemento secundario **cualquier elemento** o **cualquier atributo** nodos.  

- Grupos de atributos, representados por un **grupo de atributos** nodo.  

  Al insertar un nuevo nodo secundario en un **registro** siempre se inserta el nodo, el nodo secundario al final de los nodos secundarios actuales. Dentro de la representación de lenguaje de definición (XSD) de esquemas XML, se agregan nuevos elementos al final de sus áreas correspondientes, lo que significa que los elementos sin atributos se agregan al final de los elementos dentro de la **secuencia**, **elección**, **todas**, o **grupo** elemento y atributo elementos se agregan al final de cualquier otro elemento de atributo, que se producen después de la **secuencia** , **elección**, **todas**, o **grupo** elemento.  

## <a name="xsd-representation"></a>Representación XSD  
 Cuando se inserte por primera vez, la representación XSD de un nuevo **registro** nodo consta de tan sólo tres líneas, tal como se muestra en el ejemplo siguiente.  

```  
<xs:element name="Record">  
      <xs:complexType />  
</xs:element>  
```  

 Cuando cualquier nodo secundario que no sea uno de los tres nodos de atributo (**atributo de campo**, **grupo de atributos**, y **cualquier atributo**) se agrega a un **registro** nodo, de forma predeterminada, se coloca dentro de un **secuencia** elemento dentro de la **complexType** elemento. El **secuencia** elemento se agrega cuando el primer nodo secundario sin atributos se agregan y quitan si se eliminan todos los nodos de secundarios sin atributos. Se agregan los tres tipos de nodos de atributo dentro de la **complexType** elemento, pero fuera y después de cualquier **secuencia** elemento.  

 El **secuencia** en qué sin atributos se agregan nodos secundarios del elemento también puede ser un **elección** o **todas** elemento si cambia el **Group Order Type (nodo Propiedad de todos los esquemas)** propiedad de nodo correspondiente en el árbol de esquema para **elección** o **todas**, respectivamente.  

 En el ejemplo siguiente, la **registro** nodo ha sido shipTo cuyo nombre ha cambiado. Las ubicaciones dentro de la **registro** nodo donde se agregan nodos de atributo y sin atributos se muestran entre paréntesis.  

```  
<xs:element name="">  
    <xs:complexType>  
        <xs:sequence>  
            [Nonattribute child nodes of the record go here.]  
            [Always add new nonattribute child nodes to the end.]  
        </xs:sequence>  
            [Attribute child nodes of the record go here.]  
            [Always add new attribute child nodes to the end.]  
    </xs:complexType>  
</xs:element>  

```  

## <a name="see-also"></a>Vea también  
- [Representación de esquemas en BizTalk](../core/biztalk-representation-of-schemas.md)   
- [Propiedades de los nodos](../core/node-properties.md)   
- **Registre las propiedades de nodo** y **Group Order Type (propiedad de nodo de todos los esquemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
- [Cómo establecer las propiedades de nodo](../core/how-to-set-node-properties.md)
