---
title: Interfaces para sincrónica compatible con lotes del adaptador de envío | Documentos de Microsoft
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
ms.openlocfilehash: 3ab61fd6624468e0464cfe0c648fcc868bd20005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257676"
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a>Interfaces de un adaptador de envío sincrónico compatible con lotes
Los adaptadores compatibles con lotes pueden enviar mensajes de forma sincrónica o asincrónica y pueden realizar operaciones de envío de transacción. Para enviar lotes de mensajes, un adaptador de envío debe implementar las interfaces siguientes:  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchTransmitter**  
  
-   **IBTTransmitterBatch**  
  
 Para el envío por lotes sincrónico, el motor de mensajería obtiene un lote del adaptador y agrega mensajes mediante para que se transmitan a ese lote. El motor de mensajería agrega cada mensaje al lote y envía los mensajes únicamente cuando llama a la **realiza** método en el lote. El adaptador devuelve `True` para **bDeleteMessage** para cada mensaje que intenta transmitir de forma sincrónica. El adaptador debe guardar los datos de mensaje, en lugar de un puntero de mensaje, en su **TransmitMessage** implementación. Esto es porque el puntero de mensaje ya no es válido tras `True` se devuelve y no se debe utilizar o almacenar en caché para su uso posterior.  
  
 La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío sincrónico compatible con lotes.  
  
 ![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")  
Flujo de trabajo para enviar un mensaje de manera sincrónica  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md)   
 [Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md)   
 [Interfaces de un envío sincrónico adaptador](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [Adaptador de envío de interfaces para una asincrónica](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [Interfaces de un adaptador de envío asíncrono compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces para un adaptador de envío asincrónica transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces para una petición-respuesta del adaptador de envío](../core/interfaces-for-a-solicit-response-send-adapter.md)