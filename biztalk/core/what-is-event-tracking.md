---
title: ¿Qué es el seguimiento de eventos? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [HAT tracking], events
- DTA_Services audit table [HAT]
- HAT, events
- events, tracking
- tracking, events
- Tracking database, DTA_Services audit table
- events, HAT
ms.assetid: dd211752-d1af-4287-967a-908b8d067ebb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42799a084c579cfba7d696c700d887b1ae992db2
ms.sourcegitcommit: ed9590dbcd97c12a1fe5ce2cdf8d826492cccdff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "39640088"
---
# <a name="what-is-event-tracking"></a>¿Qué es el seguimiento de eventos?
Los datos de eventos de mensajes de los que se hace seguimiento se basan en eventos (por ejemplo, cuando empieza o finaliza un servicio, o cuando se envía o recibe un mensaje). El proceso de seguimiento de eventos de mensajes devuelve una lista de los eventos que se han producido, lo que permite ver todo lo que ha ocurrido según los filtros establecidos.  
  
 Puede realizar el seguimiento del inicio y fin de orquestaciones y puertos, cuando los mensajes se envían y reciben, así como de la ejecución de cada forma de una orquestación.  
  
 La base de datos de seguimiento de BizTalk (BizTalkDTAdb) contiene una tabla de auditorías DTA_Services. Esta tabla contiene el historial de todos los servicios implementados: canalizaciones, transportes y orquestaciones. No realiza el seguimiento de la anulación de implementaciones.  
  
 Puede realizar el seguimiento del contenido de un mensaje y de las propiedades promocionadas de un mensaje. Seguimiento de eventos de mensaje definen estas acciones como **cuerpo del mensaje** seguimiento y **propiedad Message** de seguimiento. Aunque aparezcan sobres en los resultados del seguimiento de eventos de mensajes, no se puede hacer un seguimiento de las propiedades de mensajes a partir de ellos.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el seguimiento mediante la consola de administración de BizTalk Server](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)
