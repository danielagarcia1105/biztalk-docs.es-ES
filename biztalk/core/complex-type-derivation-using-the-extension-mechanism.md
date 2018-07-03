---
title: Derivación de tipo complejo mediante el mecanismo de extensión | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7125fb5b-f77a-47c9-8000-f2332940df89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2addaf540407c7b899cc81a7512fead9bb205ad5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022234"
---
# <a name="complex-type-derivation-using-the-extension-mechanism"></a><span data-ttu-id="bad47-102">Derivación de tipo complejo mediante el mecanismo de extensión</span><span class="sxs-lookup"><span data-stu-id="bad47-102">Complex Type Derivation Using the Extension Mechanism</span></span>
<span data-ttu-id="bad47-103">Un tipo complejo derivado por extensión es un supraconjunto funcional del tipo de datos base correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bad47-103">A complex type derived by extension is a functional superset of its base data type.</span></span> <span data-ttu-id="bad47-104">Como el propio nombre indica, el tipo de datos base correspondiente constituye la base para el tipo que se está definiendo, donde las diferencias con respecto al tipo base son de naturaleza aditiva.</span><span class="sxs-lookup"><span data-stu-id="bad47-104">As the name implies, its base data type is the basis for the type being defined, where the differences from the base type are additive.</span></span> <span data-ttu-id="bad47-105">En este tema se proporciona un ejemplo en el que los dos elementos **ShippingAddress** y **BillingAddress** se basan en el tipo global complejo **GlobalAddrType**.</span><span class="sxs-lookup"><span data-stu-id="bad47-105">This topic provides an example in which the two elements **ShippingAddress** and **BillingAddress** are based on the complex global type **GlobalAddrType**.</span></span> <span data-ttu-id="bad47-106">**Valor de ShippingAddress** simplemente se define como de tipo **GlobalAddrType**, mientras que **BillingAddress** está definido para ampliar el tipo **GlobalAddrType**.</span><span class="sxs-lookup"><span data-stu-id="bad47-106">**ShippingAddress** is simply defined to be of type **GlobalAddrType**, whereas **BillingAddress** is defined to extend the type **GlobalAddrType**.</span></span> <span data-ttu-id="bad47-107">Al final del ejemplo, se agrega un elemento adicional a **BillingAddress**, denominado **departamento**, con un tipo de cadena y un valor predeterminado Accounts Payable.</span><span class="sxs-lookup"><span data-stu-id="bad47-107">At the end of the example, an additional element is added to **BillingAddress**, named **Department**, with a type of string and a default value of Accounts Payable.</span></span>  
  
 <span data-ttu-id="bad47-108">Para obtener información completa acerca de cómo derivar nuevos tipos complejos mediante el mecanismo de extensión, consulte el sitio Web de W3C.</span><span class="sxs-lookup"><span data-stu-id="bad47-108">For comprehensive information about deriving new complex types by using the extension mechanism, refer to the W3C website.</span></span> <span data-ttu-id="bad47-109">Para los diversos vínculos a este y otros sitios Web, consulte [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).</span><span class="sxs-lookup"><span data-stu-id="bad47-109">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="bad47-110">Para derivar un tipo global complejo, por extensión, en otra ubicación en el árbol de esquema, empiece por insertar un nuevo **registro** nodo en la ubicación deseada.</span><span class="sxs-lookup"><span data-stu-id="bad47-110">To derive from a complex global type by extension, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="bad47-111">A continuación, establezca su **Base Data Type** propiedad en el nombre de un tipo global complejo.</span><span class="sxs-lookup"><span data-stu-id="bad47-111">Then set its **Base Data Type** property to the name of a complex global type.</span></span>  
  
 <span data-ttu-id="bad47-112">En el ejemplo siguiente, **BillingAddress** es el nombre de las filas recién insertadas **registro** nodo, y **GlobalAddrType** es el nombre del tipo global complejo desde la que se se deriva y que tiene la intención de extender.</span><span class="sxs-lookup"><span data-stu-id="bad47-112">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type from which it derives, and intends to extend.</span></span> <span data-ttu-id="bad47-113">En la vista de árbol de esquema, una vez **Base Data Type** se ha establecido en **GlobalAddrType**, se mostraría una estructura duplicada de nodo debajo del nodo denominado **BillingAddress**, idéntica a la estructura del nodo adyacente bajo el nodo denominado **ShippingAddress**.</span><span class="sxs-lookup"><span data-stu-id="bad47-113">In the schema tree view, after **Base Data Type** has been set to **GlobalAddrType**, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span> <span data-ttu-id="bad47-114">La diferencia entre ellos es que la **BillingAddress** estructura de nodos será extensible más allá del tipo de datos base **GlobalAddrType**y el **ShippingAddress** estructura seguirá siendo idéntica al tipo de base de datos **GlobalAddrType**.</span><span class="sxs-lookup"><span data-stu-id="bad47-114">The difference between them is that the **BillingAddress** node structure will be extensible beyond the base data type **GlobalAddrType**, and the **ShippingAddress** structure will remain identical to the base data type **GlobalAddrType**.</span></span>  
  
- <span data-ttu-id="bad47-115">Antes, con un nodo recién insertado denominado **BillingAddress**.</span><span class="sxs-lookup"><span data-stu-id="bad47-115">Before, with a newly inserted node named **BillingAddress**.</span></span>  
  
  ```  
  <xs:schema>  
      <xs:element name="Root">  
          <xs:complexType>  
              <xs:sequence>  
                  <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                  <xs:element name="BillingAddress">  
                      <xs:sequence />  
                  </xs:element>  
              </xs:sequence>  
          </xs:complexType>  
      </xs:element>  
      <xs:complexType name="GlobalAddrType">  
      [Address structure defined globally here.]  
      </xs:complexType>  
  </xs:schema>  
  ```  
  
- <span data-ttu-id="bad47-116">Después de una derivación del tipo base complejo **GlobalAddrType**, por extensión.</span><span class="sxs-lookup"><span data-stu-id="bad47-116">After deriving from the complex base type **GlobalAddrType**, by extension.</span></span>  
  
  ```  
  <xs:schema>  
      <xs:element name="Root">  
          <xs:complexType>  
              <xs:sequence>  
                  <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                  <xs:element name="BillingAddress">  
                      <xs:complexType>  
                          <xs:complexContent mixed="false">  
                              <xs:extension base="GlobalAddrType" />  
                          </xs:complexContent>  
                      </xs:complexType>  
                  </xs:element>  
              </xs:sequence>  
          </xs:complexType>  
      </xs:element>  
      <xs:complexType name="GlobalAddrType">  
      [Address structure defined globally here.]   
      </xs:complexType>  
  </xs:schema>  
  ```  
  
  <span data-ttu-id="bad47-117">Especifique las extensiones para el tipo de base de datos mediante la inserción de nodos en el **BillingAddress** nodo del árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="bad47-117">You specify extensions to the base data type by inserting nodes into the **BillingAddress** node in the schema tree.</span></span> <span data-ttu-id="bad47-118">El siguiente fragmento XSD muestra cómo se expande el elemento de extensión vacío cuando un **grupo Sequence** nodo se inserta como un nuevo elemento secundario de la **BillingAddress** nodo y, a continuación, un **elemento de campo**  nodo, denominado **PaymentType**, se inserta como un nodo secundario de la **grupo Sequence** nodo.</span><span class="sxs-lookup"><span data-stu-id="bad47-118">The following XSD fragment shows how the empty extension element is expanded when a **Sequence Group** node is inserted as a new child of the **BillingAddress** node and then a **Field Element** node, named **PaymentType**, is inserted as a child node of the **Sequence Group** node.</span></span>  
  
```  
<xs:extension base="GlobalAddrType">  
    <xs:sequence>  
        <xs:element default="Accounts Payable"  
            name="Department" type="xs:string" />  
    </xs:sequence>  
</xs:extension>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bad47-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bad47-119">See Also</span></span>  
 [<span data-ttu-id="bad47-120">Derivación de tipos globales complejos</span><span class="sxs-lookup"><span data-stu-id="bad47-120">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)