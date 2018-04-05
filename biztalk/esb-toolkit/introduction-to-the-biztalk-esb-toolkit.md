---
title: Introducción al Kit de herramientas de ESB de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- ESBToolkitV2.introduction
ms.assetid: 98a957b8-5855-4872-b7e7-58a2e1d6b2b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e44d3a100cdaefe04cf9d3aedfa8cf969811fc5e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="introduction-to-the-biztalk-esb-toolkit"></a><span data-ttu-id="9ebde-102">Introducción al Kit de herramientas de ESB de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9ebde-102">Introduction to the BizTalk ESB Toolkit</span></span>
<span data-ttu-id="9ebde-103">Explica la arquitectura y el contenido de Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ebde-103">Explains the architecture and contents of the Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="9ebde-104">La documentación también muestra cómo aplicar un modelo de arquitectura de Bus de servicio de empresa (ESB) para desarrollar aplicaciones empresariales que permiten flexible y seguro, y servicios reutilizables y organización rápida de los servicios existentes en el nuevo extremo procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="9ebde-104">The documentation also demonstrates how to apply an Enterprise Service Bus (ESB) architecture pattern to develop enterprise applications that enable flexible, secure, and reusable services and rapid organization of existing services into new end-to-end business processes.</span></span>  
  
## <a name="what-is-an-enterprise-service-bus"></a><span data-ttu-id="9ebde-105">¿Qué es un Bus de servicio empresarial?</span><span class="sxs-lookup"><span data-stu-id="9ebde-105">What Is an Enterprise Service Bus?</span></span>  
 <span data-ttu-id="9ebde-106">El término que bus de servicio empresarial se usa ampliamente en el contexto de la implementación de una infraestructura para habilitar la arquitectura orientada a servicios (SOA).</span><span class="sxs-lookup"><span data-stu-id="9ebde-106">The term Enterprise Service Bus is widely used in the context of implementing an infrastructure for enabling Service-Oriented Architecture (SOA).</span></span> <span data-ttu-id="9ebde-107">Sin embargo, la experiencia real con la implementación de soluciones SOA ha demostrado que ESB es solo uno de muchos componentes necesarios para crear una infraestructura de orientada a servicios (SOI) completa.</span><span class="sxs-lookup"><span data-stu-id="9ebde-107">However, real-world experience with the deployment of SOA solutions has demonstrated that an ESB is only one of many components required to build a comprehensive Service-Oriented Infrastructure (SOI).</span></span> <span data-ttu-id="9ebde-108">El término "ESB" ha evolucionado en un número de direcciones, su definición varía con la interpretación de los proveedores de plataforma de integración y ESB individuales y con los requisitos de las iniciativas SOA.</span><span class="sxs-lookup"><span data-stu-id="9ebde-108">The term "ESB" has evolved in a number of directions—its definition varies with the interpretation of individual ESB and integration platform vendors and with the requirements of particular SOA initiatives.</span></span>  
  
 <span data-ttu-id="9ebde-109">En función de la experiencia que Microsoft ha obtenido de muchas implementaciones SOI correcta del mundo real, Microsoft considera que un Bus de servicio de empresa sea una colección de patrones de arquitectura basada en tradicional Enterprise Application Integration (EAI), middleware orientado a mensajes, servicios Web, interoperabilidad de .NET y Java, integración de sistemas de host y la interoperabilidad con registros de servicio y repositorios de activos.</span><span class="sxs-lookup"><span data-stu-id="9ebde-109">Based on the experience Microsoft has gathered from many successful real-world SOI implementations, Microsoft considers an Enterprise Service Bus to be a collection of architectural patterns based on traditional Enterprise Application Integration (EAI), message-oriented middleware, Web services, .NET and Java interoperability, host system integration, and interoperability with service registries and asset repositories.</span></span> <span data-ttu-id="9ebde-110">Figura 1 muestra la arquitectura de un Bus de servicio de la empresa.</span><span class="sxs-lookup"><span data-stu-id="9ebde-110">Figure 1 illustrates the architecture of an Enterprise Service Bus.</span></span>  
  
 <span data-ttu-id="9ebde-111">![Información general de ESB](../esb-toolkit/media/esboverview.gif "ESBOverview")</span><span class="sxs-lookup"><span data-stu-id="9ebde-111">![ESB Overview](../esb-toolkit/media/esboverview.gif "ESBOverview")</span></span>  
  
 <span data-ttu-id="9ebde-112">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="9ebde-112">**Figure 1**</span></span>  
  
 <span data-ttu-id="9ebde-113">**Una representación de alto nivel de la conectividad de la arquitectura de Bus de servicio empresarial**</span><span class="sxs-lookup"><span data-stu-id="9ebde-113">**A high-level representation of the connectivity provided by the Enterprise Service Bus architecture**</span></span>  

<!---  Old text with old links
## The Industry View of ESB  
 There are many sources of information about ESB design, architecture, infrastructure, and implementation available from industry suppliers, system integrators, and independent sources.  
-->
<!---    
 IBM defines ESB as a system that "...enables a business to make use of a comprehensive, flexible, and consistent approach to integration while also reducing the complexity of the applications being integrated. Due to the complex and varying nature of business needs, ESB is an evolutional progression that unifies message oriented, event driven and service oriented approaches for integrating applications and service." IBM describes the advantages as "...greater reuse of IT assets by separating application logics and integration tasks, so you can reduce the number, size, and complexity of integration interfaces," and the ability to "...add or change services with minimal interruption to existing IT environment; reduce cost and risk involved as business changes and new opportunities arise." For more information, see [WebSphere software](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958))on the IBM Web site.  
-->
<!---    Old text with old links
 Sonic Solutions provide a comprehensive examination of ESB, discussing the principle aspects, and the IT and business benefits. They describe the requirement for ESB: "To integrate old and new, service-oriented architecture (SOA) needs an infrastructure that can connect any IT resource, whatever its technology or wherever it is deployed." For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) on the Sonic Solutions Web site.  
-->
<!---    Old text with old links
 TIBCO Software define ESB as "...a standards-based communication layer in a service- oriented architecture (SOA) that enables services to be used across multiple communication protocols [to] simplify service deployment and management, and promote service reuse in a heterogeneous environment." They suggest, in order to provide these capabilities, ESBs "...support both open standards and proprietary technologies, including Web services and UDDI-based registries to discover and publish services, Java Message Service (JMS) and other widely deployed messaging protocols, standards-based (XML) transformations, and basic message routing." For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) on the TIBCO Web site.  
-->
<!---    Old text with old links
 In the description of his book, Enterprise Service Bus, author David Chappell states that "Rather than conform to the hub-and-spoke architecture of traditional enterprise application integration products, ESB provides a highly distributed approach to integration." He adds "...with unique capabilities that allow individual departments or business units to build out their integration projects in incremental, digestible chunks, maintaining their own local control and autonomy, while still being able to connect together each integration project into a larger, more global integration fabric, or grid." For more information, see Enterprise Service Bus by David Chappell:  
-->
<!---    Old text with old links
-   Chappell, David. Enterprise Service Bus. Sebastopol, CA: O'Reilly Media, Inc. 2004.  
-->

  
## <a name="the-biztalk-esb-toolkit"></a><span data-ttu-id="9ebde-114">El Kit de herramientas de ESB de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9ebde-114">The BizTalk ESB Toolkit</span></span>
 <span data-ttu-id="9ebde-115">Esta documentación, como un todo, introduce los arquitectos y programadores a conceptos de arquitectura de ESB como los dirigidos por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]y se explica la funcionalidad de los componentes ESB a través de un conjunto de casos de uso ESB aceptados.</span><span class="sxs-lookup"><span data-stu-id="9ebde-115">This documentation, as a whole, introduces architects and developers to ESB architectural concepts as addressed by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and explains the functionality of the ESB components through a set of commonly accepted ESB use cases.</span></span>  
  
 <span data-ttu-id="9ebde-116">Esta sección proporciona una introducción a la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]e incluye los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ebde-116">This section provides an introduction to the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and includes the following topics:</span></span>  
  
-   [<span data-ttu-id="9ebde-117">Información general sobre el kit de herramientas de BizTalk ESB</span><span class="sxs-lookup"><span data-stu-id="9ebde-117">Overview of the BizTalk ESB Toolkit</span></span>](../esb-toolkit/overview-of-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="9ebde-118">Contenido del kit de herramientas de BizTalk ESB</span><span class="sxs-lookup"><span data-stu-id="9ebde-118">Contents of the BizTalk ESB Toolkit</span></span>](../esb-toolkit/contents-of-the-biztalk-esb-toolkit.md)  
  
 <span data-ttu-id="9ebde-119">Esta documentación también incluye las siguientes secciones de tema:</span><span class="sxs-lookup"><span data-stu-id="9ebde-119">This documentation also includes the following topic sections:</span></span>  
  
-   [<span data-ttu-id="9ebde-120">Introducción al kit de herramientas de BizTalk ESB</span><span class="sxs-lookup"><span data-stu-id="9ebde-120">Getting Started with the BizTalk ESB Toolkit</span></span>](../esb-toolkit/getting-started-with-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="9ebde-121">Escenarios y tareas de desarrollo clave</span><span class="sxs-lookup"><span data-stu-id="9ebde-121">Key Scenarios and Development Tasks</span></span>](../esb-toolkit/key-scenarios-and-development-tasks.md)  
  
-   [<span data-ttu-id="9ebde-122">Creación de itinerarios mediante el Diseñador de itinerarios</span><span class="sxs-lookup"><span data-stu-id="9ebde-122">Creating Itineraries Using Itinerary Designer</span></span>](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)  
  
-   [<span data-ttu-id="9ebde-123">Aplicaciones de ejemplo del kit de herramientas de BizTalk ESB</span><span class="sxs-lookup"><span data-stu-id="9ebde-123">BizTalk ESB Toolkit Sample Applications</span></span>](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)  
  
-   [<span data-ttu-id="9ebde-124">Modificación y extensión del kit de herramientas de BizTalk ESB</span><span class="sxs-lookup"><span data-stu-id="9ebde-124">Modifying and Extending the BizTalk ESB Toolkit</span></span>](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="9ebde-125">Administración con el kit de herramientas de BizTalk ESB</span><span class="sxs-lookup"><span data-stu-id="9ebde-125">Administration with the BizTalk ESB Toolkit</span></span>](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="9ebde-126">Integración de gobierno de SOA</span><span class="sxs-lookup"><span data-stu-id="9ebde-126">SOA Governance Integration</span></span>](../esb-toolkit/soa-governance-integration.md)  
  
-   [<span data-ttu-id="9ebde-127">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="9ebde-127">Troubleshooting</span></span>](../esb-toolkit/troubleshooting-the-biztalk-esb-toolkit.md)