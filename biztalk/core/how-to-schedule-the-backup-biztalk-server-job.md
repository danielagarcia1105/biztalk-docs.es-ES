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
# <a name="how-to-schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="04b87-102">Cómo programar el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="04b87-102">How to Schedule the Backup BizTalk Server Job</span></span>
<span data-ttu-id="04b87-103">El trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ejecuta de acuerdo con lo programado mediante el servicio Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04b87-103">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs as scheduled by the SQL Server Agent service.</span></span> <span data-ttu-id="04b87-104">Si desea crear copias de seguridad con mayor o menor frecuencia, puede cambiar la programación del trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="04b87-104">If you want to create more frequent or less frequent backups, you can change the schedule of the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job by using SQL Server Management Studio.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="04b87-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="04b87-105">Prerequisites</span></span>  
 <span data-ttu-id="04b87-106">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04b87-106">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-schedule-the-backup-biztalk-server-job-sql-server-2008"></a><span data-ttu-id="04b87-107">Para programar el trabajo de copia de seguridad de BizTalk Server (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="04b87-107">To schedule the Backup BizTalk Server job (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="04b87-108">En el equipo que contiene la base de datos de administración de BizTalk, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **Microsoft SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="04b87-108">On the computer that contains the BizTalk Management database, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **Microsoft SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="04b87-109">En el **conectar al servidor** cuadro de diálogo, especifique el nombre del servidor SQL donde las bases de datos del servidor BizTalk Server residen y la autenticación apropiada escriba y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="04b87-109">In the **Connect to Server** dialog box, specify the name of the SQL Server where the BizTalk Server databases reside and the appropriate authentication type, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="04b87-110">En el Explorador de objetos, haga doble clic en **Agente SQL Server**y, a continuación, haga clic en **trabajos**.</span><span class="sxs-lookup"><span data-stu-id="04b87-110">In the Object Explorer, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="04b87-111">En el panel de detalles, haga clic en **copia de seguridad de BizTalk Server (BizTalkMgmtDb)**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="04b87-111">In the details pane, right-click **Backup BizTalk Server (BizTalkMgmtDb)**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="04b87-112">En el **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** cuadro de diálogo **seleccionar una página**, haga clic en **pasos**.</span><span class="sxs-lookup"><span data-stu-id="04b87-112">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="04b87-113">En el **lista de pasos de trabajo**, haga clic en **BackupFull**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="04b87-113">In the **Job step list**, click **BackupFull**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="04b87-114">En el **Job Step Properties - BackupFull** cuadro de diálogo, en la **comando** cuadro, edite el comando cambiando la frecuencia para el intervalo deseado en el que se va a realizar una copia de seguridad completa: **'h'** (cada hora), **tenía '** (diariamente), **'w'** (semanalmente), **'m '** (mensualmente), **'y'** (anualmente) y, a continuación, haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="04b87-114">In the **Job Step Properties - BackupFull** dialog box, in the **Command** box, edit the command by changing the frequency to the desired interval at which to perform a full backup: **'h'** (hourly), **'d'** (daily), **'w'** (weekly), **'m'** (monthly), **'y'** (yearly), and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04b87-115">La primera vez que se ejecuta el trabajo de copia de seguridad de BizTalk Server durante un nuevo periodo, se realiza una copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="04b87-115">The first time the Backup BizTalk Server job is run during a new period, a full backup is performed.</span></span>  
  
8.  <span data-ttu-id="04b87-116">En el **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** cuadro de diálogo **seleccionar una página**, haga clic en **programaciones**.</span><span class="sxs-lookup"><span data-stu-id="04b87-116">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** dialog box, under **Select a page**, click **Schedules**.</span></span>  
  
9. <span data-ttu-id="04b87-117">En el **lista de programaciones**, haga clic en **MarkAndBackupLogSched**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="04b87-117">In the **Schedule list**, click **MarkAndBackupLogSched**, and then click **Edit**.</span></span>  
  
10. <span data-ttu-id="04b87-118">En el **Job Schedule Properties - MarkAndBackupLogSched** cuadro de diálogo, en el tipo de programación, seleccione **periódica** en el cuadro de lista desplegable (si no está ya seleccionada).</span><span class="sxs-lookup"><span data-stu-id="04b87-118">In the **Job Schedule Properties - MarkAndBackupLogSched** dialog box, in Schedule type, select **Recurring** from the drop-down list box (if it is not already selected).</span></span>  
  
     <span data-ttu-id="04b87-119">De forma predeterminada, el trabajo está programado para ejecutarse cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="04b87-119">By default, the job is scheduled to run every 15 minutes.</span></span>  
  
11. <span data-ttu-id="04b87-120">Actualice la programación según corresponda y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="04b87-120">Update the schedule as desired, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04b87-121">Para obtener más información sobre la programación de trabajos del Agente SQL Server, vea "[programar un trabajo](http://go.microsoft.com/fwlink/?LinkId=195887)."</span><span class="sxs-lookup"><span data-stu-id="04b87-121">For more information about scheduling SQL Server Agent jobs, see "[Scheduling Jobs](http://go.microsoft.com/fwlink/?LinkId=195887)."</span></span>  
  
12. <span data-ttu-id="04b87-122">En el **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="04b87-122">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04b87-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="04b87-123">See Also</span></span>  
 <span data-ttu-id="04b87-124">[Cómo configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="04b87-124">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="04b87-125">[Cómo configurar el sistema de destino de trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="04b87-125">[How to Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 <span data-ttu-id="04b87-126">[Cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md) </span><span class="sxs-lookup"><span data-stu-id="04b87-126">[How to Restore Your Databases](../core/how-to-restore-your-databases.md) </span></span>  
 [<span data-ttu-id="04b87-127">Información avanzada sobre la copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="04b87-127">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)