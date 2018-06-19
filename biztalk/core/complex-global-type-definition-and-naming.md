---
title: Definición de tipo Global complejo y nomenclatura | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5a12956-7b77-4be8-b323-38363d04fcbc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe00c68f22dde956279f2dd5ac06d03bf9cb84d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231628"
---
# <a name="complex-global-type-definition-and-naming"></a><span data-ttu-id="adfd0-102">Definición y nomenclatura de los tipos globales complejos</span><span class="sxs-lookup"><span data-stu-id="adfd0-102">Complex Global Type Definition and Naming</span></span>
<span data-ttu-id="adfd0-103">Para definir un tipo global complejo en el Editor de BizTalk, defina el primer caso de tipo complejo que aparezca en una de las ubicaciones donde se usará el tipo global, después de que se haya convertido a un tipo global.</span><span class="sxs-lookup"><span data-stu-id="adfd0-103">Within BizTalk Editor, you begin to define a complex global type by defining the first occurrence of the complex type in one of the locations where the global type will be used, after it has been converted to a global type.</span></span> <span data-ttu-id="adfd0-104">Siguiendo con el ejemplo de dirección, puede definir el tipo complejo de dirección mientras configura una dirección de envío dentro del esquema.</span><span class="sxs-lookup"><span data-stu-id="adfd0-104">Continuing with the address example, you might define the complex address type in the course of defining a shipping address within the schema.</span></span>  
  
 <span data-ttu-id="adfd0-105">Una vez definido el tipo complejo, puede convertirlo a un tipo global complejo si le asigna un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="adfd0-105">After the complex type is defined, you can convert it to a global complex type by giving it a type name.</span></span> <span data-ttu-id="adfd0-106">Para ello, seleccione el nodo que corresponde al tipo complejo, que suele ser un **registro** nodo y, a continuación, escriba un nuevo nombre de tipo en la **Data Structure Type** propiedad de ese nodo.</span><span class="sxs-lookup"><span data-stu-id="adfd0-106">You do this by selecting the node that corresponds to the complex type, which will generally be a **Record** node, and then typing a new type name into the **Data Structure Type** property of that node.</span></span> <span data-ttu-id="adfd0-107">Aunque no vea cambios que se produzcan en el árbol de esquema cuando se asigne un nombre a esta propiedad (como por ejemplo, **GlobalAddrType**, como en el ejemplo siguiente), si examina lo que ocurre dentro de la representación XSD subyacente del esquema, vería el siguiente cambio (abreviado).</span><span class="sxs-lookup"><span data-stu-id="adfd0-107">Although no visible changes occur in the schema tree when you give this property a name (such as, **GlobalAddrType**, as in the following example), if you examine what happens within the underlying XSD representation of the schema, you would see the following (abbreviated) change.</span></span>  
  
 <span data-ttu-id="adfd0-108">Antes, con la estructura de dirección inicialmente definida dentro del contexto de la **ShippingAddress** lo siguiente de elemento, se ha producido.</span><span class="sxs-lookup"><span data-stu-id="adfd0-108">Before, with the address structure first defined within the context of the **ShippingAddress** element, the following occurred.</span></span>  
  
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
  
 <span data-ttu-id="adfd0-109">Después de la **ShippingAddress** nodo tiene un nombre único su **Data Structure Type** propiedad, haciendo que esté disponible como un tipo global complejo y está sujeta a reutilizar en distintas ubicaciones dentro de la esquema, ocurre lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="adfd0-109">After the **ShippingAddress** node has been given a unique name in its **Data Structure Type** property, causing it to become available as a complex global type and subject to reuse in multiple places within the schema, the following occurs.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="adfd0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="adfd0-110">See Also</span></span>  
 <span data-ttu-id="adfd0-111">[Tipo reutilización y derivaciones](../core/type-reuse-and-derivations.md) </span><span class="sxs-lookup"><span data-stu-id="adfd0-111">[Type Reuse and Derivations](../core/type-reuse-and-derivations.md) </span></span>  
 [<span data-ttu-id="adfd0-112">Cómo crear referencias a otro nodo o tipo</span><span class="sxs-lookup"><span data-stu-id="adfd0-112">How to Create References to Another Node or Type</span></span>](../core/how-to-create-references-to-another-node-or-type.md)