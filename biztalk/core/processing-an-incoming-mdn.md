---
title: Procesamiento de MDN entrante | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd78e84c-4989-47e4-b95b-80582084ddec
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e599e9ebbc7a05a466cc047d891699222c2dabac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265268"
---
# <a name="processing-an-incoming-mdn"></a>Procesar MDN entrantes
Las canalizaciones de recepción AS2 (AS2EDIReceive y AS2Receive) procesan un MDN entrante según las propiedades del acuerdo para la entidad como un receptor de mensaje AS2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] correlaciona automáticamente el MDN al mensaje AS2 saliente.  
  
 Los pasos que cada canalización realiza son los siguientes:  
  
-   Determina la entidad remitente mediante la correspondencia de AS2-de valor en el encabezado de AS2 del mensaje con el valor para AS2-de lista en la **identificadores** página de la ficha de acuerdo AS2 unidireccional de la **propiedades del acuerdo de** cuadro de diálogo. Si no se encuentra ninguna coincidencia, la canalización anula el procesamiento y genera una excepción.  
  
-   Promociona las siguientes propiedades de AS2 en el contexto:  
  
    -   IsAS2FailedMessage  
  
    -   DispositionType  
  
    -   GenerateAsynchronous200OKOnly  
  
    -   IsAS2MdnResponseMessage  
  
    -   IsAS2MessageSigned  
  
    -   OriginalMessageId  
  
    -   ReceivedContentMic  
  
    -   DispositionMode  
  
    -   MessageId  
  
-   Establece la propiedad InboundHttpHeaders en todos los encabezados HTTP del mensaje y la promociona al contexto del mensaje.  
  
-   Realiza una copia del MDN (en formato de "cable") y almacena la copia en la base de datos sin repudio (en la tabla EdiMessageContent de la base de datos BizTalkDTADb), si esta opción está habilitada en las propiedades del acuerdo AS2 unidireccional.  
  
-   Realiza el procesamiento de MIME, incluida la comprobación de la firma si el MDN está firmado.  
  
-   Compara la MIC (comprobación de integridad del mensaje) en el MDN con la MIC en el almacén de datos que la canalización AS2Send calculó al mandar el mensaje original (si corresponde). Para obtener más información, consulte [mensajes MDN](../core/mdn-messages.md).  
  
-   Realiza entradas de correlación en la base de datos sin repudio.  
  
-   Elimina el MDN, a menos que la **procesar el MDN entrante en el cuadro de mensajes para opciones de enrutado y entrega** propiedad se establece en el **configuración de MDN de remitente** página de la ficha de acuerdo AS2 unidireccional de la  **Propiedades del acuerdo de** cuadro de diálogo.  
  
-   Si el **procesar el MDN entrante en el cuadro de mensajes para opciones de enrutado y entrega** propiedad se establece en el **configuración de MDN de remitente** página de la ficha de acuerdo AS2 unidireccional de la **propiedades del acuerdo**  cuadro de diálogo, la canalización de recepción enruta el MDN en su formato correspondiente a través del descodificador AS2 como un mensaje de paso y lo coloca en el cuadro de mensajes. El MDN en formato de “cable” contiene todos los encabezados HTTP.  
  
    > [!NOTE]
    >  Puede configurar un puerto de envío para suscribirse a un MDN recibido que se ha colocado en el cuadro de mensajes. Para suscribirse al MDN recibido, establezca el filtro del puerto de envío en `IsAS2MdnResponseMessage==True`.  
  
    > [!NOTE]
    >  Si usa la canalización AS2EdiReceive para procesar un MDN recibido, no podrá enrutar el MDN en el cuadro de mensajes estableciendo la **procesar el MDN entrante en el cuadro de mensajes para opciones de enrutado y entrega** propiedad en el **MDN de remitente Configuración de** página de la ficha de acuerdo AS2 unidireccional de la **propiedades del acuerdo de** cuadro de diálogo. Al tratar de hacerlo, se producirá un error de EDI, ya que el MDN se pasará al descodificador EDI, que no puede procesar un MDN. Si el MDN no se envía al cuadro de mensajes, el descodificador AS2 consumirá el MDN, de modo que no se pasará al descodificador EDI.  
  
## <a name="message-integrity-check"></a>Comprobación de integridad del mensaje  
 La comprobación de integridad del mensaje (MIC) se usa para comprobar si un MDN correlaciona con el mensaje original enviado. La canalización de envío AS2Send calcula la MIC desde la carga del mensaje cuando genera el mensaje AS2 original y la guarda en la MIC en el almacén de datos. Cuando es necesario un MDN, el destinatario del mensaje original genera una MIC y la agrega al MDN. Cuando la canalización de recepción AS2MdnReceive recibe el MDN, si se ha solicitado un MDN firmado, lo compara la MIC en el MDN con la MIC en el almacén de datos.  
  
 Si no coinciden, significa que se ha producido un error durante la transmisión o recepción del mensaje por parte de la entidad receptora. Los valores notificados en este error son los siguientes:  
  
-   AS2DispositionType: Error  
  
-   AS2DispositionModifierExtensionType: Error  
  
-   AS2DispositionModifierExtensionDescription: Error en la comprobación de integridad  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md)   
 [Mensajes MDN](../core/mdn-messages.md)