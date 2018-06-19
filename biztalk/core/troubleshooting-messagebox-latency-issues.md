---
title: Solución de problemas de latencia de cuadro de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9eb5789-80bd-40d4-8c27-7ae117fd9232
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e37fc970230bf218bcfd820611fb6b87322e535
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279876"
---
# <a name="troubleshooting-messagebox-latency-issues"></a>Solucionar problemas de latencia del cuadro de mensajes
En un mundo perfecto, todos los mensajes se deberían procesar y entregar en el momento de publicarse en la base de datos de cuadro de mensajes, y ésta nunca debería alcanzar un tamaño excesivo. Asimismo, los trabajos del Agente SQL que limpian periódicamente las tablas de la base de datos de cuadro de mensajes deberían quitar inmediatamente los mensajes del cuadro de mensajes a los que ya no se haga referencia.  
  
 Sin embargo, en el mundo real, los mensajes no se reciben normalmente de una forma predecible y lineal, y los trabajos del Agente SQL necesitan tiempo para limpiar las tablas de la base de datos de cuadro de mensajes.  
  
 Por lo tanto, en algunas situaciones, el cuadro de mensajes puede alcanzar un tamaño bastante grande muy rápidamente.  
  
 Lo siguiente puede provocar un crecimiento excesivo del cuadro de mensajes y afectar al rendimiento general:  
  
-   **Se ha detenido la instancia de Host de Biztalk que tiene la opción "Permitir seguimiento de Host" establecida**. Se trata del host responsable de mover los datos de seguimiento de la base de datos de cuadro de mensajes a la base de datos de seguimiento de BizTalk (BizTalkDTADb).  
  
-   **No se está ejecutando el Agente SQL Server** Esto puede ocurrir si no se ejecutan los trabajos SQL responsables de mover datos de la base de datos de cuadro de mensajes a la base de datos de BizTalkDTADb [posterior purga los datos movidos en el cuadro de mensajes]. Es necesario que el servicio del Agente SQL esté en ejecución todo el tiempo para evitar este problema.  
  
-   **Trabajos de SQL Server están deshabilitados** aunque se esté ejecutando el Agente SQL Server, es imperativo que ninguno de los trabajos de SQL Server predeterminado esté deshabilitado.  
  
-   **Base de datos BizTalkDTADb crece en exceso** Esto puede ocurrir si la base de datos de BizTalkDTADb crece mucho, lo que la inserción en la base de datos de BizTalkDTADb tarden más tiempo. En tal caso, el servicio de entrega de datos de seguimiento (TDDS) moverá los datos más lentamente y se creará un trabajo acumulado en la base de datos de cuadro de mensajes. Para evitar este problema, es importante ejecutar periódicamente los trabajos de archivo y purga de SQL Server en las bases de datos BizTalkDTADb.  
  
-   **Latencia de E/S de disco excesiva** si la velocidad de entrada de datos en la base de datos de cuadro de mensajes es más rápido que lo que puede procesar el sistema y mover los datos a la base de datos de BizTalkDTADb, puede acumular trabajo en la base de datos de cuadro de mensajes. Si el trabajo se sigue acumulando sin cesar, se trata de un problema muy grave y el rendimiento del sistema se verá afectado con el tiempo. Una forma de solucionar este problema consiste en instalar discos más rápidos o actualizar el hardware para garantizar que el sistema pueda recuperarse si se detecta que los mensajes se acumulan a lo largo del tiempo.  
  
## <a name="plan-for-the-future"></a>Planear con vistas al futuro  
 Aunque se sigan todas las recomendaciones anteriores, el volumen de datos de seguimiento movidos a la base de datos BizTalkDTADb crecerá mucho con el tiempo. Es importante implementar un plan de mantenimiento de bases de datos para archivar los datos de seguimiento de forma periódica de modo que el rendimiento del sistema pueda seguir siendo óptimo.  
  
 La cantidad de datos históricos que se pueden conservar en la base de datos BizTalkDTADb depende del volumen de mensajes que pasen por el sistema. En el caso de los sistemas no sometidos a una elevada carga y procesamiento, esta base de datos crecerá a una velocidad inferior y se podrán conservar más datos históricos en la base de datos BizTalkDTADb.  
  
 Se recomienda conservar el mínimo de datos en la base de datos BizTalkDTADb para que el rendimiento en tiempo de ejecución no se vea afectado.