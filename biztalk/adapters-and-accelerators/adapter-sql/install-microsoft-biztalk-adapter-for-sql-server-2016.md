---
title: Instalar el adaptador de Microsoft BizTalk para SQL Server - 2016 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcc6b94e-1cac-4b90-8567-05b33caa9bf3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65205828e4ab178a0fec29c37cc1854f6a570242
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966981"
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2016"></a><span data-ttu-id="3de28-102">Instalar al adaptador de Microsoft BizTalk para SQL Server - 2016</span><span class="sxs-lookup"><span data-stu-id="3de28-102">Install Microsoft BizTalk Adapter for SQL Server - 2016</span></span>
<span data-ttu-id="3de28-103">Instalar el [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] incluido con [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-103">Install the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] included with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span>

 <span data-ttu-id="3de28-104">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se puede usar con:</span><span class="sxs-lookup"><span data-stu-id="3de28-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used with:</span></span>  

- <span data-ttu-id="3de28-105">Una aplicación .NET</span><span class="sxs-lookup"><span data-stu-id="3de28-105">A .NET application</span></span>  

- <span data-ttu-id="3de28-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3de28-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>  

  <span data-ttu-id="3de28-107">En función de cómo usar los adaptadores, el software necesario varía.</span><span class="sxs-lookup"><span data-stu-id="3de28-107">Based on how you use the adapters, the required software varies.</span></span>  


<a name="BKMK_prereq_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a><span data-ttu-id="3de28-108">Requisitos previos al usar el adaptador con una aplicación .NET</span><span class="sxs-lookup"><span data-stu-id="3de28-108">Prerequisites when using the adapter with a .NET Application</span></span>  
<span data-ttu-id="3de28-109">Instalar el software siguiente en el equipo donde está escribiendo aplicaciones .NET que usen el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-109">Install the following software on the computer where you are writing .NET applications that consume the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3de28-110">Instalar el software en el orden, como se muestra.</span><span class="sxs-lookup"><span data-stu-id="3de28-110">Install the software in the order as listed.</span></span>  

||
|---|
|<span data-ttu-id="3de28-111">-Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3de28-111">- Windows Server 2016</span></span> <br /><span data-ttu-id="3de28-112">-Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3de28-112">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="3de28-113">-Windows 10</span><span class="sxs-lookup"><span data-stu-id="3de28-113">- Windows 10</span></span> <br /><span data-ttu-id="3de28-114">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3de28-114">- Windows 8.1</span></span>    |
|<span data-ttu-id="3de28-115">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="3de28-115">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="3de28-116">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="3de28-116">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|
|<span data-ttu-id="3de28-117">Bibliotecas de cliente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3de28-117">SQL Server client libraries.</span></span> <span data-ttu-id="3de28-118">Consulte la [versiones compatibles](#BKMK_SuppLOB) (en este tema).</span><span class="sxs-lookup"><span data-stu-id="3de28-118">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_prereq_BTS"></a>     
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="3de28-119">Requisitos previos al usar el adaptador con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3de28-119">Prerequisites when using the adapter with BizTalk Server</span></span>  
<span data-ttu-id="3de28-120">Instalar el software siguiente en el equipo donde se usa el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-120">Install the following software on the computer where you are using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3de28-121">Instalar el software en el orden mostrado.</span><span class="sxs-lookup"><span data-stu-id="3de28-121">Install the software in the order listed.</span></span>  

||
|---|
|<span data-ttu-id="3de28-122">-Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3de28-122">- Windows Server 2016</span></span> <br /><span data-ttu-id="3de28-123">-Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3de28-123">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="3de28-124">-Windows 10</span><span class="sxs-lookup"><span data-stu-id="3de28-124">- Windows 10</span></span> <br /><span data-ttu-id="3de28-125">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3de28-125">- Windows 8.1</span></span>    |
|<span data-ttu-id="3de28-126">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="3de28-126">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="3de28-127">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="3de28-127">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="3de28-128">Instalar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] incluido con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-128">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="3de28-129">Para instalar, realice una **personalizado** (seleccione **complemento de BizTalk Server**) o **completar** instalación de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-129">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|
|[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|
|<span data-ttu-id="3de28-130">Bibliotecas de cliente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3de28-130">SQL Server client libraries.</span></span> <span data-ttu-id="3de28-131">Consulte la [versiones compatibles](#BKMK_SuppLOB) (en este tema).</span><span class="sxs-lookup"><span data-stu-id="3de28-131">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a><span data-ttu-id="3de28-132">Versiones admitidas de SQL Server y las bibliotecas de cliente</span><span class="sxs-lookup"><span data-stu-id="3de28-132">Supported SQL Server versions and client libraries</span></span>  
 <span data-ttu-id="3de28-133">La siguiente sección presenta las versiones admitidas de SQL Server y el cliente de bibliotecas requeridas por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-133">The following section presents the supported SQL Server versions and the client libraries required by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

- <span data-ttu-id="3de28-134">**Versiones compatibles de server**: SQL Server 2016, SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="3de28-134">**Supported server versions**: SQL Server 2016, SQL Server 2014</span></span>

- <span data-ttu-id="3de28-135">**Admite las versiones de cliente**: Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] agrupaciones de lo archivos DLL de cliente necesaria para conectarse a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3de28-135">**Supported client versions**: Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] bundles the client DLLs required to connect to SQL Server.</span></span> <span data-ttu-id="3de28-136">No es necesario instalar explícitamente cualquier cliente de los archivos DLL en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3de28-136">You do not need to explicitly install any client DLLs on your computer.</span></span>  

- <span data-ttu-id="3de28-137">**Controladores necesarios**:</span><span class="sxs-lookup"><span data-stu-id="3de28-137">**Required drivers**:</span></span>  

  - <span data-ttu-id="3de28-138">Si usa los UDT se incluye con las versiones de SQL Server, por ejemplo, Geography, asegúrese de que los archivos DLL siguientes están presentes en el equipo donde se usa el adaptador para realizar operaciones en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3de28-138">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="3de28-139">Por ejemplo, si crea proyectos de BizTalk para realizar operaciones en SQL Server, estos archivos DLL deben estar presentes en el equipo donde se ejecuta BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3de28-139">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  

    - <span data-ttu-id="3de28-140">Asegúrese de que Microsoft.SqlServer.Types.dll se agrega a la GAC.</span><span class="sxs-lookup"><span data-stu-id="3de28-140">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  

    - <span data-ttu-id="3de28-141">Asegúrese de que SqlServerSpatial.dll está disponible en la carpeta System32.</span><span class="sxs-lookup"><span data-stu-id="3de28-141">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>  

      <span data-ttu-id="3de28-142">Puede instalar estos archivos DLL en el equipo ejecutando el programa de instalación de SQL Server y seleccionando **herramientas de administración – básica** y **herramientas de administración – completa** en la **selección de características**página del asistente.</span><span class="sxs-lookup"><span data-stu-id="3de28-142">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>  

  - <span data-ttu-id="3de28-143">Si usa el adaptador para realizar operaciones en las columnas de tipos de datos FILESTREAM, asegúrese de que tiene instalado el SDK de conectividad de cliente de SQL.</span><span class="sxs-lookup"><span data-stu-id="3de28-143">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="3de28-144">Puede instalar el SDK de conectividad de cliente de SQL, ejecute el programa de instalación de SQL Server y seleccione **SDK de conectividad de cliente SQL** en el **selección de características** página del asistente.</span><span class="sxs-lookup"><span data-stu-id="3de28-144">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="3de28-145">El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="3de28-145">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  

  - <span data-ttu-id="3de28-146">Si crea su propio UDT en SQL Server, asegúrese de que los ensamblados respectivos para los UDT se agregan a la GAC.</span><span class="sxs-lookup"><span data-stu-id="3de28-146">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  

<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a><span data-ttu-id="3de28-147">Compatibilidad con 64 bits</span><span class="sxs-lookup"><span data-stu-id="3de28-147">64-bit support</span></span> 

<span data-ttu-id="3de28-148">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede ejecutar en una instancia de host de 32 bits o 64 bits.</span><span class="sxs-lookup"><span data-stu-id="3de28-148">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can run in a 32-bit or 64-bit host instance.</span></span>

 <span data-ttu-id="3de28-149">Para obtener información acerca de los escenarios de instalación admitidos para los 32 bits y 64 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [escenarios de instalación de 32 bits y 64 bits](#BKMK_Install_Scenarios) (en este tema).</span><span class="sxs-lookup"><span data-stu-id="3de28-149">For information about the supported installation scenarios for the 32-bit and 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see  [32-bit and 64-bit install scenarios](#BKMK_Install_Scenarios) (in this topic).</span></span>

<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a><span data-ttu-id="3de28-150">Instalar al adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="3de28-150">Install the SQL adapter</span></span>  
 <span data-ttu-id="3de28-151">Asegúrese de que tiene los requisitos previos instalados antes de instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-151">Make sure you have the prerequisites installed before installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3de28-152">Consulte [requisitos previos de .NET](#BKMK_prereq_NET) (en este tema), o [requisitos previos de BizTalk Server](#BKMK_prereq_BTS) (en este tema).</span><span class="sxs-lookup"><span data-stu-id="3de28-152">See [.NET prerequisites](#BKMK_prereq_NET) (in this topic), or [BizTalk Server prerequisites](#BKMK_prereq_BTS) (in this topic).</span></span>

 <span data-ttu-id="3de28-153">Puede instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="3de28-153">You can install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  

- <span data-ttu-id="3de28-154">**En el modo interactivo** mediante el Asistente para instalación</span><span class="sxs-lookup"><span data-stu-id="3de28-154">**In interactive mode** using the setup wizard</span></span>

- <span data-ttu-id="3de28-155">**En modo silencioso** mediante msiexec en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="3de28-155">**In silent mode** using msiexec in the command line</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="3de28-156">Debe tener privilegios administrativos en el equipo donde se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], independientemente de si va a instalar mediante el asistente o la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3de28-156">You must have administrative privileges on the computer where you install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], irrespective of whether you are installing by using the wizard or the command line.</span></span>    

### <a name="BKMK_Install_Scenarios"></a> <span data-ttu-id="3de28-157">escenarios de instalación de 32 bits y 64 bits</span><span class="sxs-lookup"><span data-stu-id="3de28-157">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="3de28-158">Con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se puede usar para:</span><span class="sxs-lookup"><span data-stu-id="3de28-158">With [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used for:</span></span>  

- [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="3de28-159"> tiempo de diseño (al generar los metadatos para operaciones).</span><span class="sxs-lookup"><span data-stu-id="3de28-159"> design time (when generating metadata for operations).</span></span>  

- <span data-ttu-id="3de28-160">Tiempo de diseño de consola de administración de BizTalk Server (para la creación de puertos físicos).</span><span class="sxs-lookup"><span data-stu-id="3de28-160">BizTalk Server Administration console design time (for creating physical ports).</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="3de28-161">Consola de administración de BizTalk Server se ejecuta como una aplicación de Microsoft Management Console (MMC) de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="3de28-161">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  

- <span data-ttu-id="3de28-162">Tiempo de ejecución de BizTalk (al enviar y recibir mensajes desde aplicaciones de LOB).</span><span class="sxs-lookup"><span data-stu-id="3de28-162">BizTalk run time (when sending and receiving messages from LOB applications).</span></span>  

  <span data-ttu-id="3de28-163">Puede tener una instalación donde se realizan todas estas tareas en el mismo equipo o en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="3de28-163">You can have an installation where you perform all these tasks on the same computer or different computers.</span></span> <span data-ttu-id="3de28-164">Dado que ambos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y MMC de BizTalk son procesos de 32 bits, debe instalar lo 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en el equipo donde desea realizar las tareas de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="3de28-164">Because both [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on the computer where you want to perform the design-time tasks.</span></span> <span data-ttu-id="3de28-165">Se admiten los escenarios siguientes para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en plataformas de 32 bits y 64 bits.</span><span class="sxs-lookup"><span data-stu-id="3de28-165">The following scenarios are supported for installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on 32-bit and 64-bit platforms.</span></span>  

#### <a name="32-bit-install-scenarios"></a><span data-ttu-id="3de28-166">escenarios de instalación de 32 bits</span><span class="sxs-lookup"><span data-stu-id="3de28-166">32-bit install scenarios</span></span>  
 <span data-ttu-id="3de28-167">Se admiten los siguientes escenarios cuando se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una plataforma de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="3de28-167">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 32-bit platform.</span></span>  


|                                                                                                               <span data-ttu-id="3de28-168">Tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3de28-168">Visual Studio design time</span></span>                                                                                                                |                                                                                                                <span data-ttu-id="3de28-169">Tiempo de diseño de MMC de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3de28-169">BizTalk MMC design time</span></span>                                                                                                                 |                                                                                                                    <span data-ttu-id="3de28-170">Tiempo de ejecución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3de28-170">BizTalk run time</span></span>                                                                                                                    |                                                                                      <span data-ttu-id="3de28-171">Tiempo de ejecución Visual tiempo de diseño de Studio o tiempo de diseño de BizTalk MMC + BizTalk</span><span class="sxs-lookup"><span data-stu-id="3de28-171">Visual Studio design time and/or  BizTalk MMC design time + BizTalk run time</span></span>                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3de28-172">-Instalación de 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-172">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-173">-Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-173">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-174">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-174">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="3de28-175">-Instalación de 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-175">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-176">-Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-176">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-177">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-177">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="3de28-178">-Instalación de 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-178">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-179">-Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-179">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-180">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-180">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="3de28-181">-Instalación de 32 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-181">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-182">-Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-182">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-183">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-183">- Install 32-bit client and other required DLLs.</span></span> |

#### <a name="64-bit-install-scenarios"></a><span data-ttu-id="3de28-184">escenarios de instalación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="3de28-184">64-bit install scenarios</span></span>  
 <span data-ttu-id="3de28-185">Se admiten los siguientes escenarios cuando se instala el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="3de28-185">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 64-bit platform.</span></span>  

> [!NOTE]
>  <span data-ttu-id="3de28-186">En cualquier equipo donde desea realizar tareas de tiempo de diseño mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o MMC de BizTalk, debe instalar lo 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-186">On any computer where you want to perform design-time tasks using either [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

|                                                                                                               <span data-ttu-id="3de28-187">Tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3de28-187">Visual Studio design time</span></span>                                                                                                                |                                                                                                                <span data-ttu-id="3de28-188">Tiempo de diseño de MMC de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3de28-188">BizTalk MMC design time</span></span>                                                                                                                 |                                                                                                                                                                                                                                                                                                   <span data-ttu-id="3de28-189">Tiempo de ejecución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3de28-189">BizTalk run time</span></span>                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                    <span data-ttu-id="3de28-190">Tiempo de ejecución Visual tiempo de diseño de Studio o tiempo de diseño de BizTalk MMC + BizTalk</span><span class="sxs-lookup"><span data-stu-id="3de28-190">Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>                                                                                                                                                                                                                                                                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3de28-191">-Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-191">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-192">-Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-192">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-193">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-193">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="3de28-194">-Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-194">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-195">-Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-195">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-196">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-196">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="3de28-197">**Para un proceso de BizTalk de 32 bits**:</span><span class="sxs-lookup"><span data-stu-id="3de28-197">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3de28-198">-Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-198">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-199">-Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-199">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-200">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-200">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="3de28-201">**Para un proceso de 64 bits BizTalk**:</span><span class="sxs-lookup"><span data-stu-id="3de28-201">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3de28-202">-Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-202">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-203">-Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-203">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-204">-Instalar el cliente de 64 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-204">- Install 64-bit client and other required DLLs.</span></span> | <span data-ttu-id="3de28-205">**Para un proceso de BizTalk de 32 bits**:</span><span class="sxs-lookup"><span data-stu-id="3de28-205">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3de28-206">-Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-206">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-207">-Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-207">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-208">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-208">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="3de28-209">**Para un proceso de 64 bits BizTalk**:</span><span class="sxs-lookup"><span data-stu-id="3de28-209">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3de28-210">-Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-210">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-211">-Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-211">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-212">-Instalar el cliente de 64 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-212">- Install 64-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="3de28-213">-Instalación de 32 bits [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-213">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3de28-214">-Instalar el cliente de 32 bits y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="3de28-214">- Install 32-bit client and other required DLLs.</span></span> |

<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-adapter-in-interactive-mode"></a><span data-ttu-id="3de28-215">Instalar al adaptador en modo interactivo</span><span class="sxs-lookup"><span data-stu-id="3de28-215">Install the adapter in interactive mode</span></span>  
<span data-ttu-id="3de28-216">Complete los pasos siguientes para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante el Asistente para instalación.</span><span class="sxs-lookup"><span data-stu-id="3de28-216">Complete the following steps to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the setup wizard.</span></span>  

1. <span data-ttu-id="3de28-217">Ejecute al instalador.</span><span class="sxs-lookup"><span data-stu-id="3de28-217">Run the installer.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3de28-218">Si está instalando el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una máquina virtual, el Asistente para la instalación no puede continuar más allá de un cuadro de diálogo que le informa de que el programa de instalación está comprobando espacio en disco disponible.</span><span class="sxs-lookup"><span data-stu-id="3de28-218">If you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="3de28-219">En tales casos, se recomienda que utilice la opción de instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="3de28-219">In such cases, we recommend that you use the silent installation option.</span></span> <span data-ttu-id="3de28-220">Para obtener más información, consulte [instalar el adaptador de SQL en modo silencioso](#BKMK_SilentInst) (en este tema).</span><span class="sxs-lookup"><span data-stu-id="3de28-220">For more information, see [Install the SQL adapter in silent mode](#BKMK_SilentInst) (in this topic).</span></span>

2. <span data-ttu-id="3de28-221">Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3de28-221">Read the information on the Welcome screen, and then click **Next**.</span></span>  

3. <span data-ttu-id="3de28-222">Lea y acepte el contrato de licencia del usuario final (CLUF) y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3de28-222">Read and accept the end-user license agreement (EULA), and then click **Next**.</span></span>  

4. <span data-ttu-id="3de28-223">En el **carpeta de destino** diálogo cuadro, especifique la ubicación donde desea instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], haga clic en **siguiente**y, a continuación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="3de28-223">In the **Destination Folder** dialog box, specify the location where you want to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], click **Next**, and then click **Install**.</span></span>  

5. <span data-ttu-id="3de28-224">En el **Customer Experience Improvement Program** diálogo cuadro, especifique si quiere inscribir para el programa para la mejora de la experiencia del usuario (CEIP).</span><span class="sxs-lookup"><span data-stu-id="3de28-224">In the **Customer Experience Improvement Program** dialog box, specify whether you would like to enroll for the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="3de28-225">Como parte de CEIP para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], con Microsoft compartirá los datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3de28-225">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  

   - <span data-ttu-id="3de28-226">Datos relacionados con el hardware del equipo en el que está instalando el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-226">Data related to the computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

   - <span data-ttu-id="3de28-227">Datos relacionados con las versiones de SQL Server que se usa para conectarse mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-227">Data related to the SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

     <span data-ttu-id="3de28-228">Especifique la elección y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3de28-228">Specify your choice and click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3de28-229">Siempre puede cambiar sus preferencias relacionada con la inscripción para el CEIP mediante la ejecución del programa de instalación en modo de reparación desde el Panel de Control.</span><span class="sxs-lookup"><span data-stu-id="3de28-229">You can always change your preference regarding enrolling for CEIP by running the Setup in Repair mode from the Control Panel.</span></span>  

6. <span data-ttu-id="3de28-230">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3de28-230">Click **Finish**.</span></span>  

<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="3de28-231">Instalar al adaptador de SQL en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="3de28-231">Install the SQL adapter in silent mode</span></span> 
<span data-ttu-id="3de28-232">Complete los pasos siguientes para realizar una instalación silenciosa de [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utilizando el `msiexec` comando.</span><span class="sxs-lookup"><span data-stu-id="3de28-232">Complete the following steps to do a silent installation of [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the `msiexec` command.</span></span>  

1. <span data-ttu-id="3de28-233">Abra un símbolo del sistema y navegue hasta la carpeta donde haya el instalador.</span><span class="sxs-lookup"><span data-stu-id="3de28-233">Open a command prompt, and navigate to the folder where you have the installer.</span></span>  

2. <span data-ttu-id="3de28-234">Ejecute el siguiente comando para instalar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3de28-234">Run the following command to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3de28-235">Para llevar a cabo una instalación silenciosa en una plataforma basado en x64 64, en los siguientes comandos, reemplace SqlAdapterSetup.msi SqlAdapterSetup64.msi.</span><span class="sxs-lookup"><span data-stu-id="3de28-235">To perform silent installation on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn  
   ```  

    <span data-ttu-id="3de28-236">También puede elegir para inscribirse en CEIP como parte de la instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="3de28-236">You can also choose to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="3de28-237">Como parte de CEIP para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], con Microsoft compartirá los datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3de28-237">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  

   - <span data-ttu-id="3de28-238">El hardware del equipo en el que está instalando el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-238">The computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

   - <span data-ttu-id="3de28-239">Las versiones de SQL Server que se usa para conectarse mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-239">The SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

     <span data-ttu-id="3de28-240">Para inscribirse en CEIP, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3de28-240">To enroll for CEIP, run the following command:</span></span>  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
   ```  

    <span data-ttu-id="3de28-241">De forma predeterminada, la opción es false.</span><span class="sxs-lookup"><span data-stu-id="3de28-241">By default, the option is false.</span></span>  

    <span data-ttu-id="3de28-242">Para obtener más información sobre la `msiexec` comando, escriba `msiexec` en la línea de comandos y presione `ENTER`, o vea [ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781).</span><span class="sxs-lookup"><span data-stu-id="3de28-242">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  

<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a><span data-ttu-id="3de28-243">Tareas posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="3de28-243">Post-installation tasks</span></span>  

<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a><span data-ttu-id="3de28-244">Registrar los enlaces</span><span class="sxs-lookup"><span data-stu-id="3de28-244">Register the bindings</span></span>  
<span data-ttu-id="3de28-245">Siga estos pasos *sólo* si se produce un error en el Asistente para instalación registrar los enlaces del adaptador en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="3de28-245">Complete these steps *only* if the setup wizard fails to register the adapter bindings in the machine.config file.</span></span>  

1. <span data-ttu-id="3de28-246">Navegue al archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3de28-246">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="3de28-247">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="3de28-247">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

2. <span data-ttu-id="3de28-248">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="3de28-248">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="3de28-249">Para registrar los enlaces del adaptador:</span><span class="sxs-lookup"><span data-stu-id="3de28-249">To register the adapter bindings:</span></span>  

   1. <span data-ttu-id="3de28-250">Busque el elemento "system.serviceModel" y agregue lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="3de28-250">Search for the element "system.serviceModel" and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. <span data-ttu-id="3de28-251">Busque el elemento "bindingElementExtensions" bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="3de28-251">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="3de28-252">Agregue la siguiente sección en el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="3de28-252">Add the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="3de28-253">Para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="3de28-253">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="3de28-254">Busque el elemento "bindingExtensions" bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="3de28-254">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="3de28-255">Agregue la siguiente sección en el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="3de28-255">Add the following section under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="3de28-256">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="3de28-256">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  <span data-ttu-id="3de28-257">Para obtener información sobre cómo determinar la clave pública, consulte [determinar la clave pública y la versión](#BKMK_PubKey).</span><span class="sxs-lookup"><span data-stu-id="3de28-257">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  

4. <span data-ttu-id="3de28-258">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="3de28-258">Save and close the machine.config file.</span></span>  

<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a><span data-ttu-id="3de28-259">Determinación de la clave pública y versión</span><span class="sxs-lookup"><span data-stu-id="3de28-259">Determining the Public Key and Version</span></span>  
<span data-ttu-id="3de28-260">Complete los pasos siguientes para determinar la clave pública y la versión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-260">Complete the following steps to determine the public key and version for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

1. <span data-ttu-id="3de28-261">Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.</span><span class="sxs-lookup"><span data-stu-id="3de28-261">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  

2. <span data-ttu-id="3de28-262">Haga clic en el archivo DLL para el que desea que la clave pública y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3de28-262">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="3de28-263">En la tabla siguiente se muestra el nombre de los archivos DLL para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-263">The following table lists the name of the DLLs for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  


   |                              <span data-ttu-id="3de28-264">Adaptador</span><span class="sxs-lookup"><span data-stu-id="3de28-264">Adapter</span></span>                              |      <span data-ttu-id="3de28-265">Nombre del archivo DLL</span><span class="sxs-lookup"><span data-stu-id="3de28-265">Name of the DLL</span></span>       |
   |-------------------------------------------------------------------|----------------------------|
   | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] | <span data-ttu-id="3de28-266">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="3de28-266">Microsoft.Adapters.Sql.dll</span></span> |


3. <span data-ttu-id="3de28-267">En el **General** pestaña, el valor con el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="3de28-267">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="3de28-268">De forma similar, el valor con el **versión** etiqueta Especifica el número de versión para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="3de28-268">Similarly, the value against the **Version** label specifies the version number for the DLL.</span></span>  

4. <span data-ttu-id="3de28-269">Copie la clave pública y, a continuación, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="3de28-269">Copy the public key, and then click **Cancel**.</span></span>  

<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a><span data-ttu-id="3de28-270">Actualizar o cambiar la instalación del adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="3de28-270">Update or change the SQL adapter installation</span></span>  
 <span data-ttu-id="3de28-271">Realice los pasos siguientes para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="3de28-271">Perform the following steps to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span> <span data-ttu-id="3de28-272">Asegúrese de que tiene el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalado antes de ejecutar el Asistente para la instalación para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="3de28-272">Make sure you have the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span>  

 <span data-ttu-id="3de28-273">Puede modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="3de28-273">You can modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the following two ways:</span></span>  

-   <span data-ttu-id="3de28-274">**En el modo interactivo** ejecutando el Asistente para instalación.</span><span class="sxs-lookup"><span data-stu-id="3de28-274">**In interactive mode** by running the setup wizard.</span></span>  

-   <span data-ttu-id="3de28-275">**En modo silencioso** mediante el uso de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3de28-275">**In silent mode** by using the command line.</span></span>  

#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a><span data-ttu-id="3de28-276">Actualizar la instalación del adaptador de SQL en modo interactivo</span><span class="sxs-lookup"><span data-stu-id="3de28-276">Update the SQL Adapter installation in interactive mode</span></span>  

1.  <span data-ttu-id="3de28-277">Haga clic en **iniciar**y, a continuación, haga clic en **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="3de28-277">Click **Start**, and then click **Control Panel**.</span></span>  

2.  <span data-ttu-id="3de28-278">En el Panel de Control, haga doble clic en **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="3de28-278">In Control Panel, double-click **Programs and Features**.</span></span>  

3.  <span data-ttu-id="3de28-279">En el **programas y características** ventana, seleccione **Microsoft BizTalk Adapter para SQL Server**y, a continuación, haga clic en **cambio**.</span><span class="sxs-lookup"><span data-stu-id="3de28-279">In the **Programs and Features** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Change**.</span></span>  

4.  <span data-ttu-id="3de28-280">Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3de28-280">Read the information on the Welcome screen, and then click **Next**.</span></span>  

5.  <span data-ttu-id="3de28-281">En el **cambiar, reparar o quitar instalación** cuadro de diálogo, haga clic en **reparar**.</span><span class="sxs-lookup"><span data-stu-id="3de28-281">In the **Change, repair, or remove installation** dialog box, click **Repair**.</span></span>  

6.  <span data-ttu-id="3de28-282">En el **preparado para reparar Microsoft BizTalk Adapter para SQL Server** cuadro de diálogo, haga clic en **reparar**.</span><span class="sxs-lookup"><span data-stu-id="3de28-282">In the **Ready to repair Microsoft BizTalk Adapter for SQL Server** dialog box, click **Repair**.</span></span>  

7.  <span data-ttu-id="3de28-283">Si es necesario, cambie las preferencias referente a optar por CEIP y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3de28-283">If required, change your preferences regarding opting for CEIP, and then click **OK**.</span></span>  

8.  <span data-ttu-id="3de28-284">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3de28-284">Click **Finish**.</span></span>  

#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a><span data-ttu-id="3de28-285">Actualizar la instalación del adaptador de SQL en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="3de28-285">Update the SQL Adapter installation in silent mode</span></span>  

1. <span data-ttu-id="3de28-286">Abra un símbolo del sistema y navegue hasta el directorio raíz de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalador.</span><span class="sxs-lookup"><span data-stu-id="3de28-286">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  

2. <span data-ttu-id="3de28-287">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3de28-287">Run the following command:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3de28-288">Para modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación en modo silencioso en una plataforma basado en x64 64, en los siguientes comandos, reemplace SqlAdapterSetup.msi SqlAdapterSetup64.msi.</span><span class="sxs-lookup"><span data-stu-id="3de28-288">To modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn /f  
   ```  

   > [!IMPORTANT]
   >  <span data-ttu-id="3de28-289">Al modificar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalación en modo silencioso, no se puede cambiar sus preferencias para participar o no en CEIP.</span><span class="sxs-lookup"><span data-stu-id="3de28-289">While modifying the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="3de28-290">Las preferencias de seguirá siendo el mismo que especificó durante la instalación, incluso si se establece explícitamente el CEIP_OPTIN en true o false.</span><span class="sxs-lookup"><span data-stu-id="3de28-290">The preferences will remain the same as you specified during the installation, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  

    <span data-ttu-id="3de28-291">Para obtener más información sobre la `msiexec` tipo de comando `msiexec` en la línea de comandos y presione `ENTER`, o vea [ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781).</span><span class="sxs-lookup"><span data-stu-id="3de28-291">For more information about the `msiexec` command type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  

<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a><span data-ttu-id="3de28-292">Desinstalar o eliminar el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="3de28-292">Uninstall or remove the SQL Adapter</span></span>  
 <span data-ttu-id="3de28-293">Realice los pasos siguientes para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] desde su equipo.</span><span class="sxs-lookup"><span data-stu-id="3de28-293">Perform the following steps to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from your computer.</span></span> <span data-ttu-id="3de28-294">Asegúrese de que tiene el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalado antes de ejecutar el Asistente para la instalación para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-294">Make sure you have the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

 <span data-ttu-id="3de28-295">Puede quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="3de28-295">You can remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  

-   <span data-ttu-id="3de28-296">**En el modo interactivo** ejecutando el Asistente para instalación.</span><span class="sxs-lookup"><span data-stu-id="3de28-296">**In interactive mode** by running the setup wizard.</span></span>  

-   <span data-ttu-id="3de28-297">**En modo silencioso** mediante el uso de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3de28-297">**In silent mode** by using the command line.</span></span>  

#### <a name="uninstall-the-sql-adapter-in-interactive-mode"></a><span data-ttu-id="3de28-298">Desinstalar el adaptador de SQL en modo interactivo</span><span class="sxs-lookup"><span data-stu-id="3de28-298">Uninstall the SQL Adapter in interactive mode</span></span>  

1.  <span data-ttu-id="3de28-299">Haga clic en **iniciar**y, a continuación, haga clic en **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="3de28-299">Click **Start**, and then click **Control Panel**.</span></span>  

2.  <span data-ttu-id="3de28-300">En el Panel de Control, haga doble clic en **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="3de28-300">In Control Panel, double-click  **Programs and Features**.</span></span>  

3.  <span data-ttu-id="3de28-301">En el **agregar o quitar programas** ventana, seleccione **Microsoft BizTalk Adapter para SQL Server**y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="3de28-301">In the **Add or Remove Programs** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Remove**.</span></span>  

4.  <span data-ttu-id="3de28-302">En el cuadro de diálogo, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3de28-302">In the dialog box, click **Yes**.</span></span>  

#### <a name="uninstall-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="3de28-303">Desinstalar el adaptador de SQL en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="3de28-303">Uninstall the SQL Adapter in silent mode</span></span>  

1. <span data-ttu-id="3de28-304">Abra un símbolo del sistema y navegue hasta el directorio raíz de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] instalador.</span><span class="sxs-lookup"><span data-stu-id="3de28-304">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  

2. <span data-ttu-id="3de28-305">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3de28-305">Run the following command:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3de28-306">Para quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en modo silencioso en una plataforma basado en x64 64, en los siguientes comandos, reemplace SqlAdapterSetup.msi con SqlAdapterSetup64.msi.</span><span class="sxs-lookup"><span data-stu-id="3de28-306">To remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  

   ```  
   msiexec /x SqlAdapterSetup.msi /qn  
   ```  

    <span data-ttu-id="3de28-307">Este comando quita el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] desde el equipo.</span><span class="sxs-lookup"><span data-stu-id="3de28-307">This command removes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from the computer.</span></span>  

    <span data-ttu-id="3de28-308">Para obtener más información sobre la `msiexec` comando, escriba `msiexec` en la línea de comandos y presione `ENTER`, o vea [ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781).</span><span class="sxs-lookup"><span data-stu-id="3de28-308">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  

<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a><span data-ttu-id="3de28-309">Tarea posterior a la desinstalación</span><span class="sxs-lookup"><span data-stu-id="3de28-309">Post-uninstall task</span></span>  
 <span data-ttu-id="3de28-310">Si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] el programa de instalación no puede quitar los enlaces del adaptador al quitar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], debe quitarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="3de28-310">If the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] setup fails to remove the adapter bindings while removing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must remove them manually.</span></span> <span data-ttu-id="3de28-311">La siguiente sección describe cómo quitar manualmente los enlaces para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de28-311">The following section describes how to manually remove the bindings for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

<span data-ttu-id="3de28-312">Siga estos pasos *sólo* si se produce un error en el Asistente para instalación quitar los enlaces del adaptador desde el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="3de28-312">Complete these steps *only* if the setup wizard fails to remove the adapter bindings from the machine.config file.</span></span>  

1. <span data-ttu-id="3de28-313">Navegue al archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3de28-313">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="3de28-314">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="3de28-314">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

   - <span data-ttu-id="3de28-315">Para Microsoft .NET Framework 3.5 SP1, \< *versión* \> es la versión v2.0.50727 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3de28-315">For Microsoft .NET Framework 3.5 SP1, \<*version*\> is the version v2.0.50727 of the .NET Framework.</span></span>  

   - <span data-ttu-id="3de28-316">Para Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \< *versión* \> es el v4.0.30319 de versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3de28-316">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*\> is the version v4.0.30319 of the .NET Framework.</span></span>  

2. <span data-ttu-id="3de28-317">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="3de28-317">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="3de28-318">Para quitar el registro de enlace del adaptador:</span><span class="sxs-lookup"><span data-stu-id="3de28-318">To remove the adapter binding registration:</span></span>  

   1. <span data-ttu-id="3de28-319">Busque el elemento "system.serviceModel" y quite el siguiente en el elemento:</span><span class="sxs-lookup"><span data-stu-id="3de28-319">Search for the element "system.serviceModel" and remove the following from under the element:</span></span>  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  

      ```  

   2. <span data-ttu-id="3de28-320">Busque el elemento "bindingElementExtensions" bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="3de28-320">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="3de28-321">Quite la siguiente sección en el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="3de28-321">Remove the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="3de28-322">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3de28-322">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="3de28-323">Busque el elemento "bindingExtensions" bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="3de28-323">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="3de28-324">Quite la siguiente sección en el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="3de28-324">Remove the following section under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="3de28-325">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3de28-325">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

4. <span data-ttu-id="3de28-326">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="3de28-326">Save and close the machine.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3de28-327">Vea también</span><span class="sxs-lookup"><span data-stu-id="3de28-327">See also</span></span>
[<span data-ttu-id="3de28-328">Instalar el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="3de28-328">Install the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[<span data-ttu-id="3de28-329">Descripción del adaptador de BizTalk para SQL Server</span><span class="sxs-lookup"><span data-stu-id="3de28-329">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)