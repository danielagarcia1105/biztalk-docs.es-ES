---
title: Recepción de procesamiento de un mensaje no perteneciente a EDI entrante a través de AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fee10cba-8b1a-4d2c-b9d9-efbb74c3f461
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed0829579108feb9dbfbf5e5e08d98291ba49604
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002813"
---
# <a name="receive-side-processing-of-an-incoming-non-edi-message-over-as2"></a>Procesar en la recepción mensajes no pertenecientes a EDI entrantes a través de AS2
Las canalizaciones AS2 incluidas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pueden utilizar para procesar un mensaje EDI o un mensaje no perteneciente a EDI sobre transporte AS2. Se usan diferentes canalizaciones para los dos tipos diferentes de cargas. La canalización AS2EdiReceive se usa para procesar un mensaje EDI entrante a través de AS2 mientras que la canalización AS2Send se usa para devolver el MDN asociado (si está habilitado). La canalización AS2Receive se usa para procesar un mensaje no perteneciente a EDI entrante a través de AS2, mientras que la canalización AS2Send se usa para devolver el MDN asociado (si está habilitado). El mensaje que no pertenece a EDI puede ser cualquier carga binaria.  
  
 La canalización de recepción AS2Receive descodifica el mensaje AS2 y, a continuación, desensambla el mensaje AS2. Una canalización de envío AS2Send codifica el MDN. Puede incluir las canalizaciones AS2Receive y AS2Send en un puerto de envío HTTP de petición-respuesta bidireccional (si el MDN es sincrónico) o en un puerto de envío MDN unidireccional y en un puerto de recepción HTTP unidireccional (si el MDN es asíncrono). Si necesita realizar un desensamblado de una carga que no sea EDI, tendrá que hacerlo en otra canalización de recepción, ya que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo permite un desensamblador en una canalización de recepción. Esto requiere un puerto de envío de bucle invertido y ubicación de recepción (consulte la [procesar la carga no perteneciente a EDI recibido](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md#BKMK_NonEDI) sección más adelante).  
  
 Para recibir un intercambio que no pertenece a EDI a través de AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] llevará a cabo los pasos siguientes:  
  
-   Procesar el mensaje AS2 recibido  
  
-   Enviar un MDN  
  
-   Procesar la carga que no pertenece a EDI recibida  
  
## <a name="processing-the-received-as2-message"></a>Procesar el mensaje AS2 recibido  
 El descodificador AS2 en la canalización de recepción AS2Receive procesa un mensaje AS2 entrante. Para ello, utiliza la propiedad de contexto `InboundHTTPHeaders` que el adaptador de HTTP crea desde los encabezados de HTTP en el mensaje AS2. Estos encabezados incluyen los siguientes encabezados de AS2:  
  
- AS2-To  
  
- AS2-From  
  
- AS2-Version  
  
- MessageID  
  
- OriginalMessageID (solo para MDN)  
  
- Disposition-Notification-To (si se ha solicitado un MDN)  
  
- Receipt-Delivery-Option (si se ha solicitado un MDN)  
  
- Signed-Receipt-MICalg (si se ha solicitado un MDN)  
  
  El descodificador AS2 promocionará estos encabezados en el contexto del mensaje. Después realiza las operaciones siguientes:  
  
- Realiza la resolución de acuerdo para determinar las propiedades que se usarán para procesar el mensaje entrante. Para obtener más información, consulte [resolución del acuerdo para mensajes AS2 entrantes](../core/agreement-resolution-for-incoming-as2-messages.md).  
  
- Autentica el remitente mediante las propiedades AS2-From y AS2-To.  
  
  > [!NOTE]
  >  Para obtener más información acerca del procesamiento que canalizaciones de recepción AS2 realizan en los mensajes AS2 entrantes, vea [procesar un mensaje AS2 entrante](../core/processing-an-incoming-as2-message.md).  
  
## <a name="sending-an-mdn"></a>Enviar un MDN  
 Si se ha habilitado un MDN, la canalización AS2Receive genera un MDN y lo coloca en el cuadro de mensajes. El modo que se utiliza para devolver el MDN al remitente del mensaje original depende de si el transporte AS2 es sincrónico o no lo es.  
  
> [!NOTE]
>  Para obtener más información acerca del procesamiento que canalizaciones de recepción AS2 realizan en los MDN salientes, consulte [generar un MDN saliente](../core/generating-an-outgoing-mdn.md).  
  
 **Modo sincrónico**  
  
 Si se envía un mensaje que no pertenece a EDI a través de AS2 en modo sincrónico, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] devolverá el MDN a través de esa conexión sincrónica y cerrará la conexión. La canalización AS2Receive generará el MDN y lo enrutará al cuadro de mensajes; allí, la canalización AS2Send, que forma parte del puerto de recepción de solicitud-respuesta, lo recogerá automáticamente.  
  
 **Modo asincrónico**  
  
 Si se envía un mensaje que no pertenece a EDI a través de transporte HTTP/HTTPS en modo asíncrono, debe crear un puerto de envío para devolver el MDN por separado. Si se trata de un puerto de envío dinámico, utilizará la dirección en la línea Receipt-Delivery-Notification en el encabezado del mensaje para enrutar el mensaje al socio comercial. Si es un puerto de envío estático, usará la dirección definida en las propiedades del puerto. Este puerto de envío se suscribe al MDN asincrónico mediante una expresión de filtro `EdiIntAS.IsAS2AsynchronousMDN==True`. En el procesamiento asíncrono, la canalización AS2Receive generará una respuesta HTTP además del MDN. El puerto de recepción devuelve la respuesta HTTP al remitente original a través de la conexión HTTP entre el puerto de recepción y la entidad remitente, que cierra la conexión. Esto es necesario, ya que el MDN no cierra la conexión sincrónica.  
  
##  <a name="BKMK_NonEDI"></a> Procesamiento de la carga que no son EDI recibidos  
 Cuando se recibe un mensaje que no está codificado en EDI a través de AS2, y necesita realizar un desensamblado en la carga, necesitará hacerlo en una canalización de recepción diferente a la canalización AS2Receive. Esto es necesario porque [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo permite un desensamblador en una canalización de recepción. En este escenario se necesitará un mecanismo de bucle invertido que utilice una ubicación de recepción y un puerto de envío. En el primer pase, la canalización EDIReceive procesa el mensaje AS2 y lo envía en su formato nativo al cuadro de mensajes. En el segundo pase, una canalización de recepción genera XML desde el formato nativo del mensaje.  
  
 BizTalk Server realizará el siguiente procesamiento en caso de recepción en un mensaje que no pertenece a EDI a través de AS2 de BizTalk Server:  
  
-   La canalización de recepción AS2Receive asociada con la ubicación de recepción de solicitud-respuesta analiza los encabezados de AS2 del mensaje que no pertenece a EDI y, después, enruta el mensaje que no pertenece a EDI al cuadro de mensajes de BizTalk.  
  
-   Un puerto de envío de bucle invertido (de archivo o MSMQ) recoge el mensaje que no pertenece a EDI del cuadro de mensaje, ya que hace el filtrado en la propiedad `IsAS2PayloadMessage == True` de BizTalk. La canalización de envío PassThruTransmit asociada a este puerto de envío pasa el mensaje a través de su formato que no es EDI y enruta el mensaje a una carpeta o a una cola MSMQ.  
  
-   Una ubicación de recepción de bucle invertido recoge el mensaje. La canalización de recepción asociada con la ubicación de recepción de bucle invertido genera un mensaje XML a partir del mensaje que no pertenece a EDI y, después, lo enruta al cuadro de mensajes.  
  
-   Si el mensaje se va a enrutar a una aplicación del servidor, un puerto de envío recoge el mensaje XML y lo enruta a la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md)   
 [Procesamiento de envío de mensajes EDI de salida a través de AS2](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)