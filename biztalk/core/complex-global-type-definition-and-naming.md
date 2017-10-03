---
title: "Definición de tipo Global complejo y nomenclatura | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5a12956-7b77-4be8-b323-38363d04fcbc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe00c68f22dde956279f2dd5ac06d03bf9cb84d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="complex-global-type-definition-and-naming"></a>Definición y nomenclatura de los tipos globales complejos
Para definir un tipo global complejo en el Editor de BizTalk, defina el primer caso de tipo complejo que aparezca en una de las ubicaciones donde se usará el tipo global, después de que se haya convertido a un tipo global. Siguiendo con el ejemplo de dirección, puede definir el tipo complejo de dirección mientras configura una dirección de envío dentro del esquema.  
  
 Una vez definido el tipo complejo, puede convertirlo a un tipo global complejo si le asigna un nombre de tipo. Para ello, seleccione el nodo que corresponde al tipo complejo, que suele ser un **registro** nodo y, a continuación, escriba un nuevo nombre de tipo en la **Data Structure Type** propiedad de ese nodo. Aunque no vea cambios que se produzcan en el árbol de esquema cuando se asigne un nombre a esta propiedad (como por ejemplo, **GlobalAddrType**, como en el ejemplo siguiente), si examina lo que ocurre dentro de la representación XSD subyacente del esquema, vería el siguiente cambio (abreviado).  
  
 Antes, con la estructura de dirección inicialmente definida dentro del contexto de la **ShippingAddress** lo siguiente de elemento, se ha producido.  
  
```  
<xs:schema>  
  <xs:element name="Root">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="ShippingAddress">  
        [address structure initially defined here.]  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 Después de la **ShippingAddress** nodo tiene un nombre único su **Data Structure Type** propiedad, haciendo que esté disponible como un tipo global complejo y está sujeta a reutilizar en distintas ubicaciones dentro de la esquema, ocurre lo siguiente.  
  
```  
<xs:schema>  
  <xs:element name="Root">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="ShippingAddress" type="GlobalAddrType" />  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  <xs:complexType name="GlobalAddrType">  
  [address structure now defined globally here.]  
  </xs:complexType>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Vea también  
 [Tipo reutilización y derivaciones](../core/type-reuse-and-derivations.md)   
 [Cómo crear referencias a otro nodo o tipo](../core/how-to-create-references-to-another-node-or-type.md)