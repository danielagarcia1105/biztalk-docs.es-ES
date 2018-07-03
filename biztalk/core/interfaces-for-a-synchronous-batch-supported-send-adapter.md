---
title: Interfaces para un valor sincrónico compatible con lotes del adaptador de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b191c41-ca4f-4d2b-bd15-a93ad87a743d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d14e278869854535695babc9ff8796a833de7217
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968229"
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a>Interfaces de un adaptador de envío sincrónico compatible con lotes
Los adaptadores compatibles con lotes pueden enviar mensajes de forma sincrónica o asincrónica y pueden realizar operaciones de envío de transacción. Para enviar lotes de mensajes, un adaptador de envío debe implementar las interfaces siguientes:  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchTransmitter**  
  
- **IBTTransmitterBatch**  
  
  Para el envío por lotes sincrónico, el motor de mensajería obtiene un lote del adaptador y agrega mensajes mediante para que se transmitan a ese lote. El motor de mensajería agrega cada mensaje al lote y envía los mensajes solo cuando se llama a la **realiza** método en el lote. El adaptador devuelve `True` para **bDeleteMessage** para cada mensaje que intenta transmitir de forma sincrónica. El adaptador debe guardar los datos de mensaje, en lugar de un puntero de mensaje, en su **TransmitMessage** implementación. Esto es porque el puntero del mensaje ya no es válido tras `True` se devuelve y no deben usar o almacenar en caché para su uso posterior.  
  
  La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío sincrónico compatible con lotes.  
  
  ![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")  
  Flujo de trabajo para enviar un mensaje de manera sincrónica  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md)   
 [Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md)   
 [Interfaces para un valor sincrónico del adaptador de envío](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [Interfaces para asincrónico del adaptador de envío](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [Interfaces de un adaptador de envío asincrónico compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío asincrónico transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío de petición-respuesta](../core/interfaces-for-a-solicit-response-send-adapter.md)