---
title: Identificación de datos de seguimiento perdidos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data loss, HAT
- reporting tools
- Orchestration Debugger
- Tracking database, data loss
- HAT, data loss
- HAT, Operation View tool
- HAT, reporting tools
- Operation View tool, MessageBox database
- MessageBox database, Operation View tool
- Operation View tool, data loss
ms.assetid: 1ac13e2c-cd5e-437e-b924-d4547931874e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17116d3a560e968e8dd9da0e42f5af221c23f5d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982861"
---
# <a name="identifying-lost-tracking-data"></a>Identificar datos de seguimiento perdidos
Puede usar la consola de administración de BizTalk Server para que le ayude a identificar los datos de seguimiento que se han perdido como resultado de un error de hardware. Puede usar la consola de administración de BizTalk Server para datos archivados o activos.  
  
 La consola de administración de BizTalk Server puede usarse para determinar los servicios que se encontraban activos cuando se recuperó el cuadro de mensajes. Ya que existe un lapso de tiempo entre el momento de recuperación de la base de datos y el tiempo del error de hardware, es posible que no pueda determinar el estado de algunas de las transacciones.  
  
 Los datos de seguimiento pueden usarse para identificar las instancias de servicio completadas e iniciadas después del punto de recuperación:  
  
- Busque las instancias completadas o iniciadas desde la última vez que se realizó una copia de seguridad de la base de datos.  
  
- Si los datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb) indican que el mensaje se ha iniciado pero no completado, y éste no se encuentra en la base de datos, entonces el mensaje se envió después de que se realizara la última copia de seguridad.  
  
  El seguimiento puede emitir un informe de cualquier servicio completado, así como indicar que un servicio se ha iniciado. Los datos de seguimiento se colocan, en una primera fase, en el cuadro de mensajes y, a continuación, se mueven a la base de datos de seguimiento de BizTalk. Es posible que se produzca la pérdida de estos datos en el trabajo acumulado del servicio de bus de sucesos BAM.  
  
  Mientras que, por razones operativas, es preciso que se efectúe la restauración de todas las bases de datos a la misma marca, se puede utilizar la base de datos de seguimiento de BizTalk (que no se perdió) en el modo de archivo para ver lo ocurrido después de la marca.  
  
  Si el seguimiento muestra una instancia de servicio como completada, podrá finalizar esta última. Es posible que muestre instancias iniciadas después del punto de recuperación. En este caso, tendrá que efectuar una compensación de las acciones que se llevaron a cabo en estas instancias y, seguidamente, volver a enviar sus mensajes de activación inicial.  
  
  Puede usar el depurador de orquestaciones para ver las últimas formas que se ejecutaron y, a continuación, usar Flujo de mensajes para ver los mensajes que se deberían haber enviado o recibido.  
  
  Si se produjo la pérdida de la base de datos de seguimiento, el descubrimiento de todo lo ocurrido después del punto de recuperación tendrá que efectuarse mediante mecanismos de elaboración de informes de sistemas externos.  
  
## <a name="see-also"></a>Vea también  
 [Resolver la pérdida de datos](../core/resolving-data-loss.md)