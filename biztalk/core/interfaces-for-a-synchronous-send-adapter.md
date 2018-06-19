---
title: Interfaces de un envío sincrónico adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e1b397a-3a35-4447-8522-d8a5f39a42d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1012b52bf5c6ab564cc219926b97445e43f60dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256916"
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a>Interfaces de un adaptador de envío sincrónico
Un adaptador envía mensajes de manera sincrónica cuando bloquea el subproceso de llamada del motor de mensajería entrante mientras realiza su operación de envío. Para poder enviar mensajes de manera sincrónica, un adaptador necesita implementar las interfaces siguientes:  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTTransmitter**  
  
 En un envío sincrónico, el adaptador envía el mensaje mientras bloquea **TransmitMessage**, y después devuelve transmisión correcta`True.`  
  
 La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío sincrónico.  
  
 ![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")  
Flujo de trabajo para enviar un mensaje de forma sincrónica  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md)   
 [Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md)   
 [Adaptador de envío de interfaces para una asincrónica](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [Interfaces para un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío asíncrono compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces para un adaptador de envío asincrónica transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces para una petición-respuesta del adaptador de envío](../core/interfaces-for-a-solicit-response-send-adapter.md)