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
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a>Usar un puerto de envío como un suscriptor de servicio itinerarios
Como ejemplo de cómo utilizar un puerto de envío como un suscriptor de itinerario del servicio, la figura 1 muestra las condiciones de filtro para un puerto envío unidireccional dinámico que recoge los mensajes que cumplen las condiciones siguientes:  
  
-   **IsRequestResponse = False**  
  
-   **ServiceName = DynamicTest**  
  
-   **ServiceState = pendiente**  
  
-   **ServiceType = mensajería**  
  
 ![Puerto de envío](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")  
  
 **Figura 1**  
  
 **Ejemplo de filtros de puertos de envío**  
  
 Utilice expresiones de filtro de puerto de envío para especificar los conjuntos de propiedad y valor de los mensajes que efectuará la recogida de la base de datos de cuadro de mensaje mediante el itinerario en rampa.  
  
> [!NOTE]
>  Es importante usar condiciones de filtro que son tan específico y tiene el foco como sea posible; en caso contrario, se corre el riesgo de recoger mensajes no deseados, lo que pudieron provocar problemas en un entorno de gran volumen. El esquema sistema-Properties.xsd define las propiedades del filtro de suscripciones.