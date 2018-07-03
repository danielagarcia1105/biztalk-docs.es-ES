---
title: ContinuationToken | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4911fc-c6fb-4628-9177-bd723d4d8ebc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f0d36737ddd16e34ecfe4680c7660e16c99f676
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001869"
---
# <a name="continuationtoken"></a>ContinuationToken
Un token de continuación se usa para correlacionar información heterogénea dentro de la infraestructura de BAM. Considere un proceso empresarial que construye los siguientes tipos de mensajes:  
  
- Pedido de compra identificado por un número de pedido de compra  
  
- Pedido de venta identificado por un número de pedido de venta  
  
- Pedido de envío identificado por un número de pedido de envío  
  
  En este proceso, hay tres identificadores importantes: Id. de pedido, Id. de pedido de ventas y trasvase de registros de Id. de pedido de compra Cada uno de estos identificadores señalan un evento importante en el período de vida del pedido original, pero no pueden correlacionarse directamente. Para realizar un seguimiento de los eventos relacionados con un pedido de compra, la información común entre los mensajes debe identificarse para ayudar a la infraestructura de seguimiento de BAM a correlacionar de forma precisa los eventos.  
  
## <a name="format"></a>Formato  
 Un token de continuación consta de un elemento de expresión y de una o varias operaciones:  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="remarks"></a>Notas  
 En expresiones de ContinuationToken, no se permiten las operaciones comunes siguientes:  
  
- And  
  
- Es igual a  
  
  [El encabezado de la sección de operaciones de WF/WCF debe tener gráficos similares y otros gráficos según sea necesario]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, un token de continuación de un proceso de WF se recupera del flujo de trabajo mediante el uso de `GetWorkflowProperty`. Aquí el programador ha decidido proporcionar asistencia para la continuación en el flujo de trabajo mediante el uso de código personalizado, probablemente porque el proceso para la determinación del token de continuación implica más de dos o tres expresiones y puede depender de los datos externos.  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>ContinuationToken</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
 Puede elegir proporcionar funcionalidades similares en sus nuevas aplicaciones WF o WCF, o bien, si el token es fácil de establecer mediante el uso de operaciones de expresiones, puede evitar escribir el código adicional.  
  
 El siguiente ejemplo establece un token de continuación para un proceso WCF mediante el uso de un **XPath** operación para recuperar el número de tarjeta de crédito del mensaje actual y el **constante** y  **concatenar** operaciones para anteponer la cadena "CID_" al número recuperado:  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CID_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//Purchase/Payment/CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="see-also"></a>Vea también  
 [Elemento OnEvent del interceptor](../core/interceptor-onevent-element.md)