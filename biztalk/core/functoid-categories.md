---
title: Categorías de functoids | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 029905e2-f01a-436a-b2ed-a364379c9cc5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bf0b07020bb58725d7a9b20f0bc514c2421d02e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015324"
---
# <a name="functoid-categories"></a>Categorías de functoids
Los functoids de BizTalk se dividen en categorías según la utilización que se les vaya a dar. Por ejemplo, los functoids de bases de datos están diseñados para extraer datos de una base de datos en tiempo de ejecución, los functoids matemáticos se utilizan para efectuar operaciones matemáticas, etc. En el asignador de BizTalk, functoids aparecen ordenados por categorías en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] cuadro de herramientas. 

## <a name="categories--description"></a>& Descripción de categorías
En la siguiente tabla se muestran las categorías de functoids, se describe brevemente la categoría y se muestra la lista de functoids de cada una de ellas, incluidos los vínculos a las correspondientes páginas de referencia.  
  
|Categoría de functoid <br/><br/> Descripción de la categoría|Functoids de la categoría|  
|---|---|  
|**Avanzadas** <br /><br /> Utilizado principalmente con registros de bucle. También se utiliza para ejecutar secuencias de comandos arbitrarias o código compilado.|Imponer, índice, iteración, bucle, copia masiva, valor nulo, número de registros, secuencias de comandos, Extractor de tablas, bucle de tabla, valor de asignación, asignación de valores (sin formato)|  
|**Conversión** <br /><br /> Se utiliza para convertir desde y hacia ASCII y entre bases numéricas.|ASCII a carácter, carácter a ASCII, Hexadecimal, Octal|  
|**Acumulativa** <br /><br /> Se utiliza para efectuar operaciones matemáticas en registros de bucle, como promedios y concatenaciones.|Acumulativo, de promedio acumulativo, concatenación acumulativa, máximo acumulativo, mínimo suma acumulativa|  
|**Base de datos** <br /><br /> Se utiliza para extraer datos de una base de datos y utilizarlos en los mensajes de instancia de destino.|Base de datos de búsqueda, la devolución de Error, formatear mensaje, obtener Id. de aplicación, obtener valor de aplicación, obtener Id. común, obtener valor común, quitar Id. de aplicación, establecer Id. común, Extractor de valor|  
|**Fecha y hora** <br /><br /> Se utiliza para obtener la fecha y hora actuales y calcular diferencias de tiempo.|Agregar días, fecha, fecha y hora, tiempo|  
|**Lógicos** <br /><br /> Se utiliza para efectuar una serie de operaciones lógicas, como mayor que y existencia lógica.|Igual, mayor que, mayor o igual que, IsNil, menor que, menor o igual a, AND lógico, fecha lógica, existencia lógica, valor numérico lógico, lógico no, o lógico, cadena lógica, no igual|  
|**Matemáticas** <br /><br /> Se utiliza para efectuar una serie de operaciones matemáticas, como la suma o la multiplicación.|Valor absoluto, suma, división, entero, valor máximo, valor mínimo, módulo, multiplicación, redondear, raíz cuadrada, resta|  
|**Científico** <br /><br /> Se utiliza para efectuar una serie de operaciones científicas, como logaritmos y trigonometría.|10 ^ n, arco tangente, logaritmo en una Base especificada, logaritmo común, coseno, función exponencial Natural, logaritmo Natural, seno, tangente, X ^ Y|  
|**String** <br /><br /> Se utiliza para efectuar una serie de funciones de cadena, como recorte y concatenación.|Minúsculas, tamaño, concatenación de cadenas, extracción, búsqueda de cadenas, cadena izquierda de la cadena, recorte izquierdo de cadena, cadena derecha, la cadena en mayúsculas, recorte derecho|  
  
> [!NOTE]
>  El objeto de un functoid suele quedar claro con su nombre.  
> 
> [!NOTE]
>  Todos los functoids incluidos con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] son C# en línea, excepto para el **base de datos** functoids.  
  
## <a name="see-also"></a>Vea también  
 [Functoids básicos](../core/basic-functoids.md)   
 [Functoids avanzados](../core/advanced-functoids.md)