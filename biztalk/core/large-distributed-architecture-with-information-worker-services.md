---
title: "Arquitectura con servicios de trabajadores de información distribuida de gran tamaño | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, examples
- architecture, large distributions
ms.assetid: 92f2d55c-3f51-42ca-99ef-60b23464691e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6b9b1729411e089566988714b83778abac80eb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="large-distributed-architecture-with-information-worker-services"></a><span data-ttu-id="68c4c-102">Arquitectura distribuida de gran tamaño con servicios de trabajadores de la información</span><span class="sxs-lookup"><span data-stu-id="68c4c-102">Large Distributed Architecture with Information Worker Services</span></span>
<span data-ttu-id="68c4c-103">Para obtener información completa acerca de cómo diseñar la arquitectura del sistema para la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).</span><span class="sxs-lookup"><span data-stu-id="68c4c-103">For complete information about designing the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="68c4c-104">La supervisión de la actividad económica (BAM) ofrece a los trabajadores de la información visibilidad de los procesos de negocio y comunicación directa con los socios.</span><span class="sxs-lookup"><span data-stu-id="68c4c-104">Business Activity Monitoring (BAM) gives information workers visibility into the business processes and direct communication with partners.</span></span> <span data-ttu-id="68c4c-105">Para proteger estos servicios, es necesario cumplir un conjunto de requisitos diferente.</span><span class="sxs-lookup"><span data-stu-id="68c4c-105">This presents a different set of requirements for securing these services.</span></span> <span data-ttu-id="68c4c-106">Es probable que los trabajadores de información tengan cuentas en el dominio corporativo y no en el dominio de datos, así mismo necesitan acceso al dominio de interfaces de servicio a fin de obtener acceso a algunos de los datos que genera BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="68c4c-106">Information workers are likely to have accounts in the corporate domain and not in the data domain, and they need access service interfaces domain to access to some of the data BizTalk Server generates.</span></span>  
  
 <span data-ttu-id="68c4c-107">La siguiente ilustración muestra una arquitectura de BizTalk Server distribuida que incluye BAM.</span><span class="sxs-lookup"><span data-stu-id="68c4c-107">The following figure shows a distributed BizTalk Server architecture that includes BAM.</span></span>  
  
 <span data-ttu-id="68c4c-108">![Arquitectura distribuida](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")</span><span class="sxs-lookup"><span data-stu-id="68c4c-108">![Distributed Architecture](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")</span></span>  
<span data-ttu-id="68c4c-109">Arquitectura distribuida de BizTalk Server con servicios de trabajadores de información</span><span class="sxs-lookup"><span data-stu-id="68c4c-109">Distributed BizTalk Server Architecture with Information Worker Services</span></span>  
  
 <span data-ttu-id="68c4c-110">En comparación con la arquitectura mostrada en [arquitectura distribuida grande](../core/large-distributed-architecture.md), la arquitectura distribuida de los servicios de trabajadores de información contiene un servicios de trabajadores de información adicional, como el Portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="68c4c-110">Compared to the architecture shown in [Large Distributed Architecture](../core/large-distributed-architecture.md), the distributed architecture for the information worker services contains an additional information worker services such as BAM Portal.</span></span> <span data-ttu-id="68c4c-111">El contenedor de servicios de trabajador de información incluye los siguientes servidores y servicios:</span><span class="sxs-lookup"><span data-stu-id="68c4c-111">The information worker services container includes the following servers and services:</span></span>  
  
-   <span data-ttu-id="68c4c-112">Un servidor de Portal de SAE:</span><span class="sxs-lookup"><span data-stu-id="68c4c-112">A BAM Portal server.</span></span> <span data-ttu-id="68c4c-113">los usuarios empresariales finales utilizan el portal de SAE para obtener acceso a las bases de datos de SAE a fin de supervisar los indicadores clave de rendimiento, que miden el progreso con respecto a un objetivo empresarial, así como otros datos sobre su proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="68c4c-113">Business end users use the BAM portal to access the BAM databases to monitor Key Performance Indicators (KPIs), which measure progress toward a business goal, as well as other information about their business process.</span></span> <span data-ttu-id="68c4c-114">Este servidor también tiene el servicio Web de consulta de SAE y el servicio Web de administración de SAE.</span><span class="sxs-lookup"><span data-stu-id="68c4c-114">This server also has the BAM Query Web service and BAM Management Web service.</span></span>  
  
-   <span data-ttu-id="68c4c-115">Un servidor de SQL Server para BAM: la base de datos de importación principal de BAM, la base de datos de archivo de BAM, la base de datos de esquema de estrella de BAM y la base de datos de análisis de BAM.</span><span class="sxs-lookup"><span data-stu-id="68c4c-115">A SQL Server for BAM: the BAM Primary Import database, BAM Archive database, BAM Star Schema database, and BAM Analysis database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68c4c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="68c4c-116">See Also</span></span>  
 <span data-ttu-id="68c4c-117">[Arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="68c4c-117">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="68c4c-118">[Arquitectura reducida con servicios de trabajadores de información](../core/scaled-down-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="68c4c-118">[Scaled Down Architecture with Information Worker Services](../core/scaled-down-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="68c4c-119">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="68c4c-119">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="68c4c-120">Arquitecturas de BizTalk Server de ejemplo</span><span class="sxs-lookup"><span data-stu-id="68c4c-120">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)