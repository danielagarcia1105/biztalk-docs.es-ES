---
title: Mover las bases de datos de servidor BizTalk Server | Documentos de Microsoft
description: Pasos para mover las bases de datos de BizTalk Server a un nuevo servidor, incluidos detener los servicios y con los trabajos de agente SQL Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec302e6d-c89d-4fe7-849f-97b5566e8ba4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12bd1d6bc8a46d4e63dc69166d87f3678a0e3272
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254180"
---
# <a name="how-to-move-the-biztalk-server-databases"></a><span data-ttu-id="e5c16-103">Movimiento de bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5c16-103">How to Move the BizTalk Server Databases</span></span>

## <a name="overview"></a><span data-ttu-id="e5c16-104">Información general</span><span class="sxs-lookup"><span data-stu-id="e5c16-104">Overview</span></span>
<span data-ttu-id="e5c16-105">Este procedimiento se puede usar para mover las bases de datos principales de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a otro servidor</span><span class="sxs-lookup"><span data-stu-id="e5c16-105">You can use this procedure to move the primary [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases to another server.</span></span> <span data-ttu-id="e5c16-106">así como para mover las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] local a un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] remoto o a un clúster de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5c16-106">This same basic procedure can also be used to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases from a local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] to a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] or to a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="e5c16-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e5c16-107">Prerequisites</span></span>  
<span data-ttu-id="e5c16-108">Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] fijo servidor sysadmin para llevar a cabo este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e5c16-108">Sign in with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
## <a name="move-steps"></a><span data-ttu-id="e5c16-109">Pasos de movimiento</span><span class="sxs-lookup"><span data-stu-id="e5c16-109">Move steps</span></span>
  
1.  <span data-ttu-id="e5c16-110">Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5c16-110">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="e5c16-111">Para obtener más información, consulte [reiniciar los servicios de BizTalk Server y apagar el servidor BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="e5c16-111">For more information, see [Restart BizTalk Server Services, and shut down BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e5c16-112">Es importante asegurarse de que todos los servicios y trabajos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se han detenido antes de mover las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e5c16-112">It is critical to make sure that all the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services and jobs are stopped before you move the databases.</span></span>  
  
2.  <span data-ttu-id="e5c16-113">Detenga el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="e5c16-113">Stop the IIS service.</span></span>  
  
3.  <span data-ttu-id="e5c16-114">Detenga el servicio del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5c16-114">Stop the SQL Server Agent service.</span></span>  
  
4.  <span data-ttu-id="e5c16-115">Realizar copias de seguridad las bases de datos de BizTalk siguiendo los procedimientos de copia de seguridad de base de datos, como se describe en [copia de seguridad y restaurar las bases de datos de BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e5c16-115">Back up the BizTalk databases by following the database backup procedures as described at [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
5.  <span data-ttu-id="e5c16-116">Restauración en los procedimientos de restauración de las bases de datos de BizTalk en el nuevo servidor de la base de datos [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e5c16-116">Restore the BizTalk databases on the new server following the database restore procedures at [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span>  
  
6.  <span data-ttu-id="e5c16-117">Los trabajos del Agente SQL Server se enumeran a continuación para la transferencia al nuevo servidor, como se describe en el script [cómo realizar copias de seguridad y restaurar trabajos del Agente SQL](../core/how-to-back-up-and-restore-sql-agent-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e5c16-117">Script the SQL Server Agent jobs listed below for transfer to the new server, as described at [How to Back Up and Restore SQL Agent Jobs](../core/how-to-back-up-and-restore-sql-agent-jobs.md).</span></span>  <span data-ttu-id="e5c16-118">Ejecute cada uno de los scripts en el servidor nuevo para volver a crear los trabajos.</span><span class="sxs-lookup"><span data-stu-id="e5c16-118">Run each of the scripts on the new server to recreate the jobs.</span></span>  
  
     <span data-ttu-id="e5c16-119">Ejecute cada uno de los scripts en el servidor nuevo para volver a crear los trabajos.</span><span class="sxs-lookup"><span data-stu-id="e5c16-119">Run each of the scripts on the new server to recreate the jobs.</span></span> <span data-ttu-id="e5c16-120">Determinados trabajos, como el **copia de seguridad de BizTalk Server (BizTalkMsgBoxDb)** de trabajo, tendrá que volver a configurar a menos que las nuevas rutas de acceso de archivo de servidor y el nombre del servidor son idénticos al servidor anterior.</span><span class="sxs-lookup"><span data-stu-id="e5c16-120">Certain jobs, such as the **Backup BizTalk Server (BizTalkMsgBoxDb)** job, will have to be reconfigured unless the new server file paths and server name are identical to the old server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e5c16-121">También puede usar SSIS/DTS **transferir trabajos** de tareas para mover los trabajos al nuevo servidor, pero la mayoría de los usuarios probablemente resultará más fácil para generar un script los trabajos mediante SQL Management Studio.</span><span class="sxs-lookup"><span data-stu-id="e5c16-121">You can also use the SSIS/DTS **Transfer Jobs** task to move the jobs to the new server, but most users will probably find it easier to script the jobs using SQL Management Studio.</span></span>  
  
7.  <span data-ttu-id="e5c16-122">Además de generar scripts para trabajos de agente SQL Server como se describe en el paso anterior, deben crear scripts de inicios de sesión tal y como se describe en [cómo realizar copias de seguridad y restaurar el inicios de sesión de SQL Server](../core/how-to-back-up-and-restore-sql-server-logins.md).</span><span class="sxs-lookup"><span data-stu-id="e5c16-122">In addition to scripting SQL Server Agent jobs as described in the previous step, you must also script logins as described in [How to Back Up and Restore SQL Server Logins](../core/how-to-back-up-and-restore-sql-server-logins.md).</span></span> <span data-ttu-id="e5c16-123">Estos inicios de sesión deben restaurarse en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e5c16-123">These logins need to be restored on the destination server.</span></span>  
  
8.  <span data-ttu-id="e5c16-124">Restaurar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, siga los pasos del 9 al 22 de [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e5c16-124">Restore the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases by following steps 9 through 22 in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="e5c16-125">En este procedimiento se explica cómo actualizar el Registro y la base de datos de administración de BizTalk (BizTalkMgmtDb) con la nueva ubicación de bases de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e5c16-125">This procedure updates the BizTalk Management (BizTalkMgmtDb) database and registry with the new location of the BizTalk databases.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e5c16-126">En el **SampleUpdateInfo.xml** de archivos, convierta en comentario todas las bases de datos excepto a los que se ha movido al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="e5c16-126">In the **SampleUpdateInfo.xml** file, comment out all of the databases except for those you have moved to the new server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c16-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5c16-127">See Also</span></span>  
 [<span data-ttu-id="e5c16-128">Mover bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5c16-128">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)