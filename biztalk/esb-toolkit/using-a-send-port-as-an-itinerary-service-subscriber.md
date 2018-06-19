---
title: Mediante un puerto de envío como un suscriptor de servicio itinerarios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 898b461c-4d0d-4703-a8ca-7f52f3f15f70
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5213b22c1bdfaa505dbf4b62a03095bcec5a1746
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295492"
---
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a><span data-ttu-id="1b80d-102">Usar un puerto de envío como un suscriptor de servicio itinerarios</span><span class="sxs-lookup"><span data-stu-id="1b80d-102">Using a Send Port as an Itinerary Service Subscriber</span></span>
<span data-ttu-id="1b80d-103">Como ejemplo de cómo utilizar un puerto de envío como un suscriptor de itinerario del servicio, la figura 1 muestra las condiciones de filtro para un puerto envío unidireccional dinámico que recoge los mensajes que cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1b80d-103">As an example of how to use a send port as an itinerary service subscriber, Figure 1 shows the filter conditions for a dynamic one-way sent port that picks up messages that meet the following conditions:</span></span>  
  
-   <span data-ttu-id="1b80d-104">**IsRequestResponse = False**</span><span class="sxs-lookup"><span data-stu-id="1b80d-104">**IsRequestResponse = False**</span></span>  
  
-   <span data-ttu-id="1b80d-105">**ServiceName = DynamicTest**</span><span class="sxs-lookup"><span data-stu-id="1b80d-105">**ServiceName = DynamicTest**</span></span>  
  
-   <span data-ttu-id="1b80d-106">**ServiceState = pendiente**</span><span class="sxs-lookup"><span data-stu-id="1b80d-106">**ServiceState = Pending**</span></span>  
  
-   <span data-ttu-id="1b80d-107">**ServiceType = mensajería**</span><span class="sxs-lookup"><span data-stu-id="1b80d-107">**ServiceType = Messaging**</span></span>  
  
 <span data-ttu-id="1b80d-108">![Puerto de envío](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")</span><span class="sxs-lookup"><span data-stu-id="1b80d-108">![Send Port](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")</span></span>  
  
 <span data-ttu-id="1b80d-109">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="1b80d-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="1b80d-110">**Ejemplo de filtros de puertos de envío**</span><span class="sxs-lookup"><span data-stu-id="1b80d-110">**Example of send port filters**</span></span>  
  
 <span data-ttu-id="1b80d-111">Utilice expresiones de filtro de puerto de envío para especificar los conjuntos de propiedad y valor de los mensajes que efectuará la recogida de la base de datos de cuadro de mensaje mediante el itinerario en rampa.</span><span class="sxs-lookup"><span data-stu-id="1b80d-111">Use send port filter expressions to specify the property and value sets of messages it will pick up from the Message Box database through the itinerary on-ramp.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b80d-112">Es importante usar condiciones de filtro que son tan específico y tiene el foco como sea posible; en caso contrario, se corre el riesgo de recoger mensajes no deseados, lo que pudieron provocar problemas en un entorno de gran volumen.</span><span class="sxs-lookup"><span data-stu-id="1b80d-112">It is important to use filter conditions that are as specific and focused as possible; otherwise, there is a risk of picking up unintended messages, which could cause problems in a high-volume environment.</span></span> <span data-ttu-id="1b80d-113">El esquema sistema-Properties.xsd define las propiedades del filtro de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="1b80d-113">The schema System-Properties.xsd defines the filter properties of subscriptions.</span></span>