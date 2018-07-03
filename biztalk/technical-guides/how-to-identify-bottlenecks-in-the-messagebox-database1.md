---
title: Cómo identificar cuellos de botella en la base de datos1 del cuadro de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a039164-5ca6-4cbc-b307-c5d4ae800689
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55d766405716a63249eae8fd47fd1f82077e05d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001124"
---
# <a name="how-to-identify-bottlenecks-in-the-messagebox-database"></a>Cómo identificar cuellos de botella en la base de datos de cuadro de mensajes
Para identificar cuellos de botella en la base de datos de cuadro de mensajes, en primer lugar debe asegurarse de que se haya iniciado el servicio del Agente de SQL Server. Cambiar el estado de inicio del servicio de Manual a automático de modo que si se reinicia el servidor, el servicio se reiniciará automáticamente.  
  
 De forma predeterminada, el servicio de BizTalk limitará si el crecen de las tablas Spool, TrackingData o applicationq aumentan. Trabajos del agente de SQL, que, si no se está ejecutando hará que la cola de impresión crezca y provocará una limitación para iniciar y proteger la base de datos contra presiones adicionales purgan estas tablas. Compruebe el estado de los siguientes contadores de rendimiento:  
  
- BizTalk:Agente de mensaje (nombre de host) Estado de limitación de entrega de mensajes  
  
- BizTalk:Agente de mensaje (nombre de host) Estado de limitación de publicación de mensajes  
  
  Un valor de "0" indica que no se produce ninguna limitación. Un valor de "6" indica que el sistema limita debido al crecimiento de la base de datos. Para obtener información sobre cómo interpretar los valores de estos contadores, vea [¿qué es la limitación de Host?](http://go.microsoft.com/fwlink/?LinkID=154694) (http://go.microsoft.com/fwlink/?LinkID=154694) y [los contadores de rendimiento de limitación de Host](http://go.microsoft.com/fwlink/?LinkID=155285) (http://go.microsoft.com/fwlink/?LinkID=155285) en la documentación de BizTalk Server 2010.  
  
## <a name="spool-table-growth"></a>Crecimiento de la tabla de cola de impresión  
 La tabla Spool puede empezar a crecer por distintos motivos. Una razón para el crecimiento de la cola de impresión es si las colas de aplicaciones están creciendo. Podía crecer debido a razones como cuellos de botella descendentes o contención de recursos.  
  
 Si las colas de aplicaciones son pequeñas y la cola de impresión sigue siendo muy grande, compruebe que los trabajos de purga se mantienen actualizados. Asegúrese de que el servicio de Agente de SQL Server esté en ejecución y, a continuación, compruebe que los siguientes trabajos se estén realizando correctamente:  
  
- MessageBox_Message_Cleanup_BizTalkMessageBoxDb  
  
- MessageBox_Parts_Cleanup_BizTalkMessageBoxDb  
  
  Si la tabla MessageZeroSum es grande, indica que se han procesado los mensajes. Esto significa que DeQueue ha completado correctamente y se eliminan los datos de las tablas de cola de la aplicación y las filas se han marcado para su eliminación. Sin embargo, los trabajos de purga no pueden eliminar los datos a la velocidad necesaria. Esto puede ocurrir si el equipo que ejecuta SQL Server está experimentando una contención grave de CPU, que afectan a la capacidad de los trabajos de purga para mantenerse al día debido a la privación de la CPU.  
  
## <a name="application-queue-table-growth"></a>Crecimiento de tabla de cola de aplicación  
 Colas de la aplicación hospedan los datos de transición en curso que, una vez procesados, son eliminados por DeQueue.  
  
 Después de procesan estos mensajes, puede limpiar la tabla Spool (que contiene referencias a estas filas).  
  
 Por ejemplo, la cola RxHostQ publica datos en la cola PxHostQ de orquestación. Esta cola publica datos en el envío TxHostQ cada uno de los que hacen referencia a una fila en la tabla de cola de impresión. Después de que se procesaron correctamente los mensajes de una cola HostQ concreta a través del sistema, DeQueue elimina estas filas. Una vez eliminadas las filas, los trabajos de purga pueden borrar el contenido de la tabla Spool (a la que estas filas ya no hacen referencia).  
  
 Crecimiento de la cola de aplicación indica que las instancias de host responsables de purga de la cola de aplicación no se puede hacer frente a la velocidad de entrada.  
  
 Por ejemplo, la cola de aplicación de orquestación (PxHostQ) puede aumentar de tamaño porque el servidor responsable de procesar las orquestaciones está enlazado a la CPU y no puede procesar más rápidamente. Sin embargo, si el servidor de recepción es rápido puede publicar más rápido que la que el servidor puede procesar, por lo que el crecimiento de la cola de la aplicación.  
  
 Otra razón para el crecimiento de la cola de orquestación podría ser debido a la contención de memoria. Cuando varias instancias de orquestación de larga ejecución al mismo tiempo se crean instancias en memoria, inundación de memoria consecuencia indirecta de limitación para reducir el grupo de subprocesos hasta que se alivia la presión de memoria.  
  
 Un motivo por qué se puede alcanzar la cola de la aplicación de envío es si el sistema de nivel inferior no puede recibir mensajes (de salida desde BizTalk Server) lo suficientemente rápido. Por tanto, los mensajes siguen residiendo en el crecimiento de cola de la aplicación que causan de sistema de BizTalk. Esto puede causar la limitación iniciar y reducir la velocidad de recepción afectar el rendimiento general del sistema.  
  
## <a name="trackingdata-table-growth"></a>Crecimiento de la tabla TrackingData  
 La tabla TrackingData en la base de datos de cuadro de mensajes es una tabla de transición en la que los interceptores escriben datos de seguimiento para el seguimiento de estado y actividad (HAT) y supervisión de la actividad económica (BAM). Si el seguimiento está deshabilitado, esta tabla debe estar vacía. De forma predeterminada, el seguimiento de HAT está habilitado para las canalizaciones y orquestaciones de eventos de entrada/salida.  
  
 Si está habilitado el seguimiento de partes de mensaje, asegúrese de que se está ejecutando el servidor de base de datos de cuadro de mensajes (es decir, el host con "Permitir seguimiento de host"). Asegurarse de que se está ejecutando el host con "Permitir seguimiento de host" reducirá la posibilidad de un cuello de botella como el host mueve los datos de la tabla TrackingData en la base de datos de cuadro de mensajes a las tablas de base de datos de seguimiento de BizTalk.  
  
 Es posible realizar el seguimiento de eventos personalizados mediante la habilitación del seguimiento de HAT personalizado, por ejemplo, en propiedades promocionadas y seguimiento de cuerpos de mensaje. Además de los datos de seguimiento de HAT, los datos de BAM también se escriben en la tabla TrackingData. Los datos descodificar servicio de seguimiento (TDDS, que se ejecuta en la instancia de host en el que el seguimiento está habilitado) es responsable de mover estos datos de la base de datos de cuadro de mensajes para las bases de datos de importación principal de BAM y de seguimiento de BizTalk. A continuación, una vez se haya movido correctamente los datos, TDDS elimina estos datos. Los datos de seguimiento de partes de mensaje los mueve por separado el trabajo TrackedMessages_Copy_BizTalkMsgBoxDb del Agente de SQL Server.  
  
 Si TDDS no puede mantener el ritmo en el que los interceptores escriben datos en la tabla TrackingData, esta tabla crece y provoca una limitación empezar. Esto afecta al rendimiento sostenible. Para reducir este problema, asegúrese de que se está ejecutando al menos un host con el seguimiento habilitado.  
  
 Si los datos siguen acumulándose, asegúrese de que la base de datos de seguimiento de BizTalk no crezca sin control. Además, asegúrese del archivado y purga el trabajo se está ejecutando y es capaz de hacer frente a la velocidad a la que llegan los datos.  
  
> [!NOTE]  
>  De forma predeterminada, el trabajo de purga no puede eliminar los datos de las tablas de base de datos de seguimiento de BizTalk hasta que estos datos se ha archivado. Si no necesita archivar los datos de seguimiento, puede modificar el trabajo para purgar la base de datos de seguimiento de BizTalk sin archivar siguiendo los pasos descritos en [cómo purgar datos de la base de datos de seguimiento de BizTalk](http://go.microsoft.com/fwlink/?LinkID=153817) (http://go.microsoft.com/fwlink/?LinkID=153817).  
  
## <a name="see-also"></a>Vea también  
 [Cuellos de botella en el nivel de base de datos](../technical-guides/bottlenecks-in-the-database-tier.md)