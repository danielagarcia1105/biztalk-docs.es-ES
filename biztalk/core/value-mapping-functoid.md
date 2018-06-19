---
title: El Functoid de asignación de valor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Value Mapping functoids
- functoids, empty tags
- Concatenate functoids
ms.assetid: 3dd626fb-3bf6-4ede-9fd2-ddae5a54d178
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 038d59827a62c9f4e83879ec7cf2e0b47fd738f4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973786"
---
# <a name="value-mapping-functoid"></a>Asignación de valores (functoid)
El **Value Mapping** functoid devuelve el valor de su segundo parámetro si el primer parámetro es true. Una utilización común del functoid es cambiar los atributos de un campo a los atributos de un registro. Para eliminar la estructura de una parte de un mensaje de entrada convirtiendo varios registros en un único registro, use el [Functoid de asignación de valores (sin formato)](../core/value-mapping-flattening-functoid.md).  
  
 La siguiente ilustración muestra un mapa con la **Value Mapping** functoid utilizado para cambiar los atributos de un campo en los atributos de un registro.  
  
 ![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")  
Asignación de functoid de asignación de valores  
  
 El código siguiente muestra un mensaje de instancia de entrada en los pares de nombres y valores se asignan a **nombre** y **valor** atributos.  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherIn">  
    <Record>  
        <Field Name="WindSpeed" Value="5"/>   
        <Field Name="Temperature" Value="20" />  
    </Record>  
    <Record>  
        <Field Name="WindSpeed" Value="15" />  
        <Field Name="Temperature" Value="18" />  
    </Record>  
</ns0:Root>  
```  
  
 La asignación anterior puede convertir este mensaje en otro en el que los valores se asignen a atributos con los correspondientes nombres en registros separados.  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 El **igual** functoids probar los valores de la **nombre** atributo. La primera **igual** pruebas de functoid para el valor de **nombre** es "WindSpeed." Cuando el **nombre** es "WindSpeed," la primera **igual** functoid devuelve **True**. Esto, a su vez, permite la **Value Mapping** functoid para establecer el valor de la **WindSpeed** atributo en el mensaje de instancia de salida.  
  
## <a name="suppressing-the-creation-of-empty-tags"></a>Suprimir la creación de etiquetas vacías  
 Para suprimir etiquetas vacías, utilice el functoid de asignación de valores para controlar si una etiqueta se crea o no. Si el valor se evalúa como, se creará el campo de destino; de lo contrario, el campo de destino no se creará. En un escenario de bucle, utilice un functoid lógico y conéctelo al registro o al campo de destino. Si la condición se evalúa como false, la etiqueta no se creará. Para obtener un ejemplo, vea [bucle condicional](../core/conditional-looping.md).  
  
## <a name="forcing-the-creation-of-empty-tags"></a>Forzar la creación de etiquetas vacías  
 Para forzar la creación de etiquetas vacías, puede agregar un valor en la propiedad de valor del campo de destino o vincular una **Concatenate** functoid para el campo de destino.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es posible forzar la generación de etiquetas vacías seleccionando el "\<vacía\>" valor de la propiedad Value del campo de destino. En este caso, el campo se creará con el valor  vacío.  
  
## <a name="see-also"></a>Vea también  
 [Valor de asignación de Functoid (sin formato)](../core/value-mapping-flattening-functoid.md)   
 [Cómo agregar Functoids de asignación a una asignación de valores](../core/how-to-add-value-mapping-functoids-to-a-map.md)   
 [Functoids avanzados](../core/advanced-functoids.md)