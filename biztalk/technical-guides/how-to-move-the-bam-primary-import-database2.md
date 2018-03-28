---
title: Cómo mover la Database2 de importación principal de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc4f2656-2faa-4503-9551-05e1b6eceb1a
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd6abeeb04521e95b32b4d6007dcc7f1f532bdbb
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-move-the-bam-primary-import-database"></a><span data-ttu-id="012ac-102">Cómo mover la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="012ac-102">How to Move the BAM Primary Import Database</span></span>
<span data-ttu-id="012ac-103">Este procedimiento se puede utilizar para mover la base de datos de importación principal de BAM a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="012ac-103">You can use this procedure to move the BAM Primary Import database to another server.</span></span> <span data-ttu-id="012ac-104">Desde una perspectiva de escenario to-end, mover la base de datos de importación principal de BAM consta de dos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="012ac-104">From an end-to-end scenario perspective, moving the BAM Primary Import database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="012ac-105">Mover la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="012ac-105">Moving the BAM Primary Import Database</span></span>](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_MovingBAMPI)  
  
-   [<span data-ttu-id="012ac-106">Actualizar las referencias a la nueva base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="012ac-106">Updating References to the New BAM Primary Import Database</span></span>](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)  
  
## <a name="prerequisites"></a><span data-ttu-id="012ac-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="012ac-107">Prerequisites</span></span>  
 <span data-ttu-id="012ac-108">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="012ac-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_MovingBAMPI"></a> <span data-ttu-id="012ac-109">Mover la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="012ac-109">Moving the BAM Primary Import Database</span></span>  
 <span data-ttu-id="012ac-110">Realice los pasos en el siguiente procedimiento para mover la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="012ac-110">Perform the steps in the following procedure to move the BAM Primary Import database.</span></span>  
  
#### <a name="to-move-the-bam-primary-import-database"></a><span data-ttu-id="012ac-111">Para mover la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="012ac-111">To move the BAM Primary Import database</span></span>  
  
1.  <span data-ttu-id="012ac-112">Detenga cualquier BAM cubo datos y actualización paquetes SSIS de mantenimiento, o impida su ejecución hasta que haya restaurado la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="012ac-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Primary Import database.</span></span>  
  
2.  <span data-ttu-id="012ac-113">Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="012ac-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="012ac-114">Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="012ac-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3.  <span data-ttu-id="012ac-115">Detenga el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="012ac-115">Stop the IIS service.</span></span>  
  
4.  <span data-ttu-id="012ac-116">Detenga el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="012ac-116">Stop the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="012ac-117">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="012ac-118">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="012ac-118">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="012ac-119">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="012ac-119">**Net stop NS$BamAlerts**</span></span>  
  
5.  <span data-ttu-id="012ac-120">Copia de seguridad principal de BAM Importar base de datos en el servidor anterior.</span><span class="sxs-lookup"><span data-stu-id="012ac-120">Back up the BAM Primary import database on the old server.</span></span> <span data-ttu-id="012ac-121">Para obtener instrucciones sobre la copia de seguridad de una base de datos, siga las instrucciones de cómo realizar copias de seguridad de una base de datos en [Cómo: copia de una base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="012ac-121">For instructions on backing up a database, follow the instructions on how to back up a database at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online.</span></span>  
  
6.  <span data-ttu-id="012ac-122">Copiar la base de datos de importación principal de BAM en la nueva [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.</span><span class="sxs-lookup"><span data-stu-id="012ac-122">Copy the BAM Primary Import database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7.  <span data-ttu-id="012ac-123">Restaure la base de datos de importación principal de BAM en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="012ac-123">Restore the BAM Primary import database on the new server.</span></span> <span data-ttu-id="012ac-124">Para obtener instrucciones acerca de cómo restaurar la base de datos, siga las instrucciones sobre cómo restaurar una base de datos en [Cómo: restaurar una copia de seguridad de base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="012ac-124">For instructions on restoring the database, follow the instructions on how to restore a database at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="012ac-125">Si restaura la base de datos de importación principal de BAM a partir de una copia de seguridad, también debe restaurar las bases de datos de archivo de BAM, de esquema de estrella de BAM y de análisis de BAM mediante una copia de seguridad anterior a la principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="012ac-125">If you restore the BAM Primary Import database from a backup, then you should also restore the BAM Archive, BAM Star Schema, and BAM Analysis databases by using a backup older than the BAM Primary backup.</span></span>  
  
##  <a name="BKMK_BAMPIRef"></a> <span data-ttu-id="012ac-126">Actualizar las referencias a la nueva base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="012ac-126">Updating References to the New BAM Primary Import Database</span></span>  
 <span data-ttu-id="012ac-127">Después de haber movido la base de datos, debe actualizar todas las referencias a la base de importación principal de BAM nueva.</span><span class="sxs-lookup"><span data-stu-id="012ac-127">After you have moved the database, you must update all the references to the new BAM Primary Import Database.</span></span> <span data-ttu-id="012ac-128">Deben actualizar las referencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="012ac-128">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="012ac-129">Actualizar todas las bases de datos de BizTalk con el nuevo nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="012ac-129">Update all the BizTalk databases with the new server name.</span></span> <span data-ttu-id="012ac-130">Puede hacerlo mediante el uso de la secuencia de comandos UpdateDatabase.vbs.</span><span class="sxs-lookup"><span data-stu-id="012ac-130">You can do so by using the UpdateDatabase.vbs script.</span></span> <span data-ttu-id="012ac-131">Vea [para actualizar las bases de datos de BizTalk con el nuevo nombre del servidor](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB).</span><span class="sxs-lookup"><span data-stu-id="012ac-131">See [To update BizTalk Databases with the new server name](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB).</span></span>  
  
-   <span data-ttu-id="012ac-132">Actualice el archivo Web.config del portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="012ac-132">Update the Web.config file for the BAM portal.</span></span> <span data-ttu-id="012ac-133">Vea [para actualizar el archivo Web.config del portal de BAM](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config).</span><span class="sxs-lookup"><span data-stu-id="012ac-133">See [To update the Web.config file for the BAM portal](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config).</span></span>  
  
-   <span data-ttu-id="012ac-134">Actualizar la referencia a BAM Importar base de datos principal en todos los archivos de Excel de Microsoft de datos activos de BAM.</span><span class="sxs-lookup"><span data-stu-id="012ac-134">Update the reference to the BAM Primary Import Database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="012ac-135">Vea [para actualizar la referencia en los archivos de Excel de Microsoft de datos activos de BAM](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel).</span><span class="sxs-lookup"><span data-stu-id="012ac-135">See [To update reference in BAM Livedata Microsoft Excel files](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel).</span></span>  
  
-   <span data-ttu-id="012ac-136">Actualice los nombres de servidor y base de datos nueva en todos los paquetes SSIS de análisis BAM.</span><span class="sxs-lookup"><span data-stu-id="012ac-136">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="012ac-137">Vea [para actualizar los nombres de servidor y base de datos en todos los paquetes SSIS de BAM](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg).</span><span class="sxs-lookup"><span data-stu-id="012ac-137">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg).</span></span>  
  
-   <span data-ttu-id="012ac-138">Actualice los nombres de servidor y base de datos nueva en orígenes de datos para todos los cubos OLAP.</span><span class="sxs-lookup"><span data-stu-id="012ac-138">Update the new server and database names in data sources for all OLAP cubes.</span></span> <span data-ttu-id="012ac-139">Vea [para actualizar los nombres de servidor y base de datos en orígenes de datos para todos los cubos OLAP](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP).</span><span class="sxs-lookup"><span data-stu-id="012ac-139">See [To update server and database names in data sources for all OLAP cubes](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP).</span></span>  
  
###  <a name="BKMK_UpdateDB"></a> <span data-ttu-id="012ac-140">Para actualizar las bases de datos de BizTalk con el nuevo nombre del servidor</span><span class="sxs-lookup"><span data-stu-id="012ac-140">To update BizTalk Databases with the new server name</span></span>  
  
1.  <span data-ttu-id="012ac-141">En un equipo que ejecuta BizTalk Server, vaya a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="012ac-141">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
    -   <span data-ttu-id="012ac-142">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="012ac-142">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="012ac-143">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\bins32\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="012ac-143">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\bins32\Schema\Restore**</span></span>  
  
    -   <span data-ttu-id="012ac-144">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="012ac-144">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="012ac-145">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="012ac-145">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span></span>  
  
2.  <span data-ttu-id="012ac-146">Haga clic en **SampleUpdateInfo.xml**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-146">Right-click **SampleUpdateInfo.xml**, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="012ac-147">Convierta en comentario todas las secciones de bases de datos, a excepción de BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert.</span><span class="sxs-lookup"><span data-stu-id="012ac-147">Comment out all of the database sections except for the BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert.</span></span>  
  
4.  <span data-ttu-id="012ac-148">En el `OldPrimaryImportDatabase` sección del archivo, para la `ServerName` propiedad, reemplace **SourceServer** con el nombre de servidor existente en el que reside la base de datos.</span><span class="sxs-lookup"><span data-stu-id="012ac-148">In the `OldPrimaryImportDatabase` section of the file, for the `ServerName` property, replace **SourceServer** with the name of existing server where the database resides.</span></span>  
  
5.  <span data-ttu-id="012ac-149">En el `PrimaryImportDatabase` sección del archivo, para la `ServerName` propiedad, reemplace **DestinationServer** con el nombre del servidor donde se ha movido la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="012ac-149">In the `PrimaryImportDatabase` section of the file, for the `ServerName` property, replace **DestinationServer** with the name of the server where you have moved the BAM Primary Import database</span></span>  
  
6.  <span data-ttu-id="012ac-150">Para la BizTalkMgmtDb, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert secciones, establezca el "SourceServer" y "Servidor de destino" en el nombre del servidor existente donde residen las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="012ac-150">For the BizTalkMgmtDb, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert sections, set the "SourceServer" and "Destination Server" to the name of the existing server where those databases reside.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="012ac-151">Flanquee el nombre de los sistemas de origen y destino con comillas.</span><span class="sxs-lookup"><span data-stu-id="012ac-151">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="012ac-152">Si cambia el nombre de alguna de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], también deberá actualizar los nombres de las bases de datos según corresponda.</span><span class="sxs-lookup"><span data-stu-id="012ac-152">If you renamed any of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must also update the database names as appropriate.</span></span>  
  
7.  <span data-ttu-id="012ac-153">Cuando haya terminado de editar el archivo, guárdelo y salga de él.</span><span class="sxs-lookup"><span data-stu-id="012ac-153">When you are finished editing the file, save it and exit.</span></span>  
  
8.  <span data-ttu-id="012ac-154">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-154">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="012ac-155">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="012ac-155">At the command prompt, navigate to the following directory:</span></span>  
  
    -   <span data-ttu-id="012ac-156">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="012ac-156">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="012ac-157">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="012ac-157">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Schema\Restore**</span></span>  
  
    -   <span data-ttu-id="012ac-158">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="012ac-158">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="012ac-159">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="012ac-159">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span></span>  
  
10. <span data-ttu-id="012ac-160">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="012ac-160">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="012ac-161">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="012ac-161">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
###  <a name="BKMK_Config"></a> <span data-ttu-id="012ac-162">Para actualizar el archivo Web.config del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="012ac-162">To update the Web.config file for the BAM portal</span></span>  
  
1.  <span data-ttu-id="012ac-163">En un equipo que ejecuta BizTalk Server, actualice los archivos Web.config en  **\<unidad\>: \Program 2010\BAMPortal\BAMManagementService\Web.Config BizTalk Server**. Actualice los nombres de servidor y base de datos en la sección siguiente en el archivo Web.config:</span><span class="sxs-lookup"><span data-stu-id="012ac-163">On a computer running BizTalk Server, update the Web.config files under **\<drive\>:\Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMManagementService\Web.Config**. Update the server and database names in the following section in the Web.config:</span></span>  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
    </appSettings>  
    ```  
  
2.  <span data-ttu-id="012ac-164">En un equipo que ejecuta BizTalk Server, actualice los archivos Web.config en  **\<unidad\>: \Program 2010\BAMPortal\BAMQueryService\Web.Config BizTalk Server**. Actualice los nombres de servidor y base de datos en la sección siguiente en el archivo Web.config:</span><span class="sxs-lookup"><span data-stu-id="012ac-164">On a computer running BizTalk Server, update the Web.config files under **\<drive\>:\Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMQueryService\Web.Config**. Update the server and database names in the following section in the Web.config:</span></span>  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
      <add key="MaxResultRows" value="2000" />  
    </appSettings>  
    ```  
  
3.  <span data-ttu-id="012ac-165">Guarde y cierre los archivos.</span><span class="sxs-lookup"><span data-stu-id="012ac-165">Save and close the files.</span></span>  
  
###  <a name="BKMK_UpdateExcel"></a> <span data-ttu-id="012ac-166">Para actualizar la referencia en los archivos de Excel de Microsoft de datos activos de BAM</span><span class="sxs-lookup"><span data-stu-id="012ac-166">To update reference in BAM Livedata Microsoft Excel files</span></span>  
  
1.  <span data-ttu-id="012ac-167">Abra el archivo de datos activos de Excel.</span><span class="sxs-lookup"><span data-stu-id="012ac-167">Open the Excel live data file.</span></span> <span data-ttu-id="012ac-168">El nombre de archivo finaliza con _LiveData.xls.</span><span class="sxs-lookup"><span data-stu-id="012ac-168">The file name ends with _LiveData.xls.</span></span>  
  
2.  <span data-ttu-id="012ac-169">En el **BAM** menú, haga clic en **conexión de base de datos de BAM**.</span><span class="sxs-lookup"><span data-stu-id="012ac-169">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
3.  <span data-ttu-id="012ac-170">En el **Seleccionar base de datos de BAM** diálogo cuadro, escriba la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo y BAMPrimaryImport la base de datos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-170">In the **Select BAM Database** dialog box, enter the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer and the BAMPrimaryImport database, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="012ac-171">En el **archivo** menú, haga clic en **cerrar y volver a Microsoft Excel**.</span><span class="sxs-lookup"><span data-stu-id="012ac-171">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
5.  <span data-ttu-id="012ac-172">En el menú **Archivo** , haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-172">On the **File** menu, click **Save**.</span></span>  
  
###  <a name="BKMK_UpdatePckg"></a> <span data-ttu-id="012ac-173">Para actualizar los nombres de servidor y base de datos en todos los paquetes SSIS de BAM</span><span class="sxs-lookup"><span data-stu-id="012ac-173">To update server and database names in all BAM SSIS packages</span></span>  
  
1.  <span data-ttu-id="012ac-174">Actualice los nombres de servidor y base de datos en todos los paquetes SSIS análisis BAM, que tienen el prefijo "BAM_AN_" o "BAM_DM_".</span><span class="sxs-lookup"><span data-stu-id="012ac-174">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_AN_" or "BAM_DM_".</span></span> <span data-ttu-id="012ac-175">Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="012ac-175">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="012ac-176">En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="012ac-176">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="012ac-177">Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="012ac-177">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="012ac-178">En el **nuevo proyecto** cuadro de diálogo, en la **tipos de proyecto** cuadro, haga clic en **proyectos de Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="012ac-178">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="012ac-179">En el panel derecho, en la **plantillas** cuadro, haga clic en **proyecto de Integration Services**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-179">In the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="012ac-180">En el **proyecto de Integration Services** cuadro de diálogo, en el Explorador de soluciones, haga clic en **paquetes SSIS**y, a continuación, haga clic en **Agregar paquete existente**.</span><span class="sxs-lookup"><span data-stu-id="012ac-180">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5.  <span data-ttu-id="012ac-181">En el **Agregar copia de paquete existente** cuadro de diálogo, en la **Server** lista desplegable, seleccione el servidor que contiene los paquetes BAM_AN_ * y BAM_DM_ *.</span><span class="sxs-lookup"><span data-stu-id="012ac-181">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN_* and BAM_DM_* packages.</span></span>  
  
6.  <span data-ttu-id="012ac-182">En **ruta de acceso del paquete**, haga clic en el botón de puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="012ac-182">In **Package Path**, click the ellipses button.</span></span>  
  
7.  <span data-ttu-id="012ac-183">En el **paquete SSIS** cuadro de diálogo, seleccione el paquete que desea actualizar, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-183">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="012ac-184">Con ello, el paquete aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="012ac-184">The package is now listed in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="012ac-185">En el Explorador de soluciones, haga doble clic en el paquete que agregó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="012ac-185">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="012ac-186">En **administradores de conexión** pestaña (disponible hacia la parte inferior de la pantalla), haga doble clic en el número de origen de datos 1 (base de datos BAMPrimaryImport).</span><span class="sxs-lookup"><span data-stu-id="012ac-186">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 1 (BAMPrimaryImport database).</span></span>  
  
9. <span data-ttu-id="012ac-187">En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-187">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="012ac-188">Haga clic en el **Explorador de paquetes** ficha, haga doble clic en el **Variables** carpeta y, a continuación, actualice los valores de la **PrimaryImportDatabase** y  **PrimaryImportServer** variables.</span><span class="sxs-lookup"><span data-stu-id="012ac-188">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **PrimaryImportDatabase** and **PrimaryImportServer** variables.</span></span> <span data-ttu-id="012ac-189">Debe actualizar los valores para que apunte al nuevo servidor y base de datos.</span><span class="sxs-lookup"><span data-stu-id="012ac-189">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="012ac-190">Repita el paso 4 y 10 para todos los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="012ac-190">Repeat step 4 through 10 for all the packages that you want to update.</span></span>  
  
11. <span data-ttu-id="012ac-191">Haga clic en, a continuación, **archivo** menú y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="012ac-191">Click then **File** menu, and then click **Save All**.</span></span>  
  
12. <span data-ttu-id="012ac-192">Inicie SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="012ac-192">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="012ac-193">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en  **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="012ac-193">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
13. <span data-ttu-id="012ac-194">En el **conectar al servidor** cuadro de diálogo, desde el **Server** lista de tipo de lista desplegable, seleccione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="012ac-194">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
14. <span data-ttu-id="012ac-195">Especifique el nombre del servidor y las credenciales para conectarse al servidor y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-195">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
15. <span data-ttu-id="012ac-196">En el **Explorador de objetos**, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.</span><span class="sxs-lookup"><span data-stu-id="012ac-196">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
16. <span data-ttu-id="012ac-197">En el **detalles del explorador de objetos** pestaña, haga clic en el paquete que actualizó anteriormente y, a continuación, haga clic en **Importar paquete**.</span><span class="sxs-lookup"><span data-stu-id="012ac-197">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
17. <span data-ttu-id="012ac-198">En el **Importar paquete** cuadro de diálogo, desde el **ubicación del paquete** lista desplegable, seleccione **sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="012ac-198">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
18. <span data-ttu-id="012ac-199">En **ruta de acceso del paquete**, navegue al proyecto guardado, seleccione el archivo DTSX para el paquete que desea importar y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="012ac-199">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
19. <span data-ttu-id="012ac-200">Haga clic dentro del cuadro Nombre del paquete para rellenar automáticamente el cuadro.</span><span class="sxs-lookup"><span data-stu-id="012ac-200">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="012ac-201">Repita el paso 16 al 19 para todos los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="012ac-201">Repeat step 16 through 19 for all the packages that you want to update.</span></span>  
  
20. <span data-ttu-id="012ac-202">Haga clic en **Aceptar**y, a continuación, haga clic en **Sí** para sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="012ac-202">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
21. <span data-ttu-id="012ac-203">Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.</span><span class="sxs-lookup"><span data-stu-id="012ac-203">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
###  <a name="BKMK_UpdateDSOLAP"></a> <span data-ttu-id="012ac-204">Para actualizar los nombres de servidor y base de datos en orígenes de datos para todos los cubos OLAP</span><span class="sxs-lookup"><span data-stu-id="012ac-204">To update server and database names in data sources for all OLAP cubes</span></span>  
  
1.  <span data-ttu-id="012ac-205">Actualice los nombres de servidor y base de datos en orígenes de datos para todos los cubos OLAP.</span><span class="sxs-lookup"><span data-stu-id="012ac-205">Update the server and database names in data sources for all OLAP cubes.</span></span> <span data-ttu-id="012ac-206">Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="012ac-206">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="012ac-207">En el **conectar al servidor** cuadro de diálogo para la **tipo de servidor** lista desplegable, seleccione **Analysis Services**, proporcione el nombre del servidor, seleccione un método de autenticación (y Proporcione credenciales si es necesario) y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-207">In the **Connect to Server** dialog box, for the **Server type** drop-down list select **Analysis Services**, provide the server name, select an authentication method (and provide credentials if required), and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="012ac-208">En el Explorador de objetos, expanda **bases de datos**, expanda **BAMAnalysis**, expanda **orígenes de datos**y, a continuación, haga doble clic en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="012ac-208">In the Object Explorer, expand **Databases**, expand **BAMAnalysis**, expand **Data Sources**, and then double-click a data source.</span></span>  
  
4.  <span data-ttu-id="012ac-209">En el **propiedades del origen de datos** diálogo cuadro, haga clic en el botón de puntos suspensivos **(...)**  contra la **cadena de conexión** propiedad.</span><span class="sxs-lookup"><span data-stu-id="012ac-209">In the **Data Source Properties** dialog box, click the ellipsis button **(…)** against the **Connection String** property.</span></span>  
  
5.  <span data-ttu-id="012ac-210">En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor que hospeda la base de datos BAMPrimaryImport, haga clic en **Aceptar**y, a continuación, haga clic en  **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-210">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server hosting the BAMPrimaryImport database, click **OK**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="012ac-211">Iniciar todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios.</span><span class="sxs-lookup"><span data-stu-id="012ac-211">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="012ac-212">Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="012ac-212">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
7.  <span data-ttu-id="012ac-213">Inicia el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="012ac-213">Start the IIS service.</span></span>  
  
8.  <span data-ttu-id="012ac-214">Inicie el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="012ac-214">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="012ac-215">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="012ac-215">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="012ac-216">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="012ac-216">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="012ac-217">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="012ac-217">**Net start NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="012ac-218">Resolver todas las instancias incompletas de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="012ac-218">Resolve any incomplete trace instances.</span></span>  <span data-ttu-id="012ac-219">Para obtener información acerca de cómo resolver instancias incompletas de actividad BAM, consulte [cómo resolver instancias de actividad incompletas](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).</span><span class="sxs-lookup"><span data-stu-id="012ac-219">For information about resolving incomplete BAM activity instances, see [How to Resolve Incomplete Activity Instances](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="012ac-220">Vea también</span><span class="sxs-lookup"><span data-stu-id="012ac-220">See Also</span></span>  
 [<span data-ttu-id="012ac-221">Mover bases de datos</span><span class="sxs-lookup"><span data-stu-id="012ac-221">Moving Databases</span></span>](../technical-guides/moving-databases.md)