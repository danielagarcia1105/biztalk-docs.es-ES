---
title: Actualizar el Acelerador de BizTalk para HL7 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91b6747f-e560-4cf8-99b5-af0d150599bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 245d59e54a39cb77a71fc546920542619a4aeb3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977645"
---
# <a name="upgrade-biztalk-accelerator-for-hl7"></a><span data-ttu-id="4a961-102">Actualizar el Acelerador de BizTalk para HL7</span><span class="sxs-lookup"><span data-stu-id="4a961-102">Upgrade BizTalk Accelerator for HL7</span></span>
<span data-ttu-id="4a961-103">Información general sobre el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="4a961-103">Overview of the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] upgrade process.</span></span> 

<a name="BKMK_BeforeUpgrade"></a>   
## <a name="before-you-upgrade"></a><span data-ttu-id="4a961-104">Antes de realizar la actualización</span><span class="sxs-lookup"><span data-stu-id="4a961-104">Before you upgrade</span></span>  

- <span data-ttu-id="4a961-105">El usuario que ejecuta la actualización debe ser miembro del grupo Administradores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4a961-105">The user running the upgrade must be a member of the BizTalk Administrators group.</span></span>  

- <span data-ttu-id="4a961-106">El servicio de SQL Server (MSSQLSERVER) debe estar ejecutándose al realizar una actualización.</span><span class="sxs-lookup"><span data-stu-id="4a961-106">The SQL Server (MSSQLSERVER) service must be running when you perform an upgrade.</span></span>  

- <span data-ttu-id="4a961-107">No ejecute una instalación silenciosa para actualizar.</span><span class="sxs-lookup"><span data-stu-id="4a961-107">Do not run a silent installation to upgrade.</span></span>  

- <span data-ttu-id="4a961-108">Cuando se actualiza, el programa de instalación migra existente [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] información de configuración a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="4a961-108">When you upgrade, the setup program migrates the existing [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] configuration information to the newer version.</span></span>  

- <span data-ttu-id="4a961-109">Cuando se actualiza, las claves del registro y las bases de datos se copian automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4a961-109">When you upgrade, the registry keys and databases are automatically backed up.</span></span>  

- <span data-ttu-id="4a961-110">Los archivos en el  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7 carpeta se actualizan.</span><span class="sxs-lookup"><span data-stu-id="4a961-110">The files in the *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7 folder are updated.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="4a961-111">La actualización no crea una nueva carpeta para los archivos actualizados, ni tampoco cambia el nombre de la carpeta existente.</span><span class="sxs-lookup"><span data-stu-id="4a961-111">The upgrade does not create a new folder for the upgraded files, nor does it change the name of the existing folder.</span></span>  

<a name="BKMK_UpgradePaths"></a>   
## <a name="supported-upgrade-paths"></a><span data-ttu-id="4a961-112">Rutas de actualización admitidas</span><span class="sxs-lookup"><span data-stu-id="4a961-112">Supported Upgrade Paths</span></span>  
 <span data-ttu-id="4a961-113">En la tabla siguiente se enumera admitidos [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] versiones que se pueden actualizar.</span><span class="sxs-lookup"><span data-stu-id="4a961-113">The following table lists the supported [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] versions that can be upgraded.</span></span> <span data-ttu-id="4a961-114">"Sí" significa que el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] versión puede actualizarse.</span><span class="sxs-lookup"><span data-stu-id="4a961-114">“Yes” means the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] version can be upgraded.</span></span> <span data-ttu-id="4a961-115">"No" significa que el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] versión no se puede actualizar.</span><span class="sxs-lookup"><span data-stu-id="4a961-115">“No” means the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] version cannot be upgraded.</span></span> <span data-ttu-id="4a961-116">Si el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] versión no aparece, no se puede actualizar esa versión.</span><span class="sxs-lookup"><span data-stu-id="4a961-116">If the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] version is not listed, that version cannot be upgraded.</span></span>  


|                                                                                              | [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] | <span data-ttu-id="4a961-117">BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a961-117">BizTalk Server 2013</span></span> |
|----------------------------------------------------------------------------------------------|------------------------------------------------------|-------------------------------------------------------|---------------------|
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4a961-118"> 2013</span><span class="sxs-lookup"><span data-stu-id="4a961-118"> 2013</span></span> |                         <span data-ttu-id="4a961-119">Sí</span><span class="sxs-lookup"><span data-stu-id="4a961-119">Yes</span></span>                          |                          <span data-ttu-id="4a961-120">Sí</span><span class="sxs-lookup"><span data-stu-id="4a961-120">Yes</span></span>                          |         <span data-ttu-id="4a961-121">no</span><span class="sxs-lookup"><span data-stu-id="4a961-121">No</span></span>          |
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4a961-122"> 2010</span><span class="sxs-lookup"><span data-stu-id="4a961-122"> 2010</span></span> |                          <span data-ttu-id="4a961-123">no</span><span class="sxs-lookup"><span data-stu-id="4a961-123">No</span></span>                          |                          <span data-ttu-id="4a961-124">Sí</span><span class="sxs-lookup"><span data-stu-id="4a961-124">Yes</span></span>                          |         <span data-ttu-id="4a961-125">Sí</span><span class="sxs-lookup"><span data-stu-id="4a961-125">Yes</span></span>         |

<a name="BKMK_UpgradeSteps"></a>   
## <a name="upgrade-steps"></a><span data-ttu-id="4a961-126">Pasos de la actualización</span><span class="sxs-lookup"><span data-stu-id="4a961-126">Upgrade Steps</span></span>  

1. <span data-ttu-id="4a961-127">Actualizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a961-127">Upgrade the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>   

2. <span data-ttu-id="4a961-128">Copia de seguridad de la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] bases de datos y su HL7 los esquemas de mensajes.</span><span class="sxs-lookup"><span data-stu-id="4a961-128">Back up the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] databases and your HL7 message schemas.</span></span>  

3. <span data-ttu-id="4a961-129">Copia de seguridad de los archivos en el ***\<unidad\>*:\Program de programa\Microsoft BizTalk Accelerator para HL7** carpeta que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="4a961-129">Back up any files under the ***\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for HL7** folder that you have changed.</span></span> <span data-ttu-id="4a961-130">Por ejemplo, realizar una copia de seguridad de archivos en el SDK.</span><span class="sxs-lookup"><span data-stu-id="4a961-130">For example, back up files in the SDK.</span></span>  

4. <span data-ttu-id="4a961-131">Instalar la actualización adecuada para su versión de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4a961-131">Install the appropriate update for your version of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:</span></span>  

   -   <span data-ttu-id="4a961-132">Si actualiza desde BTAHL7 2010, instale **HL72010Patch.msp**.</span><span class="sxs-lookup"><span data-stu-id="4a961-132">If upgrading from BTAHL7 2010, install **HL72010Patch.msp**.</span></span>  

   -   <span data-ttu-id="4a961-133">Si actualiza desde BTAHL7 2013, instale **HL72013Patch.msp**.</span><span class="sxs-lookup"><span data-stu-id="4a961-133">If upgrading from BTAHL7 2013, install **HL72013Patch.msp**.</span></span>  


5. <span data-ttu-id="4a961-134">Ejecute el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="4a961-134">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.</span></span> <span data-ttu-id="4a961-135">Consulte [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span><span class="sxs-lookup"><span data-stu-id="4a961-135">See [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  

6. <span data-ttu-id="4a961-136">Implementar el nuevo BTAHL7V2*x*proyecto común.</span><span class="sxs-lookup"><span data-stu-id="4a961-136">Deploy the new BTAHL7V2*x*Common project.</span></span>  

7. <span data-ttu-id="4a961-137">Volver a implementar todos los demás ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4a961-137">Redeploy all other assemblies.</span></span>  

8. <span data-ttu-id="4a961-138">Recompile los proyectos y ensamblados que tengan una referencia a uno o varios de los ensamblados de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a961-138">Rebuild any projects or assemblies that have a reference to one or more of the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assemblies.</span></span> <span data-ttu-id="4a961-139">Mediante **BTSTask.exe** en \< *unidad*\>: BizTalk Server \Program Files\Microsoft \<versión\>, manualmente volver a implementar estos proyectos.</span><span class="sxs-lookup"><span data-stu-id="4a961-139">Using **BTSTask.exe** in \<*drive*\>:\Program Files\Microsoft BizTalk Server \<version\>, manually redeploy these projects.</span></span>  

9. <span data-ttu-id="4a961-140">Reinicie el servicio [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a961-140">Restart the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] service.</span></span>  

<a name="BKMK_UpgradeMulti"></a>   
## <a name="upgrading-in-a-multi-server-environment"></a><span data-ttu-id="4a961-141">Realizar una actualización en un entorno multiservidor</span><span class="sxs-lookup"><span data-stu-id="4a961-141">Upgrading in a Multi-server Environment</span></span>  
 <span data-ttu-id="4a961-142">En un servidor de múltiples [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] entorno, actualización [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]s y después actualiza el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="4a961-142">In a multi-server [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] environment, upgrade all [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]s, and then upgrade the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] on all servers.</span></span> <span data-ttu-id="4a961-143">Migre los servidores en este orden:</span><span class="sxs-lookup"><span data-stu-id="4a961-143">Migrate your servers in the following order:</span></span>  

-   <span data-ttu-id="4a961-144">Servidor que hospeda el grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4a961-144">The server hosting the BizTalk Group</span></span>  

-   <span data-ttu-id="4a961-145">Cada nodo de procesamiento</span><span class="sxs-lookup"><span data-stu-id="4a961-145">Each processing node</span></span>  

-   <span data-ttu-id="4a961-146">Servidor del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="4a961-146">The BAM portal server</span></span>  

## <a name="see-also"></a><span data-ttu-id="4a961-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a961-147">See Also</span></span>  
 [<span data-ttu-id="4a961-148">Instalar el Acelerador de BizTalk para HL7</span><span class="sxs-lookup"><span data-stu-id="4a961-148">Install BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)