---
title: Functoids acumulativos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0549867-e0e4-4cdb-aae0-cadc99088e03
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6ed3d5037d64cf21e1ee2676a5739f13e18da3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="cumulative-functoids"></a>Functoids acumulados

## <a name="overview"></a>Información general
**Acumulado** functoids reducen una serie de valores en un valor único como una suma, una cadena concatenada o un promedio.  
  
 Todos los **acumulativa** functoids aceptan dos parámetros de entrada:  
  
1.  El valor que se va a acumular. Este valor es numérico para todos los **acumulativa** functoids excepto la **concatenación acumulativa** functoid que espera un valor de cadena. El valor suele ser un vínculo desde un **atributo de campo**, **elemento de campo**, o **registro** nodo (con sus **Mixed** propiedad establecida en **True**).  
  
    > [!NOTE]
    >  Si ninguno de los antecesores **registro** bucle nodos en el árbol de esquema, con un **acumulativa** functoid no es necesario.  
  
2.  El ámbito en el que se acumula este valor. Este argumento es opcional. El argumento indica el grado de relación que deben tener los valores para que se puedan acumular.  
  
 En la siguiente tabla se muestran los valores del parámetro de ámbito y su efecto.  
  
|Valor del parámetro de ámbito|Efecto|  
|-----------------------------|------------|  
|0 (cero)|Acumula los valores de todo el mensaje de instancia. El valor predeterminado.|  
|1 (uno)|Acumula los valores de los elemento o atributos con el mismo elemento primario.|  
|2|Acumula los valores de los elemento o atributos con el mismo elemento primario de segundo nivel.|  
|3 o superior|Acumula los valores de los elementos o atributos, de ámbito progresivamente más amplio, que siguen el patrón anterior (elemento primario de segundo nivel, tercero, cuarto, etc.).|  

## <a name="example"></a>Ejemplo  
 Un ejemplo del uso de un **acumulativa** functoid sería la suma de los costos a través de un pedido de compra. El código que se muestra a continuación es un ejemplo de un pedido.  
  
```  
<ns0:PurchaseOrder xmlns:ns0="http://CumulativeFunctoid.PurchaseOrder">  
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
  
 El **Max Occurs** propiedad para la **elemento** registro, por supuesto, sería **unbounded**. Esto indica que el registro de elemento se repite y el Asignador de BizTalk compila este registro como un bucle.  
  
 La siguiente ilustración muestra una asignación que utiliza un **multiplicación** functoid y un **suma acumulativa** functoid para agregar registros de elementos de una entrada de pedido de compra y mostrar los resultados en la  **POTotal** campo:  
  
 ![Mapa que muestra el uso del functoid de suma acumulativa. ] (../core/media/cumulativefunctoids.gif "cumulativefunctoids")  

  
 La asignación produce la siguiente salida con los datos anteriores y con el valor predeterminado del parámetro de ámbito, 0 (cero):  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
 En este ejemplo, todos los **elemento** registra en el **LineItems** registro participar en la acumulación: el valor predeterminado para el parámetro de ámbito indica la suma de los valores en todo el mensaje. El **precio** y **cantidad** campos se envían a un **multiplicación** functoid. El resultado de la **multiplicación** functoid se convierte en la entrada a la **suma acumulativa** functoid. El resultado de la **suma acumulativa** functoid es el valor acumulado como el **elemento** se recorren los registros del pedido de compra de entrada.  
  
> [!NOTE]
>  La suma acumulativa de entradas tiene lugar en el registro primario en el que se origina el vínculo de entrada. Incluso cuando la **acumulativa** functoid obtiene su entrada de otro functoid, la suma acumulativa tiene lugar en el registro primario de los vínculos de entrada para el functoid que actúa como entrada para el **acumulativa**functoid.  
  
 Si cambia el parámetro de ámbito a 1 (uno) y modifica ligeramente el esquema de salida, se produce el siguiente resultado:  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <ItemTotal>1999.95</ItemTotal>  
    <ItemTotal>39.5</ItemTotal>  
</ns0:SummedPO>  
```  
  
 Si establece el parámetro de ámbito a 1 (uno) se acumulan los valores de elementos o atributos con el mismo elemento primario. Aquí el **precio** y **cantidad** campos tienen **elemento** como elemento primario para que el functoid suma los valores de cada cliente individual **elemento**.  
  
 Si establece el parámetro de ámbito a 2 (dos) el functoid acumula los valores de elementos o atributos con el mismo elemento primario de segundo nivel. El primario de segundo nivel de la **precio** y **cantidad** campos es la **LineItems** registro. Dado que solo hay un **LineItems** registros en el mensaje de instancia, el resultado es el mismo que usar el valor predeterminado:  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  Functoids acumulativos (salvo el **cadena acumulativa** functoid) ignorar la entrada no numéricos. Por ejemplo, se omite un valor de entrada de "tres”.  
  
 El **promedio acumulativo**, **mínimo acumulativo**, y **máximo acumulativo** functoids se comportan de forma similar a la **suma acumulativa** functoid. El **cadena acumulativa** concatena cadenas en lugar de agregar valores numéricos.  

## <a name="available-functoids"></a>Functoids disponibles
  
 El **acumulativa** functoids son: 

* Promedio acumulativo
* Concatenación acumulativa
* Máximo acumulativo
* Mínimo acumulativo
* Suma acumulativa

Más detalles sobre estos functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
-  [Cómo agregar Functoids básicos a un mapa](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **Referencia a Functoids acumulativos**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]