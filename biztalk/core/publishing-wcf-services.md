---
title: Publicar servicios WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00136b64d5feaf552f77b92b3ad4442da4e447cc
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710243"
---
# <a name="publish-wcf-services"></a><span data-ttu-id="9f5f7-102">Publicar servicios WCF</span><span class="sxs-lookup"><span data-stu-id="9f5f7-102">Publish WCF Services</span></span>
<span data-ttu-id="9f5f7-103">Puede publicar una orquestación como un servicio WCF en BizTalk Server para ser llamado por los clientes de WCF.</span><span class="sxs-lookup"><span data-stu-id="9f5f7-103">An orchestration can be published as a WCF service in BizTalk Server to be called by WCF clients.</span></span>  
  
## <a name="publish-wcf-services-with-the-isolated-wcf-adapters"></a><span data-ttu-id="9f5f7-104">Publicar servicios WCF con los adaptadores WCF aislados</span><span class="sxs-lookup"><span data-stu-id="9f5f7-104">Publish WCF services with the isolated WCF adapters</span></span> 
  
 <span data-ttu-id="9f5f7-105">Es posible crear y publicar servicios WCF mediante el Asistente para publicación de Servicio WCF de BizTalk para adaptadores de WCF aislados, por ejemplo, el adaptador de WCF-BasicHttp, el adaptador de WCF-WSHttp y el adaptador de WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="9f5f7-105">You create and publish WCF services by using the BizTalk WCF Service Publishing Wizard for the isolated WCF adapters such as the WCF-BasicHttp adapter, the WCF-WSHttp adapter, and the WCF-CustomIsolated adapter.</span></span> <span data-ttu-id="9f5f7-106">Esto crea una ubicación de recepción que existe como una aplicación fuera de proceso en IIS.</span><span class="sxs-lookup"><span data-stu-id="9f5f7-106">This creates a receive location which exists as an out of process application in IIS.</span></span>  
  
 <span data-ttu-id="9f5f7-107">Antes de publicar un Servicio WCF con los adaptadores de WCF aislados, debe estar familiarizado con el modo en que los servicios WCF se alojan en Servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="9f5f7-107">Before you publish a WCF service with the isolated WCF adapters, you should have an understanding of how to host WCF services in Internet Information Services (IIS).</span></span>  
  
## <a name="publish-service-metadata-for-the-wcf-receive-locations"></a><span data-ttu-id="9f5f7-108">Publicar metadatos de servicio para ubicaciones de recepción de WCF</span><span class="sxs-lookup"><span data-stu-id="9f5f7-108">Publish service metadata for the WCF receive locations</span></span>
  
 <span data-ttu-id="9f5f7-109">Cree los metadatos de servicio para ubicaciones de recepción WCF publicadas mediante el Asistente para publicación de Servicio WCF de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9f5f7-109">You create service metadata for published WCF receive locations by using the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="9f5f7-110">Para generar el código de cliente del modelo de servicio de los documentos de metadatos publicados, que puede usar la herramienta Utilidad de metadatos del modelo de servicio (SvcUtil.exe) incluida en el Kit de desarrollo de Software (SDK) de Windows y componentes de tiempo de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f5f7-110">To generate service model client code from the published metadata documents you can use the Service Model Metadata Utility tool (SvcUtil.exe) included in the Windows Software Development Kit (SDK) and .NET Framework Runtime Components.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9f5f7-111">Antes de ejecutar el Asistente para publicación de Servicio WCF de BizTalk, debe habilitar los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="9f5f7-111">Before running the BizTalk WCF Service Publishing Wizard, you must enable WCF services.</span></span> <span data-ttu-id="9f5f7-112">Para obtener más información acerca de cómo habilitar servicios WCF para el sistema, consulte [configurar IIS para los adaptadores de recepción de WCF aislados](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="9f5f7-112">For more information about enabling WCF services for your system, see [Configuring IIS for the Isolated WCF Receive Adapters](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9f5f7-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9f5f7-113">Next steps</span></span>
  
-   [<span data-ttu-id="9f5f7-114">Publicación de servicios WCF con los adaptadores de recepción WCF aislados</span><span class="sxs-lookup"><span data-stu-id="9f5f7-114">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="9f5f7-115">Publicación de metadatos de servicio para los adaptadores de recepción WCF</span><span class="sxs-lookup"><span data-stu-id="9f5f7-115">Publishing Service Metadata for the WCF Receive Adapters</span></span>](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="9f5f7-116">Consideraciones al publicar servicios WCF con los adaptadores de recepción WCF</span><span class="sxs-lookup"><span data-stu-id="9f5f7-116">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="9f5f7-117">Encabezados SOAP con servicios WCF publicados</span><span class="sxs-lookup"><span data-stu-id="9f5f7-117">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)  
  
-   [<span data-ttu-id="9f5f7-118">Iniciar excepciones erróneas desde orquestaciones publicadas como servicios WCF</span><span class="sxs-lookup"><span data-stu-id="9f5f7-118">Throw Fault Exceptions from Orchestrations Published as WCF Services</span></span>](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)