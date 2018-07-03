---
title: DeleteParty (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- parties, examples
- deleting, parties
- examples, administering
- parties, deleting
- administering, examples
ms.assetid: 8161af7d-76ef-4df5-81c8-f0f5c81df9a8
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d6d488bf7431f805e8719e10fe17cef7d13fa4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982965"
---
# <a name="deleteparty-biztalk-server-sample"></a><span data-ttu-id="27bba-102">DeleteParty (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="27bba-102">DeleteParty (BizTalk Server Sample)</span></span>
<span data-ttu-id="27bba-103">El ejemplo DeleteParty muestra cómo eliminar una entidad especificada.</span><span class="sxs-lookup"><span data-stu-id="27bba-103">The DeleteParty sample demonstrates how to delete a specified party.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="27bba-104">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="27bba-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="27bba-105">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="27bba-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27bba-106">Debe crear una entidad antes de poder eliminarla.</span><span class="sxs-lookup"><span data-stu-id="27bba-106">Before you can delete a party, you must first create one.</span></span> <span data-ttu-id="27bba-107">Una forma de hacerlo es ejecutar el [PartyResolution (ejemplo de BizTalk Server)](../core/partyresolution-biztalk-server-sample.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="27bba-107">One way to do this is to run the [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md) sample.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="27bba-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="27bba-108">Prerequisites</span></span>  
  
- <span data-ttu-id="27bba-109">Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="27bba-109">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
- <span data-ttu-id="27bba-110">El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts.</span><span class="sxs-lookup"><span data-stu-id="27bba-110">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="27bba-111">Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).</span><span class="sxs-lookup"><span data-stu-id="27bba-111">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="27bba-112">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="27bba-112">What This Sample Does</span></span>  
 <span data-ttu-id="27bba-113">En este ejemplo, escrito en Microsoft Visual C# con objetos del modelo de objetos del Explorador de BizTalk (ExplorerOM), se realizan las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="27bba-113">This sample, written in Microsoft Visual C#, using objects from the BizTalk Explorer object model (ExplorerOM), performs the following operations:</span></span>  
  
-   <span data-ttu-id="27bba-114">Consultar una entidad especificada.</span><span class="sxs-lookup"><span data-stu-id="27bba-114">Query for a specified party.</span></span>  
  
-   <span data-ttu-id="27bba-115">Eliminar esa entidad.</span><span class="sxs-lookup"><span data-stu-id="27bba-115">Delete that party.</span></span>  
  
-   <span data-ttu-id="27bba-116">Administrar errores tales como la devolución al usuario de información significativa.</span><span class="sxs-lookup"><span data-stu-id="27bba-116">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="27bba-117">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="27bba-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="27bba-118">Este ejemplo se encuentra en la siguiente ubicación de SDK:</span><span class="sxs-lookup"><span data-stu-id="27bba-118">This sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="27bba-119">\<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\DeleteParty\\</span><span class="sxs-lookup"><span data-stu-id="27bba-119">\<*Samples Path*\>\Admin\ExplorerOM\DeleteParty\\</span></span>  
  
 <span data-ttu-id="27bba-120">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="27bba-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="27bba-121">Archivos</span><span class="sxs-lookup"><span data-stu-id="27bba-121">File(s)</span></span>|<span data-ttu-id="27bba-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="27bba-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27bba-123">App.ico, AssemblyInfo.cs, DeleteParty.csproj, DeleteParty.sln, DeleteParty.cs</span><span class="sxs-lookup"><span data-stu-id="27bba-123">App.ico, AssemblyInfo.cs, DeleteParty.csproj, DeleteParty.sln, DeleteParty.cs</span></span>|<span data-ttu-id="27bba-124">Archivos de proyecto, de solución y de origen para generar una aplicación de línea de comandos de Visual C# que elimine una entidad especificada.</span><span class="sxs-lookup"><span data-stu-id="27bba-124">Project, solution, and source files for building a Visual C# command-line application that removes a specified party.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="27bba-125">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="27bba-125">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="27bba-126">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución DeleteParty.sln.</span><span class="sxs-lookup"><span data-stu-id="27bba-126">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file DeleteParty.sln.</span></span>  
  
2. <span data-ttu-id="27bba-127">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="27bba-127">On the **Build** menu, click **Build Solution**.</span></span>  
  
### <a name="to-run-this-sample"></a><span data-ttu-id="27bba-128">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="27bba-128">To run this sample</span></span>  
  
1. <span data-ttu-id="27bba-129">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="27bba-129">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="27bba-130">\<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="27bba-130">\<*Samples Path*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\\</span></span>  
  
2. <span data-ttu-id="27bba-131">Ejecute el archivo DeleteParty.exe y pase uno de los dos argumentos de línea de comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="27bba-131">Run the file DeleteParty.exe, passing one of the two following command-line arguments:</span></span>  
  
   - <span data-ttu-id="27bba-132">**\<** ***PartyName* \>.**</span><span class="sxs-lookup"><span data-stu-id="27bba-132">**\<** ***PartyName* \>.**</span></span> <span data-ttu-id="27bba-133">Nombre de una entidad que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="27bba-133">The name of a party to be deleted.</span></span> <span data-ttu-id="27bba-134">Si el nombre de la entidad contiene espacios, póngalo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="27bba-134">If the party name contains spaces, enclose the name in quotes.</span></span>  
  
   - <span data-ttu-id="27bba-135">**/?.**</span><span class="sxs-lookup"><span data-stu-id="27bba-135">**/?.**</span></span> <span data-ttu-id="27bba-136">Muestra la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="27bba-136">Displays help.</span></span>  
  
     <span data-ttu-id="27bba-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27bba-137">For example:</span></span>  
  
   ```  
   DeleteParty "My Party #3"  
   ```  
  
    <span data-ttu-id="27bba-138">-O bien-</span><span class="sxs-lookup"><span data-stu-id="27bba-138">-OR-</span></span>  
  
   ```  
   DeleteParty /?  
   ```  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="27bba-139">Ejemplo de Script de Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="27bba-139">Windows Powershell Script example</span></span>  
 <span data-ttu-id="27bba-140">El siguiente fragmento de script de Windows PowerShell se puede usar para mostrar las mismas características de la **ExplorerOM** clases:</span><span class="sxs-lookup"><span data-stu-id="27bba-140">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=======================================#  
#=== If no party name is specified   ===#  
#=== just list the parties.          ===#  
#=======================================#  
  
if ($args[0] -eq $null)  
{  
  Write-Host `r`nNo party name provided for delete operation.`r`n`r`nListing Parties on local Biztalk Server:  
  
  $Catalog.Parties | Format-List Name  
}  
  
#==========================================#  
#=== Delete the specified party by name ===#  
#==========================================#  
  
else  
{  
  $party = $Catalog.Parties[$args[0]]  
  Write-Host `r`nRemoving Party named `"($args[0])`"`r`n  
  $catalog.RemoveParty($party)  
  $catalog.SaveChanges()  
}  
```  
  
 <span data-ttu-id="27bba-141">El ejemplo del script espera que se pase un único nombre de entidad como argumento de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="27bba-141">The script example expects a single party name to be passed as a command line argument.</span></span>  <span data-ttu-id="27bba-142">y busca esa entidad por su nombre e intenta eliminarla.</span><span class="sxs-lookup"><span data-stu-id="27bba-142">It looks for that party by name and attempts to delete it.</span></span>  <span data-ttu-id="27bba-143">El script mostrará todas las entidades del servidor BizTalk local si no se le pasa ningún argumento de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="27bba-143">The script will list all parties on the local Biztalk server if no commandline argument is passed to it.</span></span> <span data-ttu-id="27bba-144">A continuación se proporciona el resultado del ejemplo del script:</span><span class="sxs-lookup"><span data-stu-id="27bba-144">Here is example output from the script:</span></span>  
  
```  
PS C:\> .\DeletePart.ps1  
  
No party name provided for delete operation.  
  
Listing Parties on local Biztalk Server:  
  
Name : Party1  
  
Name : Party3  
  
Name : Party2  
  
PS C:\> .\DeletePart.ps1 Party3  
  
Removing Party named " Party3 "  
  
PS C:\> .\DeletePart.ps1  
  
No party name provided for delete operation.  
  
Listing Parties on local Biztalk Server:  
  
Name : Party1  
  
Name : Party2  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="27bba-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="27bba-145">See Also</span></span>  
 [<span data-ttu-id="27bba-146">Admin\ExplorerOM (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="27bba-146">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)