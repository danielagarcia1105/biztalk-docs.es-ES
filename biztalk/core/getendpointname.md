---
title: GetEndpointName | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5a06850-ff6d-4fe4-9834-61d14b117391
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1567f0b4bceb756381c4033f3243ac7a58fda366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getendpointname"></a>GetEndpointName (operación)
Inserta el nombre del extremo de interceptación actual en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wcf:Operation Name="GetEndpointName" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el nombre del extremo de interceptación actual.  
  
## <a name="remarks"></a>Comentarios  
 Resulta importante tener en cuenta que las aplicaciones cliente y servidor devolverán nombres distintos para el mismo nombre de extremo especificado en los archivos App.config.  
  
 En el caso de las aplicaciones cliente, el nombre del extremo recuperado por la operación GetEndPointName será el nombre del enlace seguido por un guión bajo y el nombre del contrato.  
  
 Por ejemplo, si no se establece la propiedad de nombre en ServiceEndpoint, pero se establece el enlace, el nombre se establecerá \< *enlace*> _\<*contrato*>.  
  
 Si no se establecen el nombre y el enlace, se establecerá la propiedad Name \< *contrato*>.  
  
 En el caso del servicio, el nombre recuperado será el nombre del extremo especificado en el archivo App.config.  
  
## <a name="example"></a>Ejemplo  
 La expresión de filtro de ejemplo siguiente define una interceptación para la operación Receive correspondiente al punto de llamada de contrato ServiceRequest para el extremo PurchaseOrder_EP. Se lleva a cabo mediante los pasos lógicos siguientes:  
  
1.  Compare el nombre de la operación actual con "Receive" e inserte el resultado (True o False) en la pila.  
  
2.  Compare el punto de llamada de contrato de servicio con "ServiceRequest" e inserte el resultado (True o False) en la pila. Ahora hay dos valores booleanos en la pila.  
  
3.  Comparar los resultados de los pasos anteriores con un valor booleano **y** operación e inserte el resultado en la pila. Esto deja un valor booleano en la pila.  
  
4.  Compare el extremo actual con "PurchaseOrder_EP" e inserte el resultado (True o False) en la pila. Ahora hay dos valores booleanos en la pila.  
  
5.  Por último, compare los dos valores booleanos de la pila mediante un valor booleano **y** operación e inserte el resultado en la pila. De este modo, se comprueba el resultado de la comparación del extremo con un valor booleano, cuyo valor es True si el nombre de la operación y el punto de llamada de contrato coinciden correctamente y que, en caso contrario, será False.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Receive</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wcf:Operation Name="GetServiceContractCallPoint" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ServiceRequest</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wcf:Operation Name="GetEndpointName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>PurchaseOrder_EP</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de Windows Communication Foundation](../core/operations-in-windows-communication-foundation.md)