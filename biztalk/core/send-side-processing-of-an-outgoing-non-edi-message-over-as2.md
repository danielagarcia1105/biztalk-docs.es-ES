---
title: Envío de procesamiento de un mensaje no perteneciente a EDI saliente a través de AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f19b7df-fe6d-4105-8a44-3d6db0bba451
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 537ff8147d42bce1db7135f38b9b9c5c8f1f160e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988005"
---
# <a name="send-side-processing-of-an-outgoing-non-edi-message-over-as2"></a>Procesamiento de envío de un mensaje saliente no perteneciente a EDI a través de AS2
Las canalizaciones AS2 incluidas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pueden utilizar para procesar un mensaje EDI o un mensaje no perteneciente a EDI sobre transporte AS2. Se usan diferentes canalizaciones para los dos tipos diferentes de cargas. La canalización AS2EdiSend se usa para procesar un mensaje EDI saliente a través de AS2, mientras que la canalización AS2Receive se usa para recibir el MDN asociado (si está habilitado). La canalización AS2Send se usa para procesar un mensaje saliente no perteneciente a EDI a través de AS2, mientras que la canalización AS2Receive se usa para recibir el MDN asociado (si está habilitado). El mensaje que no pertenece a EDI puede ser cualquier carga binaria.  
  
 La canalización de envío AS2Send ensambla la carga no perteneciente a EDI y codifica el mensaje AS2. La canalización de recepción AS2Receive descodifica la respuesta MDN. Puede incluir estas canalizaciones en un puerto de envío HTTP de petición-respuesta bidireccional (para MDN sincrónicos) o en un puerto de envío HTTP unidireccional y en un puerto de recepción HTTP unidireccional (para MDN asíncronos).  
  
 Para enviar un intercambio EDI a través de AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] llevará a cabo los pasos siguientes:  
  
-   Procesamiento de la carga no perteneciente a EDI para el envío  
  
-   Enviar el mensaje AS2  
  
-   Recibir el MDN devuelto  
  
## <a name="processing-the-non-edi-payload-for-sending"></a>Procesamiento de la carga no perteneciente a EDI para enviar  
 Antes de crear el mensaje AS2, un puerto de envío debe recoger la carga no perteneciente a EDI mediante el uso de una expresión de filtro apropiada para suscribirse a los mensajes. Puede usar un puerto de envío bidireccional o un puerto de envío unidireccional, en función de si el MDN va a ser sincrónico o asíncrono. La canalización de envío AS2Send procesará entonces la carga no perteneciente a EDI en un mensaje AS2.  
  
## <a name="sending-the-as2-message"></a>Envía el mensaje AS2  
 El codificador AS2 de la canalización de envío AS2 realiza primero la resolución del acuerdo para determinar las propiedades del acuerdo que se utilizarán para procesar el mensaje saliente. Para obtener más información, consulte [resolución del acuerdo para mensajes AS2 salientes](../core/agreement-resolution-for-outgoing-as2-messages.md).  
  
 El codificador AS2 crea el conjunto de encabezados HTTP necesarios para enviar un mensaje AS2. Agrega estos encabezados a la propiedad de contexto `HTTP.UserHttpHeaders`, que consiste en una cadena única de valores de encabezado. El codificador AS2 genera los siguientes encabezados AS2 en HTTP.UserHttpHeaders. Estos encabezados deben estar en los mensajes AS2.  
  
- AS2-To  
  
- AS2-From  
  
- AS2-Version  
  
- MessageID  
  
- OriginalMessageID (solo para MDN)  
  
  Si el **solicitar MDN** propiedad está activada, la canalización establecerá los encabezados Disposition-Notification-To, Receipt-Delivery-Option y Signed-Receipt-MICalg AS2 del mensaje para los valores de las propiedades correspondientes y establecerá el encabezado de AS2 Signed-Receipt-Protocol en "pcks7-signature" si el **solicitar MDN firmada** se comprueba la propiedad.  
  
  Si la propiedad de contexto `HTTP.UserHttpHeaders` no existe, el codificador AS2 la creará. Si `HTTP.UserHttpHeaders` ya existe, el codificador AS2 la utilizará en lugar de crearla. Si crea `HTTP.UserHttpHeaders`, escribe encabezados en ella y, a continuación, la escribe en el contexto del mensaje, el codificador AS2 utilizará estos encabezados y tendrán prioridad frente a los encabezados de otros orígenes. La excepción es el encabezado AS2-From que siempre se toma a de las propiedades del acuerdo.  
  
  Si un encabezado de AS2 no se encuentra en `HTTP.UserHttpHeaders`, el codificador AS2 lo agregará desde las propiedades de contexto único. Esto significa que se pueden agregar encabezados AS2 promoviéndolos o escribiéndolos en el contexto del mensaje (si no se encuentran ya en `HTTP.UserHttpHeaders`). Si un encabezado AS2 no está ni en `HTTP.UserHttpHeaders`, ni como propiedad en el contexto, el codificador AS2 lo agregará en `HTTP.UserHttpHeaders` a partir de las propiedades del acuerdo.  
  
  Después de que el codificador AS2 crea los encabezados en la propiedad `HTTP.UserHttpHeaders`, lo escribe en el contexto del mensaje. El adaptador de HTTP recoge `HTTP.UserHttpHeaders` y antepone los valores del encabezado de `HTTP.UserHttpHeaders` en el mensaje.  
  
> [!NOTE]
>  El transporte de AS2 está destinado para funcionar solo con el adaptador de HTTP. Sin embargo, si establece manualmente las propiedades de contexto adecuadas, puede utilizar el adaptador de archivo para transportar mensajes AS2. Para obtener más información, consulte [enviar un mensaje AS2 a través de un puerto de envío de archivo](../core/sending-an-as2-message-over-a-file-send-port.md).  
  
## <a name="processing-the-returned-mdn"></a>Procesar el MDN devuelto  
 Si un MDN está habilitado, la canalización de recepción asociada con el puerto de envío bidireccional recibe el MDN desde la entidad que recibe el mensaje AS2.  
  
> [!NOTE]
>  Para obtener más información acerca del procesamiento que las canalizaciones de envío AS2 realizan en los MDN entrantes, vea [enviar un MDN saliente](../core/sending-an-outgoing-mdn.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo envía BizTalk Server los mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md)