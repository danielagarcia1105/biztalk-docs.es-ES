---
title: Introducción al Kit de herramientas ESB de BizTalk | Microsoft Docs
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
ms.openlocfilehash: 5cfab980a869029d565d378aaf0f75a147403f3e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986725"
---
# <a name="introduction-to-the-biztalk-esb-toolkit"></a>Introducción al Kit de herramientas ESB de BizTalk
Explica la arquitectura y el contenido de Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. La documentación también muestra cómo aplicar un patrón de arquitectura de Bus de servicio empresarial (ESB) para desarrollar aplicaciones empresariales que permiten flexible y seguro, y servicios reutilizables y organización rápida de los servicios existentes en el nuevo extremo procesos empresariales.  

## <a name="what-is-an-enterprise-service-bus"></a>¿Qué es un Service Bus empresarial?  
 El término que bus de servicio empresarial se usa ampliamente en el contexto de implementación de una infraestructura para habilitar la arquitectura orientada a servicios (SOA). Sin embargo, la experiencia real con la implementación de soluciones SOA ha demostrado que ESB es sólo uno de muchos componentes necesarios para crear una infraestructura de orientada al servicio (SOI) completa. El término "ESB" ha evolucionado en una serie de instrucciones, su definición varía con la interpretación de los proveedores de plataformas de ESB e integración individuales y con los requisitos de las iniciativas SOA específicas.  

 En función de la experiencia de que Microsoft ha obtenido de muchas implementaciones correctas de SOI reales, Microsoft considera que un Bus de servicio empresarial sea una colección de patrones de arquitectura basada en tradicional Enterprise Application Integration (EAI), middleware orientado a mensajes, servicios Web, interoperabilidad .NET y Java, integración de sistemas de host y la interoperabilidad con registros de servicio y repositorios de activos. Figura 1 muestra la arquitectura de un Bus de servicio de la empresa.  

 ![Información general de ESB](../esb-toolkit/media/esboverview.gif "ESBOverview")  

 **Figura 1**  

 **Una representación de alto nivel de la conectividad de la arquitectura de Bus de servicio empresarial**  

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


## <a name="the-biztalk-esb-toolkit"></a>El Kit de herramientas de BizTalk ESB
 Esta documentación, como un todo, presenta los arquitectos y desarrolladores a conceptos de arquitectura de ESB según la dirección indicada por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]y se explica la funcionalidad de los componentes ESB a través de un conjunto de casos de uso comúnmente aceptados de ESB.  

 Esta sección proporciona una introducción a la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]e incluye los siguientes temas:  

- [Información general sobre el kit de herramientas de BizTalk ESB](../esb-toolkit/overview-of-the-biztalk-esb-toolkit.md)  

- [Contenido del kit de herramientas de BizTalk ESB](../esb-toolkit/contents-of-the-biztalk-esb-toolkit.md)  

  Esta documentación también incluye las siguientes secciones del tema:  

- [Introducción al kit de herramientas de BizTalk ESB](../esb-toolkit/getting-started-with-the-biztalk-esb-toolkit.md)  

- [Escenarios y tareas de desarrollo clave](../esb-toolkit/key-scenarios-and-development-tasks.md)  

- [Creación de itinerarios mediante el Diseñador de itinerarios](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)  

- [Aplicaciones de ejemplo del kit de herramientas de BizTalk ESB](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)  

- [Modificación y extensión del kit de herramientas de BizTalk ESB](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)  

- [Administración con el kit de herramientas de BizTalk ESB](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)  

- [Integración de gobierno de SOA](../esb-toolkit/soa-governance-integration.md)  

- [Solucionar problemas](../esb-toolkit/troubleshooting-the-biztalk-esb-toolkit.md)
