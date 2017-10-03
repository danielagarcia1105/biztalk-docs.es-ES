---
title: "Patrones de mediación de servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfda54db-75fa-4bc2-9f48-11d8b3cde65b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af76e6c123a3a273bc2e100b1008f40523762695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="service-mediation-patterns"></a>Patrones de mediación de servicio
## <a name="vetovetro"></a>UN VETO/VETRO  
 El patrón VETRO es un patrón compuesto común que combina varias acciones realizadas en un mensaje cuando se recibe. El término VETRO es el acrónimo de validación, enriquecimiento, transformación, ruta, Operate. En el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], estas acciones pueden administrarse como fases individuales en la canalización asociada con la ubicación de recepción. Para obtener más información acerca de cómo se puede implementar cada una de estas fases, vea tareas de desarrollo y escenarios clave.  
  
## <a name="request-response"></a>Solicitudes y respuestas  
 El patrón de solicitud-respuesta define una solución en la que un servicio o usuario envía una solicitud de mensaje y espera un mensaje de respuesta de vuelta desde el servicio de destino. Para obtener una descripción detallada de este patrón, vea [respuesta-solicitud](http://go.microsoft.com/fwlink/?LinkId=186849) ([http://go.microsoft.com/fwlink/?LinkId=186849](http://go.microsoft.com/fwlink/?LinkId=186849)) en el sitio de patrones de integración empresarial.  
  
 Para obtener más información sobre cómo implementar este patrón, vea los siguientes recursos:  
  
-   [Cómo: transformar un mensaje y una ruta a un extremo de servicio mediante un patrón de intercambio de mensajes de solicitud y respuesta](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
-   [Instalar y ejecutar el ejemplo en rampa itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)