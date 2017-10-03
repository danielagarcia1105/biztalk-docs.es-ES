---
title: Advanced Functoids | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bf2547-5e44-45f8-b577-97e5760a0339
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5002b639df79ece1019c2d013c128f615517ae5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="advanced-functoids"></a>Functoids avanzados

## <a name="overview"></a>Información general
Los functoids avanzados se dividen en cinco grupos según su uso:  
  
-   **Administrar registros de bucle.** El **índice**, **iteración**, **bucle**, **valor nulo**, **número de registros**, **tabla Extractor de tablas**, y **bucle de tabla** los functoids se utilizan en diversas combinaciones cuando el mensaje de instancia de entrada contiene secciones con un impredecible número de elementos, que se repiten como se representa mediante un bucle registros del esquema de origen.  
  
-   **Asignación condicional.** El **asignación de valores** y **asignación de valores (sin formato)** functoids se utilizan para proporcionar asignación condicional de un mensaje de instancia de entrada a un mensaje de instancia de salida. Cuando el primer parámetro de entrada tiene el valor True, el segundo parámetro de entrada se coloca en el elemento o atributo especificado del mensaje de instancia de salida; en caso contrario, no se crea ese elemento o atributo en el mensaje de instancia de salida.  
  
-   **Secuencias de comandos arbitrarias.** El **secuencias de comandos** functoid se utiliza para ejecutar secuencias de comandos arbitrarias o código compilado cuando se asigna un mensaje de instancia de entrada a un mensaje de instancia de salida. La secuencia de comandos o el código compilado pueden crearse de forma que acepten parámetros de entrada del mensaje de instancia de origen, de valores constantes configurados, de la salida de otro functoid o de alguna combinación de los anteriores.  
  
-   **Asignación simple.** El **copia masiva** functoid puede utilizarse para copiar un elemento entero, incluidos sus subelementos hasta una profundidad arbitraria, de un mensaje de instancia de entrada a un mensaje de instancia de salida.  
  
-   **Solución de problemas de**. El **Assert** functoid puede utilizarse para probar sus suposiciones acerca de los valores de elemento.  
  
## <a name="available-functoids"></a>Functoids disponibles
  
 El **avanzadas** functoids son: 

* Functoid de aserción
* Índice (functoid) 
* Iteración (functoid) 
* Bucle (functoid) 
* Copia masiva (functoid) 
* Valor nulo (functoid)
* Functoid de número de registros 
* Secuencias de comandos (functoid) 
* Bucle de tabla y Functoids de Extractor de tabla
* Asignación de valores (functoid)
* Asignación de valores (sin formato) (functoid)

Obtener más detalles sobre estos functoids están en el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Functoid de aserción](../core/assert-functoid.md)  
  
-   [Functoid de índice](../core/index-functoid.md)  
  
-   [Functoid de iteración](../core/iteration-functoid.md)  
  
-   [Functoid de bucle](../core/looping-functoid.md)  
  
-   [Functoid de copia masiva](../core/mass-copy-functoid.md)  
  
-   [Functoid de valor nulo](../core/nil-value-functoid.md)  
  
-   [Functoid de número de registros](../core/record-count-functoid.md)  
  
-   [Bucle de tabla y Functoids de Extractor de tabla](../core/table-looping-and-table-extractor-functoids.md)  
  
-   [El Functoid de asignación de valores](../core/value-mapping-functoid.md)  
  
-   [Valor de asignación de Functoid (sin formato)](../core/value-mapping-flattening-functoid.md)  
  
-   [Secuencias de comandos de Functoid](../core/scripting-functoid.md)