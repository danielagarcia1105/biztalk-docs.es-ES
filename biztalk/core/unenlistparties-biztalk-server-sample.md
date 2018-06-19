---
title: UnenlistParties (ejemplo de BizTalk Server) | Documentos de Microsoft
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
- parties, unenlisting
- examples, administering
- administering, examples
ms.assetid: a751a0fc-ca94-4610-a8aa-db3a24159334
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34cbb94dff7211a157fc492c1157fa379236641e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973474"
---
# <a name="unenlistparties-biztalk-server-sample"></a><span data-ttu-id="f3ff5-102">UnenlistParties (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="f3ff5-102">UnenlistParties (BizTalk Server Sample)</span></span>
<span data-ttu-id="f3ff5-103">El ejemplo UnenlistParties muestra cómo dar de baja todas las entidades asociadas a un ensamblado de BizTalk Server implementado.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-103">The UnenlistParties sample demonstrates how to unenlist all of the parties associated with a deployed BizTalk Server assembly.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f3ff5-104">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="f3ff5-105">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f3ff5-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f3ff5-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="f3ff5-107">Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-107">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="f3ff5-108">El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-108">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="f3ff5-109">Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).</span><span class="sxs-lookup"><span data-stu-id="f3ff5-109">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="f3ff5-110">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="f3ff5-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="f3ff5-111">Este ejemplo, escrito en Visual C# con objetos del Modelo de objetos para el Explorador de BizTalk, realiza las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3ff5-111">This sample, written in Visual C# using objects from the BizTalk Explorer object model, performs the following operations:</span></span>  
  
-   <span data-ttu-id="f3ff5-112">Consultar un ensamblado concreto.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-112">Query for a particular assembly.</span></span>  
  
-   <span data-ttu-id="f3ff5-113">Recuperar todas las funciones asociadas a dicho ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-113">Retrieve all of the roles associated with that assembly.</span></span>  
  
-   <span data-ttu-id="f3ff5-114">Dar de baja todas las entidades asociadas a cada una de esas funciones.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-114">Unenlist all of the parties associated with each such role.</span></span>  
  
-   <span data-ttu-id="f3ff5-115">Administrar errores tales como la devolución al usuario de información significativa.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-115">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="f3ff5-116">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3ff5-116">Where to Find This Sample</span></span>  
 <span data-ttu-id="f3ff5-117">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="f3ff5-117">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="f3ff5-118">\<*Ejemplos de ruta de acceso*\>\Admin\ExplorerOM\UnenlistParties\\</span><span class="sxs-lookup"><span data-stu-id="f3ff5-118">\<*Samples Path*\>\Admin\ExplorerOM\UnenlistParties\\</span></span>  
  
 <span data-ttu-id="f3ff5-119">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="f3ff5-120">Archivos</span><span class="sxs-lookup"><span data-stu-id="f3ff5-120">File(s)</span></span>|<span data-ttu-id="f3ff5-121">Description</span><span class="sxs-lookup"><span data-stu-id="f3ff5-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3ff5-122">App.ico, AssemblyInfo.cs, UnenlistParties.csproj, UnenlistParties.sln, UnenlistParties.cs</span><span class="sxs-lookup"><span data-stu-id="f3ff5-122">App.ico, AssemblyInfo.cs, UnenlistParties.csproj, UnenlistParties.sln, UnenlistParties.cs</span></span>|<span data-ttu-id="f3ff5-123">Archivos de proyecto, de solución y de origen para generar una aplicación de línea de comandos de Visual C# que dé de baja todas las entidades de un ensamblado concreto.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-123">Project, solution, and source files for building a Visual C# command-line application that unenlists all of the parties for a particular assembly.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="f3ff5-124">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3ff5-124">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="f3ff5-125">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución UnenlistParties.sln.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-125">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file UnenlistParties.sln.</span></span>  
  
2.  <span data-ttu-id="f3ff5-126">En el **generar** menú, seleccione **generar solución**.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-126">In the **Build** menu, select **Build Solution**.</span></span>  
  
### <a name="to-run-this-sample"></a><span data-ttu-id="f3ff5-127">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3ff5-127">To run this sample</span></span>  
  
1.  <span data-ttu-id="f3ff5-128">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="f3ff5-128">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="f3ff5-129">\<*Ejemplos de ruta de acceso*\>\Admin\ExplorerOM\UnenlistParties\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="f3ff5-129">\<*Samples Path*\>\Admin\ExplorerOM\UnenlistParties\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="f3ff5-130">Ejecute el archivo UnenlistParties.exe y pase uno de los dos argumentos de línea de comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3ff5-130">Run the file UnenlistParties.exe, passing one of the two following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="f3ff5-131">**\<** ***AssemblyName* \>** .</span><span class="sxs-lookup"><span data-stu-id="f3ff5-131">**\<** ***AssemblyName* \>**.</span></span> <span data-ttu-id="f3ff5-132">El nombre de un ensamblado desde el que se darán de baja todas las entidades asociadas.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-132">The name of an assembly from which all associated parties are to be unenlisted.</span></span> <span data-ttu-id="f3ff5-133">Si el nombre del ensamblado contiene espacios, enciérrelo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-133">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="f3ff5-134">**/?.**</span><span class="sxs-lookup"><span data-stu-id="f3ff5-134">**/?.**</span></span> <span data-ttu-id="f3ff5-135">Muestra la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-135">Displays help.</span></span>  
  
     <span data-ttu-id="f3ff5-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f3ff5-136">For example:</span></span>  
  
    ```  
    UnenlistParties "My BizTalk Assembly.dll"  
    ```  
  
     <span data-ttu-id="f3ff5-137">-OR-</span><span class="sxs-lookup"><span data-stu-id="f3ff5-137">-OR-</span></span>  
  
    ```  
    UnenlistParties /?  
    ```  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="f3ff5-138">Ejemplo de un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3ff5-138">Windows Powershell Script Example</span></span>  
 <span data-ttu-id="f3ff5-139">El siguiente fragmento de script de Windows Powershell puede usarse para mostrar las mismas características de la **ExplorerOM** clases:</span><span class="sxs-lookup"><span data-stu-id="f3ff5-139">The following Windows Powershell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=====================================================#  
#=== If no assembly name is specified, just list   ===#  
#=== the assemblies, roles and partyies enlisted.  ===#  
#=====================================================#  
  
if ($args[0] -eq $null)  
{  
  Write-Host `r`n===========================================================  
  Write-Host No assembly name provided for party unenlist operation.  
  Write-Host Listing Parties for each assembly on local BizTalk Server:  
  Write-Host ===========================================================`r`n  
  
  foreach ($assembly in $Catalog.Assemblies)  
  {  
    write-host $Assembly.Name`r`n  
  
    foreach ($role in $Assembly.Roles)  
    {  
      write-host `t($role.name)  
  
      foreach($party in $role.EnlistedParties)  
      {  
        Write-Host `t`t($party.Party.Name)  
      }  
      write-host  
    }  
  }  
  
  write-host  
}  
  
#=====================================================#  
#=== If assembly name is specified, remove parties ===#  
#=== enlisted in all roles for the assembly.       ===#  
#=====================================================#  
  
else  
{  
  $Assembly = $Catalog.Assemblies[$args[0]]  
  
  if ($assembly -eq $null)  
  {  
    write-host Assembly named $args[0] not found.`r`n  
  }   
  
  else  
  {  
    write-host `r`nUnenlisting parties from all roles in ($Assembly.Name)`r`n  
  
    foreach ($role in $Assembly.Roles)  
    {  
  
      $count = $role.EnlistedParties.count  
  
      for($c=0; $c -lt $count; $c++)  
      {  
        #==========================================================#  
        #=== Array index stays at zero because the collection   ===#  
        #=== changes after each item is removed.                ===#  
        #==========================================================#  
  
        $party = $role.EnlistedParties[0]  
  
        Write-Host Unenlisting ($party.Party.Name) from ($role.Name)...  
        $role.RemoveEnlistedParty($party)  
        Write-Host done.`r`n  
      }  
    }  
  
    write-Host Comitting changes...  
    $catalog.SaveChanges()  
    Write-Host done.`r`n  
  }  
}  
  
```  
  
 <span data-ttu-id="f3ff5-140">Los resultados siguientes del script se generaron de la dada de baja de entidades del ensamblado de proveedor, que forma parte del ejemplo PartyResolution.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-140">The following script output was generated from unenlisting parties from the Supplier assembly which is part of the PartyResolution sample.</span></span> <span data-ttu-id="f3ff5-141">El ejemplo PartyResolution se encuentra en la \< *ruta de ejemplos*\>\Admin\Orchestrations\PartyResolution directory.</span><span class="sxs-lookup"><span data-stu-id="f3ff5-141">The PartyResolution sample is located in the \<*Samples Path*\>\Admin\Orchestrations\PartyResolution directory.</span></span>  
  
```  
PS C:\> .\UnenlistParties.ps1 Supplier  
  
Unenlisting parties from all roles in Supplier  
  
Unenlisting ShipmentAgency1 from ShipmentRole ...  
done.  
  
Unenlisting ShipmentAgency2 from ShipmentRole ...  
done.  
  
Unenlisting BuyerAgency from Buyer ...  
done.  
  
Comitting changes...  
done.  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3ff5-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3ff5-142">See Also</span></span>  
 [<span data-ttu-id="f3ff5-143">Admin\ExplorerOM (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="f3ff5-143">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)