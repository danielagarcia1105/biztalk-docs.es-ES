---
title: Correlacionar mensajes mediante procedimientos de solicitud-respuesta | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, MQSeries adapters
- messages, correlating
- MQSeries adapters, correlating messages
ms.assetid: 4615b586-663b-41d8-949c-fefb6143c590
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2f13d8dea9192e982f597311ca3ea13fa213ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237996"
---
# <a name="correlating-messages-using-request-reply"></a><span data-ttu-id="9b53a-102">Correlacionar mensajes mediante procedimientos de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="9b53a-102">Correlating Messages Using Request-Reply</span></span>
<span data-ttu-id="9b53a-103">Hay dos formas de correlacionar mensajes en orquestaciones de BizTalk para IBM WebSphere MQ, componente Servidor para escenarios de plataformas solicitud-respuesta de Windows.</span><span class="sxs-lookup"><span data-stu-id="9b53a-103">There are two ways to correlate messages in BizTalk orchestrations for IBM WebSphere MQ, server component for Windows platforms request-reply scenarios.</span></span> <span data-ttu-id="9b53a-104">La primera consiste en proporcionar el identificador de correlación, configuración de MessageID (**MQMD_MSGID**) y CorrelationID (**MQMD_CorrelId**) en el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="9b53a-104">The first is to supply the correlation identifier by setting both the MessageID (**MQMD_MSGID**) and the CorrelationID (**MQMD_CorrelId**) to the same value.</span></span> <span data-ttu-id="9b53a-105">El segundo consiste en usar la **BizTalk_CorrelationId** propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="9b53a-105">The second is to use the **BizTalk_CorrelationId** context property.</span></span>  
  
## <a name="setting-mqmdmsgid-and-mqmdcorrelid-to-the-same-value"></a><span data-ttu-id="9b53a-106">Establecer MQMD_MsgId y MQMD_CorrelId con el mismo valor</span><span class="sxs-lookup"><span data-stu-id="9b53a-106">Setting MQMD_MsgId and MQMD_CorrelId to the Same value</span></span>  
 <span data-ttu-id="9b53a-107">Al enviar el mensaje a un administrador de cola de IBM WebSphere MQ, puede establecer el identificador de mensaje (**MQMD_MSGID**) y el identificador de correlación (**MQMD_CorrelId**) en el mismo valor en el mensaje saliente .</span><span class="sxs-lookup"><span data-stu-id="9b53a-107">When sending the message to an IBM WebSphere MQ Queue Manager, you can set the message identifier (**MQMD_MSGID**) and the correlation identifier (**MQMD_CorrelId**) to the same value in the outgoing message.</span></span> <span data-ttu-id="9b53a-108">El administrador de cola de IBM WebSphere MQ copia el MessageID al CorrelationID para el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9b53a-108">The IBM WebSphere MQ Queue Manager copies the MessageID to the CorrelationID for the reply message.</span></span> <span data-ttu-id="9b53a-109">En la siguiente ilustración muestra el proceso.</span><span class="sxs-lookup"><span data-stu-id="9b53a-109">The following figure shows the process.</span></span>  
  
 <span data-ttu-id="9b53a-110">![Correlación simple](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")</span><span class="sxs-lookup"><span data-stu-id="9b53a-110">![Simple Correlation](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")</span></span>  
  
 <span data-ttu-id="9b53a-111">Puede inicializar los conjuntos de correlaciones para el mensaje saliente y el seguimiento de los conjuntos de correlaciones para el mensaje entrante con el valor de **MQMD_CorrelId**.</span><span class="sxs-lookup"><span data-stu-id="9b53a-111">You can initialize the correlation sets for the outgoing message and follow the correlation sets for the incoming message using the value of **MQMD_CorrelId**.</span></span>  
  
## <a name="using-the-mqseriesbiztalkcorrelationid-context-property"></a><span data-ttu-id="9b53a-112">Utilizar la propiedad de contexto MQSeries.BizTalk CorrelationId</span><span class="sxs-lookup"><span data-stu-id="9b53a-112">Using the MQSeries.BizTalk_CorrelationId Context Property</span></span>  
 <span data-ttu-id="9b53a-113">En lugar de establecer MessageID y CorrelationID con el mismo valor en el mensaje saliente, puede usar el **BizTalk_CorrelationID** puerto del adaptador de MQSeries de envío de la propiedad de contexto con una petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="9b53a-113">Instead of setting the MessageID and CorrelationID to the same value in the outgoing message, you can use the **BizTalk_CorrelationID** context property with a solicit-response send port of the MQSeries adapter.</span></span> <span data-ttu-id="9b53a-114">En la ilustración siguiente se muestra este proceso.</span><span class="sxs-lookup"><span data-stu-id="9b53a-114">The following figure shows this process.</span></span>  
  
 <span data-ttu-id="9b53a-115">![Uso de petición-respuesta &#45; Respuesta para generar CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")</span><span class="sxs-lookup"><span data-stu-id="9b53a-115">![Using Solicit&#45;Response to generate CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")</span></span>  
  
 <span data-ttu-id="9b53a-116">Para utilizar identificadores proporcionados por IBM WebSphere MQ Server para correlaciones en su orquestación de BizTalk, es necesario que BizTalk Server obtenga primero el identificador.</span><span class="sxs-lookup"><span data-stu-id="9b53a-116">To use identifiers provided by IBM WebSphere MQ Server for correlations in your BizTalk orchestration, BizTalk Server must first obtain the identifier.</span></span> <span data-ttu-id="9b53a-117">Su aplicación lo obtiene mediante una solicitud Petición- Respuesta.</span><span class="sxs-lookup"><span data-stu-id="9b53a-117">Your application does this through a solicit-response request.</span></span> <span data-ttu-id="9b53a-118">BizTalk Server envía una solicitud Petición – Respuesta a IBM WebSphere MQ Server mediante el adaptador de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="9b53a-118">BizTalk Server sends a solicit-response request to the IBM WebSphere MQ Server by using the MQSeries adapter.</span></span> <span data-ttu-id="9b53a-119">En cambio, recibe una respuesta con el identificador de mensaje (**MQMD_MSGId**) y el identificador de correlación (**MQMD_CorrelId**).</span><span class="sxs-lookup"><span data-stu-id="9b53a-119">In return, it receives a response with the message identifier (**MQMD_MSGId**) and the correlation identifier (**MQMD_CorrelId**).</span></span>  
  
 <span data-ttu-id="9b53a-120">Para el mensaje saliente en un puerto de envío de petición-respuesta, el adaptador copia el **MQMD_MSGID** generados por IBM WebSphere MQ Server en el **MQSeries.BizTalk_CorrelationId** propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="9b53a-120">For the outgoing message in a solicit-response send port, the adapter copies the **MQMD_MSGID** generated by IBM WebSphere MQ Server to the **MQSeries.BizTalk_CorrelationId** context property.</span></span>  
  
 <span data-ttu-id="9b53a-121">Al recibir mensajes, el adaptador copia el **MQMD_CorrelId** a la **MQSeries.BizTalk_CorrelationId**.</span><span class="sxs-lookup"><span data-stu-id="9b53a-121">When receiving messages, the adapter copies the **MQMD_CorrelId** to the **MQSeries.BizTalk_CorrelationId**.</span></span> <span data-ttu-id="9b53a-122">En este caso, mediante conjuntos de correlaciones, puede inicializar los conjuntos de correlaciones para el mensaje saliente y el seguimiento de los conjuntos de correlaciones para el mensaje entrante mediante el **MQSeries.BizTalk_CorrelationId**.</span><span class="sxs-lookup"><span data-stu-id="9b53a-122">In this case, using correlation sets, you can initialize the correlation sets for the outgoing message and follow the correlation sets for the incoming message using the **MQSeries.BizTalk_CorrelationId**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b53a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b53a-123">See Also</span></span>  
 [<span data-ttu-id="9b53a-124">MQSCorrelationSetOrchestrationWithSolicitResponse (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="9b53a-124">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server Sample)</span></span>](../core/mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample.md)