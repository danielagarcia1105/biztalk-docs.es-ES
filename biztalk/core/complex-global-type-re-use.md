---
title: Reutilizar tipos globales complejos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d0d8018-f2c6-44cc-9330-2385ac8887eb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 492d1c345b1ac540bc2410c554be29996fc52dd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="complex-global-type-re-use"></a><span data-ttu-id="f76d0-102">Reutilizar tipos globales complejos</span><span class="sxs-lookup"><span data-stu-id="f76d0-102">Complex Global Type Re-use</span></span>
<span data-ttu-id="f76d0-103">Para usar un complejo tipo global tal cual, en otra ubicación en el árbol de esquema, comience por insertar un nuevo **registro** nodo en la ubicación deseada.</span><span class="sxs-lookup"><span data-stu-id="f76d0-103">To use a complex global type as is, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="f76d0-104">A continuación, establezca su **Data Structure Type** propiedad en el nombre de un tipo global complejo.</span><span class="sxs-lookup"><span data-stu-id="f76d0-104">Then set its **Data Structure Type** property to the name of a complex global type.</span></span>  
  
 <span data-ttu-id="f76d0-105">En el ejemplo siguiente, **BillingAddress** es el nombre de las filas recién insertadas **registro** nodo, y **GlobalAddrType** es el nombre del tipo global complejo que adopta.</span><span class="sxs-lookup"><span data-stu-id="f76d0-105">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type that it adopts.</span></span> <span data-ttu-id="f76d0-106">En la vista de árbol de esquema, se mostraría una estructura duplicada de nodo debajo del nodo denominado **BillingAddress**, idéntica a la estructura del nodo adyacente bajo el nodo denominado **ShippingAddress**.</span><span class="sxs-lookup"><span data-stu-id="f76d0-106">In the schema tree view, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span>  
  
-   <span data-ttu-id="f76d0-107">Antes, con un nodo recién insertado denominado **BillingAddress**.</span><span class="sxs-lookup"><span data-stu-id="f76d0-107">Before, with a newly inserted node named **BillingAddress**.</span></span>  
  
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
  
-   <span data-ttu-id="f76d0-108">Después de usar el tipo base complejo **GlobalAddrType**, tal y como está.</span><span class="sxs-lookup"><span data-stu-id="f76d0-108">After using the complex base type **GlobalAddrType**, as is.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f76d0-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f76d0-109">See Also</span></span>  
 [<span data-ttu-id="f76d0-110">Formas de utilizar los tipos globales complejos</span><span class="sxs-lookup"><span data-stu-id="f76d0-110">Ways to Use Complex Global Types</span></span>](../core/ways-to-use-complex-global-types.md)