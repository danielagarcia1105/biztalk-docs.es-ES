---
title: Integración de regulación de SOA con el Kit de herramientas ESB en BizTalk Server | Documentos de Microsoft
description: Lista de desafíos de integración de sistema y de terceros basada en SOA con el Kit de herramientas de ESB en BizTalk Server
caps.latest.revision: 3
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccb5ac2d-cd90-414d-a6c7-045a8fe9450b
ms.author: mandia
ms.openlocfilehash: 9e1489e01a8918d1dfa7ca61a69d57f5d7316f68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295020"
---
# <a name="soa-governance-integration"></a><span data-ttu-id="fa88f-103">Integración de regulación de SOA</span><span class="sxs-lookup"><span data-stu-id="fa88f-103">SOA Governance Integration</span></span>
<span data-ttu-id="fa88f-104">Las aplicaciones de nivel empresarial deben admitir características de administración sólida y confiable para que pueda cumplir los requisitos empresariales, legislación gubernamentales, contratos de nivel de servicio (SLA) y del cliente y comerciales las expectativas de los socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="fa88f-104">Enterprise-level applications must support robust and reliable management features to be able to comply with business requirements, government legislation, service level agreements (SLAs), and customer and trading partner expectations.</span></span> <span data-ttu-id="fa88f-105">Regulación de tiempo de ejecución se centra específicamente en los requisitos y desafíos de arquitectura orientada a servicios (SOA) se ejecute correctamente, en función de los sistemas que cumplen estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="fa88f-105">Run-time governance focuses specifically on the challenges of, and requirements for, successfully running service-oriented architecture (SOA)–based systems that meet these requirements.</span></span> <span data-ttu-id="fa88f-106">La calidad de servicio ofrecido por un sistema de negocio es el factor predominante que define su éxito o fracaso.</span><span class="sxs-lookup"><span data-stu-id="fa88f-106">The quality of service delivered by a business system is the predominant factor that defines its success or failure.</span></span>  

## <a name="soa-challenges"></a><span data-ttu-id="fa88f-107">Desafíos SOA</span><span class="sxs-lookup"><span data-stu-id="fa88f-107">SOA challenges</span></span>  
 <span data-ttu-id="fa88f-108">Implementar sistemas basados en SOA en la producción de las empresas enfrentan a una serie de desafíos, incluidas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa88f-108">Businesses deploying SOA-based systems into production face a number of challenges, including the following:</span></span>  
  
-   <span data-ttu-id="fa88f-109">Minimizar el costo de las actualizaciones y mantenimiento y permite que las actualizaciones incrementales</span><span class="sxs-lookup"><span data-stu-id="fa88f-109">Minimizing the cost of maintenance and upgrades, and allowing incremental updates</span></span>  
  
-   <span data-ttu-id="fa88f-110">Permitir cambio rápido mediante herramientas de administración y la composición de procesos de negocios</span><span class="sxs-lookup"><span data-stu-id="fa88f-110">Allowing rapid change through business process management and composition tools</span></span>  
  
-   <span data-ttu-id="fa88f-111">Seguridad de extremo a extremo; Esto incluye la confianza y la protección de la privacidad de contenido, receptores y remitentes de mensajes</span><span class="sxs-lookup"><span data-stu-id="fa88f-111">End-to-end security; this includes trust and protection of the privacy of message senders, receivers, and content</span></span>  
  
-   <span data-ttu-id="fa88f-112">Identificar, administrar y reparar las excepciones cuando se producen</span><span class="sxs-lookup"><span data-stu-id="fa88f-112">Identifying, managing, and repairing exceptions as they occur</span></span>  
  
-   <span data-ttu-id="fa88f-113">Separación de servicios y los consumidores</span><span class="sxs-lookup"><span data-stu-id="fa88f-113">Decoupling of services and consumers</span></span>  
  
-   <span data-ttu-id="fa88f-114">Medir y demostrar el valor empresarial de las aplicaciones SOA para compensar las preocupaciones de costo</span><span class="sxs-lookup"><span data-stu-id="fa88f-114">Measuring and proving the business value of SOA applications to offset cost concerns</span></span>  
  
-   <span data-ttu-id="fa88f-115">Control (control) de la proliferación de servicios duplicadas o innecesarias en caso contrario</span><span class="sxs-lookup"><span data-stu-id="fa88f-115">Control (governance) of the proliferation of duplicate or otherwise unnecessary services</span></span>  
  
-   <span data-ttu-id="fa88f-116">Facilitar la identificación de los servicios correspondientes necesarios para los usuarios posibles para reducir el costo de desarrollo inicial</span><span class="sxs-lookup"><span data-stu-id="fa88f-116">Facilitating the identification of the appropriate services required by potential users to reduce initial development cost</span></span>  
  
-   <span data-ttu-id="fa88f-117">Administrar el ciclo de vida de servicios para minimizar el costo y el riesgo del mantenimiento continuado y cambiar</span><span class="sxs-lookup"><span data-stu-id="fa88f-117">Managing the life cycle of services to minimize the cost and risk of ongoing maintenance and change</span></span>  
  
-   <span data-ttu-id="fa88f-118">Simplificar el uso real de servicios adecuados (desacoplamiento ubicación, transporte, directivas, estándares y estilos de mensajería)</span><span class="sxs-lookup"><span data-stu-id="fa88f-118">Simplifying the actual usage of appropriate services (decoupling location, transport, policies, standards, and messaging styles)</span></span>  
  
-   <span data-ttu-id="fa88f-119">Reporting instalaciones utilizadas para identificar quién está utilizando qué servicio, dónde y porqué</span><span class="sxs-lookup"><span data-stu-id="fa88f-119">Reporting facilities used to identify who is using which service, where, and why</span></span>  

## <a name="next-steps"></a><span data-ttu-id="fa88f-120">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fa88f-120">Next steps</span></span>
 <span data-ttu-id="fa88f-121">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite la integración con dos sistemas de control de tiempo de ejecución de terceros:</span><span class="sxs-lookup"><span data-stu-id="fa88f-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports integration with two third-party run-time governance systems:</span></span>  
  
-   <span data-ttu-id="fa88f-122">**Resolución de Sentinet SOA y extensiones de servidor BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="fa88f-122">**Sentinet SOA Resolver and BizTalk Server Extensions**.</span></span> <span data-ttu-id="fa88f-123">Para obtener más información sobre cómo se amplía Sentinet [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] capacidades, consulte [extender BizTalk ESB Toolkit capacidades con Sentinet](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md).</span><span class="sxs-lookup"><span data-stu-id="fa88f-123">For more information on how Sentinet extends [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] capabilities, see [Extending BizTalk ESB Toolkit Capabilities with Sentinet](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md).</span></span>
  
-   <span data-ttu-id="fa88f-124">[Punto de administración de BizTalk de SOA](../esb-toolkit/soa-biztalk-management-point.md) de SOA Software, Inc.</span><span class="sxs-lookup"><span data-stu-id="fa88f-124">[SOA BizTalk Management Point](../esb-toolkit/soa-biztalk-management-point.md) from SOA Software, Inc.</span></span>  
  
-   <span data-ttu-id="fa88f-125">[Agente de AmberPoint BizTalk Nano](../esb-toolkit/amberpoint-biztalk-nano-agent.md) de AmberPoint, Inc.</span><span class="sxs-lookup"><span data-stu-id="fa88f-125">[AmberPoint BizTalk Nano Agent](../esb-toolkit/amberpoint-biztalk-nano-agent.md) from AmberPoint, Inc.</span></span>