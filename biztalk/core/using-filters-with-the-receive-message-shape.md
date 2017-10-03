---
title: "Uso de filtros con la forma de mensaje de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filters, receive messages
- messages, filters
ms.assetid: 5310039b-6719-4971-933a-2da0573fb5e7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1434e9704e073cfef1503ef550409e6d6414bb7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-filters-with-the-receive-message-shape"></a>Uso de filtros con la forma de mensaje de recepción
Una expresión de filtro es un parámetro opcional que puede aplicarse a una forma Recepción de una orquestación que especifica un valor True para la propiedad Activar. Si se especifica una expresión de filtro, la orquestación solo se activará si un mensaje entrante cumple la condición o condiciones especificadas en dicha expresión. Si no se especifica ninguna expresión de filtro, ningún mensaje entrante al que se suscriba la orquestación la activará.  
  
 Para crear una expresión de filtro, hay que comparar una propiedad de un mensaje entrante a la izquierda de la expresión con una constante a la derecha de ésta. También se pueden crear expresiones compuestas aplicando los operadores AND y OR a dos expresiones o más. Asimismo, se puede dejar en blanco la expresión de filtro, en cuyo caso se aceptarán todos los mensajes.  
  
 Una expresión de filtro podría tener el siguiente aspecto:  
  
```  
InvoiceSchema.Quantity >= 1000  
```  
  
 En este ejemplo, se presenta un mensaje entrante a la orquestación. La orquestación tiene una activación **recepción** forma (la **activación** propiedad está establecida en **True** para que la recepción de un determinado mensaje hará que la orquestación para ejecutarse ) con la expresión de filtro anterior aplicada a él. El mensaje entrante se espera que tenga la propiedad Quantity en el espacio de nombres **InvoiceSchema**. La orquestación solo acepta facturas para 1000 elementos o más, de modo que el motor de tiempo de ejecución comprueba el mensaje entrante antes de que se ejecute.  
  
 La siguiente tabla muestra los operadores que se pueden utilizar en expresiones de filtro.  
  
|Operador|Description|Ejemplo|  
|--------------|-----------------|-------------|  
|==|igual a|ReqMsg(Total) == 100|  
|!=|no es igual a|ReqMsg(Total) != 100|  
|<|menor que|ReqMsg(Total) \< 100|  
|>|mayor que|ReqMsg(Total) > 100|  
|<=|menor que o igual a|ReqMsg(Total) \<= 100|  
|>=|mayor que o igual a|ReqMsg(Total) > = 100|  
|exists|exists|ReqMsg(Description) existe|  
  
> [!NOTE]
>  Valores de cadena en expresiones de filtro están entre comillas, por ejemplo: reqmsg (Description) = "Estado de pedido de compra". No se puede utilizar un valor de carácter en una expresión de filtro.  
  
> [!NOTE]
>  Si la recepción de activación está asociada a un puerto de enlace directo y posteriormente se envía un mensaje del mismo tipo con el mismo valor para la propiedad probada en el filtro, se creará un bucle infinito. El mensaje irá al cuadro de mensajes, de donde se recuperará porque coincide con los criterios del filtro. Para evitarlo, se debe filtrar según una propiedad diferente, enviar un mensaje de un tipo distinto o asegurarse de cambiar el valor de la propiedad antes de enviar un mensaje del mismo tipo.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar la forma recepción](../core/how-to-configure-the-receive-shape.md)   
 [Usar correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md)   
 [Usar campos distintivos y campos de propiedades](../core/using-distinguished-fields-and-property-fields.md)   
 [Usar mensajes en orquestaciones](../core/using-messages-in-orchestrations.md)