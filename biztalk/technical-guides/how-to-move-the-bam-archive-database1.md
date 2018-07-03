---
title: Cómo mover la base de datos1 del archivo BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e371321c-6b8d-4be6-a6d2-926f6218db01
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84dda0937fc0c7b060e483b2ca1585a3d5160ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023410"
---
# <a name="how-to-move-the-bam-archive-database"></a><span data-ttu-id="97ded-102">Cómo mover la base de datos de archivo de BAM</span><span class="sxs-lookup"><span data-stu-id="97ded-102">How to Move the BAM Archive Database</span></span>
<span data-ttu-id="97ded-103">Este procedimiento se puede utilizar para mover la base de datos de archivo de BAM a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="97ded-103">You can use this procedure to move the BAM Archive database to another server.</span></span>  <span data-ttu-id="97ded-104">Desde una perspectiva de escenario de extremo a otro, mover la base de datos de archivo de BAM consta de dos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="97ded-104">From an end-to-end scenario perspective, moving the BAM Archive database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="97ded-105">Mover la base de datos de archivo BAM</span><span class="sxs-lookup"><span data-stu-id="97ded-105">Moving the BAM Archive Database</span></span>](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_MovingArch)  
  
-   [<span data-ttu-id="97ded-106">Actualizar las referencias a la nueva base de datos de archivo BAM</span><span class="sxs-lookup"><span data-stu-id="97ded-106">Updating References to the New BAM Archive Database</span></span>](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)  
  
## <a name="prerequisites"></a><span data-ttu-id="97ded-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="97ded-107">Prerequisites</span></span>  
 <span data-ttu-id="97ded-108">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97ded-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_MovingArch"></a> <span data-ttu-id="97ded-109">Mover la base de datos de archivo BAM</span><span class="sxs-lookup"><span data-stu-id="97ded-109">Moving the BAM Archive Database</span></span>  
 <span data-ttu-id="97ded-110">Realice los pasos en el siguiente procedimiento para mover la base de datos de archivo de BAM.</span><span class="sxs-lookup"><span data-stu-id="97ded-110">Perform the steps in the following procedure to move the BAM Archive database.</span></span>  
  
#### <a name="to-move-the-bam-archive-database"></a><span data-ttu-id="97ded-111">Para mover la base de datos de archivo de BAM</span><span class="sxs-lookup"><span data-stu-id="97ded-111">To move the BAM Archive database</span></span>  
  
1. <span data-ttu-id="97ded-112">Detenga cualquier BAM cubo datos y actualización mantenimiento paquetes SSIS, o impida su ejecución hasta que haya restaurado la base de datos de archivo de BAM.</span><span class="sxs-lookup"><span data-stu-id="97ded-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Archive database.</span></span>  
  
2. <span data-ttu-id="97ded-113">Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97ded-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="97ded-114">Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="97ded-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3. <span data-ttu-id="97ded-115">Detenga el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="97ded-115">Stop the IIS service.</span></span>  
  
4. <span data-ttu-id="97ded-116">Detenga el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="97ded-116">Stop the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="97ded-117">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97ded-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="97ded-118">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="97ded-118">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="97ded-119">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="97ded-119">**Net stop NS$BamAlerts**</span></span>  
  
5. <span data-ttu-id="97ded-120">Copia de seguridad de la base de datos de archivo de BAM del antiguo servidor.</span><span class="sxs-lookup"><span data-stu-id="97ded-120">Back up the BAM Archive database on the old server.</span></span> <span data-ttu-id="97ded-121">Para obtener instrucciones sobre copias de una base de datos, siga las instrucciones de [Cómo: copia de una base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros acerca de cómo realizar copias de seguridad de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="97ded-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6. <span data-ttu-id="97ded-122">Copie la base de datos de archivo de BAM en el nuevo [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.</span><span class="sxs-lookup"><span data-stu-id="97ded-122">Copy the BAM Archive database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7. <span data-ttu-id="97ded-123">Restaure la base de datos de archivo de BAM en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="97ded-123">Restore the BAM Archive database on the new server.</span></span> <span data-ttu-id="97ded-124">Para obtener instrucciones sobre cómo restaurar la base de datos, siga las instrucciones de [Cómo: restaurar una copia de seguridad de base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla sobre cómo restaurar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="97ded-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <a name="BKMK_UpdateArch"></a> <span data-ttu-id="97ded-125">Actualizar las referencias a la nueva base de datos de archivo BAM</span><span class="sxs-lookup"><span data-stu-id="97ded-125">Updating References to the New BAM Archive Database</span></span>  
 <span data-ttu-id="97ded-126">Después de haber movido la base de datos, debe actualizar todas las referencias a la nueva base de datos de archivo de BAM.</span><span class="sxs-lookup"><span data-stu-id="97ded-126">After you have moved the database, you must update all the references to the new BAM Archive Database.</span></span> <span data-ttu-id="97ded-127">Deben actualizarse las referencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="97ded-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="97ded-128">Actualice la configuración de BAM con los nuevos nombres de base de datos y el servidor.</span><span class="sxs-lookup"><span data-stu-id="97ded-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="97ded-129">Consulte [para actualizar la configuración de BAM](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig).</span><span class="sxs-lookup"><span data-stu-id="97ded-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig).</span></span>  
  
-   <span data-ttu-id="97ded-130">Actualice los nombres de servidor y base de datos nueva en todos los paquetes SSIS de análisis BAM.</span><span class="sxs-lookup"><span data-stu-id="97ded-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="97ded-131">Consulte [para actualizar los nombres del servidor y base de datos en todos los paquetes de SSIS de BAM](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS).</span><span class="sxs-lookup"><span data-stu-id="97ded-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS).</span></span>  
  
###  <a name="BKMK_UpdateArchConfig"></a> <span data-ttu-id="97ded-132">Para actualizar la configuración de BAM</span><span class="sxs-lookup"><span data-stu-id="97ded-132">To update the BAM configuration</span></span>  
  
1. <span data-ttu-id="97ded-133">Obtenga una copia del archivo .xml utilizado para restaurar BAM:</span><span class="sxs-lookup"><span data-stu-id="97ded-133">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="97ded-134">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97ded-134">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="97ded-135">En un equipo que ejecuta BizTalk Server, vaya a la carpeta siguiente:</span><span class="sxs-lookup"><span data-stu-id="97ded-135">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
      - <span data-ttu-id="97ded-136">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="97ded-136">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="97ded-137">**% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="97ded-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
      - <span data-ttu-id="97ded-138">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="97ded-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="97ded-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="97ded-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   3. <span data-ttu-id="97ded-140">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="97ded-140">At the command prompt, type:</span></span>  
  
       <span data-ttu-id="97ded-141">**Bm.exe get-config –filename:BAMConfiguration.xml-server:\<servername\> -base de datos:\<base de datos\>**</span><span class="sxs-lookup"><span data-stu-id="97ded-141">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="97ded-142">Al ejecutar este comando, sustituya el nombre real del servidor desde el que se va a obtener la información de configuración \<servername\> y sustituya el nombre real de la base de datos que se va a obtener la información de configuración \<base de datos\>.</span><span class="sxs-lookup"><span data-stu-id="97ded-142">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername\> and substitute the actual name of the database from which to get the configuration information for \<database\>.</span></span> <span data-ttu-id="97ded-143">Para obtener más información sobre el uso de la utilidad de administración de BAM (BM), consulte [comandos de administración de infraestructura](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="97ded-143">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2. <span data-ttu-id="97ded-144">Edite el archivo BAMConfiguration.xml y cambie el **ServerName** en la `<DeploymentUnit Name="ArchivingDatabase">` sección para el nuevo nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="97ded-144">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="ArchivingDatabase">` section to the new server name.</span></span>  
  
3. <span data-ttu-id="97ded-145">Guarde el archivo BAMConfiguration.xml y ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="97ded-145">Save and close the BAMConfiguration.xml file.</span></span>  
  
4. <span data-ttu-id="97ded-146">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97ded-146">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="97ded-147">En un equipo que ejecuta BizTalk Server, vaya a la carpeta siguiente:</span><span class="sxs-lookup"><span data-stu-id="97ded-147">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
   - <span data-ttu-id="97ded-148">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="97ded-148">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="97ded-149">**% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="97ded-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   - <span data-ttu-id="97ded-150">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="97ded-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="97ded-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="97ded-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6. <span data-ttu-id="97ded-152">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="97ded-152">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="97ded-153">**bm.exe update-config-FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="97ded-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_UpdateArchSSIS"></a> <span data-ttu-id="97ded-154">Para actualizar los nombres del servidor y base de datos en todos los paquetes de SSIS de BAM</span><span class="sxs-lookup"><span data-stu-id="97ded-154">To update server and database names in all BAM SSIS packages</span></span>  
  
1. <span data-ttu-id="97ded-155">Actualice los nombres de servidor y base de datos en todos los paquetes SSIS análisis BAM, que tienen el prefijo "BAM_DM_".</span><span class="sxs-lookup"><span data-stu-id="97ded-155">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_DM_".</span></span> <span data-ttu-id="97ded-156">Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="97ded-156">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2. <span data-ttu-id="97ded-157">En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="97ded-157">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="97ded-158">Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="97ded-158">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="97ded-159">En el **nuevo proyecto** cuadro de diálogo el **tipos de proyecto** cuadro, haga clic en **proyectos de Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="97ded-159">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="97ded-160">En el **Explorador de objetos**, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en MSDB.</span><span class="sxs-lookup"><span data-stu-id="97ded-160">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="97ded-161">En el **detalles del explorador de objetos** pestaña, haga clic en el paquete que se ha actualizado anteriormente y, a continuación, haga clic en **Importar paquete**.</span><span class="sxs-lookup"><span data-stu-id="97ded-161">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5. <span data-ttu-id="97ded-162">En el **Agregar copia de paquete existente** cuadro de diálogo el **Server** lista desplegable, seleccione el servidor que contiene los paquetes BAM_DM_ \*.</span><span class="sxs-lookup"><span data-stu-id="97ded-162">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_DM_\* packages.</span></span>  
  
6. <span data-ttu-id="97ded-163">En **ruta de acceso de paquete**, vaya al proyecto guardado, seleccione el archivo. dtsx para el paquete que desea importar y, a continuación, haga clic en abierto.</span><span class="sxs-lookup"><span data-stu-id="97ded-163">In **Package Path**, click the ellipses button.</span></span>  
  
7. <span data-ttu-id="97ded-164">Haga clic en el cuadro Nombre del paquete para rellenar automáticamente el cuadro.</span><span class="sxs-lookup"><span data-stu-id="97ded-164">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="97ded-165">Con ello, el paquete aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="97ded-165">The package is now listed in Solution Explorer.</span></span>  
  
8. <span data-ttu-id="97ded-166">Repita el paso 18 al 21 para todos los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="97ded-166">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="97ded-167">Haga clic en **Aceptar**y, a continuación, haga clic en Sí para sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="97ded-167">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMArchive database).</span></span>  
  
9. <span data-ttu-id="97ded-168">Iniciar todos ** servicios.</span><span class="sxs-lookup"><span data-stu-id="97ded-168">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="97ded-169">Inicie el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="97ded-169">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="97ded-170">Haga clic en el **Explorador de paquetes** pestaña, haga doble clic en el **Variables** carpeta y, a continuación, actualice los valores para el **ArchivingDatabase**, **ArchivingServer** , **PrimaryImportDatabase**, y **PrimaryImportServer** variables.</span><span class="sxs-lookup"><span data-stu-id="97ded-170">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **ArchivingDatabase**, **ArchivingServer**, **PrimaryImportDatabase**, and **PrimaryImportServer** variables.</span></span> <span data-ttu-id="97ded-171">Debe actualizar los valores para que apunte al nuevo servidor y base de datos.</span><span class="sxs-lookup"><span data-stu-id="97ded-171">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="97ded-172">Repita el paso 4 y 10 para todos los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="97ded-172">Repeat step 4 through 10 for all the packages that you want to update.</span></span>  
  
11. <span data-ttu-id="97ded-173">Haga clic en, a continuación, **archivo** menú y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="97ded-173">Click then **File** menu, and then click **Save All**.</span></span>  
  
12. <span data-ttu-id="97ded-174">Inicie SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="97ded-174">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="97ded-175">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en  **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="97ded-175">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
13. <span data-ttu-id="97ded-176">En el **conectar al servidor** cuadro de diálogo desde el **Server** lista desplegable de tipo, seleccione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="97ded-176">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
14. <span data-ttu-id="97ded-177">Especifique el nombre del servidor y las credenciales para conectarse al servidor y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97ded-177">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
15. <span data-ttu-id="97ded-178">En el **Explorador de objetos**, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.</span><span class="sxs-lookup"><span data-stu-id="97ded-178">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
16. <span data-ttu-id="97ded-179">En el **detalles del explorador de objetos** pestaña, haga clic en el paquete que se ha actualizado anteriormente y, a continuación, haga clic en **Importar paquete**.</span><span class="sxs-lookup"><span data-stu-id="97ded-179">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
17. <span data-ttu-id="97ded-180">En el **Importar paquete** cuadro de diálogo desde el **ubicación del paquete** lista desplegable, seleccione **sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="97ded-180">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
18. <span data-ttu-id="97ded-181">En **ruta de acceso de paquete**, vaya al proyecto guardado, seleccione el archivo. dtsx para el paquete que desea importar y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="97ded-181">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
19. <span data-ttu-id="97ded-182">Haga clic en el cuadro Nombre del paquete para rellenar automáticamente el cuadro.</span><span class="sxs-lookup"><span data-stu-id="97ded-182">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="97ded-183">Repita el paso 16 al 19 para todos los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="97ded-183">Repeat step 16 through 19 for all the packages that you want to update.</span></span>  
  
20. <span data-ttu-id="97ded-184">Haga clic en **Aceptar**y, a continuación, haga clic en **Sí** para sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="97ded-184">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
21. <span data-ttu-id="97ded-185">Iniciar todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios.</span><span class="sxs-lookup"><span data-stu-id="97ded-185">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="97ded-186">Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="97ded-186">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
22. <span data-ttu-id="97ded-187">Inicia el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="97ded-187">Start the IIS service.</span></span>  
  
23. <span data-ttu-id="97ded-188">Inicie el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="97ded-188">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="97ded-189">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97ded-189">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="97ded-190">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="97ded-190">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="97ded-191">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="97ded-191">**Net start NS$BamAlerts**</span></span>  
  
24. <span data-ttu-id="97ded-192">Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.</span><span class="sxs-lookup"><span data-stu-id="97ded-192">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="97ded-193">Como una buena práctica, también debe mover los paquetes SSIS BAM_DM_ \* al servidor que hospeda la base de datos BAMArchive.</span><span class="sxs-lookup"><span data-stu-id="97ded-193">As a good practice, you should also move the BAM_DM_\* SSIS packages to the server hosting the BAMArchive database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ded-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ded-194">See Also</span></span>  
 [<span data-ttu-id="97ded-195">Mover bases de datos</span><span class="sxs-lookup"><span data-stu-id="97ded-195">Moving Databases</span></span>](../technical-guides/moving-databases.md)