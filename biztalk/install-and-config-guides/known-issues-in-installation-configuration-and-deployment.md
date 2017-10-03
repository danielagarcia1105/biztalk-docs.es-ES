---
title: "Problemas conocidos de instalación, configuración e implementación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed1c08eb-d647-4a4a-b9a3-c4d84e8d4b82
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda1bd5c8167bbf9f6049b3620c0c949950b1e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-in-installation-configuration-and-deployment"></a><span data-ttu-id="4690c-102">Problemas conocidos en la instalación, configuración e implementación</span><span class="sxs-lookup"><span data-stu-id="4690c-102">Known Issues in Installation, Configuration, and Deployment</span></span>
## <a name="some-biztalk-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="4690c-103">Algunos artefactos de EDI y AS2 de BizTalk siguen activos después de quitar la configuración</span><span class="sxs-lookup"><span data-stu-id="4690c-103">Some BizTalk EDI/AS2 Artifacts Are Still Active After Unconfiguring</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="4690c-104">Problema</span><span class="sxs-lookup"><span data-stu-id="4690c-104">Problem</span></span>  
 <span data-ttu-id="4690c-105">Tras quitar la configuración de la característica EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], algunos artefactos de BizTalk Server relacionados con el procesamiento de EDI y AS2 seguirán activos en el contexto de la configuración de grupos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4690c-105">After you unconfigure the BizTalk EDI/AS2 feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="4690c-106">Estos artefactos incluirán las canalizaciones EDI y AS2 y la orquestación de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="4690c-106">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="4690c-107">Como resultado, seguirá pudiendo realizar un procesamiento básico de EDI y AS2 incluso después de haber quitado la configuración de la característica de EDI y AS2 de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4690c-107">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the BizTalk EDI/AS2 feature.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="4690c-108">Causa</span><span class="sxs-lookup"><span data-stu-id="4690c-108">Cause</span></span>  
 <span data-ttu-id="4690c-109">Hay puertos activos asociados con el procesamiento de EDI y AS2.</span><span class="sxs-lookup"><span data-stu-id="4690c-109">There are active ports associated with EDI and AS2 processing.</span></span> <span data-ttu-id="4690c-110">Algunos artefactos seguirán funcionando mientras estos puertos permanezcan activos.</span><span class="sxs-lookup"><span data-stu-id="4690c-110">Some artifacts will continue to function while these ports remain active.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="4690c-111">Solución</span><span class="sxs-lookup"><span data-stu-id="4690c-111">Resolution</span></span>  
 <span data-ttu-id="4690c-112">Para deshabilitar todos los artefactos de EDI o AS2, debe deshabilitar, detener o eliminar los puertos asociados con el procesamiento de EDI y AS2.</span><span class="sxs-lookup"><span data-stu-id="4690c-112">To disable all EDI/AS2 artifacts, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="if-the-biztalk-server-computer-or-sql-server-computer-is-renamed-after-biztalk-server-configuration-the-configuration-wizard-will-fail"></a><span data-ttu-id="4690c-113">Si se cambia el nombre del equipo de BizTalk Server o del equipo de SQL Server después de configurar BizTalk Server, el Asistente para configuración dará errores</span><span class="sxs-lookup"><span data-stu-id="4690c-113">If the BizTalk Server Computer or SQL Server Computer Is Renamed After BizTalk Server Configuration, the Configuration Wizard Will Fail</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="4690c-114">Problema</span><span class="sxs-lookup"><span data-stu-id="4690c-114">Problem</span></span>  
 <span data-ttu-id="4690c-115">Este problema puede manifestarse de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="4690c-115">This problem may manifest itself in several ways:</span></span>  
  
-   <span data-ttu-id="4690c-116">La configuración de BizTalk Server cargará la página Información general de forma correcta aunque al tratar de configurar una característica, las opciones de ésta no aparecerán en pantalla.</span><span class="sxs-lookup"><span data-stu-id="4690c-116">The BizTalk Server Configuration will load the Overview page correctly, but when attempting to configure a feature the feature options do not display on the screen.</span></span>  
  
-   <span data-ttu-id="4690c-117">El asistente para configuración no se puede conectar al servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4690c-117">The configuration wizard cannot connect to the SQL Server.</span></span>  
  
-   <span data-ttu-id="4690c-118">El intento de anular la configuración de todo conseguirá anular la configuración de algunas características pero no de todas.</span><span class="sxs-lookup"><span data-stu-id="4690c-118">Attempting to Unconfigure All unconfigures some features, but not all.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="4690c-119">Causa</span><span class="sxs-lookup"><span data-stu-id="4690c-119">Cause</span></span>  
 <span data-ttu-id="4690c-120">La configuración de BizTalk Server almacena el nombre de red del equipo.</span><span class="sxs-lookup"><span data-stu-id="4690c-120">The BizTalk Server configuration stores the computer network name.</span></span> <span data-ttu-id="4690c-121">Cuando se cambia el nombre del equipo, el asistente para configuración y la configuración de BizTalk Server no pueden encontrar el servidor de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4690c-121">When the computer is renamed the BizTalk Server Configuration and configuration wizard cannot locate the BizTalk Server.</span></span> <span data-ttu-id="4690c-122">Se produce un problema parecido si se cambia el nombre del equipo del servidor SQL Server una vez que se haya configurado BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4690c-122">A similar problem will occur if the SQL Server computer is renamed after BizTalk Server is configured.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="4690c-123">Solución</span><span class="sxs-lookup"><span data-stu-id="4690c-123">Resolution</span></span>  
 <span data-ttu-id="4690c-124">No cambie el nombre del equipo del servidor BizTalk Server o del servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4690c-124">Do not rename the BizTalk Server computer or the SQL Server computer.</span></span> <span data-ttu-id="4690c-125">Si es necesario cambiar el nombre de un servidor, anule previamente la configuración de todas las características de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4690c-125">If a server must be renamed, unconfigure all BizTalk Features before renaming the computer.</span></span> <span data-ttu-id="4690c-126">Una vez que haya cambiado el nombre del equipo, vuelva a configurar las características de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4690c-126">After renaming the computer, reconfigure BizTalk Server features.</span></span>  
  
## <a name="the-biztalk-server-business-rules-configuration-wizard-fails"></a><span data-ttu-id="4690c-127">Se produce un error en el Asistente para configuración de reglas de negocios de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4690c-127">The BizTalk Server Business Rules Configuration Wizard Fails</span></span>  
  
### <a name="problem"></a><span data-ttu-id="4690c-128">Problema</span><span class="sxs-lookup"><span data-stu-id="4690c-128">Problem</span></span>  
  
-   <span data-ttu-id="4690c-129">El Asistente para configuración de reglas de negocio falla con el error "Error al configurar algunos componentes. No se aplicó la configuración a esos componentes".</span><span class="sxs-lookup"><span data-stu-id="4690c-129">The Business Rules Configuration Wizard fails with the error “Configuration failed for some components and no settings were applied for those components”.</span></span>  
  
-   <span data-ttu-id="4690c-130">En los equipos de BizTalk Server para los que ya se ha configurado correctamente el motor de reglas de negocio, se produce un error al iniciar el servicio Actualización del motor de reglas y no se puede iniciar manualmente.</span><span class="sxs-lookup"><span data-stu-id="4690c-130">On BizTalk Server computers for which the Business Rules Engine has already been successfully configured, the Rules Engine Update service fails to start and cannot be started manually.</span></span>  
  
 <span data-ttu-id="4690c-131">Cuando se da este problema, es posible que se genere un error similar al siguiente en el registro de aplicación del equipo de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="4690c-131">When this problem occurs, an error similar to the following may be generated in the BizTalk Server computer Application log:</span></span>  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
### <a name="cause"></a><span data-ttu-id="4690c-132">Causa</span><span class="sxs-lookup"><span data-stu-id="4690c-132">Cause</span></span>  
 <span data-ttu-id="4690c-133">El Centro de protección contra malware de Microsoft lanzó un archivo de firma actualizado, para tratar una posible amenaza de SettingsModifier:Win32/PossibleHostsFileHijack.</span><span class="sxs-lookup"><span data-stu-id="4690c-133">The Microsoft Malware Protection Center released an updated signature file to address a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="4690c-134">Este archivo de firma actualizado puede causar que el software de detección de malware de Microsoft, tal como Windows Defender, actualice el archivo HOSTS local para mitigar las amenazas de SettingsModifier:Win32/PossibleHostsFileHijack.</span><span class="sxs-lookup"><span data-stu-id="4690c-134">This updated signature file can cause Microsoft Malware Detection software such as Windows Defender to update the local HOSTS file to mitigate threats from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="4690c-135">Como resultado de estos cambios, es posible que se produzca un error al iniciar el Servicio de actualización del motor de reglas de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4690c-135">As a result of these changes, the BizTalk Server Rules Engine Update service may fail to start.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="4690c-136">Solución</span><span class="sxs-lookup"><span data-stu-id="4690c-136">Resolution</span></span>  
 <span data-ttu-id="4690c-137">Actualice el archivo HOSTS local para que incluya la línea siguiente:</span><span class="sxs-lookup"><span data-stu-id="4690c-137">Update the local HOSTS file to include the following line:</span></span>  
  
```  
127.0.0.1         localhost  
```  
  
 <span data-ttu-id="4690c-138">El archivo HOSTS se encuentra en el directorio %systemroot%\drivers\etc\.</span><span class="sxs-lookup"><span data-stu-id="4690c-138">The HOSTS file is located in the %systemroot%\drivers\etc\ directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4690c-139">Para obtener más información sobre la actualización de firma del Centro de protección contra malware de Microsoft que trata una posible amenaza de SettingsModifier:Win32/PossibleHostsFileHijack, consulte [http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221).</span><span class="sxs-lookup"><span data-stu-id="4690c-139">For more information about the Microsoft Malware Protection Center signature update that addresses a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack, go to [http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221).</span></span>  
  
## <a name="enlistment-of-an-orchestration-fails-if-referenced-assemblies-are-missing-from-the-gacmgmt-db"></a><span data-ttu-id="4690c-140">Se produce un error al dar de alta una orquestación si en la base de datos de GAC/Mgmt faltan ensamblados a los que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="4690c-140">Enlistment of an Orchestration Fails if Referenced Assemblies are Missing from the GAC/Mgmt DB</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="4690c-141">Problema</span><span class="sxs-lookup"><span data-stu-id="4690c-141">Problem</span></span>  
 <span data-ttu-id="4690c-142">Se produce un error al dar de alta una orquestación si en la base de datos de GAC/Mgmt faltan referencias (ensamblados de C# a los que se hace referencia en las orquestaciones).</span><span class="sxs-lookup"><span data-stu-id="4690c-142">Enlistment of an orchestration fails if references (C# assemblies which are referenced to orchestrations) are missing from the GAC/Mgmt db.</span></span> <span data-ttu-id="4690c-143">Durante la reimplementación, puede ser necesario dar de alta la orquestación basándose en su estado existente.</span><span class="sxs-lookup"><span data-stu-id="4690c-143">During re-deployment, there may be a need to enlist the orchestration based on its existing state.</span></span> <span data-ttu-id="4690c-144">Si faltan referencias, también se produce un error en la implementación.</span><span class="sxs-lookup"><span data-stu-id="4690c-144">If references are missing then the deployment also fails.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="4690c-145">Causa</span><span class="sxs-lookup"><span data-stu-id="4690c-145">Cause</span></span>  
 <span data-ttu-id="4690c-146">En la base de datos de GAC/Mgmt faltan ensamblados a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="4690c-146">Referenced assemblies are missing from GAC/Mgmt db.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="4690c-147">Solución</span><span class="sxs-lookup"><span data-stu-id="4690c-147">Resolution</span></span>  
 <span data-ttu-id="4690c-148">Agregue los ensamblados a los que se hace referencia en la GAC, o agréguelos como recursos, para que se almacenen en la base de datos Mgmt y estén disponibles al dar de alta la orquestación.</span><span class="sxs-lookup"><span data-stu-id="4690c-148">Add the referenced assemblies in GAC or add them as resources, so that they are stored in Mgmt db and are accessible during enlistment of orchestration.</span></span>  

## <a name="community-blog-biztalk-2013-r2-bugs-issues--quirks"></a><span data-ttu-id="4690c-149">Blog de la comunidad: errores, problemas y peculiaridades de BizTalk 2013 R2</span><span class="sxs-lookup"><span data-stu-id="4690c-149">Community blog: BizTalk 2013 R2 bugs, issues & quirks</span></span>

<span data-ttu-id="4690c-150">[BizTalk Server 2013 R2 known bugs, issues, quirks](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/) (Errores, problemas y peculiaridades conocidos de BizTalk Server 2013 R2)</span><span class="sxs-lookup"><span data-stu-id="4690c-150">[BizTalk Server 2013 R2 known bugs, issues, quirks](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/)</span></span>
  
## <a name="additional-configuration-topics"></a><span data-ttu-id="4690c-151">Temas adicionales sobre configuración</span><span class="sxs-lookup"><span data-stu-id="4690c-151">Additional Configuration Topics</span></span>  
  
 [<span data-ttu-id="4690c-152">Configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4690c-152">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
 [<span data-ttu-id="4690c-153">Configurar BizTalk Server en una máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="4690c-153">Configuring BizTalk Server on an Azure VM</span></span>](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
  [<span data-ttu-id="4690c-154">Configuración de BizTalk Server en un clúster</span><span class="sxs-lookup"><span data-stu-id="4690c-154">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
  
 [<span data-ttu-id="4690c-155">Proteger la implementación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4690c-155">Securing Your BizTalk Server Deployment</span></span>](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  