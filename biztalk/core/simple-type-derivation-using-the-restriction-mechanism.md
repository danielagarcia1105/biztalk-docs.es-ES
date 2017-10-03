---
title: "Derivación de tipo simple mediante el mecanismo de restricción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ca712e-9563-4917-9bfc-1033a36773e8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dda4b8ad64f1edf262446f1633eda109ba7074ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation-using-the-restriction-mechanism"></a>Derivación de tipo simple mediante el mecanismo de restricción

## <a name="overview"></a>Información general
Al derivar un nuevo tipo simple a partir de un tipo simple existente con el mecanismo de restricción, normalmente se restringen los valores permitidos en un mensaje de instancia para ese atributo o valor de elemento a un subconjunto de los valores permitidos por el tipo simple base. Por ejemplo, puede restringir un tipo string para que sea una de las distintas cadenas enumeradas.  
  
 Para obtener información completa acerca de cómo derivar nuevos tipos simples mediante el mecanismo de restricción, consulte el sitio Web de W3C. Para obtener varios vínculos a este y otros sitios Web, vea [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).  
  
## <a name="field-element-and-field-attribute"></a>Elemento de campo y atributo de campo
 Para derivar un tipo simple mediante una restricción, seleccione la correspondiente **elemento de campo** nodo o **atributo de campo** nodo en el árbol de esquema y, a continuación, en la ventana Propiedades, seleccione un tipo simple en la lista desplegable lista para la **Base Data Type** propiedad. Tan pronto como haya seleccionado un valor para esta propiedad, el **Derived By** propiedad cambiará automáticamente su valor predeterminado a **restricción**, que actúa como el valor predeterminado de derivación de tipo. Además, una nueva categoría de propiedades denominada **restricción**, disponible en la ventana Propiedades.  
  
 Según el tipo de datos base seleccionado, podrá configurar distintas propiedades de esta nueva categoría. Por ejemplo, si el tipo de base de datos es numérico, las propiedades **MaxFacet Type** (cuando **MaxFacet Value** está establecido), **MaxFacet Value**, **MinFacet Type** (cuando **MinFacet Value** está establecido), y **MinFacet Value** están disponibles para definir un intervalo exclusivo o inclusivo de valores permitidos. Si el tipo de datos base es un tipo de cadena, la **longitud**, **longitud máxima**, y **longitud mínima** propiedades están disponibles para restringir la longitud de la cadena.  
  
 Para obtener más información acerca de las distintas propiedades de restricción de nodos de campo, vea la **propiedades de nodo de elemento de campo** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 Cuando cambia un **elemento de campo** nodo o **atributo de campo** nodo de tener un tipo de datos a tener un tipo de base de datos (con lo que se inicie el proceso de derivación de tipo simple), deje el  **Derived por** propiedad establecida en **restricción**y proporcionar una restricción de enumeración basada en los valores de cadena permitidos, puede observar los cambios siguientes en el fragmento correspondiente de la vista XSD:  
  
-   Antes, con un recién insertado **elemento de campo** nodo denominado **WestCoastStates**.  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   Después de establecer el **Base Data Type** propiedad en "xs: String" y deja el valor predeterminado de derivación de **restricción** para el **Derived By** propiedad.  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" >  
                    <xs:simpleType>  
                        <xs:restriction base="xs:string" />  
                    </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   Después de establecer el **enumeración** propiedad en la categoría de restricción a los nombres de los tres estados de la costa oeste de Estados Unidos.  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates">  
                    <xs:simpleType>  
                        <xs:restriction base="xs:string" />  
                            <xs:enumeration value="Washington" />  
                            <xs:enumeration value="Oregon" />  
                            <xs:enumeration value="California" />  
                        </xs:restriction>  
                    </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Derivación de tipo simple](../core/simple-type-derivation.md)