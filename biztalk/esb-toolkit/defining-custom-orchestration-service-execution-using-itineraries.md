---
title: Definir orquestación personalizada de ejecución de servicio mediante itinerarios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6089169d-2fa1-4f81-afe1-db9d90a10382
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9336969db2c90168bf7c398276205043b06504ce
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007437"
---
# <a name="defining-custom-orchestration-service-execution-using-itineraries"></a>Definir orquestación personalizada de ejecución de servicio mediante itinerarios
En este caso de uso, un mensaje enviado para su procesamiento contiene un encabezado SOAP itinerario que describe la lista de servicios para ejecutar así como sus requisitos de resolución. El itinerario especifica uno o más orquestaciones personalizadas o procesos a través del cual el mensaje pasará durante el ciclo de procesamiento. Orquestaciones personalizadas tienen control total sobre el itinerario y otras propiedades personalizadas expuestas en el contexto del mensaje. Si lo desea, el itinerario puede contener información de resolución dinámica que determina los requisitos de transformación y los puntos de conexión para el mensaje. Figura 1 muestra una vista esquemática del proceso.  
  
 ![Definir orquestación personalizada](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3-DefiningCustomOrchestration")  
  
 **Figura 1**  
  
 **Definir la ejecución del servicio de orquestación personalizada mediante itinerarios**  
  
 El ejemplo de itinerario en rampa que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. Muestra cómo crear itinerarios que contienen la resolución, enrutamiento y las instrucciones de invocación de servicio como una serie de pasos itinerarios que definen cómo el ESB y BizTalk Server procesará el mensaje de entrada. Unidireccional y se incluyen ejemplos de solicitudes y respuestas.  
  
 Para obtener más información, consulte [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).