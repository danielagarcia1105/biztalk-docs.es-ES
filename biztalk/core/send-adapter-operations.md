---
title: "Operaciones del adaptador de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf4e0430-e3dc-4884-8411-bbcb579bd21e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 444cf4ab7958b0d44838a8331b4b9e6a467baedc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="send-adapter-operations"></a><span data-ttu-id="80fc1-102">Operaciones del adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="80fc1-102">Send Adapter Operations</span></span>
<span data-ttu-id="80fc1-103">Los adaptadores de envío pueden realizar las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="80fc1-103">Send adapters can perform the following operations:</span></span>  
  
-   <span data-ttu-id="80fc1-104">**Vuelva a intentarlo: anular reenviar (mensaje de IBaseMessage, marca de tiempo de fecha y hora).**</span><span class="sxs-lookup"><span data-stu-id="80fc1-104">**Resubmit: void Resubmit(IBaseMessage msg, DateTime timeStamp).**</span></span> <span data-ttu-id="80fc1-105">Cuando se produce un error de transmisión en un mensaje, un adaptador lo reenvía cuando sea conveniente.</span><span class="sxs-lookup"><span data-stu-id="80fc1-105">After a transmission failure occurs on a message, an adapter resubmits it when appropriate.</span></span> <span data-ttu-id="80fc1-106">La llamada a este elemento se efectúa por cada uno de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="80fc1-106">This is called on a per-message basis.</span></span> <span data-ttu-id="80fc1-107">Si un lote de mensajes se envían correctamente, el adaptador debe determinar los mensajes que han provocado el error y reenviar los que no se han provocado el lote a un error en las llamadas independientes a **reenviar**.</span><span class="sxs-lookup"><span data-stu-id="80fc1-107">If a batch of messages was submitted unsuccessfully, the adapter must determine the messages causing the failure, and resubmit the ones that did not cause the batch to fail in separate calls to **Resubmit**.</span></span> <span data-ttu-id="80fc1-108">No hay información al final de este tema sobre cómo mantener valores de propiedad de contexto de mensaje cuando se llama a **reenviar**.</span><span class="sxs-lookup"><span data-stu-id="80fc1-108">There is information at the end of this topic about how to preserve message context property values when you call **Resubmit**.</span></span>  
  
-   <span data-ttu-id="80fc1-109">**Pasar al siguiente transporte: void MoveToNextTransport (IBaseMessage msg).**</span><span class="sxs-lookup"><span data-stu-id="80fc1-109">**Move to Next Transport: void MoveToNextTransport(IBaseMessage msg).**</span></span> <span data-ttu-id="80fc1-110">Si se producen errores en un mensaje durante la operación de envío y se han agotado los reintentos, el adaptador puede enviar el mensaje al siguiente transporte que se ha configurado para la retransmisión.</span><span class="sxs-lookup"><span data-stu-id="80fc1-110">If a message fails during a send operation and its retry attempts have been exhausted, the adapter can send the message to the next configured transport for retransmission.</span></span>  
  
-   <span data-ttu-id="80fc1-111">**Suspender: void MoveToSuspendQ (IBaseMessage msg).**</span><span class="sxs-lookup"><span data-stu-id="80fc1-111">**Suspend: void MoveToSuspendQ(IBaseMessage msg).**</span></span> <span data-ttu-id="80fc1-112">Si no se ha configurado un transporte de reserva adicional, el adaptador mueve un mensaje de envío con errores a la cola de suspensión.</span><span class="sxs-lookup"><span data-stu-id="80fc1-112">The adapter moves a failed send message to the Suspended queue if no additional backup transport is configured.</span></span> <span data-ttu-id="80fc1-113">No hay información al final de este tema sobre cómo mantener valores de propiedad de contexto de mensaje cuando se llama a **Suspend**.</span><span class="sxs-lookup"><span data-stu-id="80fc1-113">There is information at the end of this topic about how to preserve message context property values when you call **Suspend**.</span></span>  
  
-   <span data-ttu-id="80fc1-114">**Delete: void DeleteMessage (IBaseMessage msg).**</span><span class="sxs-lookup"><span data-stu-id="80fc1-114">**Delete: void DeleteMessage(IBaseMessage msg).**</span></span> <span data-ttu-id="80fc1-115">El adaptador elimina un mensaje después de que BizTalk Server le haya notificado que la transmisión se ha realizado de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="80fc1-115">The adapter deletes a message after being notified by BizTalk Server of its successful transmission.</span></span> <span data-ttu-id="80fc1-116">Al eliminar un mensaje se le comunica a BizTalk Server que el adaptador ha finalizado con el mensaje.</span><span class="sxs-lookup"><span data-stu-id="80fc1-116">Deleting a message tells BizTalk Server that the adapter is finished with the message.</span></span> <span data-ttu-id="80fc1-117">Por lo general el **SubmitResponse** operación se realiza en el mismo lote que está asociada **eliminar** operación.</span><span class="sxs-lookup"><span data-stu-id="80fc1-117">Generally the **SubmitResponse** operation is done in the same batch as its associated **Delete** operation.</span></span>  
  
-   <span data-ttu-id="80fc1-118">**Enviar respuesta: void SubmitResponseMessage (IBaseMessage solicitMsgSent, IBaseMessage responseMsgToSubmit).**</span><span class="sxs-lookup"><span data-stu-id="80fc1-118">**Submit Response: void SubmitResponseMessage(IBaseMessage solicitMsgSent, IBaseMessage responseMsgToSubmit).**</span></span> <span data-ttu-id="80fc1-119">El adaptador envía una respuesta al lote que se va a enviar de vuelta a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="80fc1-119">The adapter submits a response to the batch to be sent back to BizTalk Server.</span></span> <span data-ttu-id="80fc1-120">Esta operación incluye en la llamada el mensaje original junto con la respuesta para que BizTalk Server pueda correlacionarlas.</span><span class="sxs-lookup"><span data-stu-id="80fc1-120">This operation includes the original message in the call along with the response so that BizTalk Server can correlate them.</span></span>  
  
-   <span data-ttu-id="80fc1-121">**Cancelar respuesta: void CancelResponseMessages (string correlationToken).**</span><span class="sxs-lookup"><span data-stu-id="80fc1-121">**Cancel Response: void CancelResponseMessages(string correlationToken).**</span></span> <span data-ttu-id="80fc1-122">Si el envío de un mensaje de respuesta debe cancelarse antes de que se envíe el lote, el **CancelResponseMessages** se usa el método, pasando el token de correlación para el mensaje de respuesta asociado va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="80fc1-122">If the sending of a response message needs to be canceled before the batch is submitted, the **CancelResponseMessages** method is used, passing in the correlation token for the associated response message to be deleted.</span></span>  
  
 <span data-ttu-id="80fc1-123">Al llamar a **reenviar** o **Suspend** en un mensaje que se desea conservar los valores de determinadas propiedades de contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="80fc1-123">When calling **Resubmit** or **Suspend** on a message you may want to preserve the values of certain message context properties.</span></span> <span data-ttu-id="80fc1-124">Puede hacerlo si guarda los valores de propiedad en formato XML.</span><span class="sxs-lookup"><span data-stu-id="80fc1-124">You can do this by saving property values in XML format.</span></span> <span data-ttu-id="80fc1-125">Cuando se reenvía o se suspende el mensaje, las propiedades correspondientes permanecen disponibles en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="80fc1-125">When the message is resubmitted or suspended the corresponding properties remain available in the message context.</span></span>  
  
 <span data-ttu-id="80fc1-126">La siguiente cadena XML describe el formato en el que se almacena la información:</span><span class="sxs-lookup"><span data-stu-id="80fc1-126">The following XML string describes the format in which the information is stored:</span></span>  
  
```  
<PropertiesToUpdate>  
<Property name="StringProperty" nameSpace="http://MyNamespace1" vt="8">SomeString</Property>  
<Property name="IntProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="3">4</Property>  
<Property name="BoolProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="11">0</Property>  
</PropertiesToUpdate>  
```  
  
 <span data-ttu-id="80fc1-127">El código que aparece a continuación es el que genera la cadena XML:</span><span class="sxs-lookup"><span data-stu-id="80fc1-127">This XML string is generated by the following code:</span></span>  
  
```  
private string GetPropsToUpdateXml(int nextRetryAttempt)  
{  
string result = "<PropertiesToUpdate><Property name=\"RetryAttempts\" nameSpace=\"http://schemas.microsoft.com/BizTalk/2005/test-properties\" vt=\"3\">" + nextRetryAttempt.ToString() + "</Property></PropertiesToUpdate>";  
return result;  
}  
```  
  
 <span data-ttu-id="80fc1-128">A continuación, la cadena se guarda en el contexto del mensaje utilizando el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="80fc1-128">This string is then saved to the message context by using this code:</span></span>  
  
```  
Message.Context.Write("PropertiesToUpdate", "http://schemas.microsoft.com/BizTalk/2003/system-properties", GetPropsToUpdateXml(++retryAttempt));  
```  
  
 <span data-ttu-id="80fc1-129">Cuando se reenvía el mensaje, el adaptador puede leer esta propiedad utilizando la siguiente línea de código:</span><span class="sxs-lookup"><span data-stu-id="80fc1-129">When the message is resubmitted, the adapter can read this property by using the following line of code:</span></span>  
  
```  
propValue = inmsg.Context.Read("RetryAttempts", "http://schemas.microsoft.com/BizTalk/2005/test-properties");  
```