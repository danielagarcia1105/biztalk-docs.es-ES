---
title: BrowsingArtifacts (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b63c0833-3445-4361-a8eb-63837017edf8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce76916af78a0bf7918f7e081752811d05758935
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997213"
---
# <a name="browsingartifacts-biztalk-server-sample"></a>BrowsingArtifacts (ejemplo de BizTalk Server)
En el ejemplo BrowsingArtifacts se muestra cómo enumerar los artefactos y atributos de BizTalk.  

## <a name="prerequisites"></a>Requisitos previos  

- Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.  

- El ejemplo del script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts. Para obtener más información, consulte: [examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).  

## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra cómo utilizar el **BtsCatalogExplorer** clase desde el **Microsoft.BizTalk.ExplorerOM** espacio de nombres para enumerar los artefactos y notificar sus atributos. Los siguientes artefactos se incluyen en el informe generado por este ejemplo: orquestaciones, puertos, ensamblados, entidades y transformaciones. El ejemplo está escrito en Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]. Un script de ejemplo de Windows PowerShell también se proporciona en este tema.  

## <a name="where-to-find-this-sample"></a>Dónde encontrar este ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  

 \<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\BrowsingArtifacts  

 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  


|                                Archivos                                 |                                                 Descripción                                                  |
|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                          BrowsingArtifacts.cs                          | Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo. |
| BrowsingArtifacts.sln, BrowsingArtifacts.csproj, BrowsingArtifacts.suo |                                  Archivos de solución y proyecto para el ejemplo.                                  |

## <a name="building-and-running-this-sample"></a>Generación y ejecución del ejemplo  

#### <a name="to-build-this-sample"></a>Procedimiento para generar este ejemplo  

1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución BrowsingArtifacts.sln.  

2. En el menú **Compilar** , haga clic en **Compilar solución**.  

#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  

1.  Abra una ventana de comandos y desplácese a la siguiente carpeta:  

     \<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\BrowsingArtifacts\bin\Debug  

2.  Ejecute el archivo BrowsingArtifacts.exe.  

## <a name="windows-powershell-script-example"></a>Ejemplo de un script de Windows PowerShell  
 El siguiente script de Windows PowerShell puede usarse para mostrar las mismas características de la **ExplorerOM** clases:  

```  
Function EnumOrchestrations($catalog)  
{  
    Write-Host `r`n======================  
    Write-Host ===  ORCHESTRATIONS  ===  
    Write-Host ======================`r`n   

    #=== Enumerating the assemblies and pulling orchestration information ===#  

    foreach($assembly in $catalog.Assemblies)  
    {  
        foreach($orch in $assembly.Orchestrations)  
        {  
            #=== We can’t report the host if it is not hosted or enlisted ===#  
            if ($orch.Status -ieq "Unenlisted")  
            {  
                Write-Host Name : $orch.Fullname`r`nHost : N/A`r`nStatus : $orch.Status  
            }  
            else  
            {  
                Write-Host Name : $orch.Fullname`r`nHost : $orch.Host.Name`r`nStatus : $orch.Status  
            }  

            #=== Reporting port types and operations ===#  
            foreach($port in $orch.Ports)  
            {  
                Write-Host "`tPort:"$port.PortType.FullName  

                foreach($portop in $port.PortType.Operations)  
                {  
                    Write-Host "`t`tOperation:"$portop.Name  
                }  
            }  

            #=== Reporting Used roles ===#  
            foreach($role in $orch.UsedRoles)  
            {  
                Write-Host "`tRole:"$role.Name"`("$role.ServiceLinkType"`)"  

                foreach($EnlistedParty in $role.EnlistedParties)  
                {  
                    Write-Host "`t`tParty:"$Enlistedparty.Party.Name  
                }  
            }  

            #=== Reporting implemented roles ===#  
            foreach($role in $orch.ImplementedRoles)  
            {  
                Write-Host "`tRole:"$role.Name"`("$role.ServiceLinkType"`)"  
            }  

            Write-Host  
        }  
    }  
}  

Function EnumOtherArtifacts($catalog)  
{  
    Write-Host `r`n======================  
    Write-Host "===   ASSEMBLIES   ==="  
    Write-Host ======================`r`n   

    foreach($assembly in $catalog.Assemblies)  
    {  
        Write-Host $assembly.Name  
    }  

    Write-Host `r`n======================  
    Write-Host "===     HOSTS      ==="  
    Write-Host ======================`r`n   

    foreach($btshost in $catalog.Hosts)  
    {  
        Write-Host $btshost.Name"`($($btshost.Type)`)"  
    }  

    Write-Host `r`n======================  
    Write-Host "===    PARTIES     ==="  
    Write-Host ======================`r`n   

    foreach($party in $catalog.Parties)  
    {  
        Write-Host $party.Name  

        foreach($sendport in $party.SendPorts)  
        {  
            Write-Host "`tSendPort:"$sendport.Name  
        }  

        foreach($alias in $party.Aliases)  
        {  
            Write-Host "`tAlias:"$alias.Name":"$alias.Qualifier"="$alias.Value  
        }  
    }  

    Write-Host `r`n======================  
    Write-Host "===   TRANSFORMS   ==="  
    Write-Host ======================`r`n   

    foreach($transform in $catalog.Transforms)  
    {  
        Write-Host $transform.FullName":`r`n`t"$transform.SourceSchema.Fullname"==>"$transform.TargetSchema.Fullname`r`n  
    }  
}  

#=== Main Script Body ===#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

#=== All reporting is performed in the following two functions ===#  

EnumOrchestrations $Catalog  
EnumOtherArtifacts $Catalog  
```  

 A continuación se incluye un ejemplo de la ejecución del script de Windows PowerShell junto con el resultado correspondiente:  

```  
PS C:\> .\BrowsingArtifacts.ps1  

======================  
=== ORCHESTRATIONS ===  
======================  

Name : Microsoft.BizTalk.Edi.BatchSuspendOrchestration.BatchElementSuspendService  
Host : BizTalkServerApplication  
Status : Enlisted  

Name : Microsoft.BizTalk.Edi.BatchingOrchestration.BatchingService  
Host : BizTalkServerApplication  
Status : Enlisted  

Name : Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService  
Host : BizTalkServerApplication  
Status : Enlisted  

Name : EAIOrchestrations.EAIProcess  
Host : N/A  
Status : Unenlisted  
        Port: EAIOrchestrations.ReceiveReqType  
                Operation: Operation_1  
        Port: EAIOrchestrations.SendDeclineType  
                Operation: Operation_1  
        Port: EAIOrchestrations.SendToERPType  
                Operation: Operation_1  

Name : B2BOrchestrations.B2BProcess  
Host : BizTalkServerApplication  
Status : Started  
        Port: B2BOrchestrations.ReceivePO_Type  
                Operation: Operation_1  
        Port: B2BOrchestrations.SendPOConfirmed_Type  
                Operation: Operation_1  
        Port: B2BSchemas.localhost.Process_.Process  
                Operation: ReceivePO  
        Port: B2BOrchestrations.ReceiveASN_Type  
                Operation: Operation_1  
        Port: B2BOrchestrations.ReceiveInvoice_Type  
                Operation: Operation_1  
        Port: B2BOrchestrations.PortType_PaymentVoucherArchive  
                Operation: Operation_1  
        Port: B2BSchemas.localhost1.Payment_Service_.Payment_Service  
                Operation: ProcessPayment  
        Port: B2BOrchestrations.SendPaymentAck_Type  
                Operation: Operation_1  

======================  
===   ASSEMBLIES   ===  
======================  

Microsoft.BizTalk.GlobalPropertySchemas  
Microsoft.BizTalk.DefaultPipelines  
Microsoft.BizTalk.Adapter.MSMQ.MsmqAdapterProperties  
MQSeries  
Microsoft.BizTalk.Hws.HwsPromotedProperties  
Microsoft.BizTalk.Hws.HwsSchemas  
Microsoft.BizTalk.KwTpm.StsDefaultPipelines  
Microsoft.BizTalk.KwTpm.RoleLinkTypes  
mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
Microsoft.BizTalk.Edi.BaseArtifacts  
Microsoft.BizTalk.Edi.EdiPipelines  
Microsoft.BizTalk.Edi.BatchingOrchestration  
Microsoft.BizTalk.Edi.RoutingOrchestration  
Microsoft.BizTalk.Edi.EdiIntPipelines  
EAISchemas  
EAIOrchestrations  
B2BSchemas  
B2BOrchestrations  
WCFArtifacts  
FFDisassemblerWalkthrough  
BTSWhitespaceTest  

======================  
===     HOSTS      ===  
======================  

BizTalkServerApplication (InProcess)  
BizTalkServerIsolatedHost (Isolated)  

======================  
===    PARTIES     ===  
======================  

PartyB  
        Alias: Organization : OrganizationName = PartyB  

======================  
===   TRANSFORMS   ===  
======================  

EAISchemas.FFRequestDeniedMap :  
         EAISchemas.FlatFileSchema1 ==> EAISchemas.RequestDenied  

EAISchemas.RequestDeniedMap :  
         EAISchemas.Request ==> EAISchemas.RequestDenied  

B2BSchemas.InvoiceToPayment :  
         B2BSchemas.CommonInvoice ==> B2BSchemas.localhost1.Reference  

B2BSchemas.MapToCommonPO :  
         B2BSchemas.PO ==> B2BSchemas.localhost.Reference  

BizTalkArtifacts.ConcatMap :  
         BizTalkArtifacts.InputSchema ==> BizTalkArtifacts.OutputSchema  

FFDisassemblerWalkthrough.Map1 :  
         FFDisassemblerWalkthrough.Body ==> FFDisassemblerWalkthrough.Body  

BTSWhitespaceTest.Map1 :  
         FFDisassemblerWalkthrough.Body ==> BTSWhitespaceTest.Schema1  
```  

## <a name="see-also"></a>Vea también  
 [Admin\ExplorerOM (carpeta de ejemplos de BizTalk Server)](../core/admin-explorerom-biztalk-server-samples-folder.md)