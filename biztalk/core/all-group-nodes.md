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
# <a name="all-group-nodes"></a>Nodos Todos los grupos
En el Editor de BizTalk, puede insertar un **todos los grupos** nodo para contener otros nodos que va a aparecer cero o una vez, en cualquier orden. En el lenguaje de definición (XSD) de esquemas XML, el **todos los grupos** tiene más limitaciones de uso que **secuencia** y **elección** grupos, que se traduce en algunos casos poco frecuentes en El Editor de BizTalk donde podrá crear un **todos los grupos** nodo.  
  
 Para usar un **todos los grupos** nodo en el Editor de BizTalk, tiene que seguir algunos pasos adicionales: la manera más fácil de crear un **todos los grupos** nodo consiste en cambiar el valor de la **Group Order Type** propiedad del elemento primario **registro** nodo **todos los**. Esto garantiza que todos los nodos subordinados de la **registro** nodo contenidas en el **todos los grupos** nodo.  Vea **Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 Otra manera de usar un **todos los grupos** en el Editor de BizTalk comienza por insertar un nuevo **registro** nodo. Después de insertar el nuevo **registro** nodo, cambiar su **tipo de contenido** propiedad **ComplexContent**. A continuación, puede insertar un **todos los grupos** nodo como un elemento secundario de la **registro** nodo. Esto es necesario porque el **todos los grupos** sólo puede insertar cuando existe herencia. Mediante la especificación de que la que contiene **registro** nodo incluye contenido complejo, su tipo de datos se basará en el tipo de datos **xs: anyType**, derivado mediante extension.  
  
> [!NOTE]
>  En el Editor de BizTalk, el **todos los grupos** nodo se representa con la cadena \<todos > en la vista de árbol de esquema. Si establece una referencia a un **todos los grupos** nodo, como a x, se representa como \<Group: x > en la vista de árbol de esquema.  
  
## <a name="xsd-representation"></a>Representación XSD  
 Un **todos los grupos** nodo se pueden insertar en una **registro** nodo, pero solo si es el nodo secundario sin atributos sólo de ese **registro** nodo. En el ejemplo siguiente se muestra, en los pasos, cómo una nueva **todos los grupos** nodo se representa en el lenguaje de definición (XSD) de esquemas XML como un **todos los** elemento como los pasos en el Editor de BizTalk se llevan a cabo (con nodos denominados que deja clara su identidad).  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  
  
 Después de agregar un nuevo registro, como se muestra en el fragmento XSD anterior, su **tipo de contenido** propiedad se cambia a **ComplexContent**, da lugar a las siguientes modificaciones de XSD.  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
             <xs:extension base="xs:anyType" />  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  
  
 Ahora el **todos los grupos** se puede insertar el nodo como un elemento secundario del nuevo registro, como se muestra en el siguiente fragmento XSD.  
  
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
  
 Por último, puede insertar los nodos correspondientes como elementos secundarios del nuevo **todos los grupos** nodo. El ejemplo siguiente muestra un **registro** nodo y un **elemento de campo** nodo insertado como nodos secundarios del nuevo **todos los grupos** nodo.  
  
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
-  [Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md)   
-  [Propiedades de nodo](../core/node-properties.md)   
-  **Propiedades de nodo de grupo de secuencias**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] 
-  [Cómo establecer propiedades de nodo](../core/how-to-set-node-properties.md)