---
title: "Patrones de transformación de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aef41642-d33b-4878-be65-ef336530647f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: badfb450b51aebbdf81b2beccdeac98fc549bcb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-transformation-patterns"></a>Patrones de transformación de mensajes
Patrones de transformación de mensajes definen instrucciones comprobadas para transformar los mensajes para su procesamiento adicional o para que coincida con el formato del documento esperado del servicio al que se enviará el mensaje. Un mensaje puede requerir transformación porque la estructura del mensaje recibido no es en el estándar esperado o porque el mensaje se debe convertir de un formato no estándar a XML.  
  
## <a name="message-translator"></a>Traductor de mensajes  
 El patrón de traductor de mensajes define una solución para la comunicación entre sistemas que usan formatos de datos incompatibles. Por ejemplo, una aplicación cliente puede enviar un mensaje de solicitud de archivo sin formato que se debe convertir a XML antes de que puede producirse un procesamiento adicional. Para obtener una descripción detallada de este patrón, vea [traductor de mensajes](http://go.microsoft.com/fwlink/?LinkId=186845) ([http://go.microsoft.com/fwlink/?LinkId=186845](http://go.microsoft.com/fwlink/?LinkId=186845)) en el sitio de patrones de integración empresarial.  
  
 La implementación de este patrón en el Diseñador de itinerario es una combinación de los [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] servicios de transformación y un solucionador único. El servicio de transformación itinerarios es responsable de la transformación de un mensaje con propiedades de la resolución que definen los artefactos necesarios para la transformación. La implementación de la resolución es responsable de proporcionar la configuración de transformación, que puede definir de forma estática o dinámica, dependiendo de la configuración de la resolución.  
  
 Para una implementación de ejemplo del patrón de traductor de mensajes, vea los siguientes recursos:  
  
-   [Instalar y ejecutar el ejemplo en rampa itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [Cómo: transformar un mensaje y una ruta a un extremo de servicio mediante un patrón de intercambio de mensajes de solicitud y respuesta](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
## <a name="normalizer"></a>Normalizador  
 El patrón de normalizador es una extensión del patrón de transformación de datos modelo. Este patrón define una solución en la que son semánticamente equivalentes mensajes procedentes de varios orígenes, pero los mensajes lleguen en formatos diferentes. Para obtener una descripción detallada de este patrón, vea [normalizador](http://go.microsoft.com/fwlink/?LinkId=186847) ([http://go.microsoft.com/fwlink/?LinkId=186847](http://go.microsoft.com/fwlink/?LinkId=186847)) en el sitio de patrones de integración empresarial.  
  
 La implementación de este patrón en el Diseñador de itinerario es una combinación de los [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] servicios de transformación y un solucionador único. El servicio de transformación itinerarios es responsable de la transformación de un mensaje con propiedades de la resolución que definen los artefactos necesarios para la transformación. La implementación de la resolución es responsable de resolver dinámicamente la asignación de Microsoft BizTalk adecuada para un tipo de mensaje especificado.  
  
 Para una implementación de ejemplo del patrón normalizador, consulte el [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).  
  
## <a name="content-enricher"></a>Enricher contenido  
 El modelo de contenido Enricher define una solución en el que un mensaje recibido no puede incluir todos los datos necesarios para que el sistema de destino procesar correctamente el mensaje. Por ejemplo, el servicio de envío puede incluir un código postal sin un código de estado de redundancia, pero el servicio de recepción espera un mensaje que incluye un código de estado y un código postal; datos adicionales son necesarios para que el servicio de recepción pueda procesar el mensaje recibido. Para obtener una descripción detallada de este patrón, vea [Enricher contenido](http://go.microsoft.com/fwlink/?LinkId=186848) ([http://go.microsoft.com/fwlink/?LinkId=186848](http://go.microsoft.com/fwlink/?LinkId=186848)) en el sitio de patrones de integración empresarial.  
  
 Para una implementación de ejemplo del patrón Enricher contenido, consulte la [instalar y ejecutar el ejemplo de enriquecimiento de mensajes](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md) aplicación.