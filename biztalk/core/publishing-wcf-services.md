---
title: Publicar servicios WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF services, publishing
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5f72f2b300738f2e9a1a643e152048b64cf8f55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-wcf-services"></a><span data-ttu-id="2cf89-102">Publicar servicios WCF</span><span class="sxs-lookup"><span data-stu-id="2cf89-102">Publishing WCF Services</span></span>
<span data-ttu-id="2cf89-103">Se puede publicar una orquestación como un servicio WCF en [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para ser llamado por los clientes de WCF.</span><span class="sxs-lookup"><span data-stu-id="2cf89-103">An orchestration can be published as a WCF service in [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to be called by WCF clients.</span></span>  
  
 <span data-ttu-id="2cf89-104">**Publicar servicios WCF con adaptadores de WCF aislados**</span><span class="sxs-lookup"><span data-stu-id="2cf89-104">**Publishing WCF services with the isolated WCF adapters**</span></span>  
  
 <span data-ttu-id="2cf89-105">Es posible crear y publicar servicios WCF mediante el Asistente para publicación de Servicio WCF de BizTalk para adaptadores de WCF aislados, por ejemplo, el adaptador de WCF-BasicHttp, el adaptador de WCF-WSHttp y el adaptador de WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="2cf89-105">You create and publish WCF services by using the BizTalk WCF Service Publishing Wizard for the isolated WCF adapters such as the WCF-BasicHttp adapter, the WCF-WSHttp adapter, and the WCF-CustomIsolated adapter.</span></span> <span data-ttu-id="2cf89-106">Esto crea una ubicación de recepción que existe como una aplicación fuera de proceso en IIS.</span><span class="sxs-lookup"><span data-stu-id="2cf89-106">This creates a receive location which exists as an out of process application in IIS.</span></span>  
  
 <span data-ttu-id="2cf89-107">Antes de publicar un Servicio WCF con los adaptadores de WCF aislados, debe estar familiarizado con el modo en que los servicios WCF se alojan en Servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="2cf89-107">Before you publish a WCF service with the isolated WCF adapters, you should have an understanding of how to host WCF services in Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="2cf89-108">**La publicación de metadatos de servicio para ubicaciones de recepción de WCF**</span><span class="sxs-lookup"><span data-stu-id="2cf89-108">**Publishing service metadata for the WCF receive locations**</span></span>  
  
 <span data-ttu-id="2cf89-109">Cree los metadatos de servicio para ubicaciones de recepción WCF publicadas mediante el Asistente para publicación de Servicio WCF de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2cf89-109">You create service metadata for published WCF receive locations by using the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="2cf89-110">Para generar el código de cliente del modelo de servicio de los documentos de metadatos publicados puede usar la herramienta Utilidad de metadatos del modelo de servicio (SvcUtil.exe) incluida en el [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] Kit de desarrollo de Software (SDK) para [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] y [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Componentes de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2cf89-110">To generate service model client code from the published metadata documents you can use the Service Model Metadata Utility tool (SvcUtil.exe) included in the [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] Software Development Kit (SDK) for [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] and [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Runtime Components.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2cf89-111">Antes de ejecutar el Asistente para publicación de Servicio WCF de BizTalk, debe habilitar los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="2cf89-111">Before running the BizTalk WCF Service Publishing Wizard, you must enable WCF services.</span></span> <span data-ttu-id="2cf89-112">Para obtener más información acerca de cómo habilitar servicios WCF para el sistema, consulte [configurar IIS para los adaptadores de recepción de WCF aislados](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="2cf89-112">For more information about enabling WCF services for your system, see [Configuring IIS for the Isolated WCF Receive Adapters](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cf89-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2cf89-113">In This Section</span></span>  
  
-   [<span data-ttu-id="2cf89-114">Publicar servicios WCF con WCF aislado adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="2cf89-114">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="2cf89-115">Adaptadores de recepción de la publicación de metadatos de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="2cf89-115">Publishing Service Metadata for the WCF Receive Adapters</span></span>](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="2cf89-116">Consideraciones al publicar servicios WCF con WCF adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="2cf89-116">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="2cf89-117">Encabezados SOAP con servicios WCF publicados</span><span class="sxs-lookup"><span data-stu-id="2cf89-117">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)  
  
-   [<span data-ttu-id="2cf89-118">Cómo iniciar excepciones erróneas desde orquestaciones publicadas como servicios WCF</span><span class="sxs-lookup"><span data-stu-id="2cf89-118">How to Throw Fault Exceptions from Orchestrations Published as WCF Services</span></span>](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)