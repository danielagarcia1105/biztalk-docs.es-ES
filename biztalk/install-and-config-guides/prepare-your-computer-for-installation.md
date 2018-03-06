---
title: "Preparar el equipo para la instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 03/15/2016
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53df7a2f-638b-4921-a97f-736760248526
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c2e732073ccc787cad32984720d7fac422a8cb
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="prepare-your-computer-for-installation"></a><span data-ttu-id="72c27-102">Preparar el equipo para la instalación</span><span class="sxs-lookup"><span data-stu-id="72c27-102">Prepare Your Computer for Installation</span></span>
<span data-ttu-id="72c27-103">En este tema se muestran los pasos necesarios para preparar el equipo, mediante la instalación y configuración de todos los requisitos previos de software, y para crear cuentas y configurar permisos.</span><span class="sxs-lookup"><span data-stu-id="72c27-103">This topic lists the steps to prepare your computer by installing and configuring all software prerequisites, and then creating accounts and setting permissions.</span></span>  

> [!TIP] 
> <span data-ttu-id="72c27-104">Un MVP de integración ha preparado una guía paso a paso muy detallada para instalar los requisitos previos y BizTalk Server: [BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/) (Instalación y configuración de BizTalk 2013, parte 1).</span><span class="sxs-lookup"><span data-stu-id="72c27-104">An integration MVP prepared a very detailed step-by-step guide to install the prerequisites, and BizTalk Server:  [BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/).</span></span>  
> 
> <span data-ttu-id="72c27-105">Microsoft no recomienda algunos pasos, como deshabilitar el Control de acceso de usuarios (UAC) o el Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="72c27-105">Some steps are not recommended by Microsoft, such as disabling User Access Control (UAC) or Windows Firewall.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="72c27-106">Complete estas tareas en el orden que se indica.</span><span class="sxs-lookup"><span data-stu-id="72c27-106">Complete these tasks in the order listed.</span></span>  
  
##  <a name="BKMK_InstUpdates"></a> <span data-ttu-id="72c27-107">Instalar actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="72c27-107">Install Windows Updates</span></span>  
  
-   <span data-ttu-id="72c27-108">**Windows 7**: haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="72c27-108">**Windows 7**: Click Start.</span></span> <span data-ttu-id="72c27-109">En el cuadro de texto **Buscar**, escriba **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="72c27-109">In the **Search** text box, type **Windows Update**.</span></span>  
  
-   <span data-ttu-id="72c27-110">**Windows 8.1, Windows Server 2012 y Windows Server 2012 R2**: haga clic en el botón de Windows del teclado y escriba **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="72c27-110">**Windows 8.1, Windows Server 2012, and Windows Server 2012 R2**: Click the Windows button on the keyboard and type **Windows Update**.</span></span> <span data-ttu-id="72c27-111">En los resultados de la búsqueda, haga clic en **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="72c27-111">From the search results, click **Windows Update**.</span></span>  
  
 <span data-ttu-id="72c27-112">Tras instalar las actualizaciones, puede ser necesario reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="72c27-112">After installing updates, you may need to restart the computer.</span></span>  
  
##  <a name="BKMK_IIS"></a> <span data-ttu-id="72c27-113">Habilitar Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="72c27-113">Enable Internet Information Services</span></span>  
 <span data-ttu-id="72c27-114">Microsoft Internet Information Services (IIS) proporciona una infraestructura de aplicación Web para muchas características de BizTalk Server, como:</span><span class="sxs-lookup"><span data-stu-id="72c27-114">Microsoft Internet Information Services (IIS) provides a Web application infrastructure for many BizTalk Server features, including:</span></span>  
  
-   <span data-ttu-id="72c27-115">adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="72c27-115">HTTP adapter</span></span>  
  
-   <span data-ttu-id="72c27-116">Adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="72c27-116">SOAP adapter</span></span>  
  
-   <span data-ttu-id="72c27-117">Adaptador de Windows Sharepoint Services</span><span class="sxs-lookup"><span data-stu-id="72c27-117">Windows SharePoint Services adapter</span></span>  
  
-   <span data-ttu-id="72c27-118">Cifrado de Capa de sockets seguros (SSL)</span><span class="sxs-lookup"><span data-stu-id="72c27-118">Secure Sockets Layer (SSL) encryption</span></span>  
  
-   <span data-ttu-id="72c27-119">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="72c27-119">BAM Portal</span></span>  
  
#### <a name="install-iis"></a><span data-ttu-id="72c27-120">Instalar IIS</span><span class="sxs-lookup"><span data-stu-id="72c27-120">Install IIS</span></span>

<span data-ttu-id="72c27-121">Pasos de instalación para la dirección URL, vea:</span><span class="sxs-lookup"><span data-stu-id="72c27-121">For the specific install steps, see:</span></span> 

[<span data-ttu-id="72c27-122">Instalar IIS (Windows 8 y Windows Server 2012)</span><span class="sxs-lookup"><span data-stu-id="72c27-122">Install IIS (Windows 8 and Windows Server 2012)</span></span>](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012)

[<span data-ttu-id="72c27-123">Instalar IIS (Windows 7 y Windows Vista)</span><span class="sxs-lookup"><span data-stu-id="72c27-123">Install IIS (Windows 7 and Windows Vista)</span></span>](https://docs.microsoft.com/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7)


<span data-ttu-id="72c27-124">Cuando se instala IIS, además de las opciones predeterminadas, compruebe también lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72c27-124">When you install IIS, in addition to the default checked options, also check the following:</span></span>  
  
- <span data-ttu-id="72c27-125">**Herramientas de administración web**: Seleccione también:</span><span class="sxs-lookup"><span data-stu-id="72c27-125">**Web Management Tools**: Also check:</span></span>  
  
    - <span data-ttu-id="72c27-126">Compatibilidad con la administración de IIS 6:</span><span class="sxs-lookup"><span data-stu-id="72c27-126">IIS 6 Management Compatibility:</span></span>  
  
        - <span data-ttu-id="72c27-127">Consola de administración de IIS 6</span><span class="sxs-lookup"><span data-stu-id="72c27-127">IIS 6 Management Console</span></span>  
  
        - <span data-ttu-id="72c27-128">Compatibilidad con la configuración de IIS 6 y metabase de IIS</span><span class="sxs-lookup"><span data-stu-id="72c27-128">IIS Metabase and IIS 6 configuration compatibility</span></span>  
  
    - <span data-ttu-id="72c27-129">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="72c27-129">IIS Management Console</span></span>  
  
- <span data-ttu-id="72c27-130">**Servicios World Wide Web**: expanda **Seguridad** y seleccione también:</span><span class="sxs-lookup"><span data-stu-id="72c27-130">**World Wide Web Services**: Expand **Security** and also select:</span></span>  
  
    - <span data-ttu-id="72c27-131">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="72c27-131">Basic Authentication</span></span>  
  
    - <span data-ttu-id="72c27-132">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="72c27-132">Windows Authentication</span></span>  

<span data-ttu-id="72c27-133">Considere también los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="72c27-133">Also consider the following:</span></span>  
  
- <span data-ttu-id="72c27-134">**Características de .net framework 3.5**: .NET Framework 4.5 y .NET Framework 3.5 pueden usarse para desarrollar aplicaciones de .net relacionadas con BizTalk Adapter Pack.</span><span class="sxs-lookup"><span data-stu-id="72c27-134">**.Net Framework 3.5 Features**: .NET Framework 4.5 and .NET Framework 3.5 can be used to develop .Net applications involving the BizTalk Adapter Pack.</span></span> <span data-ttu-id="72c27-135">Por lo general, **características de .NET Framework 4.5** ya está instalado.</span><span class="sxs-lookup"><span data-stu-id="72c27-135">Typically, **.NET Framework 4.5 Features** is already installed.</span></span> <span data-ttu-id="72c27-136">Si va a usar .NET Framework 3.5 para crear aplicaciones en el equipo y, a continuación, **características de .net Framework 3.5** también se puede instalar.</span><span class="sxs-lookup"><span data-stu-id="72c27-136">If you will use .NET Framework 3.5 to create applications on this computer, then **.Net Framework 3.5 Features** can also be installed.</span></span>  
  
- <span data-ttu-id="72c27-137">**Message Queue Server**: si usa el adaptador MSMQ, puede crear un almacén MSMQ local. Para ello, seleccione **Message Queue Server**.</span><span class="sxs-lookup"><span data-stu-id="72c27-137">**Message Queuing**: If you are using the MSMQ adapter, you can create a local MSMQ store by checking **Message Queuing**.</span></span>  
  
- <span data-ttu-id="72c27-138">**Servidor SMTP**: si usa el adaptador SMTP, puede crear un servidor SMTP local. Para ello, seleccione **Servidor SMTP**.</span><span class="sxs-lookup"><span data-stu-id="72c27-138">**SMTP Server**: If you are using the SMTP adapter, you can create a local SMTP Server by checking **SMTP Server**.</span></span>  
  
- <span data-ttu-id="72c27-139">**Windows Identity Foundation 3.5**: el adaptador de SharePoint requiere Windows Identity Foundation (WIF) cuando se usa la opción de instalación CSOM.</span><span class="sxs-lookup"><span data-stu-id="72c27-139">**Windows Identity Foundation 3.5**: Windows Identity Foundation (WIF) is required by the SharePoint adapter when using the CSOM installation option.</span></span> <span data-ttu-id="72c27-140">[Apéndice B: instalar el adaptador de SharePoint de Microsoft](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describe la opción de instalación de CSOM para el adaptador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="72c27-140">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the CSOM installation option for the SharePoint adapter.</span></span>    
  
 
##  <a name="BKMK_XLS"></a> <span data-ttu-id="72c27-141">Instalar Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="72c27-141">Install Microsoft Office Excel</span></span>  
  
1.  <span data-ttu-id="72c27-142">Ejecute el programa de instalación de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="72c27-142">Run the Microsoft Office setup.</span></span>  
  
2.  <span data-ttu-id="72c27-143">Cuando llegue a la pantalla **Tipo de instalación**, seleccione **Instalación personalizada** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="72c27-143">When you reach the **Type of Installation** screen, select **Custom Install**, and then select **Next**.</span></span>  
  
3.  <span data-ttu-id="72c27-144">En la pantalla **Instalación personalizada**, seleccione **Excel** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="72c27-144">On the **Custom Setup** screen, select **Excel**, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="72c27-145">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="72c27-145">Select **Install**.</span></span>  
  
5.  <span data-ttu-id="72c27-146">En **Instalación finalizada**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="72c27-146">In **Setup Completed**, select **Finish**.</span></span>  
  
 <span data-ttu-id="72c27-147">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-147">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-148">BizTalk Server solo es compatible con la versión de 32 bits de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="72c27-148">BizTalk Server supports only 32-bit version of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="72c27-149">Microsoft Office Excel es necesario por actividad de supervisión económica (BAM) en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-149">Microsoft Office Excel is required by Business Activity Monitoring (BAM) in BizTalk Server.</span></span> <span data-ttu-id="72c27-150">El libro de BAM de Office Excel se usa para definir los procesos empresariales que desee supervisar.</span><span class="sxs-lookup"><span data-stu-id="72c27-150">The BAM Office Excel Workbook defines the business processes you want to monitor.</span></span> <span data-ttu-id="72c27-151">El libro de Excel de BAM también se usa para definir el modo en que los usuarios empresariales ven los datos que BAM recopila.</span><span class="sxs-lookup"><span data-stu-id="72c27-151">You also use the BAM Excel Workbook to define the way business users see the data collected by BAM.</span></span>  
  
-   <span data-ttu-id="72c27-152">Para cargar correctamente BAM.xla en Excel, instale la opción **Visual Basic para Aplicaciones** de **Características compartidas de Office**.</span><span class="sxs-lookup"><span data-stu-id="72c27-152">To successfully load BAM.xla into Excel, install **Visual Basic for Applications** under **Office Shared Features**.</span></span> <span data-ttu-id="72c27-153">De lo contrario, puede obtener el error "Este libro ha perdido su proyecto de VBA, los controles de ActiveX y todas las demás características relacionadas con la programabilidad".</span><span class="sxs-lookup"><span data-stu-id="72c27-153">Otherwise, you may get error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span>  
  
##  <a name="BKMK_VS"></a> <span data-ttu-id="72c27-154">Instalar Visual Studio</span><span class="sxs-lookup"><span data-stu-id="72c27-154">Install Visual Studio</span></span>  
  
1.  <span data-ttu-id="72c27-155">Ejecute el programa de instalación de Visual Studio como administrador.</span><span class="sxs-lookup"><span data-stu-id="72c27-155">Run the Visual Studio setup as Administrator.</span></span>  
  
2.  <span data-ttu-id="72c27-156">Acepte el contrato de licencia y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="72c27-156">Accept the license agreement and click **Next**.</span></span>  
  
3.  <span data-ttu-id="72c27-157">En **Características opcionales para instalar**, seleccione las opciones que necesite y haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="72c27-157">In **Optional features to install**, select the options you need and then select **Install**.</span></span> <span data-ttu-id="72c27-158">BizTalk Server no necesita ninguna característica opcional.</span><span class="sxs-lookup"><span data-stu-id="72c27-158">BizTalk Server does not require any of the optional features.</span></span>  
  
4.  <span data-ttu-id="72c27-159">En la página **Finalizar**, cierre la ventana y haga clic en **Iniciar** para abrir Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="72c27-159">On the **Finish** page, close the window or click **Launch** to open Visual Studio.</span></span>  
  
 <span data-ttu-id="72c27-160">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-160">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-161">Si instala Visual Studio antes de instalar BizTalk Server y, a continuación, actualiza a Visual Studio Team Explorer, puede que necesite reparar la instalación de BizTalk Server desde el **el Panel de Control** / **programas**  opción.</span><span class="sxs-lookup"><span data-stu-id="72c27-161">If you install Visual Studio before installing BizTalk Server, and then upgrade to Visual Studio Team Explorer, you may need to repair your BizTalk Server installation from the **Control Panel** / **Programs** option.</span></span>  
  
-   <span data-ttu-id="72c27-162">Visual Studio instala automáticamente Microsoft SQL Server Express, que BizTalk Server no usa.</span><span class="sxs-lookup"><span data-stu-id="72c27-162">Visual Studio automatically installs Microsoft SQL Server Express; which is not used by BizTalk Server.</span></span> <span data-ttu-id="72c27-163">Como procedimiento recomendado, desinstale Microsoft SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="72c27-163">As a best practice, uninstall Microsoft SQL Server Express.</span></span>  
  
-   <span data-ttu-id="72c27-164">Las herramientas de desarrollo de BizTalk Server se basan en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="72c27-164">The BizTalk Server development tools are based on Visual Studio.</span></span> <span data-ttu-id="72c27-165">Como mínimo, debe instalar el componente de Microsoft Visual C#® .NET de Visual Studio antes de instalar el servidor BizTalk Server**SDK y herramientas de programadores**.</span><span class="sxs-lookup"><span data-stu-id="72c27-165">At a minimum, you must install the Microsoft Visual C#® .NET component of Visual Studio before you install the BizTalk Server**Developer Tools and SDK**.</span></span>  
  
-   <span data-ttu-id="72c27-166">Visual Studio es *no* necesario si va a instalar BizTalk Server en un equipo de producción (en tiempo de ejecución solo), en la aplicación que no se requiere el desarrollo o depuración.</span><span class="sxs-lookup"><span data-stu-id="72c27-166">Visual Studio is *not* required if you are installing BizTalk Server on a production computer (runtime only), on which no application development or debugging is required.</span></span>  
  
-   <span data-ttu-id="72c27-167">El tiempo de ejecución de BizTalk Server requiere .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="72c27-167">The BizTalk Server runtime requires .NET Framework 4.5.</span></span> <span data-ttu-id="72c27-168">Si se instala el adaptador o el interceptor de Windows Communication Foundation (WCF), es necesario .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="72c27-168">The .NET Framework 3.0 is required if the Windows Communication Foundation (WCF) adapter or WCF Interceptor is installed.</span></span>  
  
##  <a name="BKMK_SQL"></a> <span data-ttu-id="72c27-169">Instalar SQL Server</span><span class="sxs-lookup"><span data-stu-id="72c27-169">Install SQL Server</span></span>  
 <span data-ttu-id="72c27-170">Instalar [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="72c27-170">Install [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span></span>  
  
 <span data-ttu-id="72c27-171">Instalar [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="72c27-171">Install [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span></span>  
  
 <span data-ttu-id="72c27-172">Instalar [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span><span class="sxs-lookup"><span data-stu-id="72c27-172">Install [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span></span>  
  
 <span data-ttu-id="72c27-173">Cuando se instala SQL Server, seleccione las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="72c27-173">When you install SQL Server, select the following features:</span></span>  
  
-   <span data-ttu-id="72c27-174">Servicios de Motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="72c27-174">Database Engine Services</span></span>  
  
    -   <span data-ttu-id="72c27-175">Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="72c27-175">SQL Server Replication</span></span>  
  
    -   <span data-ttu-id="72c27-176">Búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="72c27-176">Full-Text Search</span></span>  
  
-   <span data-ttu-id="72c27-177">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="72c27-177">Analysis Services</span></span>  
  
-   <span data-ttu-id="72c27-178">Reporting Services</span><span class="sxs-lookup"><span data-stu-id="72c27-178">Reporting Services</span></span>  
  
-   <span data-ttu-id="72c27-179">Características compartidas</span><span class="sxs-lookup"><span data-stu-id="72c27-179">Shared Features</span></span>  
  
    -   <span data-ttu-id="72c27-180">SQL Server Data Tools (SQL Server 2014/SQL Server 2012) o Business Intelligence Development Studio (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="72c27-180">SQL Server Data Tools (SQL Server 2014 / SQL Server 2012) or Business Intelligence Development Studio (SQL Server 2008 R2)</span></span>  
  
         [<span data-ttu-id="72c27-181">Descargar las herramientas de datos SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="72c27-181">Download SQL Server 2014 Data Tools</span></span>](http://www.microsoft.com/download/details.aspx?id=42313)  
  
    -   <span data-ttu-id="72c27-182">Conectividad con las herramientas de cliente</span><span class="sxs-lookup"><span data-stu-id="72c27-182">Client Tools Connectivity</span></span>  
  
    -   <span data-ttu-id="72c27-183">Integration Services</span><span class="sxs-lookup"><span data-stu-id="72c27-183">Integration Services</span></span>  
  
    -   <span data-ttu-id="72c27-184">Herramientas de administración: básicas</span><span class="sxs-lookup"><span data-stu-id="72c27-184">Management Tools - Basic</span></span>  
  
        -   <span data-ttu-id="72c27-185">Herramientas de administración - Completa</span><span class="sxs-lookup"><span data-stu-id="72c27-185">Management Tools - Complete</span></span>  
  
 <span data-ttu-id="72c27-186">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-186">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-187">BizTalk Server admite todas las intercalaciones de SQL Server, tanto si distinguen mayúsculas y minúsculas como si no, excepto las intercalaciones binarias.</span><span class="sxs-lookup"><span data-stu-id="72c27-187">BizTalk Server supports all case-sensitive and case-insensitive SQL Server collations except for binary collations.</span></span> <span data-ttu-id="72c27-188">No se admiten intercalaciones binarias.</span><span class="sxs-lookup"><span data-stu-id="72c27-188">Binary collations are not supported.</span></span>  
  
-   <span data-ttu-id="72c27-189">Para un rendimiento óptimo, Microsoft recomienda usar Enterprise Edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-189">For optimal performance, Microsoft recommends using the Enterprise Edition of SQL Server.</span></span> <span data-ttu-id="72c27-190">Consulte [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx) (Características compatibles con las ediciones de SQL Server 2008 R2), [Características compatibles con las ediciones de SQL Server 2012](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx) o [Características compatibles con las ediciones de SQL Server 2014](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="72c27-190">See [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx), [SQL Server 2012 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx), or [SQL Server 2014 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).</span></span>  
  
-   <span data-ttu-id="72c27-191">Se admiten y deben instalarse los Service Packs y las actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="72c27-191">Service packs and Windows Updates are supported and should be installed.</span></span>  
  
-   <span data-ttu-id="72c27-192">Cuando BizTalk Server y SQL Server están en equipos independientes, Coordinador de transacciones distribuidas (MS DTC) controla las transacciones entre los equipos.</span><span class="sxs-lookup"><span data-stu-id="72c27-192">When BizTalk Server and SQL Server are on separate computers, Distributed Transaction Coordinator (MS DTC) handles the transactions between the computers.</span></span> <span data-ttu-id="72c27-193">La característica AlwaysOn de SQL Server no admite transacciones de MSDTC.</span><span class="sxs-lookup"><span data-stu-id="72c27-193">The SQL Server AlwaysOn feature does not support MSDTC transactions.</span></span> <span data-ttu-id="72c27-194">No se admite la característica AlwaysOn de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-194">The SQL Server AlwaysOn feature is not supported.</span></span>  
  
##  <a name="BKMK_MQSeries"></a> <span data-ttu-id="72c27-195">Instalar los requisitos previos de MQSeries</span><span class="sxs-lookup"><span data-stu-id="72c27-195">Install MQSeries Prerequisites</span></span>  
 <span data-ttu-id="72c27-196">**Adaptador de MQSeries**: se instala de forma automática con la instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-196">**MQSeries adapter**: Automatically installed with the BizTalk Server installation.</span></span>  
  
 <span data-ttu-id="72c27-197">**Adaptador de MQSeries Client (MQSC)**:</span><span class="sxs-lookup"><span data-stu-id="72c27-197">**MQSeries Client (MQSC) adapter**:</span></span>  
  
1.  <span data-ttu-id="72c27-198">Ejecute la instalación de Host Integration Server (HIS).</span><span class="sxs-lookup"><span data-stu-id="72c27-198">Run the Host Integration Server (HIS) installation</span></span>  
  
2.  <span data-ttu-id="72c27-199">En Instalación de componentes, expanda **BizTalk Adapters** (Adaptadores de BizTalk).</span><span class="sxs-lookup"><span data-stu-id="72c27-199">In component installation, expand **BizTalk Adapters**.</span></span>  
  
3.  <span data-ttu-id="72c27-200">Seleccione **BizTalk Adapter for WebSphere MQ (Client-Based)** (Adaptador de BizTalk para WebSphere MQ (basado en cliente)).</span><span class="sxs-lookup"><span data-stu-id="72c27-200">Select **BizTalk Adapter for WebSphere MQ (Client-Based)**.</span></span>  
  
 <span data-ttu-id="72c27-201">**Versiones de IBM WebSphere MQ admitidas**:</span><span class="sxs-lookup"><span data-stu-id="72c27-201">**Supported IBM WebSphere MQ versions**:</span></span>  
  
-   <span data-ttu-id="72c27-202">IBM WebSphere MQ 6.0.2.12 y posterior</span><span class="sxs-lookup"><span data-stu-id="72c27-202">IBM WebSphere MQ 6.0.2.12 and later</span></span>  
  
-   <span data-ttu-id="72c27-203">IBM WebSphere MQ 7.0.1.9 y posterior</span><span class="sxs-lookup"><span data-stu-id="72c27-203">IBM WebSphere MQ 7.0.1.9 and later</span></span>  
  
-   <span data-ttu-id="72c27-204">IBM WebSphere MQ 7.1.0.5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="72c27-204">IBM WebSphere MQ 7.1.0.5 and later</span></span>  
  
-   <span data-ttu-id="72c27-205">IBM WebSphere MQ 7.5.0.3 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="72c27-205">IBM WebSphere MQ 7.5.0.3 and later</span></span>  
  
-   <span data-ttu-id="72c27-206">IBM WebSphere MQ 8 (limitado al tiempo de ejecución, sin API de administración)</span><span class="sxs-lookup"><span data-stu-id="72c27-206">IBM WebSphere MQ 8 (limited to runtime; no administration APIs)</span></span>  
  
     <span data-ttu-id="72c27-207">Se incluye compatibilidad con la versión 8 de MQ con [Host Integration Server CU3](https://support.microsoft.com/kb/3019572).</span><span class="sxs-lookup"><span data-stu-id="72c27-207">MQ version 8 support is included with [Host Integration Server CU3](https://support.microsoft.com/kb/3019572).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72c27-208">Si no aparece una versión específica de WebSphere MQ, como MQ 5.x, entonces no es compatible con esta versión de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-208">If a specific WebSphere MQ version is not listed, like MQ 5.x, then it is not supported with this BizTalk Server version.</span></span>  
  
 <span data-ttu-id="72c27-209">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-209">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-210">Como práctica recomendada, instale siempre el paquete de corrección de WebSphere MQ más reciente.</span><span class="sxs-lookup"><span data-stu-id="72c27-210">As a best practice, always install the latest WebSphere MQ fix pack.</span></span> <span data-ttu-id="72c27-211">Consulte [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).</span><span class="sxs-lookup"><span data-stu-id="72c27-211">See [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).</span></span>  
  
-   <span data-ttu-id="72c27-212">Si IBM WebSphere MQ está instalado en un equipo que no tiene Windows, instale la **aplicación MQSAgent COM+** (MQSConfigWiz.exe) y **MQSeries Server para Windows** en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="72c27-212">If IBM WebSphere MQ is installed on a non-Windows computer, install the **MQSAgent COM+ application** (MQSConfigWiz.exe) and **MQSeries Server for Windows** on the same computer.</span></span> <span data-ttu-id="72c27-213">Si IBM WebSphere MQ está instalado en un equipo con Windows, no se usan la **aplicación MQSAgent COM+** y **MQSeries Server para Windows** y, por tanto, no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="72c27-213">If IBM WebSphere MQ is installed on a Windows computer, then the **MQSAgent COM+ application** and **MQSeries Server for Windows** program are not used or needed.</span></span>  
  
     <span data-ttu-id="72c27-214">**MQSConfigWiz.exe** se incluye en los archivos de instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-214">**MQSConfigWiz.exe** is included in the BizTalk Server installation files.</span></span>  
  
     <span data-ttu-id="72c27-215">**MQSeries Server para Windows** no es un programa de Microsoft y debe obtenerse con el programa IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="72c27-215">**MQSeries Server for Windows** is not a Microsoft program and must be obtained with your IBM WebSphere MQ program.</span></span>  
  
-   <span data-ttu-id="72c27-216">En [Adaptador de MQSeries](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) se proporciona más información sobre este adaptador, incluida la configuración de los diferentes componentes.</span><span class="sxs-lookup"><span data-stu-id="72c27-216">[MQSeries Adapter](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) provides more information on the MQSeries adapter, including configuring the different components.</span></span> <span data-ttu-id="72c27-217">En [BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) (BizTalk Server: adaptadores MQSeries y MQSeries Client (MQSC)) se proporciona más información sobre estos adaptadores.</span><span class="sxs-lookup"><span data-stu-id="72c27-217">[BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) provides additional details on the MQSeries and MQSC adapters.</span></span>  
  
-   <span data-ttu-id="72c27-218">IBM WebSphere no es un producto de Microsoft y, por tanto, Microsoft no ofrece soporte técnico para este producto.</span><span class="sxs-lookup"><span data-stu-id="72c27-218">IBM WebSphere is not a Microsoft product and is not supported by Microsoft.</span></span> <span data-ttu-id="72c27-219">Microsoft no garantiza la idoneidad de este programa.</span><span class="sxs-lookup"><span data-stu-id="72c27-219">Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="72c27-220">Para obtener más información acerca de IBM WebSphere MQ, incluidas las instrucciones de descarga, vea www.ibm.com.</span><span class="sxs-lookup"><span data-stu-id="72c27-220">For more information about IBM WebSphere MQ, including download instructions, see www.ibm.com.</span></span>  
  
##  <a name="BKMK_BAMAlerts"></a> <span data-ttu-id="72c27-221">Alertas de BAM</span><span class="sxs-lookup"><span data-stu-id="72c27-221">BAM Alerts</span></span>  
 <span data-ttu-id="72c27-222">Las alertas de BAM con SQL Server 2012 y versiones más recientes usan correo electrónico de base de datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-222">BAM Alerts with SQL Server 2012 and newer versions use Database Mail in SQL Server.</span></span> <span data-ttu-id="72c27-223">Las alertas de BAM con SQL Server 2008 R2 y versiones anteriores usan SQL Notification Services.</span><span class="sxs-lookup"><span data-stu-id="72c27-223">BAM Alerts with SQL Server 2008 R2 and older versions use SQL Notification Services.</span></span> <span data-ttu-id="72c27-224">Antes de instalar o configurar las alertas de BAM, debe configurar los servicios de notificación o correo electrónico de base de datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-224">Before installing or configuring BAM Alerts, you must configure the Notification Services or Database Mail in SQL Server.</span></span>  
  
###  <a name="BKMK_DBMail"></a> <span data-ttu-id="72c27-225">Alertas de BAM con SQL Server 2012/2014</span><span class="sxs-lookup"><span data-stu-id="72c27-225">BAM Alerts using SQL Server 2012/2014</span></span>  
 <span data-ttu-id="72c27-226">Configure [Correo electrónico de base de datos de SQL Server 2012](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="72c27-226">Configure [SQL Server 2012 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).</span></span>  
  
 <span data-ttu-id="72c27-227">Configure [Correo electrónico de base de datos de SQL Server 2014](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="72c27-227">Configure [SQL Server 2014 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="72c27-228">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-228">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-229">Correo electrónico de base de datos usa un servidor SMTP para enviar las alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="72c27-229">Database Mail uses an SMTP server to send the BAM Alerts.</span></span> <span data-ttu-id="72c27-230">Servidor SMTP puede instalarse localmente en el servidor BizTalk Server o en otro servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="72c27-230">SMTP Server can be installed locally on the BizTalk Server or on another IIS server.</span></span> <span data-ttu-id="72c27-231">En [Apéndice D: Crear el servidor SMTP](../install-and-config-guides/appendix-d-create-the-smtp-server.md) se enumeran los pasos necesarios para instalar y configurar un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="72c27-231">[Appendix D: Create the SMTP Server](../install-and-config-guides/appendix-d-create-the-smtp-server.md) lists the steps to install and configure a SMTP Server.</span></span>  
  
###  <a name="BKMK_SSNS"></a> <span data-ttu-id="72c27-232">Alertas de BAM con SQL Server 2008 R2: instalar SQL Server 2005 Notification Services</span><span class="sxs-lookup"><span data-stu-id="72c27-232">BAM Alerts using SQL Server 2008 R2 – Install SQL Server 2005 Notification Services</span></span>  
  
1.  <span data-ttu-id="72c27-233">Vaya a [Feature Pack para Microsoft SQL Server 2005 SP4](http://go.microsoft.com/fwlink/p/?LinkId=286285).</span><span class="sxs-lookup"><span data-stu-id="72c27-233">Go to [Feature Pack for Microsoft SQL Server 2005 SP4](http://go.microsoft.com/fwlink/p/?LinkId=286285).</span></span>  
  
2.  <span data-ttu-id="72c27-234">Descargue e instale el paquete de plataforma adecuado para los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="72c27-234">Download and install the appropriate platform package for the following components:</span></span>  
  
     <span data-ttu-id="72c27-235">**Cliente nativo de Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="72c27-235">**Microsoft SQL Server Native Client**</span></span>  
  
    -   <span data-ttu-id="72c27-236">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi" del paquete X86 (sqlncli.msi)</span><span class="sxs-lookup"><span data-stu-id="72c27-236">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi" X86 Package (sqlncli.msi)</span></span>  
  
    -   <span data-ttu-id="72c27-237">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi" del paquete X64 (sqlncli_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="72c27-237">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi" X64 Package (sqlncli_x64.msi)</span></span>  
  
     <span data-ttu-id="72c27-238">**Colección de objetos de administración de Microsoft SQL Server 2005**</span><span class="sxs-lookup"><span data-stu-id="72c27-238">**Microsoft SQL Server 2005 Management Objects Collection**</span></span>  
  
    -   <span data-ttu-id="72c27-239">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi" del paquete X86 (SQLServer2005_XMO.msi)</span><span class="sxs-lookup"><span data-stu-id="72c27-239">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi" X86 Package (SQLServer2005_XMO.msi)</span></span>  
  
    -   <span data-ttu-id="72c27-240">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi" del paquete X64 (SQLServer2005_XMO_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="72c27-240">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi" X64 Package (SQLServer2005_XMO_x64.msi)</span></span>  
  
     <span data-ttu-id="72c27-241">**Componentes de cliente de Microsoft SQL Server 2005 Notification Services**</span><span class="sxs-lookup"><span data-stu-id="72c27-241">**Microsoft SQL Server 2005 Notification Services Client Components**</span></span>  
  
    -   <span data-ttu-id="72c27-242">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi" del paquete X86 (SQLServer2005_NS.msi)</span><span class="sxs-lookup"><span data-stu-id="72c27-242">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi" X86 Package (SQLServer2005_NS.msi)</span></span>  
  
    -   <span data-ttu-id="72c27-243">HIPERVÍNCULO "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi" del paquete X64 (SQLServer2005_NS_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="72c27-243">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi" X64 Package (SQLServer2005_NS_x64.msi)</span></span>  
  
 <span data-ttu-id="72c27-244">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-244">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-245">SQL Notification Services no deben configurarse; solo se instala en el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-245">SQL Notification Services does not need to be configured; only installed on the BizTalk Server.</span></span>  
  
##  <a name="BKMK_WIF"></a> <span data-ttu-id="72c27-246">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="72c27-246">Windows Identity Foundation</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="72c27-247">Windows 8.1, Windows Server 2012 y Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="72c27-247">Windows 8.1, Windows Server 2012, and Windows Server 2012 R2</span></span>|<span data-ttu-id="72c27-248">Windows Identity Foundation se incluye con el sistema operativo como característica en **Activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="72c27-248">Windows Identity Foundation is included with the operating system as a Feature in **Turn Windows features on or off**.</span></span>|  
|<span data-ttu-id="72c27-249">Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="72c27-249">Windows Vista SP1</span></span>|<span data-ttu-id="72c27-250">Descarga disponible en [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HIPERVÍNCULO "http://www.microsoft.com/download/details.aspx?id=17331".</span><span class="sxs-lookup"><span data-stu-id="72c27-250">Download available at [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK "http://www.microsoft.com/download/details.aspx?id=17331" .</span></span>|  
  
 <span data-ttu-id="72c27-251">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-251">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-252">Windows Identity Foundation (WIF) es necesario para el adaptador de SharePoint o SharePoint Online cuando se usa con el modelo de objetos de SharePoint cliente (CSOM).</span><span class="sxs-lookup"><span data-stu-id="72c27-252">Windows Identity Foundation (WIF) is required for the SharePoint adapter or SharePoint Online when used with SharePoint Client Side Object Model (CSOM).</span></span> <span data-ttu-id="72c27-253">Concretamente:</span><span class="sxs-lookup"><span data-stu-id="72c27-253">Specifically:</span></span>  
  
    |<span data-ttu-id="72c27-254">Opción de instalación</span><span class="sxs-lookup"><span data-stu-id="72c27-254">Installation Option</span></span>|<span data-ttu-id="72c27-255">WIF requerido</span><span class="sxs-lookup"><span data-stu-id="72c27-255">WIF Required</span></span>|  
    |-------------------------|------------------|  
    |<span data-ttu-id="72c27-256">Adaptador de SharePoint con CSOM</span><span class="sxs-lookup"><span data-stu-id="72c27-256">SharePoint Adapter with CSOM</span></span>|<span data-ttu-id="72c27-257">Sí</span><span class="sxs-lookup"><span data-stu-id="72c27-257">Yes</span></span>|  
    |<span data-ttu-id="72c27-258">SharePoint Online con CSOM</span><span class="sxs-lookup"><span data-stu-id="72c27-258">SharePoint Online with CSOM</span></span>|<span data-ttu-id="72c27-259">Sí</span><span class="sxs-lookup"><span data-stu-id="72c27-259">Yes</span></span>|  
    |<span data-ttu-id="72c27-260">Servicio Web del adaptador de SharePoint (en desuso)</span><span class="sxs-lookup"><span data-stu-id="72c27-260">SharePoint Adapter Web Service (deprecated)</span></span>|<span data-ttu-id="72c27-261">no</span><span class="sxs-lookup"><span data-stu-id="72c27-261">No</span></span>|  
    |<span data-ttu-id="72c27-262">Sin SharePoint</span><span class="sxs-lookup"><span data-stu-id="72c27-262">No SharePoint</span></span>|<span data-ttu-id="72c27-263">no</span><span class="sxs-lookup"><span data-stu-id="72c27-263">No</span></span>|  
  
-   <span data-ttu-id="72c27-264">[Apéndice B: instalar el adaptador de SharePoint de Microsoft](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) proporciona información específica sobre las opciones de instalación de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="72c27-264">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides specific information on the SharePoint installation options.</span></span>  
  
##  <a name="BKMK_WSS"></a> <span data-ttu-id="72c27-265">Instalar y configurar Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="72c27-265">Install and Configure Microsoft SharePoint</span></span>  
 <span data-ttu-id="72c27-266">Instalar [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span><span class="sxs-lookup"><span data-stu-id="72c27-266">Install [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span></span>  
  
 <span data-ttu-id="72c27-267">Instalar el [servicio SharePoint Online](http://technet.microsoft.com/library/jj819267.aspx)</span><span class="sxs-lookup"><span data-stu-id="72c27-267">Install [SharePoint Online Service](http://technet.microsoft.com/library/jj819267.aspx)</span></span>  
  
 <span data-ttu-id="72c27-268">Instalar [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="72c27-268">Install [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span></span>  
  
 <span data-ttu-id="72c27-269">Instalar [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span><span class="sxs-lookup"><span data-stu-id="72c27-269">Install [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span></span>  
  
 <span data-ttu-id="72c27-270">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-270">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-271">Si va a instalar SharePoint, debe hacerlo antes de continuar con los demás requisitos previos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-271">If you are installing SharePoint, you must do so before continuing with the remaining BizTalk Server prerequisites.</span></span>  
  
-   <span data-ttu-id="72c27-272">La instalación y configuración de SharePoint consiste en los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="72c27-272">Installing and configuring SharePoint consists of the following procedures:</span></span>  
  
    -   <span data-ttu-id="72c27-273">Instalar SharePoint</span><span class="sxs-lookup"><span data-stu-id="72c27-273">Install SharePoint</span></span>  
  
    -   <span data-ttu-id="72c27-274">Configurar SharePoint</span><span class="sxs-lookup"><span data-stu-id="72c27-274">Configure SharePoint</span></span>  
  
    -   <span data-ttu-id="72c27-275">Extender el sitio web predeterminado como un servidor virtual</span><span class="sxs-lookup"><span data-stu-id="72c27-275">Extend the default Web site as a virtual server</span></span>  
  
-   <span data-ttu-id="72c27-276">En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se describen las opciones de instalación del adaptador de SharePoint para BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-276">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the SharePoint adapter installation options for BizTalk Server.</span></span>  
  
-   <span data-ttu-id="72c27-277">Cuando se use el adaptador de SharePoint, se recomienda instalar la nueva opción CSOM en lugar del servicio web de SharePoint, que se describe en [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="72c27-277">When using the SharePoint adapter, it is recommended to install the new CSOM option instead of the SharePoint Service Web Service; described at [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).</span></span>  
  
##  <a name="BKMK_SharedMem"></a> <span data-ttu-id="72c27-278">Deshabilitar el protocolo de memoria compartida</span><span class="sxs-lookup"><span data-stu-id="72c27-278">Disable the Shared Memory Protocol</span></span>  
  
1.  <span data-ttu-id="72c27-279">Abra el **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="72c27-279">Open **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="72c27-280">En **Administrador de configuración de SQL Server**, expanda **Configuración de red de SQL Server** y seleccione **Protocolos de MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="72c27-280">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, and then select **Protocols for MSSQLSERVER**.</span></span>  
  
3.  <span data-ttu-id="72c27-281">Haga clic con el botón derecho en **Memoria compartida** y seleccione **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="72c27-281">Right-click **Shared Memory**, and then select **Disable**.</span></span>  
  
4.  <span data-ttu-id="72c27-282">Seleccione **Servicios de SQL Server**, haga clic con el botón derecho en **SQL Server (MSSQLSERVER)** y elija **Detener**.</span><span class="sxs-lookup"><span data-stu-id="72c27-282">Select **SQL Server Services**, right-click **SQL Server (MSSQLSERVER)**, and then select **Stop**.</span></span> <span data-ttu-id="72c27-283">Después de detener el servicio, haga clic de nuevo con el botón derecho en **SQL Server (MSSQLSERVER)** y elija **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="72c27-283">After the service has stopped, right-click **SQL Server (MSSQLSERVER)** again, and then select **Start**.</span></span>  
  
5.  <span data-ttu-id="72c27-284">Cierre el **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="72c27-284">Close **SQL Server Configuration Manager**.</span></span>  
  
 <span data-ttu-id="72c27-285">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-285">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-286">Bajo determinadas condiciones de sobrecarga (como, por ejemplo, cuando los clientes obtienen acceso al servidor SQL Server desde el mismo equipo), el protocolo de memoria compartida de SQL Server puede reducir el rendimiento de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-286">Under certain stress conditions (such as clients accessing SQL Server from the same computer), the SQL Server Shared Memory protocol may lower BizTalk Server performance.</span></span> <span data-ttu-id="72c27-287">Para resolver este comportamiento, puede deshabilitar el uso del protocolo de red de memoria compartida en la configuración de red de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-287">You can resolve this behavior by disabling the Shared Memory network protocol in SQL Server Network Configuration.</span></span>  
  
-   <span data-ttu-id="72c27-288">ReplaceThisText</span><span class="sxs-lookup"><span data-stu-id="72c27-288">ReplaceThisText</span></span>  
  
##  <a name="BKMK_LocalAdmin"></a> <span data-ttu-id="72c27-289">Unirse al grupo de administradores local</span><span class="sxs-lookup"><span data-stu-id="72c27-289">Join the Local Administrators Group</span></span>  
 <span data-ttu-id="72c27-290">**Windows Server 2012** : [de Windows Server 2012: cómo agregar una cuenta a un grupo de administradores Local](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span><span class="sxs-lookup"><span data-stu-id="72c27-290">**Windows Server 2012** : [Windows Server 2012: How to Add an Account to a Local Administrator Group](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span></span>  
  
 <span data-ttu-id="72c27-291">**Windows 8.1**: para abrir Usuarios y grupos locales en Windows 8, pulse la tecla Windows del teclado y escriba **grupos**.</span><span class="sxs-lookup"><span data-stu-id="72c27-291">**Windows 8.1**: To open Local Users and Groups on Windows 8, click the Windows button on the keyboard and type **groups**.</span></span> <span data-ttu-id="72c27-292">En la ventana Buscar, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="72c27-292">In the Search window, click **Settings**.</span></span> <span data-ttu-id="72c27-293">En la ventana Resultados, haga clic en **Editar usuarios y grupos locales**.</span><span class="sxs-lookup"><span data-stu-id="72c27-293">In the Results window, click **Edit local users and groups**.</span></span> <span data-ttu-id="72c27-294">Haga clic en **Grupos** y después haga doble clic en Administradores para agregar una cuenta.</span><span class="sxs-lookup"><span data-stu-id="72c27-294">Click **Groups** and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="72c27-295">**Windows 7 SP1**: haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="72c27-295">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="72c27-296">En el cuadro de texto **Buscar**, escriba **Administración de equipos** y haga clic en él para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="72c27-296">In the **Search** text box, type **Computer Management**, and click it to open.</span></span> <span data-ttu-id="72c27-297">Expanda **Usuarios y grupos locales**, elija **Grupos** y haga doble clic en Administradores para agregar una cuenta.</span><span class="sxs-lookup"><span data-stu-id="72c27-297">Expand **Local Users and Groups**, click **Groups**, and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="72c27-298">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-298">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-299">Debe ser miembro del grupo Administradores local para instalar y configurar el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="72c27-299">You must be a member of the local Administrators group to install and configure BizTalk Server.</span></span>  
  
##  <a name="BKMK_AppLog"></a> <span data-ttu-id="72c27-300">Configurar el registro de eventos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="72c27-300">Configure the Application Event Log</span></span>  
  
1.  <span data-ttu-id="72c27-301">Abra el **Visor de eventos**:</span><span class="sxs-lookup"><span data-stu-id="72c27-301">Open **Event Viewer**:</span></span>  
  
     <span data-ttu-id="72c27-302">**Windows Server 2012** : haga clic en el botón de Windows del teclado y escriba **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="72c27-302">**Windows Server 2012** : Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="72c27-303">En la ventana Resultados, haga clic en **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="72c27-303">In the Results window, click **Event Viewer**.</span></span>  
  
     <span data-ttu-id="72c27-304">**Windows 8.1**: pulse la tecla Windows del teclado y escriba **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="72c27-304">**Windows 8.1**: Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="72c27-305">En la ventana Buscar, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="72c27-305">In the Search window, click **Settings**.</span></span> <span data-ttu-id="72c27-306">En la ventana Resultados, haga clic en **Ver registros de eventos**.</span><span class="sxs-lookup"><span data-stu-id="72c27-306">In the Results window, click **View event logs**.</span></span>  
  
     <span data-ttu-id="72c27-307">**Windows 7 SP1**: haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="72c27-307">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="72c27-308">En el cuadro de texto **Buscar**, escriba **Visor de eventos** y haga clic en él para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="72c27-308">In the **Search** text box, type **Event Viewer**, and click it to open.</span></span>  
  
2.  <span data-ttu-id="72c27-309">Expanda **Registros de Windows**, haga clic con el botón derecho en **Aplicación** y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="72c27-309">Expand **Windows Logs**, right-click **Application**, and then click **Properties**.</span></span> <span data-ttu-id="72c27-310">En **Propiedades del registro**:</span><span class="sxs-lookup"><span data-stu-id="72c27-310">In **Log Properties**:</span></span>  
  
    -   <span data-ttu-id="72c27-311">Para determinar el espacio disponible, compare las propiedades **Tamaño del registro** y **Máximo tamaño de registro**.</span><span class="sxs-lookup"><span data-stu-id="72c27-311">To determine the available space, compare the **Log Size** and the **Maximum log size** properties.</span></span>  
  
    -   <span data-ttu-id="72c27-312">Para proporcionar más espacio, especifique un número más alto en **Máximo tamaño de registro**.</span><span class="sxs-lookup"><span data-stu-id="72c27-312">To provide more space, enter a higher number in **Maximum log size**.</span></span>  
  
    -   <span data-ttu-id="72c27-313">Para habilitar la sobrescritura de los eventos antiguos cuando se llene el registro, seleccione **Sobrescribir eventos cuando sea necesario**.</span><span class="sxs-lookup"><span data-stu-id="72c27-313">To enable overwriting of old events when the log becomes full, select **Overwrite events as needed**.</span></span>  
  
    -   <span data-ttu-id="72c27-314">Para borrar los eventos del registro, seleccione **Vaciar registro**.</span><span class="sxs-lookup"><span data-stu-id="72c27-314">To clear the log events, select **Clear log**.</span></span>  
  
3.  <span data-ttu-id="72c27-315">Haga clic en **Aceptar** para cerrar el **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="72c27-315">Click **OK** to close the **Event Viewer**.</span></span>  
  
 <span data-ttu-id="72c27-316">**Notas**</span><span class="sxs-lookup"><span data-stu-id="72c27-316">**Additional**</span></span>  
  
-   <span data-ttu-id="72c27-317">El programa de instalación de BizTalk Server mantiene un registro de eventos en el registro de eventos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="72c27-317">BizTalk Server setup keeps a record of events in the Application Event Log.</span></span> <span data-ttu-id="72c27-318">En función de las características de BizTalk Server instaladas, la cantidad de espacio necesaria en el registro puede superar su límite.</span><span class="sxs-lookup"><span data-stu-id="72c27-318">Depending on the BizTalk Server features installed, the amount of space required in the log may exceed its limit.</span></span> <span data-ttu-id="72c27-319">Si el registro de eventos de aplicación se queda sin espacio durante la instalación de BizTalk Server, se produce un error en la instalación.</span><span class="sxs-lookup"><span data-stu-id="72c27-319">If the application event log runs out of space during BizTalk Server setup, the installation fails.</span></span> <span data-ttu-id="72c27-320">Este error se puede evitar cambiando la configuración del registro de eventos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="72c27-320">Changing the Application Event Log settings prevents this failure.</span></span>  
  
## <a name="next"></a><span data-ttu-id="72c27-321">Siguiente</span><span class="sxs-lookup"><span data-stu-id="72c27-321">Next</span></span>  
 [<span data-ttu-id="72c27-322">Elegir características y componentes de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="72c27-322">Choose BizTalk Server Features and Components</span></span>](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a><span data-ttu-id="72c27-323">Vea también</span><span class="sxs-lookup"><span data-stu-id="72c27-323">See Also</span></span>  
 <span data-ttu-id="72c27-324">[Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="72c27-324">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 <span data-ttu-id="72c27-325">[Apéndice A: Instalación silenciosa](../install-and-config-guides/appendix-a-silent-installation.md) </span><span class="sxs-lookup"><span data-stu-id="72c27-325">[Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md) </span></span>  
 <span data-ttu-id="72c27-326">[Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="72c27-326">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span></span>  
 <span data-ttu-id="72c27-327">[Apéndice C: Archivos CAB redistribuibles](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span><span class="sxs-lookup"><span data-stu-id="72c27-327">[Appendix C: Redistributable CAB Files](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span></span>  
 [<span data-ttu-id="72c27-328">Apéndice D: Crear el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="72c27-328">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
