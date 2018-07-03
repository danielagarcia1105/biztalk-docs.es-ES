---
title: Programar el trabajo de copia de seguridad de BizTalk Server | Microsoft Docs
description: Configurar los parámetros del trabajo de copia de seguridad de BizTalk Server y establézcalo en la programación por hora, diaria, semanal o mensualmente ejecución
ms.custom: ''
ms.date: 11/02/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83dd415648c55b53a9212ce20f4b1f754fb4fbb6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005133"
---
# <a name="schedule-the-backup-biztalk-server-job"></a>Programar el trabajo de copia de seguridad de BizTalk Server
El trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ejecuta de acuerdo con lo programado mediante el servicio Agente SQL Server. Si desea crear copias de seguridad con mayor o menor frecuencia, puede cambiar la programación del trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante SQL Server Management Studio.  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro del rol fijo de servidor de sysadmin de SQL Server.  
  
## <a name="schedule-the-backup-biztalk-server-job"></a>Programar el trabajo de copia de seguridad de BizTalk Server
  
1. En SQL Server que hospeda la base de datos de administración de BizTalk, abra **SQL Server Management Studio**.

2. En **conectar al servidor**, escriba el nombre del servidor SQL donde el servidor BizTalk Server que residen las bases de datos, seleccione el tipo de autenticación, y, a continuación, **Connect**.  
  
3. En el Explorador de objetos, haga doble clic en **del Agente SQL Server**y, a continuación, seleccione **trabajos**.  
  
4. En el panel de detalles, haga clic en **Backup BizTalk Server (BizTalkMgmtDb)** y, a continuación, seleccione **propiedades**.  
  
5. En el **propiedades del trabajo - Backup BizTalk Server (BizTalkMgmtDb)**, en **seleccionar una página**, seleccione **pasos**.  
  
6. En el **lista de pasos de trabajo**, seleccione **BackupFull**y, a continuación, seleccione **editar**.  
  
7. En el **Job Step Properties – BackupFull**, en el **comando** cuadro, actualice el comando cambiando la frecuencia para ejecutar una copia de seguridad completa: **'h'** (cada hora), **tenía '**  (diariamente), **'w'** (semanalmente), **'m '** (mensualmente), **'y'** (anualmente). Seleccione **Aceptar**.  
  
   > [!NOTE]
   >  La primera vez que se ejecuta el trabajo de copia de seguridad de BizTalk Server, complete una copia de seguridad completa.  
    
8. Configurar adicionales <strong>@frequency</strong> parámetros:  
  
   - <strong>@ForceFullBackupAfterPartialSetFailure</strong>: El valor predeterminado es **false**. Cuando **false**, si la copia de seguridad completa se produce un error, el sistema esperará a que el siguiente ciclo hasta que se realiza la copia de seguridad completa.  
    
     > [!NOTE]
     >  Si su <strong>@frequency</strong> configuración es largo (por ejemplo, semanal, mensual, anual), a continuación, establecer este parámetro en **false** podría ser peligroso. En este escenario, puede ser preferible establecer esta marca en **true**. Cuando **true**, cada vez hay un error, el sistema fuerza para crear una copia de seguridad completa. Puede haber un impacto en el rendimiento pequeñas, pero es safter tengan un sistema recuperable.
  
   - <strong>@BackupHour</strong>: El valor predeterminado es NULL. Este parámetro está directamente relacionado con <strong>@Frequency</strong>. Al establecer la frecuencia **h** (cada hora), se establece qué hora del día que desee ejecutar la copia de seguridad completa. Puede elegir un valor entre 0 (medianoche) a 23 (11 PM). Si se deja en blanco, la copia de seguridad completa ejecuta cada hora.  
    
      > [!NOTE]
       >  Si establece este parámetro con un número fuera del intervalo de 0 a 23 (por ejemplo, 100 o -1), el sistema convierte en 0.
  
   - <strong>@UseLocalTime</strong>: Un parámetro adicional que se indica para usar la hora local. De forma predeterminada, el trabajo funciona con la hora UTC. Por lo que si vive en Australia (que es UTC + 10 horas), la copia de seguridad se ejecuta en 10 am en lugar de a medianoche. Como práctica recomendada, se recomienda establecerlo en **1** (true).  
  
9. En el **propiedades del trabajo - Backup BizTalk Server (BizTalkMgmtDb)**, en **seleccionar una página**, haga clic en **programaciones**.  
  
10. En el **lista de programaciones**, haga clic en **MarkAndBackupLogSched**y, a continuación, haga clic en **editar**.  
  
11. En el **Job Schedule Properties - MarkAndBackupLogSched**, en el tipo de programación, seleccione **periódica** en la lista desplegable.  
  
     De forma predeterminada, el trabajo está programado para ejecutarse cada 15 minutos.  
     
    > [!NOTE]
    >  Puede cambiar este valor según sus requisitos, pero primera prueba en el entorno que no sea de producción. Al establecer este valor demasiado bajos resultados en copias de seguridad frecuentes y lo agrega a la carga en segundo plano en su entorno de SQL. Al establecer este valor demasiado alto puede aumentar el tamaño de los registros de transacciones y afectar al rendimiento. En algunas situaciones, se recomienda dejar el valor predeterminado.    
  
12. Actualice la programación si lo desea y, a continuación, seleccione **Aceptar**.  
  
    > [!NOTE]
    >  [Programación de trabajos](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job) proporciona más detalles.
  
13. En el **propiedades del trabajo - Backup BizTalk Server (BizTalkMgmtDb)**, haga clic en **Aceptar**.  
  
## <a name="more-good-stuff"></a>Otros recursos útiles  
 [Configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [Configurar el sistema de destino del trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [Restaurar las bases de datos](../core/how-to-restore-your-databases.md)   
 [Información avanzada sobre copias de seguridad y restauración](../core/advanced-information-about-backup-and-restore1.md)
