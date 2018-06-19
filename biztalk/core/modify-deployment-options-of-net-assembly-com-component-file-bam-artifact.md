---
title: Cómo modificar las opciones de implementación de un ensamblado. NET, un componente COM, un archivo o un artefacto de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [.NET assemblies], deploying
- deploying, virtual directories
- managing [applications], deploying
- managing [applications], modifying
- definition files [BAM], modifying
- modifying, artifacts
- deploying, artifacts
- managing [certificates], deploying
- deploying, .NET assemblies
- COM components, deploying
- definition files [BAM], deploying
- virtual directories, deploying
- deploying, certificates
- modifying, deployment options
- virtual directories, modifying
- deploying, COM components
ms.assetid: 4955d420-d9ff-4d5a-82f4-fb16477a828c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6469f06b7b42ae1f8b45419fa0214682bd9fa67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263980"
---
# <a name="how-to-modify-the-deployment-options-of-a-net-assembly-com-component-file-or-bam-artifact"></a><span data-ttu-id="126c5-102">Cómo modificar las opciones de implementación de un ensamblado .NET, un componente COM, un archivo o un artefacto de BAM</span><span class="sxs-lookup"><span data-stu-id="126c5-102">How to Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact</span></span>
<span data-ttu-id="126c5-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para modificar las opciones de implementación de los artefactos de recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="126c5-103">This topic describes how to use the BizTalk Server Administration console to modify the deployment options of the following resource artifacts:</span></span>  
  
-   <span data-ttu-id="126c5-104">Ensamblados .NET</span><span class="sxs-lookup"><span data-stu-id="126c5-104">.NET assemblies</span></span>  
  
-   <span data-ttu-id="126c5-105">Componentes COM</span><span class="sxs-lookup"><span data-stu-id="126c5-105">COM components</span></span>  
  
-   <span data-ttu-id="126c5-106">Archivos ad hoc</span><span class="sxs-lookup"><span data-stu-id="126c5-106">Ad hoc files</span></span>  
  
-   <span data-ttu-id="126c5-107">Artefactos de BAM</span><span class="sxs-lookup"><span data-stu-id="126c5-107">BAM artifacts</span></span>  
  
 <span data-ttu-id="126c5-108">Puede que desee modificar las propiedades de implementación para cambiar la ubicación de destino en que se copiará el artefacto cuando la aplicación se instale en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="126c5-108">You might want to modify the deployment properties to change the destination location to which the artifact file will be copied when the application is installed on the local computer.</span></span> <span data-ttu-id="126c5-109">Si no proporciona una ruta, el archivo no se copiará en el equipo local durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="126c5-109">If you do not provide a path, the file will not be copied to the local computer on installation.</span></span>  
  
 <span data-ttu-id="126c5-110">Además, puede que desee modificar las opciones siguientes para un ensamblado .NET:</span><span class="sxs-lookup"><span data-stu-id="126c5-110">In addition, you might want to modify the following options for a .NET assembly:</span></span>  
  
-   <span data-ttu-id="126c5-111">**Agregar a la caché global de ensamblados de agregar recursos (gacutil).**</span><span class="sxs-lookup"><span data-stu-id="126c5-111">**Add to the global assembly cache on add resource (gacutil).**</span></span> <span data-ttu-id="126c5-112">al activar esta opción, el ensamblado se agrega a la caché de ensamblados global (GAC) en el equipo local cuando el ensamblado se agrega a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="126c5-112">When you select this option, the assembly is added to the global assembly cache (GAC) on the local computer when the assembly is added to the application.</span></span> <span data-ttu-id="126c5-113">Además, si actualiza posteriormente el ensamblado (haga clic en él y haga clic en **actualizar**), el ensamblado se agrega a la GAC.</span><span class="sxs-lookup"><span data-stu-id="126c5-113">In addition, if you later refresh the assembly (right-click it and click **Refresh**), the assembly is added to the GAC.</span></span> <span data-ttu-id="126c5-114">Al desactivar la casilla de verificación de esta opción, el ensamblado no se quita de la GAC si actualmente existe en dicho lugar.</span><span class="sxs-lookup"><span data-stu-id="126c5-114">Clearing the check box for this option does not remove the assembly from the GAC, if it currently exists there.</span></span>  
  
-   <span data-ttu-id="126c5-115">**Agregar a la caché de ensamblados global en la importación de archivo MSI (gacutil).**</span><span class="sxs-lookup"><span data-stu-id="126c5-115">**Add to the global assembly cache on MSI file import (gacutil).**</span></span> <span data-ttu-id="126c5-116">al seleccionar esta opción, si se ha exportado la aplicación a un archivo .msi y el archivo .msi se ha importado en un grupo de BizTalk, el ensamblado se instala en la GAC del equipo local como parte del proceso de importación.</span><span class="sxs-lookup"><span data-stu-id="126c5-116">When you select this option, if the application is exported to an .msi file, and the .msi file is imported into a BizTalk group, the assembly is installed in the GAC on the local computer as part of the import process.</span></span>  
  
-   <span data-ttu-id="126c5-117">**Agregar a la caché de ensamblados global en la instalación de archivos MSI (gacutil).**</span><span class="sxs-lookup"><span data-stu-id="126c5-117">**Add to the global assembly cache on MSI file install (gacutil).**</span></span> <span data-ttu-id="126c5-118">Al seleccionar esta opción, si se ha exportado la aplicación a un archivo .msi y se ha instalado la aplicación en un equipo desde el archivo .msi, el ensamblado se instala en la GAC del equipo local como parte del proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="126c5-118">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, the assembly is installed in the GAC on the local computer as part of the installation process.</span></span>  
  
-   <span data-ttu-id="126c5-119">**Hacer visible para los componentes COM (regasm).**</span><span class="sxs-lookup"><span data-stu-id="126c5-119">**Make visible to COM components (regasm).**</span></span> <span data-ttu-id="126c5-120">al seleccionar esta opción, si la aplicación se ha exportado a un archivo .msi y se ha instalado en un equipo desde el archivo .msi, se agrega un ensamblado COM administrado al Registro de Windows en el equipo local como parte del proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="126c5-120">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, a managed COM assembly is added to the Windows registry on the local computer as part of the installation process.</span></span> <span data-ttu-id="126c5-121">Si especifica esta opción, también debe especificar una ubicación para el archivo en Destino.</span><span class="sxs-lookup"><span data-stu-id="126c5-121">If you specify this option, you must also specify a location for the file in Destination.</span></span>  
  
-   <span data-ttu-id="126c5-122">**Registrar componentes con servicios (regsvcs).**</span><span class="sxs-lookup"><span data-stu-id="126c5-122">**Register serviced components (regsvcs).**</span></span> <span data-ttu-id="126c5-123">al seleccionar esta opción, si la aplicación se ha exportado a un archivo .msi y se ha instalado en un equipo desde el archivo .msi, se agrega un ensamblado COM+ administrado al Registro de Windows en el equipo local como parte del proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="126c5-123">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, a managed COM+ assembly is added to the Windows registry on the local computer as part of the installation process.</span></span> <span data-ttu-id="126c5-124">Si especifica esta opción, también debe especificar una ubicación para el archivo en Destino.</span><span class="sxs-lookup"><span data-stu-id="126c5-124">If you specify this option, you must also specify a location for the file in Destination.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="126c5-125">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="126c5-125">Prerequisites</span></span>  
 <span data-ttu-id="126c5-126">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="126c5-126">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="126c5-127">Además, si selecciona una opción que agrega inmediatamente el ensamblado a la GAC, la cuenta debe pertenecer también al grupo de administradores local.</span><span class="sxs-lookup"><span data-stu-id="126c5-127">In addition, if you select an option that immediately adds the assembly to the GAC, your account must also be a member of the local Administrator's group.</span></span> <span data-ttu-id="126c5-128">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="126c5-128">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-properties-of-a-resource-artifact"></a><span data-ttu-id="126c5-129">Para modificar las propiedades de implementación de un artefacto de recurso</span><span class="sxs-lookup"><span data-stu-id="126c5-129">To modify the deployment properties of a resource artifact</span></span>  
  
1.  <span data-ttu-id="126c5-130">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="126c5-130">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="126c5-131">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], el grupo de BizTalk que contiene el artefacto cuyas opciones de implementación desea modificar y, a continuación, la aplicación que contiene el artefacto.</span><span class="sxs-lookup"><span data-stu-id="126c5-131">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the artifact for which to modify deployment options, and then expand the application containing the artifact.</span></span>  
  
3.  <span data-ttu-id="126c5-132">Haga clic en el **recursos** carpeta, haga clic en el artefacto y, a continuación, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="126c5-132">Click the **Resources** folder, right-click the artifact, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="126c5-133">En el **opciones** ficha, modifique las opciones de implementación según sea necesario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="126c5-133">On the **Options** tab, modify the deployment options as necessary, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126c5-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="126c5-134">See Also</span></span>  
 [<span data-ttu-id="126c5-135">Administrar ensamblados. NET, certificados y otros recursos</span><span class="sxs-lookup"><span data-stu-id="126c5-135">Managing .NET Assemblies, Certificates, and Other Resources</span></span>](../core/managing-net-assemblies-certificates-and-other-resources.md)