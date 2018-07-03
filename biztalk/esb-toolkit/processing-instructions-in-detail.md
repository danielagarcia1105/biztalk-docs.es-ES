---
title: Instrucciones de procesamiento en detalle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed5d92fb-d53b-49a2-b2c7-8558708d6554
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d867737599369ad8ff07780080b16f5ce0f6f2fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005581"
---
# <a name="processing-instructions-in-detail"></a>Instrucciones de procesamiento en detalle
Este tema describe el formato y la estructura del esquema de propiedad del sistema-Properties.xsd, que define varias propiedades de contexto necesarias para el procesamiento de itinerarios. Estas propiedades se promocionan cuando se recibe un mensaje y se procesan a través de canalizaciones de BizTalk Server; Dado que son propiedades promocionadas, son accesibles para los componentes de BizTalk Server. Las siguientes propiedades se definen en el esquema de propiedades del sistema-Properties.xsd:  
  
- **ItineraryHeader.** Esta propiedad contiene toda la información de itinerarios y una lista de servicios de itinerario para invocar a través de una secuencia de pasos de itinerarios. La API de itinerario utiliza internamente esta propiedad.  
  
- **ServiceName.** Esta propiedad contiene el nombre del servicio de itinerarios actual para procesar.  
  
- **ServiceState.** Esta propiedad contiene el estado del servicio de itinerarios actual: **pendiente**, **completar**, o **Active**. Todos los servicios de suscripción a un paso del itinerario que contiene un **ServiceState** valor **pendiente**.  
  
- **ServiceType.** Esta propiedad define el tipo del paso del itinerario (**mensajería** o **orquestación**).  
  
- **IsRequestResponse.** Esta propiedad define el tipo de mensajería (unidireccional o de solicitud-respuesta).  
  
  El servicio de itinerarios ejecuta pasos itinerarios en uno de dos maneras, dependiendo del valor de la **ServiceType** propiedad:  
  
- Los componentes de canalización itinerarios ejecutan todos los pasos de itinerarios con un **ServiceType** propiedad de **mensajería**. Los desarrolladores pueden ampliar este proceso mediante una canalización personalizada y la API de itinerario.  
  
- Cuando el **ServiceType** propiedad es **orquestación**, una orquestación, activada por una suscripción a las propiedades de contexto de itinerarios, ejecuta el paso del itinerario.  
  
  Cuando un servicio de itinerarios procesa un paso del itinerario, el servicio es responsable de avanzar el itinerario y enviar el mensaje con un nuevo contexto de itinerarios para un posterior procesamiento mediante la publicación-suscribirse funcionalidad de BizTalk Server. Un servicio de itinerarios tiene control total sobre el itinerario en el contexto del mensaje y se puede avanzar al paso adecuado según su lógica interna y el contenido del mensaje.  
  
  El mecanismo de procesamiento de itinerarios admite la combinación de pasos de itinerarios de mensajería y orquestación dentro de un único itinerario. Los desarrolladores también pueden definir servicios de itinerarios personalizados y configurar pasos de itinerarios personalizados.  
  
  Para obtener más información acerca de los itinerarios, consulte [instalar y ejecutar el ejemplo de rampa de itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).  
  
  Para obtener más información sobre los servicios de itinerarios personalizados y pasos de itinerarios personalizados, consulte [creación de un servicio de itinerarios personalizado](../esb-toolkit/creating-a-custom-itinerary-service.md).