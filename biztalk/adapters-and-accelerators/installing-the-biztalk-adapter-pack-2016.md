---
title: Instalar BizTalk Adapter Pack 2016 | Documentos de Microsoft
description: "La instalación típica o personalizada de BAP 2016, de 32 y 64 bits, instalar en modo silencioso"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f3e1717-8063-4460-bfdc-a933cd58a5c1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0939ddaa11e409ec42989062e28314c14277549
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="7b910-103">Instalar BizTalk Adapter Pack 2016</span><span class="sxs-lookup"><span data-stu-id="7b910-103">Install the BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="7b910-104">Instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b910-104">Install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="7b910-105">**En el modo interactivo**: ejecutar el Asistente para la instalación</span><span class="sxs-lookup"><span data-stu-id="7b910-105">**In interactive mode**: Run the setup wizard</span></span>  
  
-   <span data-ttu-id="7b910-106">**En modo silencioso**: usar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="7b910-106">**In silent mode**: Use the command line</span></span>  
  
> [!IMPORTANT]
> - <span data-ttu-id="7b910-107">Debe tener privilegios administrativos en el equipo donde se instala el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], independientemente de si está instalando utilizando el asistente o la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="7b910-107">You must have administrative privileges on the computer where you install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], irrespective of whether you are installing using the wizard, or the command line.</span></span>  
> - <span data-ttu-id="7b910-108">Estar seguro de que todos los [requisitos previos de software](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) instalado antes de instalar la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-108">Be sure all the [software prerequisites](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) are installed before installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>

## <a name="typical-vs-custom-installation"></a><span data-ttu-id="7b910-109">Instalación personalizada de vs típico</span><span class="sxs-lookup"><span data-stu-id="7b910-109">Typical vs custom installation</span></span>  
<span data-ttu-id="7b910-110">Enumera los tipos de instalación y las características que se instalan con cada opción:</span><span class="sxs-lookup"><span data-stu-id="7b910-110">Lists the installation types, and the features that are installed with each option:</span></span>  
  
-   <span data-ttu-id="7b910-111">El **típica** y **completar** opciones instalación todos los adaptadores, con los proveedores de datos asociados.</span><span class="sxs-lookup"><span data-stu-id="7b910-111">The **Typical** and **Complete** options install all the adapters, with the associated data providers.</span></span> <span data-ttu-id="7b910-112">No tiene la posibilidad de elegir un adaptador específico para instalar.</span><span class="sxs-lookup"><span data-stu-id="7b910-112">You do not have the option of choosing a specific adapter to install.</span></span>  
  
-   <span data-ttu-id="7b910-113">El **personalizado** opción instala uno o varios adaptadores, con los proveedores de datos asociados.</span><span class="sxs-lookup"><span data-stu-id="7b910-113">The **Custom** option installs one or more adapters, with the associated data providers.</span></span> <span data-ttu-id="7b910-114">Puede elegir qué adaptadores para instalar.</span><span class="sxs-lookup"><span data-stu-id="7b910-114">You can choose which adapters to install.</span></span> <span data-ttu-id="7b910-115">Si decide instalar a un proveedor de datos, también debe instalar al adaptador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7b910-115">If you choose to install a data provider, you must also install the corresponding adapter.</span></span> <span data-ttu-id="7b910-116">Sin embargo, puede instalar a un adaptador sin necesidad de instalar al proveedor de datos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7b910-116">However, you can install an adapter without installing the corresponding data provider.</span></span> <span data-ttu-id="7b910-117">Esto se hace al expandir el **ADO proveedores** nodo y, a continuación, seleccione los proveedores que no desea instalar.</span><span class="sxs-lookup"><span data-stu-id="7b910-117">Do this by expanding the **ADO Providers** node, and then selecting the providers that you don't want to install.</span></span> <span data-ttu-id="7b910-118">Vea **instalar mediante el Asistente para instalación** (en este tema).</span><span class="sxs-lookup"><span data-stu-id="7b910-118">See **Install using the setup wizard** (in this topic).</span></span>  
  
     <span data-ttu-id="7b910-119">Por ejemplo, si instala el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], también debe instalar la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-119">For example, if you install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], you must also install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="7b910-120">Sin embargo, puede instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] sin necesidad de instalar la [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-120">However, you can install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] without installing the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span>  
  
## <a name="32-bit-and-64-bit-install-scenarios"></a><span data-ttu-id="7b910-121">escenarios de instalación de 32 bits y 64 bits</span><span class="sxs-lookup"><span data-stu-id="7b910-121">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="7b910-122">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] puede utilizarse para:</span><span class="sxs-lookup"><span data-stu-id="7b910-122">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] can be used for:</span></span> 
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="7b910-123">tiempo de diseño (cuándo generar metadatos para las operaciones en las aplicaciones LOB)</span><span class="sxs-lookup"><span data-stu-id="7b910-123"> design time (when generating metadata for operations on LOB applications)</span></span>
  
-   <span data-ttu-id="7b910-124">Tiempo de diseño de consola de administración de BizTalk Server (para la creación de puertos físicos)</span><span class="sxs-lookup"><span data-stu-id="7b910-124">BizTalk Server Administration console design time (for creating physical ports)</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="7b910-125">Consola de administración de BizTalk Server se ejecuta como una aplicación de Microsoft Management Console (MMC) de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="7b910-125">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="7b910-126">Tiempo de ejecución de BizTalk (al enviar y recibir mensajes desde aplicaciones de LOB)</span><span class="sxs-lookup"><span data-stu-id="7b910-126">BizTalk run time (when sending and receiving messages from LOB applications)</span></span>

<span data-ttu-id="7b910-127">Puede usar un único equipo para todos estos tardará entre o utiliza equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="7b910-127">You can use a single computer for all these taks, or use different computers.</span></span> <span data-ttu-id="7b910-128">Dado que ambos [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y MMC de BizTalk son procesos de 32 bits, debe instalar el 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en el equipo donde se realizarán las tareas de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="7b910-128">Because both [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on the computer where you complete the design-time tasks.</span></span> 

### <a name="32-bit-install-scenario"></a><span data-ttu-id="7b910-129">escenario de instalación de 32 bits</span><span class="sxs-lookup"><span data-stu-id="7b910-129">32-bit install scenario</span></span>
<span data-ttu-id="7b910-130">Instalar el software siguiente en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="7b910-130">Install the following software on each computer.</span></span> <span data-ttu-id="7b910-131">Si está utilizando un único equipo, todo el software debe instalarse en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7b910-131">If you are using a single computer, all the software must be installed on that computer.</span></span> 
 
1. <span data-ttu-id="7b910-132">Instalación de 32 bits[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b910-132">Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</span></span>
2. <span data-ttu-id="7b910-133">Instalación de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-133">Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>
3. <span data-ttu-id="7b910-134">Cliente LOB de 32 bits de instalación y otro requieren archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="7b910-134">Install 32-bit LOB client and other required DLLs.</span></span>  
  
### <a name="64-bit-install-scenarios"></a><span data-ttu-id="7b910-135">escenarios de instalación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="7b910-135">64-bit install scenarios</span></span>
  
|<span data-ttu-id="7b910-136">Para tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b910-136">For Visual Studio design time</span></span>|<span data-ttu-id="7b910-137">MMC de BizTalk para tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="7b910-137">For BizTalk MMC design time</span></span>|<span data-ttu-id="7b910-138">Tiempo de ejecución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7b910-138">For BizTalk run time</span></span>|<span data-ttu-id="7b910-139">Para el diseño de Visual Studio de hora o tiempo de diseño de BizTalk MMC + BizTalk tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7b910-139">For Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="7b910-140">-Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-140">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-141">-Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-141">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-142">-Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="7b910-142">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="7b910-143">-Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-143">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-144">-Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-144">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-145">-Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="7b910-145">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="7b910-146">**Para un proceso de BizTalk de 32 bits**:</span><span class="sxs-lookup"><span data-stu-id="7b910-146">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="7b910-147">-Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-147">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-148">-Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-148">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-149">-Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="7b910-149">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="7b910-150">**Para un proceso de BizTalk de 64 bits**:</span><span class="sxs-lookup"><span data-stu-id="7b910-150">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="7b910-151">-Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-151">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-152">-Instalar 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-152">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-153">-Instalar el cliente de 64 bits de LOB y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="7b910-153">- Install 64-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="7b910-154">**Para un proceso de BizTalk de 32 bits**:</span><span class="sxs-lookup"><span data-stu-id="7b910-154">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="7b910-155">-Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-155">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-156">-Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-156">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-157">-Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="7b910-157">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="7b910-158">**Para un proceso de BizTalk de 64 bits**:</span><span class="sxs-lookup"><span data-stu-id="7b910-158">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="7b910-159">-Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-159">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-160">-Instalar 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-160">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-161">-Instalar el cliente de 64 bits de LOB y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="7b910-161">- Install 64-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="7b910-162">-Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-162">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="7b910-163">-Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.</span><span class="sxs-lookup"><span data-stu-id="7b910-163">- Install 32-bit LOB client and other required DLLs.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7b910-164">En cualquier equipo donde desea realizar tareas de tiempo de diseño, utilizando [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] o MMC de BizTalk, debe instalar lo 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-164">On any computer where you want to do design-time tasks, using either [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="install-using-the-setup-wizard"></a><span data-ttu-id="7b910-165">Instalar mediante el Asistente para la instalación</span><span class="sxs-lookup"><span data-stu-id="7b910-165">Install using the setup wizard</span></span>  
<span data-ttu-id="7b910-166">Pasos para instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en modo interactivo.</span><span class="sxs-lookup"><span data-stu-id="7b910-166">Steps to install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in interactive mode.</span></span>  
  
1.  <span data-ttu-id="7b910-167">Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**.</span><span class="sxs-lookup"><span data-stu-id="7b910-167">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**.</span></span>  
  
2.  <span data-ttu-id="7b910-168">Seleccione **instalar adaptadores de Microsoft BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="7b910-168">Select **Install Microsoft BizTalk Adapters**.</span></span> <span data-ttu-id="7b910-169">En la ventana siguiente, se enumeran los programas de requisitos previos que falten.</span><span class="sxs-lookup"><span data-stu-id="7b910-169">In the next window, any missing prerequisite programs are listed.</span></span> <span data-ttu-id="7b910-170">Si falta alguno, a continuación, seleccione el programa que falta y el programa de instalación lo instala automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7b910-170">If any are missing, then select the missing program, and setup installs it for you.</span></span> 

    <span data-ttu-id="7b910-171">Por ejemplo, seleccione **paso 2: instalar Microsoft BizTalk Adapter Pack** o **paso 3: instalar Microsoft BizTalk Adapter Pack (x64)**.</span><span class="sxs-lookup"><span data-stu-id="7b910-171">For example, select **Step 2: Install Microsoft BizTalk Adapter Pack** or **Step 3: Install Microsoft BizTalk Adapter Pack (x64)**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7b910-172">Si va a instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en una máquina virtual, el Asistente para instalación puede mostrar un mensaje que se comprueba si hay espacio disponible en disco.</span><span class="sxs-lookup"><span data-stu-id="7b910-172">If you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on a virtual machine, the setup wizard may display a message that it's checking for available disk space.</span></span> <span data-ttu-id="7b910-173">Si aparece este mensaje de bloqueo o simplemente sentarse, le recomendamos que **instalar en modo silencioso** (en este tema).</span><span class="sxs-lookup"><span data-stu-id="7b910-173">If this message appears to hang or just sit there, then we recommend you **Install in silent mode** (in this topic).</span></span>  
  
3.  <span data-ttu-id="7b910-174">En la pantalla de bienvenida, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7b910-174">On the Welcome screen, select **Next**.</span></span>  
  
4.  <span data-ttu-id="7b910-175">Acepte el contrato de licencia para el usuario final (CLUF) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7b910-175">Accept the end-user license agreement (EULA), and then select **Next**.</span></span>  
  
5.  <span data-ttu-id="7b910-176">En **Elegir tipo de instalación**:</span><span class="sxs-lookup"><span data-stu-id="7b910-176">In **Choose Setup Type**:</span></span>  
  
    -   <span data-ttu-id="7b910-177">Para instalar las características más comunes, seleccione **típica**.</span><span class="sxs-lookup"><span data-stu-id="7b910-177">To install the most common features, select **Typical**.</span></span>  
  
    -   <span data-ttu-id="7b910-178">Para seleccionar los adaptadores que desea instalar, seleccione **personalizada**y, a continuación, continúe con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="7b910-178">To select the adapters you want to install, select **Custom**, and then proceed to the next step.</span></span>  
  
    -   <span data-ttu-id="7b910-179">Para instalar todas las características, seleccione **completar**.</span><span class="sxs-lookup"><span data-stu-id="7b910-179">To install all the features, select **Complete**.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="7b910-180">Para instalar sólo el adaptador que usa para comunicarse con la aplicación de empresa, seleccione la **personalizado** instalación.</span><span class="sxs-lookup"><span data-stu-id="7b910-180">To install only the adapter that you use to interface with your enterprise application, select the **Custom** installation.</span></span>  
  
6. <span data-ttu-id="7b910-181">**Necesario** sólo si eligió la instalación personalizada.</span><span class="sxs-lookup"><span data-stu-id="7b910-181">**Required** only if you chose the Custom installation.</span></span> <span data-ttu-id="7b910-182">Si ha elegido el **típica** o **completar** instalación, a continuación, omita este paso y vaya al paso 7.</span><span class="sxs-lookup"><span data-stu-id="7b910-182">If you chose the **Typical** or **Complete** installation, then skip this step, and go to step 7.</span></span>  
  
    1.  <span data-ttu-id="7b910-183">En **personalizada**, expanda **Base adaptadores** para ver el número de adaptadores disponible.</span><span class="sxs-lookup"><span data-stu-id="7b910-183">In **Custom Setup**, expand **Base Adapters** to see the available adapters.</span></span>  
  
    2.  <span data-ttu-id="7b910-184">Para los adaptadores que no desea, seleccione el icono al lado del adaptador y, a continuación, seleccione **característica completa no estará disponible**.</span><span class="sxs-lookup"><span data-stu-id="7b910-184">For the adapters that you don't want, select the icon next to the adapter, and then select **Entire feature will be unavailable**.</span></span>  
  
    3.  <span data-ttu-id="7b910-185">Expanda **ADO proveedores**y, a continuación, seleccione los proveedores que no desea instalar.</span><span class="sxs-lookup"><span data-stu-id="7b910-185">Expand **ADO Providers**, and then select the providers that you don't want to install.</span></span>  
  
    4.  <span data-ttu-id="7b910-186">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7b910-186">Select **Next**.</span></span>  
  
7.  <span data-ttu-id="7b910-187">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="7b910-187">Select **Install**.</span></span>  
  
8.  <span data-ttu-id="7b910-188">En **Customer Experience Improvement Program**, puede elegir para inscribirse.</span><span class="sxs-lookup"><span data-stu-id="7b910-188">In **Customer Experience Improvement Program**, you can choose to enroll.</span></span> <span data-ttu-id="7b910-189">Si inscribe, puede compartir los siguientes datos con Microsoft:</span><span class="sxs-lookup"><span data-stu-id="7b910-189">If you enroll, you can share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="7b910-190">Datos relacionados con el hardware del equipo en el que va a instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-190">Data related to the computer hardware on which you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="7b910-191">Datos relacionados con las versiones de aplicación de empresa que usa con la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-191">Data related to the enterprise application versions you are using with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
     <span data-ttu-id="7b910-192">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699) proporciona más información.</span><span class="sxs-lookup"><span data-stu-id="7b910-192">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699) provides more information.</span></span>  
     
     <span data-ttu-id="7b910-193">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b910-193">Select **OK**.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="7b910-194">Siempre puede cambiar esta configuración mediante la ejecución de la instalación en modo de reparación de **programas**.</span><span class="sxs-lookup"><span data-stu-id="7b910-194">You can always change this setting by running the Setup in Repair mode from **Programs**.</span></span>  
  
9. <span data-ttu-id="7b910-195">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7b910-195">Select **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
## <a name="install-in-silent-mode"></a><span data-ttu-id="7b910-196">Instalar en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="7b910-196">Install in silent mode</span></span>  
 <span data-ttu-id="7b910-197">Use la **msiexec** comando para realizar una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="7b910-197">Use the **msiexec** command to do a silent installation.</span></span> <span data-ttu-id="7b910-198">Como parte del comando msiexec, escriba los componentes individuales que desea instalar.</span><span class="sxs-lookup"><span data-stu-id="7b910-198">As part of the msiexec command, enter the individual components that you want to install.</span></span> <span data-ttu-id="7b910-199">En la tabla siguiente se enumera los valores para cada componente en el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b910-199">The following table lists the values for each component in the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="7b910-200">Utilice estos valores para instalar componentes específicos (o quitar).</span><span class="sxs-lookup"><span data-stu-id="7b910-200">Use these values to install (or remove) specific components.</span></span> <span data-ttu-id="7b910-201">Para instalar (o quitar) más de un componente, puede usar una combinación de estos valores separados por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="7b910-201">To install (or remove) more than one component, you can use a combination of these values separated by a comma.</span></span>  
  
|<span data-ttu-id="7b910-202">Nombre de componente</span><span class="sxs-lookup"><span data-stu-id="7b910-202">Component name</span></span>|<span data-ttu-id="7b910-203">Valor correspondiente para las propiedades de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="7b910-203">Corresponding value for command-line properties</span></span>|  
|---|---|  
|[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|<span data-ttu-id="7b910-204">DbFeature</span><span class="sxs-lookup"><span data-stu-id="7b910-204">DbFeature</span></span>|  
|[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="7b910-205">OracleEBSFeature</span><span class="sxs-lookup"><span data-stu-id="7b910-205">OracleEBSFeature</span></span>|  
|[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|<span data-ttu-id="7b910-206">SapBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="7b910-206">SapBaseAdapterFeature</span></span>|  
|[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|<span data-ttu-id="7b910-207">SiebelBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="7b910-207">SiebelBaseAdapterFeature</span></span>|  
|[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|<span data-ttu-id="7b910-208">SqlFeature</span><span class="sxs-lookup"><span data-stu-id="7b910-208">SqlFeature</span></span>|  
|[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|<span data-ttu-id="7b910-209">SapAdoFeature</span><span class="sxs-lookup"><span data-stu-id="7b910-209">SapAdoFeature</span></span><br /><br /> <span data-ttu-id="7b910-210">**Tenga en cuenta**: debe proporcionar este valor solo si va a instalar la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] también.</span><span class="sxs-lookup"><span data-stu-id="7b910-210">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] also.</span></span>|  
|[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|<span data-ttu-id="7b910-211">SiebelAdoFeature</span><span class="sxs-lookup"><span data-stu-id="7b910-211">SiebelAdoFeature</span></span><br /><br /> <span data-ttu-id="7b910-212">**Tenga en cuenta**: debe proporcionar este valor solo si va a instalar la [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] también.</span><span class="sxs-lookup"><span data-stu-id="7b910-212">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] also.</span></span>|  
|<span data-ttu-id="7b910-213">Todos los componentes</span><span class="sxs-lookup"><span data-stu-id="7b910-213">All components</span></span>|<span data-ttu-id="7b910-214">ALL</span><span class="sxs-lookup"><span data-stu-id="7b910-214">ALL</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="7b910-215">Los nombres de función distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7b910-215">The feature names are case-sensitive.</span></span>  
  
 <span data-ttu-id="7b910-216">Los pasos siguientes muestran cómo realizar una instalación silenciosa de [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para los distintos componentes.</span><span class="sxs-lookup"><span data-stu-id="7b910-216">The following steps show you how to complete a silent installation of [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] for different components.</span></span>  
  
### <a name="silent-mode-steps"></a><span data-ttu-id="7b910-217">Pasos de modo silencioso</span><span class="sxs-lookup"><span data-stu-id="7b910-217">Silent mode steps</span></span>
  
1.  <span data-ttu-id="7b910-218">Abra un símbolo del sistema y vaya a la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] raíz en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="7b910-218">Open a command prompt, and go to the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] root in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span>  
  
2.  <span data-ttu-id="7b910-219">Ejecute los comandos siguientes en función de lo que va a instalar:</span><span class="sxs-lookup"><span data-stu-id="7b910-219">Run the following commands based on what you want to install:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7b910-220">Para realizar una instalación silenciosa en una plataforma basada en x64, reemplace `AdaptersSetup.msi` con `AdaptersSetup64.msi` en los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="7b910-220">To do silent installation on an x64-based platform, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi` in the following commands.</span></span>  
  
    -   <span data-ttu-id="7b910-221">Para llevar a cabo una instalación completa, que se instala todos los adaptadores incluidos los proveedores de datos de .NET Framework, escriba:</span><span class="sxs-lookup"><span data-stu-id="7b910-221">To perform a complete installation, which installs all the adapters including the .NET Framework Data Providers, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
        ```  
  
    -   <span data-ttu-id="7b910-222">Para instalar solo la [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], tipo:</span><span class="sxs-lookup"><span data-stu-id="7b910-222">To install only the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
        ```  
  
    -   <span data-ttu-id="7b910-223">Para instalar solo la [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], tipo:</span><span class="sxs-lookup"><span data-stu-id="7b910-223">To install only the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
        ```  
  
    -   <span data-ttu-id="7b910-224">Para instalar solo la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], tipo:</span><span class="sxs-lookup"><span data-stu-id="7b910-224">To install only the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="7b910-225">Para instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] junto con [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], tipo:</span><span class="sxs-lookup"><span data-stu-id="7b910-225">To install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] along with [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
        ```  
  
    -   <span data-ttu-id="7b910-226">Para instalar solo la [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], tipo:</span><span class="sxs-lookup"><span data-stu-id="7b910-226">To install only the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="7b910-227">Para instalar el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] junto con [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], tipo:</span><span class="sxs-lookup"><span data-stu-id="7b910-227">To install the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] along with [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
        ```  
  
    -   <span data-ttu-id="7b910-228">Para instalar solo la [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], tipo:</span><span class="sxs-lookup"><span data-stu-id="7b910-228">To install only the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
        ```  
  
    -   <span data-ttu-id="7b910-229">Para instalar a todos los adaptadores de base, escriba:</span><span class="sxs-lookup"><span data-stu-id="7b910-229">To install all the base adapters, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
        ```  
  
    -   <span data-ttu-id="7b910-230">Para instalar a los dos proveedores de datos de .NET Framework, escriba:</span><span class="sxs-lookup"><span data-stu-id="7b910-230">To install the two .NET Framework Data Providers, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
        ```  
  
    -   <span data-ttu-id="7b910-231">Cualquier tipo de instalación personalizada mediante la separación de los componentes por una coma.</span><span class="sxs-lookup"><span data-stu-id="7b910-231">Any type of custom installation by separating the components by a comma.</span></span> <span data-ttu-id="7b910-232">Por ejemplo, para instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] con el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]y el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] tipo:</span><span class="sxs-lookup"><span data-stu-id="7b910-232">For example, to install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] with the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], and the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="7b910-233">También puede optar por inscribirse en CEIP como parte de la instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="7b910-233">You can also opt to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="7b910-234">Tipo:</span><span class="sxs-lookup"><span data-stu-id="7b910-234">Type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
        ```  
  
         <span data-ttu-id="7b910-235">De forma predeterminada, la opción es false.</span><span class="sxs-lookup"><span data-stu-id="7b910-235">By default the option is false.</span></span> 
  
        > [!IMPORTANT]
        >  <span data-ttu-id="7b910-236">Al instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] versión de evaluación en modo silencioso, la opción predeterminada para el CEIP es true.</span><span class="sxs-lookup"><span data-stu-id="7b910-236">While installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Evaluation version in silent mode, the default option for CEIP is true.</span></span>  
  
     <span data-ttu-id="7b910-237">Para obtener más información sobre la **msiexec** de comandos, escriba `msiexec` en la línea de comandos y presione `ENTER`.</span><span class="sxs-lookup"><span data-stu-id="7b910-237">For more information about the **msiexec** command, type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="7b910-238">O vaya a [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span><span class="sxs-lookup"><span data-stu-id="7b910-238">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
     
## <a name="known-install-issue"></a><span data-ttu-id="7b910-239">Problema de instalación conocidos</span><span class="sxs-lookup"><span data-stu-id="7b910-239">Known install issue</span></span>
<span data-ttu-id="7b910-240">Para obtener una lista completa de los problemas relacionados con la instalación, consulte **solución de problemas** para cada adaptador.</span><span class="sxs-lookup"><span data-stu-id="7b910-240">For a comprehensive list of installation-related issues, refer to **Troubleshooting** topics for each adapter.</span></span>  
  
<span data-ttu-id="7b910-241">**Ejecuta la instalación en un equipo de 64 bits puede producir un error al obtener acceso al archivo de esquema**</span><span class="sxs-lookup"><span data-stu-id="7b910-241">**Running setup on a 64-bit computer may throw an error while accessing schema file**</span></span>  
  
<span data-ttu-id="7b910-242">El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] el programa de instalación produce un error al obtener acceso a la Microsoft.Adapters. *\<AdapterName >*_schema.xml archivo, pero continúa con la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="7b910-242">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup throws an error while accessing the Microsoft.Adapters.*\<AdapterName>*_schema.xml file, but proceeds with the adapter installation.</span></span>  
  
<span data-ttu-id="7b910-243">**Causa**</span><span class="sxs-lookup"><span data-stu-id="7b910-243">**Cause**</span></span>  
  
<span data-ttu-id="7b910-244">Si las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] están instalados en el mismo equipo, el archivo de esquema de destino utilizado es el mismo.</span><span class="sxs-lookup"><span data-stu-id="7b910-244">If both 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] are installed on the same computer, the target schema file used by both is the same.</span></span> <span data-ttu-id="7b910-245">Como resultado, se instala el archivo de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] podría estar utilizando IIS cuando el programa de instalación de 64 bits intenta tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="7b910-245">As a result, the file installed by the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] might be in use by IIS when the 64-bit installer tries to access it.</span></span>  
  
<span data-ttu-id="7b910-246">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="7b910-246">**Resolution**</span></span>  
  
<span data-ttu-id="7b910-247">Copie manualmente el Microsoft.Adapters.  *\<AdapterName >*archivo _schema.xml desde *C:\Program Files\Microsoft BizTalk adaptador Pack (x64) \IIS esquemas* a *C:\Windows\System32\inetsrv\config\schema* .</span><span class="sxs-lookup"><span data-stu-id="7b910-247">Manually copy the Microsoft.Adapters.*\<AdapterName>*_schema.xml file from *C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas* to *C:\Windows\System32\inetsrv\config\schema*.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="7b910-248">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7b910-248">Next step</span></span>
[<span data-ttu-id="7b910-249">Pasos posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="7b910-249">Post installation steps</span></span>](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)