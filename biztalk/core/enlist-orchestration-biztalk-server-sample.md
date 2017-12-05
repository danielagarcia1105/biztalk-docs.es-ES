---
title: "Dar de alta una orquestación (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, enlisting
- examples, orchestrations
ms.assetid: d8d53e59-2313-40dd-a278-0a29d8eb4ce8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e8d85a49b410f0571e8e9cb0be816f1feda139e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="enlist-orchestration-biztalk-server-sample"></a><span data-ttu-id="6101f-102">Dar de alta una orquestación (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="6101f-102">Enlist Orchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="6101f-103">El ejemplo para dar de alta una orquestación muestra cómo se da de alta una orquestación de BizTalk Server en un host.</span><span class="sxs-lookup"><span data-stu-id="6101f-103">The Enlist Orchestration sample demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6101f-104">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="6101f-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="6101f-105">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="6101f-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="6101f-106">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="6101f-106">What This Sample Does</span></span>  
 <span data-ttu-id="6101f-107">Este ejemplo incluye una versión de Visual Basic Scripting Edition (VBScript) que tiene acceso al modelo de objeto de Instrumental de administración de Windows (WMI) y una versión de Visual C# que tiene acceso a la **System.Management** objetos proporcionados por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6101f-107">This sample includes a Visual Basic Scripting Edition (VBScript) version that accesses the Windows Management Instrumentation (WMI) object model, and a Visual C# version that accesses the **System.Management** objects provided by the .NET Framework.</span></span> <span data-ttu-id="6101f-108">Ambas versiones obtienen acceso finalmente al proveedor WMI de BizTalk Server para llevar a cabo las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="6101f-108">Both of these versions ultimately access the BizTalk Server WMI provider to perform the following operations:</span></span>  
  
-   <span data-ttu-id="6101f-109">A partir de un nombre de orquestación y de ensamblado, consultar una orquestación de BizTalk Server implementada.</span><span class="sxs-lookup"><span data-stu-id="6101f-109">Given an orchestration name and an assembly name, query for a specific deployed BizTalk Server orchestration.</span></span>  
  
-   <span data-ttu-id="6101f-110">Dar de alta esa orquestación en el host predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6101f-110">Enlist that orchestration to the default host.</span></span>  
  
-   <span data-ttu-id="6101f-111">Administrar errores tales como la devolución al usuario de información significativa.</span><span class="sxs-lookup"><span data-stu-id="6101f-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="6101f-112">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="6101f-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="6101f-113">Estos ejemplos se encuentran en las siguientes ubicaciones de SDK:</span><span class="sxs-lookup"><span data-stu-id="6101f-113">The samples are located in the following SDK locations:</span></span>  
  
-   <span data-ttu-id="6101f-114">Versión de VBScript: \< *ruta de ejemplos*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="6101f-114">VBScript version: \<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span></span>  
  
-   <span data-ttu-id="6101f-115">Versión de Visual C#: \< *ruta de ejemplos*\>\Admin\WMI\Enlist Orchestration\CSharp\\</span><span class="sxs-lookup"><span data-stu-id="6101f-115">Visusal C# version: \<*Samples Path*\>\Admin\WMI\Enlist Orchestration\CSharp\\</span></span>  
  
 <span data-ttu-id="6101f-116">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="6101f-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="6101f-117">Archivos</span><span class="sxs-lookup"><span data-stu-id="6101f-117">File(s)</span></span>|<span data-ttu-id="6101f-118">Description</span><span class="sxs-lookup"><span data-stu-id="6101f-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6101f-119">En la carpeta \VBScript:</span><span class="sxs-lookup"><span data-stu-id="6101f-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="6101f-120">EnlistOrch.vbs</span><span class="sxs-lookup"><span data-stu-id="6101f-120">EnlistOrch.vbs</span></span>|<span data-ttu-id="6101f-121">El archivo VBScript que toma parámetros para especificar una orquestación que se va a dar de alta en un host.</span><span class="sxs-lookup"><span data-stu-id="6101f-121">VBScript file that takes parameters to specify an orchestration to be enlisted to a host.</span></span>|  
|<span data-ttu-id="6101f-122">En la carpeta \CSharp:</span><span class="sxs-lookup"><span data-stu-id="6101f-122">In the \CSharp folder:</span></span><br /><br /> <span data-ttu-id="6101f-123">App.ico, AssemblyInfo.cs, BTSampleEnlistOrc.csproj, BTSampleEnlistOrc.sln, EnlistOrc.cs</span><span class="sxs-lookup"><span data-stu-id="6101f-123">App.ico, AssemblyInfo.cs, BTSampleEnlistOrc.csproj, BTSampleEnlistOrc.sln, EnlistOrc.cs</span></span>|<span data-ttu-id="6101f-124">Archivos de proyecto, de solución y de origen para generar una aplicación de línea de comandos de Visual C# que tome parámetros para especificar una orquestación que se va a dar de alta en un host.</span><span class="sxs-lookup"><span data-stu-id="6101f-124">Project, solution, and source files for building a Visual C# command-line application that takes parameters to specify an orchestration to be enlisted to a host.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="6101f-125">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="6101f-125">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="6101f-126">La versión de VBScript del ejemplo para dar de alta una orquestación consta de un archivo de secuencias de comandos de Visual Basic que no necesita generar o inicializar.</span><span class="sxs-lookup"><span data-stu-id="6101f-126">The VBScript version of the Enlist Orchestration sample consists of a single Visual Basic script file that you do not need to build or initialize.</span></span>  
  
#### <a name="to-build-the-visual-c-version-of-the-enlist-orchestration-sample"></a><span data-ttu-id="6101f-127">Para generar la versión de Visual C# del ejemplo para dar de alta una orquestación</span><span class="sxs-lookup"><span data-stu-id="6101f-127">To build the Visual C# version of the Enlist Orchestration sample</span></span>  
  
1.  <span data-ttu-id="6101f-128">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución BTSampleEnlistOrc.sln.</span><span class="sxs-lookup"><span data-stu-id="6101f-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file BTSampleEnlistOrc.sln.</span></span>  
  
2.  <span data-ttu-id="6101f-129">En el **generar** menú, haga clic en **generar solución**.</span><span class="sxs-lookup"><span data-stu-id="6101f-129">In the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-the-enlist-orchestration-sample"></a><span data-ttu-id="6101f-130">Para ejecutar el ejemplo para dar de alta una orquestación.</span><span class="sxs-lookup"><span data-stu-id="6101f-130">To run the Enlist Orchestration sample.</span></span>  
  
1.  <span data-ttu-id="6101f-131">En una ventana de comandos, desplácese a una de las carpetas siguientes, dependiendo de si va a ejecutar la versión de VBScript o la versión de Visual C# de este ejemplo, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="6101f-131">In a command window, navigate to one of the following folders, depending on whether you are planning to run the VBScript version or the Visual C# version of this sample, respectively:</span></span>  
  
     <span data-ttu-id="6101f-132">\<*Ejemplos de ruta de acceso*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="6101f-132">\<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span></span>  
  
     <span data-ttu-id="6101f-133">\<*Ejemplos de ruta de acceso*\>AdminWMIEnlist OrchestrationCSharpbinDebug</span><span class="sxs-lookup"><span data-stu-id="6101f-133">\<*Samples Path*\>AdminWMIEnlist OrchestrationCSharpbinDebug</span></span>  
  
2.  <span data-ttu-id="6101f-134">Ejecute el archivo EnlistOrch.vbs que usa el programa Cscript, o ejecute el archivo EnlistOrc.exe, en función de si va a ejecutar la versión de VBScript o la versión de Visual C# de este ejemplo, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="6101f-134">Either run the file EnlistOrch.vbs using the cscript program, or run the file EnlistOrc.exe, depending on whether you are planning to run the VBScript version or the Visual C# version of this sample, respectively.</span></span> <span data-ttu-id="6101f-135">En cualquier evento, pase los siguientes argumentos de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="6101f-135">In any event, pass the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="6101f-136">**\<** ***OrchestrationName* \>.**</span><span class="sxs-lookup"><span data-stu-id="6101f-136">**\<** ***OrchestrationName* \>.**</span></span> <span data-ttu-id="6101f-137">El nombre de la orquestación que se va a dar de alta.</span><span class="sxs-lookup"><span data-stu-id="6101f-137">The name of the orchestration to be enlisted.</span></span>  
  
    -   <span data-ttu-id="6101f-138">**\<** ***AssemblyName* \>.**</span><span class="sxs-lookup"><span data-stu-id="6101f-138">**\<** ***AssemblyName* \>.**</span></span> <span data-ttu-id="6101f-139">El nombre del ensamblado en el que se ha implementado la orquestación.</span><span class="sxs-lookup"><span data-stu-id="6101f-139">The name of the assembly in which the orchestration was deployed.</span></span> <span data-ttu-id="6101f-140">Si el nombre del ensamblado contiene espacios, enciérrelo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="6101f-140">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
         <span data-ttu-id="6101f-141">Por ejemplo: (VBScript):</span><span class="sxs-lookup"><span data-stu-id="6101f-141">For example: (VBScript):</span></span>  
  
        ```  
        cscript EnlistOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         <span data-ttu-id="6101f-142">-O bien- (Visual C#):</span><span class="sxs-lookup"><span data-stu-id="6101f-142">-OR- (Visual C#):</span></span>  
  
        ```  
        EnlistOrc MyBusinessOrchestration "My Business Assembly"  
        ```  
  
## <a name="comments"></a><span data-ttu-id="6101f-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6101f-143">Comments</span></span>  
 <span data-ttu-id="6101f-144">Todas las tareas que puede realizar en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración también puede realizarse mediante el uso de script que tiene acceso al modelo de objetos de WMI de Windows y con Visual C# que tiene acceso a la **System.Management** objetos proporcionados .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6101f-144">All tasks that you can perform in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console can also be performed by using script that accesses the Windows WMI object model and by using Visual C# that accesses the **System.Management** objects provided by the .NET Framework.</span></span>  
  
 <span data-ttu-id="6101f-145">El archivo de secuencias de comandos EnlistOrch.vbs y el archivo de origen de Visual C# EnlistOrc.cs contienen comentarios detallados con más explicaciones sobre las operaciones que realizan.</span><span class="sxs-lookup"><span data-stu-id="6101f-145">The script file EnlistOrch.vbs and the Visual C# source file EnlistOrc.cs contain detailed comments with further explanation about the operations that they perform.</span></span> <span data-ttu-id="6101f-146">Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span><span class="sxs-lookup"><span data-stu-id="6101f-146">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6101f-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="6101f-147">See Also</span></span>  
 [<span data-ttu-id="6101f-148">Admin\WMI (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="6101f-148">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)