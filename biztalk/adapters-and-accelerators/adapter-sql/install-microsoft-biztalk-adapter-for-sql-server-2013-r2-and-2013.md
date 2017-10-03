---
title: Instalar el adaptador de Microsoft BizTalk para SQL Server R2 2013 y 2013 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56c31d0d-783b-41ee-8265-56c9547e9dca
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c88c044aa9c0454262427760829af5af1d69b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2013-r2-and-2013"></a><span data-ttu-id="e6e41-102">Instalar al adaptador de Microsoft BizTalk para SQL Server R2 2013 y 2013</span><span class="sxs-lookup"><span data-stu-id="e6e41-102">Install Microsoft BizTalk Adapter for SQL Server - 2013 R2 and 2013</span></span>
<span data-ttu-id="e6e41-103">Instalar el [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] incluido con [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)], o está incluido con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 2013.</span><span class="sxs-lookup"><span data-stu-id="e6e41-103">Install the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] included with [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)], or included with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 2013.</span></span>

 <span data-ttu-id="e6e41-104">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se puede usar con:</span><span class="sxs-lookup"><span data-stu-id="e6e41-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used with:</span></span>  
  
-   <span data-ttu-id="e6e41-105">Una aplicación .NET</span><span class="sxs-lookup"><span data-stu-id="e6e41-105">A .NET application</span></span>  
  
-   <span data-ttu-id="e6e41-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6e41-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
 <span data-ttu-id="e6e41-107">En función de cómo usar los adaptadores, que varía según el software necesario.</span><span class="sxs-lookup"><span data-stu-id="e6e41-107">Based on how you use the adapters, the required software varies.</span></span>  
 
<a name="BKMK_Prereqs_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a><span data-ttu-id="e6e41-108">Requisitos previos para configurar el adaptador con una aplicación .NET</span><span class="sxs-lookup"><span data-stu-id="e6e41-108">Prerequisites when using the adapter with a .NET Application</span></span>  
<span data-ttu-id="e6e41-109">Instalar el software siguiente en el equipo donde está escribiendo aplicaciones .NET que usen el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-109">Install the following software on the computer where you are writing .NET applications that consume the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="e6e41-110">Instalar el software en el orden en que se muestran.</span><span class="sxs-lookup"><span data-stu-id="e6e41-110">Install the software in the order as listed.</span></span>  

|<span data-ttu-id="e6e41-111">2013 R2</span><span class="sxs-lookup"><span data-stu-id="e6e41-111">2013 R2</span></span>|<span data-ttu-id="e6e41-112">2013</span><span class="sxs-lookup"><span data-stu-id="e6e41-112">2013</span></span>|  
|---|---|  
|[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]|<span data-ttu-id="e6e41-113">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6e41-113">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="e6e41-114">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="e6e41-114">Visual Studio 2013</span></span>|<span data-ttu-id="e6e41-115">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="e6e41-115">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|  
|<span data-ttu-id="e6e41-116">Las bibliotecas de cliente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6e41-116">The SQL Server client libraries.</span></span> <span data-ttu-id="e6e41-117">.</span><span class="sxs-lookup"><span data-stu-id="e6e41-117">.</span></span>|<span data-ttu-id="e6e41-118">Las bibliotecas de cliente de SQL Server...</span><span class="sxs-lookup"><span data-stu-id="e6e41-118">The SQL Server client libraries..</span></span>|  

<a name="BKMK_Prereqs_BTS"></a>    
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="e6e41-119">Requisitos previos para configurar el adaptador con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e6e41-119">Prerequisites when using the adapter with BizTalk Server</span></span>  
<span data-ttu-id="e6e41-120">Instalar el software siguiente en el equipo donde va a usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-120">Install the following software on the computer where you will be using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e6e41-121">Se recomienda instalar el software en el mismo orden que se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="e6e41-121">We recommend installing the software in the same order as listed here.</span></span>  
 
 |<span data-ttu-id="e6e41-122">2013 R2</span><span class="sxs-lookup"><span data-stu-id="e6e41-122">2013 R2</span></span>|<span data-ttu-id="e6e41-123">2013</span><span class="sxs-lookup"><span data-stu-id="e6e41-123">2013</span></span>|  
|---|---|  
|[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]|<span data-ttu-id="e6e41-124">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6e41-124">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="e6e41-125">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="e6e41-125">Visual Studio 2013</span></span>|<span data-ttu-id="e6e41-126">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="e6e41-126">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="e6e41-127">Instalar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] incluido con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-127">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="e6e41-128">Para instalar, realice una **personalizado** (seleccione **complemento de BizTalk Server**) o **completar** instalación de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-128">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="e6e41-129">Instalar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] incluido con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-129">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="e6e41-130">Para instalar, realice una **personalizado** (seleccione **complemento de BizTalk Server**) o **completar** instalación de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-130">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|  
|<span data-ttu-id="e6e41-131">BizTalk Server 2013 R2</span><span class="sxs-lookup"><span data-stu-id="e6e41-131">BizTalk Server 2013 R2</span></span>|<span data-ttu-id="e6e41-132">BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6e41-132">BizTalk Server 2013</span></span>|  
|<span data-ttu-id="e6e41-133">Las bibliotecas de cliente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6e41-133">The SQL Server client libraries.</span></span> |<span data-ttu-id="e6e41-134">Las bibliotecas de cliente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6e41-134">The SQL Server client libraries.</span></span> |  

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a><span data-ttu-id="e6e41-135">Versiones admitidas de SQL Server y las bibliotecas de cliente</span><span class="sxs-lookup"><span data-stu-id="e6e41-135">Supported SQL Server versions and client libraries</span></span>  
 <span data-ttu-id="e6e41-136">En la siguiente sección presenta las versiones admitidas de SQL Server y el cliente de bibliotecas requeridas por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-136">The following section presents the supported SQL Server versions and the client libraries required by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="e6e41-137">**Versiones de servidor admitidas**: SQL Server 2005, SQL Server 2008 SP1, SQL Server 2008 R2, SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="e6e41-137">**Supported server versions**: SQL Server 2005, SQL Server 2008 SP1, SQL Server 2008 R2, SQL Server 2012</span></span>  
  
-   <span data-ttu-id="e6e41-138">**Admite versiones de cliente**: Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] agrupaciones de lo archivos DLL de cliente necesaria para conectarse a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6e41-138">**Supported client versions**: Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] bundles the client DLLs required to connect to SQL Server.</span></span> <span data-ttu-id="e6e41-139">No es necesario instalar explícitamente cualquier cliente de DLL en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e6e41-139">You do not need to explicitly install any client DLLs on your computer.</span></span>  
  
-   <span data-ttu-id="e6e41-140">**Controladores necesarios**:</span><span class="sxs-lookup"><span data-stu-id="e6e41-140">**Required drivers**:</span></span>  
  
    -   <span data-ttu-id="e6e41-141">Si usa los UDT incluidos con las versiones de SQL Server, por ejemplo, Geography, asegúrese de que los archivos DLL siguientes están presentes en el equipo donde se usa el adaptador para realizar operaciones en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6e41-141">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="e6e41-142">Por ejemplo, si crea proyectos de BizTalk para realizar operaciones en SQL Server, estos archivos DLL deben estar presentes en el equipo donde se está ejecutando el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e6e41-142">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  
  
        -   <span data-ttu-id="e6e41-143">Asegúrese de que Microsoft.SqlServer.Types.dll se agrega a la GAC.</span><span class="sxs-lookup"><span data-stu-id="e6e41-143">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  
  
        -   <span data-ttu-id="e6e41-144">Asegúrese de que SqlServerSpatial.dll está disponible en la carpeta System32.</span><span class="sxs-lookup"><span data-stu-id="e6e41-144">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>  
  
         <span data-ttu-id="e6e41-145">Puede instalar estos archivos DLL en el equipo ejecutando el programa de instalación de SQL Server y seleccionando **herramientas de administración – básica** y **herramientas de administración – completa** en la **selección de características**página del asistente.</span><span class="sxs-lookup"><span data-stu-id="e6e41-145">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>  
  
    -   <span data-ttu-id="e6e41-146">Si usa el adaptador para realizar operaciones en columnas de tipos de datos FILESTREAM, asegúrese de que tiene instalado el SDK de conectividad de cliente de SQL.</span><span class="sxs-lookup"><span data-stu-id="e6e41-146">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="e6e41-147">Puede instalar el SDK de conectividad de cliente de SQL, ejecute el programa de instalación de SQL Server y seleccionar **SDK de conectividad de cliente de SQL** en el **selección de características** página del asistente.</span><span class="sxs-lookup"><span data-stu-id="e6e41-147">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="e6e41-148">El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e6e41-148">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  
  
    -   <span data-ttu-id="e6e41-149">Si crea su propio UDT en SQL Server, asegúrese de que los ensamblados correspondientes para los UDT se agregan a la GAC.</span><span class="sxs-lookup"><span data-stu-id="e6e41-149">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  
  
<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a><span data-ttu-id="e6e41-150">Compatibilidad con 64 bits</span><span class="sxs-lookup"><span data-stu-id="e6e41-150">64-bit support</span></span> 

<span data-ttu-id="e6e41-151">La [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede ejecutar en una instancia de host de 32 bits o 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e6e41-151">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can run in a 32-bit or 64-bit host instance.</span></span>

 <span data-ttu-id="e6e41-152">Para obtener más información acerca de los escenarios de instalación admitidos para las 32 bits y 64 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)],.</span><span class="sxs-lookup"><span data-stu-id="e6e41-152">For more information about the supported installation scenarios for the 32-bit and 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)],.</span></span> 
  
<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a><span data-ttu-id="e6e41-153">Instalar al adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="e6e41-153">Install the SQL Adapter</span></span>  
 <span data-ttu-id="e6e41-154">Asegúrese de que tiene los requisitos previos instalados antes de instalar la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-154">Make sure you have the prerequisites installed before installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="e6e41-155">Puede instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6e41-155">You can install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="e6e41-156">**En el modo interactivo** mediante el Asistente para la instalación</span><span class="sxs-lookup"><span data-stu-id="e6e41-156">**In interactive mode** using the setup wizard</span></span>  
  
-   <span data-ttu-id="e6e41-157">**En modo silencioso** mediante msiexec en el comando lin</span><span class="sxs-lookup"><span data-stu-id="e6e41-157">**In silent mode** using msiexec in the command lin</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e6e41-158">Debe tener privilegios administrativos en el equipo donde instalará el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], independientemente de si va a instalar mediante el asistente o la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e6e41-158">You must have administrative privileges on the computer where you will install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], irrespective of whether you are installing by using the wizard or the command line.</span></span>  
  
<a name="BKMK_Install_Scenarios"></a>   
### <a name="32-bit-and-64-bit-install-scenarios"></a><span data-ttu-id="e6e41-159">escenarios de instalación de 32 bits y 64 bits</span><span class="sxs-lookup"><span data-stu-id="e6e41-159">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="e6e41-160">Con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede utilizarse para:</span><span class="sxs-lookup"><span data-stu-id="e6e41-160">With [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used for:</span></span>  
  
-   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="e6e41-161">tiempo de diseño (cuándo generar metadatos para operaciones).</span><span class="sxs-lookup"><span data-stu-id="e6e41-161"> design time (when generating metadata for operations).</span></span>  
  
-   <span data-ttu-id="e6e41-162">Tiempo de diseño de consola de administración de BizTalk Server (para la creación de puertos físicos).</span><span class="sxs-lookup"><span data-stu-id="e6e41-162">BizTalk Server Administration console design time (for creating physical ports).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6e41-163">Consola de administración de BizTalk Server se ejecuta como una aplicación de Microsoft Management Console (MMC) de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="e6e41-163">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="e6e41-164">Tiempo de ejecución de BizTalk (al enviar y recibir mensajes desde aplicaciones de LOB).</span><span class="sxs-lookup"><span data-stu-id="e6e41-164">BizTalk run time (when sending and receiving messages from LOB applications).</span></span>  
  
 <span data-ttu-id="e6e41-165">Puede tener una instalación donde realizar todas estas tareas en el mismo equipo o en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="e6e41-165">You can have an installation where you perform all these tasks on the same computer or different computers.</span></span> <span data-ttu-id="e6e41-166">Dado que ambos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y MMC de BizTalk son procesos de 32 bits, debe instalar el 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en el equipo donde desea realizar las tareas de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="e6e41-166">Because both [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on the computer where you want to perform the design-time tasks.</span></span> <span data-ttu-id="e6e41-167">Se admiten los escenarios siguientes para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en plataformas de 32 bits y 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e6e41-167">The following scenarios are supported for installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on 32-bit and 64-bit platforms.</span></span>  
  
#### <a name="install-scenarios-on-a-32-bit-platform"></a><span data-ttu-id="e6e41-168">Instalar los escenarios en una plataforma de 32 bits</span><span class="sxs-lookup"><span data-stu-id="e6e41-168">Install scenarios on a 32-bit platform</span></span>  
 <span data-ttu-id="e6e41-169">Se admiten los siguientes escenarios cuando se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una plataforma de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="e6e41-169">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 32-bit platform.</span></span>  
  
|<span data-ttu-id="e6e41-170">Tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e6e41-170">Visual Studio design time</span></span>|<span data-ttu-id="e6e41-171">Tiempo de diseño de MMC de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e6e41-171">BizTalk MMC design time</span></span>|<span data-ttu-id="e6e41-172">Tiempo de ejecución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e6e41-172">BizTalk run time</span></span>|<span data-ttu-id="e6e41-173">Tiempo de ejecución de Visual tiempo de diseño de Studio o tiempo de diseño de BizTalk MMC + BizTalk</span><span class="sxs-lookup"><span data-stu-id="e6e41-173">Visual Studio design time and/or  BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="e6e41-174">-Instalar 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-174">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-175">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-175">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-176">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-176">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="e6e41-177">-Instalar 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-177">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-178">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-178">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-179">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-179">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="e6e41-180">-Instalar 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-180">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-181">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-181">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-182">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-182">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="e6e41-183">-Instalar 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-183">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-184">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-184">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-185">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-185">- Install 32-bit client and other required DLLs.</span></span>|  
  
#### <a name="install-scenarios-on-a-64-bit-platform"></a><span data-ttu-id="e6e41-186">Instalar los escenarios en una plataforma de 64 bits</span><span class="sxs-lookup"><span data-stu-id="e6e41-186">Install scenarios on a 64-bit platform</span></span>  
 <span data-ttu-id="e6e41-187">Se admiten los siguientes escenarios cuando se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e6e41-187">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 64-bit platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6e41-188">En cualquier equipo donde desea realizar tareas de tiempo de diseño mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o MMC de BizTalk, debe instalar lo 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-188">On any computer where you want to perform design-time tasks using either [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
|<span data-ttu-id="e6e41-189">Tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e6e41-189">Visual Studio design time</span></span>|<span data-ttu-id="e6e41-190">Tiempo de diseño de MMC de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e6e41-190">BizTalk MMC design time</span></span>|<span data-ttu-id="e6e41-191">Tiempo de ejecución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e6e41-191">BizTalk run time</span></span>|<span data-ttu-id="e6e41-192">Tiempo de ejecución de Visual tiempo de diseño de Studio o tiempo de diseño de BizTalk MMC + BizTalk</span><span class="sxs-lookup"><span data-stu-id="e6e41-192">Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="e6e41-193">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-193">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-194">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-194">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-195">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-195">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="e6e41-196">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-196">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-197">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-197">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-198">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-198">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="e6e41-199">**Para un proceso de BizTalk de 32 bits**:</span><span class="sxs-lookup"><span data-stu-id="e6e41-199">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="e6e41-200">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-200">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-201">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-201">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-202">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-202">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="e6e41-203">**Para un proceso de BizTalk de 64 bits**:</span><span class="sxs-lookup"><span data-stu-id="e6e41-203">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="e6e41-204">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-204">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-205">-Instalar 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-205">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-206">-Instalar el cliente de 64 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-206">- Install 64-bit client and other required DLLs.</span></span>|<span data-ttu-id="e6e41-207">**Para un proceso de BizTalk de 32 bits**:</span><span class="sxs-lookup"><span data-stu-id="e6e41-207">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="e6e41-208">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-208">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-209">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-209">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-210">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-210">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="e6e41-211">**Para un proceso de BizTalk de 64 bits**:</span><span class="sxs-lookup"><span data-stu-id="e6e41-211">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="e6e41-212">-Instalar 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-212">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-213">-Instalar 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-213">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-214">-Instalar el cliente de 64 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-214">- Install 64-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="e6e41-215">-Instalar 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-215">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="e6e41-216">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6e41-216">- Install 32-bit client and other required DLLs.</span></span>|  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-sql-adapter-in-interactive-mode"></a><span data-ttu-id="e6e41-217">Instalar al adaptador de SQL en modo interactivo</span><span class="sxs-lookup"><span data-stu-id="e6e41-217">Install the SQL Adapter in interactive mode</span></span>  
 
1.  <span data-ttu-id="e6e41-218">Ejecute al instalador.</span><span class="sxs-lookup"><span data-stu-id="e6e41-218">Run the installer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6e41-219">Si va a instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una máquina virtual, el Asistente para la instalación no puede continuar más allá de un cuadro de diálogo que le informa de que el programa de instalación comprueba si hay espacio disponible en disco.</span><span class="sxs-lookup"><span data-stu-id="e6e41-219">If you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="e6e41-220">En tales casos, se recomienda que utilice la opción de instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="e6e41-220">In such cases, we recommend that you use the silent installation option.</span></span>   
  
2.  <span data-ttu-id="e6e41-221">Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-221">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="e6e41-222">Lea y acepte el contrato de licencia para el usuario final (CLUF) y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-222">Read and accept the end-user license agreement (EULA), and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="e6e41-223">En el **carpeta de destino** diálogo cuadro, especifique la ubicación donde desea instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], haga clic en **siguiente**y, a continuación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-223">In the **Destination Folder** dialog box, specify the location where you want to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], click **Next**, and then click **Install**.</span></span>  
  
5.  <span data-ttu-id="e6e41-224">En el **Customer Experience Improvement Program** cuadro de diálogo, especifique si desea inscribir para el programa para la mejora de la experiencia del usuario (CEIP).</span><span class="sxs-lookup"><span data-stu-id="e6e41-224">In the **Customer Experience Improvement Program** dialog box, specify whether you would like to enroll for the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="e6e41-225">Como parte del CEIP para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], van a compartir los siguientes datos con Microsoft:</span><span class="sxs-lookup"><span data-stu-id="e6e41-225">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="e6e41-226">Datos relacionados con el hardware del equipo en el que va a instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-226">Data related to the computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="e6e41-227">Datos relacionados con las versiones de SQL Server que usa para conectarse mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-227">Data related to the SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="e6e41-228">Especifique la elección y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-228">Specify your choice and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6e41-229">Siempre puede cambiar su preferencia con respecto a inscribirse en CEIP ejecutando el programa de instalación en modo de reparación desde el Panel de Control.</span><span class="sxs-lookup"><span data-stu-id="e6e41-229">You can always change your preference regarding enrolling for CEIP by running the Setup in Repair mode from the Control Panel.</span></span>  
  
6.  <span data-ttu-id="e6e41-230">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-230">Click **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="e6e41-231">Instalar al adaptador de SQL en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="e6e41-231">Install the SQL adapter in Silent mode</span></span>  
 <span data-ttu-id="e6e41-232">El siguiente procedimiento muestra cómo realizar una instalación silenciosa de [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante el `msiexec` comando.</span><span class="sxs-lookup"><span data-stu-id="e6e41-232">The following procedure demonstrates how to perform a silent installation of [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the `msiexec` command.</span></span>  
  
1.  <span data-ttu-id="e6e41-233">Abra un símbolo del sistema y navegue hasta la carpeta donde haya el instalador.</span><span class="sxs-lookup"><span data-stu-id="e6e41-233">Open a command prompt, and navigate to the folder where you have the installer.</span></span>  
  
2.  <span data-ttu-id="e6e41-234">Ejecute el siguiente comando para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e6e41-234">Run the following command to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6e41-235">Para llevar a cabo una instalación silenciosa en una plataforma basada en x64, en los siguientes comandos, reemplace SqlAdapterSetup.msi por SqlAdapterSetup64.msi.</span><span class="sxs-lookup"><span data-stu-id="e6e41-235">To perform silent installation on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="e6e41-236">También puede elegir para inscribirse en CEIP como parte de la instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="e6e41-236">You can also choose to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="e6e41-237">Como parte del CEIP para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], van a compartir los siguientes datos con Microsoft:</span><span class="sxs-lookup"><span data-stu-id="e6e41-237">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="e6e41-238">El hardware del equipo en el que va a instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-238">The computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="e6e41-239">Las versiones de SQL Server que usa para conectarse mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-239">The SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="e6e41-240">Para inscribirse en CEIP, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e6e41-240">To enroll for CEIP, run the following command:</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
    ```  
  
     <span data-ttu-id="e6e41-241">De forma predeterminada, la opción es false.</span><span class="sxs-lookup"><span data-stu-id="e6e41-241">By default, the option is false.</span></span>  
  
     <span data-ttu-id="e6e41-242">Para obtener más información sobre la `msiexec` de comandos, escriba `msiexec` en la línea de comandos y presione `ENTER`, o vea [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span><span class="sxs-lookup"><span data-stu-id="e6e41-242">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a><span data-ttu-id="e6e41-243">Tareas posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="e6e41-243">Post-installation tasks</span></span>  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a><span data-ttu-id="e6e41-244">Registrar los enlaces</span><span class="sxs-lookup"><span data-stu-id="e6e41-244">Register the Bindings</span></span>  
<span data-ttu-id="e6e41-245">Siga estos pasos *sólo* si se produce un error en el Asistente para instalación registrar los enlaces del adaptador en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="e6e41-245">Complete these steps *only* if the setup wizard fails to register the adapter bindings in the machine.config file.</span></span>  
  
1.  <span data-ttu-id="e6e41-246">Navegue hasta el archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e6e41-246">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="e6e41-247">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidad del sistema >: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="e6e41-247">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    -   <span data-ttu-id="e6e41-248">Microsoft .NET Framework 3.5 SP1, \< *versión*> es el v2.0.50727 de versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6e41-248">For Microsoft .NET Framework 3.5 SP1, \<*version*> is the version v2.0.50727 of the .NET Framework.</span></span>  
  
    -   <span data-ttu-id="e6e41-249">Para Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \< *versión*> es el v4.0.30319 de versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6e41-249">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*> is the version v4.0.30319 of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="e6e41-250">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="e6e41-250">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="e6e41-251">Para registrar los enlaces del adaptador:</span><span class="sxs-lookup"><span data-stu-id="e6e41-251">To register the adapter bindings:</span></span>  
  
    1.  <span data-ttu-id="e6e41-252">Busque el elemento "system.serviceModel" y agregue lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="e6e41-252">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="e6e41-253">Busque el elemento "bindingElementExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="e6e41-253">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="e6e41-254">Agregue la siguiente sección bajo el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="e6e41-254">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="e6e41-255">Para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6e41-255">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="e6e41-256">Busque el elemento "bindingExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="e6e41-256">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="e6e41-257">Agregue la siguiente sección bajo el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="e6e41-257">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="e6e41-258">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6e41-258">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
      
  
4.  <span data-ttu-id="e6e41-259">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="e6e41-259">Save and close the machine.config file.</span></span>  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a><span data-ttu-id="e6e41-260">Determinar la versión y la clave pública</span><span class="sxs-lookup"><span data-stu-id="e6e41-260">Determining the Public Key and Version</span></span>  
<span data-ttu-id="e6e41-261">Complete los pasos siguientes para determinar la clave pública y la versión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-261">Complete the following steps to determine the public key and version for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="e6e41-262">Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.</span><span class="sxs-lookup"><span data-stu-id="e6e41-262">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="e6e41-263">Haga clic en el archivo DLL para el que desea que la clave pública y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-263">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="e6e41-264">En la tabla siguiente muestra el nombre de los archivos DLL para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-264">The following table lists the name of the DLLs for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    |<span data-ttu-id="e6e41-265">Adaptador</span><span class="sxs-lookup"><span data-stu-id="e6e41-265">Adapter</span></span>|<span data-ttu-id="e6e41-266">Nombre de la DLL</span><span class="sxs-lookup"><span data-stu-id="e6e41-266">Name of the DLL</span></span>|  
    |---|---|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|<span data-ttu-id="e6e41-267">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="e6e41-267">Microsoft.Adapters.Sql.dll</span></span>|  
  
3.  <span data-ttu-id="e6e41-268">En el **General** pestaña, el valor en el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="e6e41-268">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="e6e41-269">De forma similar, el valor en el **versión** etiqueta Especifica el número de versión para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="e6e41-269">Similarly, the value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="e6e41-270">Copie la clave pública y, a continuación, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-270">Copy the public key, and then click **Cancel**.</span></span>  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a><span data-ttu-id="e6e41-271">Actualizar o cambiar la instalación del adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="e6e41-271">Update or change the SQL adapter installation</span></span>  
 <span data-ttu-id="e6e41-272">Realice los pasos siguientes para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="e6e41-272">Perform the following steps to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span> <span data-ttu-id="e6e41-273">Asegúrese de que tiene la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalado antes de ejecutar el Asistente para la instalación para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="e6e41-273">Make sure you have the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span>  
  
 <span data-ttu-id="e6e41-274">Puede modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6e41-274">You can modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the following two ways:</span></span>  
  
-   <span data-ttu-id="e6e41-275">**En el modo interactivo** ejecutando el Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="e6e41-275">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="e6e41-276">**En modo silencioso** mediante el uso de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e6e41-276">**In silent mode** by using the command line.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a><span data-ttu-id="e6e41-277">Actualizar la instalación del adaptador de SQL en modo interactivo</span><span class="sxs-lookup"><span data-stu-id="e6e41-277">Update the SQL Adapter installation in interactive mode</span></span>  
  
1.  <span data-ttu-id="e6e41-278">Haga clic en **iniciar**y, a continuación, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-278">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="e6e41-279">En el Panel de Control, haga doble clic en **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-279">In Control Panel, double-click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="e6e41-280">En el **programas y características** ventana, seleccione **Microsoft BizTalk Adapter para SQL Server**y, a continuación, haga clic en **cambio**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-280">In the **Programs and Features** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Change**.</span></span>  
  
4.  <span data-ttu-id="e6e41-281">Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-281">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="e6e41-282">En el **cambiar, reparar o quitar instalación** cuadro de diálogo, haga clic en **reparar**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-282">In the **Change, repair, or remove installation** dialog box, click **Repair**.</span></span>  
  
6.  <span data-ttu-id="e6e41-283">En el **preparado para reparar Microsoft BizTalk Adapter para SQL Server** cuadro de diálogo, haga clic en **reparar**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-283">In the **Ready to repair Microsoft BizTalk Adapter for SQL Server** dialog box, click **Repair**.</span></span>  
  
7.  <span data-ttu-id="e6e41-284">Si es necesario, cambie las preferencias en relación con la aceptación de CEIP y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-284">If required, change your preferences regarding opting for CEIP, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="e6e41-285">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-285">Click **Finish**.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a><span data-ttu-id="e6e41-286">Actualizar la instalación del adaptador de SQL en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="e6e41-286">Update the SQL Adapter installation in silent mode</span></span>  
  
1.  <span data-ttu-id="e6e41-287">Abra un símbolo del sistema y navegue hasta el directorio raíz de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalador.</span><span class="sxs-lookup"><span data-stu-id="e6e41-287">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="e6e41-288">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e6e41-288">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6e41-289">Para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación en modo silencioso en una plataforma basada en x64, en los siguientes comandos, reemplace SqlAdapterSetup.msi por SqlAdapterSetup64.msi.</span><span class="sxs-lookup"><span data-stu-id="e6e41-289">To modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn /f  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e6e41-290">Al modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación en modo silencioso, no se puede cambiar sus preferencias para participar o excluir el CEIP.</span><span class="sxs-lookup"><span data-stu-id="e6e41-290">While modifying the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="e6e41-291">Las preferencias de seguirá siendo el mismo que especificó durante la instalación, incluso si se establece explícitamente el CEIP_OPTIN en true o false.</span><span class="sxs-lookup"><span data-stu-id="e6e41-291">The preferences will remain the same as you specified during the installation, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  
  
     <span data-ttu-id="e6e41-292">Para obtener más información sobre la `msiexec` de comandos, escriba `msiexec` en la línea de comandos y presione `ENTER`, o vea [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span><span class="sxs-lookup"><span data-stu-id="e6e41-292">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>   
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a><span data-ttu-id="e6e41-293">Desinstale o quite el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="e6e41-293">Uninstall or remove the SQL Adapter</span></span>  
 <span data-ttu-id="e6e41-294">Realice los pasos siguientes para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] desde su equipo.</span><span class="sxs-lookup"><span data-stu-id="e6e41-294">Perform the following steps to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from your computer.</span></span> <span data-ttu-id="e6e41-295">Asegúrese de que tiene la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalado antes de ejecutar el Asistente para la instalación para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-295">Make sure you have the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="e6e41-296">Puede quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6e41-296">You can remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="e6e41-297">**En el modo interactivo** ejecutando el Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="e6e41-297">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="e6e41-298">**En modo silencioso** mediante el uso de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e6e41-298">**In silent mode** by using the command line.</span></span>  
  
#### <a name="uninstall-in-interactive-mode"></a><span data-ttu-id="e6e41-299">Desinstalar en modo interactivo</span><span class="sxs-lookup"><span data-stu-id="e6e41-299">Uninstall in interactive mode</span></span>  
  
1.  <span data-ttu-id="e6e41-300">Haga clic en **iniciar**y, a continuación, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-300">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="e6e41-301">En el Panel de Control, haga doble clic en **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-301">In Control Panel, double-click  **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="e6e41-302">En el **agregar o quitar programas** ventana, seleccione **Microsoft BizTalk Adapter para SQL Server**y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-302">In the **Add or Remove Programs** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="e6e41-303">En el cuadro de diálogo, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e6e41-303">In the dialog box, click **Yes**.</span></span>  
  
#### <a name="uninstall-in-silent-mode"></a><span data-ttu-id="e6e41-304">Desinstalar en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="e6e41-304">Uninstall in silent mode</span></span>  
  
1.  <span data-ttu-id="e6e41-305">Abra un símbolo del sistema y navegue hasta el directorio raíz de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalador.</span><span class="sxs-lookup"><span data-stu-id="e6e41-305">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="e6e41-306">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e6e41-306">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6e41-307">Para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en modo silencioso en una plataforma basada en x64, en los siguientes comandos, reemplace SqlAdapterSetup.msi por SqlAdapterSetup64.msi.</span><span class="sxs-lookup"><span data-stu-id="e6e41-307">To remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /x SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="e6e41-308">Este comando quita el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] desde el equipo.</span><span class="sxs-lookup"><span data-stu-id="e6e41-308">This command removes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from the computer.</span></span>  
  
     <span data-ttu-id="e6e41-309">Para obtener más información sobre la `msiexec` de comandos, escriba `msiexec` en la línea de comandos y presione `ENTER`, o vea [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span><span class="sxs-lookup"><span data-stu-id="e6e41-309">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a><span data-ttu-id="e6e41-310">Tarea posterior a la desinstalación</span><span class="sxs-lookup"><span data-stu-id="e6e41-310">Post-uninstall task</span></span>  
 <span data-ttu-id="e6e41-311">Si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] el programa de instalación no puede quitar los enlaces del adaptador al quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], debe quitarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="e6e41-311">If the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] setup fails to remove the adapter bindings while removing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must remove them manually.</span></span> <span data-ttu-id="e6e41-312">La siguiente sección describe cómo quitar manualmente los enlaces para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e41-312">The following section describes how to manually remove the bindings for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
<a name="BKMK_Remove_Binding"></a>   
#### <a name="manually-remove-the-bindings"></a><span data-ttu-id="e6e41-313">Quitar manualmente los enlaces</span><span class="sxs-lookup"><span data-stu-id="e6e41-313">Manually remove the bindings</span></span>  
 <span data-ttu-id="e6e41-314">Siga estos pasos *sólo* si se produce un error en el Asistente para la instalación quitar los enlaces del adaptador desde el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="e6e41-314">Perform these steps *only* if the setup wizard fails to remove the adapter bindings from the machine.config file.</span></span>  
  
1.  <span data-ttu-id="e6e41-315">Navegue hasta el archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e6e41-315">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="e6e41-316">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidad del sistema >: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="e6e41-316">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    -   <span data-ttu-id="e6e41-317">Microsoft .NET Framework 3.5 SP1, \< *versión*> es el v2.0.50727 de versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6e41-317">For Microsoft .NET Framework 3.5 SP1, \<*version*> is the version v2.0.50727 of the .NET Framework.</span></span>  
  
    -   <span data-ttu-id="e6e41-318">Para Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \< *versión*> es el v4.0.30319 de versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6e41-318">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*> is the version v4.0.30319 of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="e6e41-319">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="e6e41-319">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="e6e41-320">Para quitar el registro de enlace del adaptador:</span><span class="sxs-lookup"><span data-stu-id="e6e41-320">To remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="e6e41-321">Busque el elemento "system.serviceModel" y extraiga los siguientes elementos desde el elemento:</span><span class="sxs-lookup"><span data-stu-id="e6e41-321">Search for the element "system.serviceModel" and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="e6e41-322">Busque el elemento "bindingElementExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="e6e41-322">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="e6e41-323">Quite la siguiente sección bajo el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="e6e41-323">Remove the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="e6e41-324">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="e6e41-324">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="e6e41-325">Busque el elemento "bindingExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="e6e41-325">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="e6e41-326">Quite la siguiente sección bajo el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="e6e41-326">Remove the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="e6e41-327">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="e6e41-327">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="e6e41-328">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="e6e41-328">Save and close the machine.config file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e41-329">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6e41-329">See also</span></span>
[<span data-ttu-id="e6e41-330">Instalar al adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="e6e41-330">Install the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[<span data-ttu-id="e6e41-331">Comprender el adaptador de BizTalk para SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6e41-331">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)