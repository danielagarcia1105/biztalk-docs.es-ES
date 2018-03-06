---
title: "Asignaciones básicas y complejas operaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da864b48-6255-4847-9a6f-13e489e8658d
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82876310cfa497f8002e7df680281122e90884af
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="basic-and-complex-mapping-operations"></a>Operaciones de asignaciones básicas y complejas
El Asignador de BizTalk proporciona soluciones para una serie de escenarios de asignaciones que van desde simples operaciones de tipo árbol primario-secundario hasta operaciones complejas y detalladas en las que hay registros de bucles y jerarquías. La complejidad de un escenario de asignación depende de sus preferencias y necesidades empresariales: lenguaje de definición (XSD) de esquemas XML proporciona gran flexibilidad para definir formatos estructurados. Casi todos los escenarios de asignación se dividen en dos categorías: asignación básica y asignación compleja.  
  
## <a name="basic-mapping"></a>Asignación básica  
 La asignación básica es el tipo más común de asignación que se puede crear. En una asignación básica, los elementos de entrada y salida tienen una relación de uno a uno. Un elemento de entrada se asigna a un único elemento de salida. Aunque muchos tipos de transformaciones y traducciones son posibles con la asignación básica, como el uso de varios *functoids* y functoids en cascada para manipular el valor que se está copiando, el escenario subyacente resulta relativamente simple. Las operaciones de asignación básica también incluyen la asignación de campos de dos registros primarios diferentes (que solo ocurren una vez) a campos bajo un solo registro primario en el esquema de destino.  
  
## <a name="complex-mapping"></a>Asignación compleja  
 Asignación compleja implica registros o campos que aparecen varias veces para una única instancia de la **registro** o **elemento de campo** nodo en el árbol de esquema. Tales nodos tienen sus **Max Occurs** propiedad establecida en un valor mayor que uno (1), que indica la puede haber más de un elemento correspondiente en un mensaje de instancia. Cuando una asignación de BizTalk utiliza este tipo de asignación de variable de número (también conocido como *bucle*), el compilador de hoja de estilos Extensible Stylesheet Language (XSL) debe ser capaz de determinar la ruta de acceso adecuada del bucle que se recorre para generar la salida requerida.  
  
 En general, puede vincular un campo de un registro de bucle del esquema de origen con un campo de un registro de bucle del esquema de destino. El número de elementos correspondientes en un mensaje de instancia de entrada determina el número de elementos que se han creado en el mensaje de instancia de salida. Fíjese en los siguientes fragmentos XSD de esquemas de ejemplo de origen y destino.  
  
### <a name="source-schema-fragment"></a>Fragmento de esquema de origen  
  
```  
<xs:element minOccurs="1" maxOccurs="5"  
            name="SrcLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
  
```  
  
### <a name="destination-schema-fragment"></a>Fragmento de esquema de destino  
  
```  
<xs:element minOccurs="0" maxOccurs="unbounded"  
            name="DstLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  
```  
  
 En estos fragmentos:  
  
-   **SrcLoopingRecord**, **registro** nodo en los mensajes de instancia de entrada, puede aparecer entre uno y cinco veces. También contiene el elemento secundario **elemento de campo** nodos **Field1** (una cadena) y **Field2** (un entero) que ocurren una vez para cada instancia de su elemento primario.  
  
-   **DstLoopingRecord**, **registro** nodo en los mensajes de instancia de salida, puede aparecer cero (0) o más veces, sin enlazar. También contiene el elemento secundario **elemento de campo** nodos **FieldA** (una cadena) y **FieldB** (un entero) que ocurren una vez para cada instancia de su elemento primario.  
  
 Suponiendo que Field1 está enlazado con FieldA y Field2 está enlazado con FieldB, y que el siguiente fragmento de un mensaje de instancia de entrada ha procesado esas asignaciones, se creará el siguiente fragmento de un mensaje de instancia de salida.  
  
### <a name="input-instance-message-fragment"></a>Fragmento de mensaje de instancia de entrada  
  
```  
<SrcLoopingRecord>  
    <Field1>A string</Field1>  
    <Field2>10</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>Another string</Field1>  
    <Field2>11</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>A ball of string</Field1>  
    <Field2>12</Field2>  
</SrcLoopingRecord>  
```  
  
### <a name="output-instance-message-fragment"></a>Fragmento de mensaje de instancia de salida  
  
```  
<DstLoopingRecord>  
    <FieldA>A string</FieldA>  
    <FieldB>10</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
  <FieldA>Another string</FieldA>  
  <FieldB>11</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
    <FieldA>A ball of string</FieldA>  
    <FieldB>12</FieldB>  
</DstLoopingRecord>  
```  
  
 El número de repeticiones de la **SrcLoopingRecord** elemento en el mensaje de instancia de entrada (3) determina el número de repeticiones de la **DstLoopingRecord** elemento en el mensaje de instancia de salida.  
  
 Disponer de varias rutas de bucle es un tipo de asignación que no admite el Asignador de BizTalk. Este tipo de asignación trabaja con campos de dos o más registros de bucle en el esquema de origen que está asignando a los campos dentro de un registro de bucle simple en el esquema de destino. Esto presenta un problema, no hay ninguna manera eficaz de determinar el número de elementos que se va a producir en el mensaje de instancia de salida. Varias rutas de bucle dan como resultado una advertencia de compilación de asignación que indica que el nodo de destino tiene varias rutas de bucle de origen. Sin embargo, esto no es más que una advertencia, y el número de iteraciones en la primera ruta del bucle de origen se utiliza para determinar el número de elementos que se producen en el mensaje de instancia de salida. Puede tomar el control explícito de bucle comportamiento mediante el uso de la **bucle** functoid.  
  
 Microsoft BizTalk Server integra a un nuevo tipo de bucle denominado bucle controlado por la tabla. El bucle controlado por tablas es útil cuando el mensaje de instancia de salida necesita basarse en datos del mensaje de instancia de entrada en combinación con una o más constantes, vínculos del esquema de origen o functoids. En tales casos, el mensaje de instancia de salida puede tener varios registros basándose en los datos de un registro simple en el mensaje de instancia de entrada que se combina con distintas constantes o basándose en datos procedentes de varios registros en el mensaje de instancia de entrada. Para obtener más información acerca de controlado por tablas bucle con el **bucle de tabla** y **Extractor de tablas** functoids, consulte [bucle de tabla y Functoids de Extractor de tabla](../core/table-looping-and-table-extractor-functoids.md).  
  
## <a name="see-also"></a>Vea también  
 [Mapas](../core/maps.md)   
 [Crear asignaciones usando al asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)