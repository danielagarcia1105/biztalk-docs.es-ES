---
title: Envío de procesamiento de un mensaje EDI saliente a través de AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfb63b22-6e2e-4d4f-b028-301c8d4d53b0
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c00aaae104bfe685945c7b20b62912970582381
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995421"
---
# <a name="send-side-processing-of-an-outgoing-edi-message-over-as2"></a>Procesamiento de envío de mensajes EDI salientes a través de AS2
El procesamiento de envío de un mensaje EDI a través de AS2 incluye el envío de un mensaje AS2 con la carga EDI y la recepción de confirmaciones de MDN y EDI (si están habilitadas).  
  
 La canalización de envío AS2EDISend envía un mensaje EDI/AS2 ensamblado al socio comercial receptor a través de HTTP/HTTPS. La canalización de recepción AS2EDIReceive recibe un MDN devuelto como respuesta al mensaje AS2 y una confirmación de EDI en respuesta al mensaje EDI. Cada una de estas canalizaciones procesa un mensaje AS2 y procesa la carga EDI en un mensaje AS2. Puede incluir estas canalizaciones en un puerto de envío HTTP de petición-respuesta bidireccional o en un puerto de envío HTTP unidireccional y en un puerto de recepción HTTP unidireccional.  
  
 Para enviar un intercambio EDI a través de AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] llevará a cabo los pasos siguientes:  
  
-   Procesar la carga EDI para enviar  
  
-   Enviar el mensaje AS2  
  
-   Recibir el MDN devuelto  
  
-   Recibir la confirmación EDI devuelta  
  
## <a name="processing-the-edi-payload-for-sending"></a>Procesar la carga EDI para el envío  
 Antes de crear un mensaje AS2, la canalización AS2EdiSend debe procesar el intercambio EDI. Si está habilitado el procesamiento por lotes saliente, conjuntos de transacciones se procesarán por lotes como se describe en [ensamblar un intercambio por lotes de EDI](../core/assembling-a-batched-edi-interchange.md). El ensamblador EDI creará el intercambio EDI tal como se describe en [cómo funciona el ensamblador EDI the](../core/how-the-edi-assembler-works.md).  
  
## <a name="sending-the-as2-message"></a>Envía el mensaje AS2  
 El codificador AS2 de la canalización de envío AS2 realiza primero la resolución del acuerdo para determinar las propiedades del acuerdo que se utilizarán para procesar el mensaje saliente. Para obtener más información, consulte [resolución del acuerdo para mensajes AS2 salientes](../core/agreement-resolution-for-outgoing-as2-messages.md).  
  
 El codificador AS2 crea el conjunto de encabezados HTTP necesarios para enviar un mensaje AS2. Agrega estos encabezados a la propiedad de contexto `HTTP.UserHttpHeaders`, que consiste en una cadena única de valores de encabezado. El Codificador AS2 integra los siguientes encabezados AS2 en `HTTP.UserHttpHeaders`. Estos encabezados deben estar en los mensajes AS2.  
  
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
  
## <a name="processing-the-returned-edi-acknowledgment"></a>Procesar la confirmación EDI devuelta  
 Si la confirmación EDI está habilitada, la canalización de recepción asociada con el puerto de envío bidireccional también recibe una confirmación EDI desde el receptor del mensaje EDI (porque filtra en el tipo de mensaje de confirmación EDI de BizTalk). Para obtener más información, consulte [procesamiento de confirmaciones recibidas](../core/processing-a-received-acknowledgment.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo envía BizTalk Server los mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md)