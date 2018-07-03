---
title: SendPorts (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b84f96a2-b749-4fe0-be15-e4dd13eff66f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac6ef809104e1ce11385cb88d94547d0de496af1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009909"
---
# <a name="sendports-biztalk-server-sample"></a><span data-ttu-id="957ae-102">SendPorts (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="957ae-102">SendPorts (BizTalk Server Sample)</span></span>
<span data-ttu-id="957ae-103">El ejemplo SendPorts muestra cómo enumerar y administrar puertos de envío mediante el **Microsoft.BizTalk.ExplorerOM** las clases de administración.</span><span class="sxs-lookup"><span data-stu-id="957ae-103">The SendPorts sample demonstrates how to enumerate and manage send ports by using the **Microsoft.BizTalk.ExplorerOM** administration classes.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="957ae-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="957ae-104">Prerequisites</span></span>  

- <span data-ttu-id="957ae-105">Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="957ae-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="957ae-106">El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts.</span><span class="sxs-lookup"><span data-stu-id="957ae-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="957ae-107">Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).</span><span class="sxs-lookup"><span data-stu-id="957ae-107">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="957ae-108">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="957ae-108">What This Sample Does</span></span>  
 <span data-ttu-id="957ae-109">Este ejemplo muestra cómo utilizar el **BtsCatalogExplorer** y **puertoEnvío** clases a partir de la **Microsoft.BizTalk.ExplorerOM** espacio de nombres para administrar los puertos de envío en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="957ae-109">This sample demonstrates using the **BtsCatalogExplorer** and **SendPort** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to manage send ports in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="957ae-110">El ejemplo está escrito en Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="957ae-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="957ae-111">En este tema también se incluye un script de ejemplo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="957ae-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="957ae-112">El ejemplo muestra las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="957ae-112">The sample demonstrates the following operations:</span></span>  

1. <span data-ttu-id="957ae-113">Conectarse a la base de datos de administración de BizTalk mediante el **BtsCatalogExplorer** clase.</span><span class="sxs-lookup"><span data-stu-id="957ae-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  

2. <span data-ttu-id="957ae-114">Crear dos nuevos puertos de envío denominado myStaticOnewaySendPort1 y myDynamicTwowaySendPort1.</span><span class="sxs-lookup"><span data-stu-id="957ae-114">Creating two new send ports named myStaticOnewaySendPort1 and myDynamicTwowaySendPort1.</span></span> <span data-ttu-id="957ae-115">myStaticOnewaySendPort1, como su nombre implica, es un puerto de envío unidireccional estático.</span><span class="sxs-lookup"><span data-stu-id="957ae-115">myStaticOnewaySendPort1, as its name implies, is a static one-way send port.</span></span>  <span data-ttu-id="957ae-116">Se crea para utilizar el transporte HTTP con una dirección URL de destino de ejemplo http://sample1.</span><span class="sxs-lookup"><span data-stu-id="957ae-116">It is created to use the HTTP transport with an example destination URL http://sample1.</span></span> <span data-ttu-id="957ae-117">myDynamicTwowaySendPort1 se crea como un puerto de envío bidireccional dinámico.</span><span class="sxs-lookup"><span data-stu-id="957ae-117">myDynamicTwowaySendPort1 is created as a dynamic two-way send port.</span></span>  

3. <span data-ttu-id="957ae-118">Enumeración de los puertos de envío en un entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="957ae-118">Enumerating send ports in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="957ae-119">Esta enumeración de ejemplo debe incluir los dos puertos de envío nuevos.</span><span class="sxs-lookup"><span data-stu-id="957ae-119">This example enumeration should include the two new send ports.</span></span>  

4. <span data-ttu-id="957ae-120">Eliminación de los dos puertos de envío nuevos.</span><span class="sxs-lookup"><span data-stu-id="957ae-120">Deleting the two new send ports.</span></span>  

5. <span data-ttu-id="957ae-121">Configuración de los puertos de envío nuevos.</span><span class="sxs-lookup"><span data-stu-id="957ae-121">Configuring the new send ports.</span></span> <span data-ttu-id="957ae-122">Las configuraciones que se muestran en el ejemplo se aplican al puerto de envío de ejemplo denominado myStaticOnewaySendPort1.</span><span class="sxs-lookup"><span data-stu-id="957ae-122">The configurations demonstrated by the sample are applied to the example send port named myStaticOnewaySendPort1.</span></span> <span data-ttu-id="957ae-123">Las configuraciones que se aplican en el ejemplo incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="957ae-123">The configurations applied by the sample include the following:</span></span>  

   -   <span data-ttu-id="957ae-124">Habilitar la **mensaje de solicitud antes del procesamiento de puerto** opción para realizar el seguimiento de cuerpos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="957ae-124">Enabling the **Request message before port processing** option for tracking message bodies.</span></span>  

   -   <span data-ttu-id="957ae-125">Habilitar la **mensaje de solicitud después del procesamiento de puerto** opción para realizar el seguimiento de cuerpos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="957ae-125">Enabling the **Request message after port processing** option for tracking message bodies.</span></span>  

   -   <span data-ttu-id="957ae-126">Especificación de un certificado de cifrado del puerto de envío para usarlo en los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="957ae-126">Specifying an encryption certificate for the send port to use on outgoing messages.</span></span>  

   -   <span data-ttu-id="957ae-127">Especificación de un filtro para dar de alta a un conjunto de mensajes.</span><span class="sxs-lookup"><span data-stu-id="957ae-127">Specifying a filter for enlistment against a set of messages.</span></span>  

   -   <span data-ttu-id="957ae-128">Adición de una asignación para transformar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="957ae-128">Adding a map to transform the messages.</span></span>  

6. <span data-ttu-id="957ae-129">Cambio del estado del puerto de envío en los dos puertos de envío nuevos.</span><span class="sxs-lookup"><span data-stu-id="957ae-129">Changing send port status on the two new send ports.</span></span>  <span data-ttu-id="957ae-130">La ejecución del ejemplo realizará los siguientes cambios de estado en myStaticOnewaySendPort1:</span><span class="sxs-lookup"><span data-stu-id="957ae-130">The execution of the sample will make the following status changes on the myStaticOnewaySendPort1:</span></span>  

   -   <span data-ttu-id="957ae-131">Cambio del estado a iniciado.</span><span class="sxs-lookup"><span data-stu-id="957ae-131">Change the status to started.</span></span>  

   -   <span data-ttu-id="957ae-132">Cambio del estado a detenido.</span><span class="sxs-lookup"><span data-stu-id="957ae-132">Change the status to stopped.</span></span>  

   -   <span data-ttu-id="957ae-133">Cambio del estado a enlazado.</span><span class="sxs-lookup"><span data-stu-id="957ae-133">Change the status to bound.</span></span> <span data-ttu-id="957ae-134">El estado enlazado es el mismo que dado de baja.</span><span class="sxs-lookup"><span data-stu-id="957ae-134">The bound status is the same as unenlisted.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="957ae-135">Dónde encontrar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="957ae-135">Where To Find This Sample</span></span>  
 <span data-ttu-id="957ae-136">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="957ae-136">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="957ae-137">\<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\SendPorts</span><span class="sxs-lookup"><span data-stu-id="957ae-137">\<*Samples Path*\>\Admin\ExplorerOM\SendPorts</span></span>  

 <span data-ttu-id="957ae-138">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="957ae-138">The following table shows the files in this sample and describes their purpose.</span></span>  


|                    <span data-ttu-id="957ae-139">Archivos</span><span class="sxs-lookup"><span data-stu-id="957ae-139">File(s)</span></span>                     |                                                 <span data-ttu-id="957ae-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="957ae-140">Description</span></span>                                                  |
|------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                  <span data-ttu-id="957ae-141">SendPorts.cs</span><span class="sxs-lookup"><span data-stu-id="957ae-141">SendPorts.cs</span></span>                  | <span data-ttu-id="957ae-142">Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="957ae-142">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="957ae-143">SendPorts.sln, SendPorts.csproj, SendPorts.suo</span><span class="sxs-lookup"><span data-stu-id="957ae-143">SendPorts.sln, SendPorts.csproj, SendPorts.suo</span></span> |                                  <span data-ttu-id="957ae-144">Archivos de solución y proyecto para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="957ae-144">Solution and project files for the sample.</span></span>                                  |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="957ae-145">Generación y ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="957ae-145">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="957ae-146">Procedimiento para generar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="957ae-146">To build this sample</span></span>  

1. <span data-ttu-id="957ae-147">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución SendPorts.sln.</span><span class="sxs-lookup"><span data-stu-id="957ae-147">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendPorts.sln.</span></span>  

2. <span data-ttu-id="957ae-148">En el menú principal, haga clic en **compilar**y, a continuación, haga clic en **compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="957ae-148">On the main menu, click **Build**, and then click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="957ae-149">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="957ae-149">To run this sample</span></span>  

1.  <span data-ttu-id="957ae-150">Abra una ventana de comandos y desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="957ae-150">Open a command window and navigate to the following folder:</span></span>  

     <span data-ttu-id="957ae-151">\<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\SendPorts\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="957ae-151">\<*Samples Path*\>\Admin\ExplorerOM\SendPorts\bin\Debug</span></span>  

2.  <span data-ttu-id="957ae-152">Ejecute el archivo SendPorts.exe.</span><span class="sxs-lookup"><span data-stu-id="957ae-152">Run the file SendPorts.exe.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="957ae-153">Ejemplo de un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="957ae-153">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="957ae-154">El siguiente fragmento de script de Windows PowerShell se puede usar para mostrar las mismas características de la **ExplorerOM** clases:</span><span class="sxs-lookup"><span data-stu-id="957ae-154">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  

```  
Function CreateSendPorts($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  

    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    #=== create a new static one-way send port using HTTP transport ===#  

    $myStaticOnewaySendPort = $Catalog.AddNewSendPort($false,$false)  
    $myStaticOnewaySendPort.Name = "myStaticOnewaySendPort1"  
    $myStaticOnewaySendPort.PrimaryTransport.TransportType = $catalog.ProtocolTypes["HTTP"]  
    $myStaticOnewaySendPort.PrimaryTransport.Address = "http://sample1"  
    $myStaticOnewaySendPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"]  

    #=== create a new dynamic two-way send port ===#  

    $myDynamicTwowaySendPort = $catalog.AddNewSendPort($true,$true)  
    $myDynamicTwowaySendPort.Name = "myDynamicTwowaySendPort1";  
    $myDynamicTwowaySendPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"];  
    $myDynamicTwowaySendPort.ReceivePipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLReceive"];  

    #=== Persist new ports to BizTalk configuration database ===#  

    Write-Host Adding $myStaticOnewaySendPort.Name...  
    Write-Host Adding $myDynamicTwowaySendPort.Name...  
    $catalog.SaveChanges();  
    Write-Host "`r`nCreateSendPorts() completed."  
}  

Function DeleteSendPorts($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  

    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    #=== Delete this sample's new send ports by name ===#  

    $Catalog.RemoveSendPort($Catalog.SendPorts["myStaticOnewaySendPort1"])  
    $Catalog.RemoveSendPort($Catalog.SendPorts["myDynamicTwowaySendPort1"])  

    #=== Persist changes to BizTalk configuration database ===#  

    $catalog.SaveChanges();  
    Write-Host "DeleteSendPorts() completed."  
}  

Function EnumerateSendPorts($Catalog)  
{  
    #=== Display all send ports and their status info ===#  

    $catalog.SendPorts | format-table -Property Name, Status -autosize  

    Write-Host "EnumerateSendPorts`(`) completed."  
}  

Function ConfigureSendPort($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  

    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    $sendport = $catalog.SendPorts["myStaticOnewaySendPort1"];  

    #=== specify tracking settings for tracking ===#  

    Write-Host $sendport.Name: Enabling BeforeSendPipeline and AfterSendPipeline message body tracking.  
    $sendport.Tracking = ([Microsoft.BizTalk.ExplorerOM.TrackingTypes] "BeforeSendPipeline" -bor   
                         [Microsoft.BizTalk.ExplorerOM.TrackingTypes] "AfterSendPipeline")  

    #=== specify an encryption certificate for outgoing messages ===#  

    Write-Host $sendport.Name: Adding a encryption certificate  
    foreach ($certificate in $catalog.Certificates)  
    {  
        if ($certificate.UsageType -eq [Microsoft.BizTalk.ExplorerOM.CertUsageType] "Encryption")  
        {  
            $sendport.EncryptionCert = $certificate  
        }  
    }  

    #=== specify filters for content-based routing ===#  
    Write-Host $sendport.Name: Adding a filter  
    $sendport.Filter = "<Filter><Group>" +  
                       "<Statement Property='SMTP.Subject' Operator='0' Value='Purchase Order'/>" +  
                       "<Statement Property='SMTP.From' Operator='0' Value='Customer'/>" +  
                       "</Group></Filter>"  

    #=== specify transform maps for document normalization ===#  

    foreach ($transform in $catalog.Transforms)  
    {  
        if (($transform.SourceSchema.FullName -ieq "myPO") -and (transform.TargetSchema.FullName -ieq "partnerPO"))  
        {  
            Write-Host $sendport.Name: Adding a transform  
            $sendport.OutboundTransforms.Add($transform)  
        }  
    }  

    #=== Persist all changes to BizTalk configuration database ===#  

    Write-Host $sendport.Name: Saving changes  
    $catalog.SaveChanges();  
    Write-Host "`r`nConfigureSendPort() completed."  
}  

Function ChangeSendPortStatus($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  

    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    $sendport = $catalog.SendPorts["myStaticOnewaySendPort1"];  

    #=== start the send port to begin processing messages ===#  

    $sendport.Status = [Microsoft.BizTalk.ExplorerOM.PortStatus] "Started"  
    Write-Host Changing ($sendport.Name) status to ($sendport.Status)...  
    $catalog.SaveChanges();  
    Write-Host Complete.  

    #=== stop the send port to stop processing and suspend messages ===#  

    $sendport.Status = [Microsoft.BizTalk.ExplorerOM.PortStatus] "Stopped"  
    Write-Host Changing ($sendport.Name) status to ($sendport.Status)...  
    $catalog.SaveChanges();  
    Write-Host Complete.  

    #=== unenlist the send port to stop processing and discard messages ===#  

    $sendport.Status = [Microsoft.BizTalk.ExplorerOM.PortStatus] "Bound"  
    Write-Host Changing ($sendport.Name) status to ($sendport.Status)`(Unenlisted`)...  
    $catalog.SaveChanges();  
    Write-Host Complete.  
}  

#=== Main Script Body ===#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

#=== Exercise the CreateSendPorts function to create the two new ports ===#  

Write-Host "`r`n========================="  
Write-Host "=== CreateSendPorts`(`) ==="  
Write-Host "=========================`r`n"  
CreateSendPorts $Catalog  

#=== Enumerate all send ports to view the two new ports ===#  

Write-Host "`r`n============================"  
Write-Host "=== EnumerateSendPorts`(`) ==="  
Write-Host "============================`r`n"  
EnumerateSendPorts $Catalog  

#=== Add some configuration to the static send port ===#  

Write-Host "`r`n==========================="  
Write-Host "=== ConfigureSendPort`(`) ==="  
Write-Host "===========================`r`n"  
ConfigureSendPort $Catalog  

#=== Cycle through some status changes on the static send port ===#  

Write-Host "`r`n=============================="  
Write-Host "=== ChangeSendPortStatus`(`) ==="  
Write-Host "==============================`r`n"  
ChangeSendPortStatus $Catalog  

#=== Delete the two new ports ===#  

Write-Host "`r`n========================="  
Write-Host "=== DeleteSendPorts`(`) ==="  
Write-Host "=========================`r`n"  
DeleteSendPorts $Catalog  

Write-Host  
```  

 <span data-ttu-id="957ae-155">A continuación se indica el resultado esperado del ejemplo tras la ejecución del ejemplo de script de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="957ae-155">Here is example expected output from running the Windows PowerShell script sample.</span></span>  

```  
PS C:\> & 'C:\SendPorts.ps1'  

=========================  
=== CreateSendPorts() ===  
=========================  

Adding myStaticOnewaySendPort1 ...  
Adding myDynamicTwowaySendPort1 ...  

CreateSendPorts() completed.  

============================  
=== EnumerateSendPorts() ===  
============================  

Name                      Status  
----                      ------  
ResendPort               Started  
HelloWorldSendPort       Started  
ToCustomerSendPort       Started  
CBRUSSendPort            Started  
CBRCANSendPort           Started  
SendportCANOrders          Bound  
myStaticOnewaySendPort1    Bound  
myDynamicTwowaySendPort1   Bound  

EnumerateSendPorts() completed.  

===========================  
=== ConfigureSendPort() ===  
===========================  

myStaticOnewaySendPort1 : Enabling BeforeSendPipeline and AfterSendPipeline message body tracking.  
myStaticOnewaySendPort1 : Adding a encryption certificate  
myStaticOnewaySendPort1 : Adding a filter  
myStaticOnewaySendPort1 : Saving changes  

ConfigureSendPort() completed.  

==============================  
=== ChangeSendPortStatus() ===  
==============================  

Changing myStaticOnewaySendPort1 status to Started ...  
Complete.  
Changing myStaticOnewaySendPort1 status to Stopped ...  
Complete.  
Changing myStaticOnewaySendPort1 status to Bound (Unenlisted)...  
Complete.  

=========================  
=== DeleteSendPorts() ===  
=========================  

DeleteSendPorts() completed.  
```  

## <a name="see-also"></a><span data-ttu-id="957ae-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="957ae-156">See Also</span></span>  
 [<span data-ttu-id="957ae-157">Admin\ExplorerOM (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="957ae-157">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)