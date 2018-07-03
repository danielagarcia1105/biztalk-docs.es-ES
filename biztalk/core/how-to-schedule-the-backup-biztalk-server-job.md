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
# <a name="schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="ca59b-103">Programar el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ca59b-103">Schedule the Backup BizTalk Server Job</span></span>
<span data-ttu-id="ca59b-104">El trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ejecuta de acuerdo con lo programado mediante el servicio Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca59b-104">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs as scheduled by the SQL Server Agent service.</span></span> <span data-ttu-id="ca59b-105">Si desea crear copias de seguridad con mayor o menor frecuencia, puede cambiar la programación del trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="ca59b-105">If you want to create more frequent or less frequent backups, you can change the schedule of the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job by using SQL Server Management Studio.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ca59b-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ca59b-106">Prerequisites</span></span>  
<span data-ttu-id="ca59b-107">Inicie sesión con una cuenta que sea miembro del rol fijo de servidor de sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca59b-107">Sign in with an account that is a member of the SQL Server sysadmin fixed server role.</span></span>  
  
## <a name="schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="ca59b-108">Programar el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ca59b-108">Schedule the Backup BizTalk Server job</span></span>
  
1. <span data-ttu-id="ca59b-109">En SQL Server que hospeda la base de datos de administración de BizTalk, abra **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-109">On the SQL Server that hosts the BizTalk Management database, open **SQL Server Management Studio**.</span></span>

2. <span data-ttu-id="ca59b-110">En **conectar al servidor**, escriba el nombre del servidor SQL donde el servidor BizTalk Server que residen las bases de datos, seleccione el tipo de autenticación, y, a continuación, **Connect**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-110">In **Connect to Server**, enter the name of the SQL Server where the BizTalk Server databases reside, select the authentication type, and then **Connect**.</span></span>  
  
3. <span data-ttu-id="ca59b-111">En el Explorador de objetos, haga doble clic en **del Agente SQL Server**y, a continuación, seleccione **trabajos**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-111">In the Object Explorer, double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4. <span data-ttu-id="ca59b-112">En el panel de detalles, haga clic en **Backup BizTalk Server (BizTalkMgmtDb)** y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-112">In the details pane, right-click **Backup BizTalk Server (BizTalkMgmtDb)**, and then select **Properties**.</span></span>  
  
5. <span data-ttu-id="ca59b-113">En el **propiedades del trabajo - Backup BizTalk Server (BizTalkMgmtDb)**, en **seleccionar una página**, seleccione **pasos**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-113">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, under **Select a page**, select **Steps**.</span></span>  
  
6. <span data-ttu-id="ca59b-114">En el **lista de pasos de trabajo**, seleccione **BackupFull**y, a continuación, seleccione **editar**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-114">In the **Job step list**, select **BackupFull**, and then select **Edit**.</span></span>  
  
7. <span data-ttu-id="ca59b-115">En el **Job Step Properties – BackupFull**, en el **comando** cuadro, actualice el comando cambiando la frecuencia para ejecutar una copia de seguridad completa: **'h'** (cada hora), **tenía '**  (diariamente), **'w'** (semanalmente), **'m '** (mensualmente), **'y'** (anualmente).</span><span class="sxs-lookup"><span data-stu-id="ca59b-115">In the **Job Step Properties - BackupFull**, in the **Command** box, update the command by changing the frequency to run a full backup: **'h'** (hourly), **'d'** (daily), **'w'** (weekly), **'m'** (monthly), **'y'** (yearly).</span></span> <span data-ttu-id="ca59b-116">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-116">Select **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ca59b-117">La primera vez que se ejecuta el trabajo de copia de seguridad de BizTalk Server, complete una copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="ca59b-117">The first time the Backup BizTalk Server job runs, it completes a full backup.</span></span>  
    
8. <span data-ttu-id="ca59b-118">Configurar adicionales <strong>@frequency</strong> parámetros:</span><span class="sxs-lookup"><span data-stu-id="ca59b-118">Configure additional <strong>@frequency</strong> parameters:</span></span>  
  
   - <span data-ttu-id="ca59b-119"><strong>@ForceFullBackupAfterPartialSetFailure</strong>: El valor predeterminado es **false**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-119"><strong>@ForceFullBackupAfterPartialSetFailure</strong>: The default value is **false**.</span></span> <span data-ttu-id="ca59b-120">Cuando **false**, si la copia de seguridad completa se produce un error, el sistema esperará a que el siguiente ciclo hasta que se realiza la copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="ca59b-120">When **false**, if the full backup fails, the system waits for the next cycle until the full backup is made.</span></span>  
    
     > [!NOTE]
     >  <span data-ttu-id="ca59b-121">Si su <strong>@frequency</strong> configuración es largo (por ejemplo, semanal, mensual, anual), a continuación, establecer este parámetro en **false** podría ser peligroso.</span><span class="sxs-lookup"><span data-stu-id="ca59b-121">If your <strong>@frequency</strong> setting is long (like weekly, monthly, yearly), then setting this parameter to **false** could be dangerous.</span></span> <span data-ttu-id="ca59b-122">En este escenario, puede ser preferible establecer esta marca en **true**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-122">In this scenario, it may be best to set this flag to **true**.</span></span> <span data-ttu-id="ca59b-123">Cuando **true**, cada vez hay un error, el sistema fuerza para crear una copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="ca59b-123">When **true**, every time there is a failure, the system forces itself to create a full backup.</span></span> <span data-ttu-id="ca59b-124">Puede haber un impacto en el rendimiento pequeñas, pero es safter tengan un sistema recuperable.</span><span class="sxs-lookup"><span data-stu-id="ca59b-124">There may be a small performance impact, but it’s safter to have a recoverable system.</span></span>
  
   - <span data-ttu-id="ca59b-125"><strong>@BackupHour</strong>: El valor predeterminado es NULL.</span><span class="sxs-lookup"><span data-stu-id="ca59b-125"><strong>@BackupHour</strong>: The default valueis NULL.</span></span> <span data-ttu-id="ca59b-126">Este parámetro está directamente relacionado con <strong>@Frequency</strong>.</span><span class="sxs-lookup"><span data-stu-id="ca59b-126">This parameter is directly related to <strong>@Frequency</strong>.</span></span> <span data-ttu-id="ca59b-127">Al establecer la frecuencia **h** (cada hora), se establece qué hora del día que desee ejecutar la copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="ca59b-127">When you set the frequency to **h** (hourly), you set which hour of the day you want the full backup to run.</span></span> <span data-ttu-id="ca59b-128">Puede elegir un valor entre 0 (medianoche) a 23 (11 PM).</span><span class="sxs-lookup"><span data-stu-id="ca59b-128">You can choose a value between 0 (midnight) to 23 (11 PM).</span></span> <span data-ttu-id="ca59b-129">Si se deja en blanco, la copia de seguridad completa ejecuta cada hora.</span><span class="sxs-lookup"><span data-stu-id="ca59b-129">If left blank, the full backup runs every hour.</span></span>  
    
      > [!NOTE]
       >  <span data-ttu-id="ca59b-130">Si establece este parámetro con un número fuera del intervalo de 0 a 23 (por ejemplo, 100 o -1), el sistema convierte en 0.</span><span class="sxs-lookup"><span data-stu-id="ca59b-130">If you set this parameter with a number outside the 0 to 23 range (for example, 100 or -1), the system forces it to 0.</span></span>
  
   - <span data-ttu-id="ca59b-131"><strong>@UseLocalTime</strong>: Un parámetro adicional que se indica para usar la hora local.</span><span class="sxs-lookup"><span data-stu-id="ca59b-131"><strong>@UseLocalTime</strong>: An extra parameter that states to use local time.</span></span> <span data-ttu-id="ca59b-132">De forma predeterminada, el trabajo funciona con la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="ca59b-132">By default, the job works with UTC time.</span></span> <span data-ttu-id="ca59b-133">Por lo que si vive en Australia (que es UTC + 10 horas), la copia de seguridad se ejecuta en 10 am en lugar de a medianoche.</span><span class="sxs-lookup"><span data-stu-id="ca59b-133">So if you live in Australia (which is UTC + 10 hours), your backup runs at 10am rather than midnight.</span></span> <span data-ttu-id="ca59b-134">Como práctica recomendada, se recomienda establecerlo en **1** (true).</span><span class="sxs-lookup"><span data-stu-id="ca59b-134">As a best practice, it is recommended to set this to **1** (true).</span></span>  
  
9. <span data-ttu-id="ca59b-135">En el **propiedades del trabajo - Backup BizTalk Server (BizTalkMgmtDb)**, en **seleccionar una página**, haga clic en **programaciones**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-135">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, under **Select a page**, click **Schedules**.</span></span>  
  
10. <span data-ttu-id="ca59b-136">En el **lista de programaciones**, haga clic en **MarkAndBackupLogSched**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-136">In the **Schedule list**, click **MarkAndBackupLogSched**, and then click **Edit**.</span></span>  
  
11. <span data-ttu-id="ca59b-137">En el **Job Schedule Properties - MarkAndBackupLogSched**, en el tipo de programación, seleccione **periódica** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ca59b-137">In the **Job Schedule Properties - MarkAndBackupLogSched**, in Schedule type, select **Recurring** from the drop-down list.</span></span>  
  
     <span data-ttu-id="ca59b-138">De forma predeterminada, el trabajo está programado para ejecutarse cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="ca59b-138">By default, the job is scheduled to run every 15 minutes.</span></span>  
     
    > [!NOTE]
    >  <span data-ttu-id="ca59b-139">Puede cambiar este valor según sus requisitos, pero primera prueba en el entorno que no sea de producción.</span><span class="sxs-lookup"><span data-stu-id="ca59b-139">You can change this value according to your requirements, but first test in non-production environment.</span></span> <span data-ttu-id="ca59b-140">Al establecer este valor demasiado bajos resultados en copias de seguridad frecuentes y lo agrega a la carga en segundo plano en su entorno de SQL.</span><span class="sxs-lookup"><span data-stu-id="ca59b-140">Setting this value too low results in frequent backups, and adds to the background load in your SQL environment.</span></span> <span data-ttu-id="ca59b-141">Al establecer este valor demasiado alto puede aumentar el tamaño de los registros de transacciones y afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ca59b-141">Setting this value too high may increase the size of transaction logs, and impact performance.</span></span> <span data-ttu-id="ca59b-142">En algunas situaciones, se recomienda dejar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ca59b-142">In some situations, it is recommended to leave the default value.</span></span>    
  
12. <span data-ttu-id="ca59b-143">Actualice la programación si lo desea y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-143">Update the schedule if desired, and then select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca59b-144">[Programación de trabajos](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job) proporciona más detalles.</span><span class="sxs-lookup"><span data-stu-id="ca59b-144">[Scheduling Jobs](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job) provides more details.</span></span>
  
13. <span data-ttu-id="ca59b-145">En el **propiedades del trabajo - Backup BizTalk Server (BizTalkMgmtDb)**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca59b-145">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, click **OK**.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="ca59b-146">Otros recursos útiles</span><span class="sxs-lookup"><span data-stu-id="ca59b-146">More good stuff</span></span>  
 <span data-ttu-id="ca59b-147">[Configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="ca59b-147">[Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="ca59b-148">[Configurar el sistema de destino del trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="ca59b-148">[Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 <span data-ttu-id="ca59b-149">[Restaurar las bases de datos](../core/how-to-restore-your-databases.md) </span><span class="sxs-lookup"><span data-stu-id="ca59b-149">[Restore Your Databases](../core/how-to-restore-your-databases.md) </span></span>  
 [<span data-ttu-id="ca59b-150">Información avanzada sobre copias de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="ca59b-150">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)
