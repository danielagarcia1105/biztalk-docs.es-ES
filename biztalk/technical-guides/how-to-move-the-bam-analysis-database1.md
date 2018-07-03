---
title: Cómo mover la base de datos1 del análisis BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8094153-072b-427a-b3a0-7310a37cf584
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c73b3c4fbadf44cb8031af3826c6b507d77e2f48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980733"
---
# <a name="how-to-move-the-bam-analysis-database"></a><span data-ttu-id="cb226-102">Cómo mover la base de datos de análisis de BAM</span><span class="sxs-lookup"><span data-stu-id="cb226-102">How to Move the BAM Analysis Database</span></span>
<span data-ttu-id="cb226-103">Este procedimiento se puede utilizar para mover la base de datos de análisis de BAM a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="cb226-103">You can use this procedure to move the BAM Analysis database to another server.</span></span>  <span data-ttu-id="cb226-104">Desde una perspectiva de escenario de extremo a otro, mover la base de datos de análisis de BAM consta de dos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="cb226-104">From an end-to-end scenario perspective, moving the BAM Analysis database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="cb226-105">Mover la base de datos de análisis BAM</span><span class="sxs-lookup"><span data-stu-id="cb226-105">Moving the BAM Analysis Database</span></span>](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyMoveDB)  
  
-   [<span data-ttu-id="cb226-106">Actualizar las referencias a la nueva base de datos de análisis BAM</span><span class="sxs-lookup"><span data-stu-id="cb226-106">Updating References to the New BAM Analysis Database</span></span>](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)  
  
## <a name="prerequisites"></a><span data-ttu-id="cb226-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cb226-107">Prerequisites</span></span>  
 <span data-ttu-id="cb226-108">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb226-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_AnalyMoveDB"></a> <span data-ttu-id="cb226-109">Mover la base de datos de análisis BAM</span><span class="sxs-lookup"><span data-stu-id="cb226-109">Moving the BAM Analysis Database</span></span>  
 <span data-ttu-id="cb226-110">Realice los pasos en el siguiente procedimiento para mover la base de datos de análisis de BAM.</span><span class="sxs-lookup"><span data-stu-id="cb226-110">Perform the steps in the following procedure to move the BAM Analysis database.</span></span>  
  
#### <a name="to-move-the-bam-analysis-database"></a><span data-ttu-id="cb226-111">Para mover la base de datos de análisis de BAM</span><span class="sxs-lookup"><span data-stu-id="cb226-111">To move the BAM Analysis database</span></span>  
  
1. <span data-ttu-id="cb226-112">Detenga todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE, o impida su ejecución hasta que se haya restaurado la base de datos de análisis de SAE.</span><span class="sxs-lookup"><span data-stu-id="cb226-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Analysis database.</span></span>  
  
2. <span data-ttu-id="cb226-113">Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb226-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="cb226-114">Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="cb226-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3. <span data-ttu-id="cb226-115">Detenga el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="cb226-115">Stop the IIS service.</span></span>  
  
4. <span data-ttu-id="cb226-116">Detenga el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="cb226-116">Stop the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="cb226-117">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb226-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="cb226-118">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="cb226-118">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="cb226-119">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="cb226-119">**Net stop NS$BamAlerts**</span></span>  
  
5. <span data-ttu-id="cb226-120">Copia de seguridad de la base de datos de análisis de BAM del antiguo servidor.</span><span class="sxs-lookup"><span data-stu-id="cb226-120">Back up the BAM Analysis database on the old server.</span></span> <span data-ttu-id="cb226-121">Para obtener instrucciones sobre copias de una base de datos, siga las instrucciones de [Cómo: copia de una base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros acerca de cómo realizar copias de seguridad de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="cb226-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6. <span data-ttu-id="cb226-122">Copie la base de datos de análisis de BAM en el nuevo [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.</span><span class="sxs-lookup"><span data-stu-id="cb226-122">Copy the BAM Analysis database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7. <span data-ttu-id="cb226-123">Restaure la base de datos de análisis de BAM en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="cb226-123">Restore the BAM Analysis database on the new server.</span></span> <span data-ttu-id="cb226-124">Para obtener instrucciones sobre cómo restaurar la base de datos, siga las instrucciones de [Cómo: restaurar una copia de seguridad de base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla sobre cómo restaurar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="cb226-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <a name="BKMK_AnalyUpdate"></a> <span data-ttu-id="cb226-125">Actualizar las referencias a la nueva base de datos de análisis BAM</span><span class="sxs-lookup"><span data-stu-id="cb226-125">Updating References to the New BAM Analysis Database</span></span>  
 <span data-ttu-id="cb226-126">Después de haber movido la base de datos, debe actualizar todas las referencias a la nueva base de datos de análisis de BAM.</span><span class="sxs-lookup"><span data-stu-id="cb226-126">After you have moved the database, you must update all the references to the new BAM Analysis Database.</span></span> <span data-ttu-id="cb226-127">Deben actualizarse las referencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb226-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="cb226-128">Actualice la configuración de BAM con los nuevos nombres de base de datos y el servidor.</span><span class="sxs-lookup"><span data-stu-id="cb226-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="cb226-129">Consulte [para actualizar la configuración de BAM](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateBAMConfig).</span><span class="sxs-lookup"><span data-stu-id="cb226-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateBAMConfig).</span></span>  
  
-   <span data-ttu-id="cb226-130">Actualice los nombres de servidor y base de datos nueva en todos los paquetes SSIS de análisis BAM.</span><span class="sxs-lookup"><span data-stu-id="cb226-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="cb226-131">Consulte [para actualizar los nombres del servidor y base de datos en todos los paquetes de SSIS de BAM](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateSSIS).</span><span class="sxs-lookup"><span data-stu-id="cb226-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateSSIS).</span></span>  
  
###  <a name="BKMK_AnalyUpdateBAMConfig"></a> <span data-ttu-id="cb226-132">Para actualizar la configuración de BAM</span><span class="sxs-lookup"><span data-stu-id="cb226-132">To update the BAM configuration</span></span>  
  
1. <span data-ttu-id="cb226-133">Obtenga una copia del archivo .xml utilizado para restaurar BAM:</span><span class="sxs-lookup"><span data-stu-id="cb226-133">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="cb226-134">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb226-134">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="cb226-135">En un equipo que ejecuta BizTalk Server, vaya a la carpeta siguiente:</span><span class="sxs-lookup"><span data-stu-id="cb226-135">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
      - <span data-ttu-id="cb226-136">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="cb226-136">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="cb226-137">**% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="cb226-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
      - <span data-ttu-id="cb226-138">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="cb226-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="cb226-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="cb226-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   3. <span data-ttu-id="cb226-140">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="cb226-140">At the command prompt, type:</span></span>  
  
       <span data-ttu-id="cb226-141">**Bm.exe get-config –filename:BAMConfiguration.xml-server:\<servername\> -base de datos:\<base de datos\>**</span><span class="sxs-lookup"><span data-stu-id="cb226-141">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="cb226-142">Al ejecutar este comando, sustituya el nombre real del servidor desde el que se va a obtener la información de configuración \<servername\> y sustituya el nombre real de la base de datos que se va a obtener la información de configuración \<base de datos\>.</span><span class="sxs-lookup"><span data-stu-id="cb226-142">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername\> and substitute the actual name of the database from which to get the configuration information for \<database\>.</span></span> <span data-ttu-id="cb226-143">Para obtener más información sobre el uso de la utilidad de administración de BAM (BM), consulte [comandos de administración de infraestructura](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="cb226-143">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2. <span data-ttu-id="cb226-144">Edite el archivo BAMConfiguration.xml y cambie el **ServerName** en la `<DeploymentUnit Name="AnalysisDatabase">` sección para el nuevo nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="cb226-144">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="AnalysisDatabase">` section to the new server name.</span></span>  
  
3. <span data-ttu-id="cb226-145">Guarde el archivo BAMConfiguration.xml y ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="cb226-145">Save and close the BAMConfiguration.xml file.</span></span>  
  
4. <span data-ttu-id="cb226-146">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb226-146">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="cb226-147">En un equipo que ejecuta BizTalk Server, vaya a la carpeta siguiente:</span><span class="sxs-lookup"><span data-stu-id="cb226-147">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
   - <span data-ttu-id="cb226-148">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="cb226-148">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="cb226-149">**% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="cb226-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   - <span data-ttu-id="cb226-150">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="cb226-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="cb226-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="cb226-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6. <span data-ttu-id="cb226-152">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="cb226-152">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="cb226-153">**bm.exe update-config-FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="cb226-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_AnalyUpdateSSIS"></a> <span data-ttu-id="cb226-154">Para actualizar los nombres del servidor y base de datos en todos los paquetes de SSIS de BAM</span><span class="sxs-lookup"><span data-stu-id="cb226-154">To update server and database names in all BAM SSIS packages</span></span>  
  
1. <span data-ttu-id="cb226-155">Actualice los nombres de servidor y base de datos en todos los paquetes SSIS análisis BAM, que tienen el prefijo "Bam_an_".</span><span class="sxs-lookup"><span data-stu-id="cb226-155">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_AN_".</span></span> <span data-ttu-id="cb226-156">Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="cb226-156">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2. <span data-ttu-id="cb226-157">En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="cb226-157">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="cb226-158">Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="cb226-158">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="cb226-159">En el **nuevo proyecto** cuadro de diálogo el **tipos de proyecto** cuadro, haga clic en **proyectos de Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="cb226-159">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="cb226-160">En el **Explorador de objetos**, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en MSDB.</span><span class="sxs-lookup"><span data-stu-id="cb226-160">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="cb226-161">En el **detalles del explorador de objetos** pestaña, haga clic en el paquete que se ha actualizado anteriormente y, a continuación, haga clic en **Importar paquete**.</span><span class="sxs-lookup"><span data-stu-id="cb226-161">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5. <span data-ttu-id="cb226-162">En el **Importar paquete** cuadro de diálogo desde el **ubicación del paquete** lista desplegable, seleccione sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="cb226-162">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN_\* packages.</span></span>  
  
6. <span data-ttu-id="cb226-163">En **ruta de acceso de paquete**, vaya al proyecto guardado, seleccione el archivo. dtsx para el paquete que desea importar y, a continuación, haga clic en abierto.</span><span class="sxs-lookup"><span data-stu-id="cb226-163">In **Package Path**, click the ellipses button.</span></span>  
  
7. <span data-ttu-id="cb226-164">Haga clic en el cuadro Nombre del paquete para rellenar automáticamente el cuadro.</span><span class="sxs-lookup"><span data-stu-id="cb226-164">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="cb226-165">Con ello, el paquete aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="cb226-165">The package is now listed in Solution Explorer.</span></span>  
  
8. <span data-ttu-id="cb226-166">Repita el paso 18 al 21 para todos los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="cb226-166">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="cb226-167">Haga clic en **Aceptar**y, a continuación, haga clic en Sí para sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="cb226-167">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMArchive database).</span></span>  
  
9. <span data-ttu-id="cb226-168">Iniciar todos ** servicios.</span><span class="sxs-lookup"><span data-stu-id="cb226-168">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cb226-169">Inicie el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="cb226-169">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="cb226-170">Net start NS$ BamAlerts</span><span class="sxs-lookup"><span data-stu-id="cb226-170">In the **Connection Managers** tab, double-click data source number 4 (BAMAnalysis database).</span></span> <span data-ttu-id="cb226-171">En el **Agregar administrador de conexiones de Analysis Services** cuadro de diálogo, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="cb226-171">In the **Add Analysis Services Connection Manager** dialog box, click **Edit**.</span></span>  
  
11. <span data-ttu-id="cb226-172">En el **Connection Manager** cuadro de diálogo el **nombre del servidor** cuadro, escriba el nombre del servidor, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb226-172">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, click **OK**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="cb226-173">Haga clic en el **Explorador de paquetes** pestaña, haga doble clic en el **Variables** carpeta y, a continuación, actualice los valores para el **AnalysisDatabase**, **AnalysisServer** , **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, y **StarSchemaServer** variables.</span><span class="sxs-lookup"><span data-stu-id="cb226-173">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **AnalysisDatabase**, **AnalysisServer**, **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, and **StarSchemaServer** variables.</span></span> <span data-ttu-id="cb226-174">Debe actualizar los valores para que apunte al nuevo servidor y base de datos.</span><span class="sxs-lookup"><span data-stu-id="cb226-174">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cb226-175">Repita el paso 4 y 12 para todos los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="cb226-175">Repeat step 4 through 12 for all the packages that you want to update.</span></span>  
  
13. <span data-ttu-id="cb226-176">Haga clic en, a continuación, **archivo** menú y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="cb226-176">Click then **File** menu, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="cb226-177">Inicie SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="cb226-177">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="cb226-178">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en  **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="cb226-178">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
15. <span data-ttu-id="cb226-179">En el **conectar al servidor** cuadro de diálogo desde el **Server** lista desplegable de tipo, seleccione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="cb226-179">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
16. <span data-ttu-id="cb226-180">Especifique el nombre del servidor y las credenciales para conectarse al servidor y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb226-180">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
17. <span data-ttu-id="cb226-181">En el **Explorador de objetos**, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.</span><span class="sxs-lookup"><span data-stu-id="cb226-181">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
18. <span data-ttu-id="cb226-182">En el **detalles del explorador de objetos** pestaña, haga clic en el paquete que se ha actualizado anteriormente y, a continuación, haga clic en **Importar paquete**.</span><span class="sxs-lookup"><span data-stu-id="cb226-182">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
19. <span data-ttu-id="cb226-183">En el **Importar paquete** cuadro de diálogo desde el **ubicación del paquete** lista desplegable, seleccione **sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="cb226-183">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
20. <span data-ttu-id="cb226-184">En **ruta de acceso de paquete**, vaya al proyecto guardado, seleccione el archivo. dtsx para el paquete que desea importar y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="cb226-184">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
21. <span data-ttu-id="cb226-185">Haga clic en el cuadro Nombre del paquete para rellenar automáticamente el cuadro.</span><span class="sxs-lookup"><span data-stu-id="cb226-185">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cb226-186">Repita el paso 18 al 21 para todos los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="cb226-186">Repeat step 18 through 21 for all the packages that you want to update.</span></span>  
  
22. <span data-ttu-id="cb226-187">Haga clic en **Aceptar**y, a continuación, haga clic en **Sí** para sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="cb226-187">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
23. <span data-ttu-id="cb226-188">Iniciar todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios.</span><span class="sxs-lookup"><span data-stu-id="cb226-188">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="cb226-189">Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="cb226-189">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
24. <span data-ttu-id="cb226-190">Inicia el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="cb226-190">Start the IIS service.</span></span>  
  
25. <span data-ttu-id="cb226-191">Inicie el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="cb226-191">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="cb226-192">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb226-192">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="cb226-193">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="cb226-193">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="cb226-194">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="cb226-194">**Net start NS$BamAlerts**</span></span>  
  
26. <span data-ttu-id="cb226-195">Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.</span><span class="sxs-lookup"><span data-stu-id="cb226-195">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb226-196">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb226-196">See Also</span></span>  
 [<span data-ttu-id="cb226-197">Mover bases de datos</span><span class="sxs-lookup"><span data-stu-id="cb226-197">Moving Databases</span></span>](../technical-guides/moving-databases.md)