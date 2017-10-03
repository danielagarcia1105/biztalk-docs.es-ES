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
# <a name="complex-type-derivation-using-the-restriction-mechanism"></a>Derivación de tipo complejo mediante el mecanismo de restricción
La derivación por restricción es similar a la derivación por extensión, en lo que respecta a la funcionalidad del Editor de BizTalk. Un tipo complejo derivado por restricción es similar al tipo de datos base aplicable, excepto por sus declaraciones, que son más limitadas que las declaraciones correspondientes del tipo de datos base. De hecho, los valores representados por el tipo nuevo son un subconjunto de los valores representados por el tipo de datos base (al igual que ocurre en la restricción de tipos simples). Una aplicación preparada para los valores del tipo de datos base debería poder procesar correctamente cualquiera de los valores del tipo restringido.  
  
 Para obtener información completa acerca de cómo derivar nuevos tipos complejos mediante el mecanismo de restricción, consulte el sitio Web de W3C. Para obtener varios vínculos a este y otros sitios Web, vea [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).  
  
 Para derivar un tipo global complejo mediante restriction, en otra ubicación en el árbol de esquema, empiece por insertar un nuevo **registro** nodo en la ubicación deseada. A continuación, establezca su **Base Data Type** propiedad en el nombre de un tipo global complejo. Por último, cambie el valor de la **Derived By** propiedad desde su valor predeterminado de **extensión** (al menos cuando un tipo de base de datos se establece) a **restricción**.  
  
 En el ejemplo siguiente, **BillingAddress** es el nombre de las filas recién insertadas **registro** nodo, y **GlobalAddrType** es el nombre del tipo complejo global desde la que se deriva y que tiene intención de restringir. En la vista de árbol de esquema, se mostraría una estructura duplicada de nodo debajo del nodo denominado **BillingAddress**, idéntica a la estructura del nodo adyacente bajo el nodo denominado **ShippingAddress**. La diferencia entre ellos es que la **BillingAddress** estructura de nodo se someterá a posibles restricciones al tipo de datos base **GlobalAddrType**y el **ShippingAddress** estructura seguirá siendo idéntica al tipo de datos base **GlobalAddrType**.  
  
 Puesto que ha elegido restringir el tipo de datos base, no puede insertar nodos nuevos, aunque puede cambiar las propiedades de los nodos existentes para restringir más sus valores o comportamiento posibles.  
  
-   Antes, con el **Derived By** propiedad sigue establecido **extensión**.  
  
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
  
-   Después de cambiar el **Derived By** propiedad de **extensión** a **restricción**.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Derivación de tipo Global complejo](../core/complex-global-type-derivation.md)