---
title: Estructura y los trabajos de la base de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PurgeSubscriptionsJob_BizTalkMsgBoxDb job
- MessageBox database, jobs [SQL Server Agent]
- DTA Purge and Archive (BizTalkDTADb) job
- TrackedMessages_Copy_BizTalkMsgBoxDb job
- MessageBox_Message_Cleanup_BizTalkMsgBoxDb job
- MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job
- Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], MessageBox database
- CleanupBTFExpiredEntriesJob_BizTalkMgmtDb job
- databases, structure
- Tracking database, jobs [SQL Server Agent]
- jobs [SQL Server Agent], Management database
- Backup BizTalk Server (BizTalkMgmtDb) job
- databases, SQL Server Agent jobs
- Business Rules Engine, jobs [SQL Server Agent]
- jobs, databases
- Management database, jobs [SQL Server Agent]
- MessageBox_UpdateStats_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], Business Rules Engine
- Rules_Database_Cleanup_BizTalkRuleEngineDb job
- MessageBox_Parts_Cleanup_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], Tracking database
- MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb job
ms.assetid: f5f6b17d-0f5e-4821-a7eb-c345234ffc65
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf98ef7fe236261fd3ee65ac6f4695455ba8c704
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="database-structure-and-jobs"></a>Estructura de base de datos y trabajos
Este tema describe la estructura de base de datos y los trabajos de la base de datos para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="database-write-diagram"></a>Diagrama de escritura de base de datos  
 En la siguiente ilustración se muestran los procesos y entidades que escriben en las bases de datos de servidor BizTalk Server.  
  
 ![Procesos que se escriben en las bases de datos de BizTalk Server](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")  
  
        Database write diagram showing the processes and entities that write to the BizTalk Server databases  
  
## <a name="biztalk-server-database-jobs"></a>Trabajos de base de datos de servidor BizTalk Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye los siguientes trabajos del Agente SQL Server para ayudarle a administrar las bases de datos de BizTalk Server:  
  
> [!NOTE]
>  Los nombres de los trabajos varían en función de los nombres de base de datos proporcionados durante la configuración. Si ha implementado varias bases de datos de cuadro de mensajes en su entorno, dispondrá de varios trabajos para cada cuadro de mensajes.  
  
> [!WARNING]
>  En la base de datos de administración de BizTalk (BizTalkMgmtDb), hay un procedimiento almacenado denominado **adm_CleanupMgmtDB**. **NO EJECUTE ESTE PROCEDIMIENTO ALMACENADO.** Si lo ejecuta, se eliminarán todas las entradas de la base de datos.  
  
|Trabajo|Description|  
|---------|-----------------|  
|Copia de seguridad de BizTalk Server (BizTalkMgmtDb)|Este trabajo lleva a cabo todas las copias de seguridad de registros y bases de datos de las bases de datos de servidor BizTalk Server. Para obtener más información sobre cómo configurar y ejecutar este trabajo, consulte [copia de seguridad y restaurar bases de datos de servidor de BizTalk](../core/backing-up-and-restoring-biztalk-server-databases.md).|  
|CleanupBTFExpiredEntriesJob_BizTalkMgmtDb|Este trabajo limpia las entradas caducadas de BizTalk Framework (BTF) en la base de datos de administración de BizTalk (BizTalkMgmtDb).|  
|DTA Purge and Archive (BizTalkDTADb)|Este trabajo archiva de forma automática los datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb) y purga los datos que han quedado obsoletos. Para obtener más información sobre cómo configurar y ejecutar este trabajo, consulte [archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md).|  
|MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb|Este trabajo detecta cuando una instancia de host de BizTalk Server (servicio NT) se ha detenido y libera todo el trabajo que esta instancia estaba llevando a cabo para que pueda encargarse de él otra instancia de host.|  
|MessageBox_Message_Cleanup_BizTalkMsgBoxDb|Este trabajo quita todos los mensajes a los que ningún suscriptor hace referencia en las tablas de base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb). **Precaución:** se trata de un trabajo no programado que se inicia el trabajo MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb. No inicie este trabajo manualmente.|  
|MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb|Este trabajo administra los registros de cuenta de referencia de los mensajes y determina si existen mensajes a los que ningún suscriptor hace referencia. **Nota:** a pesar de este trabajo del Agente SQL Server está programado para ejecutarse una vez por minuto, el procedimiento almacenado que llama a este trabajo contiene la lógica para asegurarse de que el procedimiento almacenado se ejecuta continuamente. Este comportamiento se debe al diseño y no debe modificarse.|  
|MessageBox_Parts_Cleanup_BizTalkMsgBoxDb|Este trabajo quita todas las partes de mensaje a las que ningún mensaje hace referencia en las tablas de base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb). Todos los mensajes están compuestos por una o varias partes, que incluyen los datos del mensaje.|  
|MessageBox_UpdateStats_BizTalkMsgBoxDb|Este trabajo actualiza la estadística de la base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) de forma manual.|  
|Supervisar BizTalk Server|Este trabajo busca en las bases de datos BizTalkMgmtDb, BizTalkMsgBoxDb y BizTalkDTADb problemas conocidos como, por ejemplo, instancias huérfanas.|  
|Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb|Este trabajo es necesario en varias implementaciones de cuadro de mensajes. Realiza acciones de funcionamiento de forma asíncrona, como, por ejemplo, la finalización masiva en el cuadro de mensajes principal una vez que se han aplicado los cambios al cuadro de mensajes subordinado.|  
|PurgeSubscriptionsJob_BizTalkMsgBoxDb|Este trabajo purga los predicados de suscripción no utilizados de la base de datos de cuadro de mensajes de BizTalk Server (BizTalkMsgBoxDb).|  
|Rules_Database_Cleanup_BizTalkRuleEngineDb|Este trabajo purga automáticamente los datos de auditoría antiguos de la base de datos del motor de reglas (BizTalkRuleEngineDb) cada 90 días. Este trabajo también purga los datos de historial antiguos (notificaciones de implementación o de anulación de implementación) de la base de datos del motor de reglas (BizTalkRuleEngineDb) cada 3 días.|  
  
## <a name="see-also"></a>Vea también  
 [El motor de mensajería](../core/the-messaging-engine.md)