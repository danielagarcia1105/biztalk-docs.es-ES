---
title: Prueba de carga sostenible | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- sustainable load test
- LoadGen tool, sustainable load test
ms.assetid: a9d752ff-aff1-4445-8af5-8f84609880e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d17d8d38323f7933c8e60cb2b87e0ec312d270c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015653"
---
# <a name="sustainable-load-test"></a>Prueba de carga sostenible
La información de este tema hace referencia a las pruebas se explica en [escenarios de prueba para medir MST del motor](../core/test-scenarios-for-measuring-mst-of-the-engine.md).  
  
 Para la primera prueba, el sistema se colocó en estado MST para que se pudiesen realizar observaciones de un sistema en buen estado.  
  
 El siguiente gráfico muestra los indicadores principales después de utilizar este enfoque para hallar el rendimiento sostenible máximo del sistema de prueba.  
  
 **Perfil de carga de prueba de carga sostenible**  
  
 ![Monitor de sistema de medición de carga sostenible](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")  
  
 Este gráfico muestra que, durante la hora de la prueba, la profundidad de la cola fue estable y no creció:  
  
- Las líneas negras situadas en la parte superior del gráfico indican el total de mensajes recibidos por segundo en el sistema (por ejemplo, en los dos servidores de recepción).  
  
- Las líneas que se encuentran en la parte inferior del gráfico especifican la profundidad de la cola del cuadro de mensajes en cada uno de los servidores SQL Server.  
  
  Una vez que el sistema alcanza el punto máximo de profundidad de cola estable, se mide el valor MST mediante el número de mensajes recibidos por segundo. Para este escenario y con el hardware descrito, se logró un valor MST de 290 mensajes por segundo.  
  
> [!NOTE]
>  Cuando el sistema alcanza un punto en el que la profundidad de la cola deja de ser estable en el tiempo significa que se ha superado el valor MST. Es posible que sea necesario llevar a cabo varias ejecuciones de prueba con distinta carga para evaluar la carga máxima con la que la profundidad de la cola se mantiene estable y con la que el sistema puede controlar el registro de mensajes sin incurrir en un registro adicional de mensajes.  
  
 Cualquier análisis de rendimiento de una implementación de BizTalk debe incluir una comprobación de algunos indicadores clave para comprender los cuellos de botella de recursos. Las medidas clave y los valores correspondientes utilizados en esta implementación ejecutada con el rendimiento sostenible máximo fueron los siguientes:  
  
 **Uso de CPU**  
  
|Servidor|Uso promedio de la CPU|  
|------------|-----------------------------|  
|Servidores BizTalk Server|55%|  
|Servidor SQL Server (servidor de cuadro de mensajes principal)|76%|  
|Servidor SQL Server (otros servidores de cuadro de mensajes)|83%|  
  
 **Tiempo de inactividad de disco físico**  
  
|Servidor|Promedio de tiempo de inactividad del disco|  
|------------|----------------------------|  
|Promedio para todos los servidores SQL Server|69%|  
  
 **Bloqueos de SQL en SQL Server**  
  
|Parámetro|Valor|  
|---------------|-----------|  
|Promedio de total de tiempos de espera de bloqueos por segundo (por servidor SQL Server)|1980|  
|Promedio de total de tiempo de espera de bloqueos (ms)|495|  
  
 Durante esta prueba, no se generaron errores en el registro de la aplicación de BizTalk o SQL Server.  
  
 A partir de estos datos se pueden extraer las siguientes conclusiones:  
  
- No existen cuellos de botella de recursos obvios en el sistema.  
  
- Todos los indicadores se encuentran dentro de los límites de buen estado de funcionamiento.  
  
- Los tiempos de inactividad de la CPU y del disco ponen de manifiesto que existe una elevada capacidad y ni tan siquiera se aproximan a valores críticos.  
  
- Los indicadores de bloqueo SQL se ven bien, **tiempos de espera de bloqueo/s** no empieza a ser un problema hasta alrededor de 5000 ó es así (dependiendo de su servidor SQL Server) y espera de bloqueo de horas de menos de 1 segundo también están en buen estado.  
  
  Tras haber demostrado cómo hallar el rendimiento sostenible máximo y haber visto cuáles son los valores de los indicadores clave en un sistema sostenible en buen estado, examinaremos algunos comportamientos asociados con un sistema que recibe más rápido de lo que procesa y que recopila elementos no utilizados. Continúe con [sobrecarga (porcentaje) prueba de carga](../core/overdrive-load-test.md).  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de prueba para medir MST del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [Prueba de sobrecarga](../core/overdrive-load-test.md)