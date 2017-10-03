---
title: "Resolución de solicitudes y respuestas de puntos de conexión y los requisitos de transformación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a1bfdae-2651-402c-b164-16db663aaa95
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72f442f1d9df457a3c1384f1d717e29c17b433f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="request-response-resolution-of-endpoints-and-transformation-requirements"></a>Resolución de solicitudes y respuestas de puntos de conexión y los requisitos de transformación
En este caso de uso, una aplicación cliente envía un mensaje de solicitud para un aumento y recibe una respuesta. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] actúa como mediador entre el cliente y el punto de conexión de servicio de destino y utiliza la resolución de ESB y el marco de trabajo para realizar la transformación del mensaje dinámico y el enrutamiento de acuerdo con la configuración de en rampa, como se muestra en la figura 1.  
  
 ![Solicitud &#45; Respuesta de resolución de extremos](../esb-toolkit/media/ch3-requestresponse.gif "Ch3-RequestResponse")  
  
 **Figura 1**  
  
 **Resolución de solicitudes y respuestas de puntos de conexión y los requisitos de transformación**  
  
 El ejemplo de resolución dinámica que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. Muestra cómo aplicar transformación dinámica y la resolución de escenarios bidireccionales mediante XML Path Language (XPath), Universal Description, Discovery y Integration (UDDI), estático, o las directivas en el motor de reglas de negocio de BizTalk Server.  
  
 Para obtener más información, consulte el escenario de mensajería bidireccional descrito en [instalar y ejecutar el ejemplo de resolución dinámicos](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).