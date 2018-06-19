---
title: Fecha y hora Functoids | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e2d49f5-1aaf-4e4d-8da1-e8605304dccb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ec31607ecefb417fef597b5ba700e6461c71a2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238524"
---
# <a name="date-and-time-functoids"></a>Functoids de fecha y hora

## <a name="overview"></a>Información general
**Fecha / hora** functoids puede dividirse en dos categorías. La primera categoría contiene un único functoid, **agregar días**, que se usa para agregar un número de días especificado a un valor de hora y fecha especificada. Esto puede ser útil cuando se supone que un campo del mensaje de instancia de salida incluye una estimación de fecha y hora en el futuro. Por ejemplo, el **agregar días** functoid puede utilizarse para generar un estimado fecha de envío en función de una diferencia de la fecha en que se recibió un pedido fija.  
  
 La segunda categoría incluye todos los functoids restantes en el **fecha y hora** categoría. Se usan para proporcionar una marca de hora en tiempo de ejecución, de modo que la fecha y la hora en las que se lleva a cabo la transformación del mensaje pueden incluirse en el mensaje de instancia de salida.  
  
 El **agregar días** functoid acepta dos parámetros de entrada, mientras que la **fecha**, **fecha y hora**, y **tiempo** functoids no tienen ninguna entrada parámetros.  

## <a name="available-functoids"></a>Functoids disponibles  
 El **fecha / hora** functoids son: 

* Agregar días
* Date
* Fecha y hora
* Time

Encuentran más detalles sobre estos functoids **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
-  [Cómo agregar Functoids básicos a un mapa](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **Referencia de Functoids de fecha y hora**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]