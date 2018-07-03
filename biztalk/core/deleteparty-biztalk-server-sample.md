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
# <a name="deleteparty-biztalk-server-sample"></a>DeleteParty (ejemplo de BizTalk Server)
El ejemplo DeleteParty muestra cómo eliminar una entidad especificada.  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
> [!NOTE]
>  Debe crear una entidad antes de poder eliminarla. Una forma de hacerlo es ejecutar el [PartyResolution (ejemplo de BizTalk Server)](../core/partyresolution-biztalk-server-sample.md) ejemplo.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
- Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.  
  
- El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts. Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo, escrito en Microsoft Visual C# con objetos del modelo de objetos del Explorador de BizTalk (ExplorerOM), se realizan las operaciones siguientes:  
  
-   Consultar una entidad especificada.  
  
-   Eliminar esa entidad.  
  
-   Administrar errores tales como la devolución al usuario de información significativa.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Este ejemplo se encuentra en la siguiente ubicación de SDK:  
  
 \<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\DeleteParty\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Descripción|  
|---------------|-----------------|  
|App.ico, AssemblyInfo.cs, DeleteParty.csproj, DeleteParty.sln, DeleteParty.cs|Archivos de proyecto, de solución y de origen para generar una aplicación de línea de comandos de Visual C# que elimine una entidad especificada.|  
  
### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución DeleteParty.sln.  
  
2. En el menú **Compilar** , haga clic en **Compilar solución**.  
  
### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1. En una ventana de comandos, desplácese a la siguiente carpeta:  
  
    \<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\  
  
2. Ejecute el archivo DeleteParty.exe y pase uno de los dos argumentos de línea de comandos siguientes:  
  
   - **\<** ***PartyName* \>.** Nombre de una entidad que se va a eliminar. Si el nombre de la entidad contiene espacios, póngalo entre comillas.  
  
   - **/?.** Muestra la Ayuda.  
  
     Por ejemplo:  
  
   ```  
   DeleteParty "My Party #3"  
   ```  
  
    -O bien-  
  
   ```  
   DeleteParty /?  
   ```  
  
## <a name="windows-powershell-script-example"></a>Ejemplo de Script de Windows Powershell  
 El siguiente fragmento de script de Windows PowerShell se puede usar para mostrar las mismas características de la **ExplorerOM** clases:  
  
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
  
 El ejemplo del script espera que se pase un único nombre de entidad como argumento de la línea de comandos  y busca esa entidad por su nombre e intenta eliminarla.  El script mostrará todas las entidades del servidor BizTalk local si no se le pasa ningún argumento de la línea de comandos. A continuación se proporciona el resultado del ejemplo del script:  
  
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
  
## <a name="see-also"></a>Vea también  
 [Admin\ExplorerOM (carpeta de ejemplos de BizTalk Server)](../core/admin-explorerom-biztalk-server-samples-folder.md)