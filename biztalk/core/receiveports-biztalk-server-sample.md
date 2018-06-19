---
title: ReceivePorts (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c403005d-5e0e-4015-b138-6318e03192af
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e34fcb08776d6be2c98e7c0e71d754caf9bdbb6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971730"
---
# <a name="receiveports-biztalk-server-sample"></a><span data-ttu-id="cbcf4-102">ReceivePorts (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="cbcf4-102">ReceivePorts (BizTalk Server Sample)</span></span>
<span data-ttu-id="cbcf4-103">El ejemplo ReceivePorts muestra cómo crear un nuevo puerto de recepción mediante el uso de la **ExplorerOM** clases administrativas.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-103">The ReceivePorts sample demonstrates how to create a new receive port by using the **ExplorerOM** administrative classes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cbcf4-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cbcf4-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="cbcf4-105">Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="cbcf4-106">El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="cbcf4-107">Para obtener más información, vea [Examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).</span><span class="sxs-lookup"><span data-stu-id="cbcf4-107">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="cbcf4-108">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbcf4-108">What This Sample Does</span></span>  
 <span data-ttu-id="cbcf4-109">Este ejemplo muestra cómo utilizar el **BtsCatalogExplorer** y **puertoRecepción** clases a partir de la **Microsoft.BizTalk.ExplorerOM** espacio de nombres para agregar un nuevo puerto de recepción para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbcf4-109">This sample demonstrates using the **BtsCatalogExplorer** and **ReceivePort** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to add a new receive port to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="cbcf4-110">El ejemplo está escrito en Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbcf4-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="cbcf4-111">En este tema también se incluye un script de ejemplo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="cbcf4-112">El ejemplo muestra las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="cbcf4-112">The sample demonstrates the following operations:</span></span>  
  
-   <span data-ttu-id="cbcf4-113">Conectarse a la base de datos de administración de BizTalk mediante el **BtsCatalogExplorer** clase.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  
  
-   <span data-ttu-id="cbcf4-114">Agregar un nuevo puerto de recepción mediante el uso de la **AddNewReceivePort** método.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-114">Adding a new receive port by using the **AddNewReceivePort** method.</span></span>  
  
-   <span data-ttu-id="cbcf4-115">Enumeración de los puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-115">Enumerating receive ports.</span></span>  
  
-   <span data-ttu-id="cbcf4-116">Eliminación de los puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-116">Deleting receive ports.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="cbcf4-117">Dónde encontrar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbcf4-117">Where To Find This Sample</span></span>  
 <span data-ttu-id="cbcf4-118">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="cbcf4-118">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="cbcf4-119">\<*Ejemplos de ruta de acceso*\>\Admin\ExplorerOM\ReceivePorts</span><span class="sxs-lookup"><span data-stu-id="cbcf4-119">\<*Samples Path*\>\Admin\ExplorerOM\ReceivePorts</span></span>  
  
 <span data-ttu-id="cbcf4-120">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="cbcf4-121">Archivos</span><span class="sxs-lookup"><span data-stu-id="cbcf4-121">File(s)</span></span>|<span data-ttu-id="cbcf4-122">Description</span><span class="sxs-lookup"><span data-stu-id="cbcf4-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cbcf4-123">ReceivePorts.cs</span><span class="sxs-lookup"><span data-stu-id="cbcf4-123">ReceivePorts.cs</span></span>|<span data-ttu-id="cbcf4-124">Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-124">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="cbcf4-125">ReceivePorts.sln y ReceivePorts.csproj</span><span class="sxs-lookup"><span data-stu-id="cbcf4-125">ReceivePorts.sln and ReceivePorts.csproj</span></span>|<span data-ttu-id="cbcf4-126">Archivo de solución y un proyecto para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-126">Solution and project file for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="cbcf4-127">Generación y ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbcf4-127">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="cbcf4-128">Procedimiento para generar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbcf4-128">To build this sample</span></span>  
  
1.  <span data-ttu-id="cbcf4-129">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución ReceivePorts.sln.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-129">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file ReceivePorts.sln.</span></span>  
  
2.  <span data-ttu-id="cbcf4-130">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-130">On the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="cbcf4-131">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbcf4-131">To run this sample</span></span>  
  
1.  <span data-ttu-id="cbcf4-132">Abra una ventana de comandos y desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="cbcf4-132">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="cbcf4-133">\<*Ejemplos de ruta de acceso*\>\Admin\ExplorerOM\ReceivePorts\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="cbcf4-133">\<*Samples Path*\>\Admin\ExplorerOM\ReceivePorts\bin\Debug</span></span>  
  
2.  <span data-ttu-id="cbcf4-134">Ejecute el archivo ReceivePorts.exe.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-134">Run the file ReceivePorts.exe.</span></span> <span data-ttu-id="cbcf4-135">El nuevo puerto de recepción deben crearse y se muestra en la enumeración de puertos.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-135">The new receive port should be created and shown in the port enumeration.</span></span> <span data-ttu-id="cbcf4-136">Después de la enumeración, el puerto de recepción se quita inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="cbcf4-136">After the enumeration the receive port is immediately removed.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="cbcf4-137">Ejemplo de un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbcf4-137">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="cbcf4-138">El siguiente script de ejemplo de Windows PowerShell puede utilizarse para mostrar las mismas características de la **ExplorerOM** clases:</span><span class="sxs-lookup"><span data-stu-id="cbcf4-138">The following Windows PowerShell example script can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
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
  
 <span data-ttu-id="cbcf4-139">Éste es un ejemplo muestra la ejecución del script de Windows PowerShell para crear el nuevo puerto de recepción:</span><span class="sxs-lookup"><span data-stu-id="cbcf4-139">Here is an example of running the Windows PowerShell script to create the new receive port:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cbcf4-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbcf4-140">See Also</span></span>  
 [<span data-ttu-id="cbcf4-141">Admin\ExplorerOM (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="cbcf4-141">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)