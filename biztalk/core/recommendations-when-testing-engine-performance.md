---
title: Recomendaciones al probar el rendimiento del motor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: maximum sustainable throughput (MST), best practices
ms.assetid: 0aa9d833-0e7d-4347-a6ca-8d658749b4f2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fc2d81ca8121fe625a30258070281d2b3ff4bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="recommendations-when-testing-engine-performance"></a>Recomendaciones al probar el rendimiento del motor
Es recomendable seguir las siguientes instrucciones al probar el rendimiento del motor de BizTalk:  
  
 **Conocer el perfil de comportamiento de carga** tal y como se han demostrado las pruebas de tres carga, es fundamental conocer el perfil de la carga en términos de mensajes procesados en el tiempo.  Cuanto mejor entienda esto, mejor podrá comprobar y ajustar la capacidad del sistema. Si lo único que conoce es el requisito de rendimiento máximo, el enfoque más conservador sería dimensionar el sistema de modo que el rendimiento máximo sostenible sea igual o mayor que la carga máxima. Sin embargo, si sabe que tiene máximos y mínimos predecibles en la carga, puede optimizar mejor el sistema para recuperarse entre máximos, lo que supone una implementación general más pequeña y menos costosa.  
  
 **Probar el rendimiento al principio** : Evite caer en la trampa de hacer un esfuerzo significativo para diseñar y probar la funcionalidad de la solución, pero espera hasta el último minuto para probar el rendimiento en hardware de producción. Ejecute lo antes posible en el ciclo de desarrollo pruebas de rendimiento en el sistema que simulen el perfil de carga esperado. Si tiene que cambiar algo en su diseño o arquitectura para alcanzar el objetivo, el hecho de saberlo pronto le proporcionará el tiempo necesario para hacer ajustes y volver a comprobar.  
  
 **Simule el perfil de carga esperado al probar el rendimiento** hay dos componentes principales para esto:  
  
1.  Simule el perfil de carga a lo largo del tiempo.  
  
2.  Ejecute la prueba el tiempo suficiente para evaluar si es sostenible.  
  
 Si, como suele ser habitual, sus ciclos son de índole diaria, debería planear la ejecución de pruebas de rendimiento de al menos un día, con el fin de validar la sostenibilidad. Cuanto más larga sea la ejecución de las pruebas, mejor.  
  
 **Emular la configuración de producción** por ejemplo, el número y tipo de puertos, el host y el host de la instancia configuración, la configuración de la base de datos y el programa de instalación del adaptador. No crea que los cambios de configuración no afectarán significativamente al rendimiento.  
  
 **Utilice mensajes reales** tamaños de mensaje y la complejidad de los mensajes afectan al rendimiento, por lo tanto asegúrese y probar con los mismos esquemas de mensaje e instancias que planea ver en producción.  
  
 **Simule las operaciones normales durante las pruebas de rendimiento** aunque las pruebas de carga no incluía las actividades estándar, estas operaciones, como las consultas periódicas de la base de datos, copias de seguridad, y purga afectará al rendimiento sostenible, por lo que asegurarse de llevar a cabo estas tareas durante las ejecuciones de pruebas de capacidad y el rendimiento. Esto incluye el seguimiento de DTA y BAM si planea utilizarlos en la fase de producción.  
  
 **La velocidad del subsistema de E/S para el cuadro de mensajes es un factor de éxito clave** las pruebas de carga que se realizaron realizan se utilizó una red de área de almacenamiento rápida para los archivos de base de datos de cuadro de mensajes que se dedica a esta salida de compilación. Incluso en este caso, los trabajos de limpieza pudieron llevar el tiempo de inactividad cerca de cero para el archivo de datos SQL. El subsistema E/S resulta con frecuencia un cuello de botella en los sistemas de producción. Una estrategia habitual para optimizar la E/S de SQL es colocar, si es posible, el archivo (o archivos) de datos de base de datos y el archivo (o archivos) de registro en unidades físicas independientes.  
  
 **Asegúrese de que el Agente SQL se ejecuta en todos los servidores de cuadro de mensajes** claramente, los trabajos de limpieza nunca se ejecutar si no se está ejecutando el Agente SQL, por lo tanto asegúrese de que se estén ejecutando.  
  
 **Profundidad de cola de impresión es un indicador clave** independientemente de otros indicadores, esta medida le proporcionará una manera rápida y sencilla para evaluar si el sistema está sobrecargándose o no.