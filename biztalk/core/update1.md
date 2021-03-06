---
title: Update 1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Update function [Business Rules Engine]
- Update function [Business Rules Engine], TypedXMLDocument
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], .NET objects
- .NET objects
- Update function [Business Rules Engine], DataConnection
ms.assetid: 939e45dc-6433-42f3-a336-8f3c247417ac
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb9c8e8b75bc67954c30bf2b4a6e6ff39b3ee01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008829"
---
# <a name="update"></a>Update
Cuando **actualización** se invoca la función de un objeto, el objeto se vuelve a imponer en el motor para volverse a evaluar, basándose en los nuevos datos y el estado. El objeto puede ser de tipo **TypedXmlDocument** o clase .NET o **DataConnection** o **TypedDataTable**.  
  
 También puede usar **actualización** función para mejorar el rendimiento del motor y evitar escenarios de bucle sin fin, como se describe en este tema.  
  
 Normalmente, se utiliza **Assert** para colocar un nuevo objeto en la memoria de trabajo del motor de reglas y usar **actualizar** para actualizar un objeto ya existente en la memoria de trabajo. Cuando se impone un objeto nuevo, se evalúan las condiciones de todas las reglas. Cuando se actualiza un objeto existente, solo se vuelven a evaluar las condiciones que usan el hecho actualizado, y las acciones se agregan a la agenda si estas condiciones se evalúan como true.  
  
## <a name="using-update-function-on-net-facts"></a>Uso de la función Actualizar en hechos .NET  
 Supongamos las dos reglas siguientes como ejemplo. Supongamos que los objetos **ItemA** y **ItemB** ya existen en la memoria de trabajo. La regla 1 evalúa el **Id** propiedad en **ItemA**, Establece el **Id** propiedad en **ItemB**y, a continuación, vuelve a imponer **ItemB** después del cambio. Cuando **ItemB** se vuelve a imponer, se trata como un nuevo objeto y el motor vuelve a evaluar todas las reglas que usan el objeto **ItemB** en los predicados o acciones. Esto garantiza que la regla 2 se vuelve a evaluar con el nuevo valor de **ItemB.Id**, como se establece en la regla 1. Regla 2 puede haber un error la primera vez se evaluó, pero se evalúa como **true** la segunda vez que se evalúa.  
  
### <a name="rule-1"></a>Regla 1  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Assert(ItemB)  
```  
  
### <a name="rule-2"></a>Regla 2  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 Esta capacidad de volver a imponer objetos en la memoria de trabajo permite al usuario tener un control explícito sobre el comportamiento en los escenarios de encadenamiento directo. Sin embargo, un efecto secundario de esta reimposición en este ejemplo es que la Regla 1 también se vuelve a evaluar. Dado que **ItemA.Id** no se ha cambiado, la regla 1 vuelve a evaluar en **true** y **itemb** acción activa de nuevo. En consecuencia, la regla crea una situación de bucle infinito.  
  
> [!NOTE]
>  El número de bucle máximo predeterminado de reevaluación de reglas es 2 ^ 32. Para ciertas reglas, la ejecución de directiva podría tardar mucho tiempo. Puede reducir el recuento ajustando el **profundidad máxima de bucle de ejecución** propiedad de la versión de directiva.  
  
 Deberá volver a imponer objetos sin crear bucles infinitos y el **actualización** función ofrece esta funcionalidad. Al igual que un reassert, el **actualización** función realiza **Retract** y **Assert** de las instancias de objeto asociado, que se han cambiado de acciones de regla, pero hay dos diferencias clave:  
  
- Las acciones de la agenda para las reglas en las que el tipo de instancia solo se utiliza en las acciones (no en los predicados) permanecerán en la agenda.  
  
- Las reglas que solo utilizan el tipo de instancia en las acciones no se volverán a evaluar.  
  
  Por lo tanto, las reglas que utilizan los tipos de instancia solo en los predicados, o tanto en los predicados como en la  acciones, se volverán a evaluar y sus acciones se agregarán a la agenda según corresponda.  
  
  Cambiar el ejemplo anterior se usan los **actualización** función garantiza que solo la regla 2 se vuelve a evaluar porque **ItemB** se utiliza en la condición de la regla 2. Regla 1 no se reevalúa porque **ItemB** solo se usa en las acciones de la regla 1, lo que elimina el escenario de bucle.  
  
### <a name="rule-1"></a>Regla 1  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Update(ItemB)  
```  
  
### <a name="rule-2"></a>Regla 2  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 No obstante, todavía es posible crear escenarios de bucle. Por ejemplo, considere la siguiente regla.  
  
### <a name="rule-1"></a>Regla 1  
  
```  
IF ItemA.Id == 1  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 Dado que **ItemA** se usa en el predicado, se vuelve a evaluar cuando **actualización** se llama en **ItemA**. Si el valor de **ItemA.Id** no se cambia en otra parte, la regla 1 sigue evaluando en **true**, haciendo que **actualización** que se llamará una vez más en A. El Diseñador de reglas debe asegurarse de que no se creen escenarios de bucle como éste.  
  
 El enfoque adecuado para esto será distinto en función de la naturaleza de las reglas. A continuación, se muestra un mecanismo sencillo para solucionar el problema del ejemplo anterior.  
  
 El **actualización** función puede utilizarse en el Compositor de reglas de negocio con una referencia a la clase, como ocurre con la **Assert**, **Retract**, o **RetractByType** funciones.  
  
### <a name="rule-1"></a>Regla 1  
  
```  
IF ItemA.Id == 1 and ItemA.Value != 20  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 Al agregar la comprobación en **ItemA.Value** impide que la regla 1 evalúe **true** nuevamente después de que se ejecutan las acciones de la regla 1 la primera vez.  
  
## <a name="using-update-function-on-xml-facts"></a>Uso de la función Actualizar en hechos XML  
 Supongamos las dos reglas siguientes como ejemplo. Suponga que. La Regla 1 evalúa el número total de elementos de un mensaje de pedido y la Regla 2 establece el estado en "Pendiente de aprobación" si el número total es mayor que o igual a 10.  
  
### <a name="rule-1"></a>Regla 1  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count)  
```  
  
### <a name="rule-2"></a>Regla 2  
  
```  
IF ProcessPO.Order:/Order/Items/TotalCount >= 10  
THEN ProcessPO.Order:/Order/Status = "Needs approval"  
```  
  
 Si se pasa el siguiente mensaje de pedido (PO) como entrada para esta directiva, observará que el estado no se establece en "Pendiente de aprobación" aunque el número de elementos totales es 14. Es dado que la regla rule2 se evalúa solo al principio cuando el valor de la **TotalCount** campo es 0, y la regla no se evalúa cada vez que se actualiza el recuento total disponible. Para que las condiciones vuelven a evaluar cada vez que el **TotalCount** está actualizado, debe llamar a la **actualización** función en el nodo primario (**elementos**) del nodo modificado ( **TotalCount**). Si cambia la Regla según se muestra abajo, y la prueba otra vez, debe ver el valor del campo Estado establecido en "Pendiente de aprobación".  
  
```  
<ns0:Order xmlns:ns0="http://ProcessPO.Order">  
    <Items>  
        <Item>  
            <Id>ITM1</Id>  
            <Count>2</Count>  
        </Item>  
        <Item>  
            <Id>ITM2</Id>  
            <Count>5</Count>  
        </Item>  
        <Item>  
            <Id>ITM3</Id>  
            <Count>7</Count>  
        </Item>  
        <TotalCount>0</TotalCount>  
    </Items>  
    <Status>No approval needed</Status>  
</ns0:Order>  
```  
  
 Modificado **regla 1** es como sigue:  
  
### <a name="rule-1"></a>Regla 1  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count) AND  
Update(ProcessPO.Order:/Order/Items)  
```  
  
## <a name="using-update-function-on-database-facts"></a>Uso de la función Actualizar en hechos de base de datos  
  
### <a name="typeddatatable"></a>TypedDataTable  
 Si **actualización** se llama en un **TypedDataTable**, **actualización** es llamado por el motor en todos los asociados **TypedDataRows**. **Actualización** también se pueden llamar en persona **TypedDataRows**.  
  
### <a name="dataconnection"></a>DataConnection  
 Actualización de un **DataConnection** no se admite. Use **Assert** en su lugar.  
  
## <a name="see-also"></a>Vea también  
 [Funciones de control del motor](../core/engine-control-functions.md)