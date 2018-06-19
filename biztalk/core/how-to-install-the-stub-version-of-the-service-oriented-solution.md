---
title: Cómo instalar la versión de código auxiliar del servicio en la solución orientada a servicios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IIS, installing virtual directories [service solutions]
- service solution tutorial, IIS virtual directories
- service solution tutorial, stub version
- deploying, BAM solutions [service solutions]
- service solution tutorial, solutions [BAM]
- service solution tutorial, service solutions
- SSO, configuring
- IBM WebSphere MQ Client
- service solution tutorial, IBM WebSphere MQ Client
- installing, tutorials
- service solutions, deploying
- service solution tutorial, SSO
- BAM, deploying solutions
- service solution tutorial, building solutions
- service solution tutorial, installing
ms.assetid: 45de7681-4df0-47a4-a02c-509140423a1e
caps.latest.revision: 53
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adaf5cb0117e0d571e0be0ddd42350ce3af2ba80
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010413"
---
# <a name="how-to-install-the-stub-version-of-the-service-oriented-solution"></a><span data-ttu-id="77fd4-102">Cómo instalar la versión de código auxiliar de esta solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-102">How to Install the Stub Version of the Service Oriented Solution</span></span>
<span data-ttu-id="77fd4-103">Los pasos siguientes describen cómo preparar el equipo para instalar la versión de código auxiliar de la solución orientada a servicios y cómo instalar ésta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="77fd4-103">The following steps describe how to prepare your computer before you install the stub version of the service oriented solution, and then how to install the solution on your computer.</span></span>  
  
-   [<span data-ttu-id="77fd4-104">Preparar el equipo para instalar la versión de código auxiliar de la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-104">Prepare the computer for installing the stub version of the Service Oriented Solution</span></span>](#step1)  
  
-   [<span data-ttu-id="77fd4-105">Instalar al cliente IBM WebSphere MQ para Windows</span><span class="sxs-lookup"><span data-stu-id="77fd4-105">Install the IBM WebSphere MQ Client for Windows</span></span>](#step3)  
  
-   [<span data-ttu-id="77fd4-106">Cree los directorios virtuales en IIS para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-106">Create the virtual directories in IIS for the Service Oriented Solution</span></span>](#step5)  
  
-   [<span data-ttu-id="77fd4-107">Crear solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-107">Build the Service Oriented Solution</span></span>](#step7)  
  
-   [<span data-ttu-id="77fd4-108">Crear las entradas de inicio de sesión único (SSO) empresarial y los valores en la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="77fd4-108">Create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>](#step9)  
  
-   [<span data-ttu-id="77fd4-109">Implementar la definición de BAM para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-109">Deploy the BAM definition for the Service Oriented Solution</span></span>](#step11)  
  
-   [<span data-ttu-id="77fd4-110">Implementar la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-110">Deploy the Service Oriented Solution</span></span>](#step13)  
  
##  <a name="step1"></a><span data-ttu-id="77fd4-111">Preparar el equipo para instalar la versión de código auxiliar de la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-111">Prepare the computer for installing the stub version of the Service Oriented Solution</span></span>  
  
#### <a name="to-prepare-the-computer-for-installing-the-stub-version-of-the-service-oriented-solution"></a><span data-ttu-id="77fd4-112">Para preparar el equipo para instalar la versión de código auxiliar de la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-112">To prepare the computer for installing the stub version of the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="77fd4-113">Asegúrese de que el **sitio Web predeterminado** está configurado para usar ASP.NET 2.X.</span><span class="sxs-lookup"><span data-stu-id="77fd4-113">Make sure that the **Default Web Site** is configured to use ASP.NET 2.X.</span></span>  
  
    1.  <span data-ttu-id="77fd4-114">Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    2.  <span data-ttu-id="77fd4-115">En el **Internet Information Services (IIS) Manager**, el nombre del equipo, expanda **sitios**, expanda **sitio Web predeterminado**, expanda **aspnet_client**, expanda **system_web**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-115">In the **Internet Information Services (IIS) Manager**, the machine name, expand  **Sites**, expand **Default Web Site**, expand **aspnet_client**, expand **system_web**.</span></span>  
  
    3.  <span data-ttu-id="77fd4-116">Asegúrese de que la subcarpeta es 2.X.</span><span class="sxs-lookup"><span data-stu-id="77fd4-116">Make sure that the sub-folder is 2.X.</span></span>  
  
2.  <span data-ttu-id="77fd4-117">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Services**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span> <span data-ttu-id="77fd4-118">Mediante el **servicios** consola, asegúrese de que se están ejecutando los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="77fd4-118">Using the **Services** console, make sure that the following services are running:</span></span>  
  
    -   <span data-ttu-id="77fd4-119">**Publicación en World Wide Web**</span><span class="sxs-lookup"><span data-stu-id="77fd4-119">**World Wide Web Publishing**</span></span>  
  
3.  <span data-ttu-id="77fd4-120">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**, haga clic en **administración de equipos** consola y, a continuación, agregue el Cuenta de servicio de BizTalk al grupo de administradores local.</span><span class="sxs-lookup"><span data-stu-id="77fd4-120">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
4.  <span data-ttu-id="77fd4-121">Si ha instalado Windows SharePoint Services, excluya la (raíz) de la **sitio Web predeterminado** de Windows SharePoint Services rutas de acceso administradas como sigue: haga clic en **iniciar**, seleccione **todos los programas** , seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-121">If you installed Windows SharePoint Services, exclude the (root) of the **Default Web Site** from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    1.  <span data-ttu-id="77fd4-122">En **configuración del servidor Virtual**, seleccione **configurar el servidor virtual**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-122">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
    2.  <span data-ttu-id="77fd4-123">En el **lista de servidores virtuales** página, haga clic en **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-123">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
    3.  <span data-ttu-id="77fd4-124">En el **configuración del servidor Virtual** página, haga clic en **definir rutas administradas**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-124">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
    4.  <span data-ttu-id="77fd4-125">En el **rutas incluidas** sección de la **definir rutas administradas** página, seleccione **raíz** y, a continuación, haga clic en **quitar rutas seleccionadas**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-125">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
    5.  <span data-ttu-id="77fd4-126">En el símbolo del sistema, ejecute IISReset.</span><span class="sxs-lookup"><span data-stu-id="77fd4-126">At a command prompt, perform an IISReset.</span></span>  
  
5.  <span data-ttu-id="77fd4-127">Cierre la sesión y, a continuación, inicie una sesión en el equipo con la cuenta de servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="77fd4-127">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
6.  <span data-ttu-id="77fd4-128">Abra un símbolo del sistema, escriba el comando siguiente y, a continuación, presione ENTRAR para establecer el entorno %BTSSolutionsPath%.</span><span class="sxs-lookup"><span data-stu-id="77fd4-128">Open a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment.</span></span> <span data-ttu-id="77fd4-129">A continuación, cierre el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="77fd4-129">Then, exit the command prompt.</span></span>  
  
    -   <span data-ttu-id="77fd4-130">setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span><span class="sxs-lookup"><span data-stu-id="77fd4-130">setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="77fd4-131">Si está utilizando un equipo de 64 bits, escriba %ProgramFiles(x86)% en lugar de %ProgramFiles%.</span><span class="sxs-lookup"><span data-stu-id="77fd4-131">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="77fd4-132">Para obtener más información acerca del comando SETX, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span><span class="sxs-lookup"><span data-stu-id="77fd4-132">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
##  <a name="step3"></a><span data-ttu-id="77fd4-133">Instalar al cliente IBM WebSphere MQ para Windows</span><span class="sxs-lookup"><span data-stu-id="77fd4-133">Install the IBM WebSphere MQ Client for Windows</span></span>  
  
#### <a name="to-install-the-ibm-websphere-mq-client-for-windows"></a><span data-ttu-id="77fd4-134">Para instalar el cliente IBM WebSphere MQ para Windows</span><span class="sxs-lookup"><span data-stu-id="77fd4-134">To install the IBM WebSphere MQ Client for Windows</span></span>  
  
1.  <span data-ttu-id="77fd4-135">Descargue la última versión del cliente IBM WebSphere MQ para Windows.</span><span class="sxs-lookup"><span data-stu-id="77fd4-135">Download the latest version of IBM WebSphere MQ Client for Windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77fd4-136">Aunque la versión de código auxiliar de la solución no requiere IBM WebSphere Server, la aplicación cliente utiliza como referencia el archivo amqmdnet.dll incluido en el cliente IBM WebSphere MQ para Windows y, por tanto, es necesario instalarlo.</span><span class="sxs-lookup"><span data-stu-id="77fd4-136">Even if the stub version of the solution doesn't require IBM WebSphere Server, the client application references the amqmdnet.dll file provided by IBM WebSphere MQ Client for Windows, so you must install it.</span></span> <span data-ttu-id="77fd4-137">En realidad, el cliente de la versión de código auxiliar no realiza llamadas a API del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="77fd4-137">The client of the stub version does not actually call an API in the DLL.</span></span> <span data-ttu-id="77fd4-138">Sólo es necesario para compilar y ejecutar la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="77fd4-138">It is required only for compiling and running the client application.</span></span> <span data-ttu-id="77fd4-139">Puede descargar el cliente IBM WebSphere MQ para Windows desde el sitio Web de IBM.</span><span class="sxs-lookup"><span data-stu-id="77fd4-139">You can download IBM WebSphere MQ Client for Windows from the IBM Web site.</span></span>  
  
2.  <span data-ttu-id="77fd4-140">Instale el cliente IBM WebSphere MQ para Windows.</span><span class="sxs-lookup"><span data-stu-id="77fd4-140">Install IBM WebSphere MQ Client for Windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77fd4-141">No es necesario configurar el cliente IBM WebSphere MQ para Windows.</span><span class="sxs-lookup"><span data-stu-id="77fd4-141">You don't need to configure IBM WebSphere MQ Client for Windows.</span></span> <span data-ttu-id="77fd4-142">Mantener toda la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="77fd4-142">Keep all of the default settings.</span></span>  
  
3.  <span data-ttu-id="77fd4-143">Agregue las clases WebSphere MQ para el ensamblado .NET a la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="77fd4-143">Add WebSphere MQ classes for the .NET assembly to the global assembly cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="77fd4-144">En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, desplácese al directorio \<directorio de instalación de MQSeries de IBM\>\bin.</span><span class="sxs-lookup"><span data-stu-id="77fd4-144">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, navigate to the directory \<IBM MQSeries Installation Directory\>\bin.</span></span>  
  
    2.  <span data-ttu-id="77fd4-145">Ejecute el siguiente comando (asegúrese de que gacutil.exe se encuentra en el entorno de la ruta):</span><span class="sxs-lookup"><span data-stu-id="77fd4-145">Run the following command (make sure gacutil.exe is in the path environment):</span></span>  
  
         `gacutil.exe /i amqmdnet.dll`  
  
##  <a name="step5"></a><span data-ttu-id="77fd4-146">Cree los directorios virtuales en IIS para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-146">Create the virtual directories in IIS for the Service Oriented Solution</span></span>  
  
#### <a name="to-create-the-virtual-directories-in-iis-for-the-service-oriented-solution"></a><span data-ttu-id="77fd4-147">Para crear en IIS los directorios virtuales para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-147">To create the virtual directories in IIS for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="77fd4-148">En el **Internet Information Services (IIS) Manager**, haga clic en **grupos de aplicaciones**, seleccione **Agregar grupo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-148">In the **Internet Information Services (IIS) Manager**, right-click **Application Pools**, select **Add Application Pool**.</span></span>  
  
     <span data-ttu-id="77fd4-149">En el **Agregar grupo de aplicaciones** cuadro de diálogo, escriba `SSOStubAppPool` en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-149">On the **Add Application Pool** dialog box, type `SSOStubAppPool` in the **Name** text box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="77fd4-150">Los directorios virtuales que utiliza la solución orientada a servicios incluye el servicio Web publicado para la versión de código auxiliar de las orquestaciones, el servicio Web SAP de código auxiliar, el servicio Web de seguimiento de pago de código auxiliar y el servicio Web de de código auxiliar de transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="77fd4-150">The virtual directories that service-oriented solution uses include the published Web service for the stub version of orchestrations, the stub SAP Web service, the stub Payment Tracker Web service, and the stub Pending Transaction Web service.</span></span>  
  
2.  <span data-ttu-id="77fd4-151">En el **Internet Information Services (IIS) Manager**, haga clic en el grupo de aplicaciones recién creado y, a continuación, haga clic en **configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-151">In the **Internet Information Services (IIS) Manager**, right-click the application pool that you just created, and then click **Advanced Settings**.</span></span>  
  
3.  <span data-ttu-id="77fd4-152">Haga clic en la columna a la derecha de la **identidad** propiedad y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="77fd4-152">Click in the column to the right of the **Identity** property, and then click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="77fd4-153">En el **identidad del grupo de aplicaciones** cuadro de diálogo, seleccione la **cuenta personalizada** opción y, a continuación, haga clic en **establecer**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-153">In the **Application Pool Identity** dialog box, select the **Custom Account** option, and then click **Set**.</span></span>  
  
5.  <span data-ttu-id="77fd4-154">En el **establecer credenciales** cuadro de diálogo, especifique un nombre de usuario y una contraseña, confirme la contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-154">In the **Set Credentials** dialog box, specify a username and password, confirm the password, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77fd4-155">Este usuario debe tener permiso para ejecutar el servicio Web de proxy de orquestación y debe agregarse a uno de los grupos de administradores de BizTalk Server, administradores de SSO o administradores de aplicaciones afiliadas de SSO.</span><span class="sxs-lookup"><span data-stu-id="77fd4-155">This user must have permission to execute the Orchestration Proxy Web service, and must be added to one of the BizTalk Server Administrators, SSO Administrators, or SSO Affiliated Administrators groups</span></span>  
  
6.  <span data-ttu-id="77fd4-156">Haga clic en **Aceptar** para cerrar el **identidad del grupo de aplicaciones** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="77fd4-156">Click **OK** to close the **Application Pool Identity** dialog box.</span></span>  
  
7.  <span data-ttu-id="77fd4-157">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Configuración avanzada** .</span><span class="sxs-lookup"><span data-stu-id="77fd4-157">Click **OK** to close the **Advanced Settings** dialog box.</span></span>  
  
8.  <span data-ttu-id="77fd4-158">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-158">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
    1.  <span data-ttu-id="77fd4-159">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión del adaptador:</span><span class="sxs-lookup"><span data-stu-id="77fd4-159">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="77fd4-160">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub</span><span class="sxs-lookup"><span data-stu-id="77fd4-160">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub</span></span>  
  
         <span data-ttu-id="77fd4-161">Ruta de acceso = \<directorio de instalación de BizTalk\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub</span><span class="sxs-lookup"><span data-stu-id="77fd4-161">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub</span></span>  
  
         <span data-ttu-id="77fd4-162">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="77fd4-162">Access Permissions = Read, Run scripts</span></span>  
  
    2.  <span data-ttu-id="77fd4-163">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión del adaptador:</span><span class="sxs-lookup"><span data-stu-id="77fd4-163">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="77fd4-164">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span><span class="sxs-lookup"><span data-stu-id="77fd4-164">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span></span>  
  
         <span data-ttu-id="77fd4-165">Ruta de acceso = \<directorio de instalación de BizTalk\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span><span class="sxs-lookup"><span data-stu-id="77fd4-165">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span></span>  
  
         <span data-ttu-id="77fd4-166">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="77fd4-166">Access Permissions = Read, Run scripts</span></span>  
  
    3.  <span data-ttu-id="77fd4-167">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión del adaptador:</span><span class="sxs-lookup"><span data-stu-id="77fd4-167">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="77fd4-168">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span><span class="sxs-lookup"><span data-stu-id="77fd4-168">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span></span>  
  
         <span data-ttu-id="77fd4-169">Ruta de acceso = \<directorio de instalación de BizTalk\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span><span class="sxs-lookup"><span data-stu-id="77fd4-169">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span></span>  
  
         <span data-ttu-id="77fd4-170">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="77fd4-170">Access Permissions = Read, Run scripts</span></span>  
  
    4.  <span data-ttu-id="77fd4-171">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión del adaptador:</span><span class="sxs-lookup"><span data-stu-id="77fd4-171">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="77fd4-172">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker</span><span class="sxs-lookup"><span data-stu-id="77fd4-172">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker</span></span>  
  
         <span data-ttu-id="77fd4-173">Ruta de acceso = \<directorio de instalación de BizTalk\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack</span><span class="sxs-lookup"><span data-stu-id="77fd4-173">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack</span></span>  
  
         <span data-ttu-id="77fd4-174">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="77fd4-174">Access Permissions = Read, Run scripts</span></span>  
  
9. <span data-ttu-id="77fd4-175">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web,** expandir la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:</span><span class="sxs-lookup"><span data-stu-id="77fd4-175">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="77fd4-176">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a **SSOStubAppPool** que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="77fd4-176">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="77fd4-177">Haga clic en **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro de grupo, seleccione **autenticación integrada de Windows habilitado**y, a continuación, desactive las demás **de acceso de autenticación** casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="77fd4-177">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, select **Only Integrated Windows Authentication enabled**, and then clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="77fd4-178">Haga clic en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="77fd4-178">Click **OK** to exit.</span></span>  
  
10. <span data-ttu-id="77fd4-179">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web,** expandir la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:</span><span class="sxs-lookup"><span data-stu-id="77fd4-179">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="77fd4-180">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a **SSOStubAppPool** que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="77fd4-180">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="77fd4-181">Haga clic en **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-181">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="77fd4-182">Haga clic en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="77fd4-182">Click **OK** to exit.</span></span>  
  
11. <span data-ttu-id="77fd4-183">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web,** expandir la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:</span><span class="sxs-lookup"><span data-stu-id="77fd4-183">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="77fd4-184">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a **SSOStubAppPool** que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="77fd4-184">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="77fd4-185">Haga clic en **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-185">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="77fd4-186">Haga clic en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="77fd4-186">Click **OK** to exit.</span></span>  
  
12. <span data-ttu-id="77fd4-187">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web,** expandir la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:</span><span class="sxs-lookup"><span data-stu-id="77fd4-187">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="77fd4-188">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a **SSOStubAppPool** que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="77fd4-188">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="77fd4-189">Haga clic en **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-189">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="77fd4-190">Haga clic en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="77fd4-190">Click **OK** to exit.</span></span>  
  
##  <a name="step7"></a><span data-ttu-id="77fd4-191">Crear solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-191">Build the Service Oriented Solution</span></span>  
  
#### <a name="to-build-the-service-oriented-solution"></a><span data-ttu-id="77fd4-192">Para compilar la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-192">To build the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="77fd4-193">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-193">Start **Visual Studio Command Prompt**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77fd4-194">En los archivos **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs** y **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\ customerserviceport.asmx.cs**, reemplace todas las instancias de 17f20caea2afcc8c por a1054514fc67bded.</span><span class="sxs-lookup"><span data-stu-id="77fd4-194">In the files **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs** and **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\customerserviceport.asmx.cs**, replace all the instances of 17f20caea2afcc8c with a1054514fc67bded.</span></span>  
  
2.  <span data-ttu-id="77fd4-195">En el símbolo del sistema de Visual Studio, cambie el directorio por la carpeta %RutaSolucionesBTS%\SO\BTSSoln y, a continuación, ejecute el siguiente comando para generar la versión de código auxiliar de la solución orientada a servicios.</span><span class="sxs-lookup"><span data-stu-id="77fd4-195">At the Visual Studio Command Prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln folder, and then run the following command to build the stub version of service-oriented solution.</span></span>  
  
    -   `SetupBTSSoln.bat`  
  
    > [!NOTE]
    >  <span data-ttu-id="77fd4-196">En los archivos que se indican a continuación, sustituya todas las instancias de 17f20caea2afcc8c por el token de clave pública actual.</span><span class="sxs-lookup"><span data-stu-id="77fd4-196">In the files listed below, replace all the instances of 17f20caea2afcc8c with the current public key token.</span></span>  
    >   
    >  -   <span data-ttu-id="77fd4-197">%RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="77fd4-197">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs</span></span>  
    > -   <span data-ttu-id="77fd4-198">%RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="77fd4-198">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs</span></span>  
    > -   <span data-ttu-id="77fd4-199">%RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="77fd4-199">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs</span></span>  
    > -   <span data-ttu-id="77fd4-200">%RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs</span><span class="sxs-lookup"><span data-stu-id="77fd4-200">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs</span></span>  
    > -   <span data-ttu-id="77fd4-201">%RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs</span><span class="sxs-lookup"><span data-stu-id="77fd4-201">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs</span></span>  
    > -   <span data-ttu-id="77fd4-202">%RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="77fd4-202">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs</span></span>  
  
##  <a name="step9"></a><span data-ttu-id="77fd4-203">Crear las entradas de inicio de sesión único (SSO) empresarial y los valores en la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="77fd4-203">Create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>  
  
#### <a name="to-create-the-enterprise-single-sign-on-sso-entries-and-values-in-the-sso-database"></a><span data-ttu-id="77fd4-204">Para crear las entradas y valores del inicio de sesión único (SSO) empresarial en la base de datos de SSO</span><span class="sxs-lookup"><span data-stu-id="77fd4-204">To create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>  
  
1.  <span data-ttu-id="77fd4-205">Abra un símbolo del sistema, cambie el directorio actual a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts y, a continuación, ejecute el siguiente comando para generar el entorno PATH en la carpeta de inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="77fd4-205">Open a command prompt, change the current directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts, and then run the following command to set the PATH environment for the Enterprise Single Sign-On folder.</span></span>  
  
    -   `Set PATH=%PATH%;%ProgramFiles%\"Common Files\Enterprise Single Sign-On"`  
  
2.  <span data-ttu-id="77fd4-206">En el símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts, abra el archivo ConfigStoreApp.xml en Notepad y, a continuación, revise el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="77fd4-206">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, open ConfigStoreApp.xml using Notepad, and then review the contents of the file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77fd4-207">Este archivo define la aplicación de almacenamiento de configuración de SSO que el escenario emplea para almacenar parámetros de configuración.</span><span class="sxs-lookup"><span data-stu-id="77fd4-207">This file defines the configuration store application in SSO that the scenario uses to store configuration parameters.</span></span> <span data-ttu-id="77fd4-208">Algunos de los parámetros de configuración incluyen la **tiempo de espera** valor que se usa para comunicarse con SAP (para las tres versiones).</span><span class="sxs-lookup"><span data-stu-id="77fd4-208">Some of the configuration parameters include the **Timeout** value used to communicate with SAP (for all three versions).</span></span> <span data-ttu-id="77fd4-209">No es necesario realizar cambios en este archivo.</span><span class="sxs-lookup"><span data-stu-id="77fd4-209">No changes to this file are necessary.</span></span>  
  
3.  <span data-ttu-id="77fd4-210">En el símbolo del sistema, ejecute el comando siguiente para crear la aplicación de almacenamiento de configuración de SSO.</span><span class="sxs-lookup"><span data-stu-id="77fd4-210">At the command prompt, run the following command to create the SSO configuration store application.</span></span>  
  
    -   `ssomanage -createapps ConfigStoreApp.xml`  
  
4.  <span data-ttu-id="77fd4-211">En el símbolo del sistema, abra el archivo SetConfigValuesInSSO.cmd con Notepad y revise su contenido.</span><span class="sxs-lookup"><span data-stu-id="77fd4-211">At the command prompt, open SetConfigValuesInSSO.cmd using Notepad, and then review the contents of the file</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77fd4-212">Este archivo de comandos establece los valores de los parámetros de configuración de la base de datos SSO.</span><span class="sxs-lookup"><span data-stu-id="77fd4-212">This command file sets the values of the configuration parameters in the SSO database.</span></span> <span data-ttu-id="77fd4-213">Contiene varias instrucciones SET que establecen los valores de las variables locales al principio del archivo de comandos.</span><span class="sxs-lookup"><span data-stu-id="77fd4-213">It contains several set statements that set the values in local variables in the beginning of the command file.</span></span> <span data-ttu-id="77fd4-214">El **SAPAdapterTimeout**, **PendingTransactionsAdapterTimeout**, y **PaymentTrackingAdapterTimeout** valores se utilizan en la versión de código auxiliar y el adaptador.</span><span class="sxs-lookup"><span data-stu-id="77fd4-214">The **SAPAdapterTimeout**, **PendingTransactionsAdapterTimeout**, and **PaymentTrackingAdapterTimeout** values are used in the stub and adapter version.</span></span> <span data-ttu-id="77fd4-215">Los valores restantes se utilizan en la versión en línea.</span><span class="sxs-lookup"><span data-stu-id="77fd4-215">The remaining values are used in the inline version.</span></span> <span data-ttu-id="77fd4-216">No es necesario realizar cambios en este archivo para la versión de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="77fd4-216">No changes to this file are necessary for stub version.</span></span>  
  
5.  <span data-ttu-id="77fd4-217">En el símbolo del sistema, escriba `SetConfigValuesInSSO.cmd`, y, a continuación, presione ENTRAR para almacenar los valores en la aplicación de almacenamiento de configuración de SSO.</span><span class="sxs-lookup"><span data-stu-id="77fd4-217">At the command prompt, type `SetConfigValuesInSSO.cmd`, and then press ENTER to store the values in the SSO configuration store application.</span></span>  
  
6.  <span data-ttu-id="77fd4-218">En el símbolo del sistema, ejecute el siguiente comando para habilitar los vales en SSO:</span><span class="sxs-lookup"><span data-stu-id="77fd4-218">At the command prompt, run the following command to enable tickets in SSO:</span></span>  
  
    -   `ssomanage -tickets yes yes`  
  
##  <a name="step11"></a><span data-ttu-id="77fd4-219">Implementar la definición de BAM para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-219">Deploy the BAM definition for the Service Oriented Solution</span></span>  
  
#### <a name="to-deploy-the-bam-definition-for-the-service-oriented-solution"></a><span data-ttu-id="77fd4-220">Para implementar la definición de SAE para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-220">To deploy the BAM definition for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="77fd4-221">En el símbolo del sistema, escriba el siguiente comando y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="77fd4-221">At a command prompt, type the following command, and then press ENTER.</span></span> <span data-ttu-id="77fd4-222">De este modo, se configurará la ruta para buscar la utilidad de SAE:</span><span class="sxs-lookup"><span data-stu-id="77fd4-222">This sets the path to find the BAM utility:</span></span>  
  
    -   <span data-ttu-id="77fd4-223">CONJUNTO PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking</span><span class="sxs-lookup"><span data-stu-id="77fd4-223">SET PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking</span></span>  
  
2.  <span data-ttu-id="77fd4-224">En el símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\BAM, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="77fd4-224">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\BAM folder, and type the following command, and then press ENTER:</span></span>  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
        > [!NOTE]
        >  <span data-ttu-id="77fd4-225">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="77fd4-225">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
##  <a name="step13"></a><span data-ttu-id="77fd4-226">Implementar solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-226">Deploy the Service Oriented Solution</span></span>  
  
#### <a name="to-deploy-the-service-oriented-solution"></a><span data-ttu-id="77fd4-227">Para implementar la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-227">To deploy the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="77fd4-228">Abra un símbolo del sistema y, a continuación, cambie el directorio a la carpeta %RutaSolucionesBTS%\SO\BTSSoln\Scripts.</span><span class="sxs-lookup"><span data-stu-id="77fd4-228">Open a command prompt and change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="77fd4-229">Modificar el **DeployStubBinding.cmd** archivo sustituyendo todas las instancias de "debug" y "development" por "release".</span><span class="sxs-lookup"><span data-stu-id="77fd4-229">Modify the **DeployStubBinding.cmd** file by replacing all the instances of “debug” and “development” with “release”.</span></span>  
  
3.  <span data-ttu-id="77fd4-230">Abra un símbolo del sistema y, a continuación, cambie el directorio a la carpeta %RutaSolucionesBTS%\SO\BTSSoln\Scripts.</span><span class="sxs-lookup"><span data-stu-id="77fd4-230">Open a command prompt and change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span> <span data-ttu-id="77fd4-231">Escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="77fd4-231">Type the following command, and then press ENTER:</span></span>  
  
    -   `DeployStubBinding.cmd`  
  
4.  <span data-ttu-id="77fd4-232">En el símbolo del sistema, ejecute el comando siguiente para iniciar las orquestaciones de la versión de código auxiliar:</span><span class="sxs-lookup"><span data-stu-id="77fd4-232">At the command prompt, run the following command to start the orchestrations for the stub version</span></span>  
  
    -   `Startstub.vbs`  
  
## <a name="next-steps"></a><span data-ttu-id="77fd4-233">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="77fd4-233">Next Steps</span></span>  
 <span data-ttu-id="77fd4-234">Probar el funcionamiento de la versión de código auxiliar de la solución orientada a servicios en [cómo ejecutar la solución orientada a servicios](../core/how-to-run-the-service-oriented-solution.md).</span><span class="sxs-lookup"><span data-stu-id="77fd4-234">You test how the stub version of the service-oriented solution works in [How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77fd4-235">Vea también</span><span class="sxs-lookup"><span data-stu-id="77fd4-235">See Also</span></span>  
 <span data-ttu-id="77fd4-236">[Antes de instalar la solución orientada a servicios](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="77fd4-236">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="77fd4-237">[Cómo instalar las versiones de adaptador del servicio y en línea solución orientada a servicios](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="77fd4-237">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="77fd4-238">Configurar el equipo del desarrollador para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="77fd4-238">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)