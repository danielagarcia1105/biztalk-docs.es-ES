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
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a>Uso de un puerto de envío como un suscriptor de servicio de itinerarios
Como ejemplo de cómo usar un puerto de envío como suscriptor de servicio de itinerarios, figura 1 muestra las condiciones de filtro para un puerto envío unidireccional dinámico que recoge los mensajes que cumplen las condiciones siguientes:  
  
- **IsRequestResponse = False**  
  
- **ServiceName = DynamicTest**  
  
- **ServiceState = pendiente**  
  
- **ServiceType = mensajería**  
  
  ![Puerto de envío](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")  
  
  **Figura 1**  
  
  **Ejemplo de filtros de puertos de envío**  
  
  Usar expresiones de filtro de puerto de envío para especificar los conjuntos de propiedad y el valor de esta se reanudará desde la base de datos de cuadro de mensaje a través de la itinerarios en rampa de mensajes.  
  
> [!NOTE]
>  Es importante usar condiciones de filtro que son tan específicos y centrado como sea posible; en caso contrario, hay un riesgo de recoger los mensajes no deseados, que podrían producir problemas en un entorno de gran volumen. El esquema del sistema-Properties.xsd define las propiedades del filtro de suscripciones.