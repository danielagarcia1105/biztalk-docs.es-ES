---
title: Problemas conocidos con los interceptores WF y WCF de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2407809-1f71-41a9-b305-722a7f86af5b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42078eb2b1272072016ded9a117e88ddf4fda038
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="5af09-102">Problemas conocidos de los interceptores de WCF y WF de BAM</span><span class="sxs-lookup"><span data-stu-id="5af09-102">Known Issues with the BAM WCF and WF Interceptors</span></span>
<span data-ttu-id="5af09-103">En esta sección se proporciona información acerca de problemas conocidos que puede encontrarse al utilizar los interceptores de BAM para Windows Workflow Foundation o Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="5af09-103">This section provides information about known issues that you may experience when using the BAM interceptors for Windows Workflow Foundation or Windows Communication Foundation.</span></span>  
  
## <a name="intercepting-a-dynamically-generated-wcf-assembly-hosted-in-iis"></a><span data-ttu-id="5af09-104">Interceptar un ensamblado de WCF generado de forma dinámica alojado en IIS</span><span class="sxs-lookup"><span data-stu-id="5af09-104">Intercepting a dynamically generated WCF assembly hosted in IIS</span></span>  
 <span data-ttu-id="5af09-105">Cuando se usa IIS para alojar una aplicación de Windows Communication Foundation (WCF) integrada (por ejemplo, un archivo de servicio que especifica el origen del ensamblado), el ensamblado de WCF se generará de forma dinámica, se le asignará un nombre de archivo arbitrario y se colocará en la carpeta temporal asp.net.</span><span class="sxs-lookup"><span data-stu-id="5af09-105">When you are using IIS to host an embedded Windows Communication Foundation application (for example, a service file that specifies the assembly source), the WCF assembly will be dynamically generated, assigned an arbitrary file name, and placed in the asp.net temporary folder.</span></span> <span data-ttu-id="5af09-106">Debido a que el archivo de configuración del interceptor necesita información de manifiesto y debido a que en los archivos de configuración del interceptor no están disponibles los caracteres comodín ni otros métodos dinámicos para especificar el manifiesto, debe volver compilar el servicio y crear el archivo de configuración del interceptor o bien volver a implementar el archivo de configuración del interceptor una vez que ha implementado todas las páginas Web asp.net que contienen código de WCF integrado.</span><span class="sxs-lookup"><span data-stu-id="5af09-106">Since the interceptor configuration file requires manifest information and since wildcard characters or other dynamic methods for specifying the manifest are not available with interceptor configuration files, you must recompile your service and then build your interceptor configuration file or redeploy your interceptor configuration file after you have deployed all of the asp.net web pages containing embedded WCF code.</span></span>  
  
## <a name="use-of-the-bam-interceptor-for-windows-workflow-foundation-is-not-supported-in-office-and-sharepoint-server"></a><span data-ttu-id="5af09-107">Uso del interceptor de BAM para Windows Workflow Foundation no compatible con Office ni con Sharepoint Server</span><span class="sxs-lookup"><span data-stu-id="5af09-107">Use of the BAM interceptor for Windows Workflow Foundation is not supported in Office and Sharepoint Server</span></span>  
 <span data-ttu-id="5af09-108">Tanto Office como Windows Sharepoint Server no leen en el archivo de configuración de la aplicación cuando inicializan el tiempo de ejecución de WF.</span><span class="sxs-lookup"><span data-stu-id="5af09-108">Both office and Windows Sharepoint Server do not read from the application configuration file when initializing the WF runtime.</span></span> <span data-ttu-id="5af09-109">Como resultado, el interceptor de BAM para WF se podría configurar para una aplicación aunque no se cargará en el tiempo de ejecución del flujo de trabajo cuando está alojado en estos entornos.</span><span class="sxs-lookup"><span data-stu-id="5af09-109">As a result, the BAM interceptor for WF may be configured for an application but it will not be loaded into the workflow runtime when hosted within these environments.</span></span>  
  
## <a name="client-service-locks-when-intiating-a-distributed-transaction"></a><span data-ttu-id="5af09-110">Bloqueo del servicio del cliente al iniciar una transacción distribuida</span><span class="sxs-lookup"><span data-stu-id="5af09-110">Client service locks when intiating a distributed transaction</span></span>  
 <span data-ttu-id="5af09-111">Si la operación del servicio no va a participar en la transacción que el cliente inicia y éste invoca el servicio desde el contexto de un ámbito de transacción, podría producirse un interbloqueo, en especial si hay datos que se recopilan desde el cliente antes de la solicitud de envío y desde el servicio por la solicitud de recepción para la misma actividad.</span><span class="sxs-lookup"><span data-stu-id="5af09-111">If the service operation will not be participating in the transaction initiated by the client and the client is invoking the service from the context of a transaction scope, a deadlock could result, especially if there is data being collected from the client before the send request and from the service by the receive request for the same activity.</span></span>  
  
 <span data-ttu-id="5af09-112">Para evitar esta situación, debe especificar que el cliente no participa en la transacción mediante la declaración "Enlist = false" en el atributo `ConnectionString` del cliente para la extensión de comportamiento de BAM en el archivo app.config del cliente, tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="5af09-112">To avoid this situation, you should specify that the client does not participate in the transaction by declaring "Enlist = false" in the client `ConnectionString` attribute for the BAM behavior extension in the client's app.config file as demonstrated below.</span></span>  
  
```  
<behavior name="bamClientBehavior">  
  <bamClientBehaviorExtension ConnectionString="Integrated Security=SSPI;Initial Catalog=BAMPrimaryImport;Data Source=.;  Enlist=false"  PollingIntervalSec="1500" />  
</behavior>  
```  
  
## <a name="open-wcf-channel-before-sending-a-message-when-bam-interceptors-are-used"></a><span data-ttu-id="5af09-113">Abrir el canal WCF antes de enviar un mensaje cuando se usan interceptores BAM</span><span class="sxs-lookup"><span data-stu-id="5af09-113">Open WCF Channel Before Sending a Message when BAM Interceptors are used</span></span>  
 <span data-ttu-id="5af09-114">Cuando el interceptor BAM se habilita para WCF con vinculación BasicHttp, el proxy debe llamar a proxy.Open() para abrir el canal explícitamente.</span><span class="sxs-lookup"><span data-stu-id="5af09-114">When BAM interceptor is enabled for WCF with BasicHttp binding, proxy should call proxy.Open() to explicitly open the channel.</span></span> <span data-ttu-id="5af09-115">Si el canal no se abre de forma explícita, la interceptación BAM puede fallar con una excepción.</span><span class="sxs-lookup"><span data-stu-id="5af09-115">If the channel is not opened explicitly, BAM interception can fail with an exception.</span></span>