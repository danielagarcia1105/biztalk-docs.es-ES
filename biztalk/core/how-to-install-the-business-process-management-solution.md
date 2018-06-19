---
title: Cómo instalar la solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, examples
- process management solution tutorial, installing
- process management solution tutorial, deployment prerequisites
ms.assetid: 930f3bb1-05e6-4b02-852d-6139aaf341f0
caps.latest.revision: 61
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 706bc1cec8afc796fa44e022243782a207fe1777
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974938"
---
# <a name="how-to-install-the-business-process-management-solution"></a><span data-ttu-id="d378d-102">Cómo instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-102">How to Install the Business Process Management Solution</span></span>
<span data-ttu-id="d378d-103">Los pasos siguientes describen cómo preparar el equipo para instalar la solución Administración de procesos empresariales (BPM) y cómo realizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="d378d-103">The following steps describe how to prepare the computer for installing the Business Process Management (BPM) solution, and how to install the solution on this computer.</span></span>  
  
-   [<span data-ttu-id="d378d-104">Preparar el equipo para instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-104">Prepare the computer for installing the Business Process Management Solution</span></span>](#step1)  
  
     <span data-ttu-id="d378d-105">En la fase de preparación, se crean las carpetas, las colas y la base de datos SQL que utilizarán los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="d378d-105">In the preparation step, you create the folders, queues, and SQL database that will be used by the receive and send ports.</span></span> <span data-ttu-id="d378d-106">También se crean los dos directorios virtuales para la aplicación cliente, CSRWebApp y el servicio Web de proxy OrderBroker.</span><span class="sxs-lookup"><span data-stu-id="d378d-106">You also create the two virtual directories for the client application, CSRWebApp, and the OrderBroker proxy Web Service.</span></span>  
  
-   [<span data-ttu-id="d378d-107">Configurar el equipo para instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-107">Configure the computer for installing the Business Process Management Solution</span></span>](#step3)  
  
-   [<span data-ttu-id="d378d-108">Instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-108">Install the Business Process Management Solution</span></span>](#step5)  
  
> [!NOTE]
>  <span data-ttu-id="d378d-109">Ejecutará algunos archivos por lotes para implementar la solución.</span><span class="sxs-lookup"><span data-stu-id="d378d-109">You will run some batch files to deploy the solution.</span></span> <span data-ttu-id="d378d-110">Se recomienda redirigir el resultado de los archivos de procesamiento por lotes a un archivo de texto para comprobar que la secuencia de comandos se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d378d-110">We recommend that you redirect the output of the batch files to a text file to verify that the script completed successfully.</span></span>  
  
##  <a name="step1"></a><span data-ttu-id="d378d-111">Preparar el equipo para instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-111">Prepare the computer for installing the Business Process Management Solution</span></span>  
  
#### <a name="to-prepare-the-computer-for-installing-the-business-process-management-solution"></a><span data-ttu-id="d378d-112">Para preparar el equipo para instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-112">To prepare the computer for installing the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="d378d-113">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Services**.</span><span class="sxs-lookup"><span data-stu-id="d378d-113">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span> <span data-ttu-id="d378d-114">Mediante el **servicios** consola, asegúrese de que se están ejecutando los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="d378d-114">Using the **Services** console, make sure that the following services are running:</span></span>  
  
    -   <span data-ttu-id="d378d-115">**Publicación FTP**</span><span class="sxs-lookup"><span data-stu-id="d378d-115">**FTP Publishing**</span></span>  
  
    -   <span data-ttu-id="d378d-116">**Message Queue Server**</span><span class="sxs-lookup"><span data-stu-id="d378d-116">**Message Queuing**</span></span>  
  
    -   <span data-ttu-id="d378d-117">**Publicación en World Wide Web**</span><span class="sxs-lookup"><span data-stu-id="d378d-117">**World Wide Web Publishing**</span></span>  
  
2.  <span data-ttu-id="d378d-118">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**, haga clic en **administración de equipos** consola y, a continuación, agregue el Cuenta de servicio de BizTalk al grupo de administradores local.</span><span class="sxs-lookup"><span data-stu-id="d378d-118">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
3.  <span data-ttu-id="d378d-119">Si ha instalado Windows SharePoint Services, excluya la (raíz) de la **sitio Web predeterminado** de Windows SharePoint Services rutas de acceso administradas como sigue: haga clic en **iniciar**, seleccione **todos los programas** , seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d378d-119">If you installed Windows SharePoint Services, exclude the (root) of the **Default Web Site** from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    1.  <span data-ttu-id="d378d-120">En **configuración del servidor Virtual**, seleccione **configurar el servidor virtual**.</span><span class="sxs-lookup"><span data-stu-id="d378d-120">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
    2.  <span data-ttu-id="d378d-121">En el **lista de servidores virtuales** página, haga clic en **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="d378d-121">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
    3.  <span data-ttu-id="d378d-122">En el **configuración del servidor Virtual** página, haga clic en **definir rutas administradas**.</span><span class="sxs-lookup"><span data-stu-id="d378d-122">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
    4.  <span data-ttu-id="d378d-123">En el **rutas incluidas** sección de la **definir rutas administradas** página, seleccione **raíz** y, a continuación, haga clic en **quitar rutas seleccionadas**.</span><span class="sxs-lookup"><span data-stu-id="d378d-123">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
    5.  <span data-ttu-id="d378d-124">En el símbolo del sistema, ejecute IISReset.</span><span class="sxs-lookup"><span data-stu-id="d378d-124">At a command prompt, perform an IISReset.</span></span>  
  
##  <a name="step3"></a><span data-ttu-id="d378d-125">Configurar el equipo para instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-125">Configure the computer for installing the Business Process Management Solution</span></span>  
  
#### <a name="to-configure-the-computer-for-installing-the-business-process-management-solution"></a><span data-ttu-id="d378d-126">Para configurar el equipo para instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-126">To configure the computer for installing the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="d378d-127">Cierre la sesión y, a continuación, inicie una sesión en el equipo con la cuenta de servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d378d-127">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
2.  <span data-ttu-id="d378d-128">Abra un símbolo del sistema, escriba el comando siguiente y, a continuación, presione ENTRAR para establecer la variable de entorno %BTSSolutionsPath% e indicar la carpeta base para las soluciones B2B.</span><span class="sxs-lookup"><span data-stu-id="d378d-128">Open a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment variable to indicate the base folder for the E2E solutions.</span></span> <span data-ttu-id="d378d-129">A continuación, cierre el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d378d-129">Then, exit the command prompt.</span></span>  
  
    -   `setx BTSSolutionsPath "%ProgramFiles%\Microsoft BizTalk Server 2009\SDK\Scenarios"`  
  
        > [!NOTE]
        >  <span data-ttu-id="d378d-130">Si está utilizando un equipo de 64 bits, escriba %ProgramFiles(x86)% en lugar de %ProgramFiles%.</span><span class="sxs-lookup"><span data-stu-id="d378d-130">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d378d-131">Para obtener más información acerca del comando SETX, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span><span class="sxs-lookup"><span data-stu-id="d378d-131">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
3.  <span data-ttu-id="d378d-132">Abra un símbolo del sistema, cambie el directorio actual a la carpeta %BTSSolutionsPath%\BPM\HistoryDB, escriba `CreateDatabase.cmd`, y presione ENTRAR para crear la base de datos de historial.</span><span class="sxs-lookup"><span data-stu-id="d378d-132">Open a command prompt, change the current directory to %BTSSolutionsPath%\BPM\HistoryDB folder, type `CreateDatabase.cmd`, and press ENTER to create the history database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d378d-133">El usuario que ejecuta el host especificado como controlador para el adaptador de envío SQL debe tener permisos para ejecutar procedimientos almacenados en la base de datos SouthridgeVideoHistory.</span><span class="sxs-lookup"><span data-stu-id="d378d-133">The user running the host specified as the handler for the SQL send adapter must have permissions to execute stored procedures on the SouthridgeVideoHistory database.</span></span>  
  
4.  <span data-ttu-id="d378d-134">En un símbolo del sistema, ejecute el comando siguiente para cambiar el host predeterminado de secuencias de comandos a CScript.exe</span><span class="sxs-lookup"><span data-stu-id="d378d-134">At a command prompt, run the following command to change the default script host to CScript.exe</span></span>  
  
    -   `CScript /H:CScript`  
  
5.  <span data-ttu-id="d378d-135">En un símbolo del sistema, ejecute el comando siguiente para crear la aplicación Web CSRWebApp.</span><span class="sxs-lookup"><span data-stu-id="d378d-135">At a command prompt, run the following command to create the CSRWebApp Web application</span></span>  
  
    -   `iisvdir /create "Default Web Site" CSRWebApp "%BTSSolutionsPath%\BPM\CSRWebApp"`  
  
        > [!NOTE]
        >  <span data-ttu-id="d378d-136">Para obtener más información acerca de iisvdir.vbs, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830).</span><span class="sxs-lookup"><span data-stu-id="d378d-136">For more information about iisvdir.vbs, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830).</span></span>  
  
6.  <span data-ttu-id="d378d-137">En un símbolo del sistema, ejecute el comando siguiente para crear un nuevo directorio virtual de IIS para OrderBroker_Proxy.</span><span class="sxs-lookup"><span data-stu-id="d378d-137">At a command prompt, run the following command to create a new IIS virtual directory for OrderBroker_Proxy.</span></span>  
  
    -   `iisvdir /create "Default Web Site" BTSScn.BPM.OrderBroker_Proxy "%BTSSolutionsPath%\BPM\OrderBroker_Proxy"`  
  
    > [!NOTE]
    >  <span data-ttu-id="d378d-138">Puede usar el Administrador de Internet Information Services (IIS) para crear la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="d378d-138">You can use Internet Information Services (IIS) Manager to create the Web Application.</span></span> <span data-ttu-id="d378d-139">Para obtener más información acerca de cómo crear aplicaciones en IIS 7.0, vea la documentación de IIS 7.0 en [http://go.microsoft.com/fwlink/?LinkId=59263](http://go.microsoft.com/fwlink/?LinkId=59263).</span><span class="sxs-lookup"><span data-stu-id="d378d-139">For more information about how to create applications in IIS 7.0, see the IIS 7.0 Documentation at [http://go.microsoft.com/fwlink/?LinkId=59263](http://go.microsoft.com/fwlink/?LinkId=59263).</span></span>  
  
7.  <span data-ttu-id="d378d-140">Cree un nuevo grupo de aplicaciones de IIS y configure su identidad como usuario miembro de los grupos Usuarios de hosts aislados de BizTalk y IIS_WPG como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="d378d-140">Create a new IIS application pool and set its identity as a user that is a member of the BizTalk Isolated Host Users group and the IIS_WPG group, as follows:</span></span>  
  
    1.  <span data-ttu-id="d378d-141">En el Administrador de Internet Information Services (IIS), haga clic en **grupos de aplicaciones**, seleccione **New**y, a continuación, seleccione **grupo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="d378d-141">In Internet Information Services (IIS) Manager, right-click **Application Pools**, select **New**, and then select **Application Pool**.</span></span>  
  
    2.  <span data-ttu-id="d378d-142">Tipo de la **Id. de grupo de aplicaciones** (cualquier valor) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d378d-142">Type the **Application pool ID** (any value), and then click **OK**.</span></span>  
  
    3.  <span data-ttu-id="d378d-143">Haga clic en el grupo de aplicaciones que creó y, a continuación, seleccione **configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="d378d-143">Right-click the application pool that you created, and then select **Advanced Settings**.</span></span>  
  
    4.  <span data-ttu-id="d378d-144">Expanda **modelo de proceso**, haga clic en la columna derecha de la **identidad** configuración y, a continuación, haga clic en **...**</span><span class="sxs-lookup"><span data-stu-id="d378d-144">Expand **Process Model**, click in the right-column for the **Identity** setting, and then click **…**</span></span>  
  
    5.  <span data-ttu-id="d378d-145">Seleccione una cuenta de usuario (ya sea un **cuenta integrada** o **cuenta personalizada** ) que tiene permisos para crear y ejecutar archivos en el directorio Windows\Temp.</span><span class="sxs-lookup"><span data-stu-id="d378d-145">Select a user account (either a **Build-in account** or **Custom account** ) that has permissions to create and execute files in the Windows\Temp directory.</span></span> <span data-ttu-id="d378d-146">Al configurar BizTalk, el proceso de configuración ya estableció estos permisos para el usuario que agregó al grupo fue a agregar al grupo Usuarios de hosts aislados de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d378d-146">When you configured BizTalk, the configuration process already set these permissions for the user it added to the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="d378d-147">Especificar el mismo usuario es una buena elección.</span><span class="sxs-lookup"><span data-stu-id="d378d-147">Specifying the same user is a good choice.</span></span>  
  
8.  <span data-ttu-id="d378d-148">En el Administrador de Internet Information Services (IIS), expanda **sitios Web**, expanda **sitio Web predeterminado**, haga clic en **BTSScn.BPM.OrderBroker_Proxy**, seleccione **Administrar la aplicación**y, a continuación, haga clic en **configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="d378d-148">In Internet Information Services (IIS) Manager, expand **Web Sites**, expand **Default Web Site**, right-click **BTSScn.BPM.OrderBroker_Proxy**, point to **Manage Application**, and then click **Advanced Settings**.</span></span>  
  
9. <span data-ttu-id="d378d-149">Establecer **grupo de aplicaciones** al grupo de aplicaciones que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="d378d-149">Set **Application Pool** to the application pool that you  created in the previous step.</span></span>  
  
10. <span data-ttu-id="d378d-150">Repita los dos pasos anteriores para la **CSRWebApp** aplicación.</span><span class="sxs-lookup"><span data-stu-id="d378d-150">Repeat the previous two steps for the **CSRWebApp** application.</span></span>  
  
11. <span data-ttu-id="d378d-151">Restablezca IIS para asegurarse de que todos estos cambios surten efecto inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="d378d-151">Reset IIS to make sure all these changes take effect immediately.</span></span> <span data-ttu-id="d378d-152">Para ello, ejecute **iisreset** en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d378d-152">To do this, run **iisreset** at a command prompt.</span></span>  
  
12. <span data-ttu-id="d378d-153">En un símbolo del sistema, cambie la carpeta actual a % BTSSolutionsPath%\BPM\Scripts, escriba `CreateQueues.vbs`, y, a continuación, presione ENTRAR para crear las colas privadas siguientes.</span><span class="sxs-lookup"><span data-stu-id="d378d-153">At a command prompt, change the current folder to the %BTSSolutionsPath%\BPM\Scripts, type `CreateQueues.vbs`, and then press ENTER to create the following private queues.</span></span>  
  
    |<span data-ttu-id="d378d-154">Nombre</span><span class="sxs-lookup"><span data-stu-id="d378d-154">Name</span></span>|<span data-ttu-id="d378d-155">Transaccional</span><span class="sxs-lookup"><span data-stu-id="d378d-155">Transactional</span></span>|<span data-ttu-id="d378d-156">Protocolo de transacciones</span><span class="sxs-lookup"><span data-stu-id="d378d-156">Transaction protocol</span></span>|  
    |----------|-------------------|--------------------------|  
    |<span data-ttu-id="d378d-157">ToFacilitiesQ</span><span class="sxs-lookup"><span data-stu-id="d378d-157">ToFacilitiesQ</span></span>|<span data-ttu-id="d378d-158">Sí</span><span class="sxs-lookup"><span data-stu-id="d378d-158">Yes</span></span>|<span data-ttu-id="d378d-159">Nativa</span><span class="sxs-lookup"><span data-stu-id="d378d-159">Native</span></span>|  
    |<span data-ttu-id="d378d-160">FromFacilitiesQ</span><span class="sxs-lookup"><span data-stu-id="d378d-160">FromFacilitiesQ</span></span>|<span data-ttu-id="d378d-161">Sí</span><span class="sxs-lookup"><span data-stu-id="d378d-161">Yes</span></span>|<span data-ttu-id="d378d-162">Nativa</span><span class="sxs-lookup"><span data-stu-id="d378d-162">Native</span></span>|  
    |<span data-ttu-id="d378d-163">FromFixedOrdersQ</span><span class="sxs-lookup"><span data-stu-id="d378d-163">FromFixedOrdersQ</span></span>|<span data-ttu-id="d378d-164">Sí</span><span class="sxs-lookup"><span data-stu-id="d378d-164">Yes</span></span>|<span data-ttu-id="d378d-165">Nativa</span><span class="sxs-lookup"><span data-stu-id="d378d-165">Native</span></span>|  
    |<span data-ttu-id="d378d-166">ToServicingSystemQ</span><span class="sxs-lookup"><span data-stu-id="d378d-166">ToServicingSystemQ</span></span>|<span data-ttu-id="d378d-167">Sí</span><span class="sxs-lookup"><span data-stu-id="d378d-167">Yes</span></span>|<span data-ttu-id="d378d-168">Nativa</span><span class="sxs-lookup"><span data-stu-id="d378d-168">Native</span></span>|  
    |<span data-ttu-id="d378d-169">ToCSRSystemQ</span><span class="sxs-lookup"><span data-stu-id="d378d-169">ToCSRSystemQ</span></span>|<span data-ttu-id="d378d-170">No</span><span class="sxs-lookup"><span data-stu-id="d378d-170">No</span></span>|<span data-ttu-id="d378d-171">HTTP</span><span class="sxs-lookup"><span data-stu-id="d378d-171">HTTP</span></span>|  
    |<span data-ttu-id="d378d-172">ToVendorSystemQ</span><span class="sxs-lookup"><span data-stu-id="d378d-172">ToVendorSystemQ</span></span>|<span data-ttu-id="d378d-173">No</span><span class="sxs-lookup"><span data-stu-id="d378d-173">No</span></span>|<span data-ttu-id="d378d-174">HTTP</span><span class="sxs-lookup"><span data-stu-id="d378d-174">HTTP</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d378d-175">Puede usar **administración de equipos** complemento para crear las colas.</span><span class="sxs-lookup"><span data-stu-id="d378d-175">You can use **Computer Management** snap-in to create the queues.</span></span> <span data-ttu-id="d378d-176">Para obtener más información sobre cómo crear una cola privada, consulte la documentación de Message Queue Server en [http://go.microsoft.com/fwlink/?LinkId=59264](http://go.microsoft.com/fwlink/?LinkId=59264).</span><span class="sxs-lookup"><span data-stu-id="d378d-176">For more information about how to create a private queue, see the Message Queuing documentation at [http://go.microsoft.com/fwlink/?LinkId=59264](http://go.microsoft.com/fwlink/?LinkId=59264).</span></span> <span data-ttu-id="d378d-177">Para obtener más información sobre cómo instalar MSMQ 3.0, consulte la documentación de Message Queue Server en [http://go.microsoft.com/fwlink/?LinkId=59265](http://go.microsoft.com/fwlink/?LinkId=59265).</span><span class="sxs-lookup"><span data-stu-id="d378d-177">For more information about how to install MSMQ 3.0, see the Message Queuing documentation at [http://go.microsoft.com/fwlink/?LinkId=59265](http://go.microsoft.com/fwlink/?LinkId=59265).</span></span>  
  
13. <span data-ttu-id="d378d-178">En un símbolo del sistema, cambie la carpeta actual a % BTSSolutionsPath%\BPM\Scripts, escriba `CreateTestDirectories.cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d378d-178">At a command prompt, change the current folder to the %BTSSolutionsPath%\BPM\Scripts, type `CreateTestDirectories.cmd`, and then press ENTER.</span></span>  
  
    -   <span data-ttu-id="d378d-179">En la carpeta %SystemDrive%\BPMTest, se crean las carpetas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d378d-179">The following folders are crated in %SystemDrive%\BPMTest folder</span></span>  
  
         <span data-ttu-id="d378d-180">CSRResponse-DSP</span><span class="sxs-lookup"><span data-stu-id="d378d-180">CSRResponse-DSP</span></span>  
  
         <span data-ttu-id="d378d-181">VendorResponse-DSP</span><span class="sxs-lookup"><span data-stu-id="d378d-181">VendorResponse-DSP</span></span>  
  
         <span data-ttu-id="d378d-182">OrderErrors-SP</span><span class="sxs-lookup"><span data-stu-id="d378d-182">OrderErrors-SP</span></span>  
  
         <span data-ttu-id="d378d-183">ErrorResponse-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="d378d-183">ErrorResponse-RP-TestRL</span></span>  
  
         <span data-ttu-id="d378d-184">Facilities-SP</span><span class="sxs-lookup"><span data-stu-id="d378d-184">Facilities-SP</span></span>  
  
         <span data-ttu-id="d378d-185">Facilities-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="d378d-185">Facilities-RP-TestRL</span></span>  
  
         <span data-ttu-id="d378d-186">HistoryInsert-SP</span><span class="sxs-lookup"><span data-stu-id="d378d-186">HistoryInsert-SP</span></span>  
  
         <span data-ttu-id="d378d-187">HistoryUpdate-SP</span><span class="sxs-lookup"><span data-stu-id="d378d-187">HistoryUpdate-SP</span></span>  
  
         <span data-ttu-id="d378d-188">Order-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="d378d-188">Order-RP-TestRL</span></span>  
  
         <span data-ttu-id="d378d-189">ServicingSystem-SP</span><span class="sxs-lookup"><span data-stu-id="d378d-189">ServicingSystem-SP</span></span>  
  
         <span data-ttu-id="d378d-190">Vendor-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="d378d-190">Vendor-RP-TestRL</span></span>  
  
         <span data-ttu-id="d378d-191">BizTalkErrors-SP</span><span class="sxs-lookup"><span data-stu-id="d378d-191">BizTalkErrors-SP</span></span>  
  
    -   <span data-ttu-id="d378d-192">La carpeta FromVendor se crea en la carpeta %SystemDrive%\Inetpub\ftproot.</span><span class="sxs-lookup"><span data-stu-id="d378d-192">FromVendor folder is created in the %SystemDrive%\Inetpub\ftproot folder.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d378d-193">Si el sistema Windows no está instalado en la unidad C, debería sustituir %SystemDrive% por C:.</span><span class="sxs-lookup"><span data-stu-id="d378d-193">If the Windows system is not installed on the C drive, you should replace %SystemDrive% with C:.</span></span> <span data-ttu-id="d378d-194">Los nombres de las carpetas tienen que coincidir con la dirección de los archivos de enlace que proporciona la solución BPM.</span><span class="sxs-lookup"><span data-stu-id="d378d-194">You have to match the folder names to the address in the binding files that the BPM solution provides.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d378d-195">La cuenta de servicio de BizTalk debe tener permiso de lectura/escritura en la carpeta FromVendor.</span><span class="sxs-lookup"><span data-stu-id="d378d-195">The BizTalk service account must have read/write permission to the FromVendor folder.</span></span>  
  
##  <a name="step5"></a><span data-ttu-id="d378d-196">Instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-196">Install the Business Process Management Solution</span></span>  
  
#### <a name="to-install-the-business-process-management-solution"></a><span data-ttu-id="d378d-197">Para instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-197">To install the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="d378d-198">En un símbolo del sistema, cambie la carpeta actual a % BTSSolutionsPath%\BPM, escriba `SetupBPM.bat`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d378d-198">At a command prompt, change the current folder to %BTSSolutionsPath%\BPM, type `SetupBPM.bat`, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d378d-199">Antes de ejecutar SetupBPM.bat, en los archivos **%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.WSDL** y **%BTSInstallPath%/SDK/ Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**, reemplace todas las instancias de 8f8bbebbb3fb375a por XXXXXXXXXXXXXXXX.</span><span class="sxs-lookup"><span data-stu-id="d378d-199">Before running SetupBPM.bat, in the files **%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.wsdl** and **%BTSInstallPath%/SDK/Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**, replace all instances of 8f8bbebbb3fb375a with XXXXXXXXXXXXXXXX.</span></span>  
  
     <span data-ttu-id="d378d-200">El archivo SetupBPM.bat realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d378d-200">The SetupBPM.bat performs the following tasks:</span></span>  
  
    1.  <span data-ttu-id="d378d-201">Crea una clave de nombre seguro único (SNK) para firmar los ensamblados de la solución BPM</span><span class="sxs-lookup"><span data-stu-id="d378d-201">Creates a unique strong name key (SNK) for signing the assemblies of the BPM Solution.</span></span>  
  
    2.  <span data-ttu-id="d378d-202">Extrae el símbolo de clave pública del SNK.</span><span class="sxs-lookup"><span data-stu-id="d378d-202">Extracts the public key token from the SNK.</span></span>  
  
    3.  <span data-ttu-id="d378d-203">Actualiza los archivos de enlace con el símbolo público.</span><span class="sxs-lookup"><span data-stu-id="d378d-203">Updates the binding files with the public token.</span></span>  
  
    4.  <span data-ttu-id="d378d-204">Genera la solución BPM e instala OpsAdapter.</span><span class="sxs-lookup"><span data-stu-id="d378d-204">Builds the BPM solution, and installs OpsAdapter.</span></span>  
  
    5.  <span data-ttu-id="d378d-205">Genera SSOApplicationConfig en la carpeta %BTSSolutionsPath%\Common.</span><span class="sxs-lookup"><span data-stu-id="d378d-205">Builds the SSOApplicationConfig in the %BTSSolutionsPath%\Common folder.</span></span>  
  
2.  <span data-ttu-id="d378d-206">Implementar reglas de negocios de Southridge Video utilizando el Asistente para implementar el motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="d378d-206">Deploy the Southridge Video business rules using the Business Rule Engine Deployment Wizard:</span></span>  
  
    1.  <span data-ttu-id="d378d-207">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="d378d-207">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d378d-208">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d378d-208">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d378d-209">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d378d-209">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
    2.  <span data-ttu-id="d378d-210">En el **bienvenida** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d378d-210">On the **Welcome** page, click **Next**.</span></span>  
  
    3.  <span data-ttu-id="d378d-211">En el **la tarea de implementación** página, seleccione **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d378d-211">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
    4.  <span data-ttu-id="d378d-212">En el **almacén de directivas** página mantener todos los demás valores predeterminados y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d378d-212">On the **Policy Store** page, keep all other default settings, and then click **Next**.</span></span>  
  
    5.  <span data-ttu-id="d378d-213">En el **archivo de motor de reglas de importación directiva o vocabulario** página, haga clic en **examinar**, seleccione el archivo DecodeAndValidateOrderRules.xml en la carpeta %BTSSolutionsPath%\BPM\Rules y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d378d-213">On the **Import Rules Engine Policy/Vocabulary file** page, click **Browse**, select the DecodeAndValidateOrderRules.xml file in the %BTSSolutionsPath%\BPM\Rules folder, and then click **Next**.</span></span>  
  
    6.  <span data-ttu-id="d378d-214">En el **listo** página, haga clic en **siguiente**y, a continuación, en la **Importando directiva o vocabulario** página, haga clic en **siguiente**</span><span class="sxs-lookup"><span data-stu-id="d378d-214">On the **Ready** page, click **Next**, and then on the **Importing Policy/Vocabulary** page, click **Next**</span></span>  
  
    7.  <span data-ttu-id="d378d-215">En la página de finalización, seleccione **vuelva a ejecutar el asistente** para abrir el Asistente para nuevo y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d378d-215">On the Completion page, select **Run the wizard again** to open the Wizard again, and then click **Finish**.</span></span>  
  
    8.  <span data-ttu-id="d378d-216">En el **bienvenida** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d378d-216">On the **Welcome** page, click **Next**.</span></span>  
  
    9. <span data-ttu-id="d378d-217">En el **la tarea de implementación** página, seleccione **directiva de implementación**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d378d-217">On the **Deployment Task** page, select **DeployPolicy**, and then click **Next**.</span></span>  
  
    10. <span data-ttu-id="d378d-218">En el **almacén de directivas** página mantener todos los demás valores predeterminados y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d378d-218">On the **Policy Store** page, keep all other default settings, and then click **Next**.</span></span>  
  
    11. <span data-ttu-id="d378d-219">En el **implementar Directiva** página, seleccione **DecodeAndValidateOrder 1.0** en el **directiva del motor de reglas** lista desplegable y, a continuación, haga clic en **siguiente** .</span><span class="sxs-lookup"><span data-stu-id="d378d-219">On the **Deploy Policy** page, select **DecodeAndValidateOrder 1.0** in the **Rule Engine Policy** drop-down list, and then click **Next**.</span></span>  
  
    12. <span data-ttu-id="d378d-220">En el **listo** página, haga clic en **siguiente**y, a continuación, en la **implementar la directiva de** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d378d-220">On the **Ready** page, click **Next**, and then on the **Deploying Policy** page, click **Next**.</span></span>  
  
    13. <span data-ttu-id="d378d-221">En la página Finalización, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d378d-221">On the Completion page, click **Finish**.</span></span>  
  
3.  <span data-ttu-id="d378d-222">Si instala la solución BPM en un equipo de 64 bits, a continuación</span><span class="sxs-lookup"><span data-stu-id="d378d-222">If you install the BPM solution on a 64-bit computer, then</span></span>  
  
    1.  <span data-ttu-id="d378d-223">Abra un símbolo del sistema de 32 bits como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `%SYSTEMROOT%\SYSWOW64\CMD.EXE`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d378d-223">Open a 32-bit command prompt as follow: Click **Start**, click **Run**, type `%SYSTEMROOT%\SYSWOW64\CMD.EXE`, and then press ENTER.</span></span>  
  
    2.  <span data-ttu-id="d378d-224">En un símbolo de sistema de 32 bits, cambie el directorio a la carpeta %BTSSolutionsPath%\BPM\Scripts.</span><span class="sxs-lookup"><span data-stu-id="d378d-224">At the 32-bit command prompt, change the directory to the %BTSSolutionsPath%\BPM\Scripts folder.</span></span>  
  
    3.  <span data-ttu-id="d378d-225">Abra CreateSouthridgeVideoApplication.cmd con el Bloc de notas y, a continuación, sustituya "%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe" por "%SystemDrive%\Archivos de programa\Archivos comunes\Enterprise Single Sign-On\ssomanage.exe".</span><span class="sxs-lookup"><span data-stu-id="d378d-225">Using Notepad, open the CreateSouthridgeVideoApplication.cmd, and then replace "%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe" with "%SystemDrive%\Program Files\Common Files\Enterprise Single Sign-On\ssomanage.exe".</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d378d-226">En un símbolo de sistema de 32 bits, cambie la variable %CommonProgramFiles% a "%ProgramFiles(x86)%\Common Files".</span><span class="sxs-lookup"><span data-stu-id="d378d-226">At a 32-bit command prompt, the %CommonProgramFiles% variable is changed to "%ProgramFiles(x86)%\Common Files".</span></span> <span data-ttu-id="d378d-227">Como la utilidad administrativa SSO está instalada en %ProgramFiles%, incluso en los equipos de 64 bits, deberá corregir la ruta.</span><span class="sxs-lookup"><span data-stu-id="d378d-227">Because the SSO administrative utility is installed in the %ProgramFiles% even on a 64-bit computer, you must fix the path.</span></span> <span data-ttu-id="d378d-228">DeployBPM.cmd llama a CreateSouthridgeVideoApplication.cmd.</span><span class="sxs-lookup"><span data-stu-id="d378d-228">The DeployBPM.cmd calls CreateSouthridgeVideoApplication.cmd.</span></span>  
  
    4.  <span data-ttu-id="d378d-229">En el símbolo del sistema de 32 bits, escriba el tipo `DeployBPM.cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d378d-229">At the 32-bit command prompt, type type `DeployBPM.cmd`, and then press ENTER.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d378d-230">DeployBPM.cmd debe ejecutarse en un símbolo de sistema de 32 bits porque incluye objetos x86 de acceso a VBScript que requieren la versión x86 de cscript.exe.</span><span class="sxs-lookup"><span data-stu-id="d378d-230">The DeployBPM.cmd must be run at a 32-bit command prompt because it includes the VB Script accessing x86 objects that requires the x86 version of cscript.exe.</span></span>  
  
4.  <span data-ttu-id="d378d-231">En un símbolo del sistema, cambie la carpeta actual a % BTSSolutionsPath%\BPM\Scripts, escriba `DeployBPM.cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d378d-231">At a command prompt, change the current folder to %BTSSolutionsPath%\BPM\Scripts, type `DeployBPM.cmd`, and then press ENTER.</span></span> <span data-ttu-id="d378d-232">DeployBPM.cmd realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d378d-232">The DeployBPM.cmd performs the following tasks:</span></span>  
  
    1.  <span data-ttu-id="d378d-233">Crea aplicaciones de BizTalk para la solución BPM.</span><span class="sxs-lookup"><span data-stu-id="d378d-233">Creates BizTalk Applications for the BPM Solution.</span></span>  
  
    2.  <span data-ttu-id="d378d-234">Agrega referencias entre las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d378d-234">Adds references between the applications.</span></span>  
  
    3.  <span data-ttu-id="d378d-235">Importa los archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="d378d-235">Imports the binding files.</span></span>  
  
    4.  <span data-ttu-id="d378d-236">Implementa los archivos de definición BAM.</span><span class="sxs-lookup"><span data-stu-id="d378d-236">Deploys the BAM definition files.</span></span>  
  
    5.  <span data-ttu-id="d378d-237">Registra el origen de eventos de SouthridgeVideo.</span><span class="sxs-lookup"><span data-stu-id="d378d-237">Registers the SouthridgeVideo event source.</span></span>  
  
    6.  <span data-ttu-id="d378d-238">Crea una aplicación afiliada de inicio de sesión único y guarda los valores de configuración en la aplicación SSO.</span><span class="sxs-lookup"><span data-stu-id="d378d-238">Creates a Single Sign-On (SSO) affiliated application, and saves configuration values to the SSO application.</span></span>  
  
5.  <span data-ttu-id="d378d-239">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d378d-239">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    1.  <span data-ttu-id="d378d-240">En el **consola de administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BTSScn.BPM.OrderBrokerApp**, expanda **ubicaciones de recepción**, haga clic en **proveedor-RP-RL**y, a continuación, haga clic en Propiedades.</span><span class="sxs-lookup"><span data-stu-id="d378d-240">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Applications**, expand **BTSScn.BPM.OrderBrokerApp**, expand **Receive Locations**, right-click **Vendor-RP-RL**, and then click Properties.</span></span>  
  
    2.  <span data-ttu-id="d378d-241">En el **propiedades** cuadro de diálogo, haga clic en **configurar**y, a continuación, escriba los valores como en la tabla siguiente en el **propiedades de transporte** cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="d378d-241">On the **Properties** dialog box, click **Configure**, and then enter values as the following table on the **Transport Properties** dialog box:</span></span>  
  
        |<span data-ttu-id="d378d-242">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="d378d-242">Property Name</span></span>|<span data-ttu-id="d378d-243">Valor</span><span class="sxs-lookup"><span data-stu-id="d378d-243">Value</span></span>|  
        |-------------------|-----------|  
        |<span data-ttu-id="d378d-244">**Server**</span><span class="sxs-lookup"><span data-stu-id="d378d-244">**Server**</span></span>|`localhost`|  
        |<span data-ttu-id="d378d-245">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="d378d-245">**User Name**</span></span>|<span data-ttu-id="d378d-246">\<*Nombre de cuenta de servicio de BizTalk*\></span><span class="sxs-lookup"><span data-stu-id="d378d-246">\<*BizTalk service account name*\></span></span>|  
        |<span data-ttu-id="d378d-247">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="d378d-247">**Password**</span></span>|<span data-ttu-id="d378d-248">\<*Contraseña de cuenta de servicio de BizTalk*\></span><span class="sxs-lookup"><span data-stu-id="d378d-248">\<*BizTalk service account password*\></span></span>|  
  
6.  <span data-ttu-id="d378d-249">Ejecute la solución BPM</span><span class="sxs-lookup"><span data-stu-id="d378d-249">Run the BPM Solution.</span></span> <span data-ttu-id="d378d-250">Para obtener más información acerca de cómo ejecutar la solución, vea [cómo ejecutar la solución de administración de procesos empresariales](../core/how-to-run-the-business-process-management-solution.md).</span><span class="sxs-lookup"><span data-stu-id="d378d-250">For more information about running the solution, see [How to Run the Business Process Management Solution](../core/how-to-run-the-business-process-management-solution.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d378d-251">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d378d-251">Next Steps</span></span>  
 <span data-ttu-id="d378d-252">Compruebe cómo funciona la solución de administración de negocio [cómo ejecutar la solución de administración de procesos empresariales](../core/how-to-run-the-business-process-management-solution.md).</span><span class="sxs-lookup"><span data-stu-id="d378d-252">You test how the Business Management Solution works in [How to Run the Business Process Management Solution](../core/how-to-run-the-business-process-management-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d378d-253">Vea también</span><span class="sxs-lookup"><span data-stu-id="d378d-253">See Also</span></span>  
 <span data-ttu-id="d378d-254">[Antes de instalar la solución de administración de procesos empresariales](../core/before-installing-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="d378d-254">[Before Installing the Business Process Management Solution](../core/before-installing-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="d378d-255">Configurar el equipo del desarrollador para la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="d378d-255">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)