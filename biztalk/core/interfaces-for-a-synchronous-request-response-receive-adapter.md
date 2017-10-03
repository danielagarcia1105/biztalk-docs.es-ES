---
title: "Interfaces para una solicitud-respuesta sincrónico del adaptador de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0c60832-52b5-4d2c-81ec-94c46c375b15
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9abd84bab5da623c2dff61c6e07a5898110588af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-synchronous-request-response-receive-adapter"></a>Interfaces de un adaptador de recepción sincrónico de solicitud-respuesta
Todos los adaptadores de recepción necesitan implementar las interfaces siguientes para funcionar en modo de solicitud-respuesta.  
  
-   **IBTTransport**  
  
-   **IBTTransportControl** (solo adaptadores normales)  
  
-   **IBTTransportConfig**  
  
-   **IBaseComponent**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchCallBack**  
  
-   **IBTTransmitter**  
  
 Los adaptadores de recepción que admiten protocolos de solicitud-respuesta (por ejemplo, el adaptador de recepción HTTP) llevan a cabo las acciones siguientes al enviar mensajes de solicitud:  
  
1.  El adaptador de recepción recibe los mensajes de solicitud entrantes. Obtiene un lote del proxy de transporte mediante una llamada a la **GetBatch** método de la **IBTTransportProxy** interfaz. En esta llamada el adaptador pasa un puntero de devolución de llamada para su implementación de la **IBTBatchCallBack.BatchComplete** método.  
  
2.  El adaptador agrega mensajes de solicitud en el lote mediante una llamada a la **SubmitRequestMessage** método de la **IBTTransportBatch** interfaz, una vez para cada mensaje de solicitud.  
  
3.  Cuando se han agregado todos los mensajes, el adaptador llama a la **realiza**método de la **IBTTransportBatch** interfaz, que envía el lote al motor de mensajería a través del proxy de transporte.  
  
4.  Una vez que se ha procesado el lote, el motor de mensajería invoca el adaptador **IBTBatchCallBack.BatchComplete** método de devolución de llamada a través del proxy de transporte. El estado del envío se pasa al adaptador en forma de matriz de valores HRESULT correspondientes a cada mensaje del lote. Si se produce un error en el lote, ya sea en la canalización o en la orquestación, se devuelve al adaptador el mensaje de error SOAP como respuesta.  
  
5.  Los mensajes de solicitud entrantes pueden tener suscriptores de orquestaciones. Después de finalizar la orquestación y se ha procesado el mensaje de solicitud, el motor de mensajería envía el mensaje de respuesta a través del proxy de transporte para el adaptador mediante una llamada del adaptador **TransmitMessage** método desde el  **IBTTransmitter** interfaz.  
  
6.  El adaptador envía un mensaje de respuesta y elimina el mensaje original de la base de datos de cuadro de mensajes.  
  
 La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de recepción sincrónico de solicitud-respuesta.  
  
 ![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")  
Flujo de trabajo de un adaptador de recepción que envía un mensaje sincrónico  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de recepción](../core/developing-a-receive-adapter.md)   
 [Crear instancias e inicializar un adaptador de recepción](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [Interfaces para un proceso en el adaptador de recepción](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [Adaptador de recepción de interfaces para un aislado](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [Adaptador de recepción de interfaces para un compatible con lotes](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [Adaptador de recepción de interfaces para transaccional compatible con lotes](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)