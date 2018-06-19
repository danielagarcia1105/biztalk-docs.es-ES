---
title: Definir enrutamiento y las invocaciones de servicio de transformación con itinerarios de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6f2448e-a5a7-496c-86d3-47f12e6f1251
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 975c830f73e0de362b25f312a8d41c4b15368cfd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294284"
---
# <a name="defining-routing-and-message-transformation-service-invocations-using-itineraries"></a>Enrutamiento de definición e invocaciones de servicio de transformación de mensaje mediante itinerarios
En este caso de uso, un mensaje enviado para su procesamiento contiene un encabezado SOAP itinerario que describe la lista de servicios para ejecutar así como sus requisitos de resolución. En concreto, un servicio de enrutamiento y la transformación se definen, cada uno de ellos opcionalmente que requieren resolución a través de una búsqueda de Universal Description, Discovery y Integration (UDDI), directiva del motor de reglas de negocios, XML Path Language (XPath) o STATIC. Este caso de uso puede ampliarse mediante la adición de otros servicios para el itinerario en el momento de publicación de mensajes.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona dos tipos de itinerario en pendientes: aquellos que admiten la comunicación unidireccional y aquellos que admiten escenarios de solicitud-respuesta. Dado que el mecanismo de resolución dinámica puede usar información en el itinerario para buscar los puntos de conexión o enlazar dinámicamente a los puntos de conexión, no hay ningún requisito para Microsoft BizTalk Server para que contenga los detalles de ruta de punto de conexión concreto. Figura 1 muestra una vista esquemática del proceso.  
  
 ![Definición de invocación de servicio de enrutamiento](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3-DefiningRoutingServiceInvocation")  
  
 **Figura 1**  
  
 **Definir mensajes y enrutamiento invocaciones de servicio de transformación con itinerarios**  
  
 El ejemplo de itinerario en rampa que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. Muestra cómo crear itinerarios que contienen la resolución, el enrutamiento, y las instrucciones de invocación de servicio como una serie de pasos itinerarios que definen cómo el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] y BizTalk Server procesará el mensaje mediante la publicación-suscribirse funcionalidad de Servidor BizTalk Server. Unidireccional y se incluyen ejemplos de solicitudes y respuestas.  
  
 Para obtener más información, consulte [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).