---
title: "Arquitectura reducida con servicios de trabajadores de información | Documentos de Microsoft"
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
ms.assetid: ce1217bf-84a5-4888-89ba-dce85dc38340
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d02558e5904bf740c09ea0db614b2189555ac75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-down-architecture-with-information-worker-services"></a><span data-ttu-id="264bc-102">Arquitectura reducida con Servicios de trabajadores de la información</span><span class="sxs-lookup"><span data-stu-id="264bc-102">Scaled Down Architecture with Information Worker Services</span></span>
<span data-ttu-id="264bc-103">Para obtener información completa sobre la arquitectura del sistema para la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).</span><span class="sxs-lookup"><span data-stu-id="264bc-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="264bc-104">La siguiente ilustración muestra un ejemplo de arquitectura de BizTalk Server que incluye los servicios de trabajadores de la información y combina algunos de los dominios y servidores de BizTalk Server para reducir el número de servidores y servidores de seguridad necesarios.</span><span class="sxs-lookup"><span data-stu-id="264bc-104">The following figure provides a sample BizTalk Server architecture including the information worker services that combines some of the domains and BizTalk Servers to reduce the number of servers and firewalls you need.</span></span> <span data-ttu-id="264bc-105">Aunque esta arquitectura no es la más distribuida, separa los servidores de BizTalk Server basándose en sus funciones.</span><span class="sxs-lookup"><span data-stu-id="264bc-105">While this architecture is not the most distributed, it still separates the BizTalk Servers based on their function.</span></span>  
  
 <span data-ttu-id="264bc-106">![Topología Scaledown](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")</span><span class="sxs-lookup"><span data-stu-id="264bc-106">![Scaledown Topology](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")</span></span>  
  
        Scaled Down Architecture with Information Worker Services  
  
 <span data-ttu-id="264bc-107">En la ilustración anterior, los servidores del dominio de servicios e interfaces de servicio se corresponden con hosts de BizTalk, no con servidores físicos.</span><span class="sxs-lookup"><span data-stu-id="264bc-107">In the previous figure, the servers in the service interfaces and services domain correspond to BizTalk Hosts, and not physical servers.</span></span> <span data-ttu-id="264bc-108">Aunque se recomienda mantener el servidor secreto principal y las herramientas administrativas en equipos independientes, puede haber instancias de hosts de seguimiento, procesamiento, envío y recepción ejecutándose en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="264bc-108">While it is recommended to keep the master secret server and the administrative tools in stand-alone computers, you can have host instances for the tracking, processing, send, and receive hosts running on multiple computers.</span></span> <span data-ttu-id="264bc-109">Asimismo, los servidores de la red perimetral se corresponden con ubicaciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="264bc-109">Similarly, the servers in the perimeter network correspond to logical locations.</span></span>  
  
 <span data-ttu-id="264bc-110">Los servidores de la red perimetral para SMTP, Message Queue de Windows (MSMQ), archivo y SQL se corresponden con los servidores de correo, cola de mensajes, directorios y SQL Server, respectivamente, desde los que reciben y envían mensajes los hosts de recepción y envío de BizTalk del dominio de interfaces de servicio.</span><span class="sxs-lookup"><span data-stu-id="264bc-110">The servers in the perimeter network for SMTP, Windows Message Queuing (also known as MSMQ), File, and SQL correspond to the mail servers, queue, directory, or SQL Server respectively from which the BizTalk receive and send hosts in the service interfaces domain receive and send messages.</span></span>  
  
 <span data-ttu-id="264bc-111">Las bases de datos de SAE del domino de datos son las de importación principal, análisis, esquema de estrella y archivo de SAE.</span><span class="sxs-lookup"><span data-stu-id="264bc-111">The BAM databases in the data domain are BAM Primary Import, BAM Analysis, BAM Star Schema, and BAM Archive databases.</span></span> <span data-ttu-id="264bc-112">Las bases de datos de seguimiento y análisis del dominio de datos son los que utiliza BizTalk Server para almacenar información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="264bc-112">The Tracking and Analysis databases in the Data domain are the ones BizTalk Server uses for storing tracking information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="264bc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="264bc-113">See Also</span></span>  
 <span data-ttu-id="264bc-114">[Arquitectura reducida](../core/scaled-down-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="264bc-114">[Scaled Down Architecture](../core/scaled-down-architecture.md) </span></span>  
 <span data-ttu-id="264bc-115">[Arquitectura distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="264bc-115">[Large Distributed Architecture with Information Worker Services](../core/large-distributed-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="264bc-116">[Diseñar una arquitectura segura](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="264bc-116">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 [<span data-ttu-id="264bc-117">Arquitecturas de BizTalk Server de ejemplo</span><span class="sxs-lookup"><span data-stu-id="264bc-117">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)