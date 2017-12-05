---
title: Operadores y Variables de XLANG-s | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02512789-2cb9-4ba9-aa78-e59b248e6b24
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c1773b7af3ec029026ee884e6c1161e27a3c330
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="xlang-s-variables-and-operators"></a>Operadores y Variables de XLANG-s
En esta sección se tratan las variables y los operadores utilizados en el lenguaje XLANG/s.  
  
## <a name="xlangs-variables"></a>Variables de XLANG/s  
 Las variables representan ubicaciones de almacenamiento. Cada variable tiene un tipo que determina qué valores se pueden almacenar en ella. XLANG/s implementa la seguridad de tipos y su compilador garantiza que los valores almacenados en las variables siempre sean del tipo apropiado. XLANG/s admite lo siguientes tipos de variables:  
  
-   Mensajes  
  
-   Conjuntos de correlaciones  
  
-   Vínculos de servicios  
  
-   Puertos  
  
-   Distinguen tipos de valor integrados: **booleano**, **bytes**, **Char**, **Decimal**, **doble**,  **Int16**, **Int32**, **Int64**, **SByte**, **único**, **cadena**, **UInt16**, **UInt32**, y **UInt64**  
  
-   Objetos  
  
-   Tipos de enumeraciones  
  
 XLANG/s proporciona una semántica de inicialización para cada uno de los tipos anteriores. Esta inicialización se puede considerar como la asignación del tipo a una variable. En XLANG/s, una variable tiene que estar asignada con carácter definitivo antes de que se pueda obtener o usar su valor.  
  
## <a name="xlangs-operators"></a>Operadores de XLANG/s  
 XLANG/s admite los operadores siguientes. Cumplen estrictamente con las funciones de los operadores correspondientes en C#.  
  
|Operador|Description|Ejemplo|  
|--------------|-----------------|-------------|  
|activado|Genera un error al producirse un desbordamiento aritmético|checked(x = y * 1000)|  
|No está activada|Hace caso omiso del desbordamiento aritmético.|unchecked(x = y * 1000)|  
|nuevo|Crea una instancia de una clase|myObject = new MyClass;|  
|typeof|Recupera un tipo|myMapType = typeof(myMap)|  
|succeeded|Comprueba la finalización correcta de ámbito transaccional u orquestación|se ha realizado correctamente (\<identificador de transacción de secundarios del ámbito actual o servicio\>)|  
|exists|Comprueba la existencia de una propiedad de contexto de mensaje|BTS.RetryCount exists Message_In|  
|+|Suma unaria|+(int x)|  
|-|Resta unaria|-(int x)|  
|!|Negación lógica|!myBool|  
|~|Complemento bit a bit|x = ~y|  
|()|Conversión de tipos|(bool) myInt|  
|*|Veces|Weight = MyMsg.numOrders * 20|  
|/|Dividido por|x / y|  
|+|signo más|x + y|  
|-|Resta|x - y|  
|<<|Desplazamiento a la izquierda|x << 2|  
|>>|Desplazamiento a la derecha|x >> 2|  
|<|Menor que|Si (MyMsg.numOrders < 10)...|  
|>|Mayor que|Si (MyMsg.numOrders > 10)...|  
|<=|Menor o igual que|Si (MyMsg.numOrders < = 10)...|  
|>=|Mayor o igual que|Si (MyMsg.numOrders > = 10)...|  
|==|Igual a|If (MyMsg.numOrders == 10)...|  
|!=|No es igual a|If (MyMsg.numOrders != 10)...|  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos de XLANG-s](../core/xlang-s-data-types.md)   
 [Instrucciones de XLANG-s](../core/xlang-s-statements.md)   
 [Expresiones de XLANG-s](../core/xlang-s-expressions.md)   
 [Palabras reservadas de XLANG-s](../core/xlang-s-reserved-words.md)   
 [Conversiones de tipos de XLANG/s a BPEL4WS](../core/xlang-s-to-bpel4ws-type-conversions.md)