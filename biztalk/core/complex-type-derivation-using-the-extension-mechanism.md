---
title: Derivación de tipo complejo mediante el mecanismo de extensión | Documentos de Microsoft
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
ms.openlocfilehash: c5d36778b5ad99a0273e6199f59bdd337429a74b
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22232476"
---
# <a name="complex-type-derivation-using-the-extension-mechanism"></a>Derivación de tipo complejo mediante el mecanismo de extensión
Un tipo complejo derivado por extensión es un supraconjunto funcional del tipo de datos base correspondiente. Como el propio nombre indica, el tipo de datos base correspondiente constituye la base para el tipo que se está definiendo, donde las diferencias con respecto al tipo base son de naturaleza aditiva. Este tema proporciona un ejemplo en el que los dos elementos **ShippingAddress** y **BillingAddress** se basan en el tipo global complejo **GlobalAddrType**. **ShippingAddress** simplemente se define como de tipo **GlobalAddrType**, mientras que **BillingAddress** está definido para ampliar el tipo **GlobalAddrType**. Al final del ejemplo, se agrega un elemento adicional a **BillingAddress**, que se denomina **departamento**, con un tipo de cadena y un valor predeterminado de cuentas por pagar.  
  
 Para obtener información completa acerca de cómo derivar nuevos tipos complejos mediante el mecanismo de extensión, consulte el sitio Web de W3C. Para obtener varios vínculos a este y otros sitios Web, vea [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).  
  
 Para derivar un tipo global complejo por extensión, en otra ubicación en el árbol de esquema, empiece por insertar un nuevo **registro** nodo en la ubicación deseada. A continuación, establezca su **Base Data Type** propiedad en el nombre de un tipo global complejo.  
  
 En el ejemplo siguiente, **BillingAddress** es el nombre de las filas recién insertadas **registro** nodo, y **GlobalAddrType** es el nombre del tipo complejo global desde la que se deriva y que tiene intención de extender. En la vista de árbol de esquema, una vez **Base Data Type** se ha establecido en **GlobalAddrType**, se mostraría una estructura duplicada de nodo debajo del nodo denominado **BillingAddress**, idéntica a la estructura del nodo adyacente bajo el nodo denominado **ShippingAddress**. La diferencia entre ellos es que la **BillingAddress** estructura de nodo se podrá extender más allá del tipo de datos base **GlobalAddrType**y el **ShippingAddress** estructura seguirá siendo idéntica al tipo de datos base **GlobalAddrType**.  
  
-   Antes, con un nodo recién insertado denominado **BillingAddress**.  
  
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
  
-   Después de una derivación del tipo base complejo **GlobalAddrType**, por extensión.  
  
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
  
 Especifique las extensiones para el tipo de base de datos mediante la inserción de nodos en el **BillingAddress** nodo en el árbol de esquema. El siguiente fragmento XSD muestra cómo se expande el elemento de extensión vacío cuando un **grupo de secuencias** nodo se insertará como un nuevo elemento secundario de la **BillingAddress** nodo y, a continuación, un **elemento de campo**  nodo, denominado **PaymentType**, se insertará como un nodo secundario de la **grupo de secuencias** nodo.  
  
```  
<xs:extension base="GlobalAddrType">  
    <xs:sequence>  
        <xs:element default="Accounts Payable"  
            name="Department" type="xs:string" />  
    </xs:sequence>  
</xs:extension>  
```  
  
## <a name="see-also"></a>Vea también  
 [Derivación de tipos globales complejos](../core/complex-global-type-derivation.md)