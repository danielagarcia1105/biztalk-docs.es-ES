---
title: Crear suscriptores itinerarios | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84a76aeb-8d40-490a-8ae6-7abfdd2d2573
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81e9790c36d1af9d48942c5de7ccc8eab6d87a5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-itinerary-subscribers"></a>Crear suscriptores itinerarios
[!INCLUDE[prague](../includes/prague-md.md)]publica automáticamente los mensajes que llegan a través de una canalización de recepción para la base de datos de cuadro de mensaje; Esto hace que los mensajes listos para la recogida por el suscriptor relevante. Este enfoque desacoplado es la mejor manera de desarrollar soluciones de BizTalk porque ofrece la máxima flexibilidad, también se escala y utiliza la publicación-suscribirse mecanismo.  
  
 Hay dos maneras de crear un suscriptor de itinerarios de servicio:  
  
-   [Usar un puerto de envío como un suscriptor de servicio itinerarios](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)  
  
-   [Utilizar una orquestación como un suscriptor de servicio itinerarios](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)