---
title: "Cómo purgar datos de la base de datos de seguimiento de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging
- DTA Purge and Archive job, purging data
- purging, DTA Purge and Archive job
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c56629aaa0934010ba79637b4e4a134bf29f26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="5ffec-102">Cómo purgar datos de la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="5ffec-102">How to Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="5ffec-103">Cuando se purgan datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb), el trabajo DTA Purge and Archive se encarga de purgar de la base de datos de seguimiento de BizTalk (BizTalkDTADb) diversos tipos de información de seguimiento como, por ejemplo, información de instancia de servicio y mensaje, información de eventos de orquestación y datos de seguimiento del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="5ffec-103">When you purge data from the BizTalk Tracking (BizTalkDTADb) database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5ffec-104">La base de datos seguimiento de BizTalk (BizTalkDTADb) no se archiva mediante este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5ffec-104">The BizTalk Tracking (BizTalkDTADb) database is not archived using this procedure.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5ffec-105">Cuando se captura y se controla una excepción en una orquestación sin haber activado el seguimiento, se podría insertar una instancia de seguimiento huérfana con estado Iniciado y la información de excepción en la base de datos de seguimiento de BizTalk Tracking (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="5ffec-105">If an exception is caught and handled in an orchestration without tracking turned on, an orphaned tracking instance with a Started state and exception information may be inserted into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="5ffec-106">Este registro permanecerá tras haber purgado la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5ffec-106">This record will remain after purging the database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5ffec-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5ffec-107">Prerequisites</span></span>  
 <span data-ttu-id="5ffec-108">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5ffec-108">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="5ffec-109">Procedimiento para purgar datos de la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="5ffec-109">To purge data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="5ffec-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="5ffec-110">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="5ffec-111">En el **conectar al servidor** cuadro de diálogo, especifique el nombre del servidor SQL donde reside la base de datos de seguimiento de BizTalk (BizTalkDTADb) y el tipo de autenticación adecuado y, a continuación, haga clic en **conectar** a conectarse a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5ffec-111">In the **Connect to Server** dialog box, specify the name of the SQL Server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the SQL Server.</span></span>  
  
3.  <span data-ttu-id="5ffec-112">En **Microsoft SQL Server Management Studio**, haga doble clic en **Agente SQL Server**y, a continuación, haga clic en **trabajos**.</span><span class="sxs-lookup"><span data-stu-id="5ffec-112">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="5ffec-113">En el **detalles del explorador de objetos** panel, haga clic en **DTA Purge and Archive (BizTalkDTADb)**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5ffec-113">In the **Object Explorer Details** pane, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="5ffec-114">En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, haga clic en **pasos**.</span><span class="sxs-lookup"><span data-stu-id="5ffec-114">In the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="5ffec-115">En el **lista de pasos de trabajo**, haga clic en **archivar y purgar**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="5ffec-115">In the **Job step list**, click **Archive and Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="5ffec-116">En el **Job Step Properties – Archive and Purge** cuadro de diálogo, en la **General** página, en la **comando** , cambie **exec dtasp_ BackupAndPurgeTrackingDatabase** a **exec dtasp_PurgeTrackingDatabase**.</span><span class="sxs-lookup"><span data-stu-id="5ffec-116">In the **Job Step Properties - Archive and Purge** dialog box, on the **General** page, in the **Command** box, change **exec dtasp_BackupAndPurgeTrackingDatabase** to **exec dtasp_PurgeTrackingDatabase**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="5ffec-117">El **exec dtasp_PurgeTrackingDatabase** procedimiento almacenado no archiva la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="5ffec-117">The **exec dtasp_PurgeTrackingDatabase** stored procedure does not archive the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="5ffec-118">Antes de utilizar esta opción, asegúrese de que ya no necesita los datos de seguimiento archivados.</span><span class="sxs-lookup"><span data-stu-id="5ffec-118">Before using this option, be certain that you no longer require archived tracking data.</span></span>  
  
8.  <span data-ttu-id="5ffec-119">En el **comando** cuadro, edite los parámetros siguientes según corresponda y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5ffec-119">In the **Command** box, edit the following parameters as appropriate, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="5ffec-120">@nHourstinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="5ffec-120">@nHours tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span>  
  
    -   <span data-ttu-id="5ffec-121">@nDaystinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="5ffec-121">@nDays tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="5ffec-122">El intervalo predeterminado es 1 día.</span><span class="sxs-lookup"><span data-stu-id="5ffec-122">Default interval is 1 day.</span></span>  
  
    -   <span data-ttu-id="5ffec-123">@nHardDaystinyint: se eliminarán todos los datos anteriores a este día, incluso si los datos están incompletos.</span><span class="sxs-lookup"><span data-stu-id="5ffec-123">@nHardDays tinyint — All data older than this day will be deleted, even if the data is incomplete.</span></span> <span data-ttu-id="5ffec-124">El intervalo de tiempo especificado para HardDeleteDays debería ser superior a la ventana de actividad de los datos.</span><span class="sxs-lookup"><span data-stu-id="5ffec-124">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="5ffec-125">La ventana de actividad de datos es el intervalo de tiempo durante el cual se desea conservar los datos de seguimiento en la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="5ffec-125">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="5ffec-126">Todo lo que sea anterior a este intervalo cumplirá los requisitos para ser objeto de archivo en el siguiente archivo y, posteriormente, de purga.</span><span class="sxs-lookup"><span data-stu-id="5ffec-126">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span>  
  
    -   <span data-ttu-id="5ffec-127">@dtLastBackup: Establezca esta propiedad en **GetUTCDate()** para purgar datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="5ffec-127">@dtLastBackup — Set this to **GetUTCDate()** to purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="5ffec-128">Cuando se establece en **NULL**, no se purgan los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5ffec-128">When set to **NULL**, data is not purged from the database.</span></span>  
  
     <span data-ttu-id="5ffec-129">La secuencia de comandos editada tendrá apariencia similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ffec-129">Your edited script should look similar to this:</span></span>  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup  
    ```  
  
9. <span data-ttu-id="5ffec-130">En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, haga clic en **General**, seleccione la **habilitado**casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5ffec-130">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **General**, select the **Enabled** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ffec-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ffec-131">See Also</span></span>  
 [<span data-ttu-id="5ffec-132">Archivar y purgar la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="5ffec-132">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)