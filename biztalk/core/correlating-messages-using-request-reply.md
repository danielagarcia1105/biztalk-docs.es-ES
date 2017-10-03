---
title: Correlacionar mensajes mediante procedimientos de solicitud-respuesta | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MQSeries adapters
- messages, correlating
- MQSeries adapters, correlating messages
ms.assetid: 4615b586-663b-41d8-949c-fefb6143c590
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2f13d8dea9192e982f597311ca3ea13fa213ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="correlating-messages-using-request-reply"></a>Correlacionar mensajes mediante procedimientos de solicitud-respuesta
Hay dos formas de correlacionar mensajes en orquestaciones de BizTalk para IBM WebSphere MQ, componente Servidor para escenarios de plataformas solicitud-respuesta de Windows. La primera consiste en proporcionar el identificador de correlación, configuración de MessageID (**MQMD_MSGID**) y CorrelationID (**MQMD_CorrelId**) en el mismo valor. El segundo consiste en usar la **BizTalk_CorrelationId** propiedad de contexto.  
  
## <a name="setting-mqmdmsgid-and-mqmdcorrelid-to-the-same-value"></a>Establecer MQMD_MsgId y MQMD_CorrelId con el mismo valor  
 Al enviar el mensaje a un administrador de cola de IBM WebSphere MQ, puede establecer el identificador de mensaje (**MQMD_MSGID**) y el identificador de correlación (**MQMD_CorrelId**) en el mismo valor en el mensaje saliente . El administrador de cola de IBM WebSphere MQ copia el MessageID al CorrelationID para el mensaje de respuesta. En la siguiente ilustración muestra el proceso.  
  
 ![Correlación simple](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")  
  
 Puede inicializar los conjuntos de correlaciones para el mensaje saliente y el seguimiento de los conjuntos de correlaciones para el mensaje entrante con el valor de **MQMD_CorrelId**.  
  
## <a name="using-the-mqseriesbiztalkcorrelationid-context-property"></a>Utilizar la propiedad de contexto MQSeries.BizTalk CorrelationId  
 En lugar de establecer MessageID y CorrelationID con el mismo valor en el mensaje saliente, puede usar el **BizTalk_CorrelationID** puerto del adaptador de MQSeries de envío de la propiedad de contexto con una petición-respuesta. En la ilustración siguiente se muestra este proceso.  
  
 ![Uso de petición-respuesta &#45; Respuesta para generar CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")  
  
 Para utilizar identificadores proporcionados por IBM WebSphere MQ Server para correlaciones en su orquestación de BizTalk, es necesario que BizTalk Server obtenga primero el identificador. Su aplicación lo obtiene mediante una solicitud Petición- Respuesta. BizTalk Server envía una solicitud Petición – Respuesta a IBM WebSphere MQ Server mediante el adaptador de MQSeries. En cambio, recibe una respuesta con el identificador de mensaje (**MQMD_MSGId**) y el identificador de correlación (**MQMD_CorrelId**).  
  
 Para el mensaje saliente en un puerto de envío de petición-respuesta, el adaptador copia el **MQMD_MSGID** generados por IBM WebSphere MQ Server en el **MQSeries.BizTalk_CorrelationId** propiedad de contexto.  
  
 Al recibir mensajes, el adaptador copia el **MQMD_CorrelId** a la **MQSeries.BizTalk_CorrelationId**. En este caso, mediante conjuntos de correlaciones, puede inicializar los conjuntos de correlaciones para el mensaje saliente y el seguimiento de los conjuntos de correlaciones para el mensaje entrante mediante el **MQSeries.BizTalk_CorrelationId**.  
  
## <a name="see-also"></a>Vea también  
 [MQSCorrelationSetOrchestrationWithSolicitResponse (ejemplo de BizTalk Server)](../core/mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample.md)