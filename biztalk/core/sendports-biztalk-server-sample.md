---
title: "PuertosEnvío (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b84f96a2-b749-4fe0-be15-e4dd13eff66f
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f6bc29589f0546dda3841221fcce3ab91d704ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sendports-biztalk-server-sample"></a>SendPorts (ejemplo de BizTalk Server)
El ejemplo SendPorts muestra cómo enumerar y administrar puertos de envío mediante el **Microsoft.BizTalk.ExplorerOM** las clases de administración.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.  
  
-   El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts. Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra cómo utilizar el **BtsCatalogExplorer** y **puertoEnvío** clases a partir de la **Microsoft.BizTalk.ExplorerOM** espacio de nombres para administrar los puertos de envío en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. El ejemplo está escrito en Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]. En este tema también se incluye un script de ejemplo de Windows PowerShell. El ejemplo muestra las siguientes operaciones:  
  
1.  Conectarse a la base de datos de administración de BizTalk mediante el **BtsCatalogExplorer** clase.  
  
2.  Crear dos nuevos puertos de envío denominados myStaticOnewaySendPort1 y myDynamicTwowaySendPort1. myStaticOnewaySendPort1, como su nombre implica, es un puerto de envío unidireccional estático.  Se crea para utilizar el transporte HTTP con un ejemplo destino URL http://sample1. myDynamicTwowaySendPort1 se crea como un puerto de envío bidireccional dinámico.  
  
3.  Enumeración de los puertos de envío en un entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esta enumeración de ejemplo debe incluir los dos puertos de envío nuevos.  
  
4.  Eliminación de los dos puertos de envío nuevos.  
  
5.  Configuración de los puertos de envío nuevos. Las configuraciones que se muestran en el ejemplo se aplican al puerto de envío de ejemplo denominado myStaticOnewaySendPort1. Las configuraciones que se aplican en el ejemplo incluyen las siguientes:  
  
    -   Habilitar la **mensaje de solicitud antes de procesamiento de puerto** opción para realizar el seguimiento de cuerpos de mensaje.  
  
    -   Habilitar la **mensaje de solicitud después del procesamiento de puerto** opción para realizar el seguimiento de cuerpos de mensaje.  
  
    -   Especificación de un certificado de cifrado del puerto de envío para usarlo en los mensajes salientes.  
  
    -   Especificación de un filtro para dar de alta a un conjunto de mensajes.  
  
    -   Adición de una asignación para transformar los mensajes.  
  
6.  Cambio del estado del puerto de envío en los dos puertos de envío nuevos.  La ejecución del ejemplo realizará los siguientes cambios de estado en myStaticOnewaySendPort1:  
  
    -   Cambio del estado a iniciado.  
  
    -   Cambio del estado a detenido.  
  
    -   Cambio del estado a enlazado. El estado enlazado es el mismo que dado de baja.  
  
## <a name="where-to-find-this-sample"></a>Dónde encontrar este ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  
  
 \<*Ejemplos de ruta de acceso*> \Admin\ExplorerOM\SendPorts  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|SendPorts.cs|Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo.|  
|SendPorts.sln, SendPorts.csproj, SendPorts.suo|Archivos de solución y proyecto para el ejemplo.|  
  
## <a name="building-and-running-this-sample"></a>Generación y ejecución del ejemplo  
  
#### <a name="to-build-this-sample"></a>Procedimiento para generar este ejemplo  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución SendPorts.sln.  
  
2.  En el menú principal, haga clic en **generar**y, a continuación, haga clic en **generar solución**.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra una ventana de comandos y desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \Admin\ExplorerOM\SendPorts\bin\Debug  
  
2.  Ejecute el archivo SendPorts.exe.  
  
## <a name="windows-powershell-script-example"></a>Ejemplo de un script de Windows PowerShell  
 El siguiente fragmento de script de Windows PowerShell puede usarse para mostrar las mismas características de la **ExplorerOM** clases:  
  
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
  
 A continuación se indica el resultado esperado del ejemplo tras la ejecución del ejemplo de script de Windows PowerShell.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Administración-ExplorerOM (carpeta de ejemplos de BizTalk Server)](../core/admin-explorerom-biztalk-server-samples-folder.md)