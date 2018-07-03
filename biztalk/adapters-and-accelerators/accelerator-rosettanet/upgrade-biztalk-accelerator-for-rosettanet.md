---
title: Actualización del Acelerador para RosettaNet (BTARN) en BizTalk Server | Microsoft Docs"
description: Siga los pasos de actualización para actualizar BTARN a la versión actual de BizTalk Server
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: 80e813ced767cdd56910027b655060e1db9f91fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011312"
---
# <a name="upgrade-the-rosettanet-accelerator"></a><span data-ttu-id="5062c-103">Actualizar el Acelerador de RosettaNet</span><span class="sxs-lookup"><span data-stu-id="5062c-103">Upgrade the RosettaNet accelerator</span></span>

## <a name="upgrade-overview"></a><span data-ttu-id="5062c-104">Información general sobre la actualización</span><span class="sxs-lookup"><span data-stu-id="5062c-104">Upgrade overview</span></span>
<span data-ttu-id="5062c-105">Puede actualizar la versión anterior del Acelerador de BizTalk para la instalación de RosettaNet (BTARN) a la versión actual.</span><span class="sxs-lookup"><span data-stu-id="5062c-105">You can upgrade the previous version of the BizTalk Accelerator for RosettaNet (BTARN) installation to the current version.</span></span> <span data-ttu-id="5062c-106">El proceso de actualización implica la actualización del servidor BizTalk Server y, a continuación, BTARN.</span><span class="sxs-lookup"><span data-stu-id="5062c-106">The upgrade process involves upgrading BizTalk Server, and then upgrading BTARN.</span></span>  
  
 <span data-ttu-id="5062c-107">Puede actualizar desde la versión anterior de BTARN en un ejecutando el programa de instalación de BTARN.</span><span class="sxs-lookup"><span data-stu-id="5062c-107">You can upgrade from the previous version of BTARN to a by running the BTARN installation program.</span></span> <span data-ttu-id="5062c-108">El programa de instalación migra la información de configuración de BTRAN a la versión actual.</span><span class="sxs-lookup"><span data-stu-id="5062c-108">The setup migrates the BTRAN configuration information to the current version.</span></span>  
  
 <span data-ttu-id="5062c-109">En un entorno de BTARN multiservidor, debe actualizar todos los servidores BizTalk primero y, a continuación, en BTARN.</span><span class="sxs-lookup"><span data-stu-id="5062c-109">In a multi-server BTARN environment, you should upgrade all BizTalk Servers first, and then to BTARN.</span></span> <span data-ttu-id="5062c-110">Migre los servidores en este orden:</span><span class="sxs-lookup"><span data-stu-id="5062c-110">Migrate your servers in the following order:</span></span>  
  
- <span data-ttu-id="5062c-111">Servidor que hospeda el grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="5062c-111">The server hosting the BizTalk Group</span></span>  
  
- <span data-ttu-id="5062c-112">Cada nodo de procesamiento</span><span class="sxs-lookup"><span data-stu-id="5062c-112">Each processing node</span></span>  
  
- <span data-ttu-id="5062c-113">Servidor del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="5062c-113">The BAM portal server</span></span>  
  
  <span data-ttu-id="5062c-114">En el BTARN proceso de actualización, asegúrese de que haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5062c-114">In the BTARN upgrade process, ensure you do the following:</span></span>  
  
- <span data-ttu-id="5062c-115">Compruebe si el servicio SQL Server (MSSQLSERVER) está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="5062c-115">Check if the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
- <span data-ttu-id="5062c-116">No realice una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="5062c-116">Do not run a silent installation.</span></span>  
  
## <a name="upgrade-steps"></a><span data-ttu-id="5062c-117">Pasos de la actualización</span><span class="sxs-lookup"><span data-stu-id="5062c-117">Upgrade steps</span></span>  
  
1.  <span data-ttu-id="5062c-118">Actualización de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5062c-118">Upgrade BizTalk Server.</span></span> <span data-ttu-id="5062c-119">Consulte [BizTalk Server Novedades, instalación, configuración y actualización](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="5062c-119">See [BizTalk Server What's New, Installation, Configuration, and Upgrade](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
  
2.  <span data-ttu-id="5062c-120">Realizar una copia de seguridad de la base de datos BTARN y esquemas de mensajes BTARN.</span><span class="sxs-lookup"><span data-stu-id="5062c-120">Back up the BTARN database and BTARN message schemas.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5062c-121">Debe realizar copias de seguridad de la base de datos BTARN por razones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5062c-121">You should back up the BTARN database for safety reasons.</span></span> <span data-ttu-id="5062c-122">El programa de instalación migra la base de datos BTRAN a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="5062c-122">The installation program migrates the BTRAN database to the newer version.</span></span>  
  
3.  <span data-ttu-id="5062c-123">Copia de seguridad de los archivos en el *< unidad\>*: \Program archivos\\Acelerador de Microsoft BizTalk para RosettaNet carpeta que haya realizado los cambios en, por ejemplo, los archivos del SDK.</span><span class="sxs-lookup"><span data-stu-id="5062c-123">Back up any files under the *<drive\>*:\Program Files\\Microsoft BizTalk Accelerator for RosettaNet folder that you have made changes to, for example, files in the SDK.</span></span>  
  
4.  <span data-ttu-id="5062c-124">Anule la implementación de los proyectos o ensamblados que tengan referencias a una o varias versiones anteriores de los ensamblados de BTARN.</span><span class="sxs-lookup"><span data-stu-id="5062c-124">Undeploy any projects or assemblies that have references to one or more of the previous versions of BTARN assemblies.</span></span>  
  
5.  <span data-ttu-id="5062c-125">En Visual Studio, manualmente anular la implementación de todos los ensamblados BTARN, en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="5062c-125">In Visual Studio, manually undeploy all BTARN assemblies, in the following order:</span></span>  
  
    -   <span data-ttu-id="5062c-126">Microsoft.Solutions.BTARN.CommonTypes</span><span class="sxs-lookup"><span data-stu-id="5062c-126">Microsoft.Solutions.BTARN.CommonTypes</span></span>  
  
    -   <span data-ttu-id="5062c-127">Microsoft.Solutions.BTARN.GlobalSchemas</span><span class="sxs-lookup"><span data-stu-id="5062c-127">Microsoft.Solutions.BTARN.GlobalSchemas</span></span>  
  
    -   <span data-ttu-id="5062c-128">Microsoft.Solutions.BTARN.PipelineReceive</span><span class="sxs-lookup"><span data-stu-id="5062c-128">Microsoft.Solutions.BTARN.PipelineReceive</span></span>  
  
    -   <span data-ttu-id="5062c-129">Microsoft.Solutions.BTARN.PipelineSend</span><span class="sxs-lookup"><span data-stu-id="5062c-129">Microsoft.Solutions.BTARN.PipelineSend</span></span>  
  
    -   <span data-ttu-id="5062c-130">Microsoft.Solutions.BTARN.PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="5062c-130">Microsoft.Solutions.BTARN.PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="5062c-131">Microsoft.Solutions.BTARN.PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="5062c-131">Microsoft.Solutions.BTARN.PrivateResponder</span></span>  
  
    -   <span data-ttu-id="5062c-132">Microsoft.Solutions.BTARN.PublicInitiator</span><span class="sxs-lookup"><span data-stu-id="5062c-132">Microsoft.Solutions.BTARN.PublicInitiator</span></span>  
  
    -   <span data-ttu-id="5062c-133">Microsoft.Solutions.BTARN.PublicResponder</span><span class="sxs-lookup"><span data-stu-id="5062c-133">Microsoft.Solutions.BTARN.PublicResponder</span></span>  
  
    -   <span data-ttu-id="5062c-134">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span><span class="sxs-lookup"><span data-stu-id="5062c-134">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span></span>  
  
    -   <span data-ttu-id="5062c-135">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span><span class="sxs-lookup"><span data-stu-id="5062c-135">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span></span>  
  
    -   <span data-ttu-id="5062c-136">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span><span class="sxs-lookup"><span data-stu-id="5062c-136">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span></span>  
  
6.  <span data-ttu-id="5062c-137">Ejecute la instalación de BTARN.</span><span class="sxs-lookup"><span data-stu-id="5062c-137">Run the BTARN installation.</span></span> <span data-ttu-id="5062c-138">Consulte [instalar y configurar el Acelerador de RosettaNet](install-configure-biztalk-accelerator-for-rosettanet.md).</span><span class="sxs-lookup"><span data-stu-id="5062c-138">See [Install and configure the RosettaNet accelerator](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>
  
7.  <span data-ttu-id="5062c-139">Use **BTSTask.exe** (\Program Files\Microsoft BizTalk Server) volver a implementar manualmente los ensamblados BTARN en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="5062c-139">Use **BTSTask.exe** (\Program Files\Microsoft BizTalk Server) to manually redeploy the BTARN assemblies in the following order:</span></span>  
  
    -   <span data-ttu-id="5062c-140">Microsoft.Solutions.BTARN.CommonTypes</span><span class="sxs-lookup"><span data-stu-id="5062c-140">Microsoft.Solutions.BTARN.CommonTypes</span></span>  
  
    -   <span data-ttu-id="5062c-141">Microsoft.Solutions.BTARN.GlobalSchemas</span><span class="sxs-lookup"><span data-stu-id="5062c-141">Microsoft.Solutions.BTARN.GlobalSchemas</span></span>  
  
    -   <span data-ttu-id="5062c-142">Microsoft.Solutions.BTARN.PipelineReceive</span><span class="sxs-lookup"><span data-stu-id="5062c-142">Microsoft.Solutions.BTARN.PipelineReceive</span></span>  
  
    -   <span data-ttu-id="5062c-143">Microsoft.Solutions.BTARN.PipelineSend</span><span class="sxs-lookup"><span data-stu-id="5062c-143">Microsoft.Solutions.BTARN.PipelineSend</span></span>  
  
    -   <span data-ttu-id="5062c-144">Microsoft.Solutions.BTARN.PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="5062c-144">Microsoft.Solutions.BTARN.PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="5062c-145">Microsoft.Solutions.BTARN.PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="5062c-145">Microsoft.Solutions.BTARN.PrivateResponder</span></span>  
  
    -   <span data-ttu-id="5062c-146">Microsoft.Solutions.BTARN.PublicInitiator</span><span class="sxs-lookup"><span data-stu-id="5062c-146">Microsoft.Solutions.BTARN.PublicInitiator</span></span>  
  
    -   <span data-ttu-id="5062c-147">Microsoft.Solutions.BTARN.PublicResponder</span><span class="sxs-lookup"><span data-stu-id="5062c-147">Microsoft.Solutions.BTARN.PublicResponder</span></span>  
  
    -   <span data-ttu-id="5062c-148">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span><span class="sxs-lookup"><span data-stu-id="5062c-148">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span></span>  
  
    -   <span data-ttu-id="5062c-149">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span><span class="sxs-lookup"><span data-stu-id="5062c-149">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span></span>  
  
    -   <span data-ttu-id="5062c-150">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span><span class="sxs-lookup"><span data-stu-id="5062c-150">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5062c-151">Para obtener más información acerca de **BTSTask.exe**, vea el tema "Referencia de línea de comandos de BTSTask" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5062c-151">For more information about **BTSTask.exe**, see the "BTSTask Command-line Reference" topic in BizTalk Server Help.</span></span>  
  
8.  <span data-ttu-id="5062c-152">Volver a generar los proyectos o ensamblados que tienen una referencia a uno o varios de los [ensamblados BTARN.</span><span class="sxs-lookup"><span data-stu-id="5062c-152">Rebuild any projects or assemblies that have a reference to one or more of the [BTARN assemblies.</span></span> <span data-ttu-id="5062c-153">Use **BTSTask.exe** volver a implementar manualmente estos proyectos.</span><span class="sxs-lookup"><span data-stu-id="5062c-153">Use **BTSTask.exe** to manually redeploy these projects.</span></span>  
  
9. <span data-ttu-id="5062c-154">Actualice las carpetas virtuales en IIS de ASP.NET 2.0 a ASP.NET 4.0 para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5062c-154">Upgrade the virtual folders in IIS from ASP.NET 2.0 to ASP.NET 4.0 for the following:</span></span>  
  
    -   <span data-ttu-id="5062c-155">BTARNApp</span><span class="sxs-lookup"><span data-stu-id="5062c-155">BTARNApp</span></span>  
  
    -   <span data-ttu-id="5062c-156">BTARNHttpReceive</span><span class="sxs-lookup"><span data-stu-id="5062c-156">BTARNHttpReceive</span></span>  
  
10. <span data-ttu-id="5062c-157">Reinicie el equipo para aplicar las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="5062c-157">Restart the computer to apply any modifications done.</span></span>  
  
