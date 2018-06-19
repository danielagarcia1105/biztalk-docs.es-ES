---
title: Programar el trabajo de copia de seguridad de BizTalk Server | Documentos de Microsoft
description: Configurar los parámetros del trabajo de copia de seguridad de BizTalk Server y establezca la programación en ejecución mensual, semanal, diariamente o cada hora
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
ms.openlocfilehash: 7f09ca97f65605ac3bf427d1c1fcc322a14feb53
ms.sourcegitcommit: 9aaed443492b74729171fef79c634bff561af929
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2017
ms.locfileid: "23980756"
---
# <a name="schedule-the-backup-biztalk-server-job"></a>Programar el trabajo de copia de seguridad de BizTalk Server
El trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ejecuta de acuerdo con lo programado mediante el servicio Agente SQL Server. Si desea crear copias de seguridad con mayor o menor frecuencia, puede cambiar la programación del trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante SQL Server Management Studio.  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro del rol sysadmin de SQL Server rol fijo de servidor.  
  
## <a name="schedule-the-backup-biztalk-server-job"></a>Programar el trabajo de copia de seguridad de BizTalk Server
  
1.  En el servidor SQL Server que hospeda la base de datos de administración de BizTalk, abra **SQL Server Management Studio**.

2.  En **conectar al servidor**, escriba el nombre del servidor SQL donde el servidor BizTalk Server que residen las bases de datos, seleccione el tipo de autenticación, y, a continuación, **conectar**.  
  
3.  En el Explorador de objetos, haga doble clic en **Agente SQL Server**y, a continuación, seleccione **trabajos**.  
  
4.  En el panel de detalles, haga clic en **copia de seguridad de BizTalk Server (BizTalkMgmtDb)** y, a continuación, seleccione **propiedades**.  
  
5.  En el **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, en **seleccionar una página**, seleccione **pasos**.  
  
6.  En el **lista de pasos de trabajo**, seleccione **BackupFull**y, a continuación, seleccione **editar**.  
  
7.  En el **Job Step Properties - BackupFull**, en la **comando** cuadro, actualice el comando cambiando la frecuencia para ejecutar una copia de seguridad completa: **'h'** (cada hora), **tenía '**  (diariamente), **'w'** (semanalmente), **'m '** (mensualmente), **'y'** (anualmente). Seleccione **Aceptar**.  
  
    > [!NOTE]
    >  La primera vez que se ejecuta el trabajo de copia de seguridad de BizTalk Server, se completa una copia de seguridad completa.  
    
8.  Configurar adicionales  **@frequency**  parámetros:  
  
    - **@ForceFullBackupAfterPartialSetFailure**: El valor predeterminado es **false**. Cuando **false**, si la copia de seguridad completa se produce un error, el sistema esperará a que el siguiente ciclo hasta que se realiza la copia de seguridad completa.  
    
        > [!NOTE]
        >  Si su  **@frequency**  configuración es larga (por ejemplo, semanal, mensual, anual), a continuación, establecer este parámetro en **false** puede ser peligroso. En este escenario, puede ser preferible establecer esta marca en **true**. Cuando **true**, cada vez que hay un error, el sistema fuerza automáticamente para crear una copia de seguridad completa. Puede haber un impacto de rendimiento de pequeñas, pero es safter para que un sistema recuperable.
  
    - **@BackupHour**: Es de valor predeterminado es NULL. Este parámetro está directamente relacionado con  **@Frequency** . Cuando se establece la frecuencia en **h** (cada hora), establecer qué hora del día que desee ejecutar la copia de seguridad completa. Puede elegir un valor entre 0 (medianoche) a 23 (11 P.M.). Si se deja en blanco, la copia de seguridad ejecuta cada hora.  
    
       > [!NOTE]
        >  Si establece este parámetro con un número que está fuera del intervalo de 0 a 23 (por ejemplo, 100 o -1), el sistema convierte en 0.
  
    - **@UseLocalTime**: Un parámetro adicional que se indica para usar la hora local. De forma predeterminada, el trabajo funciona con la hora UTC. Por lo que si vive en Australia (que es UTC + 10 horas), la copia de seguridad se ejecuta en 10 am en lugar de medianoche. Como práctica recomendada, se recomienda establecerlo en **1** (true).  
  
9.  En el **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, en **seleccionar una página**, haga clic en **programaciones**.  
  
10. En el **lista de programaciones**, haga clic en **MarkAndBackupLogSched**y, a continuación, haga clic en **editar**.  
  
11. En el **Job Schedule Properties - MarkAndBackupLogSched**, en el tipo de programación, seleccione **periódica** en la lista desplegable.  
  
     De forma predeterminada, el trabajo está programado para ejecutarse cada 15 minutos.  
     
    > [!NOTE]
    >  Puede cambiar este valor según los requisitos, pero la primera prueba en entornos de no producción. Establecer este valor demasiado bajos resultados en copias de seguridad frecuentes y lo agrega a la carga en segundo plano en el entorno de SQL. Al establecer este valor demasiado alto puede aumentar el tamaño de los registros de transacciones y afectar al rendimiento. En algunas situaciones, se recomienda dejar el valor predeterminado.    
  
12. Actualice la programación si lo desea y, a continuación, seleccione **Aceptar**.  
  
    > [!NOTE]
    >  [Programar trabajos](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job) proporcionan más detalles.
  
13. En el **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, haga clic en **Aceptar**.  
  
## <a name="more-good-stuff"></a>Otros recursos útiles  
 [Configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [Configurar el sistema de destino de trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [Restaurar las bases de datos](../core/how-to-restore-your-databases.md)   
 [Información avanzada sobre copias de seguridad y restauración](../core/advanced-information-about-backup-and-restore1.md)
