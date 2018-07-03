---
title: Cómo identificar cuellos de botella en la base de datos2 del cuadro de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b2eb1e-541c-457d-9735-ac6fb069b209
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffc04f31544a48f0ab25338c95beefaf14d5097c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010629"
---
# <a name="how-to-identify-bottlenecks-in-the-messagebox-database"></a>Cómo identificar cuellos de botella en la base de datos de cuadro de mensajes
Para identificar cuellos de botella en la base de datos de cuadro de mensajes, en primer lugar debe asegurarse de que se haya iniciado el servicio del Agente de SQL Server. Cambie el estado de inicio del servicio de manual a automático, de modo que el servicio se reinicie automáticamente aunque se reinicie el servidor.  
  
 De manera predeterminada, el servicio de BizTalk se limita si las tablas Spool, TrackingData o ApplicationQ aumentan de tamaño. Los trabajos del Agente de SQL purgan estas tablas, de manera que, si éste no se ejecuta, la cola de impresión aumentará de tamaño y provocará una limitación para proteger la base de datos contra presiones adicionales. Compruebe el estado de los siguientes contadores de rendimiento:  
  
- BizTalk:Agente de mensaje (nombre de host) Estado de limitación de entrega de mensajes  
  
- BizTalk:Agente de mensaje (nombre de host) Estado de limitación de publicación de mensajes  
  
  Un valor de 0 indica que no se está produciendo ninguna limitación. El valor 6 indica que el sistema se está limitando a causa del crecimiento de la base de datos. Vea la documentación para obtener información sobre cómo interpretar los demás valores de estos contadores.  
  
## <a name="spool-table-growth"></a>Crecimiento de la tabla Spool  
 La tabla Spool puede empezar a crecer por distintos motivos. Uno de estos motivos es que aumenten de tamaño las colas de aplicaciones. Éstas, a su vez, pueden crecer por diversas razones, como cuellos de botella o contención de recursos en niveles inferiores.  
  
 Si las colas de aplicaciones son pequeñas y el tamaño de la tabla Spool se mantiene elevado, compruebe que los trabajos de purga estén funcionando al ritmo preciso. Asegúrese de que el servicio de Agente de SQL Server esté en ejecución y, a continuación, compruebe que los siguientes trabajos se estén realizando correctamente:  
  
- MessageBox_Message_Cleanup_BizTalkMessageBoxDb  
  
- MessageBox_Parts_Cleanup_BizTalkMessageBoxDb  
  
  Si la tabla MessageZeroSum es grande, indica que los mensajes se han procesado (DeQueue se ha ejecutado correctamente y ha eliminado los datos de las tablas de colas de aplicaciones) y las filas se han marcado para su eliminación. Sin embargo, los trabajos de purga no pueden eliminar los datos a la velocidad necesaria. Un motivo de ello puede ser que el equipo de SQL Server esté experimentando una contención grave de la CPU, lo que afecta a la capacidad de los trabajos de purga para funcionar al ritmo apropiado a causa de la privación de la CPU.  
  
## <a name="application-queue-table-growth"></a>Crecimiento de la tabla de colas de aplicaciones  
 Las colas de aplicaciones alojan datos de transición en curso que, una vez procesados, son eliminados por DeQueue.  
  
 Después de procesar estos mensajes, se puede borrar el contenido de la tabla Spool (que contiene referencias a estas filas).  
  
 Por ejemplo, la cola RxHostQ publica datos en la cola PxHostQ de la orquestación que, a su vez, publica datos en la cola TxHostQ de envío, y cada uno de ellas hace referencia a una fila de la tabla Spool. Una vez procesados correctamente los mensajes correspondientes a una cola HostQ concreta a través del sistema, DeQueue elimina estas filas. Una vez eliminadas las filas, los trabajos de purga pueden borrar el contenido de la tabla Spool (a la que estas filas ya no hacen referencia).  
  
 El crecimiento de la cola de aplicaciones ApplicationQ indica que las instancias de host responsables de purgarla no consiguen mantener el ritmo de entrada; es decir, la velocidad a la que se publican los mensajes en una cola de aplicación concreta.  
  
 Por ejemplo, la cola de aplicación de orquestación (PxHostQ) puede aumentar de tamaño porque el servidor responsable de procesar las orquestaciones está enlazado a la CPU y no puede procesar más rápidamente. No obstante, si el servidor de recepción es rápido, podría publicar a más velocidad de la que el servidor es capaz procesar, lo que da como resultado el crecimiento de la cola de aplicaciones.  
  
 Otra razón de que aumente el tamaño de la cola de orquestaciones puede ser la contención de memoria, que hace que se creen en la memoria muchas instancias de orquestaciones de larga ejecución, lo que provoca una inundación de la memoria. Esto, indirectamente, hace que la limitación reduzca el grupo de subprocesos hasta que disminuya la presión ejercida sobre la memoria. Una razón por la que puede crecer la cola de aplicaciones de envío es que el sistema de nivel inferior no pueda recibir mensajes (de salida desde BizTalk) con la suficiente rapidez. En este caso, los mensajes siguen residiendo en el sistema de BizTalk, lo que provoca el crecimiento de la cola de aplicaciones. Esto, en definitiva, provocará una limitación que, a su vez, dará lugar a una reducción de la velocidad de recepción que afectará al rendimiento global del sistema.  
  
## <a name="trackingdata-table-growth"></a>Crecimiento de la tabla TrackingData  
 La tabla TrackingData de la base de datos de cuadro de mensajes es una tabla de transición en la que los interceptores escriben datos de seguimiento para el seguimiento de instancias de mensajes y servicios, y el seguimiento de BAM. Si el seguimiento está deshabilitado, esta tabla debe estar vacía. De manera predeterminada, el seguimiento de instancias de mensajes y servicios está habilitado para los eventos de entrada y salida de las canalizaciones y orquestaciones.  
  
 Si está habilitado el seguimiento de partes de mensaje, asegúrese de que esté en ejecución el servidor del cuadro de mensajes (es decir, el host donde se activó "Permitir seguimiento de host"). Reducirá el cuello de botella, ya que transfiere datos de la tabla TrackingData de la base de datos de cuadro de mensajes a las tablas BizTalkDTADb.  
  
 Es posible realizar el seguimiento de los eventos personalizados si se habilita el seguimiento de instancias de mensajes y servicios, por ejemplo, en las propiedades promocionadas y el seguimiento de partes de mensaje. Además de los datos de seguimiento, en esta tabla también se escriben los datos de BAM. Es responsabilidad de TDDS (el host en que está habilitado el seguimiento) transferir estos datos de la base de datos de cuadro de mensajes a las bases de datos BizTalkDTADb y BAMPrimaryImport, y, una vez transferidos correctamente, eliminarlos. Los datos de seguimiento de partes de mensaje los mueve por separado el trabajo TrackedMessages_Copy_BizTalkMsgBoxDb del Agente de SQL Server.  
  
 Si TDDS no puede mantener el ritmo al que los interceptores escriben datos en la tabla TrackingData, esta tabla crece y provoca una limitación, lo que en definitiva afecta al rendimiento sostenible. Para aliviar este problema, asegúrese de que haya al menos 1 host en ejecución con el seguimiento habilitado.  
  
 Si los datos siguen acumulándose, compruebe la base de datos BizTalkDTADb para asegurarse de que no crezca sin control. Asegúrese asimismo de que se esté ejecutando el trabajo de archivo y purga, y de consigue hacerlo a la velocidad a la que llegan los datos.  
  
> [!NOTE]
>  El trabajo de purga no puede eliminar datos de las tablas de BizTalkDTADb hasta que éstos se han archivado.  
  
 Compruebe que la tabla TrackingData no crece. Asegúrese de que el seguimiento esté habilitado (TDDS) al menos en una instancia de host que esté en ejecución. Si el tamaño de la base de datos BizTalkDTADb es excesivo, puede afectar de manera negativa a la capacidad de TDDS para transferir los datos desde la base de datos de cuadro de mensajes a la base de datos BizTalkDTADb.  
  
 El crecimiento de la tabla TrackingData puede provocar una limitación, lo que afectará al rendimiento sostenible en tiempo de ejecución.