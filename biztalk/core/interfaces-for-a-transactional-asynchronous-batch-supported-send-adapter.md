---
title: Interfaces de un adaptador de envío asincrónico transaccional compatible con lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5b2dbdf-e6ba-4b58-a0a5-fc78feaf5c35
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c3ad79f09563b3e65ccfab64da5b9ec6ea3033c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982901"
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a>Interfaces de un adaptador de envío asíncrono transaccional compatible con lotes
Un adaptador de envío puede crear y controlar transacciones cuando se necesite la transmisión transaccional de mensajes. Para admitir el envío transaccional, un adaptador debe implementar las interfaces siguientes:  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchTransmitter**  
  
- **IBTTransmitterBatch**  
  
- **IBTBatchCallBack**  
  
  Un adaptador crea una transacción MSDTC y devuelve un puntero a ese objeto en la llamada a la **BeginBatch** método de la **IBTTransmitterBatch** interfaz. El motor de mensajería llama a ese método para obtener un lote con el que envía mensajes salientes al adaptador de envío. Cuando el adaptador finalice la operación de envío y se confirma o revierte una transacción, notifica el motor de mensajería del resultado de la transacción mediante el uso de la **DTCCommitConfirm** método de la **IBTDTCCommitConfirm**  interfaz.  
  
  En la siguiente ilustración se muestra la interacción entre el proxy de transporte y el adaptador de envío al realizar una operación de envío transaccional.  
  
  ![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")  
  Flujo de trabajo para enviar un mensaje transaccional de forma asincrónica  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md)   
 [Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md)   
 [Interfaces para un valor sincrónico del adaptador de envío](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [Interfaces para asincrónico del adaptador de envío](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [Interfaces de un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío asincrónico compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío de petición-respuesta](../core/interfaces-for-a-solicit-response-send-adapter.md)