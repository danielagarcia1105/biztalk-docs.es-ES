---
title: Y | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80bd8f1f-edae-476d-b488-78e6c5ee70bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 676940dfa5cbc23d0c8127923d292e382a4e3cad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230020"
---
# <a name="and"></a>And
Quita los dos elementos principales de la pila, realiza un booleano **AND** de los dos elementos y, a continuación, inserta el resultado en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<ic:Operation Name="And" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Dos elementos principales en la pila.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena resultado booleano **AND** operación.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="example"></a>Ejemplo  
 El **y** operación es útil cuando necesita evaluar varias instrucciones. La expresión de filtro de ejemplo siguiente comprueba si el nombre de actividad es "CheckPO" y se cierra el evento de actividad mediante el uso de la **y** operación.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 En este ejemplo **y** es la operación final en la expresión porque se basa en los resultados de las comparaciones (y saca de la pila para realizar la comparación). Puede ampliar esta idea para realizar **y** operaciones en más de dos elementos. Por ejemplo, para evaluar si se cumplen las condiciones A, B y C, se usaría una expresión como la siguiente:  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityType"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyType</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>   
```  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de interceptor](../core/interceptor-operations.md)