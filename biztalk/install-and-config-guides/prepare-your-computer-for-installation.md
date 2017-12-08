---
title: "Preparar el equipo para la instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 2016-03-15
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53df7a2f-638b-4921-a97f-736760248526
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a493c1a0ef38e9be5e229ff82f8773211adfe765
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-your-computer-for-installation"></a><span data-ttu-id="14182-102">Preparar el equipo para la instalación</span><span class="sxs-lookup"><span data-stu-id="14182-102">Prepare Your Computer for Installation</span></span>
<span data-ttu-id="14182-103">En este tema se muestran los pasos necesarios para preparar el equipo, mediante la instalación y configuración de todos los requisitos previos de software, y para crear cuentas y configurar permisos.</span><span class="sxs-lookup"><span data-stu-id="14182-103">This topic lists the steps to prepare your computer by installing and configuring all software prerequisites, and then creating accounts and setting permissions.</span></span>  

> [!TIP] 
> <span data-ttu-id="14182-104">Un MVP de integración ha preparado una guía paso a paso muy detallada para instalar los requisitos previos y BizTalk Server: [BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/) (Instalación y configuración de BizTalk 2013, parte 1).</span><span class="sxs-lookup"><span data-stu-id="14182-104">An integration MVP prepared a very detailed step-by-step guide to install the prerequisites, and BizTalk Server:  [BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/).</span></span>  
> 
> <span data-ttu-id="14182-105">Microsoft no recomienda algunos pasos, como deshabilitar el Control de acceso de usuarios (UAC) o el Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="14182-105">Some steps are not recommended by Microsoft, such as disabling User Access Control (UAC) or Windows Firewall.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="14182-106">Complete estas tareas en el orden que se indica.</span><span class="sxs-lookup"><span data-stu-id="14182-106">Complete these tasks in the order listed.</span></span>  
  
##  <a name="BKMK_InstUpdates"></a> <span data-ttu-id="14182-107">Instalar actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="14182-107">Install Windows Updates</span></span>  
  
-   <span data-ttu-id="14182-108">**Windows 7**: haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="14182-108">**Windows 7**: Click Start.</span></span> <span data-ttu-id="14182-109">En el cuadro de texto **Buscar**, escriba **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="14182-109">In the **Search** text box, type **Windows Update**.</span></span>  
  
-   <span data-ttu-id="14182-110">**Windows 8.1, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] y [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2**: pulse la tecla Windows del teclado y escriba **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="14182-110">**Windows 8.1, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], and [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2**: Click the Windows button on the keyboard and type **Windows Update**.</span></span> <span data-ttu-id="14182-111">En los resultados de la búsqueda, haga clic en **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="14182-111">From the search results, click **Windows Update**.</span></span>  
  
 <span data-ttu-id="14182-112">Tras instalar las actualizaciones, puede ser necesario reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="14182-112">After installing updates, you may need to restart the computer.</span></span>  
  
##  <a name="BKMK_IIS"></a> <span data-ttu-id="14182-113">Habilitar Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="14182-113">Enable Internet Information Services</span></span>  
 <span data-ttu-id="14182-114">Microsoft Internet Information Services (IIS) proporciona una infraestructura de aplicación web para numerosas características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], incluidas:</span><span class="sxs-lookup"><span data-stu-id="14182-114">Microsoft Internet Information Services (IIS) provides a Web application infrastructure for many [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features, including:</span></span>  
  
-   <span data-ttu-id="14182-115">adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="14182-115">HTTP adapter</span></span>  
  
-   <span data-ttu-id="14182-116">Adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="14182-116">SOAP adapter</span></span>  
  
-   <span data-ttu-id="14182-117">Adaptador de Windows Sharepoint Services</span><span class="sxs-lookup"><span data-stu-id="14182-117">Windows SharePoint Services adapter</span></span>  
  
-   <span data-ttu-id="14182-118">Cifrado de Capa de sockets seguros (SSL)</span><span class="sxs-lookup"><span data-stu-id="14182-118">Secure Sockets Layer (SSL) encryption</span></span>  
  
-   <span data-ttu-id="14182-119">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="14182-119">BAM Portal</span></span>  
  
#### <a name="install-iis-75-on-windows-7-sp1"></a><span data-ttu-id="14182-120">Instalar IIS 7.5 en Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="14182-120">Install IIS 7.5 on Windows 7 SP1</span></span>  
  
1.  <span data-ttu-id="14182-121">Seleccione **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="14182-121">Select **Start**.</span></span> <span data-ttu-id="14182-122">En el cuadro de texto **Buscar**, escriba **Programas y características** y ábralo.</span><span class="sxs-lookup"><span data-stu-id="14182-122">In the **Search** text box, type **Programs and Features**, and open it.</span></span>  
  
2.  <span data-ttu-id="14182-123">Seleccione **Activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="14182-123">Select**Turn Windows features on or off**.</span></span>  
  
3.  <span data-ttu-id="14182-124">Seleccione **Internet Information Services** y expanda **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="14182-124">Select**Internet Information Services** and expand **Internet Information Services**.</span></span> <span data-ttu-id="14182-125">Además de las opciones predeterminadas, seleccione las siguientes:</span><span class="sxs-lookup"><span data-stu-id="14182-125">In addition to the default checked options, also check the following:</span></span>  
  
    -   <span data-ttu-id="14182-126">**Herramientas de administración web**: Seleccione también:</span><span class="sxs-lookup"><span data-stu-id="14182-126">**Web Management Tools**: Also check:</span></span>  
  
        -   <span data-ttu-id="14182-127">Compatibilidad con la administración de IIS 6:</span><span class="sxs-lookup"><span data-stu-id="14182-127">IIS 6 Management Compatibility:</span></span>  
  
            -   <span data-ttu-id="14182-128">Consola de administración de IIS 6</span><span class="sxs-lookup"><span data-stu-id="14182-128">IIS 6 Management Console</span></span>  
  
            -   <span data-ttu-id="14182-129">Compatibilidad con la configuración de IIS 6 y metabase de IIS</span><span class="sxs-lookup"><span data-stu-id="14182-129">IIS Metabase and IIS 6 configuration compatibility</span></span>  
  
        -   <span data-ttu-id="14182-130">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="14182-130">IIS Management Console</span></span>  
  
    -   <span data-ttu-id="14182-131">**Servicios World Wide Web**: expanda **Seguridad** y seleccione también:</span><span class="sxs-lookup"><span data-stu-id="14182-131">**World Wide Web Services**: Expand **Security** and also select:</span></span>  
  
        -   <span data-ttu-id="14182-132">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="14182-132">Basic Authentication</span></span>  
  
        -   <span data-ttu-id="14182-133">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="14182-133">Windows Authentication</span></span>  
  
4.  <span data-ttu-id="14182-134">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="14182-134">Select **OK**.</span></span> <span data-ttu-id="14182-135">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="14182-135">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="14182-136">En [http://go.microsoft.com/fwlink/p/?LinkId=257033](http://go.microsoft.com/fwlink/p/?LinkId=257033) se proporcionan también los pasos para habilitar IIS en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="14182-136">[http://go.microsoft.com/fwlink/p/?LinkId=257033](http://go.microsoft.com/fwlink/p/?LinkId=257033) also lists the steps to enable IIS on Windows 7.</span></span>  
  
#### <a name="install-iis-80-on-windows-8"></a><span data-ttu-id="14182-137">Instalar IIS 8.0 en Windows 8</span><span class="sxs-lookup"><span data-stu-id="14182-137">Install IIS 8.0 on Windows 8</span></span>  
  
1.  <span data-ttu-id="14182-138">Presione la tecla Windows del teclado.</span><span class="sxs-lookup"><span data-stu-id="14182-138">Select the Windows button on your keyboard.</span></span> <span data-ttu-id="14182-139">Escriba **Programas y características** y seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="14182-139">Type **Programs and Features** and select**Settings**.</span></span> <span data-ttu-id="14182-140">En la ventana Resultados, seleccione **Programas y características**.</span><span class="sxs-lookup"><span data-stu-id="14182-140">In the Results window, select **Programs and Features**.</span></span>  
  
2.  <span data-ttu-id="14182-141">Seleccione **Activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="14182-141">Select **Turn Windows features on or off**.</span></span>  
  
3.  <span data-ttu-id="14182-142">Seleccione **Internet Information Services** y expanda **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="14182-142">Select **Internet Information Services** and expand **Internet Information Services**.</span></span> <span data-ttu-id="14182-143">Además de las opciones predeterminadas, seleccione las siguientes:</span><span class="sxs-lookup"><span data-stu-id="14182-143">In addition to the default checked options, also select the following:</span></span>  
  
    -   <span data-ttu-id="14182-144">**Herramientas de administración web**: Seleccione también:</span><span class="sxs-lookup"><span data-stu-id="14182-144">**Web Management Tools**: Also check:</span></span>  
  
        -   <span data-ttu-id="14182-145">Compatibilidad con la administración de IIS 6:</span><span class="sxs-lookup"><span data-stu-id="14182-145">IIS 6 Management Compatibility:</span></span>  
  
            -   <span data-ttu-id="14182-146">Consola de administración de IIS 6</span><span class="sxs-lookup"><span data-stu-id="14182-146">IIS 6 Management Console</span></span>  
  
            -   <span data-ttu-id="14182-147">Compatibilidad con la configuración de IIS 6 y metabase de IIS</span><span class="sxs-lookup"><span data-stu-id="14182-147">IIS Metabase and IIS 6 configuration compatibility</span></span>  
  
        -   <span data-ttu-id="14182-148">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="14182-148">IIS Management Console</span></span>  
  
    -   <span data-ttu-id="14182-149">**Servicios World Wide Web**: expanda **Seguridad** y seleccione también:</span><span class="sxs-lookup"><span data-stu-id="14182-149">**World Wide Web Services**: Expand **Security** and also check:</span></span>  
  
        -   <span data-ttu-id="14182-150">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="14182-150">Basic Authentication</span></span>  
  
        -   <span data-ttu-id="14182-151">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="14182-151">Windows Authentication</span></span>  
  
4.  <span data-ttu-id="14182-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="14182-152">Click **OK**.</span></span> <span data-ttu-id="14182-153">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="14182-153">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="14182-154">En [http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) se proporcionan también los pasos para habilitar IIS en Windows 8.</span><span class="sxs-lookup"><span data-stu-id="14182-154">[http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) also lists the steps to enable IIS on Windows 8.</span></span>  
  
#### <a name="install-iis-80-on-windows-server-2012"></a><span data-ttu-id="14182-155">Instalar IIS 8.0 en Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="14182-155">Install IIS 8.0 on Windows Server 2012</span></span>  
  
1.  <span data-ttu-id="14182-156">Abra **Administrador del servidor** y haga clic en **Panel** en el panel de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="14182-156">Open **Server Manager** and click **Dashboard** in the left pane.</span></span>  
  
2.  <span data-ttu-id="14182-157">Haga clic en **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="14182-157">Click **Add roles and features**.</span></span> <span data-ttu-id="14182-158">También se puede abrir **Agregar roles y características** desde el menú **Administrar** de la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="14182-158">**Add Roles and Features** can also be opened from the **Manage** menu in the top right-hand corner.</span></span>  
  
3.  <span data-ttu-id="14182-159">En la ventana **Antes de comenzar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="14182-159">On the **Before You Begin** window, click **Next**.</span></span>  
  
4.  <span data-ttu-id="14182-160">En la ventana **Tipo de instalación**, haga clic en **Instalación basada en características o en roles** y, después, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="14182-160">On the **Installation Type** window, click **Role-based or feature-based installation**, and click **Next**.</span></span>  
  
5.  <span data-ttu-id="14182-161">En la ventana **Selección de servidor**, haga clic en **Seleccionar un servidor del grupo de servidores**, elija el servidor deseado y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="14182-161">On the **Server Selection** window, click **Select a server from the server pool**, click the desired server, and click **Next**.</span></span>  
  
     <span data-ttu-id="14182-162">En la ventana **Selección del servidor** se muestra una lista de los servidores que se han agregado con la opción **Agregar servidor** en el **Administrador del servidor**.</span><span class="sxs-lookup"><span data-stu-id="14182-162">The **Server Selection** window lists the servers that have been added using **Add Server** in **Server Manager**.</span></span> <span data-ttu-id="14182-163">De forma predeterminada, se selecciona el servidor local.</span><span class="sxs-lookup"><span data-stu-id="14182-163">By default, it selects the local server.</span></span> <span data-ttu-id="14182-164">En [Adición de servidores al Administrador del servidor](http://go.microsoft.com/fwlink/p/?LinkID=241353) se proporcionan los pasos para usar la opción **Agregar servidor** en [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-164">[Add Servers to Server Manager](http://go.microsoft.com/fwlink/p/?LinkID=241353) lists the steps to use **Add Server** on [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)].</span></span>  
  
6.  <span data-ttu-id="14182-165">En la ventana **Roles de servidor**, haga clic en **Servidor web (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="14182-165">On the **Server Roles** window, click **Web Server (IIS)**.</span></span> <span data-ttu-id="14182-166">Si se le pide, haga clic en **Agregar características** y, después, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="14182-166">If prompted, click **Add Features**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="14182-167">En la ventana **Características**, deje habilitadas las opciones predeterminadas y considere también lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="14182-167">On the **Features** window, keep the default options enabled and also consider the following:</span></span>  
  
     <span data-ttu-id="14182-168">**Características de .NET Framework 3.5**: [!INCLUDE[dotnet45](../includes/dotnet45-md.md)] y [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] se pueden usar para desarrollar aplicaciones .NET con [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-168">**.Net Framework 3.5 Features**: [!INCLUDE[dotnet45](../includes/dotnet45-md.md)] and [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] can be used to develop .Net applications involving the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="14182-169">Normalmente, **Características de [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]** está ya instalado.</span><span class="sxs-lookup"><span data-stu-id="14182-169">Typically, **[!INCLUDE[dotnet45](../includes/dotnet45-md.md)] Features** is already installed.</span></span> <span data-ttu-id="14182-170">Si va a usar [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] para crear aplicaciones en este equipo, puede instalar también **Características de .NET Framework 3.5**.</span><span class="sxs-lookup"><span data-stu-id="14182-170">If you will use [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] to create applications on this computer, then **.Net Framework 3.5 Features** can also be installed.</span></span>  
  
     <span data-ttu-id="14182-171">**Message Queue Server**: si usa el adaptador MSMQ, puede crear un almacén MSMQ local. Para ello, seleccione **Message Queue Server**.</span><span class="sxs-lookup"><span data-stu-id="14182-171">**Message Queuing**: If you are using the MSMQ adapter, you can create a local MSMQ store by checking **Message Queuing**.</span></span>  
  
     <span data-ttu-id="14182-172">**Servidor SMTP**: si usa el adaptador SMTP, puede crear un servidor SMTP local. Para ello, seleccione **Servidor SMTP**.</span><span class="sxs-lookup"><span data-stu-id="14182-172">**SMTP Server**: If you are using the SMTP adapter, you can create a local SMTP Server by checking **SMTP Server**.</span></span>  
  
     <span data-ttu-id="14182-173">**Windows Identity Foundation 3.5**: el adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] requiere Windows Identity Foundation (WIF) cuando se usa la opción de instalación CSOM.</span><span class="sxs-lookup"><span data-stu-id="14182-173">**Windows Identity Foundation 3.5**: Windows Identity Foundation (WIF) is required by the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adapter when using the CSOM installation option.</span></span> <span data-ttu-id="14182-174">En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se describe la opción de instalación CSOM para el adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-174">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the CSOM installation option for the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adapter.</span></span>  
  
     <span data-ttu-id="14182-175">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="14182-175">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="14182-176">En la ventana **Rol de servidor web (IIS)**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="14182-176">On the **Web Server Role (IIS)** window, click **Next**.</span></span>  
  
9. <span data-ttu-id="14182-177">En la ventana **Servicios de rol** (en **Rol de servidor web (IIS)**), haga clic en las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="14182-177">On the **Role Services** window (under **Web Server Role (IIS)**), click the following options:</span></span>  
  
     <span data-ttu-id="14182-178">**Seguridad**: además de las opciones predeterminadas, haga clic en:</span><span class="sxs-lookup"><span data-stu-id="14182-178">**Security**: In addition to the default options, also click:</span></span>  
  
    -   <span data-ttu-id="14182-179">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="14182-179">Basic Authentication</span></span>  
  
    -   <span data-ttu-id="14182-180">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="14182-180">Windows Authentication</span></span>  
  
     <span data-ttu-id="14182-181">**Desarrollo de aplicaciones**: las opciones predeterminadas son suficientes para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-181">**Application Development**: The default options are sufficient for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="14182-182">Si hospeda otras aplicaciones basadas en IIS en este equipo, seleccione los roles necesarios.</span><span class="sxs-lookup"><span data-stu-id="14182-182">If you host other IIS-based applications on this computer, check the needed roles.</span></span>  
  
     <span data-ttu-id="14182-183">**Herramientas de administración**: además de las opciones predeterminadas, haga clic en:</span><span class="sxs-lookup"><span data-stu-id="14182-183">**Management Tools**: In addition to the default options, also click:</span></span>  
  
    -   <span data-ttu-id="14182-184">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="14182-184">IIS Management Console</span></span>  
  
    -   <span data-ttu-id="14182-185">Compatibilidad con la administración de IIS 6:</span><span class="sxs-lookup"><span data-stu-id="14182-185">IIS 6 Management Compatibility:</span></span>  
  
        -   <span data-ttu-id="14182-186">Compatibilidad con la metabase de IIS 6</span><span class="sxs-lookup"><span data-stu-id="14182-186">IIS 6 Metabase Compatibility</span></span>  
  
        -   <span data-ttu-id="14182-187">Consola de administración de IIS 6</span><span class="sxs-lookup"><span data-stu-id="14182-187">IIS 6 Management Console</span></span>  
  
     <span data-ttu-id="14182-188">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="14182-188">Click **Next**.</span></span>  
  
10. <span data-ttu-id="14182-189">En la ventana **Confirmación**, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="14182-189">On the **Confirmation** window, click **Install**.</span></span> <span data-ttu-id="14182-190">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="14182-190">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="14182-191">En [http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) se proporcionan también los pasos para habilitar IIS en [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-191">[http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) also lists the steps to enable IIS on [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)].</span></span>  
  
##  <a name="BKMK_XLS"></a> <span data-ttu-id="14182-192">Instalar Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="14182-192">Install Microsoft Office Excel</span></span>  
  
1.  <span data-ttu-id="14182-193">Ejecute el programa de instalación de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="14182-193">Run the Microsoft Office setup.</span></span>  
  
2.  <span data-ttu-id="14182-194">Cuando llegue a la pantalla **Tipo de instalación**, seleccione **Instalación personalizada** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="14182-194">When you reach the **Type of Installation** screen, select **Custom Install**, and then select **Next**.</span></span>  
  
3.  <span data-ttu-id="14182-195">En la pantalla **Instalación personalizada**, seleccione **Excel** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="14182-195">On the **Custom Setup** screen, select **Excel**, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="14182-196">Elija **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="14182-196">Select **Install**.</span></span>  
  
5.  <span data-ttu-id="14182-197">En **Instalación finalizada**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="14182-197">In **Setup Completed**, select **Finish**.</span></span>  
  
 <span data-ttu-id="14182-198">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-198">**Additional**</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="14182-199"> solo es compatible con la versión de 32 bits de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="14182-199"> supports only 32-bit version of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="14182-200">Microsoft Office Excel es necesario para la Supervisión de la actividad económica (BAM) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-200">Microsoft Office Excel is required by Business Activity Monitoring (BAM) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="14182-201">El libro de BAM de Office Excel se usa para definir los procesos empresariales que desee supervisar.</span><span class="sxs-lookup"><span data-stu-id="14182-201">The BAM Office Excel Workbook defines the business processes you want to monitor.</span></span> <span data-ttu-id="14182-202">El libro de Excel de BAM también se usa para definir el modo en que los usuarios empresariales ven los datos que BAM recopila.</span><span class="sxs-lookup"><span data-stu-id="14182-202">You also use the BAM Excel Workbook to define the way business users see the data collected by BAM.</span></span>  
  
-   <span data-ttu-id="14182-203">Para cargar correctamente BAM.xla en Excel, instale la opción **Visual Basic para Aplicaciones** de **Características compartidas de Office**.</span><span class="sxs-lookup"><span data-stu-id="14182-203">To successfully load BAM.xla into Excel, install **Visual Basic for Applications** under **Office Shared Features**.</span></span> <span data-ttu-id="14182-204">De lo contrario, puede obtener el error "Este libro ha perdido su proyecto de VBA, los controles de ActiveX y todas las demás características relacionadas con la programabilidad".</span><span class="sxs-lookup"><span data-stu-id="14182-204">Otherwise, you may get error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span>  
  
##  <a name="BKMK_VS"></a> <span data-ttu-id="14182-205">Instalar Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14182-205">Install Visual Studio</span></span>  
  
1.  <span data-ttu-id="14182-206">Ejecute el programa de instalación de Visual Studio como administrador.</span><span class="sxs-lookup"><span data-stu-id="14182-206">Run the Visual Studio setup as Administrator.</span></span>  
  
2.  <span data-ttu-id="14182-207">Acepte el contrato de licencia y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="14182-207">Accept the license agreement and click **Next**.</span></span>  
  
3.  <span data-ttu-id="14182-208">En **Características opcionales para instalar**, seleccione las opciones que necesite y haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="14182-208">In **Optional features to install**, select the options you need and then select **Install**.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="14182-209"> no necesita ninguna característica opcional.</span><span class="sxs-lookup"><span data-stu-id="14182-209"> does not require any of the optional features.</span></span>  
  
4.  <span data-ttu-id="14182-210">En la página **Finalizar**, cierre la ventana y haga clic en **Iniciar** para abrir Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="14182-210">On the **Finish** page, close the window or click **Launch** to open Visual Studio.</span></span>  
  
 <span data-ttu-id="14182-211">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-211">**Additional**</span></span>  
  
-   <span data-ttu-id="14182-212">Si instala Visual Studio antes de instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y después actualiza a Visual Studio Team Explorer, puede que sea necesario reparar la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde la opción **Panel de control** / **Programas**.</span><span class="sxs-lookup"><span data-stu-id="14182-212">If you install Visual Studio before installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then upgrade to Visual Studio Team Explorer, you may need to repair your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation from the **Control Panel** / **Programs** option.</span></span>  
  
-   <span data-ttu-id="14182-213">Visual Studio instala automáticamente Microsoft SQL Server Express, que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no usa.</span><span class="sxs-lookup"><span data-stu-id="14182-213">Visual Studio automatically installs Microsoft SQL Server Express; which is not used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="14182-214">Como procedimiento recomendado, desinstale Microsoft SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="14182-214">As a best practice, uninstall Microsoft SQL Server Express.</span></span>  
  
-   <span data-ttu-id="14182-215">Las herramientas de programadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] están basadas en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="14182-215">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development tools are based on Visual Studio.</span></span> <span data-ttu-id="14182-216">Como mínimo, debe instalar el componente Microsoft Visual C#® .NET de Visual Studio antes de instalar el **SDK y herramientas de desarrollo** de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-216">At a minimum, you must install the Microsoft Visual C#® .NET component of Visual Studio before you install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**Developer Tools and SDK**.</span></span>  
  
-   <span data-ttu-id="14182-217">Visual Studio *no* es necesario si va a instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un equipo de producción (solo en tiempo de ejecución), en el que no es necesario ningún trabajo de desarrollo o depuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="14182-217">Visual Studio is *not* required if you are installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a production computer (runtime only), on which no application development or debugging is required.</span></span>  
  
-   <span data-ttu-id="14182-218">El runtime de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] requiere [!INCLUDE[dotnet45](../includes/dotnet45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-218">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime requires [!INCLUDE[dotnet45](../includes/dotnet45-md.md)].</span></span> <span data-ttu-id="14182-219">Si se instala el adaptador o el interceptor de Windows Communication Foundation (WCF), es necesario .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="14182-219">The .NET Framework 3.0 is required if the Windows Communication Foundation (WCF) adapter or WCF Interceptor is installed.</span></span>  
  
##  <a name="BKMK_SQL"></a> <span data-ttu-id="14182-220">Instalar SQL Server</span><span class="sxs-lookup"><span data-stu-id="14182-220">Install SQL Server</span></span>  
 <span data-ttu-id="14182-221">Instalar [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="14182-221">Install [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span></span>  
  
 <span data-ttu-id="14182-222">Instalar [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="14182-222">Install [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span></span>  
  
 <span data-ttu-id="14182-223">Instalar [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span><span class="sxs-lookup"><span data-stu-id="14182-223">Install [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span></span>  
  
 <span data-ttu-id="14182-224">Cuando instale [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], seleccione las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="14182-224">When you install [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], select the following features:</span></span>  
  
-   <span data-ttu-id="14182-225">Servicios de Motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="14182-225">Database Engine Services</span></span>  
  
    -   <span data-ttu-id="14182-226">Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="14182-226">SQL Server Replication</span></span>  
  
    -   <span data-ttu-id="14182-227">Búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="14182-227">Full-Text Search</span></span>  
  
-   <span data-ttu-id="14182-228">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="14182-228">Analysis Services</span></span>  
  
-   <span data-ttu-id="14182-229">Reporting Services</span><span class="sxs-lookup"><span data-stu-id="14182-229">Reporting Services</span></span>  
  
-   <span data-ttu-id="14182-230">Características compartidas</span><span class="sxs-lookup"><span data-stu-id="14182-230">Shared Features</span></span>  
  
    -   <span data-ttu-id="14182-231">SQL Server Data Tools (SQL Server 2014/SQL Server 2012) o Business Intelligence Development Studio (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="14182-231">SQL Server Data Tools (SQL Server 2014 / SQL Server 2012) or Business Intelligence Development Studio (SQL Server 2008 R2)</span></span>  
  
         [<span data-ttu-id="14182-232">Descargar las herramientas de datos SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="14182-232">Download SQL Server 2014 Data Tools</span></span>](http://www.microsoft.com/download/details.aspx?id=42313)  
  
    -   <span data-ttu-id="14182-233">Conectividad con las herramientas de cliente</span><span class="sxs-lookup"><span data-stu-id="14182-233">Client Tools Connectivity</span></span>  
  
    -   <span data-ttu-id="14182-234">Integration Services</span><span class="sxs-lookup"><span data-stu-id="14182-234">Integration Services</span></span>  
  
    -   <span data-ttu-id="14182-235">Herramientas de administración: básicas</span><span class="sxs-lookup"><span data-stu-id="14182-235">Management Tools - Basic</span></span>  
  
        -   <span data-ttu-id="14182-236">Herramientas de administración - Completa</span><span class="sxs-lookup"><span data-stu-id="14182-236">Management Tools - Complete</span></span>  
  
 <span data-ttu-id="14182-237">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-237">**Additional**</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="14182-238"> admite todas las intercalaciones de SQL Server, tanto si distinguen mayúsculas y minúsculas como si no, excepto las intercalaciones binarias.</span><span class="sxs-lookup"><span data-stu-id="14182-238"> supports all case-sensitive and case-insensitive SQL Server collations except for binary collations.</span></span> <span data-ttu-id="14182-239">No se admiten intercalaciones binarias.</span><span class="sxs-lookup"><span data-stu-id="14182-239">Binary collations are not supported.</span></span>  
  
-   <span data-ttu-id="14182-240">Para un rendimiento óptimo, Microsoft recomienda usar Enterprise Edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="14182-240">For optimal performance, Microsoft recommends using the Enterprise Edition of SQL Server.</span></span> <span data-ttu-id="14182-241">Consulte [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx) (Características compatibles con las ediciones de SQL Server 2008 R2), [Características compatibles con las ediciones de SQL Server 2012](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx) o [Características compatibles con las ediciones de SQL Server 2014](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="14182-241">See [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx), [SQL Server 2012 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx), or [SQL Server 2014 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).</span></span>  
  
-   <span data-ttu-id="14182-242">Se admiten y deben instalarse los Service Packs y las actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="14182-242">Service packs and Windows Updates are supported and should be installed.</span></span>  
  
-   <span data-ttu-id="14182-243">Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] están en equipos diferentes, el Coordinador de transacciones distribuidas (MS DTC) controla las transacciones entre los equipos.</span><span class="sxs-lookup"><span data-stu-id="14182-243">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are on separate computers, Distributed Transaction Coordinator (MS DTC) handles the transactions between the computers.</span></span> <span data-ttu-id="14182-244">La característica AlwaysOn de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] no admite transacciones MSDTC.</span><span class="sxs-lookup"><span data-stu-id="14182-244">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn feature does not support MSDTC transactions.</span></span> <span data-ttu-id="14182-245">No se admite la característica AlwaysOn de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-245">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn feature is not supported.</span></span>  
  
##  <a name="BKMK_MQSeries"></a> <span data-ttu-id="14182-246">Instalar los requisitos previos de MQSeries</span><span class="sxs-lookup"><span data-stu-id="14182-246">Install MQSeries Prerequisites</span></span>  
 <span data-ttu-id="14182-247">**Adaptador de MQSeries**: se instala de forma automática con la instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="14182-247">**MQSeries adapter**: Automatically installed with the BizTalk Server installation.</span></span>  
  
 <span data-ttu-id="14182-248">**Adaptador de MQSeries Client (MQSC)**:</span><span class="sxs-lookup"><span data-stu-id="14182-248">**MQSeries Client (MQSC) adapter**:</span></span>  
  
1.  <span data-ttu-id="14182-249">Ejecute la instalación de Host Integration Server (HIS).</span><span class="sxs-lookup"><span data-stu-id="14182-249">Run the Host Integration Server (HIS) installation</span></span>  
  
2.  <span data-ttu-id="14182-250">En Instalación de componentes, expanda **BizTalk Adapters** (Adaptadores de BizTalk).</span><span class="sxs-lookup"><span data-stu-id="14182-250">In component installation, expand **BizTalk Adapters**.</span></span>  
  
3.  <span data-ttu-id="14182-251">Seleccione **BizTalk Adapter for WebSphere MQ (Client-Based)** (Adaptador de BizTalk para WebSphere MQ (basado en cliente)).</span><span class="sxs-lookup"><span data-stu-id="14182-251">Select **BizTalk Adapter for WebSphere MQ (Client-Based)**.</span></span>  
  
 <span data-ttu-id="14182-252">**Versiones de IBM WebSphere MQ admitidas**:</span><span class="sxs-lookup"><span data-stu-id="14182-252">**Supported IBM WebSphere MQ versions**:</span></span>  
  
-   <span data-ttu-id="14182-253">IBM WebSphere MQ 6.0.2.12 y posterior</span><span class="sxs-lookup"><span data-stu-id="14182-253">IBM WebSphere MQ 6.0.2.12 and later</span></span>  
  
-   <span data-ttu-id="14182-254">IBM WebSphere MQ 7.0.1.9 y posterior</span><span class="sxs-lookup"><span data-stu-id="14182-254">IBM WebSphere MQ 7.0.1.9 and later</span></span>  
  
-   <span data-ttu-id="14182-255">IBM WebSphere MQ 7.1.0.5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="14182-255">IBM WebSphere MQ 7.1.0.5 and later</span></span>  
  
-   <span data-ttu-id="14182-256">IBM WebSphere MQ 7.5.0.3 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="14182-256">IBM WebSphere MQ 7.5.0.3 and later</span></span>  
  
-   <span data-ttu-id="14182-257">IBM WebSphere MQ 8 (limitado al tiempo de ejecución, sin API de administración)</span><span class="sxs-lookup"><span data-stu-id="14182-257">IBM WebSphere MQ 8 (limited to runtime; no administration APIs)</span></span>  
  
     <span data-ttu-id="14182-258">Se incluye compatibilidad con la versión 8 de MQ con [Host Integration Server CU3](https://support.microsoft.com/kb/3019572).</span><span class="sxs-lookup"><span data-stu-id="14182-258">MQ version 8 support is included with [Host Integration Server CU3](https://support.microsoft.com/kb/3019572).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14182-259">Si no aparece una versión específica de WebSphere MQ, como MQ 5.x, entonces no es compatible con esta versión [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-259">If a specific WebSphere MQ version is not listed, like MQ 5.x, then it is not supported with this [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] version.</span></span>  
  
 <span data-ttu-id="14182-260">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-260">**Additional**</span></span>  
  
-   <span data-ttu-id="14182-261">Como práctica recomendada, instale siempre el paquete de corrección de WebSphere MQ más reciente.</span><span class="sxs-lookup"><span data-stu-id="14182-261">As a best practice, always install the latest WebSphere MQ fix pack.</span></span> <span data-ttu-id="14182-262">Consulte [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).</span><span class="sxs-lookup"><span data-stu-id="14182-262">See [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).</span></span>  
  
-   <span data-ttu-id="14182-263">Si IBM WebSphere MQ está instalado en un equipo que no tiene Windows, instale la **aplicación MQSAgent COM+** (MQSConfigWiz.exe) y **MQSeries Server para Windows** en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="14182-263">If IBM WebSphere MQ is installed on a non-Windows computer, install the **MQSAgent COM+ application** (MQSConfigWiz.exe) and **MQSeries Server for Windows** on the same computer.</span></span> <span data-ttu-id="14182-264">Si IBM WebSphere MQ está instalado en un equipo con Windows, no se usan la **aplicación MQSAgent COM+** y **MQSeries Server para Windows** y, por tanto, no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="14182-264">If IBM WebSphere MQ is installed on a Windows computer, then the **MQSAgent COM+ application** and **MQSeries Server for Windows** program are not used or needed.</span></span>  
  
     <span data-ttu-id="14182-265">**MQSConfigWiz.exe** se incluye en los archivos de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-265">**MQSConfigWiz.exe** is included in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation files.</span></span>  
  
     <span data-ttu-id="14182-266">**MQSeries Server para Windows** no es un programa de Microsoft y debe obtenerse con el programa IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="14182-266">**MQSeries Server for Windows** is not a Microsoft program and must be obtained with your IBM WebSphere MQ program.</span></span>  
  
-   <span data-ttu-id="14182-267">En [Adaptador de MQSeries](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) se proporciona más información sobre este adaptador, incluida la configuración de los diferentes componentes.</span><span class="sxs-lookup"><span data-stu-id="14182-267">[MQSeries Adapter](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) provides more information on the MQSeries adapter, including configuring the different components.</span></span> <span data-ttu-id="14182-268">En [BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) (BizTalk Server: adaptadores MQSeries y MQSeries Client (MQSC)) se proporciona más información sobre estos adaptadores.</span><span class="sxs-lookup"><span data-stu-id="14182-268">[BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) provides additional details on the MQSeries and MQSC adapters.</span></span>  
  
-   <span data-ttu-id="14182-269">IBM WebSphere no es un producto de Microsoft y, por tanto, Microsoft no ofrece soporte técnico para este producto.</span><span class="sxs-lookup"><span data-stu-id="14182-269">IBM WebSphere is not a Microsoft product and is not supported by Microsoft.</span></span> <span data-ttu-id="14182-270">Microsoft no garantiza la idoneidad de este programa.</span><span class="sxs-lookup"><span data-stu-id="14182-270">Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="14182-271">Para obtener más información acerca de IBM WebSphere MQ, incluidas las instrucciones de descarga, vea www.ibm.com.</span><span class="sxs-lookup"><span data-stu-id="14182-271">For more information about IBM WebSphere MQ, including download instructions, see www.ibm.com.</span></span>  
  
##  <a name="BKMK_BAMAlerts"></a> <span data-ttu-id="14182-272">Alertas de BAM</span><span class="sxs-lookup"><span data-stu-id="14182-272">BAM Alerts</span></span>  
 <span data-ttu-id="14182-273">Las alertas de BAM con [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)] o [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] utilizan Correo electrónico de base de datos en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-273">BAM Alerts with [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)] or [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] uses Database Mail in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="14182-274">Las alertas de BAM con [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] usan SQL Notification Services.</span><span class="sxs-lookup"><span data-stu-id="14182-274">BAM Alerts with [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] uses SQL Notification Services.</span></span> <span data-ttu-id="14182-275">Antes de instalar o configurar alertas de BAM, debe configurar Notification Services o Correo electrónico de base de datos en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-275">Before installing or configuring BAM Alerts, you must configure the Notification Services or Database Mail in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
###  <a name="BKMK_DBMail"></a> <span data-ttu-id="14182-276">Alertas de BAM con SQL Server 2012/2014</span><span class="sxs-lookup"><span data-stu-id="14182-276">BAM Alerts using SQL Server 2012/2014</span></span>  
 <span data-ttu-id="14182-277">Configure [Correo electrónico de base de datos de SQL Server 2012](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="14182-277">Configure [SQL Server 2012 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).</span></span>  
  
 <span data-ttu-id="14182-278">Configure [Correo electrónico de base de datos de SQL Server 2014](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="14182-278">Configure [SQL Server 2014 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="14182-279">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-279">**Additional**</span></span>  
  
-   <span data-ttu-id="14182-280">Correo electrónico de base de datos usa un servidor SMTP para enviar las alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="14182-280">Database Mail uses an SMTP server to send the BAM Alerts.</span></span> <span data-ttu-id="14182-281">El servidor SMTP se puede instalar en modo local en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] u otro servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="14182-281">SMTP Server can be installed locally on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or on another IIS server.</span></span> <span data-ttu-id="14182-282">En [Apéndice D: Crear el servidor SMTP](../install-and-config-guides/appendix-d-create-the-smtp-server.md) se enumeran los pasos necesarios para instalar y configurar un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="14182-282">[Appendix D: Create the SMTP Server](../install-and-config-guides/appendix-d-create-the-smtp-server.md) lists the steps to install and configure a SMTP Server.</span></span>  
  
###  <a name="BKMK_SSNS"></a> <span data-ttu-id="14182-283">Alertas de BAM con SQL Server 2008 R2: instalar SQL Server 2005 Notification Services</span><span class="sxs-lookup"><span data-stu-id="14182-283">BAM Alerts using SQL Server 2008 R2 – Install SQL Server 2005 Notification Services</span></span>  
  
1.  <span data-ttu-id="14182-284">Vaya a [Feature Pack para Microsoft SQL Server 2005 SP4](http://go.microsoft.com/fwlink/p/?LinkId=286285).</span><span class="sxs-lookup"><span data-stu-id="14182-284">Go to [Feature Pack for Microsoft SQL Server 2005 SP4](http://go.microsoft.com/fwlink/p/?LinkId=286285).</span></span>  
  
2.  <span data-ttu-id="14182-285">Descargue e instale el paquete de plataforma adecuado para los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="14182-285">Download and install the appropriate platform package for the following components:</span></span>  
  
     <span data-ttu-id="14182-286">**Cliente nativo de Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="14182-286">**Microsoft SQL Server Native Client**</span></span>  
  
    -   <span data-ttu-id="14182-287">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi" del paquete X86 (sqlncli.msi)</span><span class="sxs-lookup"><span data-stu-id="14182-287">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi" X86 Package (sqlncli.msi)</span></span>  
  
    -   <span data-ttu-id="14182-288">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi" del paquete X64 (sqlncli_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="14182-288">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi" X64 Package (sqlncli_x64.msi)</span></span>  
  
     <span data-ttu-id="14182-289">**Colección de objetos de administración de Microsoft SQL Server 2005**</span><span class="sxs-lookup"><span data-stu-id="14182-289">**Microsoft SQL Server 2005 Management Objects Collection**</span></span>  
  
    -   <span data-ttu-id="14182-290">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi" del paquete X86 (SQLServer2005_XMO.msi)</span><span class="sxs-lookup"><span data-stu-id="14182-290">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi" X86 Package (SQLServer2005_XMO.msi)</span></span>  
  
    -   <span data-ttu-id="14182-291">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi" del paquete X64 (SQLServer2005_XMO_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="14182-291">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi" X64 Package (SQLServer2005_XMO_x64.msi)</span></span>  
  
     <span data-ttu-id="14182-292">**Componentes de cliente de Microsoft SQL Server 2005 Notification Services**</span><span class="sxs-lookup"><span data-stu-id="14182-292">**Microsoft SQL Server 2005 Notification Services Client Components**</span></span>  
  
    -   <span data-ttu-id="14182-293">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi" del paquete X86 (SQLServer2005_NS.msi)</span><span class="sxs-lookup"><span data-stu-id="14182-293">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi" X86 Package (SQLServer2005_NS.msi)</span></span>  
  
    -   <span data-ttu-id="14182-294">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi" del paquete X64 (SQLServer2005_NS_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="14182-294">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi" X64 Package (SQLServer2005_NS_x64.msi)</span></span>  
  
 <span data-ttu-id="14182-295">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-295">**Additional**</span></span>  
  
-   <span data-ttu-id="14182-296">No es necesario configurar SQL Notification Services, solo instalarlo en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-296">SQL Notification Services does not need to be configured; only installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##  <a name="BKMK_WIF"></a> <span data-ttu-id="14182-297">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="14182-297">Windows Identity Foundation</span></span>  
  
|||  
|-|-|  
|[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]<span data-ttu-id="14182-298"> 8.1, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] y [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2</span><span class="sxs-lookup"><span data-stu-id="14182-298"> 8.1, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], and [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2</span></span>|<span data-ttu-id="14182-299">Windows Identity Foundation se incluye con el sistema operativo como característica en **Activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="14182-299">Windows Identity Foundation is included with the operating system as a Feature in **Turn Windows features on or off**.</span></span>|  
|[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]<span data-ttu-id="14182-300"> SP1</span><span class="sxs-lookup"><span data-stu-id="14182-300"> SP1</span></span>|<span data-ttu-id="14182-301">Descarga disponible en [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HIPERVÍNCULO "http://www.microsoft.com/download/details.aspx?id=17331".</span><span class="sxs-lookup"><span data-stu-id="14182-301">Download available at [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK "http://www.microsoft.com/download/details.aspx?id=17331" .</span></span>|  
  
 <span data-ttu-id="14182-302">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-302">**Additional**</span></span>  
  
-   <span data-ttu-id="14182-303">SharePoint Online o el adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] requieren Windows Identity Foundation (WIF) cuando se utilizan con el modelo de objetos de cliente (CSOM) de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-303">Windows Identity Foundation (WIF) is required for the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter or SharePoint Online when used with [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Client Side Object Model (CSOM).</span></span> <span data-ttu-id="14182-304">Concretamente:</span><span class="sxs-lookup"><span data-stu-id="14182-304">Specifically:</span></span>  
  
    |<span data-ttu-id="14182-305">Opción de instalación</span><span class="sxs-lookup"><span data-stu-id="14182-305">Installation Option</span></span>|<span data-ttu-id="14182-306">WIF requerido</span><span class="sxs-lookup"><span data-stu-id="14182-306">WIF Required</span></span>|  
    |-------------------------|------------------|  
    |<span data-ttu-id="14182-307">Adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] con CSOM</span><span class="sxs-lookup"><span data-stu-id="14182-307">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter with CSOM</span></span>|<span data-ttu-id="14182-308">Sí</span><span class="sxs-lookup"><span data-stu-id="14182-308">Yes</span></span>|  
    |<span data-ttu-id="14182-309">SharePoint Online con CSOM</span><span class="sxs-lookup"><span data-stu-id="14182-309">SharePoint Online with CSOM</span></span>|<span data-ttu-id="14182-310">Sí</span><span class="sxs-lookup"><span data-stu-id="14182-310">Yes</span></span>|  
    |<span data-ttu-id="14182-311">Servicio web del adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="14182-311">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter Web Service (deprecated)</span></span>|<span data-ttu-id="14182-312">No</span><span class="sxs-lookup"><span data-stu-id="14182-312">No</span></span>|  
    |<span data-ttu-id="14182-313">Sin SharePoint</span><span class="sxs-lookup"><span data-stu-id="14182-313">No SharePoint</span></span>|<span data-ttu-id="14182-314">No</span><span class="sxs-lookup"><span data-stu-id="14182-314">No</span></span>|  
  
-   <span data-ttu-id="14182-315">En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se proporciona información específica sobre las opciones de instalación de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-315">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides specific information on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] installation options.</span></span>  
  
##  <a name="BKMK_WSS"></a> <span data-ttu-id="14182-316">Instalar y configurar Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="14182-316">Install and Configure Microsoft SharePoint</span></span>  
 <span data-ttu-id="14182-317">Instalar [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span><span class="sxs-lookup"><span data-stu-id="14182-317">Install [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span></span>  
  
 <span data-ttu-id="14182-318">Instalar el [servicio SharePoint Online](http://technet.microsoft.com/library/jj819267.aspx)</span><span class="sxs-lookup"><span data-stu-id="14182-318">Install [SharePoint Online Service](http://technet.microsoft.com/library/jj819267.aspx)</span></span>  
  
 <span data-ttu-id="14182-319">Instalar [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="14182-319">Install [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span></span>  
  
 <span data-ttu-id="14182-320">Instalar [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span><span class="sxs-lookup"><span data-stu-id="14182-320">Install [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span></span>  
  
 <span data-ttu-id="14182-321">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-321">**Additional**</span></span>  
  
-   <span data-ttu-id="14182-322">Si instala SharePoint, debe hacerlo antes de continuar con el resto de los requisitos previos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-322">If you are installing SharePoint, you must do so before continuing with the remaining [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] prerequisites.</span></span>  
  
-   <span data-ttu-id="14182-323">La instalación y configuración de SharePoint consiste en los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="14182-323">Installing and configuring SharePoint consists of the following procedures:</span></span>  
  
    -   <span data-ttu-id="14182-324">Instalar SharePoint</span><span class="sxs-lookup"><span data-stu-id="14182-324">Install SharePoint</span></span>  
  
    -   <span data-ttu-id="14182-325">Configurar SharePoint</span><span class="sxs-lookup"><span data-stu-id="14182-325">Configure SharePoint</span></span>  
  
    -   <span data-ttu-id="14182-326">Extender el sitio web predeterminado como un servidor virtual</span><span class="sxs-lookup"><span data-stu-id="14182-326">Extend the default Web site as a virtual server</span></span>  
  
-   <span data-ttu-id="14182-327">En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se describen las opciones de instalación del adaptador de SharePoint para BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="14182-327">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the SharePoint adapter installation options for BizTalk Server.</span></span>  
  
-   <span data-ttu-id="14182-328">Cuando se use el adaptador de SharePoint, se recomienda instalar la nueva opción CSOM en lugar del servicio web de SharePoint, que se describe en [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="14182-328">When using the SharePoint adapter, it is recommended to install the new CSOM option instead of the SharePoint Service Web Service; described at [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).</span></span>  
  
##  <a name="BKMK_SharedMem"></a> <span data-ttu-id="14182-329">Deshabilitar el protocolo de memoria compartida</span><span class="sxs-lookup"><span data-stu-id="14182-329">Disable the Shared Memory Protocol</span></span>  
  
1.  <span data-ttu-id="14182-330">Abra el **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="14182-330">Open **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="14182-331">En **Administrador de configuración de SQL Server**, expanda **Configuración de red de SQL Server** y seleccione **Protocolos de MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="14182-331">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, and then select **Protocols for MSSQLSERVER**.</span></span>  
  
3.  <span data-ttu-id="14182-332">Haga clic con el botón derecho en **Memoria compartida** y seleccione **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="14182-332">Right-click **Shared Memory**, and then select **Disable**.</span></span>  
  
4.  <span data-ttu-id="14182-333">Seleccione **Servicios de SQL Server**, haga clic con el botón derecho en **SQL Server (MSSQLSERVER)** y elija **Detener**.</span><span class="sxs-lookup"><span data-stu-id="14182-333">Select **SQL Server Services**, right-click **SQL Server (MSSQLSERVER)**, and then select **Stop**.</span></span> <span data-ttu-id="14182-334">Después de detener el servicio, haga clic de nuevo con el botón derecho en **SQL Server (MSSQLSERVER)** y elija **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="14182-334">After the service has stopped, right-click **SQL Server (MSSQLSERVER)** again, and then select **Start**.</span></span>  
  
5.  <span data-ttu-id="14182-335">Cierre el **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="14182-335">Close **SQL Server Configuration Manager**.</span></span>  
  
 <span data-ttu-id="14182-336">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-336">**Additional**</span></span>  
  
-   <span data-ttu-id="14182-337">En ciertas condiciones de sobrecarga (como cuando los clientes tienen acceso a SQL Server desde el mismo equipo), el protocolo de memoria compartida de SQL Server puede reducir el rendimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-337">Under certain stress conditions (such as clients accessing SQL Server from the same computer), the SQL Server Shared Memory protocol may lower [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance.</span></span> <span data-ttu-id="14182-338">Para resolver este comportamiento, puede deshabilitar el uso del protocolo de red de memoria compartida en la configuración de red de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="14182-338">You can resolve this behavior by disabling the Shared Memory network protocol in SQL Server Network Configuration.</span></span>  
  
-   <span data-ttu-id="14182-339">ReplaceThisText</span><span class="sxs-lookup"><span data-stu-id="14182-339">ReplaceThisText</span></span>  
  
##  <a name="BKMK_LocalAdmin"></a> <span data-ttu-id="14182-340">Unirse al grupo de administradores local</span><span class="sxs-lookup"><span data-stu-id="14182-340">Join the Local Administrators Group</span></span>  
 <span data-ttu-id="14182-341">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: [Windows Server 2012: How to Add an Account to a Local Administrator Group](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx) (Windows Server 2012: cómo agregar una cuenta a un grupo de administradores local)</span><span class="sxs-lookup"><span data-stu-id="14182-341">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : [Windows Server 2012: How to Add an Account to a Local Administrator Group](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span></span>  
  
 <span data-ttu-id="14182-342">**Windows 8.1**: para abrir Usuarios y grupos locales en Windows 8, pulse la tecla Windows del teclado y escriba **grupos**.</span><span class="sxs-lookup"><span data-stu-id="14182-342">**Windows 8.1**: To open Local Users and Groups on Windows 8, click the Windows button on the keyboard and type **groups**.</span></span> <span data-ttu-id="14182-343">En la ventana Buscar, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="14182-343">In the Search window, click **Settings**.</span></span> <span data-ttu-id="14182-344">En la ventana Resultados, haga clic en **Editar usuarios y grupos locales**.</span><span class="sxs-lookup"><span data-stu-id="14182-344">In the Results window, click **Edit local users and groups**.</span></span> <span data-ttu-id="14182-345">Haga clic en **Grupos** y después haga doble clic en Administradores para agregar una cuenta.</span><span class="sxs-lookup"><span data-stu-id="14182-345">Click **Groups** and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="14182-346">**Windows 7 SP1**: haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="14182-346">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="14182-347">En el cuadro de texto **Buscar**, escriba **Administración de equipos** y haga clic en él para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="14182-347">In the **Search** text box, type **Computer Management**, and click it to open.</span></span> <span data-ttu-id="14182-348">Expanda **Usuarios y grupos locales**, elija **Grupos** y haga doble clic en Administradores para agregar una cuenta.</span><span class="sxs-lookup"><span data-stu-id="14182-348">Expand **Local Users and Groups**, click **Groups**, and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="14182-349">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-349">**Additional**</span></span>  
  
-   <span data-ttu-id="14182-350">Debe ser miembro del grupo de administradores local para instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14182-350">You must be a member of the local Administrators group to install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##  <a name="BKMK_AppLog"></a> <span data-ttu-id="14182-351">Configurar el registro de eventos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="14182-351">Configure the Application Event Log</span></span>  
  
1.  <span data-ttu-id="14182-352">Abra el **Visor de eventos**:</span><span class="sxs-lookup"><span data-stu-id="14182-352">Open **Event Viewer**:</span></span>  
  
     <span data-ttu-id="14182-353">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: pulse la tecla Windows del teclado y escriba **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="14182-353">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="14182-354">En la ventana Resultados, haga clic en **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="14182-354">In the Results window, click **Event Viewer**.</span></span>  
  
     <span data-ttu-id="14182-355">**Windows 8.1**: pulse la tecla Windows del teclado y escriba **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="14182-355">**Windows 8.1**: Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="14182-356">En la ventana Buscar, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="14182-356">In the Search window, click **Settings**.</span></span> <span data-ttu-id="14182-357">En la ventana Resultados, haga clic en **Ver registros de eventos**.</span><span class="sxs-lookup"><span data-stu-id="14182-357">In the Results window, click **View event logs**.</span></span>  
  
     <span data-ttu-id="14182-358">**Windows 7 SP1**: haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="14182-358">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="14182-359">En el cuadro de texto **Buscar**, escriba **Visor de eventos** y haga clic en él para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="14182-359">In the **Search** text box, type **Event Viewer**, and click it to open.</span></span>  
  
2.  <span data-ttu-id="14182-360">Expanda **Registros de Windows**, haga clic con el botón derecho en **Aplicación** y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="14182-360">Expand **Windows Logs**, right-click **Application**, and then click **Properties**.</span></span> <span data-ttu-id="14182-361">En **Propiedades del registro**:</span><span class="sxs-lookup"><span data-stu-id="14182-361">In **Log Properties**:</span></span>  
  
    -   <span data-ttu-id="14182-362">Para determinar el espacio disponible, compare las propiedades **Tamaño del registro** y **Máximo tamaño de registro**.</span><span class="sxs-lookup"><span data-stu-id="14182-362">To determine the available space, compare the **Log Size** and the **Maximum log size** properties.</span></span>  
  
    -   <span data-ttu-id="14182-363">Para proporcionar más espacio, especifique un número más alto en **Máximo tamaño de registro**.</span><span class="sxs-lookup"><span data-stu-id="14182-363">To provide more space, enter a higher number in **Maximum log size**.</span></span>  
  
    -   <span data-ttu-id="14182-364">Para habilitar la sobrescritura de los eventos antiguos cuando se llene el registro, seleccione **Sobrescribir eventos cuando sea necesario**.</span><span class="sxs-lookup"><span data-stu-id="14182-364">To enable overwriting of old events when the log becomes full, select **Overwrite events as needed**.</span></span>  
  
    -   <span data-ttu-id="14182-365">Para borrar los eventos del registro, seleccione **Vaciar registro**.</span><span class="sxs-lookup"><span data-stu-id="14182-365">To clear the log events, select **Clear log**.</span></span>  
  
3.  <span data-ttu-id="14182-366">Haga clic en **Aceptar** para cerrar el **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="14182-366">Click **OK** to close the **Event Viewer**.</span></span>  
  
 <span data-ttu-id="14182-367">**Notas**</span><span class="sxs-lookup"><span data-stu-id="14182-367">**Additional**</span></span>  
  
-   <span data-ttu-id="14182-368">La instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mantiene un registro de eventos en el registro de eventos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="14182-368">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup keeps a record of events in the Application Event Log.</span></span> <span data-ttu-id="14182-369">Según las características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instaladas, la cantidad de espacio necesario en el registro puede superar su límite.</span><span class="sxs-lookup"><span data-stu-id="14182-369">Depending on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features installed, the amount of space required in the log may exceed its limit.</span></span> <span data-ttu-id="14182-370">Si se agota el espacio del registro de eventos de aplicaciones durante la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ésta no se llevará a cabo.</span><span class="sxs-lookup"><span data-stu-id="14182-370">If the application event log runs out of space during [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup, the installation fails.</span></span> <span data-ttu-id="14182-371">Este error se puede evitar cambiando la configuración del registro de eventos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="14182-371">Changing the Application Event Log settings prevents this failure.</span></span>  
  
## <a name="next"></a><span data-ttu-id="14182-372">Siguiente</span><span class="sxs-lookup"><span data-stu-id="14182-372">Next</span></span>  
 [<span data-ttu-id="14182-373">Elegir características y componentes de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="14182-373">Choose BizTalk Server Features and Components</span></span>](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a><span data-ttu-id="14182-374">Ver también</span><span class="sxs-lookup"><span data-stu-id="14182-374">See Also</span></span>  
 <span data-ttu-id="14182-375">[Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="14182-375">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 <span data-ttu-id="14182-376">[Apéndice A: Instalación silenciosa](../install-and-config-guides/appendix-a-silent-installation.md) </span><span class="sxs-lookup"><span data-stu-id="14182-376">[Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md) </span></span>  
 <span data-ttu-id="14182-377">[Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="14182-377">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span></span>  
 <span data-ttu-id="14182-378">[Apéndice C: Archivos CAB redistribuibles](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span><span class="sxs-lookup"><span data-stu-id="14182-378">[Appendix C: Redistributable CAB Files](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span></span>  
 [<span data-ttu-id="14182-379">Apéndice D: Crear el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="14182-379">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
