---
title: Valor de asignación de Functoid (sin formato) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Value Mapping (Flattening) functoids
ms.assetid: d30c3ffe-d3ed-46fd-a692-cd26d042033c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d17d5d64409cd434075dfd4c556209864784e4d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287876"
---
# <a name="value-mapping-flattening-functoid"></a>Asignación de valores (sin formato) (functoid)
El **asignación de valores (sin formato)** functoid permite aplanar una parte de un mensaje de instancia de entrada convirtiendo varios registros en un único registro. Ésta es una operación común para convertir catálogos de Microsoft Commerce Server.  
  
> [!NOTE]
>  El **asignación de valores (sin formato)** functoid no debe combinarse con la **bucle** functoid o **bucle de tabla** functoid. Si se combinan, se produce una asignación compilada que considera que no hay dependencia de los nodos de destino que están por debajo de bucle de origen el **bucle** o **bucle de tabla** functoid.  
  
 En el siguiente código se muestra una parte de un catálogo que enumera variantes de producto, con cada característica de la variante en un registro independiente.  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlat.ProductsIn">  
    <ProductVariant ListPrice="99.99" ID="45-01">  
        <Feature Name="Material" Value="Leather" />  
        <Feature Name="Color" Value="Black" />  
    </ProductVariant>  
    <ProductVariant ListPrice="69.99" ID="45-02">  
        <Feature Name="Material" Value="Vinyl" />  
        <Feature Name="Color" Value="Brown" />  
    </ProductVariant>  
</nso0:Root>  
```  
  
 Reducción de esta parte del catálogo convertiría la **característica** registros a atributos de la **ProductVariant** registro.  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlat.ProductsOut">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 En la ilustración siguiente se muestra una asignación que realiza esta conversión.  
  
 ![Asignar registros de origen mediante un functoid. ](../core/media/valuemappingflattenfunctoid.gif "valuemappingflattenfunctoid")  
Asignación del functoid de asignación de valores (sin formato)  
  
 El **asignación de valores (sin formato)** functoid devuelve el valor de su segundo parámetro si el primer parámetro es true. En esta asignación, la primera **igual** functoid comprueba si el **nombre** atributo es igual a "Material". Si el atributo es igual a "Material", la **igual** functoid devuelve **True**. A su vez, esto hace que la **asignación de valores (sin formato)** functoid para asignar el valor de la **valor** atributo al campo en el mensaje de salida.  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar la asignación de valores (sin formato) Functoids a una asignación](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md)   
 [Esquema sin formato a catálogo](../core/flat-schema-to-catalog.md)   
 [Functoids avanzados](../core/advanced-functoids.md)