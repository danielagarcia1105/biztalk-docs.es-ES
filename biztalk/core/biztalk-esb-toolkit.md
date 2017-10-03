---
title: Kit de herramientas ESB de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08035518-17ad-44d2-ab06-90d725c95ced
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 535fd99ee5c1b9f9c25dd49e2a2441acb855c78a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-esb-toolkit"></a>Kit de herramientas de BizTalk ESB
El kit de herramientas de Microsoft BizTalk ESB usa Microsoft BizTalk Server para admitir una arquitectura de mensajería ligeramente acoplada. BizTalk Server incluye un eficaz mecanismo de publicación o suscripción para aplicaciones de mensajería que funciona al crear y completar suscripciones, lo que proporciona una plataforma escalable y de gran eficacia para aplicaciones de arquitectura orientada a servicios (SOA). El kit de herramientas de BizTalk ESB amplía la funcionalidad de BizTalk Server para proporcionar una variedad de capacidades nuevas centradas en la creación de robustas aplicaciones orientadas a servicios y conectadas que incorporen una invocación de servicios basada en itinerarios para la composición de servicios ligeros, la resolución dinámica de extremos y asignaciones, servicio web e integración con WS-*, administración e informes de errores, así como integración con soluciones de control SOA de terceros.  
  
## <a name="overview"></a>Información general  
 El kit de herramientas de BizTalk ESB proporciona una guía de arquitectura, patrones y un conjunto de componentes de BizTalk Server y.NET Framework para simplificar el desarrollo de un bus de servicios de empresa (ESB) en la plataforma de Microsoft y para permitir a los clientes de Microsoft ampliar sus propias soluciones de mensajería e integración.  
  
## <a name="common-scenarios"></a>Escenarios habituales  
 El término bus de servicios de empresa (ESB) se usa ampliamente en el contexto de la implementación de una infraestructura para habilitar una arquitectura orientada al servicio (SOA). Sin embargo, la experiencia real con la implementación de SOA ha demostrado que ESB solo es uno de los varios bloques de generación que conforman una infraestructura orientada al servicio (SOI) completa. El término ESB se ha transformado en una gran variedad de direcciones diferentes y su definición depende de la interpretación de cada ESB concreto, de los proveedores de la plataforma de integración y de los requisitos de las iniciativas SOA específicas. Según la experiencia que Microsoft ha obtenido de varias implementaciones SOI reales de éxito, puede pensar en un ESB como un conjunto de patrones de arquitectura basados en la integración de aplicaciones empresariales (EAI) tradicionales, middleware orientado a mensajes, servicios web, interoperabilidad de .NET y Java, integración de sistema host e interoperabilidad con registros de servicio y repositorios de activos.  
  
## <a name="audience-requirements"></a>Requisitos del público  
 El kit de herramientas de BizTalk ESB está diseñado para programadores que crean soluciones de Microsoft BizTalk Server u otras soluciones que usen los componentes del kit de herramientas de BizTalk ESB. Para sacar el máximo provecho del kit de herramientas de BizTalk ESB, los programadores deben tener conocimientos y experiencia en el uso de los elementos siguientes:  
  
1.  Microsoft BizTalk Server  
  
2.  Microsoft Visual Studio  
  
3.  Técnicas de desarrollo de Microsoft. NET, incluido el desarrollo de servicios web de ASP.NET y componentes de .NET Framework  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>Funcionamiento del kit de herramientas de BizTalk ESB  
 El kit de herramientas de BizTalk ESB acepta mensajes de entrada y trabaja en ellos, quizás (pero no siempre) mediante la ejecución de procesos, tales como transformación, entrega o cualquier otro proceso personalizado definido. Para especificar las operaciones requeridas, los componentes de procesamiento principales requieren que un mensaje contenga instrucciones o metadatos asociados que definan los procesos que se deben aplicar y las tareas que se deben ejecutar con el contenido del mensaje.   
Este método proporciona un acoplamiento entre los servicios; Esto significa que ESB no requiere el conocimiento previo del procesamiento específico para cada mensaje. Solo necesita saber el intervalo posible de procesos y cómo aplicar cada proceso. La amplia variedad de opciones para especificar los procesos disponibles y la asignación entre los procesos y las instrucciones dentro de los mensajes proporciona un mecanismo flexible para configurar y ajustar el comportamiento, sin requerir cambios en el código ni la nueva implementación de componentes.  
  
## <a name="getting-started"></a>Introducción  
 Después de instalar el Kit de herramientas de ESB de BizTalk, debe leer el tema "Introducción" en la [documentación del Kit de herramientas de ESB de BizTalk](http://go.microsoft.com/fwlink/?LinkId=193578) para comprender la arquitectura, el flujo de mensajes y los componentes principales del Kit de herramientas de ESB de BizTalk. También debe instalar y ejecutar los ejemplos incluidos con el kit de herramientas de BizTalk ESB, en los que se muestran los casos de uso común descritos en el tema "Introducción" y otros escenarios de mensajería. Este método permitirá comprender rápidamente cómo funciona el kit de herramientas de BizTalk ESB y cómo se pueden aprovechar sus características en las aplicaciones SOA propias.  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de servicios empresariales de BizTalk](http://go.microsoft.com/fwlink/?LinkId=193577)   
 [Solución orientada a servicios](../core/service-oriented-solution.md)   
 [Con los servicios Web](../core/using-web-services.md)