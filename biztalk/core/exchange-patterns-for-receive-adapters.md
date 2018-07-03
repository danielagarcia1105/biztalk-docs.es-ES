---
title: Patrones de intercambio para adaptadores de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e505559e-66be-4c32-a2a8-a242cba10000
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc93f587e8d04e93e96a8e326abfcc68c51daf69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004823"
---
# <a name="exchange-patterns-for-receive-adapters"></a>Intercambiar patrones para adaptadores de recepción
Recibir los adaptadores reciben datos procedentes del "cable" y enviarlo como un mensaje en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Este proceso de envío puede ser un patrón de intercambio de mensajes unidireccional o bidireccional.  
  
## <a name="one-way-submit"></a>Envío unidireccional  
 Para que un adaptador de recepción envíe un mensaje al motor de mensajería de BizTalk, primero será necesario crear un mensaje de BizTalk nuevo. El ejemplo de código del tema IBaseMessage muestra cómo se ha realizado. La secuencia que el adaptador define como cuerpo del mensaje debe ser normalmente una secuencia progresiva, lo que significa que no debe almacenar en caché los datos que se han leído previamente en la memoria.  
  
 Antes de que el adaptador envía el mensaje al motor, debe escribir el **InboundTransportLocation** propiedad de contexto en el espacio de nombres del sistema en el mensaje de BizTalk del mensaje. Esto se muestra en el siguiente fragmento de código:  
  
 `Assembly References:`  
  
 `Microsoft.XLANGs.BaseTypes.dll`  
  
 `Microsoft.BizTalk.Pipeline.dll`  
  
 `Microsoft.BizTalk.GlobalPropertySchemas.dll`  
  
```  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.XLANGs.BaseTypes;  
  
private static readonly PropertyBase InboundTransportLocationProp =   
new BTS.InboundTransportLocation();  
  
private void StampMsgCtxProps(  
IBaseMessage msg, string uri, string adapterType)  
{  
msg.Context.Write(  
 InboundTransportLocationProp.Name.Name,   
 InboundTransportLocationProperty.Name.Namespace,   
  uri);  
}  
```  
  
 Además, es posible que el adaptador defina sus propios esquemas de propiedades y escriba las propiedades del contexto del mensaje relacionadas con el extremo sobre el que se ha recibido el mensaje. Por ejemplo, un adaptador de HTTP podría escribir los encabezados HTTP en el contexto del mensaje y un receptor SMTP podría escribir el asunto del correo electrónico en el contexto del mensaje. Esta información puede ser útil para componentes de nivel inferior, como componentes de canalización, programación de orquestación o un adaptador de envío.  
  
 Una vez que se preparen los mensajes, se pueden enviar al motor de mensajería. Para ver cómo un adaptador de recepción unidireccional puede enviar un mensaje al motor, vea el ejemplo de código [SubmitDirect (ejemplo de BizTalk Server)](../core/submitdirect-biztalk-server-sample.md).  
  
## <a name="request-response"></a>Solicitud-respuesta  
 Los adaptadores de recepción bidireccionales se utilizan, por lo general, en puertos de recepción unidireccionales o bidireccionales. El adaptador determina si la ubicación de recepción que proporciona el servicio es un puerto unidireccional o bidireccional inspeccionando el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bolsa de propiedades. Este proceso se explica en el **IBTTransportConfig.AddReceiveEndpoint (método) (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
 El diagrama de interacción de objetos muestra el proceso de realización de un intercambio de mensajes solicitud-respuesta. El adaptador solicita un nuevo lote del proxy de transporte y pasa su referencia a la **IBTTransmitter** interfaz a través de la **SubmitRequestMessage** método. El motor de mensajería entrega el mensaje de respuesta en esta interfaz mediante el **TransmitMessage** método.  
  
 Puesto que el motor está procesando mensajes de forma asincrónica, es posible que suceda lo siguiente:  
  
- El **BatchComplete** devolución de llamada puede producirse antes de **realiza** ha devuelto.  
  
- Es posible que la llamada a TransmitMessage se realice antes que BatchComplete, e incluso antes que Done.  
  
  Aunque ambos escenarios son extraños, el adaptador debe protegerse contra esto.  
  
  Se recomienda que el mensaje de respuesta se transmita mediante una llamada asincrónica sin bloqueo.  
  
  El proyecto BaseAdapter tiene una clase de utilidad, **StandardRequestResponseHandler**, que encapsula la semántica de solicitud-respuesta explicada en este tema.  
  
## <a name="request-response-message-time-outs"></a>Tiempos de espera de mensaje de solicitud-respuesta  
 Cuando un adaptador envía un mensaje de solicitud de la solicitud, debe especificar el tiempo de espera del mensaje de solicitud en el **IBTTransportBatch.SubmitRequestMessage (método) (COM)** API [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. Se entregará un mensaje de respuesta al adaptador únicamente dentro del período de espera. Después de que el tiempo de espera se agote, se entregará una confirmación negativa (NACK) al adaptador en lugar del mensaje de respuesta. Si el adaptador no especifica un valor de tiempo de espera, el motor utiliza el valor predeterminado de 20 minutos.  
  
 El tiempo de espera predeterminado para mensajes de solicitud-respuesta puede controlarse mediante la utilización de la siguiente clave del Registro para adaptadores de recepción de tipo En curso:  
  
 **DWORD**  
  
 **\MessagingReqRespTTL HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {Guid de Host}**  
  
 La clave del Registro está en una ubicación diferente para adaptadores de recepción aislados:  
  
 **DWORD**  
  
 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**  
  
 NACK (confirmaciones negativas) son errores SOAP y existen dos modos de controlarlos. Por lo general, el adaptador devuelve NACK al cliente y el cliente controla NACK. De forma alternativa, puede que la canalización de transmisión que controla el mensaje de respuesta se configure para cambiar el contenido del mensaje de respuesta mediante de la utilización de una asignación o de un componente de canalización personalizado.