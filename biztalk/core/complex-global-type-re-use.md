---
title: Reutilizar tipos globales complejos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d0d8018-f2c6-44cc-9330-2385ac8887eb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 492d1c345b1ac540bc2410c554be29996fc52dd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231772"
---
# <a name="complex-global-type-re-use"></a>Reutilizar tipos globales complejos
Para usar un complejo tipo global tal cual, en otra ubicación en el árbol de esquema, comience por insertar un nuevo **registro** nodo en la ubicación deseada. A continuación, establezca su **Data Structure Type** propiedad en el nombre de un tipo global complejo.  
  
 En el ejemplo siguiente, **BillingAddress** es el nombre de las filas recién insertadas **registro** nodo, y **GlobalAddrType** es el nombre del tipo global complejo que adopta. En la vista de árbol de esquema, se mostraría una estructura duplicada de nodo debajo del nodo denominado **BillingAddress**, idéntica a la estructura del nodo adyacente bajo el nodo denominado **ShippingAddress**.  
  
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
  
-   Después de usar el tipo base complejo **GlobalAddrType**, tal y como está.  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress" type="GlobalAddrType" />  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
        <xs:complexType name="GlobalAddrType">  
        [Address structure defined globally here.]  
        </xs:complexType>  
    </xs:schema>  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Formas de utilizar los tipos globales complejos](../core/ways-to-use-complex-global-types.md)