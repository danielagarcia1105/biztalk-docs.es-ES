---
title: Prueba de carga de control de tráfico | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- LoadGen tool, simulating floodgate events
- performance, floodgate peaks
- floodgate events [performance]
ms.assetid: 937f2478-339b-4ae2-b107-56f3a4bfc579
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74954d8b94207832ceee5bbb699a7de1a245f61b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246212"
---
# <a name="floodgate-load-test"></a>Prueba de carga de control de tráfico (floodgate)
La información de este tema hace referencia a las pruebas que se explican en [escenarios de prueba para medir el rendimiento máximo Sostenible del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md).  
  
## <a name="what-causes-floodgate-events"></a>¿Qué provoca un evento de control de tráfico (floodgate)?  
 Hay varios escenarios donde solo unos pocos valores máximos (también conocido como **eventos de control de tráfico**) de los mensajes llegan en el sistema, cada día. Entre estos valores máximos, el rendimiento puede ser muy bajo. Entre los ejemplos de estos tipos de escenarios se incluyen:  
  
-   Operaciones de patrimonio neto, por ejemplo, en la apertura y el cierre de los mercados  
  
-   Sistemas bancarios, por ejemplo, durante la conciliación de las transacciones del día  
  
 Otros tipos de eventos puede producir un comportamiento de acumulación similar a los eventos de control de tráfico (floodgate). Por ejemplo, si la dirección de envío de un socio comercial queda sin conexión de modo que los mensajes cuyo destino era dicha dirección deben volver a intentarse o suspenderse, esto puede provocar la generación de una acumulación. Cuando el socio comercial vuelva a estar conectado, podría haber un gran número de mensajes suspendidos que deben reanudarse, lo que provocaría otro tipo de evento de control de tráfico (floodgate). La siguiente prueba del sistema ilustra este comportamiento.  
  
## <a name="simulating-a-floodgate-event"></a>Simular un evento de control de tráfico (floodgate)  
 A fines de esta prueba, el sistema se puso aproximadamente a la mitad del rendimiento máximo sostenible, valor que por supuesto era muy estable A continuación, para simular un evento de control de tráfico (floodgate), se configuró la herramienta de generación de cargas para que enviara unos 419 mensajes/segundo durante un corto período de tiempo (el mismo valor que para la prueba de sobrecarga). A continuación, se muestra el perfil de carga resultante que mide los mensajes recibidos por segundo y la profundidad de la cola.  
  
 **Perfil de carga de prueba de carga de control de tráfico**  
  
 ![Pantalla del monitor de rendimiento de carga de control de tráfico](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")  
  
 Observe en el gráfico que las tablas de colas generan una acumulación rápidamente durante el evento de control de tráfico (floodgate). Sin embargo, puesto que el evento fue relativamente corto y la velocidad de recepción posterior fue inferior a la velocidad máxima sostenible, los trabajos de limpieza pudieron ejecutarse y recuperarse del evento sin necesidad de una interrupción de recepción en el sistema Para esta prueba específica, el cuadro de mensajes se alojó en SQL Server 2005. La duración de esta prueba, de principio a fin, fue de aproximadamente 45 minutos.  
  
 Por supuesto, todos los sistemas son diferentes, por lo tanto, los datos serán distintos El mejor modo de comprobar que puede recuperarse es probar con una carga representativa antes de pasar a producción.  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de prueba para medir MST del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [Mediante el panel de configuración de BizTalk Server ajuste del rendimiento](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)   
 [Prueba de sobrecarga](../core/overdrive-load-test.md)   
 [Prueba de carga sostenible](../core/sustainable-load-test.md)