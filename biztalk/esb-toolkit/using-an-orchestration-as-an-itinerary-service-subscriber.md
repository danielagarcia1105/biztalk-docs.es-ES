---
title: "Utilizar una orquestación como un suscriptor de servicio itinerarios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 278564f1-de9f-4fbf-8c7f-09b3e607c28b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f496884d0aed8d5f351f681ca8cfe59e05684240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a>Utilizar una orquestación como un suscriptor de servicio itinerarios
Las orquestaciones también pueden actuar como servicios itinerarios. Para participar en un itinerario, primero debe diseñar la orquestación como enlace directo; Para ello, utilice una suscripción de filtro similar a la que el puerto de envío en el tema anterior, [mediante un puerto de envío como un suscriptor de servicio de itinerario](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md). La figura 1 muestra un ejemplo de una expresión de filtro para una orquestación adecuada recoger los mensajes que cumplen las condiciones siguientes:  
  
-   **ServiceName = Microsoft.Practices.ESB.Services.Transform**  
  
-   **ServiceState = pendiente**  
  
-   **ServiceType = orquestación**  
  
 ![Orquestación](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")  
  
 **Figura 1**  
  
 **Expresión de filtro de ejemplo para una orquestación que vaya a participar en un itinerario como suscriptor**  
  
 Cuando llegan los mensajes de Microsoft BizTalk Server a través de ESB en rampa, el paso de validación en la canalización ESB escribe los valores de propiedad para las propiedades del filtro en las propiedades de contexto de BizTalk del mensaje entrante; Esto promueve al contexto del mensaje. El servicio itinerario siempre establece la **ServiceName** propiedad para el servicio activo actualmente en el nombre del servicio para procesar a continuación y con un **ServiceState** el valor de propiedad  **Pendiente**. Para una suscripción, debe establecer al menos los primeros tres de las siguientes propiedades:  
  
-   **ServiceName.** Este es el nombre del servicio, tal como se almacena en el itinerario ESB y puede ser cualquier nombre. El itinerario utiliza este nombre para identificar qué servicio para ejecutar.  
  
-   **ServiceState.** Este es el estado del paso actual servicio itinerarios para ejecutar. El paso de servicio actual (para procesar a continuación) siempre tendrá el valor **pendiente**, establecer cualquier ESB itinerarios componente de canalización, el componente de canalización de Selector de itinerario de ESB, o el código que llama el **por adelantado**  método de la API de itinerario.  
  
-   **ServiceType.** Esta propiedad define el tipo de servicio, que indica si se origina desde la orquestación o el subsistema de mensajería de BizTalk.  
  
-   **IsRequestResponse.** Esta propiedad opcional debe tener el mismo valor que el **IsRequestResponse** propiedad del servicio.