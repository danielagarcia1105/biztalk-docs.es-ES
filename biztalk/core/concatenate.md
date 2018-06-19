---
title: Concatenar | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e21a773d-a9cc-4a6f-b548-46badcd92aab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4766f65fb0cbe26c8f3c545c38235d83abb283a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231700"
---
# <a name="concatenate"></a>Concatenate
Quita los dos elementos principales de la pila, los concatena y después inserta el resultado en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<ic:Operation Name="Concatenate" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Dos elementos principales en la pila.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena resultado de la operación de concatenación.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente actualizar expresión, la cadena de constante "iniciar:" se concatena con el valor de la propiedad de contexto "EventTime" y se conservan en la columna de base de datos NewOrderCreateTime.  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de interceptor](../core/interceptor-operations.md)