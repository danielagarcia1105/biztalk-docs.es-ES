---
title: "Cómo configurar la purga DTA y archivar trabajo | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-11-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- purging, configuring
- DTA Purge and Archive job, configuring
- archiving [Tracking database], DTA Purge and Archive job
- archiving [Tracking database], configuring
- purging, DTA Purge and Archive job
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f4985e657f26945aa2fdc168b273dbfdb159efc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="742fe-102">Cómo configurar el trabajo DTA Purge and Archive</span><span class="sxs-lookup"><span data-stu-id="742fe-102">How to Configure the DTA Purge and Archive Job</span></span>
<span data-ttu-id="742fe-103">Antes de poder archivar o purgar datos en la base de datos de seguimiento de BizTalk (BizTalkDTADb), debe configurar el trabajo DTA Purge and Archive (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="742fe-103">Before you can archive or purge data from the BizTalk Tracking (BizTalkDTADb) database, you must configure the DTA Purge and Archive (BizTalkDTADb) job.</span></span> <span data-ttu-id="742fe-104">Este trabajo está configurado para llamar al procedimiento de almacén dtasp_backupandpurgetrackingdatabase por que utiliza seis parámetros que debe configurar.</span><span class="sxs-lookup"><span data-stu-id="742fe-104">This job is configured to call the dtasp_BackupAndPurgeTrackingDatabase store procedure, which uses six parameters you must configure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="742fe-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="742fe-105">Prerequisites</span></span>  
 <span data-ttu-id="742fe-106">Debe ser iniciado sesión con una cuenta que sea miembro del rol sysadmin de SQL Server rol fijo de servidor debe seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="742fe-106">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to follow these steps.</span></span>  
  
### <a name="to-configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="742fe-107">Para configurar el trabajo de purga y archivo DTA</span><span class="sxs-lookup"><span data-stu-id="742fe-107">To configure the DTA purge and archive job</span></span>  
  
1.  <span data-ttu-id="742fe-108">En el servidor SQL Server que hospeda la base de datos de seguimiento de BizTalk (BizTalkDTADb), abra **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="742fe-108">On the SQL Server that hosts the BizTalk Tracking (BizTalkDTADb) database, open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="742fe-109">En **conectar al servidor**, escriba el nombre del servidor SQL donde el seguimiento (BizTalkDTADb) de BizTalk reside base de datos, especifique el tipo de autenticación y, a continuación, seleccione **conectar** para conectarse a SQL server.</span><span class="sxs-lookup"><span data-stu-id="742fe-109">In **Connect to Server**, enter the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides, enter the authentication type, and then select **Connect** to connect to the SQL server.</span></span>  
  
3.  <span data-ttu-id="742fe-110">En **Microsoft SQL Server Management Studio**, haga doble clic en **Agente SQL Server**y, a continuación, haga clic en **trabajos**.</span><span class="sxs-lookup"><span data-stu-id="742fe-110">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="742fe-111">En el **detalles del explorador de objetos** panel, haga clic en **DTA Purge and Archive (BizTalkDTADb)**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="742fe-111">In the **Object Explorer Details** pane, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="742fe-112">En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, haga clic en **pasos**.</span><span class="sxs-lookup"><span data-stu-id="742fe-112">In the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="742fe-113">En el **lista de pasos de trabajo**, haga clic en **archivar y purgar**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="742fe-113">In the **Job step list**, click **Archive and Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="742fe-114">En el **General** página, en la **comando** cuadro, edite los parámetros siguientes según corresponda y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="742fe-114">On the **General** page, in the **Command** box, edit the following parameters as appropriate, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="742fe-115">@nLiveHourstinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="742fe-115">@nLiveHours tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="742fe-116">Se trata de un parámetro necesario y no tiene valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="742fe-116">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="742fe-117">@nLiveDaystinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="742fe-117">@nLiveDays tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="742fe-118">Intervalo predeterminado es 0 días.</span><span class="sxs-lookup"><span data-stu-id="742fe-118">Default interval is 0 days.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="742fe-119">Para los propósitos de la base de datos de seguimiento de BizTalk (BizTalkDTADb), la suma de LiveHours más LiveDays es la ventana de actividad de los datos que desea mantener en el entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="742fe-119">For the purposes of the BizTalk Tracking (BizTalkDTADb) database, the sum of LiveHours plus LiveDays is the live window of data you want to maintain in your BizTalk Server environment.</span></span> <span data-ttu-id="742fe-120">Se eliminan todos los datos asociados a una instancia completa anterior a la ventana de actividad de los datos.</span><span class="sxs-lookup"><span data-stu-id="742fe-120">All data associated with a completed instance older than the live window of data is deleted.</span></span>  
  
    -   <span data-ttu-id="742fe-121">@nHardDeleteDaystinyint, todos los datos (aunque incompletos) anteriores a éste se eliminará.</span><span class="sxs-lookup"><span data-stu-id="742fe-121">@nHardDeleteDays tinyint — All data (even if incomplete) older than this will be deleted.</span></span> <span data-ttu-id="742fe-122">El intervalo de tiempo especificado para HardDeleteDays debería ser superior a la ventana de actividad de los datos.</span><span class="sxs-lookup"><span data-stu-id="742fe-122">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="742fe-123">La ventana de actividad de datos es el intervalo de tiempo durante el cual se desea conservar los datos de seguimiento en la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="742fe-123">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="742fe-124">Todo lo que sea anterior a este intervalo cumplirá los requisitos para ser objeto de archivo en el siguiente archivo y, posteriormente, de purga.</span><span class="sxs-lookup"><span data-stu-id="742fe-124">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span> <span data-ttu-id="742fe-125">Valor predeterminado es 0 días.</span><span class="sxs-lookup"><span data-stu-id="742fe-125">Default is 0 days.</span></span>  
  
    -   <span data-ttu-id="742fe-126">@nvcFoldernvarchar (1024): carpeta en la que se va a colocar los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="742fe-126">@nvcFolder nvarchar(1024) — Folder in which to put the backup files.</span></span> <span data-ttu-id="742fe-127">Se trata de un parámetro necesario y no tiene valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="742fe-127">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="742fe-128">@nvcValidatingServersysname: servidor en el que se realizará la validación.</span><span class="sxs-lookup"><span data-stu-id="742fe-128">@nvcValidatingServer sysname — Server on which validation will be done.</span></span> <span data-ttu-id="742fe-129">El valor NULL indica que no se efectúa ninguna validación.</span><span class="sxs-lookup"><span data-stu-id="742fe-129">NULL value indicates no validation is being done.</span></span> <span data-ttu-id="742fe-130">Valor predeterminado es NULL.</span><span class="sxs-lookup"><span data-stu-id="742fe-130">Default is NULL.</span></span>  
  
    -   <span data-ttu-id="742fe-131">@fForceBackupint: valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="742fe-131">@fForceBackup int — Default is 0.</span></span> <span data-ttu-id="742fe-132">Se reserva para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="742fe-132">This is reserved for future use.</span></span>  
  
     <span data-ttu-id="742fe-133">El comando editado debería parecerse al siguiente.</span><span class="sxs-lookup"><span data-stu-id="742fe-133">The edited command should look similar to the following.</span></span> <span data-ttu-id="742fe-134">En el ejemplo siguiente, hay una ventana de 1 hora y purga incondicional de 1 día:</span><span class="sxs-lookup"><span data-stu-id="742fe-134">In the following example, there is a live window of 1 hour and a hard purge of 1 day:</span></span>  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0  
    ```  
  
8.  <span data-ttu-id="742fe-135">En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, haga clic en **General**, seleccione la **habilitado**casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="742fe-135">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **General**, select the **Enabled** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="742fe-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="742fe-136">See Also</span></span>  
 [<span data-ttu-id="742fe-137">Archivar y purgar la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="742fe-137">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)