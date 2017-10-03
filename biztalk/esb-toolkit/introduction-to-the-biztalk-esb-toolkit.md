---
title: "Introducción al Kit de herramientas de ESB de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ESBToolkitV2.introduction
ms.assetid: 98a957b8-5855-4872-b7e7-58a2e1d6b2b8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9763e55c44fc3ea45ab93127ffae8c9c742f0dc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="introduction-to-the-biztalk-esb-toolkit"></a>Introducción al Kit de herramientas de ESB de BizTalk
Explica la arquitectura y el contenido de Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. La documentación también muestra cómo aplicar un modelo de arquitectura de Bus de servicio de empresa (ESB) para desarrollar aplicaciones empresariales que permiten flexible y seguro, y servicios reutilizables y organización rápida de los servicios existentes en el nuevo extremo procesos empresariales.  
  
## <a name="what-is-an-enterprise-service-bus"></a>¿Qué es un Bus de servicio empresarial?  
 El término que bus de servicio empresarial se usa ampliamente en el contexto de la implementación de una infraestructura para habilitar la arquitectura orientada a servicios (SOA). Sin embargo, la experiencia real con la implementación de soluciones SOA ha demostrado que ESB es solo uno de muchos componentes necesarios para crear una infraestructura de orientada a servicios (SOI) completa. El término "ESB" ha evolucionado en un número de direcciones, su definición varía con la interpretación de los proveedores de plataforma de integración y ESB individuales y con los requisitos de las iniciativas SOA.  
  
 En función de la experiencia que Microsoft ha obtenido de muchas implementaciones SOI correcta del mundo real, Microsoft considera que un Bus de servicio de empresa sea una colección de patrones de arquitectura basada en tradicional Enterprise Application Integration (EAI), middleware orientado a mensajes, servicios Web, interoperabilidad de .NET y Java, integración de sistemas de host y la interoperabilidad con registros de servicio y repositorios de activos. Figura 1 muestra la arquitectura de un Bus de servicio de la empresa.  
  
 ![Información general de ESB](../esb-toolkit/media/esboverview.gif "ESBOverview")  
  
 **Figura 1**  
  
 **Una representación de alto nivel de la conectividad de la arquitectura de Bus de servicio empresarial**  

\<!---Texto anterior con vínculos antiguos
## <a name="the-industry-view-of-esb"></a>La vista de la industria de ESB  
 Existen numerosas fuentes de información sobre el diseño ESB, arquitectura, infraestructura e implementación de proveedores del sector, integradores de sistemas y orígenes independientes.  
-->
\<!---    
 IBM define ESB como un sistema que ".. .enables una empresa para hacer uso de un amplio, flexible y un nuevo enfoque coherente a la integración además de reducir la complejidad de las aplicaciones se integra. Debido a la naturaleza compleja y variada necesidades empresariales, ESB es una progresión evolutional que unifica orientado a mensajes, orientada a eventos y el servicio orientada a servicios enfoques para la integración de aplicaciones y servicios." IBM describe las ventajas como ".. .mayores reutilización de activos de TI mediante la separación lógica de aplicación y las tareas de integración, por lo que puede reducir el número, el tamaño y la complejidad de las interfaces de integración,"y la capacidad de".. *.Add o cambiar servicios con mínima interrupción del entorno de TI existente; reducir el costo y riesgo que conlleva como los cambios del negocio y surgen nuevas oportunidades". Para obtener más información, consulte [WebSphere software](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958)) en el sitio IBM Web.  
-->
\<!---Texto anterior con vínculos antiguos Sonic Solutions proporcionan un examen exhaustivo de ESB, hablar sobre los aspectos de la entidad de seguridad y la TI y beneficios para el negocio. Se describen los requisitos para ESB: "Para integrar antiguos y nuevos, arquitectura orientada a servicios (SOA) necesita una infraestructura que se puede conectar a los recursos de TI, cualquier su tecnología de o, donde se implementa". Para obtener más información, consulte [Bus de servicio de empresa (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) en el sitio Web de Sonic Solutions.  
-->
\<!---Texto anterior con vínculos antiguos TIBCO Software definir ESB como ".. .una capa de comunicación basada en estándares en una arquitectura de service-oriented (SOA) que permite que los servicios que se usará en varios protocolos de comunicación [a] para simplificar la implementación de servicio y administración y promover la reutilización de servicio en un entorno heterogéneo. " Sugieren, con el fin de proporcionar estas capacidades, ESB ".. .support ambos estándares abiertos y tecnologías patentadas, incluidos los servicios Web y los registros basados en UDDI para detectar y publicar servicios, Java Message Service (JMS) y otros ampliamente implementada protocolos de mensajería, basada en estándares (XML) transformaciones y enrutamiento de mensajes básicos." Para obtener más información, consulte [Bus de servicio de empresa (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) en el sitio Web de TIBCO.  
-->
\<!---Texto anterior con vínculos anteriores en la descripción de su libro, Bus de servicio empresarial, autor David Chappell indica que "en su lugar que se ajusta a la arquitectura de concentrador y radio de productos de integración de aplicaciones empresariales tradicionales, ESB proporciona una alta enfoque distribuida para la integración." Agrega ".. with capacidades únicas que permiten a los departamentos individuales o unidades de negocio para crear fuera de sus proyectos de integración en fragmentos por incremental, que se mantiene su propio control local y la autonomía, mientras todavía se puede conectar entre sí cada proyecto de integración en una mayor, más global tejido de integración o una cuadrícula." Para obtener más información, vea el Bus de servicio empresarial David Chappell:  
-->
\<!---Texto anterior con vínculos antiguos
-   Chappell, David. Bus de servicio empresarial. Sebastopol, CA: O ' Reilly Media, Inc. 2004.  
-->

  
## <a name="the-biztalk-esb-toolkit"></a>El Kit de herramientas de ESB de BizTalk
 Esta documentación, como un todo, introduce los arquitectos y programadores a conceptos de arquitectura de ESB como los dirigidos por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]y se explica la funcionalidad de los componentes ESB a través de un conjunto de casos de uso ESB aceptados.  
  
 Esta sección proporciona una introducción a la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]e incluye los temas siguientes:  
  
-   [Información general sobre el Kit de herramientas de ESB de BizTalk](../esb-toolkit/overview-of-the-biztalk-esb-toolkit.md)  
  
-   [Contenido del Kit de herramientas de ESB de BizTalk](../esb-toolkit/contents-of-the-biztalk-esb-toolkit.md)  
  
 Esta documentación también incluye las siguientes secciones de tema:  
  
-   [Cómo empezar a usar el Kit de herramientas de ESB de BizTalk](../esb-toolkit/getting-started-with-the-biztalk-esb-toolkit.md)  
  
-   [Escenarios clave y las tareas de desarrollo](../esb-toolkit/key-scenarios-and-development-tasks.md)  
  
-   [Crear itinerarios mediante el Diseñador de itinerarios](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)  
  
-   [Aplicaciones de ejemplo de Kit de herramientas de ESB de BizTalk](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)  
  
-   [Modificar y extender el Kit de herramientas de ESB de BizTalk](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)  
  
-   [Administración con el Kit de herramientas de ESB de BizTalk](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)  
  
-   [Integración de regulación de SOA](../esb-toolkit/soa-governance-integration.md)  
  
-   [Solucionar problemas](../esb-toolkit/troubleshooting-the-biztalk-esb-toolkit.md)