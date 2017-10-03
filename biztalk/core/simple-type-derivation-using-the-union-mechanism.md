---
title: "Derivación de tipo simple mediante el mecanismo de unión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e51ae390-78f5-4fb9-9163-2a8023aea1ec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1414fa506f824415de8e8449e8b2b27befd2fc76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation-using-the-union-mechanism"></a>Derivación de tipo simple mediante el mecanismo de unión
Al derivar un nuevo tipo simple a partir de un tipo simple existente con el mecanismo de unión, se especifica que el valor de este atributo o elemento puede ser de más de un tipo, según una lista de tipos que proporcione. Por ejemplo, puede especificar que un valor de atributo o elemento es una fecha, una hora o un valor de fecha y hora.  
  
 Para obtener información completa acerca de cómo derivar nuevos tipos simples mediante el mecanismo de unión, consulte el sitio Web de W3C. Para obtener varios vínculos a este y otros sitios Web, vea [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).  
  
 Para derivar un tipo simple como una unión de varios tipos posibles, seleccione la correspondiente **elemento de campo** nodo o **atributo de campo** nodo en el árbol de esquema y, a continuación, en la ventana Propiedades, seleccione un tipo simple de la lista desplegable para la **Base Data Type** propiedad. Tan pronto como haya seleccionado un valor para esta propiedad, el **Derived By** propiedad cambiará automáticamente su valor predeterminado a **restricción**, que actúa como el valor predeterminado de derivación de tipo. Debe cambiar la **Derived By** propiedad de **restricción** a **unión**, lo que hace que la **Base Data Type** propiedad se va a cambiar como el **tipos de miembro** propiedad (a propósito, la propiedad cuyo nombre ha cambiado se mueve a una posición diferente en la lista de propiedades debido al orden alfabético de las propiedades).  
  
 Por último, puede usar las casillas de verificación en la **tipos de miembro** lista de comprobación de lista desplegable para seleccionar tipos adicionales para permitir que los valores correspondientes en mensajes de instancia.  
  
 Cuando cambia un **elemento de campo** nodo o **atributo de campo** nodo tener un datos escriba a tener un tipo de base de datos (con lo que se inicie el proceso de derivación de tipo simple) y, a continuación, establezca el **Derived By** propiedad **unión**, puede observar el siguiente cambio en el fragmento correspondiente de la vista XSD.  
  
-   Antes, con un recién insertado **elemento de campo** nodo denominado **DatesAndOrTimes**.  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   Después de establecer el **Base Data Type** propiedad a **xs: Date**y estableciendo el **Derived By** propiedad a **unión** (después del cual el  **Base Data Type** se cambia el nombre de propiedad para que sea el **tipos de miembro** propiedad) y, a continuación, seleccionar también **xs: DateTime** y **xs: Time** como adicional permite tipos en el **tipos de miembro** lista de comprobación de lista desplegable.  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Derivación de tipo simple](../core/simple-type-derivation.md)