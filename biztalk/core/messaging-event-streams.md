---
title: "Secuencias de eventos de mensajería | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dc56aff-c093-4c79-9cc7-f72079ee927f
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d955dbc2b50d1d9c40b54736762fcbaa2bfe536
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messaging-event-streams"></a>Secuencias de eventos de mensajería
Las secuencias de eventos de mensajería (MES) se usan cuando la aplicación se ejecuta en un equipo en el que BizTalk Server está instalado y cuando realiza el seguimiento de elementos que forman parte de las transacciones de canalización de BizTalk. El uso de MES garantiza que la persistencia de eventos de BAM permanece sincronizada con las transacciones de canalización de BizTalk.  
  
 Secuencias de eventos de mensajería son instancias de los objetos EventStream devueltas por la [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx) método.  
  
 Las secuencias de eventos de mensajería son asíncronas y almacenan datos de seguimiento primero en la base de datos de cuadro de mensajes de BizTalk. De forma periódica, el Servicio de descodificación de datos de seguimiento (TDDS) los datos se procesan y se almacenan de forma permanente en la base de datos de importación principal de BAM.  
  
 IPipelineContext se encuentra en la [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx) espacio de nombres. Para usar la API debe agregar Microsoft.BizTalk.Pipeline (en microsoft.biztalk.pipeline.dll) al proyecto.  
  
## <a name="see-also"></a>Vea también  
 [OrchestrationEventStream](../core/orchestrationeventstream.md)   
 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx)   
 [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)