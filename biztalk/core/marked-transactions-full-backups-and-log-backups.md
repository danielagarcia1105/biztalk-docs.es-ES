---
title: Transacciones marcadas, copias de seguridad completas y diferenciales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, transaction logs
- backing up, full backups
- transaction logs
- backing up, backup jobs
ms.assetid: a383a16d-1e40-4b0b-a515-f1cb90bfb4d2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff71cbe7eb910c66530dee3264822eae121c0ce2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973594"
---
# <a name="marked-transactions-full-backups-and-log-backups"></a>Copias de seguridad de registros, copias de seguridad completas y transacciones marcadas
El trabajo de copia de seguridad de BizTalk Server crea copias de seguridad sincronizadas de todas las bases de datos de BizTalk Server mediante el uso de las copias de seguridad completa de la base de datos y copias de seguridad de registro de transacciones, junto con un tipo de transacción que se conoce como un *transacción marcada*. Las transacciones marcadas son transacciones que colocan una marca en el registro de transacciones de todas las bases de datos que participan en la transacción. La transacción marcada bloquea el inicio de nuevas transacciones distribuidas, espera a que se completen las transacciones distribuidas que están actualmente en ejecución y, seguidamente, efectúa la ejecución para colocar la marca.  
  
 La marca representa un punto de transacción coherente en todas las bases de datos y que puede utilizarse con sucesivas copias de seguridad de registros para restaurar las bases de datos en ese punto.  
  
 Para cada una de las bases de datos de BizTalk Server, el trabajo de copia de seguridad de BizTalk Server crea una copia de seguridad de registros de transacciones marcada cada vez que se ejecuta; asimismo, crea una copia de seguridad completa en función de un periodo especificado.  
  
## <a name="full-backups"></a>Copias de seguridad completas  
 Cuando se ejecuta el trabajo de copia de seguridad de BizTalk Server ejecuta el primer proceso de copia de seguridad, *BackupFull*, una vez cada periodo (y no cada vez que se ejecuta el trabajo). Para obtener más información sobre cómo programar el trabajo de copia de seguridad de BizTalk Server, vea [cómo programar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-schedule-the-backup-biztalk-server-job.md).  
  
 La primera vez que se ejecuta el trabajo de copia de seguridad de BizTalk Server durante un nuevo periodo, lleva a cabo una copia de seguridad completa. Por ejemplo, si programa el trabajo para que se ejecute una vez cada hora, pero configura el periodo como diario, el trabajo de copia de seguridad de BizTalk Server efectúa una copia de seguridad la primera vez que se ejecuta y, posteriormente, una vez al día (a medianoche).  
  
## <a name="transaction-log-backups"></a>Copias de seguridad del registro de transacciones  
 Es el segundo proceso que realiza el trabajo de copia de seguridad de BizTalk Server *MarkAndBackupLog*. Este proceso coloca una marca en todas las bases de datos de BizTalk Server y realiza una copia de seguridad de registros de transacciones cada vez que se ejecuta el trabajo.  
  
 La marca es la cadena creada mediante el uso de  *\<ServerName\>*_*\<DatabaseName\>*_Log\_  *\<LogMarkName\>*\_*\<Timestamp\>*.bak, donde el  *\<nombre de la marca de registro\>*  está configurado en el trabajo del Agente SQL Server. Esta marca se debe utilizar al restaurar el último registro en cada base de datos.  
  
 Para obtener más información, vea las secciones que tratan de las copias de seguridad de registros de transacciones, y de la copia de seguridad de las bases de datos relacionadas y de su restauración, en los Libros en pantalla de SQL Server.  
  
## <a name="see-also"></a>Vea también  
 [Información avanzada sobre copias de seguridad y restauración](../core/advanced-information-about-backup-and-restore1.md)