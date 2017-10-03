---
title: Contadores de rendimiento del motor de orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dcaf7517-da4a-4ed0-a3bb-7e9b73931bff
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c4b3dada1e3775c918d99b1ce0269ac8b1e2a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-engine-performance-counters"></a>Contadores de rendimiento de motor de orquestaciones
El motor de orquestaciones mantiene varios contadores de rendimiento que puede examinar con el Monitor de rendimiento para ver cuántas instancias de orquestación y transacciones procesa el motor durante un cierto período.  
  
 Para ejecutar el Monitor de rendimiento, vaya a la **iniciar** menú, seleccione **ejecutar**, escriba **perfmon**y presione **ENTRAR**. Haga clic en el **agregar** botón y seleccione **orquestaciones XLANG/s** desde el **objeto de rendimiento** lista desplegable.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **orquestaciones XLANG/s** categoría de objeto de rendimiento:  
  
|Contador|Comentarios|  
|-------------|--------------|  
|% usado de memoria física|Porcentaje de memoria física total utilizado en el equipo.|  
|Dominios de aplicación activa|Número de dominios de aplicación de orquestación cargados en el proceso.|  
|Factor de lotes medio|Número de puntos de persistencia alcanzados desde que se inició la instancia de host, divididos entre el número de transacciones subyacentes.|  
|Transacciones de base de datos|Número de transacciones de base de datos realizadas desde que se inició la instancia de host|  
|Transacciones de base de datos/seg.|Número promedio realizado por segundo.|  
|Orquestaciones deshidratables|Número de instancias de orquestación que se pueden deshidratar y que están actualmente alojadas por la instancia de host.|  
|Deshidratando orquestaciones|Número de orquestaciones que se están deshidratando.|  
|Ciclo de deshidratación en curso|Indica si es actualmente hay un ciclo de deshidratación en curso.|  
|Ciclos de deshidratación|Número de ciclos de deshidratación completados.|  
|Umbral de deshidratación|Número en milisegundos que determina la forma agresiva en que se deshidratan orquestaciones. Si el motor de orquestaciones predice que una instancia será deshidratable durante un período superior a este umbral, deshidratará la instancia.|  
|Orquestaciones inactivas|Número de instancias de orquestaciones inactivas que están actualmente alojadas por la instancia de host. Hace referencia a orquestaciones que no progresan pero que no son deshidratables, como cuando se bloquea la orquestación mientras se espera una recepción, escucha o retraso en una transacción atómica.|  
|Megabytes asignados a la memoria privada|Megabytes de memoria privada asignada para la instancia de host.|  
|Megabytes asignados a la memoria virtual|Megabytes reservados para memoria virtual para la instancia de host.|  
|Errores de conexión de bases de datos de cuadro de mensajes|Número de conexiones de base de datos intentadas que produjeron errores desde que se inició la instancia de host.|  
|Bases de datos de cuadro de mensajes en línea|Número de bases de datos de cuadro de mensajes que actualmente están disponibles para la aplicación.|  
|Orquestaciones completadas|Número de instancias de orquestación completadas desde que se inició la instancia de host.|  
|Orquestaciones completadas/seg|Número promedio completado por segundo.|  
|Orquestaciones creadas|Número de instancias de orquestación creadas desde que se inició la instancia de host.|  
|Orquestaciones creadas/seg.|Número promedio creado por segundo.|  
|Orquestaciones deshidratadas|Número de instancias de orquestación deshidratadas desde que se inició la instancia de host.|  
|Orquestaciones deshidratadas/seg.|Número promedio deshidratado por segundo.|  
|Orquestaciones descartadas|Número de instancias de orquestación descartadas de la memoria desde que se inició la instancia de host. Una orquestación se puede descartar si el motor no conserva su estado.|  
|Orquestaciones descartadas/seg.|Número promedio descartado por segundo.|  
|Orquestaciones rehidratadas|Número de instancias de orquestación rehidratadas desde que se inició la instancia de host.|  
|Orquestaciones rehidratadas/seg.|Número promedio rehidratado por segundo.|  
|Orquestaciones residentes en memoria|Número de instancias de orquestación alojadas actualmente por la instancia de host.|  
|Orquestaciones programadas para deshidratación|Número de orquestaciones deshidratables para las que existe una solicitud de deshidratación pendiente.|  
|Orquestaciones suspendidas|Número de instancias de orquestación suspendidas desde que se inició la instancia de host.|  
|Orquestaciones suspendidas/seg.|Número promedio suspendido por segundo.|  
|Mensajes pendientes|Número de mensajes recibidos para los que aún no se ha confirmado recepción al cuadro de mensajes.|  
|Elementos de trabajo pendiente|Número de bloques de ejecución de código programados para ejecución.|  
|Puntos de persistencia|Número de veces que una instancia de orquestación ha conservado su estado en la base de datos desde que se inició la instancia de host.|  
|Puntos de persistencia/seg.|Número promedio de instancias de orquestación guardadas por segundo.|  
|Orquestaciones ejecutables|Número de instancias de orquestación listas para ejecutarse.|  
|Orquestaciones en ejecución|Número de instancias de orquestación que se están ejecutando actualmente.|  
|Ámbitos transaccionales anulados|Número de ámbitos atómicos o de larga ejecución que se han anulado desde que se inició la instancia de host.|  
|Ámbitos transaccionales anulados/seg.|Número promedio anulado por segundo.|  
|Ámbitos transaccionales asignados|Número de ámbitos atómicos o de larga ejecución que se han completado correctamente desde que se inició la instancia de host.|  
|Ámbitos transaccionales asignados/seg.|Número promedio asignado por segundo.|  
|Ámbitos transaccionales compensados|Número de ámbitos atómicos o de larga ejecución que han completado correctamente ámbitos de compensación desde que se inició la aplicación.|  
|Ámbitos transaccionales compensados/seg.|Número promedio compensado por segundo.|  
  
## <a name="see-also"></a>Vea también  
 [Características de rendimiento del motor](../core/engine-performance-characteristics.md)   
 [Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [Medir el rendimiento máximo sostenible del motor](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)