---
title: "El Functoid de número de registros | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Max Occurs property
- Record Count functoids
ms.assetid: e6aab13f-afbe-4401-abbe-020570e2ff16
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87653709bf5d52c21537064bad286078ad625cf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="record-count-functoid"></a>Functoid de número de registros
El **número de registros** functoid recuentos de registros en el mensaje de instancia de entrada.  
  
 El **número de registros** functoid tiene una entrada y una salida. La entrada es un vínculo de un registro de bucle en el esquema de origen. El resultado de la **número de registros** functoid es el número de registro de bucle en un mensaje de instancia de entrada real.  
  
 Los registros de bucle corresponden a los elementos que se repiten un número impredecible de veces en un mensaje de instancia de entrada. Por ejemplo, en un pedido de compra, la **elemento** elemento podría aparecer muchas veces. Y el **elemento** elemento puede incluir productos, descripciones, precios y cantidades. El siguiente código es un ejemplo simplificado de este pedido.  
  
```  
<ns0:PurchaseOrder xmlns:ns0="http://RecordFunctoid.PurchaseOrder">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <LineItems>  
        <Item>  
            <Product>Laptop Computer</Product>  
            <Description>Thin profile laptop</Description>  
            <Price>1999.95</Price>  
            <Quantity>1</Quantity>  
        </Item>  
        <Item>  
            <Product>Monitor Swipes</Product>  
            <Description>Disposable monitor swipes</Description>  
            <Price>3.95</Price>  
            <Quantity>10</Quantity>  
        </Item>  
    </LineItems>  
</ns0:PurchaseOrder>  
```  
  
 El **Max Occurs** propiedad para la **elemento** registro se establece como ilimitado. Esto indica que la **elemento** bucles de registro y el asignador de BizTalk compila este registro como un bucle.  
  
 Imagine que desea buscar el número total de **elementos** elementos de la instancia de entrada de pedido de compra de mensajes y colocar el resultado en un campo en el mensaje de instancia de salida.  
  
 La siguiente ilustración muestra un **número de registros** functoid que cuenta el número de elementos de un pedido entrante y escribe ese valor en el **ItemCount** campo el **SummedPO**mensaje de instancia de salida.  
  
 ![Mapa que muestra el uso del functoid de número de registros. ] (../core/media/recordcountfunctoid.gif "recordcountfunctoid")  
Asignación de functoid de número de registros  
  
 Tenga en cuenta que la **Max Occurs** propiedad para la **elemento** registro sería **unbounded**. Esto indica que la **elemento** bucles de registro y el asignador de BizTalk compila este registro como un bucle.  
  
 Para el anterior ejemplo instancia mensaje de pedido, que contiene dos **elemento** elementos, el valor de la **ItemCount** campo se establecerá en 2.  
  
```  
<ns0:SummedPO xmlns:ns0="http://RecordCountFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
    <ItemCount>2</ItemCount>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  También puede usar el **número de registros** functoid para contar los elementos de campo de repetición. No está restringido para los registros.  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar Functoids de número de registros a un mapa](../core/how-to-add-record-count-functoids-to-a-map.md)   
 [Functoids avanzados](../core/advanced-functoids.md)   
 [Functoid de índice](../core/index-functoid.md)   
 [Functoid de iteración](../core/iteration-functoid.md)   
 [Functoid de bucle](../core/looping-functoid.md)