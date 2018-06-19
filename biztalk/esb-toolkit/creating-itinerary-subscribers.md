---
title: Crear suscriptores itinerarios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84a76aeb-8d40-490a-8ae6-7abfdd2d2573
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f470ed5268c445ab3b7175f1cba07ff1de52a27
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007197"
---
# <a name="creating-itinerary-subscribers"></a><span data-ttu-id="81117-102">Crear suscriptores itinerarios</span><span class="sxs-lookup"><span data-stu-id="81117-102">Creating Itinerary Subscribers</span></span>
<span data-ttu-id="81117-103">BizTalk Server publica automáticamente los mensajes que llegan a través de una canalización de recepción para la base de datos de cuadro de mensaje; Esto hace que los mensajes listos para la recogida por el suscriptor relevante.</span><span class="sxs-lookup"><span data-stu-id="81117-103">BizTalk Server automatically publishes messages arriving through a receive pipeline to the Message Box database; this makes the messages ready for pick-up by the relevant subscriber.</span></span> <span data-ttu-id="81117-104">Este enfoque desacoplado es la mejor manera de desarrollar soluciones de BizTalk porque ofrece la máxima flexibilidad, también se escala y utiliza la publicación-suscribirse mecanismo.</span><span class="sxs-lookup"><span data-stu-id="81117-104">This decoupled approach is the preferred way to develop BizTalk solutions because it provides maximum flexibility, scales well, and uses the publish-subscribe mechanism.</span></span>  
  
 <span data-ttu-id="81117-105">Hay dos maneras de crear un suscriptor de itinerarios de servicio:</span><span class="sxs-lookup"><span data-stu-id="81117-105">There are two ways to create an itinerary service subscriber:</span></span>  
  
-   [<span data-ttu-id="81117-106">Uso de un puerto de envío como un suscriptor de servicio de itinerarios</span><span class="sxs-lookup"><span data-stu-id="81117-106">Using a Send Port as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)  
  
-   [<span data-ttu-id="81117-107">Uso de una orquestación como un suscriptor de servicio de itinerarios</span><span class="sxs-lookup"><span data-stu-id="81117-107">Using an Orchestration as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)