---
title: Las relaciones de actividad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], relationships
ms.assetid: da7c7205-18c6-44df-af03-3140214c84e6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3709ad02ed082595665c68485502847b52e5a1d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="activity-relationships"></a>Relaciones de actividades
Las relaciones entre actividades existen cuando una actividad está relacionada con una o más actividades. Por ejemplo, cuando se tienen varias actividades de envío relacionadas con una sola actividad de pedido, o una actividad de envío que contiene elementos procedentes de dos actividades de pedido.  
  
 Para indicar que dos actividades están relacionadas, deberá conocer ambos nombres y tener los ActivityID correspondientes en memoria para llamar a AddRelatedActivity. Esta API crea el vínculo entre los registros de actividad correspondientes.  
  
 En la siguiente ilustración, las líneas de código resaltadas muestran cómo establecer una relación entre la instancia de actividad de pedido n.º 123 y las actividades de envío n.º 1549, 1550 y 1551.  
  
 ![](../core/media/activity-relationships-example.gif "activity_relationships_example")  
  
 El usuario final de negocios consulta una página Web que muestra el historial de un pedido. Puede indicar a las 10 A.M. llega, los dos días más tarde recibe la aprobación y la página proporciona un vínculo a los documentos en cuestión. Debido al código mostrado en la ilustración anterior, la página también proporcionará hipervínculos que lleven al usuario empresarial final hasta las páginas Web de envío correspondientes.  
  
> [!NOTE]
>  Todas las llamadas a `AddRelatedActivity` deberán producirse entre `BeginActivity` y `EndActivity`.  
  
## <a name="see-also"></a>Vea también  
  
 [Continuación de actividad](../core/activity-continuation.md)   
 [Infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md)   
 [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md)   
 [API de BAM en una expresión de orquestación (ejemplo de BizTalk Server)](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)