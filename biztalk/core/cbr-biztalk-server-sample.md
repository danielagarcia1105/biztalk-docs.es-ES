---
title: CBR (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add16683-4090-4854-8d6e-923b58937e9d
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a4f27cd62a546213041be594094ff6b5e39274b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005325"
---
# <a name="cbr-biztalk-server-sample"></a><span data-ttu-id="5a03b-102">CBR (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="5a03b-102">CBR (BizTalk Server Sample)</span></span>
<span data-ttu-id="5a03b-103">El ejemplo CBR muestra cómo utilizar el **ExplorerOM** objetos de administración para agregar y configurar nuevos puertos de envío para enrutamiento por contenidos de mensajes de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5a03b-103">The CBR sample demonstrates using the **ExplorerOM** administrative objects to add and configure new send ports for content-based routing of BizTalk messages.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="5a03b-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5a03b-104">Prerequisites</span></span>  

- <span data-ttu-id="5a03b-105">Este ejemplo requiere que se ha implementado CBRSample mediante la ejecución de setup.bat ubicado en el \< *ruta de ejemplos*\>directory \Messaging\CBRSample.</span><span class="sxs-lookup"><span data-stu-id="5a03b-105">This sample requires that the CBRSample be deployed by running setup.bat located in the \<*Samples Path*\>\Messaging\CBRSample directory.</span></span>  

- <span data-ttu-id="5a03b-106">Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5a03b-106">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="5a03b-107">El ejemplo del script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts.</span><span class="sxs-lookup"><span data-stu-id="5a03b-107">The Windows PowerShell script example requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="5a03b-108">Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).</span><span class="sxs-lookup"><span data-stu-id="5a03b-108">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="5a03b-109">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a03b-109">What This Sample Does</span></span>  
 <span data-ttu-id="5a03b-110">Este ejemplo muestra cómo utilizar los objetos de administración en el **Microsoft.BizTalk.ExplorerOM** espacio de nombres para agregar dos nuevos puertos al ejemplo CBRApplication.</span><span class="sxs-lookup"><span data-stu-id="5a03b-110">This sample demonstrates using the administrative objects in the **Microsoft.BizTalk.ExplorerOM** namespace to add two new ports to the CBRApplication sample.</span></span> <span data-ttu-id="5a03b-111">Estos nuevos puertos son puertos de ejemplo para CBRApplication.</span><span class="sxs-lookup"><span data-stu-id="5a03b-111">These new ports are example ports for CBRApplication.</span></span> <span data-ttu-id="5a03b-112">Los puertos están configurados para enrutar mensajes a una dirección hipotética de servicios web HTTP mediante el uso del adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="5a03b-112">The ports are configured to route messages to a hypothetical HTTP Web service address by using the HTTP adapter.</span></span> <span data-ttu-id="5a03b-113">En el ejemplo se muestran las siguientes operaciones con los objetos **ExplorerOM** :</span><span class="sxs-lookup"><span data-stu-id="5a03b-113">The sample demonstrates the following operations using the **ExplorerOM** objects:</span></span>  

-   <span data-ttu-id="5a03b-114">Mediante el **AddNewSendPort** método de la **aplicación** clase para agregar un nuevo puerto de envío denominado SendportUSOrders a CBRApplication.</span><span class="sxs-lookup"><span data-stu-id="5a03b-114">Using the **AddNewSendPort** method of the **Application** class to add a new send port called SendportUSOrders to CBRApplication.</span></span> <span data-ttu-id="5a03b-115">El puerto está configurado para usar el adaptador de HTTP para el transporte con una dirección web hipotética.</span><span class="sxs-lookup"><span data-stu-id="5a03b-115">The port is configured to use the HTTP adapter for transport with a hypothetical Web address.</span></span>  

-   <span data-ttu-id="5a03b-116">Agregar un filtro a SendportUSOrders que se suscribe a mensajes de CBRApplication con los Estados Unidos. Valor de código de país de 100.</span><span class="sxs-lookup"><span data-stu-id="5a03b-116">Adding a filter to SendportUSOrders that subscribes to messages in CBRApplication with the U.S. Country Code value of 100.</span></span>  

-   <span data-ttu-id="5a03b-117">Adición de la asignación CBRApplication para transformar los mensajes basados en Estados Unidos a las asignaciones salientes para SendportUSOrders.</span><span class="sxs-lookup"><span data-stu-id="5a03b-117">Adding the CBRApplication map for transforming U.S.-based messages to the outbound maps for SendportUSOrders.</span></span>  

-   <span data-ttu-id="5a03b-118">Adición a CBRApplication de un nuevo puerto de envío denominado SendportCANOrders y configuración de éste para usar el adaptador HTTP para el transporte con una dirección web hipotética.</span><span class="sxs-lookup"><span data-stu-id="5a03b-118">Adding a new send port called SendportCANOrders to CBRApplication and configuring it to use the HTTP adapter for transport with a hypothetical Web address.</span></span>  

-   <span data-ttu-id="5a03b-119">Adición de un filtro a SendportCANOrders que se suscribe a mensajes de CBRApplication con el valor de código de país 200 de Canadá.</span><span class="sxs-lookup"><span data-stu-id="5a03b-119">Adding a filter to SendportCANOrders that subscribes to messages in CBRApplication with the Canada Country Code value of 200.</span></span>  

-   <span data-ttu-id="5a03b-120">Adición de la asignación CBRApplication para transformar los mensajes basados en Canadá a las asignaciones salientes para SendportCANOrders.</span><span class="sxs-lookup"><span data-stu-id="5a03b-120">Adding the CBRApplication map for transforming Canadian-based messages to the outbound maps for SendportCANOrders.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="5a03b-121">Dónde encontrar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a03b-121">Where To Find This Sample</span></span>  
 <span data-ttu-id="5a03b-122">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="5a03b-122">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="5a03b-123">\<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\CBR</span><span class="sxs-lookup"><span data-stu-id="5a03b-123">\<*Samples Path*\>\Admin\ExplorerOM\CBR</span></span>  

 <span data-ttu-id="5a03b-124">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="5a03b-124">The following table shows the files in this sample and describes their purpose.</span></span>  


|           <span data-ttu-id="5a03b-125">Archivos</span><span class="sxs-lookup"><span data-stu-id="5a03b-125">File(s)</span></span>            |                                                 <span data-ttu-id="5a03b-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a03b-126">Description</span></span>                                                  |
|------------------------------|--------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="5a03b-127">ContentBasedRouting.cs</span><span class="sxs-lookup"><span data-stu-id="5a03b-127">ContentBasedRouting.cs</span></span>    | <span data-ttu-id="5a03b-128">Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5a03b-128">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="5a03b-129">CBR.sln, CBR.csproj, CBR.suo</span><span class="sxs-lookup"><span data-stu-id="5a03b-129">CBR.sln, CBR.csproj, CBR.suo</span></span> |                                  <span data-ttu-id="5a03b-130">Archivos de solución y proyecto para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5a03b-130">Solution and project files for the sample.</span></span>                                  |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="5a03b-131">Generación y ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a03b-131">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="5a03b-132">Procedimiento para generar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a03b-132">To build this sample</span></span>  

1. <span data-ttu-id="5a03b-133">Asegúrese de haber completado los pasos para generar, implementar y configurar CBRSample.</span><span class="sxs-lookup"><span data-stu-id="5a03b-133">Make sure you have completed the steps for building, deploying, and configuring the CBRSample.</span></span> <span data-ttu-id="5a03b-134">Estos pasos se proporcionan en [CBRSample (ejemplo de BizTalk Server)](../core/cbrsample-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5a03b-134">Those steps are provided in [CBRSample (BizTalk Server Sample)](../core/cbrsample-biztalk-server-sample.md).</span></span>  

2. <span data-ttu-id="5a03b-135">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución CBR.sln.</span><span class="sxs-lookup"><span data-stu-id="5a03b-135">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file CBR.sln.</span></span>  

3. <span data-ttu-id="5a03b-136">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="5a03b-136">On the **Build** menu, click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="5a03b-137">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a03b-137">To run this sample</span></span>  

1. <span data-ttu-id="5a03b-138">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola y navegue hasta la **CBRApplication** nodo.</span><span class="sxs-lookup"><span data-stu-id="5a03b-138">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and navigate to the **CBRApplication** node.</span></span>  

2. <span data-ttu-id="5a03b-139">Expanda el **CBRApplication** nodo para comprobar que la **puertos de envío** nodo tiene actualmente dos puertos como CBRUSSendPort y CBRCANSendPort.</span><span class="sxs-lookup"><span data-stu-id="5a03b-139">Expand the **CBRApplication** node to verify that the **Send Ports** node currently has only two ports listed as CBRUSSendPort and CBRCANSendPort.</span></span>  

3. <span data-ttu-id="5a03b-140">Abra una ventana de comandos y desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="5a03b-140">Open a command window and navigate to the following folder:</span></span>  

    <span data-ttu-id="5a03b-141">\<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\CBR\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="5a03b-141">\<*Samples Path*\>\Admin\ExplorerOM\CBR\bin\Debug</span></span>  

4. <span data-ttu-id="5a03b-142">Ejecute el archivo CBR.exe.</span><span class="sxs-lookup"><span data-stu-id="5a03b-142">Run the file CBR.exe.</span></span>  

5. <span data-ttu-id="5a03b-143">Presione F5 en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para actualizar la vista bajo el **puertos de envío** nodo.</span><span class="sxs-lookup"><span data-stu-id="5a03b-143">Press F5 in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to refresh the view under the **Send Ports** node.</span></span> <span data-ttu-id="5a03b-144">Ahora debería ver los dos nuevos puertos agregados a CBRApplication mediante este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5a03b-144">You should now see the two new ports added to CBRApplication by this sample.</span></span> <span data-ttu-id="5a03b-145">Se denominan SendportUSOrders y SendportCANOrders.</span><span class="sxs-lookup"><span data-stu-id="5a03b-145">They are called SendportUSOrders and SendportCANOrders.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="5a03b-146">Ejemplo de un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a03b-146">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="5a03b-147">El siguiente script de Windows PowerShell se puede usar para mostrar las mismas características de las clases **ExplorerOM** :</span><span class="sxs-lookup"><span data-stu-id="5a03b-147">The following Windows PowerShell script can be used to demonstrate the same features of the **ExplorerOM** classes.</span></span> <span data-ttu-id="5a03b-148">Sin embargo, dado que el **agregar** método para el **SendPort.OutboundTranforms** colección está marcado como interno en el **ExplorerOM** no se puede llamar directamente desde el ensamblado Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a03b-148">However, because the **Add** method for the **SendPort.OutboundTranforms** collection is marked Internal in the **ExplorerOM** assembly it cannot be called directly from Windows PowerShell.</span></span> <span data-ttu-id="5a03b-149">Este script de Windows PowerShell muestra el uso del proveedor WMI de BizTalk desde Windows PowerShell para agregar la asignación de transformación saliente al nuevo puerto.</span><span class="sxs-lookup"><span data-stu-id="5a03b-149">This Windows PowerShell script demonstrates using the BizTalk WMI Provider from Windows PowerShell to add the outbound transform map to the new port.</span></span>  

```  
Function WMI_AddOutboundTransformToPort($transform,$strPortName)  
{  
    Write-Host "WMI Processing Transform...`r`nPortName `:"$strPortName  
    Write-Host "Transform `:"$transform.AssemblyQualifiedName  

    $WMIsendport = get-wmiobject MSBTS_SendPort -filter "Name=`"$strPortName`"" -namespace root\microsoftbiztalkserver  
    $WMIsendport.OutboundTransforms = $transform.AssemblyQualifiedName  
    [Void] $WMIsendport.Put()  
    [Void] $WMIsendport.Start()  
}  

#===================#  
#=== Main Script ===#  
#===================#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

$CBRApp = $Catalog.Applications["CBRApplication"]  

if ($CBRApp -eq $null)  
{  
    Write-Host "`r`nFailed to find `"CBRApplication`" deployed on this BizTalk server."  
    Write-Host "You must deploy the SDK\Samples\Messaging\CBRSample in order to test this script.`r`n"  
}  
else  
{  
    #=== Register a trap handler for any exceptions ===#  
    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    #===================================#  
    #=== Create the U.S. Orders Port ===#  
    #===================================#  

    $USPort = $CBRApp.AddNewSendPort($false,$false)  
    $USPort.Name = "SendportUSOrders"  
    $USPort.PrimaryTransport.TransportType = $Catalog.ProtocolTypes["HTTP"]  
    $USPort.PrimaryTransport.Address = "http://process_orders_US.asp"  
    $USPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"]  

    #=== add the filter to subscribe to messages with U.S country code 100 ===#  

    $USPort.Filter = "<Filter><Group>" +  
                     "<Statement Property='BTS.ReceivePortName' Operator='0' Value='ReceivePortPO'/>" +   
                     "<Statement Property='CBRSample.CountryCode' Operator='0' Value='100'/>" +  
                     "</Group></Filter>"  

    Write-Host("`r`nAdding " + $UsPort.Name + " to catalog ...")  
    $Catalog.SaveChanges()  

    #=========================================================================================#  
    #=== SendPortTranformCollection::Add is marked internal in ExplorerOM for some reason. ===#  
    #=== Use WMI to set this as a workaround through PowerShell.                           ===#  
    #=========================================================================================#  

    WMI_AddOutboundTransformToPort $Catalog.Transforms["CBRSample.CBRInput2USMap"] $USport.Name  

    #=====================================#  
    #=== Create the Canada Orders Port ===#  
    #=====================================#  

    $CanadaPort = $CBRApp.AddNewSendPort($false,$false)  
    $CanadaPort.Name = "SendportCANOrders"  
    $CanadaPort.PrimaryTransport.TransportType = $Catalog.ProtocolTypes["HTTP"]  
    $CanadaPort.PrimaryTransport.Address = "http://process_orders_CAN.asp"  
    $CanadaPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"]  

    #=== add the filter to subscribe to messages with U.S country code 100 ===#  

    $CanadaPort.Filter = "<Filter><Group>" +  
                     "<Statement Property='BTS.ReceivePortName' Operator='0' Value='ReceivePortPO'/>" +   
                     "<Statement Property='CBRSample.CountryCode' Operator='0' Value='200'/>" +  
                     "</Group></Filter>"  

    Write-Host("`r`nAdding " + $UsPort.Name + " to catalog ...")  
    $Catalog.SaveChanges()  

    #=========================================================================================#  
    #=== SendPortTranformCollection::Add is marked internal in ExplorerOM for some reason. ===#  
    #=== Use WMI to set this as a workaround through PowerShell.                           ===#  
    #=========================================================================================#  

    WMI_AddOutboundTransformToPort $Catalog.Transforms["CBRSample.CBRInput2CANMap"] $CanadaPort.Name  

    Write-Host  
}  
```  

 <span data-ttu-id="5a03b-150">Éste es un ejemplo de los resultados de la ejecución del script de Windows PowerShell para crear los dos nuevos puertos.</span><span class="sxs-lookup"><span data-stu-id="5a03b-150">Here is an example output from running the Windows PowerShell script to create the two new ports.</span></span> <span data-ttu-id="5a03b-151">Los nuevos puertos también se pueden comprobar en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tal como se menciona arriba.</span><span class="sxs-lookup"><span data-stu-id="5a03b-151">The new ports can also be verified in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console as mentioned above.</span></span>  

```  
PS C:\> .\CBR.ps1  

Adding SendportUSOrders to catalog ...  
WMI Processing Transform...  
PortName : SendportUSOrders  
Transform : CBRSample.CBRInput2USMap,CBRSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ba2e1651515c6db7  

Adding SendportUSOrders to catalog ...  
WMI Processing Transform...  
PortName : SendportCANOrders  
Transform : CBRSample.CBRInput2CANMap,CBRSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ba2e1651515c6db7  

```  

## <a name="see-also"></a><span data-ttu-id="5a03b-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a03b-152">See Also</span></span>  
 <span data-ttu-id="5a03b-153">[Admin\explorerom (carpeta de ejemplos de BizTalk Server)](../core/admin-explorerom-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="5a03b-153">[Admin-ExplorerOM (BizTalk Server Samples Folder)](../core/admin-explorerom-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="5a03b-154">CBRSample (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="5a03b-154">CBRSample (BizTalk Server Sample)</span></span>](../core/cbrsample-biztalk-server-sample.md)