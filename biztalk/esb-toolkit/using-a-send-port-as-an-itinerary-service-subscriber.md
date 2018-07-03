---
title: Uso de un puerto de envío como un suscriptor de servicio de itinerarios | Microsoft Docs
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
ms.openlocfilehash: c8cf33ab303127ba369a619637abf455c80ee539
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018731"
---
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a><span data-ttu-id="0c3b6-102">Uso de un puerto de envío como un suscriptor de servicio de itinerarios</span><span class="sxs-lookup"><span data-stu-id="0c3b6-102">Using a Send Port as an Itinerary Service Subscriber</span></span>
<span data-ttu-id="0c3b6-103">Como ejemplo de cómo usar un puerto de envío como suscriptor de servicio de itinerarios, figura 1 muestra las condiciones de filtro para un puerto envío unidireccional dinámico que recoge los mensajes que cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0c3b6-103">As an example of how to use a send port as an itinerary service subscriber, Figure 1 shows the filter conditions for a dynamic one-way sent port that picks up messages that meet the following conditions:</span></span>  
  
- <span data-ttu-id="0c3b6-104">**IsRequestResponse = False**</span><span class="sxs-lookup"><span data-stu-id="0c3b6-104">**IsRequestResponse = False**</span></span>  
  
- <span data-ttu-id="0c3b6-105">**ServiceName = DynamicTest**</span><span class="sxs-lookup"><span data-stu-id="0c3b6-105">**ServiceName = DynamicTest**</span></span>  
  
- <span data-ttu-id="0c3b6-106">**ServiceState = pendiente**</span><span class="sxs-lookup"><span data-stu-id="0c3b6-106">**ServiceState = Pending**</span></span>  
  
- <span data-ttu-id="0c3b6-107">**ServiceType = mensajería**</span><span class="sxs-lookup"><span data-stu-id="0c3b6-107">**ServiceType = Messaging**</span></span>  
  
  <span data-ttu-id="0c3b6-108">![Puerto de envío](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")</span><span class="sxs-lookup"><span data-stu-id="0c3b6-108">![Send Port](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")</span></span>  
  
  <span data-ttu-id="0c3b6-109">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="0c3b6-109">**Figure 1**</span></span>  
  
  <span data-ttu-id="0c3b6-110">**Ejemplo de filtros de puertos de envío**</span><span class="sxs-lookup"><span data-stu-id="0c3b6-110">**Example of send port filters**</span></span>  
  
  <span data-ttu-id="0c3b6-111">Usar expresiones de filtro de puerto de envío para especificar los conjuntos de propiedad y el valor de esta se reanudará desde la base de datos de cuadro de mensaje a través de la itinerarios en rampa de mensajes.</span><span class="sxs-lookup"><span data-stu-id="0c3b6-111">Use send port filter expressions to specify the property and value sets of messages it will pick up from the Message Box database through the itinerary on-ramp.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c3b6-112">Es importante usar condiciones de filtro que son tan específicos y centrado como sea posible; en caso contrario, hay un riesgo de recoger los mensajes no deseados, que podrían producir problemas en un entorno de gran volumen.</span><span class="sxs-lookup"><span data-stu-id="0c3b6-112">It is important to use filter conditions that are as specific and focused as possible; otherwise, there is a risk of picking up unintended messages, which could cause problems in a high-volume environment.</span></span> <span data-ttu-id="0c3b6-113">El esquema del sistema-Properties.xsd define las propiedades del filtro de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="0c3b6-113">The schema System-Properties.xsd defines the filter properties of subscriptions.</span></span>