---
title: OrchestrationEventStream | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7c63610-6344-4b71-8d65-3add7883bc79
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1fd0dc229c38b3a060c75a9c584259175d72fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="orchestrationeventstream"></a>OrchestrationEventStream
Utilice la API OrchestrationEventStream (OES) cuando la aplicación se ejecute en un equipo en el que BizTalk Server está instalado y cuando realice el seguimiento de elementos que forman parte de las transacciones de orquestación de BizTalk.  
  
 La API de OES almacena primero los datos de seguimiento en la base de datos de cuadro de mensajes de BizTalk. De forma periódica, el Servicio de descodificación de datos de seguimiento (TDDS) los datos se procesan y se almacenan de forma permanente en la base de datos de importación principal de BAM.  
  
 La API de OES se encuentra en el espacio de nombres Microsoft.BizTalk.Bam.EventObservation. Para usar la API debe agregar Microsoft.Biztalk.BAM.Xlangs.dll al proyecto.  
  
## <a name="oes-members"></a>Miembros de OES  
 La API de OES se deriva de la clase [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) .  
  
 OES implementa todos los métodos dentro de la clase EventStream, aunque presenta la siguiente excepción en los comportamientos:  
  
 **public static void Clear();}**  
  
 No realiza ninguna operación.  
  
 **pública Flush() void estático;**  
  
 No realiza ninguna operación.  
  
## <a name="see-also"></a>Vea también  
 [Clases EventStream](../core/eventstream-classes.md)