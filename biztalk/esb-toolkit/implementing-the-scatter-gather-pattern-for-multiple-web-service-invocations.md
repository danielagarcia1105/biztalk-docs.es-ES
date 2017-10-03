---
title: "Implementar el patrón de dispersión y recopilación de varias invocaciones de servicio Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 912512a4-9649-40df-bb82-b8f4b85c8ca6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03fb129d23b0884fdca518dca574be64d7672c6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-the-scatter-gather-pattern-for-multiple-web-service-invocations"></a>Implementar el patrón de dispersión y recopilación de varias invocaciones de servicio Web
En este caso de uso, un mensaje contiene un paso de servicio itinerarios que especifica externas más de un servicio que [!INCLUDE[prague](../includes/prague-md.md)] debe tener acceso a. Resolución dinámica usa para determinar las ubicaciones de servicio y los puntos de conexión y cualquier BizTalk Service opcional que se asigna para transformar los datos devueltos. La orquestación que implementa este servicio lleva a cabo la transformación y las invocaciones de y todas las invocaciones del servicio se producen de forma asincrónica. Después de completar todas las invocaciones de servicio, el servicio itinerario agrega las respuestas en un único mensaje de respuesta y envía el mensaje al cliente a través de un punto de conexión asignado dinámicamente. La figura 1 muestra este caso de uso.  
  
 ![Implementación de dispersión recopilar patrón](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3-ImplementingScatter")  
  
 **Figura 1**  
  
 **Implementar el patrón de dispersión y recopilación para varias invocaciones de servicio Web**  
  
 El ejemplo de dispersión y recopilación que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.  
  
 Para obtener más información, consulte [instalar y ejecutar el ejemplo de dispersión y recopilación](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).