---
title: Actualizar acelerador para RosettaNet (BTARN) en BizTalk Server | Documentos de Microsoft"
description: "Siga los pasos de actualización para actualizar BTARN a la versión actual de BizTalk Server"
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
ms.author: mandia
ms.openlocfilehash: 16e6083f3e5fb1778d77536cd602ee2208c0005f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-the-rosettanet-accelerator"></a><span data-ttu-id="0f718-103">Actualización del Acelerador para RosettaNet</span><span class="sxs-lookup"><span data-stu-id="0f718-103">Upgrade the RosettaNet accelerator</span></span>

## <a name="upgrade-overview"></a><span data-ttu-id="0f718-104">Información general sobre la actualización</span><span class="sxs-lookup"><span data-stu-id="0f718-104">Upgrade overview</span></span>
<span data-ttu-id="0f718-105">Puede actualizar la versión anterior del Acelerador de BizTalk para la instalación de RosettaNet (BTARN) a la versión actual.</span><span class="sxs-lookup"><span data-stu-id="0f718-105">You can upgrade the previous version of the BizTalk Accelerator for RosettaNet (BTARN) installation to the current version.</span></span> <span data-ttu-id="0f718-106">El proceso de actualización implica la actualización del servidor BizTalk Server y, a continuación, BTARN.</span><span class="sxs-lookup"><span data-stu-id="0f718-106">The upgrade process involves upgrading BizTalk Server, and then upgrading BTARN.</span></span>  
  
 <span data-ttu-id="0f718-107">Puede actualizar desde la versión anterior de BTARN a un ejecutando el programa de instalación de BTARN.</span><span class="sxs-lookup"><span data-stu-id="0f718-107">You can upgrade from the previous version of BTARN to a by running the BTARN installation program.</span></span> <span data-ttu-id="0f718-108">El programa de instalación migra la información de configuración de BTRAN a la versión actual.</span><span class="sxs-lookup"><span data-stu-id="0f718-108">The setup migrates the BTRAN configuration information to the current version.</span></span>  
  
 <span data-ttu-id="0f718-109">En un entorno de BTARN de varios servidores, debe actualizar todos los servidores de BizTalk en primer lugar y, a continuación, BTARN.</span><span class="sxs-lookup"><span data-stu-id="0f718-109">In a multi-server BTARN environment, you should upgrade all BizTalk Servers first, and then to BTARN.</span></span> <span data-ttu-id="0f718-110">Migre los servidores en este orden:</span><span class="sxs-lookup"><span data-stu-id="0f718-110">Migrate your servers in the following order:</span></span>  
  
-   <span data-ttu-id="0f718-111">Servidor que hospeda el grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="0f718-111">The server hosting the BizTalk Group</span></span>  
  
-   <span data-ttu-id="0f718-112">Cada nodo de procesamiento</span><span class="sxs-lookup"><span data-stu-id="0f718-112">Each processing node</span></span>  
  
-   <span data-ttu-id="0f718-113">Servidor del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="0f718-113">The BAM portal server</span></span>  
  
 <span data-ttu-id="0f718-114">En el BTARN proceso de actualización, asegúrese de que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f718-114">In the BTARN upgrade process, ensure you do the following:</span></span>  
  
-   <span data-ttu-id="0f718-115">Compruebe si el servicio SQL Server (MSSQLSERVER) está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="0f718-115">Check if the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
-   <span data-ttu-id="0f718-116">No realice una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="0f718-116">Do not run a silent installation.</span></span>  
  
## <a name="upgrade-steps"></a><span data-ttu-id="0f718-117">Pasos de la actualización</span><span class="sxs-lookup"><span data-stu-id="0f718-117">Upgrade steps</span></span>  
  
1.  <span data-ttu-id="0f718-118">Actualización de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0f718-118">Upgrade BizTalk Server.</span></span> <span data-ttu-id="0f718-119">Vea [BizTalk Server What's New, instalación, configuración y actualización](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="0f718-119">See [BizTalk Server What's New, Installation, Configuration, and Upgrade](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
  
2.  <span data-ttu-id="0f718-120">Realizar una copia de la base de datos BTARN y esquemas de mensajes BTARN.</span><span class="sxs-lookup"><span data-stu-id="0f718-120">Back up the BTARN database and BTARN message schemas.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f718-121">Debe realizar una copia de la base de datos BTARN por razones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0f718-121">You should back up the BTARN database for safety reasons.</span></span> <span data-ttu-id="0f718-122">El programa de instalación migra la base de datos BTRAN a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="0f718-122">The installation program migrates the BTRAN database to the newer version.</span></span>  
  
3.  <span data-ttu-id="0f718-123">Los archivos de copia de seguridad la *< unidad\>*: \Program archivos\\Acelerador de Microsoft BizTalk para RosettaNet carpeta que ha realizado cambios en, por ejemplo, archivos en el SDK.</span><span class="sxs-lookup"><span data-stu-id="0f718-123">Back up any files under the *<drive\>*:\Program Files\\Microsoft BizTalk Accelerator for RosettaNet folder that you have made changes to, for example, files in the SDK.</span></span>  
  
4.  <span data-ttu-id="0f718-124">Anule la implementación de los proyectos o ensamblados que tengan referencias a una o varias versiones anteriores de los ensamblados de BTARN.</span><span class="sxs-lookup"><span data-stu-id="0f718-124">Undeploy any projects or assemblies that have references to one or more of the previous versions of BTARN assemblies.</span></span>  
  
5.  <span data-ttu-id="0f718-125">En Visual Studio, manualmente anular la implementación de todos los ensamblados BTARN, en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f718-125">In Visual Studio, manually undeploy all BTARN assemblies, in the following order:</span></span>  
  
    -   <span data-ttu-id="0f718-126">Microsoft.Solutions.BTARN.CommonTypes</span><span class="sxs-lookup"><span data-stu-id="0f718-126">Microsoft.Solutions.BTARN.CommonTypes</span></span>  
  
    -   <span data-ttu-id="0f718-127">Microsoft.Solutions.BTARN.GlobalSchemas</span><span class="sxs-lookup"><span data-stu-id="0f718-127">Microsoft.Solutions.BTARN.GlobalSchemas</span></span>  
  
    -   <span data-ttu-id="0f718-128">Microsoft.Solutions.BTARN.PipelineReceive</span><span class="sxs-lookup"><span data-stu-id="0f718-128">Microsoft.Solutions.BTARN.PipelineReceive</span></span>  
  
    -   <span data-ttu-id="0f718-129">Microsoft.Solutions.BTARN.PipelineSend</span><span class="sxs-lookup"><span data-stu-id="0f718-129">Microsoft.Solutions.BTARN.PipelineSend</span></span>  
  
    -   <span data-ttu-id="0f718-130">Microsoft.Solutions.BTARN.PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="0f718-130">Microsoft.Solutions.BTARN.PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="0f718-131">Microsoft.Solutions.BTARN.PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="0f718-131">Microsoft.Solutions.BTARN.PrivateResponder</span></span>  
  
    -   <span data-ttu-id="0f718-132">Microsoft.Solutions.BTARN.PublicInitiator</span><span class="sxs-lookup"><span data-stu-id="0f718-132">Microsoft.Solutions.BTARN.PublicInitiator</span></span>  
  
    -   <span data-ttu-id="0f718-133">Microsoft.Solutions.BTARN.PublicResponder</span><span class="sxs-lookup"><span data-stu-id="0f718-133">Microsoft.Solutions.BTARN.PublicResponder</span></span>  
  
    -   <span data-ttu-id="0f718-134">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span><span class="sxs-lookup"><span data-stu-id="0f718-134">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span></span>  
  
    -   <span data-ttu-id="0f718-135">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span><span class="sxs-lookup"><span data-stu-id="0f718-135">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span></span>  
  
    -   <span data-ttu-id="0f718-136">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span><span class="sxs-lookup"><span data-stu-id="0f718-136">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span></span>  
  
6.  <span data-ttu-id="0f718-137">Ejecutar la instalación de BTARN.</span><span class="sxs-lookup"><span data-stu-id="0f718-137">Run the BTARN installation.</span></span> <span data-ttu-id="0f718-138">Vea [instalar y configurar el Acelerador para RosettaNet](install-configure-biztalk-accelerator-for-rosettanet.md).</span><span class="sxs-lookup"><span data-stu-id="0f718-138">See [Install and configure the RosettaNet accelerator](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>
  
7.  <span data-ttu-id="0f718-139">Use **BTSTask.exe** (\Program BizTalk Server) para volver a implementar manualmente los ensamblados BTARN en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="0f718-139">Use **BTSTask.exe** (\Program Files\Microsoft BizTalk Server) to manually redeploy the BTARN assemblies in the following order:</span></span>  
  
    -   <span data-ttu-id="0f718-140">Microsoft.Solutions.BTARN.CommonTypes</span><span class="sxs-lookup"><span data-stu-id="0f718-140">Microsoft.Solutions.BTARN.CommonTypes</span></span>  
  
    -   <span data-ttu-id="0f718-141">Microsoft.Solutions.BTARN.GlobalSchemas</span><span class="sxs-lookup"><span data-stu-id="0f718-141">Microsoft.Solutions.BTARN.GlobalSchemas</span></span>  
  
    -   <span data-ttu-id="0f718-142">Microsoft.Solutions.BTARN.PipelineReceive</span><span class="sxs-lookup"><span data-stu-id="0f718-142">Microsoft.Solutions.BTARN.PipelineReceive</span></span>  
  
    -   <span data-ttu-id="0f718-143">Microsoft.Solutions.BTARN.PipelineSend</span><span class="sxs-lookup"><span data-stu-id="0f718-143">Microsoft.Solutions.BTARN.PipelineSend</span></span>  
  
    -   <span data-ttu-id="0f718-144">Microsoft.Solutions.BTARN.PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="0f718-144">Microsoft.Solutions.BTARN.PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="0f718-145">Microsoft.Solutions.BTARN.PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="0f718-145">Microsoft.Solutions.BTARN.PrivateResponder</span></span>  
  
    -   <span data-ttu-id="0f718-146">Microsoft.Solutions.BTARN.PublicInitiator</span><span class="sxs-lookup"><span data-stu-id="0f718-146">Microsoft.Solutions.BTARN.PublicInitiator</span></span>  
  
    -   <span data-ttu-id="0f718-147">Microsoft.Solutions.BTARN.PublicResponder</span><span class="sxs-lookup"><span data-stu-id="0f718-147">Microsoft.Solutions.BTARN.PublicResponder</span></span>  
  
    -   <span data-ttu-id="0f718-148">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span><span class="sxs-lookup"><span data-stu-id="0f718-148">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span></span>  
  
    -   <span data-ttu-id="0f718-149">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span><span class="sxs-lookup"><span data-stu-id="0f718-149">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span></span>  
  
    -   <span data-ttu-id="0f718-150">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span><span class="sxs-lookup"><span data-stu-id="0f718-150">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f718-151">Para obtener más información acerca de **BTSTask.exe**, vea el tema "Referencia de línea de comandos de BTSTask" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0f718-151">For more information about **BTSTask.exe**, see the "BTSTask Command-line Reference" topic in BizTalk Server Help.</span></span>  
  
8.  <span data-ttu-id="0f718-152">Volver a generar los proyectos o ensamblados que tienen una referencia a uno o varios de los [ensamblados BTARN.</span><span class="sxs-lookup"><span data-stu-id="0f718-152">Rebuild any projects or assemblies that have a reference to one or more of the [BTARN assemblies.</span></span> <span data-ttu-id="0f718-153">Use **BTSTask.exe** para volver a implementar manualmente estos proyectos.</span><span class="sxs-lookup"><span data-stu-id="0f718-153">Use **BTSTask.exe** to manually redeploy these projects.</span></span>  
  
9. <span data-ttu-id="0f718-154">Actualice las carpetas virtuales en IIS de ASP.NET 2.0 a ASP.NET 4.0 para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f718-154">Upgrade the virtual folders in IIS from ASP.NET 2.0 to ASP.NET 4.0 for the following:</span></span>  
  
    -   <span data-ttu-id="0f718-155">BTARNApp</span><span class="sxs-lookup"><span data-stu-id="0f718-155">BTARNApp</span></span>  
  
    -   <span data-ttu-id="0f718-156">BTARNHttpReceive</span><span class="sxs-lookup"><span data-stu-id="0f718-156">BTARNHttpReceive</span></span>  
  
10. <span data-ttu-id="0f718-157">Reinicie el equipo para aplicar las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="0f718-157">Restart the computer to apply any modifications done.</span></span>  
  
