---
title: Configurar la purga DTA y archivar trabajo | Documentos de Microsoft
description: "Establecer los parámetros del trabajo DTA Purge and Archive en Agente SQL Server para mantener la base de datos de seguimiento de BizTalk Server"
ms.custom: 
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 149719b7eea50ce53c14298597c94729162d43b0
ms.sourcegitcommit: 1fb633fcf919ce3124405420a5d9faa79d9d508e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2017
---
# <a name="configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="729a6-103">Configurar la purga DTA y archivar trabajo</span><span class="sxs-lookup"><span data-stu-id="729a6-103">Configure the DTA Purge and Archive Job</span></span>
<span data-ttu-id="729a6-104">Antes de poder archivar o purgar datos en la base de datos de seguimiento de BizTalk (BizTalkDTADb), debe configurar el trabajo DTA Purge and Archive (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="729a6-104">Before you can archive or purge data from the BizTalk Tracking (BizTalkDTADb) database, you must configure the DTA Purge and Archive (BizTalkDTADb) job.</span></span> <span data-ttu-id="729a6-105">Este trabajo está configurado para llamar al procedimiento de almacén dtasp_backupandpurgetrackingdatabase por que utiliza seis parámetros que debe configurar.</span><span class="sxs-lookup"><span data-stu-id="729a6-105">This job is configured to call the dtasp_BackupAndPurgeTrackingDatabase store procedure, which uses six parameters you must configure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="729a6-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="729a6-106">Prerequisites</span></span>  
 <span data-ttu-id="729a6-107">Inicie sesión con una cuenta que sea miembro del rol sysadmin de SQL Server rol fijo de servidor.</span><span class="sxs-lookup"><span data-stu-id="729a6-107">Sign in with an account that is a member of the SQL Server sysadmin fixed server role.</span></span>  
  
## <a name="configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="729a6-108">Configurar la purga DTA y archivar trabajo</span><span class="sxs-lookup"><span data-stu-id="729a6-108">Configure the DTA purge and archive job</span></span>  
  
1.  <span data-ttu-id="729a6-109">En el servidor SQL Server que hospeda la base de datos de seguimiento de BizTalk (BizTalkDTADb), abra **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="729a6-109">On the SQL Server that hosts the BizTalk Tracking (BizTalkDTADb) database, open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="729a6-110">En **conectar al servidor**, escriba el nombre del servidor SQL donde el seguimiento (BizTalkDTADb) de BizTalk reside base de datos, especifique el tipo de autenticación y, a continuación, seleccione **conectar** para conectarse a SQL server.</span><span class="sxs-lookup"><span data-stu-id="729a6-110">In **Connect to Server**, enter the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides, enter the authentication type, and then select **Connect** to connect to the SQL server.</span></span>  
  
3. <span data-ttu-id="729a6-111">Haga doble clic en **Agente SQL Server**y, a continuación, seleccione **trabajos**.</span><span class="sxs-lookup"><span data-stu-id="729a6-111">Double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4.  <span data-ttu-id="729a6-112">En **detalles del explorador de objetos**, haga clic en **DTA Purge and Archive (BizTalkDTADb)**y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="729a6-112">In **Object Explorer Details**, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then select **Properties**.</span></span>  
  
5.  <span data-ttu-id="729a6-113">En **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, en **seleccionar una página**, seleccione **pasos**.</span><span class="sxs-lookup"><span data-stu-id="729a6-113">In **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="729a6-114">En el **lista de pasos de trabajo**, seleccione **archivar y purgar**y, a continuación, seleccione **editar**.</span><span class="sxs-lookup"><span data-stu-id="729a6-114">In the **Job step list**, select **Archive and Purge**, and then select **Edit**.</span></span>  
  
7.  <span data-ttu-id="729a6-115">En **General**, en la **comando** cuadro, actualizar los parámetros siguientes y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="729a6-115">In **General**, in the **Command** box, update the following parameters, and then select **OK**.</span></span>  
  
    -   <span data-ttu-id="729a6-116">@nLiveHourstinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="729a6-116">@nLiveHours tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="729a6-117">Se trata de un parámetro necesario y no tiene valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="729a6-117">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="729a6-118">@nLiveDaystinyint: cualquier instancias completadas anteriores a (horas de actividad) + (días de actividad) se eliminarán junto con todos los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="729a6-118">@nLiveDays tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="729a6-119">Intervalo predeterminado es 0 días.</span><span class="sxs-lookup"><span data-stu-id="729a6-119">Default interval is 0 days.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="729a6-120">Para los propósitos de la base de datos de seguimiento de BizTalk (BizTalkDTADb), la suma de LiveHours más LiveDays es la ventana de actividad de los datos que desea mantener en el entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="729a6-120">For the purposes of the BizTalk Tracking (BizTalkDTADb) database, the sum of LiveHours plus LiveDays is the live window of data you want to maintain in your BizTalk Server environment.</span></span> <span data-ttu-id="729a6-121">Se eliminan todos los datos asociados a una instancia completa anterior a la ventana de actividad de los datos.</span><span class="sxs-lookup"><span data-stu-id="729a6-121">All data associated with a completed instance older than the live window of data is deleted.</span></span>  
  
    -   <span data-ttu-id="729a6-122">@nHardDeleteDaystinyint, todos los datos (aunque incompletos) anteriores a éste se eliminará.</span><span class="sxs-lookup"><span data-stu-id="729a6-122">@nHardDeleteDays tinyint — All data (even if incomplete) older than this will be deleted.</span></span> <span data-ttu-id="729a6-123">El intervalo de tiempo especificado para HardDeleteDays debería ser superior a la ventana de actividad de los datos.</span><span class="sxs-lookup"><span data-stu-id="729a6-123">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="729a6-124">La ventana de actividad de datos es el intervalo de tiempo durante el cual se desea conservar los datos de seguimiento en la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="729a6-124">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="729a6-125">Todo lo que sea anterior a este intervalo cumplirá los requisitos para ser objeto de archivo en el siguiente archivo y, posteriormente, de purga.</span><span class="sxs-lookup"><span data-stu-id="729a6-125">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span> <span data-ttu-id="729a6-126">Valor predeterminado es 0 días.</span><span class="sxs-lookup"><span data-stu-id="729a6-126">Default is 0 days.</span></span>  
  
    -   <span data-ttu-id="729a6-127">@nvcFoldernvarchar (1024): carpeta en la que se va a colocar los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="729a6-127">@nvcFolder nvarchar(1024) — Folder in which to put the backup files.</span></span> <span data-ttu-id="729a6-128">Se trata de un parámetro necesario y no tiene valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="729a6-128">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="729a6-129">@nvcValidatingServersysname: servidor en el que se realizará la validación.</span><span class="sxs-lookup"><span data-stu-id="729a6-129">@nvcValidatingServer sysname — Server on which validation will be done.</span></span> <span data-ttu-id="729a6-130">El valor NULL indica que no se efectúa ninguna validación.</span><span class="sxs-lookup"><span data-stu-id="729a6-130">NULL value indicates no validation is being done.</span></span> <span data-ttu-id="729a6-131">Valor predeterminado es NULL.</span><span class="sxs-lookup"><span data-stu-id="729a6-131">Default is NULL.</span></span>  
  
    -   <span data-ttu-id="729a6-132">@fForceBackupint: valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="729a6-132">@fForceBackup int — Default is 0.</span></span> <span data-ttu-id="729a6-133">Se reserva para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="729a6-133">This is reserved for future use.</span></span>  
  
    -   <span data-ttu-id="729a6-134">@fHardDeleteRunningInstancesint: el valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="729a6-134">@fHardDeleteRunningInstances int - Default is 0.</span></span> <span data-ttu-id="729a6-135">Cuando se establece en 1, elimina todas las instancias anteriores a en ejecución la @nHardDeleteDays valor.</span><span class="sxs-lookup"><span data-stu-id="729a6-135">When set to 1, it deletes all running service instances older than the @nHardDeleteDays value.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="729a6-136">El @fHardDeleteRunningInstances propiedad está disponible a partir de [actualización acumulativa 1 de BizTalk Server 2016](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [actualización acumulativa 6 de BizTalk Server 2013 R2](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), y [acumulativa de BizTalk Server 2013 Actualizar 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).</span><span class="sxs-lookup"><span data-stu-id="729a6-136">The @fHardDeleteRunningInstances property is available starting with [BizTalk Server 2016 Cumulative Update 1](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [BizTalk Server 2013 R2 Cumulative Update 6](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), and [BizTalk Server 2013 Cumulative Update 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).</span></span>  
  
    <span data-ttu-id="729a6-137">El comando editado debería parecerse al siguiente.</span><span class="sxs-lookup"><span data-stu-id="729a6-137">Your edited command should look similar to the following.</span></span> <span data-ttu-id="729a6-138">En el ejemplo siguiente, hay una ventana de 1 hora, purga incondicional de 1 día y las eliminaciones ejecutan todos instancias anteriores a 1 día de servicio:</span><span class="sxs-lookup"><span data-stu-id="729a6-138">In the following example, there is a live window of 1 hour, a hard purge of 1 day, and deletes all running service instances older than 1 day:</span></span>  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0, 1  
    ```  
  
8.  <span data-ttu-id="729a6-139">En el **Job Properties - DTA Purge and Archive (BizTalkDTADb)** cuadro de diálogo **seleccionar una página**, seleccione **General**, seleccione la **habilitado**casilla de verificación y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="729a6-139">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, select **General**, select the **Enabled** check box, and then select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="729a6-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="729a6-140">See Also</span></span>  
 [<span data-ttu-id="729a6-141">Archivar y purgar la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="729a6-141">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
