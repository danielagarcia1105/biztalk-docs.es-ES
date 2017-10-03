---
title: Interfaz de IBaseMessage | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10bfb95c-aef5-46ba-ba0e-9961833f27a3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7de478b27105ee6c01d582aa9b728bd0496d0487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ibasemessage-interface"></a>IBaseMessage (interfaz)
Cuando un adaptador de recepción acepta un paquete de datos entrante a través de su protocolo, utiliza el **IBaseMessage** interfaz para crear un mensaje que se pasará al motor de mensajería. Todos los mensajes se representan mediante esta interfaz.  
  
 Un mensaje tiene uno o más partes del mensaje representan por la **IBaseMessagePart** interfaz. Cada parte del mensaje tiene una referencia a sus datos a través de un **IStream** puntero de interfaz. El contexto de un mensaje está representado por su **IBaseMessageContext** interfaz. En la siguiente ilustración se muestra el modelo de objetos de mensaje de BizTalk.  
  
 ![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")  
  
 El contexto de mensaje es un diccionario que organizado en pares de claves con una combinación de nombre de propiedad y espacio de nombres de la propiedad. Este modo evita conflictos entre propiedades con nombres parecidos de orígenes diferentes, por ejemplo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] propiedades del sistema y las propiedades de adaptador personalizado. Los valores de estas propiedades son del tipo .NET **objeto**, pero en realidad son variantes.  
  
 Cada parte tiene un contexto de parte que también es un diccionario, pero sin la noción de espacio de nombres. El valor de un contexto de parte son metadatos que hacen referencia a los datos de esa parte. Un ejemplo de esto es el **Charset** propiedad que especifica el juego de caracteres utilizado para codificar los mensajes.  
  
 Las propiedades se pueden escribir y leer en el contexto de mensaje. También se pueden promocionar a fin de utilizarlas para el enrutamiento de mensajes. Promocionar significa escribirlas como parte de metadatos que fluyen con el mensaje. Una propiedad promocionada permite que su valor se use en la creación de expresiones de filtro de las orquestaciones y los puertos de envío. Los componentes de nivel inferior y el código de usuario de las orquestaciones pueden leer las propiedades promocionadas y también escribir en ellas valores nuevos.  
  
 Después de haber hecho coincidir una propiedad promocionada con una suscripción existente y de haberla utilizado para enrutar un mensaje, se degrada para evitar coincidencias cíclicas con suscripciones. Una propiedad degradada permanece en el contexto de mensaje como metadatos, pero pierde el estado promocionado.  
  
 **Sugerencia para la implementación:** propiedades de contexto de mensaje se cargan en memoria en tiempo de ejecución. Muy grandes conjuntos de datos no deben escribirse en el contexto del mensaje porque esto podría impedir potencialmente la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admitir mensajes grandes. Los objetos se pueden serializar en el contexto del mensaje siempre que implementen la **IPersistStream** interfaz. Además, las propiedades promocionadas están limitadas a 255 caracteres.  
  
 Siempre debe utilizarse el generador de mensajes para crear mensajes nuevos.  El fragmento de código siguiente ilustra cómo se crea un mensaje de BizTalk nuevo a partir de la secuencia de datos recibida por el adaptador.  
  
```  
using Microsoft.BizTalk.Message.Interop;  
  
IBaseMessage CreateMessage( Stream s, IBaseMessageFactory msgFactory )  
{  
IBaseMessage msg = null;  
IBaseMessagePart part = msgFactory.CreateMessagePart();  
part.Data = s;  
msg = msgFactory.CreateMessage();  
msg.AddPart("body", part, true);  
return msg;  
}  
```