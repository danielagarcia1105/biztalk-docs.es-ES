---
title: ReceivePorts (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c403005d-5e0e-4015-b138-6318e03192af
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb14221ba11fe514ab076dd6bad8cc0aeb5b929e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receiveports-biztalk-server-sample"></a>ReceivePorts (ejemplo de BizTalk Server)
El ejemplo ReceivePorts muestra cómo crear un nuevo puerto de recepción mediante el uso de la **ExplorerOM** clases administrativas.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.  
  
-   El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts. Para obtener más información, vea [Examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra cómo utilizar el **BtsCatalogExplorer** y **puertoRecepción** clases a partir de la **Microsoft.BizTalk.ExplorerOM** espacio de nombres para agregar un nuevo puerto de recepción para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El ejemplo está escrito en Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]. En este tema también se incluye un script de ejemplo de Windows PowerShell. El ejemplo muestra las siguientes operaciones:  
  
-   Conectarse a la base de datos de administración de BizTalk mediante el **BtsCatalogExplorer** clase.  
  
-   Agregar un nuevo puerto de recepción mediante el uso de la **AddNewReceivePort** método.  
  
-   Enumeración de los puertos de recepción.  
  
-   Eliminación de los puertos de recepción.  
  
## <a name="where-to-find-this-sample"></a>Dónde encontrar este ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  
  
 \<*Ejemplos de ruta de acceso*> \Admin\ExplorerOM\ReceivePorts  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|ReceivePorts.cs|Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo.|  
|ReceivePorts.sln y ReceivePorts.csproj|Archivo de solución y un proyecto para el ejemplo.|  
  
## <a name="building-and-running-this-sample"></a>Generación y ejecución del ejemplo  
  
#### <a name="to-build-this-sample"></a>Procedimiento para generar este ejemplo  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución ReceivePorts.sln.  
  
2.  En el menú **Compilar** , haga clic en **Compilar solución**.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra una ventana de comandos y desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \Admin\ExplorerOM\ReceivePorts\bin\Debug  
  
2.  Ejecute el archivo ReceivePorts.exe. El nuevo puerto de recepción deben crearse y se muestra en la enumeración de puertos. Después de la enumeración, el puerto de recepción se quita inmediatamente.  
  
## <a name="windows-powershell-script-example"></a>Ejemplo de un script de Windows PowerShell  
 El siguiente script de ejemplo de Windows PowerShell puede utilizarse para mostrar las mismas características de la **ExplorerOM** clases:  
  
```  
#==================================================================#  
#===                                                            ===#  
#=== Create a new receive port named "My Receive Port".         ===#  
#===                                                            ===#  
#==================================================================#  
Function CreateReceivePort()  
{   
  #=== Passing false here creates a one-way receive port opposed to a two-way ===#  
  $myreceivePort = $catalog.AddNewReceivePort($false)  
  
  $myreceivePort.Name = "My Receive Port"  
  $myreceivePort.Tracking = [Microsoft.BizTalk.ExplorerOM.TrackingTypes] "AfterReceivePipeline"  
  
  #=== Try to commit the changes made so far. If the commit fails, ===#  
  #=== roll back all changes.                                      ===#  
  $catalog.SaveChanges()  
}  
  
#===============================================================#  
#===                                                         ===#  
#=== Delete the receive port named "My Receive Port"         ===#  
#===                                                         ===#  
#===============================================================#  
Function DeleteReceivePort  
{  
  $receivePort = $catalog.ReceivePorts["My Receive Port"]  
  
  if ($receivePort -ne $null)  
  {  
    $catalog.RemoveReceivePort($receivePort)    
  
    #=== Try to commit the changes made so far. If the commit fails, ===#  
    #=== roll back all changes in the trap handler.                  ===#  
    $catalog.SaveChanges()  
  }  
}  
  
#================================================================#  
#===                                                          ===#  
#=== Enumerate the receive ports.                             ===#  
#===                                                          ===#  
#================================================================#  
Function EnumerateReceivePorts  
{  
   #=== Enumerate the receive ports. ===#  
   foreach ($receivePort in $catalog.ReceivePorts)  
   {  
      Write-host "`r`n$($receivePort.Name)"  
   }  
  
   Write-host ""  
}  
  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we want to delete the ===#  
#=== receive port.                                              ===#  
#==================================================================#  
  
$Script:NoExceptionOccurred = $true  
$ErrorActionPreference="silentlycontinue"  
trap   
{   
  $Script:NoExceptionOccurred = $false  
  "Exception encountered:`r`n"; $_; "`r`nDiscarding changes and continuing execution so we can attempt to clean up the receive port...`r`n"  
  $Catalog.DiscardChanges()  
}  
  
#=== Create the new receive port ===#  
Write-Host "`r`nAttempting to create `"My Receive Port`"..."  
CreateReceivePort  
  
#=== Enumerate each receive port ===#  
Write-Host "`r`nEnumerating all receive ports...`r`n"  
EnumerateReceivePorts  
  
#=== Prompt before removing the new example receive port ===#  
Write-Host "`r`nPress <ENTER> to delete `"My Receive Port`"..."  
Read-Host  
DeleteReceivePort  
  
#=== Enumerate again to show the receive port was removed ===#  
Write-Host "`r`nEnumerating all receive ports to show `"My Receive Port`" was removed...`r`n"  
EnumerateReceivePorts  
  
```  
  
 Éste es un ejemplo muestra la ejecución del script de Windows PowerShell para crear el nuevo puerto de recepción:  
  
```  
PS C:\> .\receiveports.ps1  
  
Attempting to create "My Receive Port"...  
  
Enumerating all receive ports...  
  
BatchControlMessageRecvPort  
  
ResendReceivePort  
  
HelloWorldReceivePort  
  
CBRReceivePort  
  
RP_ReceivePOFromInternal  
  
RP_ShipmentAgency1_OrderFiles  
  
RP_ShipmentAgency2_OrderFiles  
  
RP_ReceivePOFromBuyer  
  
RP_Receive_ShipmentAgency_Ack  
  
My Receive Port  
  
Press <ENTER> to delete "My Receive Port"...  
  
Enumerating all receive ports to show "My Receive Port" was removed...  
  
BatchControlMessageRecvPort  
  
ResendReceivePort  
  
HelloWorldReceivePort  
  
CBRReceivePort  
  
RP_ReceivePOFromInternal  
  
RP_ShipmentAgency1_OrderFiles  
  
RP_ShipmentAgency2_OrderFiles  
  
RP_ReceivePOFromBuyer  
  
RP_Receive_ShipmentAgency_Ack  
```  
  
## <a name="see-also"></a>Vea también  
 [Administración-ExplorerOM (carpeta de ejemplos de BizTalk Server)](../core/admin-explorerom-biztalk-server-samples-folder.md)