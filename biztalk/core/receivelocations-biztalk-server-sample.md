---
title: ReceiveLocations (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d75941-3973-4166-91b0-f1192b25a804
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df19296fcf6c93d582034464402597248335e826
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019172"
---
# <a name="receivelocations-biztalk-server-sample"></a><span data-ttu-id="e8f76-102">ReceiveLocations (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="e8f76-102">ReceiveLocations (BizTalk Server Sample)</span></span>
<span data-ttu-id="e8f76-103">El ejemplo ReceiveLocations muestra cómo crear ubicaciones de recepción en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante el uso de la **ExplorerOM** objetos de administración.</span><span class="sxs-lookup"><span data-stu-id="e8f76-103">The ReceiveLocations sample demonstrates how to create receive locations in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by using the **ExplorerOM** administration objects.</span></span> <span data-ttu-id="e8f76-104">Para obtener más información acerca de las ubicaciones de recepción en general, vea [ubicaciones de recepción](../core/receive-locations.md).</span><span class="sxs-lookup"><span data-stu-id="e8f76-104">For more information about receive locations in general, see [Receive Locations](../core/receive-locations.md).</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="e8f76-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e8f76-105">Prerequisites</span></span>  

- <span data-ttu-id="e8f76-106">Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e8f76-106">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="e8f76-107">El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts.</span><span class="sxs-lookup"><span data-stu-id="e8f76-107">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="e8f76-108">Para obtener más información, vea [Examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).</span><span class="sxs-lookup"><span data-stu-id="e8f76-108">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="e8f76-109">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8f76-109">What This Sample Does</span></span>  
 <span data-ttu-id="e8f76-110">Este ejemplo muestra cómo utilizar el **ExplorerOM** clases administrativas para crear y configurar puertos de recepción y ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="e8f76-110">This sample demonstrates using the **ExplorerOM** administrative classes to create and configure receive ports and receive locations.</span></span> <span data-ttu-id="e8f76-111">En este tema también se incluye un script de ejemplo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8f76-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="e8f76-112">El ejemplo realiza las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="e8f76-112">The sample performs the following operations:</span></span>  

-   <span data-ttu-id="e8f76-113">Crear un nuevo puerto de recepción denominado “Mi puerto de recepción”.</span><span class="sxs-lookup"><span data-stu-id="e8f76-113">Create a new receive port named “My Receive Port”.</span></span>  

-   <span data-ttu-id="e8f76-114">Crear una nueva ubicación de recepción asociada con el nuevo puerto y configurada para usar el protocolo de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="e8f76-114">Create a new receive location associated with the new port and configured to use the HTTP transport protocol.</span></span>  

-   <span data-ttu-id="e8f76-115">En este ejemplo también se incluyen procedimientos de ejemplo para eliminar y enumerar puertos y ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="e8f76-115">This sample also contains example procedures to delete and enumerate receive ports and locations.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="e8f76-116">Dónde encontrar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8f76-116">Where To Find This Sample</span></span>  
 <span data-ttu-id="e8f76-117">Este ejemplo se encuentra en la siguiente ubicación de SDK:</span><span class="sxs-lookup"><span data-stu-id="e8f76-117">This sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="e8f76-118">\<*Ejemplos de la ruta de acceso* \> \Admin\ExplorerOM\ReceiveLocations</span><span class="sxs-lookup"><span data-stu-id="e8f76-118">\<*Samples Path*\> \Admin\ExplorerOM\ReceiveLocations</span></span>  

 <span data-ttu-id="e8f76-119">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="e8f76-119">The following table shows the files in this sample and describes their purpose.</span></span>  


|                     <span data-ttu-id="e8f76-120">Archivos</span><span class="sxs-lookup"><span data-stu-id="e8f76-120">File(s)</span></span>                      |                                                   <span data-ttu-id="e8f76-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8f76-121">Description</span></span>                                                    |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|               <span data-ttu-id="e8f76-122">ReceiveLocations.cs</span><span class="sxs-lookup"><span data-stu-id="e8f76-122">ReceiveLocations.cs</span></span>                | [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]<span data-ttu-id="e8f76-123"> archivo de código fuente para las operaciones que se muestran en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e8f76-123"> source file for the operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="e8f76-124">ReceiveLocations.sln y ReceiveLocations.csproj</span><span class="sxs-lookup"><span data-stu-id="e8f76-124">ReceiveLocations.sln and ReceiveLocations.csproj</span></span> |                                   <span data-ttu-id="e8f76-125">Archivos de solución y proyecto para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e8f76-125">Solution and project files for this sample.</span></span>                                    |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="e8f76-126">Generación y ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8f76-126">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="e8f76-127">Procedimiento para generar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8f76-127">To build this sample</span></span>  

1. <span data-ttu-id="e8f76-128">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución ReceiveLocations.sln.</span><span class="sxs-lookup"><span data-stu-id="e8f76-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file ReceiveLocations.sln.</span></span>  

2. <span data-ttu-id="e8f76-129">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="e8f76-129">On the **Build** menu, click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="e8f76-130">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8f76-130">To run this sample</span></span>  

1. <span data-ttu-id="e8f76-131">Abra un símbolo del sistema con privilegios de administrador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8f76-131">Open a command prompt with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges.</span></span>  

2. <span data-ttu-id="e8f76-132">Cambie a la \< *ejemplos*\>directory \Admin\ExplorerOM\ReceiveLocations\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="e8f76-132">Change to the \<*Samples*\>\Admin\ExplorerOM\ReceiveLocations\bin\debug directory.</span></span>  

3. <span data-ttu-id="e8f76-133">Ejecute ReceiveLocations.exe.</span><span class="sxs-lookup"><span data-stu-id="e8f76-133">Run ReceiveLocations.exe.</span></span>  

4. <span data-ttu-id="e8f76-134">Visualice el nuevo puerto de recepción y ubicación de recepción mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8f76-134">View the new receive port and receive location with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="e8f76-135">Ejemplo de un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8f76-135">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="e8f76-136">En el siguiente script de ejemplo de PowerShell se muestran las mismas operaciones que la versión [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8f76-136">The following PowerShell example script demonstrates the same operations as the [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] version.</span></span> <span data-ttu-id="e8f76-137">Asegúrese de que la política de ejecución de scripts se ha configurado correctamente, tal como se indica en la sección de requisitos de este tema.</span><span class="sxs-lookup"><span data-stu-id="e8f76-137">Make sure the script execution policy has been properly configured as mentioned in the requirements section of this topic.</span></span>  

```  
#==================================================================#  
#===                                                            ===#  
#=== Create a new receive port named "My Receive Port" as an    ===#  
#=== example.                                                   ===#  
#===                                                            ===#  
#=== A new receive location will also be created and associated ===#  
#=== with the receive port.                                     ===#  
#===                                                            ===#  
#==================================================================#  
Function CreateAndConfigureReceiveLocation()  
{  
   $myreceivePort = $catalog.AddNewReceivePort($false)  

   #=== Note that if you don’t set the name property for the receieve port, ===#  
   #=== it will create a new receive location and add it to the receive     ===#     
   #=== port.                                                               ===#  

   $myreceivePort.Name = "My Receive Port"  

   #=== Create a new receive location and add it to the receive port ===#  
   $myreceiveLocation = $myreceivePort.AddNewReceiveLocation()  

   foreach ($handler in $catalog.ReceiveHandlers)  
   {  
      if ($handler.TransportType.Name -eq "HTTP")  
      {  
         $myreceiveLocation.ReceiveHandler = $handler  
         break  
      }  
   }  

   #=== Associate a transport protocol and URI with the receive location. ===#   
   $myreceiveLocation.TransportType = $catalog.ProtocolTypes["HTTP"]  
   $myreceiveLocation.Address = "/home"  

   #=== Assign the first receive pipeline found to process the message. ===#  
   foreach ($pipeline in $catalog.Pipelines)  
   {  
      if ($pipeline.Type -eq [Microsoft.Biztalk.ExplorerOM.PipelineType] "Receive")  
      {  
         $myreceiveLocation.ReceivePipeline = $pipeline  
         break  
      }  

      #=== Enable the receive location. ===#  
      $myreceiveLocation.Enable = $true  

      #=== Optional Properties ===#  
      $myreceiveLocation.FragmentMessages = [Microsoft.BizTalk.ExplorerOM.Fragmentation] "Yes"  
      $myreceiveLocation.ServiceWindowEnabled = $false    
   }  

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

    #=== Enumerate the receive locations. ===#  
    foreach ($location in $receivePort.ReceiveLocations)  
    {  
        if (($location.Name -eq "Receive Location1") -and ($location.IsPrimary -eq $false))  
        {  
          $receivePort.RemoveReceiveLocation($location)  
        }  
    }  

    $catalog.RemoveReceivePort($receivePort)    

    #=== Try to commit the changes made so far. If the commit fails, ===#  
    #=== roll back all changes in the trap handler.                  ===#  
    $catalog.SaveChanges()  
  }  
}  

#================================================================#  
#===                                                          ===#  
#=== Enumerate the receive ports and their receive locations. ===#  
#===                                                          ===#  
#================================================================#  
Function EnumerateReceiveLocations  
{  
   #=== Enumerate the receive locations in each of the receive ports. ===#  
   foreach ($receivePort in $catalog.ReceivePorts)  
   {  
      Write-host "`r`n$($receivePort.Name)"  

      #=== Enumerate the receive locations. ===#  
      foreach ($location in $receivePort.ReceiveLocations)  
      {  
         Write-Host "`t$($location.Name)"  
      }  
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
  "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution so we can attempt to clean up the receive port...`r`n"  
  $Catalog.DiscardChanges()  
}  

#=== Create the new receive port with its new receive location ===#  
CreateAndConfigureReceiveLocation  
Write-Host "`r`n`"My Receive Port`" created."  

#=== Enumerate each receive port along with its receive locations ===#  
Write-Host "`r`nEnumerating all receive ports...`r`n"  
EnumerateReceiveLocations  

#=== Prompt before removing the new example receive port and location ===#  
Write-Host "`r`nPress <ENTER> to delete `"My Receive Port`"..."  
Read-Host  
DeleteReceivePort  

#=== Enumerate again to show the receive port and location was removed ===#  
Write-Host "`r`nEnumerating all receive ports to show `"My Receive Port`" was removed...`r`n"  
EnumerateReceiveLocations  

```  

 <span data-ttu-id="e8f76-138">Aquí se muestra un ejemplo de la ejecución de scripts de PowerShell que muestra el puerto de recepción y la ubicación que se están creando y eliminando:</span><span class="sxs-lookup"><span data-stu-id="e8f76-138">Here is example output from the PowerShell script execution showing the receive port and location being created and deleted:</span></span>  

```  
PS C:\> .\ReceiveLocations.ps1  

"My Receive Port" created.  

Enumerating all receive ports...  

BatchControlMessageRecvPort  
        BatchControlMessageRecvLoc  

ResendReceivePort  
        ResendReceiveLocation  

HelloWorldReceivePort  
        HelloWorldReceiveLocation  

CBRReceivePort  
        CBRReceiveLocation  

RP_ReceivePOFromInternal  
        RL_ReceivePOFromInternal  

RP_ShipmentAgency1_OrderFiles  
        RL_ShipmentAgency1_OrderFiles  

RP_ShipmentAgency2_OrderFiles  
        RL_ShipmentAgency2_OrderFiles  

RP_ReceivePOFromBuyer  
        RL_ReceivePOFromBuyer  

RP_Receive_ShipmentAgency_Ack  
        RL_Receive_ShipmentAgency_Ack  

My Receive Port  
        Receive Location1  

Press <ENTER> to delete "My Receive Port"...  

Enumerating all receive ports to show "My Receive Port" was removed...  

BatchControlMessageRecvPort  
        BatchControlMessageRecvLoc  

ResendReceivePort  
        ResendReceiveLocation  

HelloWorldReceivePort  
        HelloWorldReceiveLocation  

CBRReceivePort  
        CBRReceiveLocation  

RP_ReceivePOFromInternal  
        RL_ReceivePOFromInternal  

RP_ShipmentAgency1_OrderFiles  
        RL_ShipmentAgency1_OrderFiles  

RP_ShipmentAgency2_OrderFiles  
        RL_ShipmentAgency2_OrderFiles  

RP_ReceivePOFromBuyer  
        RL_ReceivePOFromBuyer  

RP_Receive_ShipmentAgency_Ack  
        RL_Receive_ShipmentAgency_Ack  

```  

## <a name="see-also"></a><span data-ttu-id="e8f76-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8f76-139">See Also</span></span>  
 <span data-ttu-id="e8f76-140">[Las ubicaciones de recepción](../core/receive-locations.md) </span><span class="sxs-lookup"><span data-stu-id="e8f76-140">[Receive Locations](../core/receive-locations.md) </span></span>  
 [<span data-ttu-id="e8f76-141">Admin\ExplorerOM (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="e8f76-141">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)