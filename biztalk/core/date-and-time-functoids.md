---
title: Functoids de fecha y hora | Microsoft Docs
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
ms.openlocfilehash: 5224c409a6d705806cccc493009ce2c32062f0a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010669"
---
# <a name="date-and-time-functoids"></a>Functoids de fecha y hora

## <a name="overview"></a>Información general
**Fecha / hora** functoids pueden dividirse en dos categorías. La primera categoría contiene un único functoid, **agregar días**, que se usa para agregar un número de días especificado a un valor de hora y fecha especificada. Esto puede ser útil cuando se supone que un campo del mensaje de instancia de salida incluye una estimación de fecha y hora en el futuro. Por ejemplo, el **agregar días** functoid puede utilizarse para generar un estimado fecha de envío en función de una diferencia fija de la fecha en que se recibió un pedido.  

 La segunda categoría incluye todos los functoids restantes en el **fecha y hora** categoría. Se usan para proporcionar una marca de hora en tiempo de ejecución, de modo que la fecha y la hora en las que se lleva a cabo la transformación del mensaje pueden incluirse en el mensaje de instancia de salida.  

 El **agregar días** functoid acepta dos parámetros de entrada, mientras que el **fecha**, **fecha y hora**, y **tiempo** los functoids no tienen ninguna entrada parámetros.  

## <a name="available-functoids"></a>Functoids disponibles  
 El **fecha / hora** functoids son: 

* Agregar días
* date
* Fecha y hora
* Time

Encontrará más detalles sobre estos functoids **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

## <a name="see-also"></a>Vea también  
- [Cómo agregar Functoids básicos a una asignación](../core/how-to-add-basic-functoids-to-a-map.md)   
- **Referencia de Functoids de fecha y hora** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
