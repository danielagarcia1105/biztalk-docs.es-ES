---
title: Es igual a | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac93031a-9d18-443d-9e38-71ef9edd5a30
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b82ac5c779dc6b4d3624b48cebe9df1bc3d1966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="equals"></a>Es igual a
Quita los dos elementos principales de la pila, los compara y después inserta el resultado en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<ic:Operation Name="Equals" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Dos elementos principales en la pila.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena resultado de la operación de comparación.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="example"></a>Ejemplo  
 La siguiente expresión de filtro en el ejemplo se utiliza la **es igual a** operación al comparar el nombre de la actividad actual a la constante "CheckPO". Si ambas son iguales, la expresión se evalúa como `true`.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 Se puede caer en la tentación de crear la expresión tal y como se escribiría una instrucción en C# al realizar las comparaciones. Por ejemplo, si se quisieran comparar tres valores, la sintaxis en C# sería similar a la siguiente:  
  
```  
bool res = a == b == c;  
```  
  
 Sin embargo, como modelo para el filtro de expresión, no sería suficiente. En su lugar, veamos la instrucción modificada (pero equivalente):  
  
```  
Bool res = (a == b) && (a == c);  
```  
  
 Se aproxima mucho más a la expresión de filtro que usaría para realizar la comparación. Para obtener más información y un ejemplo, vea [y](../core/and.md).  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de interceptor](../core/interceptor-operations.md)