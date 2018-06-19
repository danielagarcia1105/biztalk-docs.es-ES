---
title: Cargar interceptores de BAM con la API de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d77ea5fb-a796-48f1-8c77-173e995c5252
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 363c4fc43092e63b664d42bb0420263bd7439dad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261932"
---
# <a name="loading-bam-interceptors-using-the-bam-api"></a><span data-ttu-id="21f5e-102">Cargar interceptores de BAM con la API de BAM</span><span class="sxs-lookup"><span data-stu-id="21f5e-102">Loading BAM Interceptors Using the BAM API</span></span>
<span data-ttu-id="21f5e-103">En este tema se ofrece información sobre la carga de interceptores de WF y WCF desde el código, en lugar de a través de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="21f5e-103">This topic provides information about loading the WF and WCF interceptors from your code rather than through a configuration file.</span></span>  
  
## <a name="loading-the-wf-interceptor-from-code"></a><span data-ttu-id="21f5e-104">Cargar el interceptor de WF desde código</span><span class="sxs-lookup"><span data-stu-id="21f5e-104">Loading the WF Interceptor from Code</span></span>  
 <span data-ttu-id="21f5e-105">Para cargar el tiempo de ejecución del interceptor de WF desde el código, debe crear una nueva instancia de WorkflowRuntime y llamar al método AddService con una instancia nueva de BamTrackingService.</span><span class="sxs-lookup"><span data-stu-id="21f5e-105">To load the WF interceptor runtime from your code, you must create a new instance of WorkflowRuntime and call the AddService method with a new instance of BamTrackingService.</span></span> <span data-ttu-id="21f5e-106">Observe la demostración siguiente.</span><span class="sxs-lookup"><span data-stu-id="21f5e-106">This is demonstrated below.</span></span>  
  
```csharp  
string connectionString = "Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport";  
int PollingIntervalSec = 300;  
  
WorkflowRuntime workflowRuntime = new WorkflowRuntime();  
workflowRuntime.AddService(new BamTrackingService(connectionString, interceptorConfigurationPollingInterval));  
```  
  
## <a name="loading-the-wcf-interceptor-from-code"></a><span data-ttu-id="21f5e-107">Cargar el interceptor de WCF desde código</span><span class="sxs-lookup"><span data-stu-id="21f5e-107">Loading the WCF Interceptor from Code</span></span>  
 <span data-ttu-id="21f5e-108">Para cargar el interceptor de WCF, debe crear una clase derivada que abra el servicio y esté accesible para la implementación.</span><span class="sxs-lookup"><span data-stu-id="21f5e-108">To load the WCF interceptor, you must create a derived class that opens the service and is accessible to your implementation.</span></span> <span data-ttu-id="21f5e-109">Observe la demostración siguiente.</span><span class="sxs-lookup"><span data-stu-id="21f5e-109">This is demonstrated below.</span></span>  
  
```csharp  
// Your project must have a reference to Microsoft.BizTalk.BAM.Interceptors.dll.  
// Create a derived class accessible to the implementation that opens the service.  
internal class MyBamBehaviorExtension : BamBehaviorExtension  
{  
    internal MyBamBehaviorExtension(string connectionString, int pollingInterval)  
        : base()  
    {  
        this.ConnectionString = connectionString;  
        this.PollingIntervalSec = pollingInterval.ToString();  
    }  
  
    internal IEndpointBehavior Create()  
    {  
        return (IEndpointBehavior) this.CreateBehavior();  
    }  
}  
  
// Add the endpoint behavior just before the service is opened.   
// In this example the connection string and polling intervals are being read from appSettings in App.config.  
MyBamBehaviorExtension bamBehaviorExtension = new MyBamBehaviorExtension(ConfigurationManager.AppSettings["ConnectionString"], int.Parse(ConfigurationManager.AppSettings["PollingIntervalSec"]));  
IEndpointBehavior bamBehavior = bamBehaviorExtension.Create();  
foreach (System.ServiceModel.Description.ServiceEndpoint endpoint in myServiceHost.Description.Endpoints)  
{  
    if (endpoint.Behaviors.Find<MyBamBehaviorExtension>() == null)  
        endpoint.Behaviors.Add(bamBehavior);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="21f5e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="21f5e-110">See Also</span></span>  
 [<span data-ttu-id="21f5e-111">Uso de los interceptores WF y WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="21f5e-111">Using the BAM WCF and WF Interceptors</span></span>](../core/using-the-bam-wcf-and-wf-interceptors.md)