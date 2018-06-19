---
title: Cómo identificar cuellos de botella en el cuadro de mensajes Database1 | Documentos de Microsoft
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
ms.openlocfilehash: b25a575f8cd6a3f7d7239ce20cb4d3befdde1966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297660"
---
# <a name="how-to-identify-bottlenecks-in-the-messagebox-database"></a>Cómo identificar cuellos de botella en la base de datos de cuadro de mensajes
Para identificar cuellos de botella en la base de datos de cuadro de mensajes, en primer lugar debe asegurarse de que se haya iniciado el servicio del Agente de SQL Server. Cambiar el estado de inicio del servicio de Manual a automático para que si se reinicia el servidor, el servicio se reiniciará automáticamente.  
  
 De forma predeterminada, el servicio de BizTalk limitar si el crecen de las tablas Spool, TrackingData o applicationq aumentan. Estas tablas se hayan eliminado por trabajos del agente de SQL, que, si no se está ejecutando hará que la cola de impresión aumente y provocará una limitación para iniciar y proteger la base de datos contra presiones adicionales. Compruebe el estado de los siguientes contadores de rendimiento:  
  
-   BizTalk:Agente de mensaje (nombre de host) Estado de limitación de entrega de mensajes  
  
-   BizTalk:Agente de mensaje (nombre de host) Estado de limitación de publicación de mensajes  
  
 Un valor de "0" indica que ninguna limitación se está produciendo. Un valor de "6" indica que el sistema está limitando a causa de crecimiento de la base de datos. Para obtener información sobre cómo interpretar los valores de estos contadores, vea [¿qué es la limitación de Host?](http://go.microsoft.com/fwlink/?LinkID=154694) (http://go.microsoft.com/fwlink/?LinkID=154694) y [contadores de rendimiento de limitación de Host](http://go.microsoft.com/fwlink/?LinkID=155285) (http://go.microsoft.com/fwlink/?LinkID=155285) en la documentación de BizTalk Server 2010.  
  
## <a name="spool-table-growth"></a>Crecimiento de la tabla de cola de impresión  
 La tabla Spool puede empezar a crecer por distintos motivos. Una razón para el crecimiento de la cola de impresión es si las colas de la aplicación está creciendo. Pudieron crecer por motivos como los cuellos de botella o contención de recursos.  
  
 Si las colas de aplicaciones son pequeñas y la cola de impresión sigue siendo muy grande, compruebe que los trabajos de purga se mantenerse al día. Asegúrese de que el servicio de Agente de SQL Server esté en ejecución y, a continuación, compruebe que los siguientes trabajos se estén realizando correctamente:  
  
-   MessageBox_Message_Cleanup_BizTalkMessageBoxDb  
  
-   MessageBox_Parts_Cleanup_BizTalkMessageBoxDb  
  
 Si la tabla MessageZeroSum es grande, indica que se ha procesado el mensaje. Esto significa que DeQueue ha completado correctamente y se eliminan los datos de las tablas de cola de la aplicación y las filas se han marcado para su eliminación. Sin embargo, los trabajos de purga no pueden eliminar los datos a la velocidad necesaria. Esto puede ocurrir si el equipo que ejecuta SQL Server esté experimentando grave contención de CPU, que afectan a la capacidad de los trabajos de purga para mantener el ritmo debido a la privación de la CPU.  
  
## <a name="application-queue-table-growth"></a>Crecimiento de tabla de cola de aplicación  
 Colas de la aplicación hospedan datos de transición en curso que, una vez procesados, son eliminados por DeQueue.  
  
 Después de procesan estos mensajes, puede limpiar la tabla de cola de impresión (que contiene referencias a estas filas).  
  
 Por ejemplo, la cola RxHostQ publica datos en la orquestación PxHostQ. Esta cola publica datos en el envío TxHostQ cada uno de los que hacen referencia a una fila en la tabla de cola de impresión. Una vez procesan correctamente los mensajes de una cola HostQ concreta a través del sistema, DeQueue elimina estas filas. Una vez eliminadas las filas, los trabajos de purga pueden borrar el contenido de la tabla Spool (a la que estas filas ya no hacen referencia).  
  
 Crecimiento de la cola de aplicación indica que las instancias de host responsables de purga de la cola de aplicación no se puede hacer frente a la velocidad de entrada.  
  
 Por ejemplo, la cola de aplicación de orquestación (PxHostQ) puede aumentar de tamaño porque el servidor responsable de procesar las orquestaciones está enlazado a la CPU y no puede procesar más rápidamente. No obstante, si el servidor de recepción es rápido puede publicar más rápido que la que el servidor puede procesar inicial para el crecimiento de la cola de la aplicación.  
  
 Otra razón para el crecimiento de la cola de orquestación podría ser debido a la contención de la memoria. Cuando varias instancias de orquestación que tardan en ejecutarse simultáneamente se crean instancias en memoria, inundación de memoria consecuencia indirecta de limitación reducir el grupo de subprocesos hasta que se libera la presión de memoria.  
  
 Un motivo por qué se puede alcanzar la cola de la aplicación de envío es si el sistema de nivel inferior no se pueden recibir mensajes (de salida desde BizTalk Server) lo suficientemente rápido. Por lo tanto, los mensajes continuará residiendo en el crecimiento de cola de la aplicación que producen de sistema de BizTalk. Esto puede provocar una limitación iniciar y reducir la velocidad de recepción afecta al rendimiento global del sistema.  
  
## <a name="trackingdata-table-growth"></a>Crecimiento de la tabla de seguimiento de datos  
 La tabla TrackingData en la base de datos de cuadro de mensajes es una tabla de transición en la que los interceptores escriben datos de seguimiento para el seguimiento de estado y actividad (HAT) y supervisión de la actividad económica (BAM). Si el seguimiento está deshabilitado, esta tabla debe estar vacía. De forma predeterminada, el seguimiento de HAT está habilitado para las canalizaciones y orquestaciones eventos de entrada/salida.  
  
 Si está habilitado el seguimiento de partes de mensaje, asegúrese de que se está ejecutando el servidor de base de datos de cuadro de mensajes (es decir, el host con "Permitir seguimiento de host"). Asegurarse de que se está ejecutando el host con "Permitir seguimiento de host" se reducirá la probabilidad de un cuello de botella que se produzca cuando el host pasa los datos de tabla TrackingData de la base de datos de cuadro de mensajes a las tablas de base de datos de seguimiento de BizTalk.  
  
 Es posible realizar el seguimiento de eventos personalizados habilitando el seguimiento de HAT personalizado, por ejemplo, en propiedades promocionadas y seguimiento de cuerpos de mensaje. Además de los datos de seguimiento de HAT, datos BAM también se escriben en la tabla TrackingData. Los datos descodificar servicio de seguimiento (TDDS, que se ejecuta en la instancia de host en el que el seguimiento está habilitado) es responsable de mover estos datos de la base de datos de cuadro de mensajes a las bases de datos de importación principal de BAM y de seguimiento de BizTalk. A continuación, después de que los datos se haya movido correctamente, TDDS elimina estos datos. Los datos de seguimiento de partes de mensaje los mueve por separado el trabajo TrackedMessages_Copy_BizTalkMsgBoxDb del Agente de SQL Server.  
  
 Si TDDS no puede hacer frente a la velocidad a la que los interceptores escriben datos en la tabla TrackingData, esta tabla crece y provoca una limitación empezar. Esto afecta al rendimiento sostenible. Para reducir este problema, asegúrese de que se ejecuta al menos un host con el seguimiento habilitado.  
  
 Si los datos siguen acumulándose, asegúrese de que la base de datos de seguimiento de BizTalk no crezca sin control. Además, asegúrese del archivado y purga de trabajo se está ejecutando y es capaz de hacer frente a la velocidad a la que llegan los datos.  
  
> [!NOTE]  
>  De forma predeterminada, el trabajo de purga es no se puede eliminar datos de las tablas de base de datos de seguimiento de BizTalk hasta que estos datos se han archivado. Si no es necesario archivar los datos de seguimiento, puede modificar el trabajo para purgar la base de datos de seguimiento de BizTalk sin archivar siguiendo los pasos descritos en [cómo purgar datos desde la base de datos de seguimiento de BizTalk](http://go.microsoft.com/fwlink/?LinkID=153817) (http://go.microsoft.com/ ¿fwlink /? LinkID = 153817).  
  
## <a name="see-also"></a>Vea también  
 [Cuellos de botella en el nivel de base de datos](../technical-guides/bottlenecks-in-the-database-tier.md)