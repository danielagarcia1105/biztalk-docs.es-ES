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
# <a name="send-adapter-operations"></a>Operaciones del adaptador de envío
Los adaptadores de envío pueden realizar las siguientes operaciones:  
  
-   **Vuelva a intentarlo: anular reenviar (mensaje de IBaseMessage, marca de tiempo de fecha y hora).** Cuando se produce un error de transmisión en un mensaje, un adaptador lo reenvía cuando sea conveniente. La llamada a este elemento se efectúa por cada uno de los mensajes. Si un lote de mensajes se envían correctamente, el adaptador debe determinar los mensajes que han provocado el error y reenviar los que no se han provocado el lote a un error en las llamadas independientes a **reenviar**. No hay información al final de este tema sobre cómo mantener valores de propiedad de contexto de mensaje cuando se llama a **reenviar**.  
  
-   **Pasar al siguiente transporte: void MoveToNextTransport (IBaseMessage msg).** Si se producen errores en un mensaje durante la operación de envío y se han agotado los reintentos, el adaptador puede enviar el mensaje al siguiente transporte que se ha configurado para la retransmisión.  
  
-   **Suspender: void MoveToSuspendQ (IBaseMessage msg).** Si no se ha configurado un transporte de reserva adicional, el adaptador mueve un mensaje de envío con errores a la cola de suspensión. No hay información al final de este tema sobre cómo mantener valores de propiedad de contexto de mensaje cuando se llama a **Suspend**.  
  
-   **Delete: void DeleteMessage (IBaseMessage msg).** El adaptador elimina un mensaje después de que BizTalk Server le haya notificado que la transmisión se ha realizado de forma correcta. Al eliminar un mensaje se le comunica a BizTalk Server que el adaptador ha finalizado con el mensaje. Por lo general el **SubmitResponse** operación se realiza en el mismo lote que está asociada **eliminar** operación.  
  
-   **Enviar respuesta: void SubmitResponseMessage (IBaseMessage solicitMsgSent, IBaseMessage responseMsgToSubmit).** El adaptador envía una respuesta al lote que se va a enviar de vuelta a BizTalk Server. Esta operación incluye en la llamada el mensaje original junto con la respuesta para que BizTalk Server pueda correlacionarlas.  
  
-   **Cancelar respuesta: void CancelResponseMessages (string correlationToken).** Si el envío de un mensaje de respuesta debe cancelarse antes de que se envíe el lote, el **CancelResponseMessages** se usa el método, pasando el token de correlación para el mensaje de respuesta asociado va a eliminar.  
  
 Al llamar a **reenviar** o **Suspend** en un mensaje que se desea conservar los valores de determinadas propiedades de contexto del mensaje. Puede hacerlo si guarda los valores de propiedad en formato XML. Cuando se reenvía o se suspende el mensaje, las propiedades correspondientes permanecen disponibles en el contexto del mensaje.  
  
 La siguiente cadena XML describe el formato en el que se almacena la información:  
  
```  
<PropertiesToUpdate>  
<Property name="StringProperty" nameSpace="http://MyNamespace1" vt="8">SomeString</Property>  
<Property name="IntProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="3">4</Property>  
<Property name="BoolProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="11">0</Property>  
</PropertiesToUpdate>  
```  
  
 El código que aparece a continuación es el que genera la cadena XML:  
  
```  
private string GetPropsToUpdateXml(int nextRetryAttempt)  
{  
string result = "<PropertiesToUpdate><Property name=\"RetryAttempts\" nameSpace=\"http://schemas.microsoft.com/BizTalk/2005/test-properties\" vt=\"3\">" + nextRetryAttempt.ToString() + "</Property></PropertiesToUpdate>";  
return result;  
}  
```  
  
 A continuación, la cadena se guarda en el contexto del mensaje utilizando el siguiente código:  
  
```  
Message.Context.Write("PropertiesToUpdate", "http://schemas.microsoft.com/BizTalk/2003/system-properties", GetPropsToUpdateXml(++retryAttempt));  
```  
  
 Cuando se reenvía el mensaje, el adaptador puede leer esta propiedad utilizando la siguiente línea de código:  
  
```  
propValue = inmsg.Context.Read("RetryAttempts", "http://schemas.microsoft.com/BizTalk/2005/test-properties");  
```