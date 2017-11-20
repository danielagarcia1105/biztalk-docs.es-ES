---
title: SendPortGroups (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4510aa31-16c3-475a-98aa-b590e13ae189
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fa513f0dfb9208abc3e9231f3b8eb23c0b561d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sendportgroups-biztalk-server-sample"></a><span data-ttu-id="89193-102">SendPortGroups (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="89193-102">SendPortGroups (BizTalk Server Sample)</span></span>
<span data-ttu-id="89193-103">El ejemplo SendPortGroups muestra cómo enumerar y administrar grupos de puertos de envío mediante el **Microsoft.BizTalk.ExplorerOM** las clases de administración.</span><span class="sxs-lookup"><span data-stu-id="89193-103">The SendPortGroups sample demonstrates how to enumerate and manage send port groups by using the **Microsoft.BizTalk.ExplorerOM** administration classes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="89193-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="89193-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="89193-105">Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="89193-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="89193-106">El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts.</span><span class="sxs-lookup"><span data-stu-id="89193-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="89193-107">Para obtener más información, vea [Examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).</span><span class="sxs-lookup"><span data-stu-id="89193-107">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="89193-108">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="89193-108">What This Sample Does</span></span>  
 <span data-ttu-id="89193-109">Este ejemplo muestra cómo utilizar el **BtsCatalogExplorer** y **grupoPuertosEnvío** clases a partir de la **Microsoft.BizTalk.ExplorerOM** espacio de nombres para administrar grupos de puertos de envío en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="89193-109">This sample demonstrates using the **BtsCatalogExplorer** and **SendPortGroup** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to manage send port groups in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="89193-110">El ejemplo está escrito en Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89193-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="89193-111">En este tema también se incluye un script de ejemplo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89193-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="89193-112">El ejemplo muestra las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="89193-112">The sample demonstrates the following operations:</span></span>  
  
-   <span data-ttu-id="89193-113">Conectarse a la base de datos de administración de BizTalk mediante el **BtsCatalogExplorer** clase.</span><span class="sxs-lookup"><span data-stu-id="89193-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  
  
-   <span data-ttu-id="89193-114">Creación de un nuevo puerto de envío denominado “My Send Port Group”.</span><span class="sxs-lookup"><span data-stu-id="89193-114">Creating a new send port group named “My Send Port Group”.</span></span>  
  
-   <span data-ttu-id="89193-115">Enumeración de grupos de puerto de envío para mostrar el grupo de puertos de envío recién creados.</span><span class="sxs-lookup"><span data-stu-id="89193-115">Enumerating send port groups to display the newly created send port group.</span></span>  
  
-   <span data-ttu-id="89193-116">Eliminación del nuevo grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="89193-116">Deleting the new send port group.</span></span>  
  
 <span data-ttu-id="89193-117">En el ejemplo están presentes funciones adicionales, pero no se ejecutan en la versión [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89193-117">Additional functions are present in the sample but are not executed in the [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] version.</span></span>  <span data-ttu-id="89193-118">Algunas de las funciones adicionales se muestran en el script de ejemplo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89193-118">Some of the additional functions are demonstrated in the PowerShell example script.</span></span> <span data-ttu-id="89193-119">Las funciones adicionales muestran las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="89193-119">The additional functions demonstrate the following functionality:</span></span>  
  
-   <span data-ttu-id="89193-120">Adición de un puerto de envío al grupo de puertos de envío recién creado (que se describe en el ejemplo de PowerShell).</span><span class="sxs-lookup"><span data-stu-id="89193-120">Adding a send port to the newly created send port group (covered in the PowerShell example).</span></span>  
  
-   <span data-ttu-id="89193-121">Eliminación de un puerto de envío del grupo de puertos de envío (que se describe en el ejemplo de PowerShell).</span><span class="sxs-lookup"><span data-stu-id="89193-121">Deleting a send port from the send port group (covered in the PowerShell example).</span></span>  
  
-   <span data-ttu-id="89193-122">Inicio del grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="89193-122">Starting the send port group.</span></span>  
  
-   <span data-ttu-id="89193-123">Detención del grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="89193-123">Stopping the send port group.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="89193-124">Dónde encontrar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="89193-124">Where To Find This Sample</span></span>  
 <span data-ttu-id="89193-125">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="89193-125">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="89193-126">\<*Ejemplos de ruta de acceso*> \Admin\ExplorerOM\SendPortGroups</span><span class="sxs-lookup"><span data-stu-id="89193-126">\<*Samples Path*>\Admin\ExplorerOM\SendPortGroups</span></span>  
  
 <span data-ttu-id="89193-127">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="89193-127">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="89193-128">Archivos</span><span class="sxs-lookup"><span data-stu-id="89193-128">File(s)</span></span>|<span data-ttu-id="89193-129">Description</span><span class="sxs-lookup"><span data-stu-id="89193-129">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89193-130">SendPortGroups.cs</span><span class="sxs-lookup"><span data-stu-id="89193-130">SendPortGroups.cs</span></span>|<span data-ttu-id="89193-131">Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="89193-131">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="89193-132">SendPortGroups.sln, SendPortGroups.csproj, SendPortGroups.suo</span><span class="sxs-lookup"><span data-stu-id="89193-132">SendPortGroups.sln, SendPortGroups.csproj, SendPortGroups.suo</span></span>|<span data-ttu-id="89193-133">Archivos de solución y proyecto para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="89193-133">Solution and project files for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="89193-134">Generación y ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="89193-134">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="89193-135">Procedimiento para generar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="89193-135">To build this sample</span></span>  
  
1.  <span data-ttu-id="89193-136">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución SendPortGroups.sln.</span><span class="sxs-lookup"><span data-stu-id="89193-136">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendPortGroups.sln.</span></span>  
  
2.  <span data-ttu-id="89193-137">En el Explorador de soluciones, haga doble clic en **SendPortGroups.cs** para abrir el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="89193-137">In Solution Explorer, double click **SendPortGroups.cs** to open the sample code.</span></span>  
  
3.  <span data-ttu-id="89193-138">Busque `root.ConnectionString` en la función `CreateSendPortGroup`.</span><span class="sxs-lookup"><span data-stu-id="89193-138">Find the `root.ConnectionString` in the `CreateSendPortGroup` function.</span></span>  <span data-ttu-id="89193-139">Debe cambiar la especificación del servidor para que señale correctamente al servidor SQL que hospeda la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="89193-139">You must change the server specification to correctly point to the SQL server hosting your BizTalk Management database.</span></span>  <span data-ttu-id="89193-140">También puede usar un punto (.) para conectarse al servidor SQL local.</span><span class="sxs-lookup"><span data-stu-id="89193-140">You can also use a period (.) to connect to the local SQL server.</span></span>  <span data-ttu-id="89193-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="89193-141">For example:</span></span>  
  
    ```  
    root.ConnectionString = "Integrated Security=SSPI;database=BizTalkMgmtDb;server=.";  
    ```  
  
4.  <span data-ttu-id="89193-142">Repita el paso 3 para las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="89193-142">Repeat step 3 for the following functions:</span></span>  
  
    -   <span data-ttu-id="89193-143">**EnumerateSendPortGroups**</span><span class="sxs-lookup"><span data-stu-id="89193-143">**EnumerateSendPortGroups**</span></span>  
  
    -   <span data-ttu-id="89193-144">**DeleteSendPortGroup**</span><span class="sxs-lookup"><span data-stu-id="89193-144">**DeleteSendPortGroup**</span></span>  
  
5.  <span data-ttu-id="89193-145">Guardar **SendPortGroups.cs**.</span><span class="sxs-lookup"><span data-stu-id="89193-145">Save **SendPortGroups.cs**.</span></span>  
  
6.  <span data-ttu-id="89193-146">En el menú principal, haga clic en **generar**y, a continuación, haga clic en **generar solución**.</span><span class="sxs-lookup"><span data-stu-id="89193-146">On the main menu, click **Build**, and then click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="89193-147">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="89193-147">To run this sample</span></span>  
  
1.  <span data-ttu-id="89193-148">Abra una ventana de comandos y desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="89193-148">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="89193-149">\<*Ejemplos de ruta de acceso*> \Admin\ExplorerOM\SendPortGroups\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="89193-149">\<*Samples Path*>\Admin\ExplorerOM\SendPortGroups\bin\Debug</span></span>  
  
2.  <span data-ttu-id="89193-150">Ejecute el archivo SendPortGroups.exe.</span><span class="sxs-lookup"><span data-stu-id="89193-150">Run the file SendPortGroups.exe.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="89193-151">Ejemplo de un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89193-151">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="89193-152">El siguiente fragmento de script de Windows PowerShell puede usarse para mostrar las mismas características de la **ExplorerOM** clases:</span><span class="sxs-lookup"><span data-stu-id="89193-152">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
Function CreateSendPortGroup($Catalog, $strName)  
{  
   #=== Register a trap handler to discard changes on exceptions ===#  
  
   $ErrorActionPreference="silentlycontinue"  
   trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  
  
   #=== Create a new send port group and set its name ===#  
  
   $NewSendPortGroup = $Catalog.AddNewSendPortGroup()  
   $NewSendPortGroup.Name = $strName  
  
   #=== Persist new ports to the BizTalk Management database ===#  
  
   Write-Host Adding "`"$($NewSendPortGroup.Name)`"..."  
   $catalog.SaveChanges();  
   Write-Host "`r`nCreateSendPortGroup() completed."  
}  
  
Function DeleteSendPortGroup($Catalog,$strName)  
{  
   #=== Register a trap handler to discard changes on exceptions ===#  
  
   $ErrorActionPreference="silentlycontinue"  
   trap { "Exception encountered DeleteSendPortGroup:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();}  
  
   #=== Delete this sample's new send ports by name ===#  
  
   $NewSendPortGroup = $Catalog.SendPortGroups[$strName]  
   $Catalog.RemoveSendPortGroup($NewSendPortGroup)  
  
   #=== Persist changes to the BizTalk Management database ===#  
  
   Write-Host "Deleting `"$strName`"..."  
   $catalog.SaveChanges();  
   Write-Host "DeleteSendPortGroup() completed."  
}  
  
Function EnumerateSendPortGroups($Catalog)  
{  
   #=== Register a trap handler to discard changes on exceptions ===#  
  
   $ErrorActionPreference="silentlycontinue"  
   trap { "Exception encountered During Enumeration:`r`n"; $_; "`r`n"}  
  
   #=== Display all send port groups by name ===#  
  
   $count = 1  
   foreach ($group in $catalog.SendPortGroups)  
   {  
     Write-Host "$count. $($group.Name)"  
     $count++  
   }  
  
   Write-Host "`r`nEnumerateSendPortGroups() completed."  
}  
  
Function PromptForSendPort($Catalog)  
{  
   #=== Provide a list of the send ports for the user to make a selection ===#  
  
   Write-Host "Here is a list of send ports:`r`n"  
   $count = 1  
   foreach($sendport in $Catalog.SendPorts)  
   {  
      Write-Host ($Count). ($Sendport.Name)  
      $count++  
   }     
  
   Write-Host "`r`nChoose a port to add to the group by ordinal (ex. 1,2, etc): " -nonewline  
   $selection = read-host  
   $selection = $Catalog.SendPorts[([int]$selection)-1]  
   Write-Host $Selection.Name selected.  
  
   return $Selection.Name     
}  
  
Function AddSendPortToSendPortGroup($Catalog,$strPortName,$strGroupName)  
{  
  
   #=== Add the user's selected send port to the group ===#  
  
   #========================================================#  
   #=== Presently, we have to use WMI from PowerShell    ===#  
   #=== This is because the methods on the collections   ===#  
   #=== are marked internal. So unfortunately the        ===#  
   #=== following very straightforward code won't work.  ===#  
   #========================================================#  
  
   # $sendportgroup = $Catalog.SendPortGroups[$strName]  
   # $sendportgroup.SendPorts.Add($Catalog.SendPorts[$strPortName])  
   # $catalog.SaveChanges();  
  
   #============================================================================#  
   #=== Get the WMI send port group representation to look up DB and server. ===#     
   #=== Expecting only one to match the query in this example.               ===#  
   #============================================================================#  
  
   $WQL = "select * from MSBTS_SendPortGroup where Name='" + $strGroupName + "'"  
   $groupset = gwmi -query ($WQL) -namespace "root\MicrosoftBizTalkServer"  
  
   #=== Create a new MSBTS_SendPortGroup2SendPort instance to map the port to the group ===#     
  
   $group2port = [WMICLASS]"root\MicrosoftBizTalkServer:MSBTS_SendPortGroup2SendPort"  
   $newPortEntry = [WMI] $group2port.psbase.CreateInstance()  
   $newPortEntry.MgmtDbServerOverride = $groupset.MgmtDbServerOverride   
   $newPortEntry.MgmtDbNameOverride = $groupset.MgmtDbNameOverride  
   $newPortEntry.SendPortGroupName = $groupset.Name  
   $newPortEntry.SendPortName = $strPortName  
   Write-Host "Adding $strPortName to $($groupset.Name)"  
  
   #=== Persist changes to the BizTalk Management database ===#  
  
   #=== POWERSHELL V1 BUG WORKAROUND =============================#  
   #=== First method call on a non-cimv2 WMI object can fail.  ===#  
   #=== The workaround in PowerShell V1 is to call GetType()   ===#  
   #=== as the first method.                                   ===#   
   $ErrorActionPreference="silentlycontinue"                     
   trap {}  
   $newPortEntry.GetType()  
   #=== POWERSHELL V1 BUG WORKAROUND =============================#  
  
   $ErrorActionPreference="continue"                     
   [void] $newPortEntry.Put()  
  
   #=== Since we used WMI to update the BizTalk Management database, ===#  
   #=== refresh our BtsExplorerCatalog to have an updated DB view.   ===#  
  
   $Catalog.Refresh()  
   Write-Host "AddSendPortToSendPortGroup() completed."  
}  
  
Function DeleteSendPortFromSendPortGroup($Catalog, $strPortName, $strGroupName)  
{  
   #========================================================#  
   #=== Presently, we have to use WMI from PowerShell    ===#  
   #=== This is because the methods on the collections   ===#  
   #=== are marked internal. So unfortunately the        ===#  
   #=== following very straightforward code won't work.  ===#  
   #========================================================#  
  
   # $sendportgroup = $Catalog.SendPortGroups[$strGroupName]  
   # $sendportgroup.SendPorts.Remove($Catalog.SendPorts[$strPortName])  
   # $catalog.SaveChanges();  
  
   #============================================================================#  
   #=== Get the WMI send port to group instance and delete it.               ===#     
   #=== Expecting only one to match the query in this example.               ===#  
   #============================================================================#  
  
   $WQL = "select * from MSBTS_SendPortGroup2SendPort where " +   
          "SendPortName='" + $strPortName + "' and " +   
          "SendPortGroupName='" + $strGroupName + "'"  
  
   $groupset = gwmi -query ($WQL) -namespace "root\MicrosoftBizTalkServer"  
  
   write-host "Removing $strPortName from $strGroupName..."  
   $groupset.Delete();  
  
   #=== Since we used WMI to update the BizTalk Management database, ===#  
   #=== refresh our BtsExplorerCatalog to have an updated DB view.   ===#  
  
   $Catalog.Refresh()  
   Write-Host "DeleteSendPortFromSendPortGroup() completed."  
}  
  
#========================#  
#=== Main Script Body ===#  
#========================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "DATABASE=BizTalkMgmtDb;Integrated Security=SSPI;SERVER=."  
  
#=== Exercise the CreateSendPortGroup function to create a new send port group ===#  
  
$SendPortGroupName = "PowerShell Sample Send Port Group"  
  
Write-Host "`r`n============================="  
Write-Host "=== CreateSendPortGroup() ==="  
Write-Host "=============================`r`n"  
CreateSendPortGroup $Catalog $SendPortGroupName  
  
#=== Enumerate all send port groups to view the new one ===#  
  
Write-Host "`r`n================================="  
Write-Host "=== EnumerateSendPortGroups() ==="  
Write-Host "=================================`r`n"  
EnumerateSendPortGroups $Catalog  
  
#=== Add a send port to the group ===#  
  
Write-Host "`r`n===================================="  
Write-Host "=== AddSendPortToSendPortGroup() ==="  
Write-Host "====================================`r`n"  
$SendPortName = PromptForSendPort($Catalog)  
AddSendPortToSendPortGroup $Catalog $SendPortName $SendPortGroupName  
  
#=== Remove the send port from the group ===#  
  
Write-Host "`r`n========================================="  
Write-Host "=== DeleteSendPortFromSendPortGroup() ==="  
Write-Host "=========================================`r`n"  
DeleteSendPortFromSendPortGroup $Catalog $SendPortName $SendPortGroupName  
  
#=== Delete the group ===#  
  
Write-Host "`r`n============================="  
Write-Host "=== DeleteSendPortGroup() ==="  
Write-Host "=============================`r`n"  
DeleteSendPortGroup $Catalog $SendPortGroupName  
  
Write-Host  
```  
  
 <span data-ttu-id="89193-153">A continuación se indica el resultado esperado del ejemplo tras la ejecución del ejemplo de script de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89193-153">Here is example expected output from running the Windows PowerShell script sample.</span></span>  
  
```  
PS C:\> .\sendportgroups.ps1  
  
=============================  
=== CreateSendPortGroup() ===  
=============================  
  
Adding "PowerShell Sample Send Port Group"...  
  
CreateSendPortGroup() completed.  
  
=================================  
=== EnumerateSendPortGroups() ===  
=================================  
  
1. PowerShell Sample Send Port Group  
  
EnumerateSendPortGroups() completed.  
  
====================================  
=== AddSendPortToSendPortGroup() ===  
====================================  
  
Here is a list of send ports:  
  
1 . ResendPort  
2 . HelloWorldSendPort  
3 . ToCustomerSendPort  
4 . CBRUSSendPort  
5 . CBRCANSendPort  
6 . SendportCANOrders  
  
Choose a port to add to the group by ordinal (ex. 1,2, etc): 2  
HelloWorldSendPort selected.  
Adding HelloWorldSendPort to PowerShell Sample Send Port Group  
AddSendPortToSendPortGroup() completed.  
  
=========================================  
=== DeleteSendPortFromSendPortGroup() ===  
=========================================  
  
Removing HelloWorldSendPort from PowerShell Sample Send Port Group...  
DeleteSendPortFromSendPortGroup() completed.  
  
=============================  
=== DeleteSendPortGroup() ===  
=============================  
  
Deleting "PowerShell Sample Send Port Group"...  
DeleteSendPortGroup() completed.  
```  
  
## <a name="see-also"></a><span data-ttu-id="89193-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="89193-154">See Also</span></span>  
 [<span data-ttu-id="89193-155">Administración-ExplorerOM (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="89193-155">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)