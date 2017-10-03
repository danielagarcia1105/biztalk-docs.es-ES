---
title: "Derivación de tipo simple mediante el mecanismo de lista | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14f3c7b7-7585-4297-9177-2deaef8355f0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aafc6a540e9595f426858bc16fedfb1f8fe0bc8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation-using-the-list-mechanism"></a>Derivación de tipo simple mediante el mecanismo de lista
Al derivar un nuevo tipo simple a partir de un tipo simple existente con el mecanismo de lista, se especifica que el valor de este atributo o elemento puede ser una lista de valores separados por espacios del tipo especificado. Por ejemplo, puede especificar que un valor de atributo o de elemento sea una lista de enteros separados por espacios.  
  
 Para obtener información completa acerca de cómo derivar nuevos tipos simples mediante el mecanismo de lista, vea el sitio web de W3C. Para obtener varios vínculos a este y otros sitios Web, vea [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).  
  
 Para derivar un tipo simple como una lista de ese tipo, seleccione la correspondiente **elemento de campo** nodo o **atributo de campo** nodo en el árbol de esquema y, a continuación, en la ventana Propiedades, seleccione un tipo simple en la lista desplegable lista para la **Base Data Type** propiedad. Tan pronto como seleccione un valor para esta propiedad, el **Derived By** propiedad cambiará automáticamente su valor predeterminado a **restricción**, que actúa como el valor predeterminado de derivación de tipo. Debe cambiar la **Derived By** propiedad de **restricción** a **lista**, lo que hace que la **Base Data Type** propiedad se va a cambiar como el **tipo de elemento de** propiedad (a propósito, la propiedad cuyo nombre ha cambiado se mueve a una posición diferente en la lista de propiedades debido al orden alfabético de las propiedades).  
  
> [!NOTE]
>  Puede usar a la vez los mecanismos de restricción y de lista de modo; es decir, crear una derivación de tipo simple con nombre mediante el mecanismo de restricción y, a continuación, usar dicho tipo como el tipo de elemento de otra derivación de tipo simple mediante el mecanismo de lista. Esto puede producir, por ejemplo, un valor que esté restringido a ser una lista de cadenas separadas por espacios que pertenezcan a un conjunto enumerado concreto de cadenas.  
  
> [!CAUTION]
>  El uso del mecanismo de lista para la derivación de tipo simple puede ser complicado cuando el tipo de elemento elegido permite espacios, como las cadenas, ya que este mecanismo utiliza espacios para separar los valores del tipo permitido en la lista.  
  
 Cuando cambia un **elemento de campo** nodo o **atributo de campo** nodo tener un datos escriba a tener un tipo de base de datos (con lo que se inicie el proceso de derivación de tipo simple) y, a continuación, establezca el **Derived By** propiedad **lista**, puede observar el siguiente cambio en el fragmento correspondiente de la vista XSD:  
  
-   Antes, con un recién insertado **elemento de campo** nodo denominado **ZipCodeList**.  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   Después de establecer el **Base Data Type** propiedad a xs: Integer y establecer el **Derived By** propiedad **lista** (después del cual el **Base Data Type**se cambia el nombre de propiedad para que sea el **tipo de elemento de** propiedad).  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList">  
                    <xs:simpleType>  
               <xs:list itemType="xs:integer" />   
                       </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
> [!NOTE]
>  En un esquema de la vida real, sería mejor definir primero y el nombre de una derivación de tipo simple del entero que restringe el número entero a cinco dígitos, y, a continuación, para derivar el **ZipCodeList** elemento de ese tipo, de forma eficaz limitando la lista para enteros que tienen cinco dígitos.  
  
## <a name="see-also"></a>Vea también  
 [Derivación de tipo simple](../core/simple-type-derivation.md)