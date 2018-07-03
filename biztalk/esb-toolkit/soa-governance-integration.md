---
title: Integración de gobierno de SOA con el Kit de herramientas ESB en BizTalk Server | Microsoft Docs
description: Lista de los desafíos de integración del sistema y de terceros basadas en SOA con el Kit de herramientas de ESB en BizTalk Server
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
ms.openlocfilehash: 1b989373f4e0f10439374842c2dcf6c8b8226165
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023050"
---
# <a name="soa-governance-integration"></a><span data-ttu-id="9258c-103">Integración de gobierno de SOA</span><span class="sxs-lookup"><span data-stu-id="9258c-103">SOA Governance Integration</span></span>
<span data-ttu-id="9258c-104">Aplicaciones de nivel empresarial deben admitir las características de administración sólidas y confiables para poder cumplir con los requisitos empresariales, legislación gubernamental, acuerdos de nivel de servicio (SLA) y al cliente y comerciales expectativas asociado.</span><span class="sxs-lookup"><span data-stu-id="9258c-104">Enterprise-level applications must support robust and reliable management features to be able to comply with business requirements, government legislation, service level agreements (SLAs), and customer and trading partner expectations.</span></span> <span data-ttu-id="9258c-105">Regulación de tiempo de ejecución se centra específicamente en los requisitos y desafíos de la arquitectura orientada a servicios (SOA) se ejecuta correctamente: en función de los sistemas que cumplen estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="9258c-105">Run-time governance focuses specifically on the challenges of, and requirements for, successfully running service-oriented architecture (SOA)–based systems that meet these requirements.</span></span> <span data-ttu-id="9258c-106">La calidad del servicio ofrecido por un sistema de negocio es el factor predominante que define su éxito o fracaso.</span><span class="sxs-lookup"><span data-stu-id="9258c-106">The quality of service delivered by a business system is the predominant factor that defines its success or failure.</span></span>  

## <a name="soa-challenges"></a><span data-ttu-id="9258c-107">Retos de SOA:</span><span class="sxs-lookup"><span data-stu-id="9258c-107">SOA challenges</span></span>  
 <span data-ttu-id="9258c-108">Las empresas implementar sistemas basados en SOA en producción enfrentan a una serie de desafíos, incluidas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9258c-108">Businesses deploying SOA-based systems into production face a number of challenges, including the following:</span></span>  

-   <span data-ttu-id="9258c-109">Minimizar el costo de las actualizaciones y mantenimiento y permite que las actualizaciones incrementales</span><span class="sxs-lookup"><span data-stu-id="9258c-109">Minimizing the cost of maintenance and upgrades, and allowing incremental updates</span></span>  

-   <span data-ttu-id="9258c-110">Lo que permite un cambio rápido a través de las herramientas de administración y la composición de procesos de negocios</span><span class="sxs-lookup"><span data-stu-id="9258c-110">Allowing rapid change through business process management and composition tools</span></span>  

-   <span data-ttu-id="9258c-111">Seguridad de extremo a otro; Esto incluye la confianza y la protección de la privacidad de contenido, receptores y remitentes de mensajes</span><span class="sxs-lookup"><span data-stu-id="9258c-111">End-to-end security; this includes trust and protection of the privacy of message senders, receivers, and content</span></span>  

-   <span data-ttu-id="9258c-112">Identificar, administrar y reparar las excepciones cuando se producen</span><span class="sxs-lookup"><span data-stu-id="9258c-112">Identifying, managing, and repairing exceptions as they occur</span></span>  

-   <span data-ttu-id="9258c-113">Desacoplamiento de servicios y los consumidores</span><span class="sxs-lookup"><span data-stu-id="9258c-113">Decoupling of services and consumers</span></span>  

-   <span data-ttu-id="9258c-114">Medir y demostrar el valor empresarial de las aplicaciones SOA se va a desplazar las preocupaciones de costo</span><span class="sxs-lookup"><span data-stu-id="9258c-114">Measuring and proving the business value of SOA applications to offset cost concerns</span></span>  

-   <span data-ttu-id="9258c-115">Control (control) de la proliferación de servicios duplicadas o innecesarias en caso contrario</span><span class="sxs-lookup"><span data-stu-id="9258c-115">Control (governance) of the proliferation of duplicate or otherwise unnecessary services</span></span>  

-   <span data-ttu-id="9258c-116">Facilitar la identificación de los servicios apropiados que se necesitan los usuarios potenciales para reducir los costos de desarrollo inicial</span><span class="sxs-lookup"><span data-stu-id="9258c-116">Facilitating the identification of the appropriate services required by potential users to reduce initial development cost</span></span>  

-   <span data-ttu-id="9258c-117">Administración del ciclo de vida de servicios para minimizar los costos y riesgos de mantenimiento continuo y cambiar</span><span class="sxs-lookup"><span data-stu-id="9258c-117">Managing the life cycle of services to minimize the cost and risk of ongoing maintenance and change</span></span>  

-   <span data-ttu-id="9258c-118">Lo que simplifica el uso real de los servicios apropiados (desacoplamiento ubicación, transporte, directivas, estándares y estilos de mensajería)</span><span class="sxs-lookup"><span data-stu-id="9258c-118">Simplifying the actual usage of appropriate services (decoupling location, transport, policies, standards, and messaging styles)</span></span>  

-   <span data-ttu-id="9258c-119">Informar de las instalaciones que se usa para identificar quién está usando el servicio, dónde y por qué</span><span class="sxs-lookup"><span data-stu-id="9258c-119">Reporting facilities used to identify who is using which service, where, and why</span></span>  

## <a name="next-steps"></a><span data-ttu-id="9258c-120">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9258c-120">Next steps</span></span>
 <span data-ttu-id="9258c-121">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite la integración con dos sistemas de control de tiempo de ejecución de terceros:</span><span class="sxs-lookup"><span data-stu-id="9258c-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports integration with two third-party run-time governance systems:</span></span>  

- <span data-ttu-id="9258c-122">**Resolución de Sentinet SOA y las extensiones de servidor BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="9258c-122">**Sentinet SOA Resolver and BizTalk Server Extensions**.</span></span> <span data-ttu-id="9258c-123">Para obtener más información sobre cómo se amplía Sentinet [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] capacidades, consulte [ampliar capacidades de Kit de herramientas de BizTalk ESB con Sentinet](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md).</span><span class="sxs-lookup"><span data-stu-id="9258c-123">For more information on how Sentinet extends [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] capabilities, see [Extending BizTalk ESB Toolkit Capabilities with Sentinet](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md).</span></span>

- <span data-ttu-id="9258c-124">[Punto de administración de BizTalk de SOA](../esb-toolkit/soa-biztalk-management-point.md) de SOA Software, Inc.</span><span class="sxs-lookup"><span data-stu-id="9258c-124">[SOA BizTalk Management Point](../esb-toolkit/soa-biztalk-management-point.md) from SOA Software, Inc.</span></span>  

- <span data-ttu-id="9258c-125">[Agente Nano de BizTalk de AmberPoint](../esb-toolkit/amberpoint-biztalk-nano-agent.md) de AmberPoint, Inc.</span><span class="sxs-lookup"><span data-stu-id="9258c-125">[AmberPoint BizTalk Nano Agent](../esb-toolkit/amberpoint-biztalk-nano-agent.md) from AmberPoint, Inc.</span></span>
