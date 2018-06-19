---
title: Uso de canalizaciones desde el servicio solución orientada a servicios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, pipelines
- pipelines, service solutions
ms.assetid: 0870fce1-52ec-4ff8-884f-a3199bd7ccbb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d6b8021a22db366b31cde26abdc3ef48f3e51a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287212"
---
# <a name="using-pipelines-from-the-service-oriented-solution"></a>Uso de canalizaciones desde el servicio solución orientada a servicios
La versión en línea de la orquestación de atención al cliente (**CustomerService**) llama el pago al sistema de seguimiento directamente. Para preparar el mensaje de envío y procesar el mensaje recibido, la orquestación llama a las canalizaciones desde el código. Esto permite la reutilización de las canalizaciones desde las otras versiones de escenarios. También mantiene la separación de la orquestación desde las fases de canalización.  
  
## <a name="calling-the-pipelines"></a>Llamar a las canalizaciones  
 Para utilizar las canalizaciones desde el código, debe crear una colección de mensajes, agregar el mensaje que vaya a procesar a la colección, crear un mensaje vacío para recibir el mensaje resultante e invocar la canalización.  
  
 El siguiente código de la **CustomerService** orquestación se encuentra en la **ConstructRequestMessageAfterSendPipeline** forma:  
  
```  
// Create the collection of messages to be sent to the send pipeline...  
sendPipelineInputMessages =   
    new Microsoft.XLANGs.Pipeline.SendPipelineInputMessages();  
sendPipelineInputMessages.Add(LastPaymentRequest);  
  
// Create an empty message for the output from the pipeline...  
LastPaymentRequestAfterSendPipeline = null;  
  
// Execute the send pipeline and get the message output from   
// the send pipeline.  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.  
    ExecuteSendPipeline(  
        typeof(  
            Microsoft.Samples.BizTalk.  
                WoodgroveBank.PaymentTrackerPipelines.  
                    PaymentTrackerSendPipeline  
        ),  
        sendPipelineInputMessages,  
        LastPaymentRequestAfterSendPipeline  
    );  
```  
  
 El **GetLastPaymentResponse** forma toma el mensaje en el código anterior, lo envía en el sistema de seguimiento de pagos y procesa el mensaje devuelto a través de la canalización de recepción:  
  
```  
// Execute the inline method to send the message to the   
// Payment Tracking System and get the response.  
// The response message received should be passed through the   
// receive pipeline.  
  
LastPaymentResponseBeforeReceivePipeline =   
    Microsoft.Samples.BizTalk.  
        WoodgroveBank.  
            PaymentTrackerCall.  
                PaymentTrackerCaller.  
                    GetPaymeTrackerResponse  
                    (  
                        LastPaymentRequestAfterSendPipeline  
                    );   
  
// Execute the receive pipeline using the helper class so that we don't  
// need to declare the non-serializable types involved.  
  
// Set the documentspec name so the xml disassembler in the   
// pipeline can resolve the schemas for the received message  
// without ambiguity.  
LastPaymentResponseBeforeReceivePipeline(XMLNORM.DocumentSpecName) =   
"Microsoft.Samples.BizTalk.WoodgroveBank.Schemas.LastPaymentResponse, Microsoft.Samples.BizTalk.WoodgroveBank.Schemas, Version=1.0.0.0, Culture=neutral, PublicKeyToken=5f57a322d27bc5fb";  
// Create an empty response message and fill it in with the   
// real response from the Payment Tracking System  
LastPaymentResponse = null;  
  
Microsoft.Samples.BizTalk.WoodgroveBank.Utilities.  
    ReceivePipelineHelper.CallReceivePipeLine (  
        typeof(  
            Microsoft.Samples.BizTalk.WoodgroveBank.  
                PaymentTrackerPipelines.PaymentTrackerReceivePipeline  
            ),  
            LastPaymentResponseBeforeReceivePipeline,  
            LastPaymentResponse  
        );  
```  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación del servicio en la solución orientada a servicios](../core/implementation-highlights-of-the-service-oriented-solution.md)