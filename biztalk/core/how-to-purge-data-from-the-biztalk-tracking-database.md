---
title: Purgar datos de la base de datos de seguimiento de BizTalk | Documentos de Microsoft
description: Configurar el procedimiento almacenado dtasp_PurgeTrackingDatabase para purgar la base de datos de seguimiento (BizTalkDTADB) en BizTalk Server
ms.custom: ''
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06217a7d5012eb402698ad35e76ccfc886952f6e
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="abc1e-103">Purgar datos de la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="abc1e-103">Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="abc1e-104">Cuando se purgan datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb), el trabajo DTA Purge and Archive se encarga de purgar de la base de datos de seguimiento de BizTalk (BizTalkDTADb) diversos tipos de información de seguimiento como, por ejemplo, información de instancia de servicio y mensaje, información de eventos de orquestación y datos de seguimiento del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="abc1e-104">When you purge data from the BizTalk Tracking (BizTalkDTADb) database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="abc1e-105">La base de datos seguimiento de BizTalk (BizTalkDTADb) no se archiva mediante este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="abc1e-105">The BizTalk Tracking (BizTalkDTADb) database is not archived using this procedure.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="abc1e-106">Cuando se captura y se controla una excepción en una orquestación sin haber activado el seguimiento, se podría insertar una instancia de seguimiento huérfana con estado Iniciado y la información de excepción en la base de datos de seguimiento de BizTalk Tracking (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="abc1e-106">If an exception is caught and handled in an orchestration without tracking turned on, an orphaned tracking instance with a Started state and exception information may be inserted into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="abc1e-107">Este registro permanecerá tras haber purgado la base de datos.</span><span class="sxs-lookup"><span data-stu-id="abc1e-107">This record will remain after purging the database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="abc1e-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="abc1e-108">Prerequisites</span></span>  
<span data-ttu-id="abc1e-109">Inicie sesión con una cuenta que sea miembro del rol sysadmin de SQL Server rol fijo de servidor para llevar a cabo este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="abc1e-109">Sign in with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
## <a name="purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="abc1e-110">Purgar datos de la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="abc1e-110">Purge data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="abc1e-111">En el servidor SQL Server que hospeda la base de datos de seguimiento de BizTalk (BizTalkDTADb), abra **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="abc1e-111">On the SQL Server that hosts the BizTalk Tracking (BizTalkDTADb) database, open **SQL Server Management Studio**.</span></span> 
  
2.  <span data-ttu-id="abc1e-112">En **conectar al servidor**, escriba el nombre del servidor SQL donde el seguimiento (BizTalkDTADb) de BizTalk reside base de datos, especifique el tipo de autenticación y, a continuación, seleccione **conectar** para conectarse a SQL server.</span><span class="sxs-lookup"><span data-stu-id="abc1e-112">In **Connect to Server**, enter the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides, enter the authentication type, and then select **Connect** to connect to the SQL server.</span></span> 
  
3.  <span data-ttu-id="abc1e-113">Haga doble clic en **Agente SQL Server**y, a continuación, seleccione **trabajos**.</span><span class="sxs-lookup"><span data-stu-id="abc1e-113">Double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4.  <span data-ttu-id="abc1e-114">En **detalles del explorador de objetos**, haga clic en **DTA Purge and Archive (BizTalkDTADb)**y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="abc1e-114">In **Object Explorer Details**, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then select **Properties**.</span></span>  
  
5.  <span data-ttu-id="abc1e-115">En **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, en **seleccionar una página**, seleccione **pasos**.</span><span class="sxs-lookup"><span data-stu-id="abc1e-115">In **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="abc1e-116">En **lista de pasos de trabajo**, seleccione **archivar y purgar**y, a continuación, seleccione **editar**.</span><span class="sxs-lookup"><span data-stu-id="abc1e-116">In **Job step list**, select **Archive and Purge**, and then select **Edit**.</span></span>  
  
7.  <span data-ttu-id="abc1e-117">En **Job Step Properties – Archive and Purge**, en la **General** página, en la **comando** , cambie **exec dtasp_backupandpurgetrackingdatabase por** a **exec dtasp_PurgeTrackingDatabase**.</span><span class="sxs-lookup"><span data-stu-id="abc1e-117">In **Job Step Properties - Archive and Purge**, on the **General** page, in the **Command** box, change **exec dtasp_BackupAndPurgeTrackingDatabase** to **exec dtasp_PurgeTrackingDatabase**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="abc1e-118">El **exec dtasp_PurgeTrackingDatabase** procedimiento almacenado no archiva la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="abc1e-118">The **exec dtasp_PurgeTrackingDatabase** stored procedure does not archive the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="abc1e-119">Antes de utilizar esta opción, asegúrese de que ya no necesita los datos de seguimiento archivados.</span><span class="sxs-lookup"><span data-stu-id="abc1e-119">Before using this option, be certain that you no longer require archived tracking data.</span></span>  
  
8.  <span data-ttu-id="abc1e-120">En el **comando** cuadro, actualizar los parámetros siguientes y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="abc1e-120">In the **Command** box, update the following parameters, and then select **OK**.</span></span>  
  
    -   <span data-ttu-id="abc1e-121">@nHours tinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="abc1e-121">@nHours tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span>  
  
    -   <span data-ttu-id="abc1e-122">@nDays tinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="abc1e-122">@nDays tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="abc1e-123">El intervalo predeterminado es 1 día.</span><span class="sxs-lookup"><span data-stu-id="abc1e-123">Default interval is 1 day.</span></span>  
  
    -   <span data-ttu-id="abc1e-124">@nHardDays tinyint: se eliminarán todos los datos anteriores a este día, incluso si los datos están incompletos.</span><span class="sxs-lookup"><span data-stu-id="abc1e-124">@nHardDays tinyint — All data older than this day will be deleted, even if the data is incomplete.</span></span> <span data-ttu-id="abc1e-125">El intervalo de tiempo especificado para HardDeleteDays debería ser superior a la ventana de actividad de los datos.</span><span class="sxs-lookup"><span data-stu-id="abc1e-125">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="abc1e-126">La ventana de actividad de datos es el intervalo de tiempo durante el cual se desea conservar los datos de seguimiento en la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="abc1e-126">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="abc1e-127">Todo lo que sea anterior a este intervalo cumplirá los requisitos para ser objeto de archivo en el siguiente archivo y, posteriormente, de purga.</span><span class="sxs-lookup"><span data-stu-id="abc1e-127">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span>  
  
    -   <span data-ttu-id="abc1e-128">@dtLastBackup : Establezca esta propiedad en **GetUTCDate()** para purgar datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="abc1e-128">@dtLastBackup — Set this to **GetUTCDate()** to purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="abc1e-129">Cuando se establece en **NULL**, no se purgan los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="abc1e-129">When set to **NULL**, data is not purged from the database.</span></span>  

    -  <span data-ttu-id="abc1e-130">@fHardDeleteRunningInstances int: el valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="abc1e-130">@fHardDeleteRunningInstances int - Default is 0.</span></span> <span data-ttu-id="abc1e-131">Cuando se establece en 1, elimina todas las instancias anteriores a en ejecución la @nHardDeleteDays valor.</span><span class="sxs-lookup"><span data-stu-id="abc1e-131">When set to 1, it deletes all running service instances older than the @nHardDeleteDays value.</span></span>  
    
        > [!NOTE] 
        > <span data-ttu-id="abc1e-132">El @fHardDeleteRunningInstances propiedad está disponible a partir de [actualización acumulativa 1 de BizTalk Server 2016](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [actualización acumulativa 6 de BizTalk Server 2013 R2](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), y [acumulativa de BizTalk Server 2013 Actualizar 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).</span><span class="sxs-lookup"><span data-stu-id="abc1e-132">The @fHardDeleteRunningInstances property is available starting with [BizTalk Server 2016 Cumulative Update 1](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [BizTalk Server 2013 R2 Cumulative Update 6](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), and [BizTalk Server 2013 Cumulative Update 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).</span></span>   

    <span data-ttu-id="abc1e-133">La secuencia de comandos editada tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="abc1e-133">Your edited script looks similar to the following:</span></span>  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup, 1  
    ```  
    
9. <span data-ttu-id="abc1e-134">En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, seleccione **General**, seleccione la **habilitado**casilla de verificación y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="abc1e-134">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, select **General**, select the **Enabled** check box, and then select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abc1e-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="abc1e-135">See Also</span></span>  
 [<span data-ttu-id="abc1e-136">Archivar y purgar la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="abc1e-136">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
