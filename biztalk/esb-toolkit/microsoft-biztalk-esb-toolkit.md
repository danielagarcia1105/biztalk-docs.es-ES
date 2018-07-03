---
title: Kit de herramientas de Microsoft BizTalk ESB | Microsoft Docs
description: Introducción, escenarios comunes y los componentes del Kit de herramientas ESB en BizTalk Server
caps.latest.revision: 14
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ffaebc-7e33-4de8-8e94-109cd5d16ca0
ms.author: mandia
ms.openlocfilehash: f425c02e8f869952658f93185c78474e58df304b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023402"
---
# <a name="microsoft-biztalk-esb-toolkit"></a>Kit de herramientas de Microsoft BizTalk ESB
![Logotipo del Kit de herramientas de BizTalk ESB](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")  
  
## <a name="summary"></a>Resumen  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] usa [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] para admitir una arquitectura de mensajería ligeramente acoplada. BizTalk Server incluye un eficaz mecanismo de publicación o suscripción para aplicaciones de mensajería que funciona al crear y completar suscripciones, lo que proporciona una plataforma escalable y de gran eficacia para aplicaciones de arquitectura orientada a servicios (SOA).  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía la funcionalidad de BizTalk Server para proporcionar una gama de nuevas capacidades sobre la creación de aplicaciones robustas, conectadas y orientada a servicios que incorporan la invocación del servicio basado en itinerarios para un servicio ligero composición, resolución dinámica de los puntos de conexión y mapas, servicio Web y WS-* integración, administración de errores y reporting e integración con soluciones de gobierno de SOA de terceros.  
  
## <a name="overview"></a>Información general  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona una guía de arquitectura, patrones y una colección de componentes de BizTalk Server y .NET Framework para simplificar el desarrollo de un Bus de servicio empresarial (ESB) en la plataforma de Microsoft y para permitir que los clientes de Microsoft ampliar sus propias soluciones de mensajería e integración.  
  
## <a name="common-scenarios"></a>Escenarios habituales  
 El término bus de servicios de empresa (ESB) se usa ampliamente en el contexto de la implementación de una infraestructura para habilitar una arquitectura orientada al servicio (SOA). Sin embargo, la experiencia real con la implementación de SOA ha demostrado que ESB solo es uno de los varios bloques de generación que conforman una infraestructura orientada al servicio (SOI) completa. El término ESB se ha transformado en una gran variedad de direcciones diferentes y su definición depende de la interpretación de cada ESB concreto, de los proveedores de la plataforma de integración y de los requisitos de las iniciativas SOA específicas.  
  
 Según la experiencia que Microsoft ha obtenido de varias implementaciones SOI reales de éxito, puede pensar en un ESB como un conjunto de patrones de arquitectura basados en la integración de aplicaciones empresariales (EAI) tradicionales, middleware orientado a mensajes, servicios web, interoperabilidad de .NET y Java, integración de sistema host e interoperabilidad con registros de servicio y repositorios de activos.  
  
 Figura 1 muestra una visión general del tipo de interconectividad que puede proporcionar una arquitectura ESB.  
  
 ![Información general de ESB](../esb-toolkit/media/esboverview.gif "ESBOverview")  
  
 **Figura 1**  
  
 **Un ejemplo de alto nivel de la conectividad proporciona la arquitectura de Service Bus empresarial**  
  
## <a name="audience-requirements"></a>Requisitos del público  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] está destinada a desarrolladores que crean soluciones de Microsoft BizTalk Server u otras soluciones que usan el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes. Para aprovechar al máximo la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], los desarrolladores deben poseer conocimientos y experiencias con lo siguiente:  

- [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

- [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]
  
- Técnicas de desarrollo de Microsoft. NET, incluido el desarrollo de servicios web de ASP.NET y componentes de .NET Framework  
  
## <a name="design-goals"></a>Objetivos de diseño  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consta de una serie de interoperación de los componentes que admiten e implementan un entorno de mensajería con acoplamiento flexible que resulta más fácil crear aplicaciones empresariales basadas en mensajes. Los servicios y componentes se dividen de forma natural en las siguientes siete categorías:  
  
- **Servicios Web** : estos exponen servicios internos, como el procesamiento de itinerarios, administración de excepciones, la resolución de extremos y asignaciones, las operaciones de BizTalk Server y transformación de mensajes.  
  
- **Servicios de itinerario** : los servicios basados en mensajería y orquestación para realizar el enrutamiento basado en itinerarios para [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. Puede crear servicios personalizados para el enrutamiento basado en itinerarios.  
  
- **Itinerarios con rampas.** Estos recepción los mensajes externos, adjuntar el itinerario adecuado para cada mensaje y realizan el procesamiento de itinerarios; usan el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y el marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y los metadatos.  
  
- **Con rampas** : estos recibirán los mensajes externos en una variedad de formatos y los transportes, como HTTP, JMS, WMQ, FTP, archivo sin formato y XML. Son típicos de BizTalk Server ubicaciones de recepción que, opcionalmente, use el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes de canalización de interoperabilidad y la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y el marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y los metadatos.  
  
- **Rampas** : estos implementan puertos de envío para la entrega de mensajes con formatos y los transportes como SOAP, WCF, JMS, WMQ, FTP, HTTP, archivo sin formato, XML o cualquier otros formatos personalizados. Son puertos de envío dinámicos típicos de BizTalk Server que se enlace directo al cuadro de mensaje y que, opcionalmente, use el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes de canalización de interoperabilidad y la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y resolución y los metadatos.  
  
- **Marco de administración de excepciones** : Esto incluye la excepción del servicio Web, la API de administración de excepciones y los componentes que enriquecen, procesar y pasar los detalles de la excepción en el Portal de administración de ESB.  
  
- **Portal de administración de ESB** : se trata del registro de aprovisionamiento, mediación de excepción, notificación de alerta y análisis.  
  
  Muchos de estos componentes y servicios dependen de las características implementadas por [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], como los motores de orquestación, transformación y las reglas de negocios y la base de datos de cuadro de mensaje. Figura 2 muestra una vista esquemática de las categorías; los componentes y servicios que se producen normalmente dentro de cada categoría; y los componentes principales del sistema de BizTalk Server utilizados por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
  ![Arquitectura ESB](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
  **Figura 2**  
  
  **La arquitectura y los componentes de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>Funcionamiento del kit de herramientas de BizTalk ESB  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] acepta mensajes de entrada y trabaja en ellos, quizás (pero no siempre) mediante la realización de procesos como la transformación, entrega o cualquier otro proceso personalizado definido. Para especificar las operaciones requeridas, los componentes de procesamiento principales requieren que un mensaje contenga instrucciones o metadatos asociados que definan los procesos que se deben aplicar y las tareas que se deben ejecutar con el contenido del mensaje.  
  
 Este enfoque proporciona un acoplamiento entre servicios; Esto significa que ESB no requiere conocimiento previo del procesamiento específico para cada mensaje. Solo necesita saber el intervalo posible de procesos y cómo aplicar cada proceso. La amplia variedad de opciones para especificar los procesos disponibles y la asignación entre los procesos y las instrucciones dentro de los mensajes proporciona un mecanismo flexible para configurar y ajustar el comportamiento, sin requerir cambios en el código ni la nueva implementación de componentes.  
  
## <a name="in-this-section"></a>En esta sección

- [Instalar y configurar el Kit de herramientas de Microsoft BizTalk ESB](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)

- [Introducción al kit de herramientas de BizTalk ESB](introduction-to-the-biztalk-esb-toolkit.md)

- [Introducción y entender el Kit de herramientas de ESB de BizTalk](getting-started-with-the-biztalk-esb-toolkit.md)

- [Escenarios clave y las tareas de desarrollo](key-scenarios-and-development-tasks.md)

- [Creación de itinerarios mediante el Diseñador de itinerarios](creating-itineraries-using-itinerary-designer.md)

- [Aplicaciones de ejemplo del Kit de herramientas de BizTalk ESB](biztalk-esb-toolkit-sample-applications.md)

- [Modificación y extensión del Kit de herramientas de ESB de BizTalk](modifying-and-extending-the-biztalk-esb-toolkit.md)

- [Administración con el kit de herramientas de BizTalk ESB](administration-with-the-biztalk-esb-toolkit.md)

- [Integración de gobierno de SOA](soa-governance-integration.md)

- [Solución de problemas del kit de herramientas de BizTalk ESB](troubleshooting-the-biztalk-esb-toolkit.md)
  
## <a name="related-topics"></a>Temas relacionados  
  
-   [Servicio de BizTalk orientada a soluciones](../core/service-oriented-solution.md)

- [Uso de servicios Web con BizTalk Server](../core/using-web-services.md)  