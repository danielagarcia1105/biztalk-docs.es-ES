---
title: Enviar un MDN saliente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dce7620-d354-4b76-bcbc-f97dc93c3fc3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d947751e06e0dc9892ab63e109b417047ad91b59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271428"
---
# <a name="sending-an-outgoing-mdn"></a>Enviar un MDN saliente
La canalización de recepción AS2EDIReceive o AS2Receive genera un MDN saliente, y la canalización AS2Send lo envía. En este tema se describe cómo se envía un MDN. Para obtener más información sobre cómo se genera un MDN, vea [generar un MDN saliente](../core/generating-an-outgoing-mdn.md).  
  
> [!NOTE]
>  La canalización de envío AS2EDISend no se usa para enviar un MDN saliente, ya que el ensamblador EDI de esa canalización no se usa en el procesamiento de un MDN.  
  
## <a name="agreement-resolution-for-an-mdn"></a>Resolución de acuerdos para un MDN  
 Un MDN se enruta a sí mismo. Contiene la información necesaria para enrutarse al acuerdo deseado. La canalización de envío usa las propiedades del acuerdo AS2 para procesar el MDN saliente. No obstante, el MDN no tiene que tener un acuerdo resuelto para que se enrute a la entidad.  
  
 Cuando la canalización AS2Send procesa un MDN saliente, usa el valor AS2-To en el contexto del mensaje para obtener las propiedades del acuerdo y procesar el MDN. Lo hace mediante la correspondencia de AS2-para la propiedad de contexto con AS2-a propiedades de acuerdo en el **identificadores** página en la ficha de acuerdo AS2 unidireccional en el **propiedades del acuerdo de** cuadro de diálogo. Esta resolución de acuerdo para el MDN puede producir un error si el valor AS2-To no está establecido para el acuerdo. Si el acuerdo no puede determinarse, se usará un acuerdo predeterminado para generar el MDN.  
  
 En el acuerdo predeterminado para un MDN saliente, se realiza la verificación de la lista de resolución de certificados. Si no desea que se realice esta verificación, compruebe que está establecida la propiedad del acuerdo de AS2-To correcta, de forma que la entidad de recepción pueda resolverse y las propiedades del acuerdo puedan determinarse. En ese caso, no se usará el acuerdo predeterminado que solicita la verificación de la lista de resolución de certificados. También necesitará deshabilitar el **Comprobar lista de revocación de certificados** propiedad en el **validación** página de la ficha de acuerdo AS2 unidireccional en el **propiedades del acuerdo de** cuadro de diálogo.  
  
## <a name="synchronous-and-asynchronous-transmission"></a>Transmisión sincrónica y asíncrona  
 En el procesamiento predeterminado de AS2, se envía un MDN de forma sincrónica. El puerto de envío asociado a un puerto de recepción bidireccional envía el MDN. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]envía el MDN como una respuesta HTTP a una solicitud HTTP POST o como una respuesta HTTPS a una solicitud HTTPS POST en la misma conexión TCP/IP. El MDN está incluido en el cuerpo del mensaje del comando de respuesta HTTP.  
  
 Si el MDN se va a enviar de forma asíncrona, debe enviarse por un puerto de envío independiente, que recoge el MDN del cuadro de mensajes. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]envía el MDN como un HTTP Post independiente en una conexión TCP/IP única, distinta del que se utiliza para entregar el mensaje AS2 original. Aunque el MDN esté establecido como un HTTP Post independiente, un comando de respuesta HTTP sigue siendo necesario para el Post.  
  
 Normalmente, un MDN asíncrono se enviará a la URL del encabezado Receipt-Delivery-Option del mensaje AS2 original. Sin embargo, si la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad se establece en la en la **validación** página de la ficha de acuerdo AS2 unidireccional en el **acuerdo Propiedades** cuadro de diálogo, el MDN se enviará a la dirección URL que el **Receipt-Delivery-Option (URL)** acuerdo propiedad está establecida en.  
  
## <a name="how-the-send-pipeline-processes-an-outgoing-mdn"></a>Cómo procesa la canalización de envío un MDN saliente  
 La canalización AS2Send procesa un MDN saliente de la siguiente manera:  
  
-   Realiza un procesamiento MIME, incluida la aplicación de una firma digital, si se habilita en las propiedades de acuerdo unidireccional de AS2.  
  
-   Realiza entradas de correlación en la base de datos sin repudio (la tabla EdiMessageContent de la base de datos BizTalkDTADb).  
  
-   Realiza una copia del MDN (en su formato correspondiente) y lo almacena en la base de datos sin repudio, si se habilita en el **NRR habilitado para MDN de salida** propiedad del acuerdo.  
  
-   Entrega el MDN al adaptador de HTTP.  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 Componentes de envío](../core/as2-send-components.md)