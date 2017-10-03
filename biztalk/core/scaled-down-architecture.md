---
title: Arquitectura reducida | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: e25798aa-4a1e-418c-9e0c-db964e8b5a80
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a112f3f737a1a5aec0cfac16b7689d3dada1e8ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-down-architecture"></a><span data-ttu-id="3c9c2-102">Arquitectura reducida</span><span class="sxs-lookup"><span data-stu-id="3c9c2-102">Scaled Down Architecture</span></span>
<span data-ttu-id="3c9c2-103">Para obtener información completa sobre la arquitectura del sistema para[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación, consulte [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).</span><span class="sxs-lookup"><span data-stu-id="3c9c2-103">For complete information about the system architecture for[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="3c9c2-104">La siguiente ilustración muestra un ejemplo de arquitectura de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que combina algunos de los dominios y servidores de BizTalk Server para reducir el número de servidores y firewalls necesarios.</span><span class="sxs-lookup"><span data-stu-id="3c9c2-104">The following figure provides a sample [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture that combines some of the domains and BizTalk Servers to reduce the number of servers and firewalls you need.</span></span> <span data-ttu-id="3c9c2-105">Aunque esta arquitectura no es la más distribuida, separa los servidores de BizTalk Server basándose en sus funciones.</span><span class="sxs-lookup"><span data-stu-id="3c9c2-105">While this architecture is not the most distributed, it still separates the BizTalk Servers based on their function.</span></span>  
  
 <span data-ttu-id="3c9c2-106">![Arquitectura reducida](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")</span><span class="sxs-lookup"><span data-stu-id="3c9c2-106">![Scaled down architecture](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")</span></span>  
  
        Scaled Down Architecture  
  
 <span data-ttu-id="3c9c2-107">En la ilustración anterior, los servidores del dominio de servicios e interfaces de servicio se corresponden con hosts de BizTalk, no con servidores físicos.</span><span class="sxs-lookup"><span data-stu-id="3c9c2-107">In the previous figure, the servers in the service interfaces and services domain correspond to BizTalk Hosts, and not physical servers.</span></span> <span data-ttu-id="3c9c2-108">Aunque se recomienda mantener el servidor secreto principal y las herramientas administrativas en equipos independientes, puede haber instancias de hosts de seguimiento, procesamiento, envío y recepción ejecutándose en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="3c9c2-108">While it is recommended to keep the master secret server and the administrative tools in stand-alone computers, you can have host instances for the tracking, processing, send, and receive hosts running on multiple computers.</span></span> <span data-ttu-id="3c9c2-109">Asimismo, los servidores de la red perimetral se corresponden con ubicaciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="3c9c2-109">Similarly, the servers in the perimeter network correspond to logical locations.</span></span>  
  
 <span data-ttu-id="3c9c2-110">Los servidores de la red perimetral para SMTP, Message Queue Server, archivo y SQL se corresponden con los servidores de correo, cola de mensajes, directorios y SQL Server, respectivamente, desde los que reciben y envían mensajes los hosts de recepción y envío de BizTalk del dominio de procesamiento y servicios.</span><span class="sxs-lookup"><span data-stu-id="3c9c2-110">The servers in the perimeter network for SMTP, Message Queuing, File, and SQL correspond to the mail servers, queue, directory, or SQL Server respectively from which the BizTalk receive and send hosts in the processing and services domain receive and send messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c9c2-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c9c2-111">See Also</span></span>  
 <span data-ttu-id="3c9c2-112">[Arquitectura reducida con servicios de trabajadores de información](../core/scaled-down-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="3c9c2-112">[Scaled Down Architecture with Information Worker Services](../core/scaled-down-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="3c9c2-113">[Arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="3c9c2-113">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="3c9c2-114">[Diseñar una arquitectura segura](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="3c9c2-114">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 [<span data-ttu-id="3c9c2-115">Arquitecturas de BizTalk Server de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c9c2-115">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)