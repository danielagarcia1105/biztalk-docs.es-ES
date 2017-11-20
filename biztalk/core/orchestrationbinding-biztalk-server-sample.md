---
title: OrchestrationBinding (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea14c0db-ea83-4bf9-b417-f877b3cb1bf9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d539b4249e02422b4189d9c8daea5c19011c4722
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="orchestrationbinding-biztalk-server-sample"></a><span data-ttu-id="44e16-102">OrchestrationBinding (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="44e16-102">OrchestrationBinding (BizTalk Server Sample)</span></span>
<span data-ttu-id="44e16-103">En el ejemplo de enlace de orquestación se muestra el uso de los objetos administrativos de [Microsoft.BizTalk.ExplorerOM](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.aspx) para configurar y administrar las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="44e16-103">The Orchestration Binding sample demonstrates using the [Microsoft.BizTalk.ExplorerOM](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.aspx) administrative objects to configure and manage orchestrations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="44e16-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="44e16-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="44e16-105">Este ejemplo requiere que el ejemplo HelloWorld se pueden implementar mediante la ejecución de setup.bat ubicado en el \< *ruta de ejemplos*> \Orchestrations\HelloWorld directory.</span><span class="sxs-lookup"><span data-stu-id="44e16-105">This sample requires that the HelloWorld sample be deployed by running setup.bat located in the \<*Samples Path*>\Orchestrations\HelloWorld directory.</span></span>  
  
-   <span data-ttu-id="44e16-106">Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="44e16-106">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="44e16-107">El ejemplo del script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts.</span><span class="sxs-lookup"><span data-stu-id="44e16-107">The Windows PowerShell script example requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="44e16-108">Para obtener más información, vea [Examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).</span><span class="sxs-lookup"><span data-stu-id="44e16-108">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="44e16-109">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="44e16-109">What This Sample Does</span></span>  
 <span data-ttu-id="44e16-110">En este ejemplo muestra cómo usar los objetos de administración en el espacio de nombres **Microsoft.BizTalk.ExplorerOM** para administrar las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="44e16-110">This sample demonstrates using the administrative objects in the **Microsoft.BizTalk.ExplorerOM** namespace to manage orchestrations.</span></span> <span data-ttu-id="44e16-111">En el ejemplo se muestran las siguientes operaciones con los objetos **ExplorerOM** :</span><span class="sxs-lookup"><span data-stu-id="44e16-111">The sample demonstrates the following operations using the **ExplorerOM** objects:</span></span>  
  
-   <span data-ttu-id="44e16-112">Conexión a la base de datos de administración de BizTalk mediante la clase[Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.btscatalogexplorer.aspx) .</span><span class="sxs-lookup"><span data-stu-id="44e16-112">Connecting to the BizTalk Management database by using the[Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.btscatalogexplorer.aspx) class.</span></span>  
  
-   <span data-ttu-id="44e16-113">Detener e iniciar orquestaciones mediante el cambio de la propiedad **Estado** de la clase [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) .</span><span class="sxs-lookup"><span data-stu-id="44e16-113">Stopping and starting orchestrations by changing the **Status** property of the [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) class.</span></span>  
  
-   <span data-ttu-id="44e16-114">Dar de alta y de baja orquestaciones mediante el cambio de la propiedad **Estado** de la clase [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) .</span><span class="sxs-lookup"><span data-stu-id="44e16-114">Enlisting and unenlisting orchestrations by changing the **Status** property of the [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) class.</span></span>  
  
-   <span data-ttu-id="44e16-115">Enlazar y desenlazar orquestaciones mediante el uso de la colección **Puertos** de la clase [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) .</span><span class="sxs-lookup"><span data-stu-id="44e16-115">Binding and unbinding orchestrations by using the **Ports** collection on the [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) class.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="44e16-116">Dónde encontrar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="44e16-116">Where To Find This Sample</span></span>  
 <span data-ttu-id="44e16-117">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="44e16-117">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="44e16-118">\<*Ejemplos de ruta de acceso*> \Admin\ExplorerOM\OrchestrationBinding</span><span class="sxs-lookup"><span data-stu-id="44e16-118">\<*Samples Path*>\Admin\ExplorerOM\OrchestrationBinding</span></span>  
  
 <span data-ttu-id="44e16-119">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="44e16-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="44e16-120">Archivos</span><span class="sxs-lookup"><span data-stu-id="44e16-120">File(s)</span></span>|<span data-ttu-id="44e16-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="44e16-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44e16-122">OrchestrationBinding.cs</span><span class="sxs-lookup"><span data-stu-id="44e16-122">OrchestrationBinding.cs</span></span>|<span data-ttu-id="44e16-123">Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="44e16-123">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="44e16-124">OrchestrationBinding.sln, OrchestrationBinding.csproj, OrchestrationBinding.suo</span><span class="sxs-lookup"><span data-stu-id="44e16-124">OrchestrationBinding.sln, OrchestrationBinding.csproj, OrchestrationBinding.suo</span></span>|<span data-ttu-id="44e16-125">Archivos de solución y proyecto para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="44e16-125">Solution and project files for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="44e16-126">Generación y ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="44e16-126">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="44e16-127">Procedimiento para generar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="44e16-127">To build this sample</span></span>  
  
1.  <span data-ttu-id="44e16-128">Asegúrese de haber completado los pasos para crear e inicializar el ejemplo HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="44e16-128">Make sure you have completed the steps for building and initializing the HelloWorld sample.</span></span> <span data-ttu-id="44e16-129">Estos pasos se proporcionan en [HelloWorld (ejemplo de BizTalk Server)](../core/helloworld-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="44e16-129">Those steps are provided in [HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md).</span></span>  
  
2.  <span data-ttu-id="44e16-130">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución OrchestrationBinding.sln.</span><span class="sxs-lookup"><span data-stu-id="44e16-130">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file OrchestrationBinding.sln.</span></span>  
  
3.  <span data-ttu-id="44e16-131">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="44e16-131">On the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="44e16-132">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="44e16-132">To run this sample</span></span>  
  
1.  <span data-ttu-id="44e16-133">Abra una ventana de comandos y desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="44e16-133">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="44e16-134">\<*Ejemplos de ruta de acceso*> \Admin\ExplorerOM\OrchestrationBinding\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="44e16-134">\<*Samples Path*>\Admin\ExplorerOM\OrchestrationBinding\bin\Debug</span></span>  
  
2.  <span data-ttu-id="44e16-135">Ejecute el archivo OrchestrationBinding.exe y siga las instrucciones que proporciona el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="44e16-135">Run the file OrchestrationBinding.exe and follow the directions provided by the sample.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="44e16-136">Ejemplo de un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44e16-136">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="44e16-137">El siguiente script de Windows PowerShell se puede usar para mostrar las mismas características de las clases **ExplorerOM** :</span><span class="sxs-lookup"><span data-stu-id="44e16-137">The following Windows PowerShell script can be used to demonstrate the same features of the **ExplorerOM** classes.</span></span>  
  
```  
  
Function RefreshPrompt($oldstatus,$newstatus)  
{  
  Write-Host Orchestration Status should now be `"$oldstatus`"  
  Write-Host Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify   
  
  if ($newstatus)  
  {  
    Write-Host Pressing `<Enter`> now will $newstatus the orchestration using ExplorerOM`.`.`.  
    Read-Host  
    Write-Host "=== Please wait, attempting to $newstatus the orchestration... ===`r`n"  
  }  
  else  
  {  
    write-host `r`n  
  }  
}  
  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=== This sample expects the HelloWorld sample orchestration to be using the ===#  
#=== default name "Biztalk Application 1"                                    ===#  
  
$HelloWorldApp = $Catalog.Applications["Biztalk Application 1"]  
$orch = $HelloWorldApp.orchestrations["Microsoft.Samples.BizTalk.HelloWorld.HelloSchedule"]  
  
#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we need to re-enlist, ===#  
#=== re-bind, or restart the orchestration.                     ===#  
#==================================================================#  
  
$ErrorActionPreference="silentlycontinue"  
trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution...`r`n";$Catalog.DiscardChanges();}  
  
write-host `r`nMake sure the "HelloWorld" sample application is deployed and running.  
write-host By default it will be listed in the BizTalk Server Administration Console  
write-host with the application name: `"BizTalk.Application.1`"`r`n  
  
#==========================================================#  
#=== Change orchestration state from Started to stopped ===#  
#==========================================================#  
  
RefreshPrompt Started stop  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Enlisted"  
$Catalog.SaveChanges()  
  
#=============================================================#  
#=== Change orchestration state from stopped to unenlisted ===#  
#=============================================================#  
  
RefreshPrompt Stopped unenlist  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Unenlisted"  
$Catalog.SaveChanges()  
  
#=============================================================#  
#=== Change orchestration state from unenlisted to unbound ===#  
#=============================================================#  
  
RefreshPrompt Unenlisted unbind  
$orch.Ports["SendInvoicePort"].SendPort = $null  
$orch.Ports["ReceivePOPort"].ReceivePort = $null;  
$orch.Host = $null  
$Catalog.SaveChanges()  
  
#==================================================================#  
#=== Change orchestration state from unbound back to unenlisted ===#  
#==================================================================#  
  
RefreshPrompt Unenlisted`(Unbound`) re-bind  
$orch.Ports["SendInvoicePort"].SendPort = $Catalog.SendPorts["HelloWorldSendPort"]  
$orch.Ports["ReceivePOPort"].ReceivePort = $Catalog.ReceivePorts["HelloWorldReceivePort"]  
$orch.Host = $Catalog.Hosts["BizTalkServerApplication"]  
$Catalog.SaveChanges()  
  
#==================================================================#  
#=== Change orchestration state from unenlisted back to stopped ===#  
#==================================================================#  
  
RefreshPrompt Unenlisted enlist  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Enlisted"  
$Catalog.SaveChanges()  
  
#===============================================================#  
#=== Change orchestration state from stopped back to started ===#  
#===============================================================#  
  
RefreshPrompt Stopped restart  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Started"  
$Catalog.SaveChanges()  
  
RefreshPrompt Started  
  
```  
  
 <span data-ttu-id="44e16-138">A continuación se proporciona el resultado de la ejecución del script de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44e16-138">Here is an example output from running the Windows PowerShell script.</span></span>  
  
```  
PS C:\> .\OrchestrationBind.ps1  
  
Make sure the HelloWorld sample application is deployed and running.  
By default it will be listed in the BizTalk Server Administration Console  
with the application name: "BizTalk.Application.1"  
  
Orchestration Status should now be "Started"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will stop the orchestration using ExplorerOM...  
  
=== Please wait, attempting to stop the orchestration... ===  
  
Orchestration Status should now be "Stopped"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will unenlist the orchestration using ExplorerOM...  
  
=== Please wait, attempting to unenlist the orchestration... ===  
  
Orchestration Status should now be "Unenlisted"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will unbind the orchestration using ExplorerOM...  
  
=== Please wait, attempting to unbind the orchestration... ===  
  
Orchestration Status should now be "Unenlisted(Unbound)"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will re-bind the orchestration using ExplorerOM...  
  
=== Please wait, attempting to re-bind the orchestration... ===  
  
Orchestration Status should now be "Unenlisted"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will enlist the orchestration using ExplorerOM...  
  
=== Please wait, attempting to enlist the orchestration... ===  
  
Orchestration Status should now be "Stopped"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will restart the orchestration using ExplorerOM...  
  
=== Please wait, attempting to restart the orchestration... ===  
  
Orchestration Status should now be "Started"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="44e16-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="44e16-139">See Also</span></span>  
 <span data-ttu-id="44e16-140">[Administración-ExplorerOM (carpeta de ejemplos de BizTalk Server)](../core/admin-explorerom-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="44e16-140">[Admin-ExplorerOM (BizTalk Server Samples Folder)](../core/admin-explorerom-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="44e16-141">HelloWorld (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="44e16-141">HelloWorld (BizTalk Server Sample)</span></span>](../core/helloworld-biztalk-server-sample.md)