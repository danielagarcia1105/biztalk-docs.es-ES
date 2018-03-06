---
title: "Orquestación deshidratación y rehidratación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57d7c0bf-a707-4ebd-afab-e75dd80c3c34
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7cee568cda6c869ede94e28bce441462c0c7cdc
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="orchestration-dehydration-and-rehydration"></a>Deshidratación y rehidratación de orquestaciones
Cuando se ejecutan a la vez muchos procesos empresariales de larga duración, la memoria y el rendimiento se convierten en problemas potenciales. El motor de la orquestación aborda estos problemas mediante la "deshidratación" y la "rehidratación" de las instancias de orquestación.  
  
 La deshidratación es el proceso de serializar el estado de una orquestación en una base de datos de SQL Server. Rehidratación es el proceso inverso: deserializar el último estado de ejecución de una orquestación de la base de datos. La deshidratación se utiliza para minimizar el uso de recursos de sistema al reducir el número de las orquestaciones de las que a la vez se tiene que crear la instancia en memoria.  
  
## <a name="dehydration"></a>Deshidratación  
 La orquestación puede determinar que una instancia de orquestación ha estado inactiva durante un período relativamente grande. Calcula umbrales para determinar el tiempo que esperará para que tengan lugar varias acciones y, si dichos umbrales se superan, deshidrata la instancia. Esto puede producirse en las siguientes circunstancias:  
  
-   Si la orquestación espera la recepción de un mensaje y el tiempo de espera es superior al umbral determinado por el motor.  
  
-   Cuando la orquestación "escucha" para un mensaje, como ocurre cuando se usa un **escuchar** forma y ninguna bifurcación se desencadena antes de un umbral determinado por el motor. La única excepción a esto es cuando la **escuchar** forma contiene una activación de recepción.  
  
-   Si un retraso en la orquestación es mayor que el umbral determinado por el motor.  
  
 El motor deshidrata la instancia; para ello, guarda el estado de la instancia y libera la memoria que ésta necesita. Mediante la deshidratación de instancias de orquestación latentes, el motor permite un gran número de procesos empresariales de larga ejecución para ejecutar simultáneamente en el mismo equipo.  
  
 Se pueden establecer 12 propiedades para configurar el funcionamiento de la deshidratación en BizTalk Server. Los temas de esta sección enumeran y describen las propiedades y sus valores predeterminados, y explican el modo en que los distintos valores afectan al comportamiento de la deshidratación.  
  
## <a name="rehydration"></a>Rehidratación  
 El motor de orquestaciones se inicia para rehidratar una instancia de orquestación mediante la recepción de un mensaje o el vencimiento de un tiempo de espera especificado en una forma Retraso. Después carga la instancia de orquestación guardada en la memoria, restaura su estado y la ejecuta desde el punto en que se interrumpió. Para obtener más información sobre el uso de formas en orquestaciones, consulte [formas de orquestación](../core/orchestration-shapes.md).  
  
 Una orquestación se puede configurar para que se ejecute en más de un servidor. Después de que una instancia de orquestación se haya deshidratado, puede rehidratarse en cualquiera de estos servidores. Si un servidor deja de funcionar, el motor continúa ejecutando la orquestación en un servidor diferente desde su estado anterior. El motor también aprovecha esta característica para implementar el equilibrio de carga entre los servidores.  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Propiedades predeterminadas de deshidratación](../core/dehydration-default-properties.md)  
  
-   [Cómo calcular la deshidratación](../core/how-to-calculate-dehydration.md)  
  
-   [Ejemplo de cálculo de deshidratación](../core/sample-dehydration-calculation.md)  
  
-   [Contadores de rendimiento de deshidratación de orquestaciones](../core/orchestration-dehydration-performance-counters.md)  
  
-   [BTSNTSvc.exe.config (archivo)](../core/btsntsvc-exe-config-file.md)  
  
-   [Otras actividades que pueden afectar al comportamiento de deshidratación](../core/other-activities-that-can-affect-dehydration-behavior.md)