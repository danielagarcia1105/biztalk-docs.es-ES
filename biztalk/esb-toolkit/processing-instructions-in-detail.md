---
title: Instrucciones de procesamiento en detalle | Documentos de Microsoft
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
ms.openlocfilehash: 9cf0a726d2c8c4f6242ed19a7dcd1e5430775e63
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008941"
---
# <a name="processing-instructions-in-detail"></a>Instrucciones de procesamiento en detalle
Este tema describe el formato y la estructura del esquema de propiedad al sistema-Properties.xsd, que define varias propiedades de contexto necesarias para el procesamiento de itinerarios. Estas propiedades se promocionan cuando se recibe un mensaje y se procesan a través de canalizaciones de BizTalk Server; Dado que son las propiedades promocionadas, son accesibles a los componentes de BizTalk Server. Las siguientes propiedades se definen en el esquema de propiedades del sistema-Properties.xsd:  
  
-   **ItineraryHeader.** Esta propiedad contiene toda la información de itinerarios y una lista de servicios itinerarios para invocarse a través de una secuencia de pasos de itinerarios. La API de itinerario utiliza internamente esta propiedad.  
  
-   **ServiceName.** Esta propiedad contiene el nombre del servicio actual itinerario para procesar.  
  
-   **ServiceState.** Esta propiedad contiene el estado del servicio itinerario actual: **pendiente**, **completar**, o **Active**. Todos los servicios de suscriben a un paso itinerario que contiene un **ServiceState** valo **pendiente**.  
  
-   **ServiceType.** Esta propiedad define el tipo de paso itinerario (**mensajería** o **orquestación**).  
  
-   **IsRequestResponse.** Esta propiedad define el tipo de mensajería (unidireccional o de solicitud-respuesta).  
  
 El servicio de itinerario ejecuta los pasos itinerarios en uno de dos maneras, dependiendo del valor de la **ServiceType** propiedad:  
  
-   Componentes de canalización itinerarios ejecutan todos los pasos itinerarios con un **ServiceType** propiedad de **mensajería**. Los programadores pueden ampliar este proceso mediante una canalización personalizada y la API de itinerario.  
  
-   Cuando el **ServiceType** propiedad es **orquestación**, una orquestación, activada por una suscripción a las propiedades de contexto itinerarios, ejecuta el paso de itinerarios.  
  
 Cuando un servicio de itinerario procesa un paso itinerario, este servicio es responsable para avanzar el itinerario y enviar el mensaje con un nuevo contexto itinerario para su posterior procesamiento mediante la publicación-suscribirse funcionalidad de BizTalk Server. Un servicio itinerario tenga control total sobre el itinerario en el contexto del mensaje y puede avanzar al paso adecuado según su lógica interna y el contenido del mensaje.  
  
 El mecanismo de procesamiento itinerarios admite la combinación de mensajería y orquestación pasos itinerarios dentro de un único itinerario. Los desarrolladores también pueden definir servicios itinerarios personalizados y configurar pasos itinerarios personalizados.  
  
 Para obtener más información acerca de itinerarios, consulte [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).  
  
 Para obtener más información sobre los servicios de itinerarios personalizados y pasos itinerarios personalizados, consulte [crear un servicio personalizado de itinerario](../esb-toolkit/creating-a-custom-itinerary-service.md).