---
title: "Consideraciones para BAM código mantenimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, code maintenance
- BAMInterceptor class
ms.assetid: e1f1d8e0-207c-47e1-b9bd-a473c86922ce
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f7cfdb75a32c23ef5c8dedec3b6a4c783bf089a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-for-bam-code-maintenance"></a>Consideraciones sobre el mantenimiento de códigos de BAM
Cuando decida cómo instrumentar la aplicación para usar BAM, debe considerar la posibilidad de que las necesidades cambiarán. Si llama métodos en una de las clases [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) para escribir los datos que se supervisan, básicamente está "codificando" el modelo de observación en la aplicación. Si necesita cambiar qué datos se supervisan, deberá desactivar la aplicación, modificar el código, recompilar la aplicación y, a continuación, volver a implementar la aplicación actualizada.  
  
 Como alternativa, puede instrumentar la aplicación llamando a métodos de la clase [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) . La clase [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) hace referencia a un archivo de configuración para determinar qué eventos y datos se supervisan. Usando la clase [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) , puede instrumentar el código una vez y, a continuación, modificar los datos que se supervisan mediante la actualización de los metadatos, sin tener que desactivar la aplicación.  
  
## <a name="instrumenting-your-application-by-using-the-eventstream-object"></a>Instrumentación de la aplicación con el objeto EventStream  
 Esta aproximación es más sencilla y puede aplicarse cuando se construye una aplicación dedicada con requisitos de supervisión específicos y muy conocidos. Antes de decidirse a usar esta aproximación, deberá poder responder a las siguientes preguntas:  
  
-   ¿Cuáles son los hitos de BAM y dónde se encuentran en el código?  
  
-   ¿Qué datos se supervisan y qué momento y qué lugar del código están los datos disponibles?  
  
 Si es probable que la respuesta una de estas preguntas cambie, debe considerar la posibilidad de instrumentar la aplicación mediante el objeto [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)en su lugar.  
  
 Si sigue esta aproximación de "codificación", simplemente llama a métodos de la clase [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx), [Microsoft.BizTalk.Bam.EventObservation.BufferedEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.bufferedeventstream.aspx), **MessagingEventStream** (de implementaciones de canalizaciones) o bien **OrchestrationEventStream** (de implementaciones de orquestaciones), en función de las necesidades.  
  
## <a name="instrumenting-your-application-by-using-the-baminterceptor-object"></a>Instrumentación de la aplicación con el objeto BAMInterceptor  
 La aproximación es mejor cuando:  
  
-   Necesita equilibrar la visibilidad de datos con el rendimiento de la aplicación, y desea poder controlar los datos que se supervisan en tiempo de ejecución.  
  
-   La aplicación procesa mensajes XML de grandes dimensiones, en los que todos los datos pueden ser importantes para la supervisión.  
  
-   No se admite detener la aplicación y cambiar el código para supervisar datos distintos.  
  
 En esta aproximación, se instrumenta la aplicación de una forma genérica mediante los métodos de la clase [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx). Si se pasan al interceptor distintas configuraciones, se pueden cambiar los datos que BAM supervisa.  
  
 Puede usar el Editor de perfiles de seguimiento (TPE) para modificar los datos que BAM recopila de una orquestación de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Uso de una actividad](../core/using-an-activity.md)   
 [¿Qué es el Interceptor de BAM?](../core/what-is-the-bam-interceptor.md)   
 [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md)