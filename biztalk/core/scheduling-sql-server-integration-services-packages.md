---
title: Paquetes de programación de SQL Server Integration Services | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 037ae2cf-c352-4823-95df-9a723f2b5a81
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17d8518a8c74f1fef77cf713852f1dfc87c8ef23
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975954"
---
# <a name="scheduling-sql-server-integration-services-packages"></a><span data-ttu-id="17d67-102">Programación de paquetes de SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="17d67-102">Scheduling SQL Server Integration Services Packages</span></span>
<span data-ttu-id="17d67-103">Los usuarios crear vistas de BAM basadas en datos almacenados en un cubo de procesamiento analítico en línea (OLAP).</span><span class="sxs-lookup"><span data-stu-id="17d67-103">Users create BAM views based on data stored in an online analytical processing (OLAP) cube.</span></span> <span data-ttu-id="17d67-104">El paquete de actualización de cubos de Integration Services actualiza los datos del cubo para que las vistas OLAP reflejen los datos correctos.</span><span class="sxs-lookup"><span data-stu-id="17d67-104">The Cube Update Integration Services package refreshes the data in the cube so that OLAP views reflect the correct data.</span></span>  
  
 <span data-ttu-id="17d67-105">Debe ejecutar este paquete al menos una vez para que las vistas OLAP funcionen.</span><span class="sxs-lookup"><span data-stu-id="17d67-105">You must run this package at least once for the OLAP views to work.</span></span> <span data-ttu-id="17d67-106">Para un mantenimiento continuado, es aconsejable programar una ejecución periódica del paquete.</span><span class="sxs-lookup"><span data-stu-id="17d67-106">For ongoing maintenance, you should schedule the package to run on a regular basis.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="17d67-107">Si ha restaurado la base de datos de esquema de estrella de BAM o detenido [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] antes de ejecutar el paquete de servicios de integración de actualización de cubos, deberá actualizar los orígenes de datos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Manager o reiniciar el servicio OLAP para poder ejecutar el paquete correctamente.</span><span class="sxs-lookup"><span data-stu-id="17d67-107">If you restored the BAM Star Schema database or stopped [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] before running the Cube Update Integration Services package, you must refresh the data sources in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Manager or restart the OLAP service before you can run the package successfully.</span></span>  
  
 <span data-ttu-id="17d67-108">Puede programar un paquete guardado para ejecutarlo en momentos determinados, una vez o en intervalos periódicos.</span><span class="sxs-lookup"><span data-stu-id="17d67-108">You can schedule a saved package to execute at specific times, either once or at recurring intervals.</span></span> <span data-ttu-id="17d67-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17d67-109">For example:</span></span>  
  
-   <span data-ttu-id="17d67-110">Diariamente a medianoche.</span><span class="sxs-lookup"><span data-stu-id="17d67-110">Daily at midnight.</span></span>  
  
-   <span data-ttu-id="17d67-111">Semanalmente, los domingos a las 06:00.</span><span class="sxs-lookup"><span data-stu-id="17d67-111">Weekly on Sunday at 06:00.</span></span>  
  
-   <span data-ttu-id="17d67-112">El primer o último día del mes.</span><span class="sxs-lookup"><span data-stu-id="17d67-112">The first or last day of the month.</span></span>  
  
 <span data-ttu-id="17d67-113">Un paquete programado se ejecuta mediante [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] como un trabajo.</span><span class="sxs-lookup"><span data-stu-id="17d67-113">A scheduled package is executed by [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] as a job.</span></span>  
  
 <span data-ttu-id="17d67-114">Para obtener información acerca de cómo ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] paquetes, consulte [http://go.microsoft.com/fwlink/?LinkId=125738](http://go.microsoft.com/fwlink/?LinkId=125738).</span><span class="sxs-lookup"><span data-stu-id="17d67-114">For information about running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] packages, see [http://go.microsoft.com/fwlink/?LinkId=125738](http://go.microsoft.com/fwlink/?LinkId=125738).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17d67-115">De forma predeterminada, el registro para archivar paquetes SSIS de BAM y elaborar cubos a partir de ellos está activado y almacenado en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="17d67-115">By default, logging for archiving and cubing BAM SSIS packages is turned on and is stored in the msdb database.</span></span> <span data-ttu-id="17d67-116">Con el tiempo, esto puede resultar en un volumen significativo de datos de registro de eventos SSIS derivado de una gran cantidad de actividades BAM o de la ejecución frecuente de paquetes SSIS de BAM.</span><span class="sxs-lookup"><span data-stu-id="17d67-116">Overtime, this may result in a significant volume of SSIS event log data caused by large number of BAM activities or frequent execution of BAM owned SSIS packages.</span></span> <span data-ttu-id="17d67-117">Para resolverlo, puede eliminar las entradas de registro antiguas, ya que estas entradas se usan, principalmente, para la depuración.</span><span class="sxs-lookup"><span data-stu-id="17d67-117">To resolve this, you can delete the old log entries because these entries are used primarily for debugging.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="17d67-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="17d67-118">Prerequisites</span></span>  
 <span data-ttu-id="17d67-119">Para llevar a cabo estos procedimientos, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="17d67-119">You must be logged on as a member of the BizTalk Server Administrators group to perform these procedures.</span></span>  
  
### <a name="to-run-the-cube-update-integration-services-package"></a><span data-ttu-id="17d67-120">Para ejecutar el paquete de servicios de integración de actualización de cubos</span><span class="sxs-lookup"><span data-stu-id="17d67-120">To run the Cube Update Integration Services package</span></span>  
  
1.  <span data-ttu-id="17d67-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP1** o **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en  **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="17d67-121">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="17d67-122">En el **conectar al servidor** cuadro de diálogo, en la **tipo de servidor** lista desplegable, seleccione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="17d67-122">In the **Connect to server** dialog box, in the **Server type** drop-down list, select **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="17d67-123">En el **nombre del servidor** lista desplegable, seleccione el nombre del servidor en el que se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="17d67-123">In the **Server name** drop-down list, select the name of the server on which you are running the package.</span></span>  
  
4.  <span data-ttu-id="17d67-124">En el **autenticación** lista desplegable, seleccione el tipo de autenticación que utilizan para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="17d67-124">In the **Authentication** drop-down list, select the type of authentication that you are using to connect to the server.</span></span>  
  
5.  <span data-ttu-id="17d67-125">Si es necesario, escriba su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="17d67-125">If necessary, type your user name and password.</span></span>  
  
6.  <span data-ttu-id="17d67-126">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="17d67-126">Click **Connect**.</span></span>  
  
7.  <span data-ttu-id="17d67-127">En el árbol de consola, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.</span><span class="sxs-lookup"><span data-stu-id="17d67-127">In the console tree, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
8.  <span data-ttu-id="17d67-128">Haga clic en el **BAM_AN_\<nombre de la vista\>**  del paquete y, a continuación, haga clic en **Ejecutar paquete**.</span><span class="sxs-lookup"><span data-stu-id="17d67-128">Right-click the **BAM_AN_\<View name\>** package, and then click **Run Package**.</span></span>  
  
### <a name="to-run-the-maintaining-bam-data-integration-services-package"></a><span data-ttu-id="17d67-129">Para ejecutar el paquete de mantenimiento de servicios de integración de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="17d67-129">To run the Maintaining BAM Data Integration Services package</span></span>  
  
1.  <span data-ttu-id="17d67-130">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP1** o **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en  **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="17d67-130">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="17d67-131">En el **conectar al servidor** cuadro de diálogo, en la **tipo de servidor** lista desplegable, seleccione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="17d67-131">In the **Connect to server** dialog box, in the **Server type** drop-down list, select **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="17d67-132">En el **nombre del servidor** lista desplegable, seleccione el nombre del servidor en el que se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="17d67-132">In the **Server name** drop-down list, select the name of the server on which you are running the package.</span></span>  
  
4.  <span data-ttu-id="17d67-133">En el **autenticación** lista desplegable, seleccione el tipo de autenticación que utilizan para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="17d67-133">In the **Authentication** drop-down list, select the type of authentication that you are using to connect to the server.</span></span>  
  
5.  <span data-ttu-id="17d67-134">Si es necesario, escriba su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="17d67-134">If necessary, type your user name and password.</span></span>  
  
6.  <span data-ttu-id="17d67-135">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="17d67-135">Click **Connect**.</span></span>  
  
7.  <span data-ttu-id="17d67-136">En el árbol de consola, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.</span><span class="sxs-lookup"><span data-stu-id="17d67-136">In the console tree, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
8.  <span data-ttu-id="17d67-137">Haga clic en el **BAM_DM_\<nombre de la actividad\>**  del paquete y, a continuación, haga clic en **Ejecutar paquete**.</span><span class="sxs-lookup"><span data-stu-id="17d67-137">Right-click the **BAM_DM_\<Activity name\>** package, and then click **Run Package**.</span></span>  
  
### <a name="to-schedule-the-packages-to-run-regularly"></a><span data-ttu-id="17d67-138">Para programar los paquetes para que se ejecuten con regularidad</span><span class="sxs-lookup"><span data-stu-id="17d67-138">To schedule the packages to run regularly</span></span>  
  
1.  <span data-ttu-id="17d67-139">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP1** o **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en  **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="17d67-139">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="17d67-140">En el **conectar al servidor** cuadro de diálogo, en la **tipo de servidor** lista desplegable, seleccione **motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="17d67-140">In the **Connect to server** dialog box, in the **Server type** drop-down list, select **Database Engine**.</span></span>  
  
3.  <span data-ttu-id="17d67-141">En el **nombre del servidor** lista desplegable, seleccione el nombre del servidor en el que se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="17d67-141">In the **Server name** drop-down list, select the name of the server on which you are running the package.</span></span>  
  
4.  <span data-ttu-id="17d67-142">En el **autenticación** lista desplegable, seleccione el tipo de autenticación que utilizan para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="17d67-142">In the **Authentication** drop-down list, select the type of authentication that you are using to connect to the server.</span></span>  
  
5.  <span data-ttu-id="17d67-143">Si es necesario, escriba su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="17d67-143">If necessary, type your user name and password.</span></span>  
  
6.  <span data-ttu-id="17d67-144">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="17d67-144">Click **Connect**.</span></span>  
  
7.  <span data-ttu-id="17d67-145">En el árbol de consola, expanda el servidor y seleccione **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="17d67-145">In the console tree, expand your server, and select **SQL Server Agent**.</span></span>  
  
8.  <span data-ttu-id="17d67-146">Si **Agente SQL Server** está deshabilitado, haga clic en **Agente SQL Server**y, a continuación, seleccione **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="17d67-146">If **SQL Server Agent** is disabled, right-click **SQL Server Agent**, and then select **Start**.</span></span>  
  
9. <span data-ttu-id="17d67-147">Haga clic en **Agente SQL Server**y seleccione **nuevo trabajo**.</span><span class="sxs-lookup"><span data-stu-id="17d67-147">Right-click **SQL Server Agent**, and select  **New Job**.</span></span>  
  
10. <span data-ttu-id="17d67-148">En el **nuevo trabajo** cuadro de diálogo, escriba un nombre para el trabajo en el **nombre** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="17d67-148">In the **New Job** dialog box, type a name for the job in the **Name** text box.</span></span>  
  
11. <span data-ttu-id="17d67-149">En el **seleccionar una página** ventana, haga clic en **pasos**y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="17d67-149">In the **Select a page** window, click **Steps**, and then click **New**.</span></span> <span data-ttu-id="17d67-150">Se abrirá la **nuevo paso de trabajo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="17d67-150">This opens the **New Job Step** dialog box.</span></span>  
  
12. <span data-ttu-id="17d67-151">En el **nombre del paso** texto, escriba un nombre de identificación del paso.</span><span class="sxs-lookup"><span data-stu-id="17d67-151">In the **Step name** text box, type an identifying name for the step.</span></span>  
  
13. <span data-ttu-id="17d67-152">En el **tipo** lista desplegable, seleccione **paquete SQL Server Integration Services** y en el **origen del paquete** lista desplegable, seleccione **almacén de paquetes SSIS** .</span><span class="sxs-lookup"><span data-stu-id="17d67-152">In the **Type** drop-down list, select **SQL Server Integration Services Package** and in the **Package source** drop-down list, select **SSIS Package Store**.</span></span>  
  
14. <span data-ttu-id="17d67-153">En el **Server** lista desplegable, seleccione el servidor en el que se ejecuta el trabajo.</span><span class="sxs-lookup"><span data-stu-id="17d67-153">In the **Server** drop-down list, select the server on which you are running the job.</span></span>  
  
15. <span data-ttu-id="17d67-154">Haga clic en el botón selector de archivos para el **paquete** texto, seleccione el paquete que está programando (ya sea la **BAM_DM_\<nombre de la actividad\>**  o **BAM_AN_ \<Nombre de la vista\>**  paquete) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="17d67-154">Click the file selector button for the **Package** text box, select the package you are scheduling (either the **BAM_DM_\<Activity name\>** or **BAM_AN_\<View name\>** package), and then click **OK**.</span></span>  
  
16. <span data-ttu-id="17d67-155">En el **seleccionar una página** ventana, haga clic en **programaciones**y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="17d67-155">In the **Select a page** window, click **Schedules**, and then click **New**.</span></span> <span data-ttu-id="17d67-156">Se abrirá la **nueva programación de trabajo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="17d67-156">This opens the **New Job Schedule** dialog box.</span></span>  
  
17. <span data-ttu-id="17d67-157">En el **nombre** cuadro de texto, escriba un nombre para la programación.</span><span class="sxs-lookup"><span data-stu-id="17d67-157">In the **Name** text box, type a name for the schedule.</span></span>  
  
18. <span data-ttu-id="17d67-158">Cree su programación mediante los campos de frecuencia.</span><span class="sxs-lookup"><span data-stu-id="17d67-158">Create your schedule using the frequency fields.</span></span>  
  
19. <span data-ttu-id="17d67-159">Haga clic en **Aceptar** para guardar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="17d67-159">Click **OK** to save the job.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="17d67-160">Si BAM se configura con una instancia no predeterminada de SQL Server, BAM_AN_POCube DTSPackage no se programa o ejecuta con precisión.</span><span class="sxs-lookup"><span data-stu-id="17d67-160">If BAM is configured with a non-default instance of SQL Server, then the BAM_AN_POCube DTSPackage does not get scheduled/executed accurately.</span></span> <span data-ttu-id="17d67-161">Tiene que modificar el archivo de configuración para que los paquetes sigan ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="17d67-161">You need to modify the configuration file to allow packages to continue running.</span></span> <span data-ttu-id="17d67-162">Para obtener más información, consulte la sección "Modificar el contenido del archivo de configuración" en [http://go.microsoft.com/fwlink/?LinkId=196768](http://go.microsoft.com/fwlink/?LinkId=196768).</span><span class="sxs-lookup"><span data-stu-id="17d67-162">For more information, refer to the "Modifying the Contents of the Configuration File" section at [http://go.microsoft.com/fwlink/?LinkId=196768](http://go.microsoft.com/fwlink/?LinkId=196768).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d67-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="17d67-163">See Also</span></span>  
 [<span data-ttu-id="17d67-164">Administración de bases de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="17d67-164">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)