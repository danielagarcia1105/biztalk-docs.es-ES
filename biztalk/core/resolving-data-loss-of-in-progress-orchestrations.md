---
title: "Resolver la pérdida de datos de las orquestaciones en curso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data loss, MessageBox database
- data recovery
- data loss, recovery
- data loss, orchestrations
- data recovery, MessageBox database
- data recovery, orchestrations
- data loss, data recovery
- orchestrations, data recovery
- orchestrations, data loss
ms.assetid: dc6f1fd2-1976-40f2-ab57-41c7db40705e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eca757b80e31ee5db829d2d2079bf657d01079b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="resolving-data-loss-of-in-progress-orchestrations"></a>Resolver la pérdida de datos de orquestaciones en curso
Las bases de datos de cuadro de mensajes contienen el estado de las orquestaciones actualmente en curso. Aunque no exista ninguna forma de saber con exactitud qué datos se han perdido de las bases de datos de cuadro de mensajes, se pueden seguir algunos pasos para recopilar información acerca de ellos:  
  
-   Determine los mensajes que se han enviado y recibido en las orquestaciones actuales, así como los sistemas externos que se han utilizado después del punto de recuperación. Por ejemplo, si su sistema mantiene un registro externo de mensajes y sucesos, puede examinar ese registro. Es posible que también tenga que revisar manualmente los sistemas externos para ver qué actividades han tenido lugar.  
  
-   Después de determinar la causa de la pérdida de los datos, puede empezar a corregir el sistema restaurado decidiendo qué procesos pueden continuar, cuáles deben finalizarse y reiniciarse (para lo que tendrá que reenviar los mensajes de activación perdidos), y cuáles se han completado correctamente y pueden finalizarse. Este proceso depende en gran medida de la arquitectura de su sistema y debe considerarse parte del plan de recuperación del sistema.  
  
## <a name="see-also"></a>Vea también  
 [Resolver la pérdida de datos](../core/resolving-data-loss.md)