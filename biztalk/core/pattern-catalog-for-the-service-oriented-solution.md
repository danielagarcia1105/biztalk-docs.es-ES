---
title: "Solución orientada a servicios de catálogo de patrones para el servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Calling Pipelines from Code pattern [service solutions]
- Recipient List pattern [service solutions]
- filters, design patterns
- Filter pattern [service solutions]
- caching, patterns [service solutions]
- Service Interface pattern [service solutions]
- Content-Based Routing pattern [service solutions]
- Inline Invocation of Back-End Processes pattern [service solutions]
- content-based routing, patterns [service solutions]
- messages, Translator pattern [service solutions]
- aggregations, patterns [service solutions]
- Translator pattern, service solutions
- Caching pattern [service solutions]
- Aggregation pattern [service solutions]
- patterns [service solutions], pattern types
- back-end processes
- services, interface pattern [service solutions]
ms.assetid: 5d8135c5-d5de-4e61-b3e8-2aa7f6de98c8
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9441ead974cdcaba66dd9d038e786a5a8c7b156e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="pattern-catalog-for-the-service-oriented-solution"></a>Catálogo de patrones para el servicio de la solución orientada a servicios
Los patrones de la solución orientada a servicios incluyen patrones de prácticas de programación específicas de BizTalk Server, así como patrones de integración de empresas de secciones anteriores. La lista de esta sección incluye ambos tipos de patrones.  
  
## <a name="pattern-types"></a>Tipos de patrón  
 Las entradas descritas en los siguientes temas explican brevemente el patrón y apuntan a otros temas que explican cómo utiliza la solución el patrón. En el caso de los patrones generales, como un filtro, se proporcionan vínculos a temas más generales.  
  
### <a name="aggregation-pattern"></a>Patrón de agregación  
 Agregación es el patrón para recibir información de varios orígenes y consolidarla en un solo mensaje. La solución orientada a servicios combina información de crédito de tres orígenes diferentes en una sola respuesta. La agregación se puede realizar de varias formas, dependiendo de la naturaleza de la solución que está escribiendo. En algunos casos, puede ser necesario esperar que lleguen todas las respuestas. En otros casos, como presupuestos de préstamos, quizá prefiera obtener una respuesta en cuanto tenga un número mínimo. La solución orientada a servicios espera hasta que tiene las tres respuestas porque requiere las tres para devolver un informe de crédito completo. Para obtener más información, consulte [traducir los patrones de la solución orientada a servicios](../core/translating-the-patterns-of-the-service-oriented-solution.md).  
  
### <a name="calling-pipelines-from-code-pattern"></a>Llamar a canalizaciones desde un patrón de código  
 Ahora puede llamar a canalizaciones desde el código y las orquestaciones. Esto permite reutilizar las canalizaciones y contribuye a mantener una orquestación desacoplada de las fases de canalización. Para obtener más información, consulte [utilizando canalizaciones desde la solución orientada a servicios](../core/using-pipelines-from-the-service-oriented-solution.md).  
  
### <a name="caching-pattern"></a>Patrón de almacenamiento en caché  
 El almacenamiento en caché es una estrategia general de almacenamiento de información en lugar de recuperarla de un almacén de datos cada vez que se requiere. La recuperación de datos de referencia o configuración del sistema de inicio de sesión único empresarial es un factor que limita la solución. La solución almacena en caché la información y actualiza la caché periódicamente. Para obtener más información, consulte [usar SSO de forma eficaz en la solución orientada a servicios](../core/using-sso-efficiently-in-the-service-oriented-solution.md). La solución Administración de procesos empresariales también almacena en caché la información de SSO, aunque utiliza un proceso ligeramente diferente. Para obtener más información, consulte [usar SSO de forma eficaz en la solución de administración de procesos empresariales](../core/using-sso-efficiently-in-the-business-process-management-solution.md).  
  
### <a name="content-based-routing-pattern"></a>Patrón de enrutamiento basado en contenido  
 En los patrones de integración de empresas, el enrutamiento basado en contenido se concibe con mayor amplitud que en BizTalk. En los patrones de integración de empresas, el enrutamiento basado en contenido determina el destinatario de un mensaje en función de alguna parte del contenido del mensaje. La solución orientada a servicios utiliza una forma muy sencilla de enrutamiento basado en contenido, una forma de decisión únicos en una orquestación envía el mensaje a uno de estos dos lugares. Para obtener más información, vea "Traducir los componentes en formas orquestación" en [traducir los patrones de la solución orientada a servicios](../core/translating-the-patterns-of-the-service-oriented-solution.md).  
  
### <a name="filter-pattern"></a>Patrón de filtro  
 El patrón de filtro selecciona mensajes que cumplen determinados criterios para el procesamiento. En BizTalk Server, el patrón de filtro casi siempre se convierte en expresión de filtro en un puerto. Para obtener más información sobre los filtros de puertos, consulte [utilizando filtros con el mensaje de forma recepción](../core/using-filters-with-the-receive-message-shape.md).  
  
### <a name="inline-invocation-of-back-end-processes-pattern"></a>Patrón de invocación en línea de procesos de servidor  
 La versión en línea de la solución utiliza invocación en línea de los procesos de servidor mediante ensamblados personalizados. Esto tiene la ventaja de mejorar notablemente el rendimiento. Sin embargo, tiene el inconveniente de acoplar firmemente la orquestación al protocolo de transporte. Para obtener más información, consulte [invocación de Back-end de inserción](../core/inlining-back-end-invocation.md).  
  
### <a name="recipient-list-pattern"></a>Patrón de lista de destinatarios  
 En un sentido abstracto, la solución orientada a servicios implementa una lista de destinatarios porque envía mensajes a tres sistemas diferentes. En términos prácticos, la aplicación implementada determina los destinatarios asignando los puertos lógicos a ubicaciones específicas. En este caso (versión en línea de la aplicación), las conexiones se crean mediante la información de configuración de SSO. Para obtener más información, consulte [traducir los patrones de la solución orientada a servicios](../core/translating-the-patterns-of-the-service-oriented-solution.md).  
  
### <a name="service-interface-pattern"></a>Patrón de interfaz de servicio  
 La solución orientada a servicios se presenta como un servicio Web, sólo una de las muchas formas en que se puede hacer un servicio. Para obtener más información acerca del uso de orquestaciones como servicios Web, consulte [uso de servicios Web](../core/using-web-services.md).  
  
### <a name="translator-pattern"></a>Patrón de traductor  
 El patrón de empresa de un traductor, es decir, la conversión de un mensaje de un formulario a otro formato, a menudo se traduce en una asignación de BizTalk Server. Para obtener información general acerca de las asignaciones de BizTalk Server, vea [crear asigna utilizando el asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md).  
  
## <a name="see-also"></a>Vea también  
 [Patrones en la solución orientada a servicios](../core/patterns-in-the-service-oriented-solution.md)