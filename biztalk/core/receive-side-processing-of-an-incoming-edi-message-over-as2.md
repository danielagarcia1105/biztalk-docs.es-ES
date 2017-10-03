---
title: "Procesamiento de un mensaje EDI entrante a través de AS2 de lado de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 118451ab-d847-4f87-80ab-3cf812d71ac3
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fc9069dddf8a8b58ad439ed915fc9afa539c2a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-side-processing-of-an-incoming-edi-message-over-as2"></a>Procesamiento de recepción de un mensaje EDI entrante a través de AS2
El procesamiento de recepción de un mensaje EDI a través de AS2 incluye la recepción de un mensaje AS2, el envío de un MDN, el procesamiento de la carga EDI y el envío de confirmaciones EDI (si están habilitadas).  
  
 La canalización de recepción AS2EdiReceive recibe el mensaje AS2 y desensambla la carga EDI dentro del mensaje AS2. La canalización de envío AS2EDIReceive envía un MDN devuelto como respuesta al mensaje AS2 y una confirmación de EDI en respuesta al mensaje EDI. Puede incluir estas canalizaciones en un puerto de envío HTTP de petición-respuesta bidireccional (si el MDN es sincrónico) o en un puerto de envío HTTP unidireccional y en un puerto de recepción HTTP unidireccional (si el MDN es asíncrono).  
  
 Para recibir un intercambio EDI a través de AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] llevará a cabo los pasos siguientes:  
  
-   Procesar el mensaje AS2 recibido  
  
-   Enviar un MDN  
  
-   Procesar la carga EDI recibida  
  
-   Enviar una confirmación EDI  
  
## <a name="processing-the-received-as2-message"></a>Procesar el mensaje AS2 recibido  
 El descodificador AS2 en la canalización de recepción AS2EdiReceive procesa un mensaje de AS2 entrante. Para ello, utiliza la propiedad de contexto `InboundHTTPHeaders` que el adaptador de HTTP crea desde los encabezados de HTTP en el mensaje AS2. Estos encabezados incluyen los siguientes encabezados de AS2:  
  
-   AS2-To  
  
-   AS2-From  
  
-   AS2-Version  
  
-   MessageID  
  
-   OriginalMessageID (solo para MDN)  
  
-   Disposition-Notification-To (si se ha solicitado un MDN)  
  
-   Receipt-Delivery-Option (si se ha solicitado un MDN)  
  
-   Signed-Receipt-MICalg (si se ha solicitado un MDN)  
  
 El descodificador AS2 promocionará estos encabezados en el contexto del mensaje. Después realiza las operaciones siguientes:  
  
-   Realiza la resolución de acuerdo para determinar las propiedades que se usarán para procesar el mensaje entrante. Para obtener más información, consulte [resolución del acuerdo para mensajes AS2 entrantes](../core/agreement-resolution-for-incoming-as2-messages.md).  
  
-   Autentica el remitente mediante la **AS2-de** propiedad.  
  
    > [!NOTE]
    >  Para obtener más información acerca del procesamiento que canalizaciones de recepción AS2 realizan en mensajes AS2 entrantes, vea [procesar un mensaje AS2 entrante](../core/processing-an-incoming-as2-message.md).  
  
## <a name="sending-an-mdn"></a>Enviar un MDN  
 Si se ha habilitado un MDN, la canalización AS2EdiReceive genera un MDN y lo coloca en el cuadro de mensajes.  
  
> [!NOTE]
>  Para obtener más información acerca del procesamiento que canalizaciones de recepción AS2 realizan en los MDN salientes, vea [generar un MDN saliente](../core/generating-an-outgoing-mdn.md).  
  
 **Modo sincrónico**  
  
 Si se envía un mensaje EDI a través de AS2 en modo sincrónico, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] devolverá el MDN a través de esa conexión sincrónica y cerrará la conexión. Cuando se cierra la conexión, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede devolver una confirmación EDI (997, TA1 o CONTRL) a través de esa conexión. Las confirmaciones EDI siempre se envían de forma asíncrona a través de AS2.  
  
 La canalización AS2EDIReceive generará el MDN. Esta canalización enruta el MDN al cuadro de mensajes y, a continuación, la canalización AS2Send, que forma parte del puerto solicitud-respuesta, lo recogerá automáticamente.  
  
 **Modo asincrónico**  
  
 Si se envía un mensaje con codificación AS2/EDIINT I a través de transporte HTTP/HTTPS en modo asíncrono, debe crear un puerto de envío para devolver el MDN por separado. Puede configurar este puerto de envío para devolver los MDN asíncronos y las confirmaciones EDI. Si se trata de un puerto de envío dinámico, utilizará la dirección en la línea Receipt-Delivery-Notification en el encabezado del mensaje para enrutar el mensaje al socio comercial. Si es un puerto de envío estático, utilizará la dirección configurada en las propiedades del puerto. Este puerto de envío se suscribe al MDN asincrónico mediante una expresión de filtro `EdiIntAS.IsAS2AsynchronousMDN==True`.  
  
 En el procesamiento asíncrono, la canalización AS2EdiReceive generará una respuesta HTTP además del MDN. El puerto de recepción devuelve la respuesta HTTP al remitente original a través de la conexión HTTP entre el puerto de recepción y la entidad remitente, que cierra la conexión. Esto es necesario, ya que el MDN no cierra la conexión sincrónica.  
  
 Si BizTalk transporta un mensaje con codificación AS2/EDIINT a través de HTTP/HTTPS pero se produce un error en el procesamiento de la carga con codificación EDI, el remitente del mensaje original recibirá un MDN que indica un procesamiento AS2 correcto y una confirmación EDI que indica un error en el procesamiento de EDI. Se suspenderá la carga de codificación EDI y se registrará un error.  
  
## <a name="processing-the-received-edi-payload"></a>Procesar la carga EDI recibida  
 Si el **opción de procesamiento por lotes de entrada** para EDI se establece en **dividir intercambio**, asociada con la de canalización de recepción de la AS2EdiReceive analiza de ubicación de recepción de solicitud-respuesta el Establezca el mensaje EDI en un mensaje XML independiente para cada transacción de EDI. Si el **opción de procesamiento por lotes de entrada** está establecido en **conservar intercambio**, la canalización de recepción no analizará el mensaje EDI.  
  
 La canalización de recepción enruta los conjuntos de transacciones XML o el intercambio EDI conservado en el cuadro de mensajes de BizTalk.  
  
 Si el mensaje se va a enrutar a una aplicación del servidor, un puerto de envío recoge el mensaje XML y lo enruta a la aplicación.  
  
> [!NOTE]
>  Este puerto de envío puede ser de cualquier tipo.  
  
## <a name="sending-the-edi-acknowledgment"></a>Enviar la confirmación EDI  
 Si se habilitó una confirmación EDI, el desensamblador EDI en el puerto de recepción AS2EdiReceive generará las confirmaciones EDI (si están habilitadas). Las confirmaciones EDI deben enviarse mediante la canalización de envío AS2EdiSend en un puerto de envío unidireccional independiente.  
  
 Si configuras una solicitud-respuesta bidireccional puerto de recepción para mensajes EDI/AS2 devolver un MDN sincrónico o una respuesta HTTP (en el caso de un MDN asíncrono), el **puerto de recepción de enrutar confirmación para la canalización de envío de solicitud-respuesta** (de propiedad establecer en el **configuración de Host Local** página del acuerdo de EDI unidireccional en el **propiedades del acuerdo de** cuadro de diálogo) se pasará por alto. Incluso si se selecciona esta propiedad, la canalización de envío se devolverá un MDN sincrónico o una respuesta HTTP, no una confirmación EDI.  
  
 Para obtener más información, consulte [envía una confirmación EDI](../core/sending-an-edi-acknowledgment.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md)