---
title: "Cómo programar el trabajo de copia de seguridad de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, scheduling
- backing up, backup jobs
- scheduling, backup jobs
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d6b40ae933874e1c25cb3a93dbbeab514ef5dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-schedule-the-backup-biztalk-server-job"></a>Cómo programar el trabajo de copia de seguridad de BizTalk Server
El trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ejecuta de acuerdo con lo programado mediante el servicio Agente SQL Server. Si desea crear copias de seguridad con mayor o menor frecuencia, puede cambiar la programación del trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante SQL Server Management Studio.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.  
  
### <a name="to-schedule-the-backup-biztalk-server-job-sql-server-2008"></a>Para programar el trabajo de copia de seguridad de BizTalk Server (SQL Server 2008)  
  
1.  En el equipo que contiene la base de datos de administración de BizTalk, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **Microsoft SQL Server Management Studio**.  
  
2.  En el **conectar al servidor** cuadro de diálogo, especifique el nombre del servidor SQL donde las bases de datos del servidor BizTalk Server residen y la autenticación apropiada escriba y, a continuación, haga clic en **conectar**.  
  
3.  En el Explorador de objetos, haga doble clic en **Agente SQL Server**y, a continuación, haga clic en **trabajos**.  
  
4.  En el panel de detalles, haga clic en **copia de seguridad de BizTalk Server (BizTalkMgmtDb)**y, a continuación, haga clic en **propiedades**.  
  
5.  En el **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** cuadro de diálogo **seleccionar una página**, haga clic en **pasos**.  
  
6.  En el **lista de pasos de trabajo**, haga clic en **BackupFull**y, a continuación, haga clic en **editar**.  
  
7.  En el **Job Step Properties - BackupFull** cuadro de diálogo, en la **comando** cuadro, edite el comando cambiando la frecuencia para el intervalo deseado en el que se va a realizar una copia de seguridad completa: **'h'** (cada hora), **tenía '** (diariamente), **'w'** (semanalmente), **'m '** (mensualmente), **'y'** (anualmente) y, a continuación, haga clic en **Aceptar** .  
  
    > [!NOTE]
    >  La primera vez que se ejecuta el trabajo de copia de seguridad de BizTalk Server durante un nuevo periodo, se realiza una copia de seguridad completa.  
  
8.  En el **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** cuadro de diálogo **seleccionar una página**, haga clic en **programaciones**.  
  
9. En el **lista de programaciones**, haga clic en **MarkAndBackupLogSched**y, a continuación, haga clic en **editar**.  
  
10. En el **Job Schedule Properties - MarkAndBackupLogSched** cuadro de diálogo, en el tipo de programación, seleccione **periódica** en el cuadro de lista desplegable (si no está ya seleccionada).  
  
     De forma predeterminada, el trabajo está programado para ejecutarse cada 15 minutos.  
  
11. Actualice la programación según corresponda y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Para obtener más información sobre la programación de trabajos del Agente SQL Server, vea "[programar un trabajo](http://go.microsoft.com/fwlink/?LinkId=195887)."  
  
12. En el **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** cuadro de diálogo, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [Cómo configurar el sistema de destino de trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [Cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md)   
 [Información avanzada sobre la copia de seguridad y restauración](../core/advanced-information-about-backup-and-restore1.md)