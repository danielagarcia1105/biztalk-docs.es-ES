---
title: Herramienta de limpieza de A4SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- A4SWIFT Cleanup tool
ms.assetid: e694f824-6097-4d60-bc7b-b4f1a40acea0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b2d0e251bf5e8a4169ff0d86cc6635944ca12e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="a4swift-cleanup-tool"></a><span data-ttu-id="03944-102">Herramienta de limpieza de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="03944-102">A4SWIFT Cleanup Tool</span></span>
<span data-ttu-id="03944-103">El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] limpieza herramienta le permite preparar un servidor que tiene el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] instalado en él para una nueva instalación de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03944-103">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] cleanup tool enables you to prepare a server that has the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] installed on it for a new installation of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="03944-104">La herramienta quita los artefactos de A4SWIFT como contratos, departamentos y las directivas de motor de reglas de negocios (BRE) y anula la implementación de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="03944-104">The tool removes A4SWIFT artifacts such as agreements, departments, and Business Rule Engine (BRE) policies, and undeploys assemblies.</span></span> <span data-ttu-id="03944-105">Ejecutar la herramienta le permite evitar la eliminación manual de muchos artefactos de A4SWIFT y resuelve los problemas con los ensamblados de anular la implementación que se pueden hacer referencia desde otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="03944-105">Running the tool enables you to avoid manually removing many A4SWIFT artifacts, and resolves problems with undeploying assemblies that might be referenced from other assemblies.</span></span>  
  
 <span data-ttu-id="03944-106">Al ejecutar la herramienta de limpieza, tiene la opción de dejar instalado en el equipo (el valor predeterminado) o desinstalar A4SWIFT después de quitar los artefactos de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="03944-106">When you run the cleanup tool, you have the choice of leaving A4SWIFT installed on the computer (the default), or uninstalling A4SWIFT after removing the artifacts.</span></span> <span data-ttu-id="03944-107">Debe ejecutar la herramienta antes de desinstalar A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="03944-107">You should run the tool before uninstalling A4SWIFT.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="03944-108">No utilice la herramienta de limpieza de A4SWIFT en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="03944-108">Do not use the A4SWIFT cleanup tool in a production environment.</span></span> <span data-ttu-id="03944-109">La herramienta está diseñada para usarse en un entorno de desarrollo de servidor único, no en una implementación multiservidor.</span><span class="sxs-lookup"><span data-stu-id="03944-109">The tool is intended to be used in a single-server development environment, not in a multiserver deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03944-110">De forma predeterminada, la herramienta de limpieza no funciona para cualquier otro idioma de inglés.</span><span class="sxs-lookup"><span data-stu-id="03944-110">By default, the cleanup tool does not work for any other language than English.</span></span> <span data-ttu-id="03944-111">Sin embargo, puede modificar el entorno de modo que funcione la herramienta de limpieza en un equipo localizado.</span><span class="sxs-lookup"><span data-stu-id="03944-111">You can, however, modify the environment so that the cleanup tool works on a localized computer.</span></span> <span data-ttu-id="03944-112">Ejecutar la herramienta FormPublish con el parámetro t y la cadena adaptada para la biblioteca de documentos de plantillas, por ejemplo, **t:VorLagen** en un entorno de alemán.</span><span class="sxs-lookup"><span data-stu-id="03944-112">Run the FormPublish tool with the t parameter and the localized string for the Templates document library, for example, **t:VorLagen** in a German environment.</span></span> <span data-ttu-id="03944-113">A continuación, puede ejecutar la herramienta de limpieza en un entorno traducido y adaptado.</span><span class="sxs-lookup"><span data-stu-id="03944-113">You can then run the cleanup tool in a localized environment.</span></span>  
  
 <span data-ttu-id="03944-114">A continuación debe cumplir para poder ejecutar la herramienta de limpieza:</span><span class="sxs-lookup"><span data-stu-id="03944-114">The following must be true for the cleanup tool to run:</span></span>  
  
-   <span data-ttu-id="03944-115">Debe ser miembro del [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] los grupos de administradores.</span><span class="sxs-lookup"><span data-stu-id="03944-115">You must be a member the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators groups.</span></span>  
  
-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]<span data-ttu-id="03944-116">debe instalarse en el servidor en el que se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="03944-116"> must be installed on the server on which you run the tool.</span></span>  
  
-   <span data-ttu-id="03944-117">MrsrConfiguration.dll, Shared.dll y RuleEngineExtension.dll deben implementarse en el servidor en el que se ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="03944-117">MrsrConfiguration.dll, Shared.dll, and RuleEngineExtension.dll must be deployed on the server on which you run the tool.</span></span>  
  
## <a name="what-the-cleanup-tool-does"></a><span data-ttu-id="03944-118">¿Qué hace la herramienta de limpieza</span><span class="sxs-lookup"><span data-stu-id="03944-118">What the cleanup tool does</span></span>  
 <span data-ttu-id="03944-119">La herramienta de limpieza de A4SWIFT realiza las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="03944-119">The A4SWIFT cleanup tool performs the following operations:</span></span>  
  
-   <span data-ttu-id="03944-120">Se ejecuta **anular la implementación de BM** contra ForActivities.xml y MRSRBAM.xml</span><span class="sxs-lookup"><span data-stu-id="03944-120">Runs **BM Undeploy** against ForActivities.xml and MRSRBAM.xml</span></span>  
  
-   <span data-ttu-id="03944-121">Quita los archivos FrrActivities_ConnectionStrings.xml y MRSRActivities_ConnectionStrings.xml, si existen</span><span class="sxs-lookup"><span data-stu-id="03944-121">Removes the FrrActivities_ConnectionStrings.xml and MRSRActivities_ConnectionStrings.xml files, if they exist</span></span>  
  
-   <span data-ttu-id="03944-122">Quita A4SWIFT 2.1, si existe (si ha actualizado el servidor a [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], pero el programa de instalación ha dejado 2.1 A4SWIFT instalado) y elimina la carpeta de A4SWIFT 2.1</span><span class="sxs-lookup"><span data-stu-id="03944-122">Removes A4SWIFT 2.1 if it exists (if you have upgraded the server to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], but Setup has left A4SWIFT 2.1 installed) and deletes the A4SWIFT 2.1 folder</span></span>  
  
-   <span data-ttu-id="03944-123">Anula la implementación de todos los ensamblados de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="03944-123">Undeploys all A4SWIFT assemblies</span></span>  
  
-   <span data-ttu-id="03944-124">Elimina el grupo de administradores de A4SWIFT y el grupo de usuarios de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="03944-124">Deletes the A4SWIFT Administrator group and the A4SWIFT Users group</span></span>  
  
-   <span data-ttu-id="03944-125">Elimina la base de datos de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="03944-125">Deletes the A4SWIFT database</span></span>  
  
-   <span data-ttu-id="03944-126">Elimina el directorio virtual de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="03944-126">Deletes the A4SWIFT virtual directory</span></span>  
  
-   <span data-ttu-id="03944-127">Se ejecuta una desinstalación silenciosa completa de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] y elimina el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] carpeta (si ha seleccionado)</span><span class="sxs-lookup"><span data-stu-id="03944-127">Runs a complete silent uninstall of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] and deletes the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] folder (if selected)</span></span>  
  
 <span data-ttu-id="03944-128">Tal y como quitan los artefactos y anula la implementación de ensamblados, la herramienta de limpieza también hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="03944-128">As it removes artifacts and undeploys assemblies, the cleanup tool also does the following:</span></span>  
  
-   <span data-ttu-id="03944-129">Inicia Internet Information Services (IIS) Admin Service con el fin de ejecutar</span><span class="sxs-lookup"><span data-stu-id="03944-129">Starts Internet Information Services (IIS) Admin Service in order to run</span></span>  
  
-   <span data-ttu-id="03944-130">Se detiene y, a continuación, reinicia los servicios MSSQLSERVER, SQLSERVERAGENT, BizTalk y Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="03944-130">Stops and then restarts the MSSQLSERVER, SQLSERVERAGENT, BizTalk, and Enterprise Single Sign-On services</span></span>  
  
#### <a name="to-run-the-a4swift-cleanup-tool"></a><span data-ttu-id="03944-131">Para ejecutar la herramienta de limpieza de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="03944-131">To run the A4SWIFT cleanup tool</span></span>  
  
1.  <span data-ttu-id="03944-132">Antes de ejecutar la herramienta de limpieza de A4SWIFT, anular la implementación de cualquier proyecto que hace referencia a cualquiera de los ensamblados de forma predeterminada de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="03944-132">Prior to running the A4SWIFT cleanup tool, undeploy any project that refers to any of the A4SWIFT default assemblies.</span></span>  
  
2.  <span data-ttu-id="03944-133">Abra un símbolo del sistema y mover a \< *unidad*\>: \Program BizTalk Accelerator for SWIFT\SDK\Tools.</span><span class="sxs-lookup"><span data-stu-id="03944-133">Open a command prompt and move to \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools.</span></span>  
  
3.  <span data-ttu-id="03944-134">Tipo de **A4SWIFTCleanupTool.exe** y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="03944-134">Type **A4SWIFTCleanupTool.exe** and then press **ENTER**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03944-135">Cuando se ejecute inicialmente A4SWIFTCleanupTool.exe, la herramienta muestra una pantalla de ayuda y le pide que escriba un parámetro.</span><span class="sxs-lookup"><span data-stu-id="03944-135">When you initially run A4SWIFTCleanupTool.exe, the tool displays a help screen, and prompts you to enter a parameter.</span></span> <span data-ttu-id="03944-136">La herramienta no se ejecutará hasta que se especifique el parámetro.</span><span class="sxs-lookup"><span data-stu-id="03944-136">The tool will not run until you enter the parameter.</span></span>  
  
4.  <span data-ttu-id="03944-137">Dependiendo de las acciones que desea que realice la herramienta, presione una de las claves siguientes y, a continuación, presione **ENTRAR**:</span><span class="sxs-lookup"><span data-stu-id="03944-137">Depending upon the actions that you want the tool to take, press one of the following keys, and then press **ENTER**:</span></span>  
  
    -   <span data-ttu-id="03944-138">**0** para ninguna de las acciones realizada (el valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="03944-138">**0** for no actions taken (the default)</span></span>  
  
    -   <span data-ttu-id="03944-139">**1** para quitar todos los recursos de A4SWIFT locales en el equipo, incluida la configuración del registro y el directorio virtual</span><span class="sxs-lookup"><span data-stu-id="03944-139">**1** to remove all the local A4SWIFT resources on the computer, including the virtual directory and registry settings</span></span>  
  
    -   <span data-ttu-id="03944-140">**2** para quitar todos los recursos compartidos de A4SWIFT en el grupo de BizTalk Server, incluidas las carpetas Sharepoint Web, plantillas de mensaje FIN, las directivas del BRE y vocabularios, artefactos de BizTalk y la base de datos de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="03944-140">**2** to remove all the shared A4SWIFT resources on the BizTalk Server group, including Sharepoint Web folders, FIN message templates, BRE policies and vocabularies, BizTalk artifacts, and the A4SWIFT database</span></span>  
  
    -   <span data-ttu-id="03944-141">**3** para quitar todos los recursos locales y compartidos</span><span class="sxs-lookup"><span data-stu-id="03944-141">**3** to remove all the local and shared resources</span></span>  
  
    -   <span data-ttu-id="03944-142">**4** para quitar todos los recursos locales y compartidos y desinstalar el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] producto.</span><span class="sxs-lookup"><span data-stu-id="03944-142">**4** to remove all the local and shared resources and uninstall the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] product.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03944-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="03944-143">See Also</span></span>  
 [<span data-ttu-id="03944-144">Herramientas</span><span class="sxs-lookup"><span data-stu-id="03944-144">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)