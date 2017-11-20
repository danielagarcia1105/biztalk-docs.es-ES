---
title: "Cómo mover la Database2 de esquema de estrella de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6832ac2-c8c5-4515-883e-26d125d6ace0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00567514d3a3ce197065ffdfbf499ebba46c6b06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-star-schema-database"></a><span data-ttu-id="5126c-102">Cómo mover la base de datos de esquema de estrella de BAM</span><span class="sxs-lookup"><span data-stu-id="5126c-102">How to Move the BAM Star Schema Database</span></span>
<span data-ttu-id="5126c-103">Este procedimiento se puede utilizar para mover la base de datos de esquema de estrella de BAM a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="5126c-103">You can use this procedure to move the BAM Star Schema database to another server.</span></span>  <span data-ttu-id="5126c-104">Desde una perspectiva de escenario to-end, mover la base de datos de esquema de estrella de BAM consta de dos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="5126c-104">From an end-to-end scenario perspective, moving the BAM Star Schema database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="5126c-105">Mover la base de datos de esquema de estrella de BAM</span><span class="sxs-lookup"><span data-stu-id="5126c-105">Moving the BAM Star Schema Database</span></span>](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarMoveDB)  
  
-   [<span data-ttu-id="5126c-106">Actualizar las referencias a la nueva base de datos de esquema de estrella de BAM</span><span class="sxs-lookup"><span data-stu-id="5126c-106">Updating References to the New BAM Star Schema Database</span></span>](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)  
  
## <a name="prerequisites"></a><span data-ttu-id="5126c-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5126c-107">Prerequisites</span></span>  
 <span data-ttu-id="5126c-108">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5126c-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <span data-ttu-id="5126c-109"><a name="BKMK_StarMoveDB"></a>Mover la base de datos de esquema de estrella de BAM</span><span class="sxs-lookup"><span data-stu-id="5126c-109"><a name="BKMK_StarMoveDB"></a> Moving the BAM Star Schema Database</span></span>  
 <span data-ttu-id="5126c-110">Realice los pasos en el siguiente procedimiento para mover la base de datos de esquema de estrella de BAM.</span><span class="sxs-lookup"><span data-stu-id="5126c-110">Perform the steps in the following procedure to move the BAM Star Schema database.</span></span>  
  
#### <a name="to-move-the-bam-star-schema-database"></a><span data-ttu-id="5126c-111">Para mover la base de datos de esquema de estrella de BAM</span><span class="sxs-lookup"><span data-stu-id="5126c-111">To move the BAM Star Schema database</span></span>  
  
1.  <span data-ttu-id="5126c-112">Detenga todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE, o impida su ejecución hasta que se haya restaurado la base de datos de esquema de estrella de SAE.</span><span class="sxs-lookup"><span data-stu-id="5126c-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Star Schema database.</span></span>  
  
2.  <span data-ttu-id="5126c-113">Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5126c-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="5126c-114">Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="5126c-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3.  <span data-ttu-id="5126c-115">Detenga el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="5126c-115">Stop the IIS service.</span></span>  
  
4.  <span data-ttu-id="5126c-116">Detenga el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="5126c-116">Stop the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="5126c-117">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="5126c-118">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="5126c-118">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="5126c-119">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="5126c-119">**Net stop NS$BamAlerts**</span></span>  
  
5.  <span data-ttu-id="5126c-120">Hacer copia de seguridad de la base de datos de esquema de estrella de BAM en el servidor anterior.</span><span class="sxs-lookup"><span data-stu-id="5126c-120">Back up the BAM Star Schema database on the old server.</span></span> <span data-ttu-id="5126c-121">Para obtener instrucciones sobre la copia de seguridad de una base de datos, siga las instrucciones de [Cómo: copia de una base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla acerca de cómo realizar copias de seguridad de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="5126c-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6.  <span data-ttu-id="5126c-122">Copiar la base de datos de esquema de estrella de BAM en la nueva [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.</span><span class="sxs-lookup"><span data-stu-id="5126c-122">Copy the BAM Star Schema database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7.  <span data-ttu-id="5126c-123">Restaure la base de datos de esquema de estrella de BAM en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="5126c-123">Restore the BAM Star Schema database on the new server.</span></span> <span data-ttu-id="5126c-124">Para obtener instrucciones acerca de cómo restaurar la base de datos, siga las instrucciones de [Cómo: restaurar una copia de seguridad de base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla acerca de cómo restaurar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="5126c-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <span data-ttu-id="5126c-125"><a name="BKMK_StarUpdate"></a>Actualizar las referencias a la nueva base de datos de esquema de estrella de BAM</span><span class="sxs-lookup"><span data-stu-id="5126c-125"><a name="BKMK_StarUpdate"></a> Updating References to the New BAM Star Schema Database</span></span>  
 <span data-ttu-id="5126c-126">Después de haber movido la base de datos, debe actualizar todas las referencias a la base de datos de esquema de estrella de BAM nueva.</span><span class="sxs-lookup"><span data-stu-id="5126c-126">After you have moved the database, you must update all the references to the new BAM Star Schema Database.</span></span> <span data-ttu-id="5126c-127">Deben actualizar las referencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="5126c-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="5126c-128">Actualizar la configuración de BAM con los nuevos nombres de base de datos y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5126c-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="5126c-129">Vea [para actualizar la configuración de BAM](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig).</span><span class="sxs-lookup"><span data-stu-id="5126c-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig).</span></span>  
  
-   <span data-ttu-id="5126c-130">Actualice los nombres de servidor y base de datos nueva en todos los paquetes SSIS de análisis BAM.</span><span class="sxs-lookup"><span data-stu-id="5126c-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="5126c-131">Vea [para actualizar los nombres de servidor y base de datos en todos los paquetes SSIS de BAM](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef).</span><span class="sxs-lookup"><span data-stu-id="5126c-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef).</span></span>  
  
-   <span data-ttu-id="5126c-132">Actualice los nombres de servidor y base de datos nueva en orígenes de datos para todos los cubos OLAP no.</span><span class="sxs-lookup"><span data-stu-id="5126c-132">Update the new server and database names in data sources for all non-OLAP cubes.</span></span> <span data-ttu-id="5126c-133">Vea [para actualizar los nombres de servidor y base de datos en orígenes de datos para todos los cubos OLAP no](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP).</span><span class="sxs-lookup"><span data-stu-id="5126c-133">See [To update server and database names in data sources for all non-OLAP cubes](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP).</span></span>  
  
###  <span data-ttu-id="5126c-134"><a name="BKMK_StarUpdateBAMConfig"></a>Para actualizar la configuración de BAM</span><span class="sxs-lookup"><span data-stu-id="5126c-134"><a name="BKMK_StarUpdateBAMConfig"></a> To update the BAM configuration</span></span>  
  
1.  <span data-ttu-id="5126c-135">Obtenga una copia del archivo .xml utilizado para restaurar BAM:</span><span class="sxs-lookup"><span data-stu-id="5126c-135">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="5126c-136">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-136">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="5126c-137">En un equipo en el que se ejecute [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], desplácese hasta la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="5126c-137">On a computer running [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], browse to the following folder:</span></span>  
  
        -   <span data-ttu-id="5126c-138">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="5126c-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="5126c-139">**% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="5126c-139">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
        -   <span data-ttu-id="5126c-140">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="5126c-140">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="5126c-141">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="5126c-141">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    3.  <span data-ttu-id="5126c-142">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="5126c-142">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="5126c-143">**Bm.exe get-config –filename:BAMConfiguration.xml-server:\<nombreDeServidor >-base de datos:\<base de datos >**</span><span class="sxs-lookup"><span data-stu-id="5126c-143">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername> -database:\<database>**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5126c-144">Cuando se ejecuta este comando, sustituya el nombre real del servidor desde el que se va a obtener la información de configuración de \<nombreDeServidor > y sustituya el nombre real de la base de datos que se va a obtener la información de configuración de \<base de datos >.</span><span class="sxs-lookup"><span data-stu-id="5126c-144">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername> and substitute the actual name of the database from which to get the configuration information for \<database>.</span></span> <span data-ttu-id="5126c-145">Para obtener más información sobre el uso de la utilidad de administración de BAM (BM), consulte [comandos de administración de infraestructura](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="5126c-145">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2.  <span data-ttu-id="5126c-146">Edite el archivo BAMConfiguration.xml y cambie la **ServerName** en la `<DeploymentUnit Name="StarSchemaDatabase">` sección para el nuevo nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="5126c-146">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="StarSchemaDatabase">` section to the new server name.</span></span>  
  
3.  <span data-ttu-id="5126c-147">Guarde el archivo BAMConfiguration.xml y ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="5126c-147">Save and close the BAMConfiguration.xml file.</span></span>  
  
4.  <span data-ttu-id="5126c-148">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-148">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="5126c-149">En un equipo en el que se ejecute [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], desplácese hasta la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="5126c-149">On a computer running [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], browse to the following folder:</span></span>  
  
    -   <span data-ttu-id="5126c-150">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="5126c-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="5126c-151">**% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="5126c-151">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    -   <span data-ttu-id="5126c-152">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="5126c-152">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="5126c-153">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="5126c-153">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6.  <span data-ttu-id="5126c-154">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="5126c-154">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="5126c-155">**bm.exe update-config-FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="5126c-155">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <span data-ttu-id="5126c-156"><a name="BKMK_StarUpdateRef"></a>Para actualizar los nombres de servidor y base de datos en todos los paquetes SSIS de BAM</span><span class="sxs-lookup"><span data-stu-id="5126c-156"><a name="BKMK_StarUpdateRef"></a> To update server and database names in all BAM SSIS packages</span></span>  
  
1.  <span data-ttu-id="5126c-157">Actualice los nombres de servidor y base de datos en todos los paquetes SSIS análisis BAM, que tienen el prefijo "Bam_an_".</span><span class="sxs-lookup"><span data-stu-id="5126c-157">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_AN_".</span></span> <span data-ttu-id="5126c-158">Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="5126c-158">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="5126c-159">En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="5126c-159">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="5126c-160">Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="5126c-160">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="5126c-161">En el **nuevo proyecto** cuadro de diálogo, en la **tipos de proyecto** cuadro, haga clic en **proyectos de Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="5126c-161">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="5126c-162">En el panel derecho, en la **plantillas** cuadro, haga clic en **proyecto de Integration Services**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-162">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="5126c-163">En el **proyecto de Integration Services** cuadro de diálogo, en el Explorador de soluciones, haga clic en **paquetes SSIS**y, a continuación, haga clic en **Agregar paquete existente**.</span><span class="sxs-lookup"><span data-stu-id="5126c-163">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5.  <span data-ttu-id="5126c-164">En el **Agregar copia de paquete existente** cuadro de diálogo, en la **Server** lista desplegable, seleccione el servidor que contiene los paquetes BAM_AN_ *.</span><span class="sxs-lookup"><span data-stu-id="5126c-164">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN_* packages.</span></span>  
  
6.  <span data-ttu-id="5126c-165">En **ruta de acceso del paquete**, haga clic en el botón de puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="5126c-165">In **Package Path**, click the ellipses button.</span></span>  
  
7.  <span data-ttu-id="5126c-166">En el **paquete SSIS** cuadro de diálogo, seleccione el paquete que desea actualizar, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-166">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="5126c-167">Con ello, el paquete aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="5126c-167">The package is now listed in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="5126c-168">En el Explorador de soluciones, haga doble clic en el paquete que agregó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="5126c-168">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="5126c-169">En **administradores de conexión** pestaña (disponible hacia la parte inferior de la pantalla), haga doble clic en el número de origen de datos 2 (base de datos BAMStarSchema).</span><span class="sxs-lookup"><span data-stu-id="5126c-169">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMStarSchema database).</span></span>  
  
9. <span data-ttu-id="5126c-170">En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-170">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5126c-171">Repita este paso para el número de origen de datos 3 (base de datos MSDB).</span><span class="sxs-lookup"><span data-stu-id="5126c-171">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="5126c-172">En el **administradores de conexión** ficha, haga doble clic en el número de origen de datos 4 (base de datos BAMAnalysis).</span><span class="sxs-lookup"><span data-stu-id="5126c-172">In the **Connection Managers** tab, double-click data source number 4 (BAMAnalysis database).</span></span> <span data-ttu-id="5126c-173">En el **Agregar administrador de conexión de Analysis Services** cuadro de diálogo, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-173">In the **Add Analysis Services Connection Manager** dialog box, click **Edit**.</span></span>  
  
11. <span data-ttu-id="5126c-174">En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-174">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, click **OK**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="5126c-175">Haga clic en el **Explorador de paquetes** ficha, haga doble clic en el **Variables** carpeta y, a continuación, actualice los valores de la **AnalysisDatabase**, **AnalysisServer** , **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, y **StarSchemaServer** variables.</span><span class="sxs-lookup"><span data-stu-id="5126c-175">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **AnalysisDatabase**, **AnalysisServer**, **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, and **StarSchemaServer** variables.</span></span> <span data-ttu-id="5126c-176">Debe actualizar los valores para que apunte al nuevo servidor y base de datos.</span><span class="sxs-lookup"><span data-stu-id="5126c-176">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5126c-177">Repita el paso 4 y 12 para todos los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="5126c-177">Repeat step 4 through 12 for all the packages that you want to update.</span></span>  
  
13. <span data-ttu-id="5126c-178">Haga clic en, a continuación, **archivo** menú y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="5126c-178">Click then **File** menu, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="5126c-179">Inicie SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="5126c-179">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="5126c-180">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en  **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="5126c-180">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
15. <span data-ttu-id="5126c-181">En el **conectar al servidor** cuadro de diálogo, desde el **Server** lista de tipo de lista desplegable, seleccione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="5126c-181">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
16. <span data-ttu-id="5126c-182">Especifique el nombre del servidor y las credenciales para conectarse al servidor y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-182">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
17. <span data-ttu-id="5126c-183">En el **Explorador de objetos**, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.</span><span class="sxs-lookup"><span data-stu-id="5126c-183">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
18. <span data-ttu-id="5126c-184">En el **detalles del explorador de objetos** pestaña, haga clic en el paquete que actualizó anteriormente y, a continuación, haga clic en **Importar paquete**.</span><span class="sxs-lookup"><span data-stu-id="5126c-184">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
19. <span data-ttu-id="5126c-185">En el **Importar paquete** cuadro de diálogo, desde el **ubicación del paquete** lista desplegable, seleccione **sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="5126c-185">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
20. <span data-ttu-id="5126c-186">En **ruta de acceso del paquete**, navegue al proyecto guardado, seleccione el archivo DTSX para el paquete que desea importar y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="5126c-186">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
21. <span data-ttu-id="5126c-187">Haga clic dentro del cuadro Nombre del paquete para rellenar automáticamente el cuadro.</span><span class="sxs-lookup"><span data-stu-id="5126c-187">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5126c-188">Repita el paso 18 al 21 para todos los paquetes que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="5126c-188">Repeat step 18 through 21 for all the packages that you want to update.</span></span>  
  
22. <span data-ttu-id="5126c-189">Haga clic en **Aceptar**y, a continuación, haga clic en **Sí** para sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="5126c-189">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
23. <span data-ttu-id="5126c-190">Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.</span><span class="sxs-lookup"><span data-stu-id="5126c-190">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
###  <span data-ttu-id="5126c-191"><a name="BKMK_UpdateDS_non_OLAP"></a>Para actualizar los nombres de servidor y base de datos en orígenes de datos para todos los cubos OLAP no</span><span class="sxs-lookup"><span data-stu-id="5126c-191"><a name="BKMK_UpdateDS_non_OLAP"></a> To update server and database names in data sources for all non-OLAP cubes</span></span>  
  
1.  <span data-ttu-id="5126c-192">Actualice los nombres de servidor y base de datos en orígenes de datos para todos los cubos OLAP no.</span><span class="sxs-lookup"><span data-stu-id="5126c-192">Update the server and database names in data sources for all non-OLAP cubes.</span></span> <span data-ttu-id="5126c-193">Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="5126c-193">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="5126c-194">En el **conectar al servidor** cuadro de diálogo para la **tipo de servidor** lista desplegable, seleccione **Analysis Services**, proporcione el nombre del servidor, seleccione un método de autenticación (y Proporcione credenciales si es necesario) y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-194">In the **Connect to Server** dialog box, for the **Server type** drop-down list select **Analysis Services**, provide the server name, select an authentication method (and provide credentials if required), and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="5126c-195">En el Explorador de objetos, expanda **bases de datos**, expanda **BAMAnalysis**, expanda **orígenes de datos**y, a continuación, haga doble clic en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5126c-195">In the Object Explorer, expand **Databases**, expand **BAMAnalysis**, expand **Data Sources**, and then double-click a data source.</span></span>  
  
4.  <span data-ttu-id="5126c-196">En el **propiedades del origen de datos** diálogo cuadro, haga clic en el botón de puntos suspensivos **(...)**  contra la **cadena de conexión** propiedad.</span><span class="sxs-lookup"><span data-stu-id="5126c-196">In the **Data Source Properties** dialog box, click the ellipsis button **(…)** against the **Connection String** property.</span></span>  
  
5.  <span data-ttu-id="5126c-197">En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor que hospeda la base de datos BAMStarSchema, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-197">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server hosting the BAMStarSchema database, click **OK**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="5126c-198">Iniciar todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios.</span><span class="sxs-lookup"><span data-stu-id="5126c-198">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="5126c-199">Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="5126c-199">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
7.  <span data-ttu-id="5126c-200">Inicia el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="5126c-200">Start the IIS service.</span></span>  
  
8.  <span data-ttu-id="5126c-201">Inicie el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="5126c-201">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="5126c-202">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5126c-202">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="5126c-203">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="5126c-203">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="5126c-204">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="5126c-204">**Net start NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="5126c-205">Resolver todas las instancias incompletas de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5126c-205">Resolve any incomplete trace instances.</span></span>  <span data-ttu-id="5126c-206">Para obtener información acerca de cómo resolver instancias incompletas de actividad BAM, consulte [cómo resolver instancias de actividad incompletas](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).</span><span class="sxs-lookup"><span data-stu-id="5126c-206">For information about resolving incomplete BAM activity instances, see [How to Resolve Incomplete Activity Instances](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="5126c-207">Como una buena práctica, debe mover también los paquetes de SSIS BAM_AN_ * al servidor que hospeda la base de datos BAMStarSchema.</span><span class="sxs-lookup"><span data-stu-id="5126c-207">As a good practice, you should also move the BAM_AN_* SSIS packages to the server hosting the BAMStarSchema database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5126c-208">Vea también</span><span class="sxs-lookup"><span data-stu-id="5126c-208">See Also</span></span>  
 [<span data-ttu-id="5126c-209">Mover bases de datos</span><span class="sxs-lookup"><span data-stu-id="5126c-209">Moving Databases</span></span>](../technical-guides/moving-databases.md)