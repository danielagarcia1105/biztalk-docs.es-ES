---
title: Cómo instalar un ensamblado en la GAC | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6afc2f81-fa28-4144-b4bd-21c8f35f2270
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e843d74b5420f8973f9d3663cfd05210c26996
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752369"
---
# <a name="how-to-install-an-assembly-in-the-gac"></a><span data-ttu-id="b52a6-102">Cómo instalar un ensamblado en la GAC</span><span class="sxs-lookup"><span data-stu-id="b52a6-102">How to Install an Assembly in the GAC</span></span>
<span data-ttu-id="b52a6-103">Instalar y desinstalar un ensamblado de BizTalk en la memoria caché global de ensamblados (GAC) mediante la herramienta Gacutil incluida con manualmente [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b52a6-103">Manually install and uninstall a BizTalk assembly in the global assembly cache (GAC) using the Gacutil tool included with [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b52a6-104">Uso de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], puede hacer que los ensamblados de BizTalk se instala automáticamente en la GAC cuando se implementan desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b52a6-104">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can have BizTalk assemblies automatically installed in the GAC when they are deployed from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="b52a6-105">Establezca esta opción en las propiedades de implementación del proyecto de BizTalk; consulte [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="b52a6-105">Set this option in the Deployment Properties of the BizTalk project; see [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span> <span data-ttu-id="b52a6-106">No puede utilizar este método para instalar los ensamblados de .NET que no sean de BizTalk en la GAC; debe instalarlos manualmente, tal como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="b52a6-106">You cannot, use this method to install non-BizTalk .NET assemblies in the GAC; you must install them manually, as described in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b52a6-107">También se pueden especificar opciones de implementación para ensamblados una vez implementados en una aplicación de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b52a6-107">You can also specify deployment options for assemblies after they are deployed into a BizTalk application by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b52a6-108">Consulte [cómo modificar las opciones de implementación de un ensamblado de BizTalk](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md), y [cómo modificar las opciones de implementación de un ensamblado .NET, un componente COM, un archivo o un artefacto de BAM](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md).</span><span class="sxs-lookup"><span data-stu-id="b52a6-108">See [How to Modify the Deployment Options of a BizTalk Assembly](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md), and [How to Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b52a6-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b52a6-109">Prerequisites</span></span>  
<span data-ttu-id="b52a6-110">Inicie sesión con una cuenta que tenga permiso de escritura en la GAC.</span><span class="sxs-lookup"><span data-stu-id="b52a6-110">Sign in with an account that has Write permission to the GAC.</span></span> <span data-ttu-id="b52a6-111">La cuenta de administradores del equipo local cuenta con este permiso.</span><span class="sxs-lookup"><span data-stu-id="b52a6-111">The Administrators account on the local computer has this permission.</span></span>  

  
## <a name="install-using-gacutil"></a><span data-ttu-id="b52a6-112">Instalación mediante gacutil</span><span class="sxs-lookup"><span data-stu-id="b52a6-112">Install using gacutil</span></span>
  
1.  <span data-ttu-id="b52a6-113">Copie el ensamblado de BizTalk en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b52a6-113">Copy the BizTalk assembly to your local computer.</span></span>  
  
2.  <span data-ttu-id="b52a6-114">Abra **símbolo del sistema para desarrolladores de Visual Studio** como administrador.</span><span class="sxs-lookup"><span data-stu-id="b52a6-114">Open **Developer Command Prompt for Visual Studio** as administrator.</span></span>  
  
3.  <span data-ttu-id="b52a6-115">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b52a6-115">Type the following:</span></span>  
  
     `gacutil /i path_to_assembly_file /f`

    <span data-ttu-id="b52a6-116">Por ejemplo, escriba:</span><span class="sxs-lookup"><span data-stu-id="b52a6-116">For example, type:</span></span>  
    `gacutil /i c:\temp\filename.dll /f`
    
<span data-ttu-id="b52a6-117">El `/f` opción sobrescribe cualquier ensamblado existente que tiene el mismo nombre de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b52a6-117">The `/f` option overwrites any existing assembly that has the same assembly name.</span></span> <span data-ttu-id="b52a6-118">Para obtener más información sobre los comandos gacutil y opciones, escriba `gacutil /?`.</span><span class="sxs-lookup"><span data-stu-id="b52a6-118">For more info on the gacutil commands and options, type `gacutil /?`.</span></span> 

## <a name="uninstall-using-gacutil"></a><span data-ttu-id="b52a6-119">Desinstalar mediante gacutil</span><span class="sxs-lookup"><span data-stu-id="b52a6-119">Uninstall using gacutil</span></span>
<span data-ttu-id="b52a6-120">Desinstalar un ensamblado de la caché global de ensamblados (GAC) es necesario anular totalmente la implementación de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="b52a6-120">Uninstalling an assembly from the global assembly cache (GAC) is necessary to completely undeploy an application.</span></span> <span data-ttu-id="b52a6-121">Puede automatizar este proceso.</span><span class="sxs-lookup"><span data-stu-id="b52a6-121">You can automate this process.</span></span> <span data-ttu-id="b52a6-122">Antes de implementar la aplicación en un entorno de producción, escribir una secuencia de comandos previa al procesamiento que desinstala el ensamblado de la GAC automáticamente cuando se desinstala la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b52a6-122">Before deploying the application into a production environment, write a pre-processing script that uninstalls the assembly from the GAC automatically when the application is uninstalled.</span></span> <span data-ttu-id="b52a6-123">Consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicación](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="b52a6-123">See [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
 <span data-ttu-id="b52a6-124">También puede usar un script para quitar archivos adicionales y opciones.</span><span class="sxs-lookup"><span data-stu-id="b52a6-124">You can also use a script to remove additional files and settings.</span></span> <span data-ttu-id="b52a6-125">Consulte [cómo quitar otros archivos y configuraciones para una aplicación de BizTalk](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="b52a6-125">See [How to Remove Other Files and Settings for a BizTalk Application](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span></span>  
 
#### <a name="using-the-windows-interface"></a><span data-ttu-id="b52a6-126">Utilización de la interfaz de Windows</span><span class="sxs-lookup"><span data-stu-id="b52a6-126">Using the Windows interface</span></span>  
  
1.  <span data-ttu-id="b52a6-127">Abrir en % systemdrive%\Windows\Assembly.</span><span class="sxs-lookup"><span data-stu-id="b52a6-127">Open to %systemdrive%\Windows\Assembly.</span></span>  
  
2.  <span data-ttu-id="b52a6-128">Haga clic en cada archivo de ensamblado incluido en la aplicación, seleccione **desinstalar**y, a continuación, seleccione **Sí** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="b52a6-128">Right-click each assembly file included in your application, select **Uninstall**, and then select **Yes** to confirm.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="b52a6-129">Utilizar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b52a6-129">Using the command line</span></span>  
  
1.  <span data-ttu-id="b52a6-130">Abra **símbolo del sistema para desarrolladores de Visual Studio** como administrador.</span><span class="sxs-lookup"><span data-stu-id="b52a6-130">Open **Developer Command Prompt for Visual Studio** as administrator.</span></span> 
  
2.  <span data-ttu-id="b52a6-131">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b52a6-131">Type the following:</span></span>  
  
     <span data-ttu-id="b52a6-132">`gacutil /u` \<*nombre completo del ensamblado*\></span><span class="sxs-lookup"><span data-stu-id="b52a6-132">`gacutil /u` \<*fully qualified assembly name*\></span></span>  
  
     <span data-ttu-id="b52a6-133">Por ejemplo, escriba:</span><span class="sxs-lookup"><span data-stu-id="b52a6-133">For example, type:</span></span>  
     `gacutil /u "hello,Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"`
       
## <a name="see-also"></a><span data-ttu-id="b52a6-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b52a6-134">See Also</span></span>  
 [<span data-ttu-id="b52a6-135">Implementación de ensamblados de BizTalk en una aplicación de BizTalk desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b52a6-135">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)  
<span data-ttu-id="b52a6-136">[Anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="b52a6-136">[Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md) </span></span>  
 <span data-ttu-id="b52a6-137">[Cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="b52a6-137">[How to Uninstall a BizTalk Application](../core/how-to-uninstall-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="b52a6-138">Cómo eliminar una aplicación de BizTalk del grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b52a6-138">How to Delete a BizTalk Application from the BizTalk Group</span></span>](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)
 
