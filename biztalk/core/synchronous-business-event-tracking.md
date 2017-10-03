---
title: "Seguimiento de eventos empresariales sincrónico | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 302c7918-bc62-46f1-a949-fbf94a7073e3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84223714e2e04cec6c079862693a09786cb19a7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="synchronous-business-event-tracking"></a>Seguimiento sincrónico de eventos empresariales
La manera más fácil de enviar datos de evento a BAM consiste en usar una instancia de la clase DirectEventStream. Esta clase guarda los datos de evento directamente en la base de datos de importación principal de BAM en el contexto de la transacción actual de la aplicación (si existe).  
  
 Si se produce cualquier error durante esta operación, la llamada a método iniciará una excepción de nuevo en la aplicación que hace la llamada. Por ejemplo, esto sucederá si el nombre de un elemento que se pasa en UpdateActivity no coincide con la definición de actividad de BAM, o si aún no implementó la definición de BAM. Esto permite que la aplicación que hace la llamada pueda filtrar y corregir cualquier error al guardar los datos de BAM, lo que da lugar a una administración más sencilla.  
  
 Guardar los datos sincrónicamente podría tener un impacto en el rendimiento, ya que la aplicación que hace la llamada tiene que esperar hasta que BAM ejecute todos los desencadenadores y procedimientos almacenados.  
  
## <a name="see-also"></a>Vea también  
 [Seguimiento de eventos empresariales asíncronos](../core/asynchronous-business-event-tracking.md)