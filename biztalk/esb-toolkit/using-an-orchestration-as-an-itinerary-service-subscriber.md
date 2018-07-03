---
title: Uso de una orquestación como un suscriptor de servicio de itinerarios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 278564f1-de9f-4fbf-8c7f-09b3e607c28b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd787ec23e09bc420939d33c25005dd611f5fd38
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009565"
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a>Uso de una orquestación como un suscriptor de servicio de itinerarios
Las orquestaciones también pueden actuar como servicios de itinerario. Para participar en un itinerario, primero debe diseñar la orquestación como enlace directo; Para ello, use una suscripción de filtro similar a la del puerto de envío en el tema anterior, [utilizando un puerto de envío como un suscriptor de servicio de itinerarios](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md). Figura 1 muestra un ejemplo de una expresión de filtro para una orquestación adecuada recoger los mensajes que cumplen las condiciones siguientes:  

- **ServiceName = Microsoft.Practices.ESB.Services.Transform**  

- **ServiceState = pendiente**  

- **ServiceType = orquestación**  

  ![Orquestación](../esb-toolkit/media/ch4-orchestration.jpg "Ch4 orquestación")  

  **Figura 1**  

  **Expresión de filtro para una orquestación que participará en un itinerario como suscriptor**  

  Cuando los mensajes llegan en Microsoft BizTalk Server a través de una rampa de ESB, el paso de validación en la canalización ESB escribe los valores de propiedad para las propiedades de filtro en las propiedades de contexto de BizTalk del mensaje entrante. Esto promueve al contexto del mensaje. El servicio de itinerarios siempre establece la **ServiceName** propiedad para el servicio activo actualmente en el nombre del servicio para procesar a continuación y con un **ServiceState** el valor de propiedad  **Pendiente**. Para una suscripción, debe establecer al menos los primeros tres de las siguientes propiedades:  

- **ServiceName.** Este es el nombre del servicio, tal como está almacenado en los itinerarios ESB y puede ser cualquier nombre. El itinerario utiliza este nombre para identificar qué servicio para ejecutar.  

- **ServiceState.** Es el estado de la que se ejecute el paso actual de servicio de itinerarios. El paso de servicio actual (para el procesamiento a continuación) siempre tendrá el valor **pendiente**, establecer cualquier ESB itinerarios componente de canalización, el componente de canalización de Selector de itinerarios de ESB, o código que llama a la **por adelantado**  método de la API de itinerario.  

- **ServiceType.** Esta propiedad define el tipo de servicio, que indica si se origina desde la orquestación o el subsistema de mensajería de BizTalk.  

- **IsRequestResponse.** Esta propiedad opcional debe tener el mismo valor que el **IsRequestResponse** propiedad del servicio.
