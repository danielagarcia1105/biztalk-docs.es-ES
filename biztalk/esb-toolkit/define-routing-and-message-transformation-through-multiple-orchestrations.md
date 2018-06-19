---
title: Definir enrutamiento y transformación a través de varias orquestaciones mediante itinerarios de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63141b83-798e-40d0-908d-6b7649923e69
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c5a87b06700794dca6c4aae9588c3068b98d995
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294020"
---
# <a name="defining-routing-and-message-transformation-through-multiple-orchestrations-using-itineraries"></a>Definición de enrutamiento y transformación de mensajes a través de varias orquestaciones mediante itinerarios
En este caso de uso, un mensaje enviado para su procesamiento contiene un encabezado SOAP itinerario que describe la lista de servicios para ejecutar así como sus requisitos de resolución. El itinerario especifica una o varias orquestaciones de Microsoft BizTalk Server a través del cual el mensaje pasará durante el ciclo de procesamiento. Si lo desea, el itinerario puede contener información de enrutamiento dinámico que se usa para determinar los puntos de conexión o requisitos de transformación para el mensaje. Figura 1 muestra una vista esquemática del proceso.  
  
 ![Definir enrutamiento de múltiples orquestaciones](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3-DefiningRoutingMultipleOrchestrations")  
  
 **Figura 1**  
  
 **Definir la transformación de mensajes y enrutamiento a través de varias orquestaciones mediante itinerarios**  
  
 El ejemplo de itinerario en rampa que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. Muestra cómo crear itinerarios que contienen la resolución, el enrutamiento, y las instrucciones de invocación de servicio como una serie de pasos itinerarios que definen cómo el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] y BizTalk Server procesará el mensaje de entrada. Unidireccional y se incluyen ejemplos de solicitudes y respuestas.  
  
 Para obtener más información, consulte [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).