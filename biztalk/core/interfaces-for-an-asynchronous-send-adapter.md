---
title: Interfaces de un envío asincrónico adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a214716-8f39-400d-a111-ba1b92a284b4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd90aa9c5d010acc4d73a66220964ebdcb31e1f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980357"
---
# <a name="interfaces-for-an-asynchronous-send-adapter"></a>Interfaces de un adaptador de envío asíncrono
Los adaptadores que envían mensajes de uno en uno pueden enviar mensajes de forma sincrónica o asíncrona. Un adaptador envía mensajes de forma asíncrona cuando no bloquea el subproceso del proxy de transporte pero, en su lugar, utiliza un subproceso distinto al realizar operaciones de envío. Para poder enviar mensajes de forma asíncrona, un adaptador necesita implementar las interfaces siguientes:  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTTransmitter**  
  
  Los siguientes pasos describen la secuencia de acciones que realiza un adaptador de envío para transmitir mensajes fuera del servidor a petición del motor de mensajería:  
  
1.  El motor de mensajería usa el proxy de transporte para pasar un mensaje saliente a un adaptador de envío mediante una llamada a la **TransmitMessage** método de la **IBTTransmitter** interfaz.  
  
2.  El adaptador devuelve inmediatamente desde **TransmitMessage** después de almacenar el mensaje que se enviará a alguna cola interna y devuelve `False` para **bDeleteMessage**. Esto indica al motor de mensajería que el mensaje se transmitirá de forma asíncrona.  
  
3.  El adaptador envía el mensaje mediante su propio grupo de subprocesos.  
  
4.  Cuando la operación de envío se completa, el adaptador elimina el mensaje original de la base de datos de cuadro de mensajes. Obtiene un lote desde el motor de mensajería mediante el **IBTTransportBatch.GetBatch** método de proxy de transporte y, a continuación, llama a **DeleteMessage**.  
  
     La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío asíncrono.  
  
     ![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")  
Flujo de trabajo para enviar un mensaje de forma asíncrona  
  
> [!NOTE]
>  Se recomienda que el adaptador realice un recuento de los mensajes cuyo procesamiento está en curso. El adaptador debe bloquear la **Terminate** método hasta que llegue a cero el número de mensajes. En el caso de los adaptadores de envío, los mensajes cuyo proceso está en curso deberían controlarse de forma adecuada. Esto significa que cualquier mensaje entregado correctamente de forma asíncrona debe eliminarse de la cola privada de mensajes de la aplicación del adaptador para evitar que se envíe dos veces. En general, después **Terminate** es llamado por el motor de mensajería no acepta solicitudes para publicar nuevos mensajes desde el adaptador. La excepción a esto son los mensajes de respuesta relacionados con los pares petición-respuesta.  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md)   
 [Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md)   
 [Interfaces para un valor sincrónico del adaptador de envío](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [Interfaces de un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío asincrónico compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío asincrónico transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío de petición-respuesta](../core/interfaces-for-a-solicit-response-send-adapter.md)