---
title: "Interfaces para una petición-respuesta del adaptador de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c54650e8-dbfb-4c66-843b-0b82c8183dd4
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb8ce9b625bfea144f9a4a615a604efdbe2a3cb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a>Interfaces de un adaptador de envío de petición-respuesta
Los adaptadores de envío utilizan el mismo mecanismo de lotes que los adaptadores de recepción para enviar mensajes de respuesta al servidor.  
  
> [!NOTE]
>  Se recomienda que el adaptador Petición-Respuesta procese mensajes de forma asincrónica. Si el adaptador procesa mensajes de manera sincrónica, se corre el riesgo de que se dupliquen los mensajes.  
  
 Los adaptadores de envío necesitan implementar las interfaces siguientes para funcionar en modo de Petición-Respuesta.  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTTransmitter**  
  
-   **IBTTransmitterBatch** y **IBTBatchTransmitter** (si es necesario el procesamiento por lotes de envío)  
  
-   **IBTBatchCallBack**  
  
 Los pasos que conlleva la interacción de objetos se muestran a continuación:  
  
1.  Cuando el adaptador envía un mensaje de petición, recibe un mensaje de respuesta del servidor de destino. A continuación, obtiene un lote del proxy de transporte.  
  
2.  El adaptador agrega el mensaje de respuesta al lote mediante una llamada a **ibttransportproxy:: Submitresponsemessage**.  
  
3.  El adaptador envía el lote mediante una llamada a **ibttransportproxy:: Done** pasando un puntero a su **IBTBatchComplete** interfaz para la devolución de llamada del motor de mensajería.  
  
4.  El motor de mensajería llama el adaptador **ibtbatchcallback::** método de devolución de llamada mediante el proxy de transporte que se le notifica que el resultado de la operación de envío.  
  
 La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío Petición-Respuesta.  
  
 ![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")  
Diagrama de interacción para un adaptador de envío Petición-Respuesta  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md)   
 [Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md)   
 [Interfaces de un envío sincrónico adaptador](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [Adaptador de envío de interfaces para una asincrónica](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [Interfaces para un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [Interfaces de un adaptador de envío asíncrono compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [Interfaces para un adaptador de envío asincrónica transaccional compatible con lotes](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)