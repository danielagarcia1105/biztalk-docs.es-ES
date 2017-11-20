---
title: Instalar el adaptador de Microsoft BizTalk para SQL Server - 2016 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcc6b94e-1cac-4b90-8567-05b33caa9bf3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d4df12cfc9e37ed5deff59051cb483dd092facb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2016"></a><span data-ttu-id="f9ea1-102">Instalar al adaptador de Microsoft BizTalk para SQL Server - 2016</span><span class="sxs-lookup"><span data-stu-id="f9ea1-102">Install Microsoft BizTalk Adapter for SQL Server - 2016</span></span>
<span data-ttu-id="f9ea1-103">Instalar el [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] incluido con [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-103">Install the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] included with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span>

 <span data-ttu-id="f9ea1-104">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se puede usar con:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used with:</span></span>  
  
-   <span data-ttu-id="f9ea1-105">Una aplicación .NET</span><span class="sxs-lookup"><span data-stu-id="f9ea1-105">A .NET application</span></span>  
  
-   <span data-ttu-id="f9ea1-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9ea1-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
 <span data-ttu-id="f9ea1-107">En función de cómo usar los adaptadores, que varía según el software necesario.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-107">Based on how you use the adapters, the required software varies.</span></span>  
 
  
<a name="BKMK_prereq_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a><span data-ttu-id="f9ea1-108">Requisitos previos para configurar el adaptador con una aplicación .NET</span><span class="sxs-lookup"><span data-stu-id="f9ea1-108">Prerequisites when using the adapter with a .NET Application</span></span>  
<span data-ttu-id="f9ea1-109">Instalar el software siguiente en el equipo donde está escribiendo aplicaciones .NET que usen el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-109">Install the following software on the computer where you are writing .NET applications that consume the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="f9ea1-110">Instalar el software en el orden en que se muestran.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-110">Install the software in the order as listed.</span></span>  

||
|---|
|<span data-ttu-id="f9ea1-111">-Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f9ea1-111">- Windows Server 2016</span></span> <br /><span data-ttu-id="f9ea1-112">-Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f9ea1-112">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="f9ea1-113">-Windows 10</span><span class="sxs-lookup"><span data-stu-id="f9ea1-113">- Windows 10</span></span> <br /><span data-ttu-id="f9ea1-114">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f9ea1-114">- Windows 8.1</span></span>    |
|<span data-ttu-id="f9ea1-115">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="f9ea1-115">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="f9ea1-116">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="f9ea1-116">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|
|<span data-ttu-id="f9ea1-117">Bibliotecas de cliente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-117">SQL Server client libraries.</span></span> <span data-ttu-id="f9ea1-118">Consulte la [versiones compatibles](#BKMK_SuppLOB) (en este tema).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-118">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_prereq_BTS"></a>     
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="f9ea1-119">Requisitos previos para configurar el adaptador con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f9ea1-119">Prerequisites when using the adapter with BizTalk Server</span></span>  
<span data-ttu-id="f9ea1-120">Instalar el software siguiente en el equipo donde se usa el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-120">Install the following software on the computer where you are using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f9ea1-121">Instalar el software en el orden indicado.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-121">Install the software in the order listed.</span></span>  

||
|---|
|<span data-ttu-id="f9ea1-122">-Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f9ea1-122">- Windows Server 2016</span></span> <br /><span data-ttu-id="f9ea1-123">-Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f9ea1-123">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="f9ea1-124">-Windows 10</span><span class="sxs-lookup"><span data-stu-id="f9ea1-124">- Windows 10</span></span> <br /><span data-ttu-id="f9ea1-125">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f9ea1-125">- Windows 8.1</span></span>    |
|<span data-ttu-id="f9ea1-126">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="f9ea1-126">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="f9ea1-127">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="f9ea1-127">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="f9ea1-128">Instalar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] incluido con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-128">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="f9ea1-129">Para instalar, realice una **personalizado** (seleccione **complemento de BizTalk Server**) o **completar** instalación de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-129">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|
|[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|
|<span data-ttu-id="f9ea1-130">Bibliotecas de cliente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-130">SQL Server client libraries.</span></span> <span data-ttu-id="f9ea1-131">Consulte la [versiones compatibles](#BKMK_SuppLOB) (en este tema).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-131">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a><span data-ttu-id="f9ea1-132">Versiones admitidas de SQL Server y las bibliotecas de cliente</span><span class="sxs-lookup"><span data-stu-id="f9ea1-132">Supported SQL Server versions and client libraries</span></span>  
 <span data-ttu-id="f9ea1-133">En la siguiente sección presenta las versiones admitidas de SQL Server y el cliente de bibliotecas requeridas por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-133">The following section presents the supported SQL Server versions and the client libraries required by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="f9ea1-134">**Versiones de servidor admitidas**: SQL Server 2016, SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="f9ea1-134">**Supported server versions**: SQL Server 2016, SQL Server 2014</span></span>
  
-   <span data-ttu-id="f9ea1-135">**Admite versiones de cliente**: Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] agrupaciones de lo archivos DLL de cliente necesaria para conectarse a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-135">**Supported client versions**: Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] bundles the client DLLs required to connect to SQL Server.</span></span> <span data-ttu-id="f9ea1-136">No es necesario instalar explícitamente cualquier cliente de DLL en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-136">You do not need to explicitly install any client DLLs on your computer.</span></span>  
  
-   <span data-ttu-id="f9ea1-137">**Controladores necesarios**:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-137">**Required drivers**:</span></span>  
  
    -   <span data-ttu-id="f9ea1-138">Si usa los UDT incluidos con las versiones de SQL Server, por ejemplo, Geography, asegúrese de que los archivos DLL siguientes están presentes en el equipo donde se usa el adaptador para realizar operaciones en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-138">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="f9ea1-139">Por ejemplo, si crea proyectos de BizTalk para realizar operaciones en SQL Server, estos archivos DLL deben estar presentes en el equipo donde se está ejecutando el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-139">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  
  
        -   <span data-ttu-id="f9ea1-140">Asegúrese de que Microsoft.SqlServer.Types.dll se agrega a la GAC.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-140">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  
  
        -   <span data-ttu-id="f9ea1-141">Asegúrese de que SqlServerSpatial.dll está disponible en la carpeta System32.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-141">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>  
  
         <span data-ttu-id="f9ea1-142">Puede instalar estos archivos DLL en el equipo ejecutando el programa de instalación de SQL Server y seleccionando **herramientas de administración – básica** y **herramientas de administración – completa** en la **selección de características**página del asistente.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-142">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>  
  
    -   <span data-ttu-id="f9ea1-143">Si usa el adaptador para realizar operaciones en columnas de tipos de datos FILESTREAM, asegúrese de que tiene instalado el SDK de conectividad de cliente de SQL.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-143">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="f9ea1-144">Puede instalar el SDK de conectividad de cliente de SQL, ejecute el programa de instalación de SQL Server y seleccionar **SDK de conectividad de cliente de SQL** en el **selección de características** página del asistente.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-144">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="f9ea1-145">El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-145">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  
  
    -   <span data-ttu-id="f9ea1-146">Si crea su propio UDT en SQL Server, asegúrese de que los ensamblados correspondientes para los UDT se agregan a la GAC.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-146">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  
  
<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a><span data-ttu-id="f9ea1-147">Compatibilidad con 64 bits</span><span class="sxs-lookup"><span data-stu-id="f9ea1-147">64-bit support</span></span> 

<span data-ttu-id="f9ea1-148">La [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede ejecutar en una instancia de host de 32 bits o 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-148">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can run in a 32-bit or 64-bit host instance.</span></span>

 <span data-ttu-id="f9ea1-149">Para obtener información acerca de los escenarios de instalación admitidos para las 32 bits y 64 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [escenarios de instalación de 32 bits y 64 bits](#BKMK_Install_Scenarios) (en este tema).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-149">For information about the supported installation scenarios for the 32-bit and 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see  [32-bit and 64-bit install scenarios](#BKMK_Install_Scenarios) (in this topic).</span></span>
  
<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a><span data-ttu-id="f9ea1-150">Instalar al adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="f9ea1-150">Install the SQL adapter</span></span>  
 <span data-ttu-id="f9ea1-151">Asegúrese de que tiene los requisitos previos instalados antes de instalar la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-151">Make sure you have the prerequisites installed before installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="f9ea1-152">Vea [requisitos previos de .NET](#BKMK_prereq_NET) (en este tema), o [requisitos previos de BizTalk Server](#BKMK_prereq_BTS) (en este tema).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-152">See [.NET prerequisites](#BKMK_prereq_NET) (in this topic), or [BizTalk Server prerequisites](#BKMK_prereq_BTS) (in this topic).</span></span>
  
 <span data-ttu-id="f9ea1-153">Puede instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-153">You can install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="f9ea1-154">**En el modo interactivo** mediante el Asistente para la instalación</span><span class="sxs-lookup"><span data-stu-id="f9ea1-154">**In interactive mode** using the setup wizard</span></span>
  
-   <span data-ttu-id="f9ea1-155">**En modo silencioso** mediante msiexec en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="f9ea1-155">**In silent mode** using msiexec in the command line</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f9ea1-156">Debe tener privilegios administrativos en el equipo donde se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], independientemente de si va a instalar mediante el asistente o la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-156">You must have administrative privileges on the computer where you install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], irrespective of whether you are installing by using the wizard or the command line.</span></span>    

### <span data-ttu-id="f9ea1-157"><a name="BKMK_Install_Scenarios"></a>escenarios de instalación de 32 bits y 64 bits</span><span class="sxs-lookup"><span data-stu-id="f9ea1-157"><a name="BKMK_Install_Scenarios"></a> 32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="f9ea1-158">Con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede utilizarse para:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-158">With [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used for:</span></span>  
  
-   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="f9ea1-159">tiempo de diseño (cuándo generar metadatos para operaciones).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-159"> design time (when generating metadata for operations).</span></span>  
  
-   <span data-ttu-id="f9ea1-160">Tiempo de diseño de consola de administración de BizTalk Server (para la creación de puertos físicos).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-160">BizTalk Server Administration console design time (for creating physical ports).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9ea1-161">Consola de administración de BizTalk Server se ejecuta como una aplicación de Microsoft Management Console (MMC) de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-161">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="f9ea1-162">Tiempo de ejecución de BizTalk (al enviar y recibir mensajes desde aplicaciones de LOB).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-162">BizTalk run time (when sending and receiving messages from LOB applications).</span></span>  
  
 <span data-ttu-id="f9ea1-163">Puede tener una instalación donde realizar todas estas tareas en el mismo equipo o en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-163">You can have an installation where you perform all these tasks on the same computer or different computers.</span></span> <span data-ttu-id="f9ea1-164">Dado que ambos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y MMC de BizTalk son procesos de 32 bits, debe instalar el 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en el equipo donde desea realizar las tareas de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-164">Because both [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on the computer where you want to perform the design-time tasks.</span></span> <span data-ttu-id="f9ea1-165">Se admiten los escenarios siguientes para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en plataformas de 32 bits y 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-165">The following scenarios are supported for installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on 32-bit and 64-bit platforms.</span></span>  
  
#### <a name="32-bit-install-scenarios"></a><span data-ttu-id="f9ea1-166">escenarios de instalación de 32 bits</span><span class="sxs-lookup"><span data-stu-id="f9ea1-166">32-bit install scenarios</span></span>  
 <span data-ttu-id="f9ea1-167">Se admiten los siguientes escenarios cuando se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una plataforma de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-167">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 32-bit platform.</span></span>  
  
|<span data-ttu-id="f9ea1-168">Tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f9ea1-168">Visual Studio design time</span></span>|<span data-ttu-id="f9ea1-169">Tiempo de diseño de MMC de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f9ea1-169">BizTalk MMC design time</span></span>|<span data-ttu-id="f9ea1-170">Tiempo de ejecución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f9ea1-170">BizTalk run time</span></span>|<span data-ttu-id="f9ea1-171">Tiempo de ejecución de Visual tiempo de diseño de Studio o tiempo de diseño de BizTalk MMC + BizTalk</span><span class="sxs-lookup"><span data-stu-id="f9ea1-171">Visual Studio design time and/or  BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="f9ea1-172">-Instalar 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-172">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-173">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-173">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-174">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-174">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="f9ea1-175">-Instalar 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-175">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-176">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-176">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-177">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-177">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="f9ea1-178">-Instalar 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-178">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-179">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-179">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-180">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-180">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="f9ea1-181">-Instalar 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-181">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-182">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-182">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-183">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-183">- Install 32-bit client and other required DLLs.</span></span>|  
  
#### <a name="64-bit-install-scenarios"></a><span data-ttu-id="f9ea1-184">escenarios de instalación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="f9ea1-184">64-bit install scenarios</span></span>  
 <span data-ttu-id="f9ea1-185">Se admiten los siguientes escenarios cuando se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-185">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 64-bit platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9ea1-186">En cualquier equipo donde desea realizar tareas de tiempo de diseño mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o MMC de BizTalk, debe instalar lo 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-186">On any computer where you want to perform design-time tasks using either [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
|<span data-ttu-id="f9ea1-187">Tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f9ea1-187">Visual Studio design time</span></span>|<span data-ttu-id="f9ea1-188">Tiempo de diseño de MMC de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f9ea1-188">BizTalk MMC design time</span></span>|<span data-ttu-id="f9ea1-189">Tiempo de ejecución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f9ea1-189">BizTalk run time</span></span>|<span data-ttu-id="f9ea1-190">Tiempo de ejecución de Visual tiempo de diseño de Studio o tiempo de diseño de BizTalk MMC + BizTalk</span><span class="sxs-lookup"><span data-stu-id="f9ea1-190">Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="f9ea1-191">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-191">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-192">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-192">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-193">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-193">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="f9ea1-194">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-194">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-195">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-195">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-196">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-196">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="f9ea1-197">**Para un proceso de BizTalk de 32 bits**:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-197">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="f9ea1-198">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-198">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-199">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-199">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-200">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-200">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="f9ea1-201">**Para un proceso de BizTalk de 64 bits**:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-201">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="f9ea1-202">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-202">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-203">-Instalar 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-203">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-204">-Instalar el cliente de 64 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-204">- Install 64-bit client and other required DLLs.</span></span>|<span data-ttu-id="f9ea1-205">**Para un proceso de BizTalk de 32 bits**:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-205">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="f9ea1-206">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-206">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-207">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-207">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-208">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-208">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="f9ea1-209">**Para un proceso de BizTalk de 64 bits**:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-209">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="f9ea1-210">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-210">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-211">-Instalar 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-211">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-212">-Instalar el cliente de 64 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-212">- Install 64-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="f9ea1-213">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-213">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="f9ea1-214">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-214">- Install 32-bit client and other required DLLs.</span></span>|  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-adapter-in-interactive-mode"></a><span data-ttu-id="f9ea1-215">Instalar al adaptador en modo interactivo</span><span class="sxs-lookup"><span data-stu-id="f9ea1-215">Install the adapter in interactive mode</span></span>  
<span data-ttu-id="f9ea1-216">Complete los pasos siguientes para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante el Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-216">Complete the following steps to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the setup wizard.</span></span>  
  
1.  <span data-ttu-id="f9ea1-217">Ejecute al instalador.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-217">Run the installer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9ea1-218">Si va a instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una máquina virtual, el Asistente para la instalación no puede continuar más allá de un cuadro de diálogo que le informa de que el programa de instalación comprueba si hay espacio disponible en disco.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-218">If you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="f9ea1-219">En tales casos, se recomienda que utilice la opción de instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-219">In such cases, we recommend that you use the silent installation option.</span></span> <span data-ttu-id="f9ea1-220">Para obtener más información, consulte [instalar el adaptador de SQL en modo silencioso](#BKMK_SilentInst) (en este tema).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-220">For more information, see [Install the SQL adapter in silent mode](#BKMK_SilentInst) (in this topic).</span></span>
  
2.  <span data-ttu-id="f9ea1-221">Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-221">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="f9ea1-222">Lea y acepte el contrato de licencia para el usuario final (CLUF) y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-222">Read and accept the end-user license agreement (EULA), and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f9ea1-223">En el **carpeta de destino** diálogo cuadro, especifique la ubicación donde desea instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], haga clic en **siguiente**y, a continuación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-223">In the **Destination Folder** dialog box, specify the location where you want to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], click **Next**, and then click **Install**.</span></span>  
  
5.  <span data-ttu-id="f9ea1-224">En el **Customer Experience Improvement Program** cuadro de diálogo, especifique si desea inscribir para el programa para la mejora de la experiencia del usuario (CEIP).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-224">In the **Customer Experience Improvement Program** dialog box, specify whether you would like to enroll for the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="f9ea1-225">Como parte del CEIP para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], van a compartir los siguientes datos con Microsoft:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-225">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="f9ea1-226">Datos relacionados con el hardware del equipo en el que va a instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-226">Data related to the computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="f9ea1-227">Datos relacionados con las versiones de SQL Server que usa para conectarse mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-227">Data related to the SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="f9ea1-228">Especifique la elección y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-228">Specify your choice and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9ea1-229">Siempre puede cambiar su preferencia con respecto a inscribirse en CEIP ejecutando el programa de instalación en modo de reparación desde el Panel de Control.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-229">You can always change your preference regarding enrolling for CEIP by running the Setup in Repair mode from the Control Panel.</span></span>  
  
6.  <span data-ttu-id="f9ea1-230">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-230">Click **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="f9ea1-231">Instalar al adaptador de SQL en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="f9ea1-231">Install the SQL adapter in silent mode</span></span> 
<span data-ttu-id="f9ea1-232">Complete los pasos siguientes para realizar una instalación silenciosa de [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante el `msiexec` comando.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-232">Complete the following steps to do a silent installation of [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the `msiexec` command.</span></span>  
  
1.  <span data-ttu-id="f9ea1-233">Abra un símbolo del sistema y navegue hasta la carpeta donde haya el instalador.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-233">Open a command prompt, and navigate to the folder where you have the installer.</span></span>  
  
2.  <span data-ttu-id="f9ea1-234">Ejecute el siguiente comando para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-234">Run the following command to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9ea1-235">Para llevar a cabo una instalación silenciosa en una plataforma basada en x64, en los siguientes comandos, reemplace SqlAdapterSetup.msi por SqlAdapterSetup64.msi.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-235">To perform silent installation on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="f9ea1-236">También puede elegir para inscribirse en CEIP como parte de la instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-236">You can also choose to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="f9ea1-237">Como parte del CEIP para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], van a compartir los siguientes datos con Microsoft:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-237">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="f9ea1-238">El hardware del equipo en el que va a instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-238">The computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="f9ea1-239">Las versiones de SQL Server que usa para conectarse mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-239">The SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="f9ea1-240">Para inscribirse en CEIP, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-240">To enroll for CEIP, run the following command:</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
    ```  
  
     <span data-ttu-id="f9ea1-241">De forma predeterminada, la opción es false.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-241">By default, the option is false.</span></span>  
  
     <span data-ttu-id="f9ea1-242">Para obtener más información sobre la `msiexec` de comandos, escriba `msiexec` en la línea de comandos y presione `ENTER`, o vea [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-242">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a><span data-ttu-id="f9ea1-243">Tareas posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="f9ea1-243">Post-installation tasks</span></span>  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a><span data-ttu-id="f9ea1-244">Registrar los enlaces</span><span class="sxs-lookup"><span data-stu-id="f9ea1-244">Register the bindings</span></span>  
<span data-ttu-id="f9ea1-245">Siga estos pasos *sólo* si se produce un error en el Asistente para instalación registrar los enlaces del adaptador en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-245">Complete these steps *only* if the setup wizard fails to register the adapter bindings in the machine.config file.</span></span>  
  
1.  <span data-ttu-id="f9ea1-246">Navegue hasta el archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-246">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="f9ea1-247">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidad del sistema >: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-247">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
2.  <span data-ttu-id="f9ea1-248">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-248">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="f9ea1-249">Para registrar los enlaces del adaptador:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-249">To register the adapter bindings:</span></span>  
  
    1.  <span data-ttu-id="f9ea1-250">Busque el elemento "system.serviceModel" y agregue lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-250">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="f9ea1-251">Busque el elemento "bindingElementExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-251">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="f9ea1-252">Agregue la siguiente sección bajo el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="f9ea1-252">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="f9ea1-253">Para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-253">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="f9ea1-254">Busque el elemento "bindingExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-254">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="f9ea1-255">Agregue la siguiente sección bajo el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="f9ea1-255">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="f9ea1-256">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-256">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f9ea1-257">Para obtener información sobre cómo determinar la clave pública, consulte [determinar la clave pública y la versión](#BKMK_PubKey).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-257">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="f9ea1-258">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-258">Save and close the machine.config file.</span></span>  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a><span data-ttu-id="f9ea1-259">Determinar la versión y la clave pública</span><span class="sxs-lookup"><span data-stu-id="f9ea1-259">Determining the Public Key and Version</span></span>  
<span data-ttu-id="f9ea1-260">Complete los pasos siguientes para determinar la clave pública y la versión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-260">Complete the following steps to determine the public key and version for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="f9ea1-261">Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-261">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="f9ea1-262">Haga clic en el archivo DLL para el que desea que la clave pública y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-262">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="f9ea1-263">En la tabla siguiente muestra el nombre de los archivos DLL para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-263">The following table lists the name of the DLLs for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    |<span data-ttu-id="f9ea1-264">Adaptador</span><span class="sxs-lookup"><span data-stu-id="f9ea1-264">Adapter</span></span>|<span data-ttu-id="f9ea1-265">Nombre de la DLL</span><span class="sxs-lookup"><span data-stu-id="f9ea1-265">Name of the DLL</span></span>|  
    |---|---|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|<span data-ttu-id="f9ea1-266">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="f9ea1-266">Microsoft.Adapters.Sql.dll</span></span>|  
  
3.  <span data-ttu-id="f9ea1-267">En el **General** pestaña, el valor en el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-267">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="f9ea1-268">De forma similar, el valor en el **versión** etiqueta Especifica el número de versión para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-268">Similarly, the value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="f9ea1-269">Copie la clave pública y, a continuación, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-269">Copy the public key, and then click **Cancel**.</span></span>  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a><span data-ttu-id="f9ea1-270">Actualizar o cambiar la instalación del adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="f9ea1-270">Update or change the SQL adapter installation</span></span>  
 <span data-ttu-id="f9ea1-271">Realice los pasos siguientes para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-271">Perform the following steps to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span> <span data-ttu-id="f9ea1-272">Asegúrese de que tiene la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalado antes de ejecutar el Asistente para la instalación para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-272">Make sure you have the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span>  
  
 <span data-ttu-id="f9ea1-273">Puede modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-273">You can modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the following two ways:</span></span>  
  
-   <span data-ttu-id="f9ea1-274">**En el modo interactivo** ejecutando el Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-274">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="f9ea1-275">**En modo silencioso** mediante el uso de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-275">**In silent mode** by using the command line.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a><span data-ttu-id="f9ea1-276">Actualizar la instalación del adaptador de SQL en modo interactivo</span><span class="sxs-lookup"><span data-stu-id="f9ea1-276">Update the SQL Adapter installation in interactive mode</span></span>  
  
1.  <span data-ttu-id="f9ea1-277">Haga clic en **iniciar**y, a continuación, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-277">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="f9ea1-278">En el Panel de Control, haga doble clic en **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-278">In Control Panel, double-click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="f9ea1-279">En el **programas y características** ventana, seleccione **Microsoft BizTalk Adapter para SQL Server**y, a continuación, haga clic en **cambio**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-279">In the **Programs and Features** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Change**.</span></span>  
  
4.  <span data-ttu-id="f9ea1-280">Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-280">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="f9ea1-281">En el **cambiar, reparar o quitar instalación** cuadro de diálogo, haga clic en **reparar**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-281">In the **Change, repair, or remove installation** dialog box, click **Repair**.</span></span>  
  
6.  <span data-ttu-id="f9ea1-282">En el **preparado para reparar Microsoft BizTalk Adapter para SQL Server** cuadro de diálogo, haga clic en **reparar**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-282">In the **Ready to repair Microsoft BizTalk Adapter for SQL Server** dialog box, click **Repair**.</span></span>  
  
7.  <span data-ttu-id="f9ea1-283">Si es necesario, cambie las preferencias en relación con la aceptación de CEIP y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-283">If required, change your preferences regarding opting for CEIP, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="f9ea1-284">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-284">Click **Finish**.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a><span data-ttu-id="f9ea1-285">Actualizar la instalación del adaptador de SQL en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="f9ea1-285">Update the SQL Adapter installation in silent mode</span></span>  
  
1.  <span data-ttu-id="f9ea1-286">Abra un símbolo del sistema y navegue hasta el directorio raíz de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalador.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-286">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="f9ea1-287">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-287">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9ea1-288">Para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación en modo silencioso en una plataforma basada en x64, en los siguientes comandos, reemplace SqlAdapterSetup.msi por SqlAdapterSetup64.msi.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-288">To modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn /f  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f9ea1-289">Al modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación en modo silencioso, no se puede cambiar sus preferencias para participar o excluir el CEIP.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-289">While modifying the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="f9ea1-290">Las preferencias de seguirá siendo el mismo que especificó durante la instalación, incluso si se establece explícitamente el CEIP_OPTIN en true o false.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-290">The preferences will remain the same as you specified during the installation, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  
  
     <span data-ttu-id="f9ea1-291">Para obtener más información sobre la `msiexec` tipo de comando `msiexec` en la línea de comandos y presione `ENTER`, o vea [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-291">For more information about the `msiexec` command type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a><span data-ttu-id="f9ea1-292">Desinstale o quite el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="f9ea1-292">Uninstall or remove the SQL Adapter</span></span>  
 <span data-ttu-id="f9ea1-293">Realice los pasos siguientes para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] desde su equipo.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-293">Perform the following steps to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from your computer.</span></span> <span data-ttu-id="f9ea1-294">Asegúrese de que tiene la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalado antes de ejecutar el Asistente para la instalación para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-294">Make sure you have the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="f9ea1-295">Puede quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-295">You can remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="f9ea1-296">**En el modo interactivo** ejecutando el Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-296">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="f9ea1-297">**En modo silencioso** mediante el uso de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-297">**In silent mode** by using the command line.</span></span>  
  
#### <a name="uninstall-the-sql-adapter-in-interactive-mode"></a><span data-ttu-id="f9ea1-298">Desinstalar el adaptador de SQL en modo interactivo</span><span class="sxs-lookup"><span data-stu-id="f9ea1-298">Uninstall the SQL Adapter in interactive mode</span></span>  
  
1.  <span data-ttu-id="f9ea1-299">Haga clic en **iniciar**y, a continuación, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-299">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="f9ea1-300">En el Panel de Control, haga doble clic en **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-300">In Control Panel, double-click  **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="f9ea1-301">En el **agregar o quitar programas** ventana, seleccione **Microsoft BizTalk Adapter para SQL Server**y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-301">In the **Add or Remove Programs** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="f9ea1-302">En el cuadro de diálogo, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-302">In the dialog box, click **Yes**.</span></span>  
  
#### <a name="uninstall-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="f9ea1-303">Desinstalar el adaptador de SQL en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="f9ea1-303">Uninstall the SQL Adapter in silent mode</span></span>  
  
1.  <span data-ttu-id="f9ea1-304">Abra un símbolo del sistema y navegue hasta el directorio raíz de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalador.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-304">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="f9ea1-305">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-305">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9ea1-306">Para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en modo silencioso en una plataforma basada en x64, en los siguientes comandos, reemplace SqlAdapterSetup.msi por SqlAdapterSetup64.msi.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-306">To remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /x SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="f9ea1-307">Este comando quita el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] desde el equipo.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-307">This command removes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from the computer.</span></span>  
  
     <span data-ttu-id="f9ea1-308">Para obtener más información sobre la `msiexec` de comandos, escriba `msiexec` en la línea de comandos y presione `ENTER`, o vea [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span><span class="sxs-lookup"><span data-stu-id="f9ea1-308">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a><span data-ttu-id="f9ea1-309">Tarea posterior a la desinstalación</span><span class="sxs-lookup"><span data-stu-id="f9ea1-309">Post-uninstall task</span></span>  
 <span data-ttu-id="f9ea1-310">Si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] el programa de instalación no puede quitar los enlaces del adaptador al quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], debe quitarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-310">If the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] setup fails to remove the adapter bindings while removing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must remove them manually.</span></span> <span data-ttu-id="f9ea1-311">La siguiente sección describe cómo quitar manualmente los enlaces para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ea1-311">The following section describes how to manually remove the bindings for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
<span data-ttu-id="f9ea1-312">Siga estos pasos *sólo* si se produce un error en el Asistente para la instalación quitar los enlaces del adaptador desde el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-312">Complete these steps *only* if the setup wizard fails to remove the adapter bindings from the machine.config file.</span></span>  
  
1.  <span data-ttu-id="f9ea1-313">Navegue hasta el archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-313">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="f9ea1-314">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidad del sistema >: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-314">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    -   <span data-ttu-id="f9ea1-315">Microsoft .NET Framework 3.5 SP1, \< *versión*> es el v2.0.50727 de versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-315">For Microsoft .NET Framework 3.5 SP1, \<*version*> is the version v2.0.50727 of the .NET Framework.</span></span>  
  
    -   <span data-ttu-id="f9ea1-316">Para Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \< *versión*> es el v4.0.30319 de versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-316">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*> is the version v4.0.30319 of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="f9ea1-317">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-317">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="f9ea1-318">Para quitar el registro de enlace del adaptador:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-318">To remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="f9ea1-319">Busque el elemento "system.serviceModel" y extraiga los siguientes elementos desde el elemento:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-319">Search for the element "system.serviceModel" and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="f9ea1-320">Busque el elemento "bindingElementExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-320">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="f9ea1-321">Quite la siguiente sección bajo el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="f9ea1-321">Remove the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="f9ea1-322">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-322">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="f9ea1-323">Busque el elemento "bindingExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-323">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="f9ea1-324">Quite la siguiente sección bajo el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="f9ea1-324">Remove the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="f9ea1-325">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="f9ea1-325">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="f9ea1-326">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="f9ea1-326">Save and close the machine.config file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ea1-327">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9ea1-327">See also</span></span>
[<span data-ttu-id="f9ea1-328">Instalar al adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="f9ea1-328">Install the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[<span data-ttu-id="f9ea1-329">Comprender el adaptador de BizTalk para SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9ea1-329">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)