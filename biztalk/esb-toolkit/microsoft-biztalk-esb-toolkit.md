---
title: Kit de herramientas de Microsoft BizTalk ESB | Documentos de Microsoft
description: Introducción, los escenarios comunes y los componentes del Kit de herramientas de ESB en BizTalk Server
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
ms.openlocfilehash: 1763ed4bb7f090b91565c3a5f5f480d2c081b48c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297036"
---
# <a name="microsoft-biztalk-esb-toolkit"></a>Kit de herramientas de Microsoft BizTalk ESB
![Logotipo del Kit de herramientas de BizTalk ESB](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")  
  
## <a name="summary"></a>Resumen  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] utiliza [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] para admitir una arquitectura de mensajería con acoplamiento flexible. BizTalk Server incluye un eficaz mecanismo de publicación o suscripción para aplicaciones de mensajería que funciona al crear y completar suscripciones, lo que proporciona una plataforma escalable y de gran eficacia para aplicaciones de arquitectura orientada a servicios (SOA).  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía la funcionalidad de BizTalk Server proporciona una gama de nuevas capacidades que se centra en crear aplicaciones sólidas, conectadas, orientadas a servicios que incorporan la invocación del servicio basado en itinerario de servicio ligera composición, resolución dinámica de extremos y asignaciones, servicio Web y WS-* integración, la administración de errores y reporting e integración con soluciones de regulación de SOA de terceros.  
  
## <a name="overview"></a>Información general  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona una guía de arquitectura, patrones y una colección de componentes de BizTalk Server y .NET Framework para simplificar el desarrollo de un Bus de servicio empresarial (ESB) en la plataforma de Microsoft y para permitir que los clientes de Microsoft extender sus propias soluciones de mensajería e integración.  
  
## <a name="common-scenarios"></a>Escenarios habituales  
 El término bus de servicios de empresa (ESB) se usa ampliamente en el contexto de la implementación de una infraestructura para habilitar una arquitectura orientada al servicio (SOA). Sin embargo, la experiencia real con la implementación de SOA ha demostrado que ESB solo es uno de los varios bloques de generación que conforman una infraestructura orientada al servicio (SOI) completa. El término ESB se ha transformado en una gran variedad de direcciones diferentes y su definición depende de la interpretación de cada ESB concreto, de los proveedores de la plataforma de integración y de los requisitos de las iniciativas SOA específicas.  
  
 Según la experiencia que Microsoft ha obtenido de varias implementaciones SOI reales de éxito, puede pensar en un ESB como un conjunto de patrones de arquitectura basados en la integración de aplicaciones empresariales (EAI) tradicionales, middleware orientado a mensajes, servicios web, interoperabilidad de .NET y Java, integración de sistema host e interoperabilidad con registros de servicio y repositorios de activos.  
  
 Figura 1 muestra una vista de alto nivel del tipo de interconectividad que puede proporcionar una arquitectura ESB.  
  
 ![Información general de ESB](../esb-toolkit/media/esboverview.gif "ESBOverview")  
  
 **Figura 1**  
  
 **Un ejemplo de alto nivel de la conectividad proporciona la arquitectura de Bus de servicio empresarial**  
  
## <a name="audience-requirements"></a>Requisitos del público  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] está destinada a desarrolladores que crean soluciones de Microsoft BizTalk Server u otras soluciones que usan la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes. Para aprovechar al máximo la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], los desarrolladores deben poseer conocimientos y experiencia en el uso con lo siguiente:  

- [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

- [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]
  
-   Técnicas de desarrollo de Microsoft. NET, incluido el desarrollo de servicios web de ASP.NET y componentes de .NET Framework  
  
## <a name="design-goals"></a>Objetivos de diseño  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consta de una serie de interoperar componentes que admiten e implementan un entorno de mensajería con acoplamiento flexible que resulta más fácil crear aplicaciones empresariales basadas en mensajes. Los servicios y componentes se dividen de forma natural en las siete categorías siguientes:  
  
-   **Servicios Web** : estos exponen servicios internos como el procesamiento de itinerarios, administración de excepciones, la resolución de extremos y asignaciones, las operaciones del servidor de BizTalk y transformación de mensajes.  
  
-   **Servicios itinerarios** : se incluyen los servicios basados en la mensajería y orquestación para realizar el enrutamiento basado en itinerario para [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. Puede crear servicios personalizados para el enrutamiento de itinerario.  
  
-   **Pendientes en itinerarios.** Estos mensajes externos de recepción, adjuntar el itinerario adecuado para cada mensaje y realizan un procesamiento itinerario; usan el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y los metadatos.  
  
-   **En pendientes** : estos reciban mensajes externos en una variedad de formatos y transportes, como HTTP, JMS, wmq de ESB, FTP, archivo sin formato y XML. Son típicos BizTalk Server ubicaciones de recepción que, opcionalmente, use la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes de canalización de interoperabilidad y la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y los metadatos.  
  
-   **Desactivar pendientes** : estos implementan puertos de envío para la entrega de mensajes con formatos y transportes, como SOAP, WCF, JMS, wmq de ESB, FTP, HTTP, archivo sin formato, XML o cualquier otros formatos personalizados. Son puertos de envío dinámicos típicos de BizTalk Server que se enlace directo en el cuadro de mensajes y que, opcionalmente, use la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] componentes de canalización de interoperabilidad y la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y marco de proveedores de adaptador para la resolución dinámica de los puntos de conexión y los metadatos.  
  
-   **Marco de administración de excepciones** : se trata de la excepción del servicio Web, la API de administración de la excepción, y los componentes que enriquecen, procesar y pasar los detalles de la excepción en el Portal de administración de ESB.  
  
-   **Portal de administración de ESB** : se trata del registro de aprovisionamiento, mediación de excepción, notificación de alertas y análisis.  
  
 Muchos de estos componentes y servicios dependen de las características implementadas por [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], por ejemplo, los motores de orquestación, transformación y las reglas de negocios y la base de datos de cuadro de mensaje. La figura 2 muestra una vista esquemática de las categorías; los componentes y servicios que normalmente se producen dentro de cada categoría; y los componentes principales del sistema de BizTalk Server utilizados por el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
 ![Arquitectura ESB](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
 **Figura 2**  
  
 **La arquitectura y los componentes de la[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>Funcionamiento del kit de herramientas de BizTalk ESB  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] acepta mensajes de entrada y trabaja en ellos, quizás (pero no siempre) mediante la ejecución de procesos como la transformación, entrega o cualquier otro proceso personalizado definido. Para especificar las operaciones requeridas, los componentes de procesamiento principales requieren que un mensaje contenga instrucciones o metadatos asociados que definan los procesos que se deben aplicar y las tareas que se deben ejecutar con el contenido del mensaje.  
  
 Este método proporciona un acoplamiento entre los servicios; Esto significa que ESB no requiere el conocimiento previo del procesamiento específico para cada mensaje. Solo necesita saber el intervalo posible de procesos y cómo aplicar cada proceso. La amplia variedad de opciones para especificar los procesos disponibles y la asignación entre los procesos y las instrucciones dentro de los mensajes proporciona un mecanismo flexible para configurar y ajustar el comportamiento, sin requerir cambios en el código ni la nueva implementación de componentes.  
  
## <a name="in-this-section"></a>En esta sección

- [Instalar y configurar el Kit de herramientas de Microsoft BizTalk ESB](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)

- [Introducción al Kit de herramientas de ESB de BizTalk](introduction-to-the-biztalk-esb-toolkit.md)

- [Introducción y entender el Kit de herramientas de ESB de BizTalk](getting-started-with-the-biztalk-esb-toolkit.md)

- [Escenarios clave y las tareas de desarrollo](key-scenarios-and-development-tasks.md)

- [Crear itinerarios mediante el Diseñador de itinerarios](creating-itineraries-using-itinerary-designer.md)

- [Aplicaciones de ejemplo del Kit de herramientas de ESB de BizTalk](biztalk-esb-toolkit-sample-applications.md)

- [Modificar y extender el Kit de herramientas de ESB de BizTalk](modifying-and-extending-the-biztalk-esb-toolkit.md)

- [Administración con el Kit de herramientas de ESB de BizTalk](administration-with-the-biztalk-esb-toolkit.md)

- [Integración de regulación de SOA](soa-governance-integration.md)

- [Solución de problemas del Kit de herramientas de ESB de BizTalk](troubleshooting-the-biztalk-esb-toolkit.md)
  
## <a name="related-topics"></a>Temas relacionados  
  
-   [Soluciones de orientadas a servicios de BizTalk](../core/service-oriented-solution.md)

- [Con los servicios Web con BizTalk Server](../core/using-web-services.md)  