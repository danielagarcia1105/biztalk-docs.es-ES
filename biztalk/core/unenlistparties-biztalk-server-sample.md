---
title: UnenlistParties (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, parties
- parties, examples
- parties, unenlisting
- examples, administering
- administering, examples
ms.assetid: a751a0fc-ca94-4610-a8aa-db3a24159334
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34cbb94dff7211a157fc492c1157fa379236641e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="unenlistparties-biztalk-server-sample"></a>UnenlistParties (ejemplo de BizTalk Server)
El ejemplo UnenlistParties muestra cómo dar de baja todas las entidades asociadas a un ensamblado de BizTalk Server implementado.  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.  
  
-   El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts. Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 Este ejemplo, escrito en Visual C# con objetos del Modelo de objetos para el Explorador de BizTalk, realiza las operaciones siguientes:  
  
-   Consultar un ensamblado concreto.  
  
-   Recuperar todas las funciones asociadas a dicho ensamblado.  
  
-   Dar de baja todas las entidades asociadas a cada una de esas funciones.  
  
-   Administrar errores tales como la devolución al usuario de información significativa.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  
  
 \<*Ejemplos de ruta de acceso*\>\Admin\ExplorerOM\UnenlistParties\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|App.ico, AssemblyInfo.cs, UnenlistParties.csproj, UnenlistParties.sln, UnenlistParties.cs|Archivos de proyecto, de solución y de origen para generar una aplicación de línea de comandos de Visual C# que dé de baja todas las entidades de un ensamblado concreto.|  
  
### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución UnenlistParties.sln.  
  
2.  En el **generar** menú, seleccione **generar solución**.  
  
### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\Admin\ExplorerOM\UnenlistParties\bin\Debug\  
  
2.  Ejecute el archivo UnenlistParties.exe y pase uno de los dos argumentos de línea de comandos siguientes:  
  
    -   **\<** ***AssemblyName* \>** . El nombre de un ensamblado desde el que se darán de baja todas las entidades asociadas. Si el nombre del ensamblado contiene espacios, enciérrelo entre comillas.  
  
    -   **/?.** Muestra la Ayuda.  
  
     Por ejemplo:  
  
    ```  
    UnenlistParties "My BizTalk Assembly.dll"  
    ```  
  
     -OR-  
  
    ```  
    UnenlistParties /?  
    ```  
  
## <a name="windows-powershell-script-example"></a>Ejemplo de un script de Windows PowerShell  
 El siguiente fragmento de script de Windows Powershell puede usarse para mostrar las mismas características de la **ExplorerOM** clases:  
  
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
  
 Los resultados siguientes del script se generaron de la dada de baja de entidades del ensamblado de proveedor, que forma parte del ejemplo PartyResolution. El ejemplo PartyResolution se encuentra en la \< *ruta de ejemplos*\>\Admin\Orchestrations\PartyResolution directory.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Admin\ExplorerOM (carpeta de ejemplos de BizTalk Server)](../core/admin-explorerom-biztalk-server-samples-folder.md)