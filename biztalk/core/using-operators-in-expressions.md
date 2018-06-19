---
title: Usar operadores en expresiones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, operators
- XLANG/s, operators
- orchestrations, XLANG/s
ms.assetid: f0948ce2-c508-48aa-af79-d207f577b22f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5aec9ed6ebecb0b151dbfe9d5c09707b954fdf45
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974306"
---
# <a name="using-operators-in-expressions"></a>Usar operadores en expresiones
Los siguientes operadores XLAN/s están disponibles para su uso en expresiones de orquestaciones. Cumplen estrictamente con las funciones de los operadores correspondientes en C#.  
  
|Operador|Description|Ejemplo|  
|--------------|-----------------|-------------|  
|checked()|genera error al producirse un desbordamiento aritmético|checked(x = y * 1000)|  
|unchecked()|omite el desbordamiento aritmético.|unchecked(x = y * 1000)|  
|nuevo|crea una instancia de una clase|myObject = new MyClass;|  
|typeof|recuperación de tipo|myMapType = typeof(myMap)|  
|succeeded()|prueba para la finalización correcta de ámbito transaccional u orquestación|se ha realizado correctamente (\<identificador de transacción de secundarios del ámbito actual o servicio\>)|  
|exists|prueba para la existencia de una propiedad de contexto de mensaje|BTS.RetryCount exists Message_In|  
|+|más unario|+(int x)|  
|-|menos unario|-(int x)|  
|!|negación lógica|!myBool|  
|~|complemento bit a bit|x = ~y|  
|()|Conversión de tipos|(bool) myInt|  
|*|times|Weight = MyMsg.numOrders * 20|  
|/|dividido por|x / y|  
|+|más|x + y|  
|-|menos|x - y|  
|<<|desplazar a la izquierda|x << 2|  
|>>|desplazar a la derecha|x >> 2|  
|<|menor que|Si (MyMsg.numOrders < 10)...|  
|>|mayor que|Si (MyMsg.numOrders > 10)...|  
|<=|menor que o igual a|Si (MyMsg.numOrders < = 10)...|  
|>=|mayor que o igual a|Si (MyMsg.numOrders > = 10)...|  
|==|igual a|If (MyMsg.numOrders == 10)...|  
|!=|no es igual a|If (MyMsg.numOrders != 10)...|  
|&|y|Si (myByte & 255)...|  
|^|exclusivo o|If (myByte ^ 1)...|  
|&#124;|o bien|Si (myByte &#124; 1)...|  
|&&|condicional y|Si (MyMsg.numOrders > 10) & & (MyMsg.numOrders < 100)|  
|&#124;&#124;|condicional o|Si (MyMsg.numOrders < 10) &#124; &#124; (MyMsg.numOrders > 100)|  
|//|comentario|//Éste es el comentario|  
  
> [!NOTE]
>  Las reglas difieren entre las expresiones generales y las expresiones de filtro que se usan con la **recepción** forma.  
  
## <a name="see-also"></a>Vea también  
 [Uso de filtros con la forma Recibir mensaje](../core/using-filters-with-the-receive-message-shape.md)