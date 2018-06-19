---
title: CBR (ejemplo de BizTalk Server) | Documentos de Microsoft
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
ms.openlocfilehash: 30811b4f0dba463d518bdd9cd8f6d227e0e79aac
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967474"
---
# <a name="cbr-biztalk-server-sample"></a>CBR (ejemplo de BizTalk Server)
El ejemplo CBR se muestra el uso del **ExplorerOM** objetos de administración para agregar y configurar nuevos puertos de envío para enrutamiento por contenidos de mensajes de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Este ejemplo es necesario haber implementado CBRSample mediante la ejecución de setup.bat ubicado en el \< *ruta de ejemplos*\>\Messaging\CBRSample directory.  
  
-   Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.  
  
-   El ejemplo del script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts. Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra cómo utilizar los objetos de administración en el **Microsoft.BizTalk.ExplorerOM** espacio de nombres para agregar dos nuevos puertos al ejemplo CBRApplication. Estos nuevos puertos son puertos de ejemplo para CBRApplication. Los puertos están configurados para enrutar mensajes a una dirección hipotética de servicios web HTTP mediante el uso del adaptador de HTTP. En el ejemplo se muestran las siguientes operaciones con los objetos **ExplorerOM** :  
  
-   Mediante el **AddNewSendPort** método de la **aplicación** clase para agregar un nuevo puerto de envío denominado SendportUSOrders a CBRApplication. El puerto está configurado para usar el adaptador de HTTP para el transporte con una dirección web hipotética.  
  
-   Agregar un filtro a SendportUSOrders que se suscribe a mensajes de CBRApplication con los Estados Unidos Valor de código de país de 100.  
  
-   Adición de la asignación CBRApplication para transformar los mensajes basados en Estados Unidos a las asignaciones salientes para SendportUSOrders.  
  
-   Adición a CBRApplication de un nuevo puerto de envío denominado SendportCANOrders y configuración de éste para usar el adaptador HTTP para el transporte con una dirección web hipotética.  
  
-   Adición de un filtro a SendportCANOrders que se suscribe a mensajes de CBRApplication con el valor de código de país 200 de Canadá.  
  
-   Adición de la asignación CBRApplication para transformar los mensajes basados en Canadá a las asignaciones salientes para SendportCANOrders.  
  
## <a name="where-to-find-this-sample"></a>Dónde encontrar este ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  
  
 \<*Ejemplos de ruta de acceso*\>\Admin\ExplorerOM\CBR  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|ContentBasedRouting.cs|Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo.|  
|CBR.sln, CBR.csproj, CBR.suo|Archivos de solución y proyecto para el ejemplo.|  
  
## <a name="building-and-running-this-sample"></a>Generación y ejecución del ejemplo  
  
#### <a name="to-build-this-sample"></a>Procedimiento para generar este ejemplo  
  
1.  Asegúrese de haber completado los pasos para generar, implementar y configurar CBRSample. Estos pasos se proporcionan en [CBRSample (ejemplo de BizTalk Server)](../core/cbrsample-biztalk-server-sample.md).  
  
2.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución CBR.sln.  
  
3.  En el menú **Compilar** , haga clic en **Compilar solución**.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola del sistema y desplácese a la **CBRApplication** nodo.  
  
2.  Expanda el **CBRApplication** nodo para comprobar que la **puertos de envío** nodo actualmente tiene solo dos puertos como CBRUSSendPort y CBRCANSendPort.  
  
3.  Abra una ventana de comandos y desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\Admin\ExplorerOM\CBR\bin\Debug  
  
4.  Ejecute el archivo CBR.exe.  
  
5.  Presione F5 en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para actualizar la vista bajo la **puertos de envío** nodo. Ahora debería ver los dos nuevos puertos agregados a CBRApplication mediante este ejemplo. Se denominan SendportUSOrders y SendportCANOrders.  
  
## <a name="windows-powershell-script-example"></a>Ejemplo de un script de Windows PowerShell  
 El siguiente script de Windows PowerShell se puede usar para mostrar las mismas características de las clases **ExplorerOM** : Sin embargo, dado que la **agregar** método para el **SendPort.OutboundTranforms** colección está marcado como interno en el **ExplorerOM** ensamblado no se puede llamar directamente desde Windows PowerShell. Este script de Windows PowerShell muestra el uso del proveedor WMI de BizTalk desde Windows PowerShell para agregar la asignación de transformación saliente al nuevo puerto.  
  
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
  
 Éste es un ejemplo de los resultados de la ejecución del script de Windows PowerShell para crear los dos nuevos puertos. Los nuevos puertos también se pueden comprobar en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tal como se menciona arriba.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Administración-ExplorerOM (carpeta de ejemplos de BizTalk Server)](../core/admin-explorerom-biztalk-server-samples-folder.md)   
 [CBRSample (ejemplo de BizTalk Server)](../core/cbrsample-biztalk-server-sample.md)