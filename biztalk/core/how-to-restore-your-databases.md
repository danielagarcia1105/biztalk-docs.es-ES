---
title: Cómo restaurar las bases de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 2016-05-10
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- restoring [BAM], Star Schema database, Star Schema database [BAM], restoring
- restoring, 64-bit environments
- Star Schema database [BAM], restoring
- restoring [BAM], Analysis database
- log shipping
- databases, restoring
- Archive database [BAM], restoring
- backing up, restoring
- Analysis database [BAM], restoring
- restoring [BAM], Archive database
- restoring [BAM], Star Schema database
- databases, restoring [64-bit environment]
- Primary Import database [BAM], restoring
- 64-bit environments, restoring databases
- restoring, databases
ms.assetid: 0176932a-6b3d-4502-975b-a76296189092
caps.latest.revision: 52
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6833fff893a692475e97e7722d9d65658eace0d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255772"
---
# <a name="how-to-restore-your-databases"></a><span data-ttu-id="c0a7d-102">Cómo restaurar las bases de datos</span><span class="sxs-lookup"><span data-stu-id="c0a7d-102">How to Restore Your Databases</span></span>
<span data-ttu-id="c0a7d-103">Es preciso efectuar una restauración de todas las bases de datos en la misma marca para garantizar que el estado transaccional sea coherente en todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-103">You must restore all databases to the same mark to ensure a consistent transactional state among the databases.</span></span> <span data-ttu-id="c0a7d-104">Vea [transacciones marcadas, copias de seguridad completas y diferenciales](../core/marked-transactions-full-backups-and-log-backups.md).</span><span class="sxs-lookup"><span data-stu-id="c0a7d-104">See [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
 <span data-ttu-id="c0a7d-105">Si solo hay un servidor en el sistema de destino, asegúrese de que se han restaurado todos los conjuntos de copias de seguridad de registro (excepto el más reciente).</span><span class="sxs-lookup"><span data-stu-id="c0a7d-105">If there is only one server in the destination system, make sure that all of the log backup sets (except for the most recent set) have been restored.</span></span> <span data-ttu-id="c0a7d-106">Vea [ver el historial de restaura las copias de seguridad](../core/viewing-the-history-of-restored-backups.md).</span><span class="sxs-lookup"><span data-stu-id="c0a7d-106">See [Viewing the History of Restored Backups](../core/viewing-the-history-of-restored-backups.md).</span></span> <span data-ttu-id="c0a7d-107">Si no se han restaurado todos los conjuntos de copias de seguridad de registro y el trabajo de restauración no se está ejecutando en ese momento, ejecútelo (de forma manual, si es necesario).</span><span class="sxs-lookup"><span data-stu-id="c0a7d-107">If all the log backup sets have not been restored, and the restore job is not currently running, run the restore job (manually if necessary).</span></span> <span data-ttu-id="c0a7d-108">Si hay conjuntos de copia de seguridad pendientes que se puedan recuperar, la tarea los procesa hasta que estén todos restaurados.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-108">If there are outstanding backup sets that can be restored, the job processes them until they are all restored.</span></span>  
  
 <span data-ttu-id="c0a7d-109">Si hay varios servidores en el sistema de destino, se deben restaurar todos en el mismo conjunto de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-109">If there are multiple servers in the destination system, all servers must be restored to the same backup set.</span></span> <span data-ttu-id="c0a7d-110">Consulte el historial de restauración de cada servidor y asegúrese de que el registro más reciente de conjuntos de copia de seguridad es el mismo en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-110">View the restore history on each server and make sure that the most recent log backup set restored is the same on all servers.</span></span> <span data-ttu-id="c0a7d-111">Si no es así, debe ejecutar manualmente el trabajo de restauración en los servidores en los que se deba restaurar el conjunto de copias de seguridad de registro más reciente.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-111">If it is not, you must manually run the restore job on each server that needs the most recent log backup set restored.</span></span>  
  
 <span data-ttu-id="c0a7d-112">Cuando todos los servidores se encuentren en el mismo conjunto de copias de seguridad, puede restaurar manualmente el conjunto final.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-112">After all of the servers are on the same backup set, the final set can be manually restored.</span></span>  
  
 <span data-ttu-id="c0a7d-113">La tabla adm_BackupHistory constituye el punto central de historial para el proceso de trasvase de registros del sistema de origen.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-113">The adm_BackupHistory table is the central history point for the log shipping process for the source system.</span></span> <span data-ttu-id="c0a7d-114">En esta tabla se registran todos los trabajos de copia de seguridad realizados.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-114">All backup work performed is recorded to this table.</span></span> <span data-ttu-id="c0a7d-115">Todos los servidores del sistema de destino efectúan una lectura de esta tabla para obtener la información necesaria para realizar la restauración.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-115">All servers in your destination system read from this table to receive the information needed to perform their restore work.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0a7d-116">Si restaura la base de datos de importación principal de BAM a partir de una copia de seguridad, también debe restaurar las bases de datos de archivo de BAM, de esquema de estrella de BAM y de análisis de BAM mediante una copia de seguridad anterior a la principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-116">If you restore the BAM Primary Import database from a backup, then you should also restore the BAM Archive, BAM Star Schema, and BAM Analysis databases by using a backup older than the BAM Primary backup.</span></span> <span data-ttu-id="c0a7d-117">Vea [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span><span class="sxs-lookup"><span data-stu-id="c0a7d-117">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0a7d-118">Si mueve las copias de seguridad completas o de registro de una base de datos de origen desde la ubicación en la que las colocó el trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe actualizar la fila asociada a esa base de datos en la tabla bts_LogShippingDatabases del sistema de destino. Para ello, establezca LogFileLocation o DBFileLocation en la nueva ubicación en la que el sistema de destino debe leer los archivos de copia de seguridad completa o de registro.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-118">If you move the full or log backups for a source database from the location in which the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job put them, you should update the associated row for that database in the bts_LogShippingDatabases table on the destination system by setting the LogFileLocation or DBFileLocation to the new location where the destination system should read the full/log backup files.</span></span> <span data-ttu-id="c0a7d-119">Esta tabla se rellena al ejecutar el procedimiento almacenado bts_ConfigureBtsLogShipping.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-119">This table is populated when you run the bts_ConfigureBtsLogShipping stored procedure.</span></span> <span data-ttu-id="c0a7d-120">De forma predeterminada, estas columnas se configuran como null, lo que indica que el sistema de destino debe leer los archivos de copia de seguridad desde la ubicación almacenada en la tabla adm_BackupHistory.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-120">By default, these columns are set to null, which indicates that the destination system should read the backup files from the location stored in the adm_BackupHistory table.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c0a7d-121">Guarde siempre una copia de sus archivos de copia de seguridad en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-121">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="c0a7d-122">Aunque haya registrado copias de seguridad, no podrá restaurar las bases de datos sin los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-122">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c0a7d-123">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c0a7d-123">Prerequisites</span></span>  
 <span data-ttu-id="c0a7d-124">Inicie sesión en SQL Server con una cuenta que sea miembro del rol sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-124">Log in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
### <a name="to-restore-your-databases"></a><span data-ttu-id="c0a7d-125">Para restaurar sus bases de datos</span><span class="sxs-lookup"><span data-stu-id="c0a7d-125">To restore your databases</span></span>  
  
1.  <span data-ttu-id="c0a7d-126">En el sistema de destino, abra **SQL Server Management Studio**y conectarse a su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0a7d-126">On the destination system, open **SQL Server Management Studio**, and connect to your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0a7d-127">Expanda **Agente SQL Server** y **Trabajos**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-127">Expand **SQL Server Agent**, and expand **Jobs**.</span></span> <span data-ttu-id="c0a7d-128">Realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0a7d-128">Do the following:</span></span>  
  
    1.  <span data-ttu-id="c0a7d-129">Haga clic en el **envío de registro BTS - obtener historial de copia de seguridad** de trabajo y seleccione **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-129">Right-click the **BTS Log Shipping - Get Backup History** job and select **Disable**.</span></span> <span data-ttu-id="c0a7d-130">El estado se cambia a Correcto.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-130">The status changes to Success.</span></span>  
  
    2.  <span data-ttu-id="c0a7d-131">Haga clic en el **envío de registro BTS - Restaurar bases de datos** de trabajo y seleccione **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-131">Right-click the **BTS Log Shipping - Restore Databases** job and select **Disable**.</span></span> <span data-ttu-id="c0a7d-132">El estado se cambia a Correcto.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-132">The status changes to Success.</span></span>  
  
    3.  <span data-ttu-id="c0a7d-133">Haga clic en el **envío de registro BTS - Restaurar en marca** y seleccione **iniciar trabajo en el paso**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-133">Right-click the **BTS Log Shipping - Restore To Mark** and select **Start Job at Step**.</span></span> <span data-ttu-id="c0a7d-134">Seleccione **Id. de paso 1** y seleccione **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-134">Select **Step ID 1** and select **Start**.</span></span>  
  
         <span data-ttu-id="c0a7d-135">Cuando el estado cambia a **correcto**, los trabajos del Agente SQL Server y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se restauran las bases de datos en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-135">When the status changes to **Success**, the SQL Server Agent jobs and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are restored to the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c0a7d-136">Si el **estado** es Error, seleccione el vínculo en el campo de mensaje para determinar la causa.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-136">If the **Status** is Error, select the link in the Message field to determine the cause.</span></span> <span data-ttu-id="c0a7d-137">Estos trabajos deberían tener un estado de Correcto antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-137">These jobs should have a Success status before continuing.</span></span>  
  
3.  <span data-ttu-id="c0a7d-138">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] donde editó el archivo SampleUpdateInfo.xml, abra un símbolo del sistema y vaya a:</span><span class="sxs-lookup"><span data-stu-id="c0a7d-138">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] where you edited the SampleUpdateInfo.xml file, open a command prompt, and go to:</span></span>  
  
     <span data-ttu-id="c0a7d-139">equipo de 32 bits:`%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="c0a7d-139">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
     <span data-ttu-id="c0a7d-140">equipo de 64 bits:`%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="c0a7d-140">64-bit computer: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
4.  <span data-ttu-id="c0a7d-141">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="c0a7d-141">At the command prompt, type:</span></span>  
  
     `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
  
     <span data-ttu-id="c0a7d-142">Este script actualiza todas las tablas que almacenan información acerca de la ubicación de otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-142">This script updates all tables that store information about the location of other databases.</span></span>  
  
    > [!IMPORTANT]
    >  -   <span data-ttu-id="c0a7d-143">Ejecute UpdateDatabase.vbs en **una** servidor en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-143">Run UpdateDatabase.vbs on **one** server in the BizTalk group.</span></span>  
    > -   <span data-ttu-id="c0a7d-144">En los equipos de 64 bits, debe ejecutar UpdateDatabase.vbs desde un símbolo del sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-144">On 64-bit computers, you must run UpdateDatabase.vbs from a 64-bit command prompt.</span></span> <span data-ttu-id="c0a7d-145">Tenga en cuenta que el símbolo del sistema por defecto en los equipos de 64 bits es un símbolo de sistema de 64 bits y está ubicado en %SystemDrive%\windows\System32\cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-145">Note that the default command prompt on 64-bit computers is a 64-bit command prompt and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
    > -   <span data-ttu-id="c0a7d-146">El motor de EDI de BizTalk no requiere ninguna de sus propias modificaciones a SampleUpdateInfo.xml al restaurar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-146">The BizTalk EDI engine does not require any of its own modifications to SampleUpdateInfo.xml when restoring databases.</span></span>  <span data-ttu-id="c0a7d-147">Se basa en la conectividad con la base de datos de BizTalkDTADb para tener acceso a las tablas EDI.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-147">It relies on connectivity to the BizTalkDTADb database to access the EDI tables.</span></span>  
  
5.  <span data-ttu-id="c0a7d-148">Copie el archivo SampleUpdateInfo.xml editado en la carpeta siguiente en **cada** equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en este grupo de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="c0a7d-148">Copy the edited SampleUpdateInfo.xml file to the following folder on **every** computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in this BizTalk group:</span></span>  
  
     <span data-ttu-id="c0a7d-149">equipo de 32 bits: copiar a`%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="c0a7d-149">32-bit computer: Copy to `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
     <span data-ttu-id="c0a7d-150">equipo de 64 bits: copiar a`%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="c0a7d-150">64-bit computer: Copy to `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
6.  <span data-ttu-id="c0a7d-151">En **cada** equipo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de grupo, abra un símbolo del sistema y vaya a:</span><span class="sxs-lookup"><span data-stu-id="c0a7d-151">On **each** computer in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group, open a command prompt, and go to:</span></span>  
  
     <span data-ttu-id="c0a7d-152">equipo de 32 bits:`%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="c0a7d-152">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
     <span data-ttu-id="c0a7d-153">equipo de 64 bits:`%SystemDrive%Program Files (x86)Microsoft BizTalk Server <version>Bins32SchemaRestore`</span><span class="sxs-lookup"><span data-stu-id="c0a7d-153">64-bit computer: `%SystemDrive%Program Files (x86)Microsoft BizTalk Server <version>Bins32SchemaRestore`</span></span>  
  
7.  <span data-ttu-id="c0a7d-154">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="c0a7d-154">At the command prompt, type:</span></span>  
  
     `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
     <span data-ttu-id="c0a7d-155">Este script actualiza todas las entradas del Registro que almacenan información acerca de la ubicación de otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-155">This script updates all registry entries that store information about the location of other databases.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c0a7d-156">Ejecute UpdateRegistry.vbs en **cada** servidor en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-156">Run UpdateRegistry.vbs on **every** server in the BizTalk group.</span></span>  
    >   
    >  <span data-ttu-id="c0a7d-157">En los equipos de 64 bits, debe ejecutar UpdateRegistry.vbs desde un símbolo del sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-157">On 64-bit computers, you must run UpdateRegistry.vbs from a 64-bit command prompt.</span></span>  <span data-ttu-id="c0a7d-158">Tenga en cuenta que el símbolo del sistema por defecto en los equipos de 64 bits es un símbolo de sistema de 64 bits y está ubicado en %SystemDrive%\windows\System32\cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-158">Note that the default command prompt on 64-bit computers is a 64-bit command prompt and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
  
8.  <span data-ttu-id="c0a7d-159">Reinicie todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0a7d-159">Restart all the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="c0a7d-160">Vea [cómo iniciar, detener, pausar, reanudar o reiniciar el servidor BizTalk Server de servicios](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="c0a7d-160">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
9. <span data-ttu-id="c0a7d-161">Después de restaurar sus bases de datos, reinicie el servicio del Instrumental de administración de Windows:</span><span class="sxs-lookup"><span data-stu-id="c0a7d-161">After restoring your databases, restart the Windows Management Instrumentation service:</span></span>  
  
    1.  <span data-ttu-id="c0a7d-162">Abra **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-162">Open **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="c0a7d-163">Haga clic en **Windows Management Instrumentation**y, a continuación, seleccione **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-163">Right-click **Windows Management Instrumentation**, and then select **Restart**.</span></span>  
  
10. <span data-ttu-id="c0a7d-164">Abra **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-164">Open **BizTalk Server Administration**.</span></span> <span data-ttu-id="c0a7d-165">Realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0a7d-165">Do the following:</span></span>  
  
    1.  <span data-ttu-id="c0a7d-166">Haga clic en el **grupo de BizTalk** y seleccione **quitar**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-166">Right-click the **BizTalk Group** and select **Remove**.</span></span>  
  
    2.  <span data-ttu-id="c0a7d-167">Haga clic en **administración de BizTalk Server** y seleccione **conectar a grupo existente**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-167">Right-click **BizTalk Server Administration** and select **Connect to Existing Group**.</span></span>  
  
    3.  <span data-ttu-id="c0a7d-168">En **nombre de SQL Server**, seleccione el nombre de la instancia de SQL Server que hospeda la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-168">In **SQL Server name**, select the name of the SQL Server instance that hosts the BizTalk Management database.</span></span> <span data-ttu-id="c0a7d-169">Cuando seleccione la instancia de SQL Server, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] detectará automáticamente las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-169">When you select the SQL Server instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically detects the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases on that computer.</span></span>  
  
    4.  <span data-ttu-id="c0a7d-170">En **nombre de base de datos**, seleccione la base de datos de administración de BizTalk (**BizTalkMgmtDb** de forma predeterminada) y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-170">In **Database name**, select your BizTalk Management database (**BizTalkMgmtDb** by default), and then select **OK**.</span></span>  
  
     <span data-ttu-id="c0a7d-171">La consola de Administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] agregará el grupo BizTalk a la consola de Administración.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-171">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console adds the BizTalk group to the Administration console.</span></span>  
  
     <span data-ttu-id="c0a7d-172">Con ello, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se habrá restaurado y debería estar en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-172">Your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is now restored and should be running.</span></span> <span data-ttu-id="c0a7d-173">A continuación, configure el trabajo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de copia de seguridad para comenzar a realizar copias de seguridad en un nuevo servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-173">Next, configure the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job to start writing backups to a new destination server.</span></span> <span data-ttu-id="c0a7d-174">Asimismo, debe volver a configurar un nuevo sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-174">You should also reconfigure a new destination system.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c0a7d-175">Si usa el motor de reglas, debe reiniciar el Servicio de actualización de motor de reglas en todos los servidores del grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] después de restaurar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-175">If you are using the Rules Engine, after restoring the databases, you must restart the Rule Engine Update Service on every server in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="c0a7d-176">Vea [cómo iniciar, detener, pausar, reanudar o reiniciar el servidor BizTalk Server de servicios](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="c0a7d-176">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0a7d-177">Si usa BAM, este es el tiempo para restaurar las bases de datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="c0a7d-177">If you are using BAM, this is the time to restore the BAM databases.</span></span> <span data-ttu-id="c0a7d-178">Vea [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span><span class="sxs-lookup"><span data-stu-id="c0a7d-178">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c0a7d-179">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c0a7d-179">Next Steps</span></span>  
 [<span data-ttu-id="c0a7d-180">Copia de seguridad y restauración de BAM</span><span class="sxs-lookup"><span data-stu-id="c0a7d-180">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a><span data-ttu-id="c0a7d-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0a7d-181">See Also</span></span>  
 <span data-ttu-id="c0a7d-182">[Cómo configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="c0a7d-182">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="c0a7d-183">Cómo configurar el sistema de destino de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="c0a7d-183">How to Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)