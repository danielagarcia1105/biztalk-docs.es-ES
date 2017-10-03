---
title: "Derivación de tipo complejo mediante el mecanismo de restricción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3003d88-6b75-4dcb-834f-1babcf7449cb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddbd9d8266d9c289b9b4bae9dd7060906e01ebd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="complex-type-derivation-using-the-restriction-mechanism"></a><span data-ttu-id="e508a-102">Derivación de tipo complejo mediante el mecanismo de restricción</span><span class="sxs-lookup"><span data-stu-id="e508a-102">Complex Type Derivation Using the Restriction Mechanism</span></span>
<span data-ttu-id="e508a-103">La derivación por restricción es similar a la derivación por extensión, en lo que respecta a la funcionalidad del Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e508a-103">Derivation by restriction is similar to derivation by extension, in terms of BizTalk Editor functionality.</span></span> <span data-ttu-id="e508a-104">Un tipo complejo derivado por restricción es similar al tipo de datos base aplicable, excepto por sus declaraciones, que son más limitadas que las declaraciones correspondientes del tipo de datos base.</span><span class="sxs-lookup"><span data-stu-id="e508a-104">A complex type derived by restriction is similar to its base data type, except that its declarations are more limited than the corresponding declarations in the base data type.</span></span> <span data-ttu-id="e508a-105">De hecho, los valores representados por el tipo nuevo son un subconjunto de los valores representados por el tipo de datos base (al igual que ocurre en la restricción de tipos simples).</span><span class="sxs-lookup"><span data-stu-id="e508a-105">In fact, the values represented by the new type are a subset of the values represented by the base data type (as is the case with restriction of simple types).</span></span> <span data-ttu-id="e508a-106">Una aplicación preparada para los valores del tipo de datos base debería poder procesar correctamente cualquiera de los valores del tipo restringido.</span><span class="sxs-lookup"><span data-stu-id="e508a-106">An application prepared for the values of the base data type ought to be able to successfully process any of the values of the restricted type.</span></span>  
  
 <span data-ttu-id="e508a-107">Para obtener información completa acerca de cómo derivar nuevos tipos complejos mediante el mecanismo de restricción, consulte el sitio Web de W3C.</span><span class="sxs-lookup"><span data-stu-id="e508a-107">For comprehensive information about deriving new complex types by using the restriction mechanism, refer to the W3C website.</span></span> <span data-ttu-id="e508a-108">Para obtener varios vínculos a este y otros sitios Web, vea [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).</span><span class="sxs-lookup"><span data-stu-id="e508a-108">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="e508a-109">Para derivar un tipo global complejo mediante restriction, en otra ubicación en el árbol de esquema, empiece por insertar un nuevo **registro** nodo en la ubicación deseada.</span><span class="sxs-lookup"><span data-stu-id="e508a-109">To derive from a complex global type by restriction, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="e508a-110">A continuación, establezca su **Base Data Type** propiedad en el nombre de un tipo global complejo.</span><span class="sxs-lookup"><span data-stu-id="e508a-110">Then set its **Base Data Type** property to the name of a complex global type.</span></span> <span data-ttu-id="e508a-111">Por último, cambie el valor de la **Derived By** propiedad desde su valor predeterminado de **extensión** (al menos cuando un tipo de base de datos se establece) a **restricción**.</span><span class="sxs-lookup"><span data-stu-id="e508a-111">Finally, change the setting of the **Derived By** property from its default value of **Extension** (at least when a base data type is set) to **Restriction**.</span></span>  
  
 <span data-ttu-id="e508a-112">En el ejemplo siguiente, **BillingAddress** es el nombre de las filas recién insertadas **registro** nodo, y **GlobalAddrType** es el nombre del tipo complejo global desde la que se deriva y que tiene intención de restringir.</span><span class="sxs-lookup"><span data-stu-id="e508a-112">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type from which it derives, and intends to restrict.</span></span> <span data-ttu-id="e508a-113">En la vista de árbol de esquema, se mostraría una estructura duplicada de nodo debajo del nodo denominado **BillingAddress**, idéntica a la estructura del nodo adyacente bajo el nodo denominado **ShippingAddress**.</span><span class="sxs-lookup"><span data-stu-id="e508a-113">In the schema tree view, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span> <span data-ttu-id="e508a-114">La diferencia entre ellos es que la **BillingAddress** estructura de nodo se someterá a posibles restricciones al tipo de datos base **GlobalAddrType**y el **ShippingAddress** estructura seguirá siendo idéntica al tipo de datos base **GlobalAddrType**.</span><span class="sxs-lookup"><span data-stu-id="e508a-114">The difference between them is that the **BillingAddress** node structure will be subject to possible restrictions to the base data type **GlobalAddrType**, and the **ShippingAddress** structure will remain identical to the base data type **GlobalAddrType**.</span></span>  
  
 <span data-ttu-id="e508a-115">Puesto que ha elegido restringir el tipo de datos base, no puede insertar nodos nuevos, aunque puede cambiar las propiedades de los nodos existentes para restringir más sus valores o comportamiento posibles.</span><span class="sxs-lookup"><span data-stu-id="e508a-115">Because you have chosen to restrict the base data type, you are not allowed to insert any new nodes, but you can change the properties of the existing nodes to further restrict their possible values or behavior.</span></span>  
  
-   <span data-ttu-id="e508a-116">Antes, con el **Derived By** propiedad sigue establecido **extensión**.</span><span class="sxs-lookup"><span data-stu-id="e508a-116">Before, with the **Derived By** property still set to **Extension**.</span></span>  
  
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
  
-   <span data-ttu-id="e508a-117">Después de cambiar el **Derived By** propiedad de **extensión** a **restricción**.</span><span class="sxs-lookup"><span data-stu-id="e508a-117">After switching the **Derived By** property from **Extension** to **Restriction**.</span></span>  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress">  
                        <xs:complexType>  
                            <xs:complexContent mixed="false">  
                                <xs:restriction base="GlobalAddrType">  
                   [Duplicate of address structure now appears  
                   here, ready to be restricted with additional  
                   attributes, set using the properties of the  
                   relevant nodes in the schema tree.]  
                                </xs:restriction>  
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
  
## <a name="see-also"></a><span data-ttu-id="e508a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e508a-118">See Also</span></span>  
 [<span data-ttu-id="e508a-119">Derivación de tipo Global complejo</span><span class="sxs-lookup"><span data-stu-id="e508a-119">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)