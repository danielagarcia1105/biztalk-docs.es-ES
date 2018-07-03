---
title: Enumerar ubicaciones de recepción (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enumerating
- examples, receive locations
ms.assetid: 27ff8ac6-7e8e-4dde-84d1-d21bf417ddd7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f92e279ce53f068657e46912eb93093728e3185
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021259"
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a><span data-ttu-id="bd18c-102">Enumerar ubicaciones de recepción (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="bd18c-102">Enumerate Receive Locations (BizTalk Server Sample)</span></span>
<span data-ttu-id="bd18c-103">El ejemplo Enumerar ubicaciones de recepción demuestra cómo recuperar detalles sobre una o varias ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="bd18c-103">The Enumerate Receive Locations sample demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bd18c-104">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="bd18c-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="bd18c-105">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="bd18c-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="bd18c-106">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd18c-106">What This Sample Does</span></span>  
 <span data-ttu-id="bd18c-107">Este ejemplo incluye una versión de Visual Basic Scripting Edition (VBScript) que tiene acceso al modelo de objetos WMI de Windows y una versión de Visual C# que tiene acceso a la **System.Management** objetos proporcionados por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd18c-107">This sample includes a Visual Basic Scripting Edition (VBScript) version that accesses the Windows WMI object model, and a Visual C# version that accesses the **System.Management** objects provided by the .NET Framework.</span></span> <span data-ttu-id="bd18c-108">Ambas versiones obtienen acceso finalmente al proveedor WMI de BizTalk Server para llevar a cabo las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="bd18c-108">Both of these versions ultimately access the BizTalk Server WMI provider to perform the following operations:</span></span>  
  
-   <span data-ttu-id="bd18c-109">Consultar el conjunto de ubicaciones de recepción configuradas, o bien una ubicación de recepción por su nombre.</span><span class="sxs-lookup"><span data-stu-id="bd18c-109">Query for the set of configured receive locations or for a specific receive location, given its name.</span></span>  
  
-   <span data-ttu-id="bd18c-110">Recuperar y mostrar detalles sobre cada ubicación de recepción de interés.</span><span class="sxs-lookup"><span data-stu-id="bd18c-110">Retrieve and display details about each receive location of interest.</span></span>  
  
-   <span data-ttu-id="bd18c-111">Administrar errores tales como la devolución al usuario de información significativa.</span><span class="sxs-lookup"><span data-stu-id="bd18c-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="bd18c-112">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd18c-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="bd18c-113">Estos ejemplos se encuentran en las siguientes ubicaciones de SDK:</span><span class="sxs-lookup"><span data-stu-id="bd18c-113">The samples are located in the following SDK locations:</span></span>  
  
- <span data-ttu-id="bd18c-114">Versión de VBScript: \< *ruta de ejemplos*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="bd18c-114">VBScript version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
- <span data-ttu-id="bd18c-115">Versión Visual C#: \< *ruta de ejemplos*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span><span class="sxs-lookup"><span data-stu-id="bd18c-115">Visual C# version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span></span>  
  
  <span data-ttu-id="bd18c-116">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="bd18c-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="bd18c-117">Archivos</span><span class="sxs-lookup"><span data-stu-id="bd18c-117">File(s)</span></span>|<span data-ttu-id="bd18c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd18c-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bd18c-119">En la carpeta \VBScript:</span><span class="sxs-lookup"><span data-stu-id="bd18c-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="bd18c-120">EnumRecLocs.vbs</span><span class="sxs-lookup"><span data-stu-id="bd18c-120">EnumRecLocs.vbs</span></span>|<span data-ttu-id="bd18c-121">El archivo VBScript que recupera los detalles sobre todas las ubicaciones de recepción configuradas.</span><span class="sxs-lookup"><span data-stu-id="bd18c-121">VBScript file that retrieves details about all configured receive locations.</span></span>|  
|<span data-ttu-id="bd18c-122">En la carpeta \CSharp:</span><span class="sxs-lookup"><span data-stu-id="bd18c-122">In the \CSharp folder:</span></span><br /><br /> <span data-ttu-id="bd18c-123">App.ico, AssemblyInfo.cs, BTSampleEnumerateRLs.csproj, BTSampleEnumerateRLs.sln, EnumRLs.cs</span><span class="sxs-lookup"><span data-stu-id="bd18c-123">App.ico, AssemblyInfo.cs, BTSampleEnumerateRLs.csproj, BTSampleEnumerateRLs.sln, EnumRLs.cs</span></span>|<span data-ttu-id="bd18c-124">Archivos de proyecto, de solución y de origen para generar una aplicación de línea de comandos de Visual C# que recupere los detalles de todas las ubicaciones de recepción configuradas o de una ubicación de recepción específica.</span><span class="sxs-lookup"><span data-stu-id="bd18c-124">Project, solution, and source files for building a Visual C# command-line application that retrieves details about all configured receive locations, or about a specific receive location.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="bd18c-125">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd18c-125">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="bd18c-126">La versión de VBScript de la muestra Enumerar ubicaciones de recepción consta de un archivo de secuencias de comandos de Visual Basic que no necesita generar o inicializar.</span><span class="sxs-lookup"><span data-stu-id="bd18c-126">The VBScript version of the Enumerate Receive Locations sample consists of a single Visual Basic script file that you do not need to build or initialize.</span></span>  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a><span data-ttu-id="bd18c-127">Para generar la versión de Visual C# del ejemplo Enumerar ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="bd18c-127">To build the Visual C# version of the Enumerate Receive Locations sample</span></span>  
  
1. <span data-ttu-id="bd18c-128">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución BTSampleEnumerateRLs.sln.</span><span class="sxs-lookup"><span data-stu-id="bd18c-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file BTSampleEnumerateRLs.sln.</span></span>  
  
2. <span data-ttu-id="bd18c-129">En el **compilar** menú, haga clic en **compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="bd18c-129">In the **Build** menu, click **Build Solution**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="bd18c-130">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd18c-130">Running This Sample</span></span>  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a><span data-ttu-id="bd18c-131">Para ejecutar el ejemplo Enumerar ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="bd18c-131">To run the Enumerate Receive Locations sample</span></span>  
  
1.  <span data-ttu-id="bd18c-132">En una ventana de comandos, desplácese hasta una de las siguientes carpetas, en función de si va a ejecutar la versión de VBScript o la versión de Visual C# de este ejemplo, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="bd18c-132">In a command window, navigate to one of the following folders, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively:</span></span>  
  
     <span data-ttu-id="bd18c-133">\<*Ejemplos de la ruta de acceso*\>\Admin\WMI\Enumerate recibir Locations\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="bd18c-133">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
     <span data-ttu-id="bd18c-134">\<*Ejemplos de la ruta de acceso*\>\Admin\WMI\Enumerate recibir Locations\CSharp\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="bd18c-134">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="bd18c-135">Ejecute el archivo EnumRecLocs.vbs que usa el programa Cscript, o ejecute el archivo EnumRl.exe, en función de si va a ejecutar la versión de VBScript o la versión de Visual C# de este ejemplo, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="bd18c-135">Either run the file EnumRecLocs.vbs using the cscript program, or run the file EnumRl.exe, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively.</span></span> <span data-ttu-id="bd18c-136">Para la versión de Visual C#, pase uno de los dos siguientes argumentos de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="bd18c-136">For the Visual C# version, pass one of the following two command-line arguments:</span></span>  
  
    -   <span data-ttu-id="bd18c-137">**\<ReceiveLocationName\>.**</span><span class="sxs-lookup"><span data-stu-id="bd18c-137">**\<ReceiveLocationName\>.**</span></span> <span data-ttu-id="bd18c-138">El nombre de la ubicación de recepción para la que se mostrarán los detalles.</span><span class="sxs-lookup"><span data-stu-id="bd18c-138">The name of the receive location for which details will be displayed.</span></span> <span data-ttu-id="bd18c-139">Si el nombre de la ubicación de recepción contiene espacios, enciérrelo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="bd18c-139">If the receive location name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="bd18c-140">**/?.**</span><span class="sxs-lookup"><span data-stu-id="bd18c-140">**/?.**</span></span> <span data-ttu-id="bd18c-141">Muestra la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="bd18c-141">Displays help.</span></span>  
  
         <span data-ttu-id="bd18c-142">Por ejemplo (VBScript):</span><span class="sxs-lookup"><span data-stu-id="bd18c-142">For example (VBScript):</span></span>  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         <span data-ttu-id="bd18c-143">-O bien- (Visual C#):</span><span class="sxs-lookup"><span data-stu-id="bd18c-143">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         <span data-ttu-id="bd18c-144">-O bien- (Visual C#):</span><span class="sxs-lookup"><span data-stu-id="bd18c-144">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="bd18c-145">La versión de VBScript de este ejemplo no acepta ningún parámetro de línea de comandos y, por lo tanto, sólo es capaz de recuperar y mostrar detalles de todas las ubicaciones de recepción configuradas.</span><span class="sxs-lookup"><span data-stu-id="bd18c-145">The VBScript version of this sample does not accept any command-line parameters, and therefore is only capable of retrieving and displaying details about all configured receive locations.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="bd18c-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd18c-146">Comments</span></span>  
 <span data-ttu-id="bd18c-147">Todas las tareas que puede realizar en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración también pueden realizarse mediante el uso de secuencias de comandos que tiene acceso al modelo de objetos WMI de Windows y con Visual C# que tiene acceso a la **System.Management** objetos proporcionados .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd18c-147">All tasks that you can perform in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console can also be performed by using script that accesses the Windows WMI object model and by using Visual C# that accesses the **System.Management** objects provided by the .NET Framework.</span></span>  
  
 <span data-ttu-id="bd18c-148">El archivo de secuencias de comandos EnumRecLocs.vbs y el archivo de origen de Visual C# EnumRLs.cs contienen comentarios detallados con más explicaciones sobre las operaciones que realizan.</span><span class="sxs-lookup"><span data-stu-id="bd18c-148">The script file EnumRecLocs.vbs and the Visual C# source file EnumRLs.cs contain detailed comments with further explanation about the operations that they perform.</span></span> <span data-ttu-id="bd18c-149">Para obtener más información, vea Instrumental de administración de Windows en [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102).</span><span class="sxs-lookup"><span data-stu-id="bd18c-149">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd18c-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd18c-150">See Also</span></span>  
 [<span data-ttu-id="bd18c-151">Admin\WMI (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="bd18c-151">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)