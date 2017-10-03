---
title: "Categorías de functoids | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 029905e2-f01a-436a-b2ed-a364379c9cc5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89db4168af133e616f48ded54cce98cd54bb8ec8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="functoid-categories"></a>Categorías de functoids
Los functoids de BizTalk se dividen en categorías según la utilización que se les vaya a dar. Por ejemplo, los functoids de bases de datos están diseñados para extraer datos de una base de datos en tiempo de ejecución, los functoids matemáticos se utilizan para efectuar operaciones matemáticas, etc. En el asignador de BizTalk, functoids aparecen ordenados por categorías en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] cuadro de herramientas. 

## <a name="categories--description"></a>Descripción de la & categorías
En la siguiente tabla se muestran las categorías de functoids, se describe brevemente la categoría y se muestra la lista de functoids de cada una de ellas, incluidos los vínculos a las correspondientes páginas de referencia.  
  
|Categoría de functoid <br/><br/> Descripción de la categoría|Functoids de la categoría|  
|---|---|  
|**Avanzadas** <br /><br /> Utilizado principalmente con registros de bucle. También se utiliza para ejecutar secuencias de comandos arbitrarias o código compilado.|Imponer, índice, iteración, bucle, copia masiva, valor nulo, número de registros, secuencias de comandos, Extractor de tablas, bucle de tabla, asignación, de valores (sin formato) de asignación de valores|  
|**Conversión** <br /><br /> Se utiliza para convertir desde y hacia ASCII y entre bases numéricas.|ASCII a carácter, carácter a ASCII, Hexadecimal, Octal|  
|**Acumulativa** <br /><br /> Se utiliza para efectuar operaciones matemáticas en registros de bucle, como promedios y concatenaciones.|Acumulado, promedio acumulativo, concatenación máximo acumulativo, mínimo, acumulativa suma acumulativa|  
|**Base de datos** <br /><br /> Se utiliza para extraer datos de una base de datos y utilizarlos en los mensajes de instancia de destino.|Base de datos de búsqueda, devolución de Error, formatear mensaje, obtener Id. de aplicación, obtener valor de aplicación, obtener Id. común, obtener valor común, quitar Id. de aplicación, establecer Id. común, Extractor de valor|  
|**Fecha y hora** <br /><br /> Se utiliza para obtener la fecha y hora actuales y calcular diferencias de tiempo.|Agregar días, fecha, fecha y hora, tiempo|  
|**Lógicos** <br /><br /> Se utiliza para efectuar una serie de operaciones lógicas, como mayor que y existencia lógica.|Igual, mayor que, mayor o igual que, IsNil, menor que, menor o igual a, AND lógico, fecha lógica, existencia lógica, valor numérico lógico, lógico no, o lógico, cadena lógica, no igual|  
|**Matemáticas** <br /><br /> Se utiliza para efectuar una serie de operaciones matemáticas, como la suma o la multiplicación.|Valor absoluto, suma, división, entero, valor máximo, valor mínimo, módulo, multiplicación, Round, raíz cuadrada, resta|  
|**Científico** <br /><br /> Se utiliza para efectuar una serie de operaciones científicas, como logaritmos y trigonometría.|10 ^ n, arco tangente, logaritmo en una Base especificada, logaritmo común, coseno, función exponencial Natural, logaritmo Natural, seno, tangente, X ^ Y|  
|**String** <br /><br /> Se utiliza para efectuar una serie de funciones de cadena, como recorte y concatenación.|Minúsculas, tamaño, concatenación de cadenas, cadena extracción, búsqueda de cadenas, cadena izquierda, recorte izquierdo de cadena, cadena derecha, cadena en mayúsculas, recorte derecho|  
  
> [!NOTE]
>  El objeto de un functoid suele quedar claro con su nombre.  
  
> [!NOTE]
>  Todos los functoids incluidos con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] son C# en línea excepto la **base de datos** functoids.  
  
## <a name="see-also"></a>Vea también  
 [Functoids básicos](../core/basic-functoids.md)   
 [Functoids avanzados](../core/advanced-functoids.md)