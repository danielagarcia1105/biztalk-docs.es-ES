---
title: CorrelationID | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4faf210-7e7f-450d-8bb1-84d3d31c3022
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1192de4a49c300220ce0b297bbc1ee02ce64c6dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237772"
---
# <a name="correlationid"></a>CorrelationID
El elemento `CorrelationID` se usa para especificar un Id. de correlación para un mensaje.  
  
## <a name="format"></a>Formato  
 El elemento `CorrelationID` se compone de un elemento `Expression` que usa uno o más elementos `Operation` para especificar la cadena que se debe usar como Id. de correlación.  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="remarks"></a>Comentarios  
 En expresiones de Id. de correlación, no se permiten las operaciones comunes siguientes:  
  
-   And  
  
-   Es igual a  
  
## <a name="example"></a>Ejemplo  
 El bloque de configuración del ejemplo del interceptor de Workflow Foundation (WF) siguiente usa "OrderNum" para establecer un Id. de correlación. Mediante WF y las operaciones comunes, se pueden generar expresiones sofisticadas para construir un Id. de correlación adecuado para el flujo de trabajo.  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>OrderNum</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 En el caso de aplicaciones de Windows Communication Foundation (WCF), se pueden usar operaciones comunes y específicas de WCF para construir un Id. de correlación. El siguiente ejemplo se utiliza la **XPath** operación y XPath para recuperar un número de tarjeta de crédito de un mensaje para su uso como un identificador de correlación:  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wcf:Operation Name ="XPath">  
      <wcf:Argument>//s:Body/creditCard:CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>Vea también  
 [Elemento OnEvent del interceptor](../core/interceptor-onevent-element.md)