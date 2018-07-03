---
title: Interfaces para asincrónico compatible con lotes del adaptador de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d38b8b87-508a-499b-86b2-846938050b44
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc579995821a97dc588b2221f8a7dd2e9cd1e136
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993021"
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a>Interfaces de un adaptador de envío asíncrono compatible con lotes
Los adaptadores compatibles con lotes pueden enviar mensajes de forma sincrónica o asincrónica y pueden realizar envíos de transacción. Para enviar lotes de mensajes, un adaptador de envío debe implementar las interfaces siguientes:  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchTransmitter**  
  
- **IBTTransmitterBatch**  
  
  Para el envío por lotes asíncrono, el motor de mensajería obtiene un lote del adaptador y agrega mensajes mediante para que se transmitan a ese lote. Los mensajes se envían solo cuando el motor de mensajería llama a la **realiza** método en el lote. El adaptador devuelve `False` para cada mensaje que intenta transmitir de forma asincrónica. A continuación, el adaptador obtiene un lote desde el proxy del adaptador y elimina aquellos mensajes que ha transmitido correctamente.  
  
  La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío asíncrono compatible con lotes.  
  
  ![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")  
  Flujo de trabajo para enviar un mensaje de forma asíncrona  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md)   
 [Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md)   
 [Interfaces para un valor sincrónico del adaptador de envío](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [Interfaces para asincrónico del adaptador de envío](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [Interfaces de un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío asincrónico transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío de petición-respuesta](../core/interfaces-for-a-solicit-response-send-adapter.md)