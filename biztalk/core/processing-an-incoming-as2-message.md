---
title: Procesar un mensaje AS2 entrante | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 998ff334-71e2-4686-b2b7-44940a0ebed1
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b221ea3697180c27e347250570b0e96105a50f08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266396"
---
# <a name="processing-an-incoming-as2-message"></a>Procesar un mensaje AS2 entrante
La canalización de recepción AS2 procesa un mensaje entrante a través de AS2. La canalización de recepción AS2EdiReceive procesa un mensaje con codificación EDI mediante el Desensamblador EDI. La canalización de recepción AS2Receive procesa un mensaje sin codificación EDI mediante el Desensamblador de AS2. Las dos canalizaciones procesan la carga del mensaje AS2 y generan un MDN de forma distinta; sin embargo, ambas canalizaciones de recepción utilizan el descodificador AS2 para procesar el mensaje AS2.  
  
 Si AS2EdiReceivePipeline procesa un mensaje AS2 con una carga EDI, completa el procesamiento de AS2 del mensaje recibido antes de llevar a cabo el procesamiento de EDI. Cuando la canalización genera una confirmación de EDI para la carga EDI de un mensaje AS2, debe devolver la confirmación de EDI de forma asíncrona porque la respuesta de AS2 cierra la conexión.  
  
## <a name="the-receive-port"></a>El puerto de recepción  
 Se usa un puerto de recepción HTTP para recibir un mensaje AS2 con una carga EDI o que no sea EDI. Si el MDN se va a devolver de forma sincrónica, el puerto de recepción debe ser un puerto de recepción de solicitud-respuesta.  
  
 Un MDN puede devolverse de forma sincrónica o asincrónica. Esto viene determinado por el encabezado Disposition-notification-to del mensaje AS2, a menos que la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad está seleccionada en la ficha de acuerdo AS2 unidireccional del  **Propiedades del acuerdo de** cuadro de diálogo. Si la propiedad está seleccionada, la forma en que se devuelve el MDN se determina por la **solicitar MDN asíncrono** propiedad en el **configuración de MDN de remitente** página de la ficha de acuerdo AS2 unidireccional de la  **Propiedades del acuerdo de** cuadro de diálogo. Para obtener más información, consulte [mensajes AS2](../core/as2-messages.md) y [mensajes MDN](../core/mdn-messages.md).  
  
 Si el MDN se devuelve de forma sincrónica, el MDN se devolverá a través del puerto de envío de la ubicación de recepción bidireccional. Este MDN sirve como respuesta HTTP, por ejemplo, un valor 200OK que indica una recepción correcta del mensaje.  
  
 Si el MDN se va a devolver de forma asíncrona, deberá hacerse a través de un puerto de envío independiente. Si se usa un puerto de envío dinámico, el MDN se enviará a la dirección incluida en el encabezado Disposition-notification-to.  
  
> [!NOTE]
>  El puerto de recepción bidireccional que se va a utilizar para recibir mensajes AS2 no debe utilizarse para recibir mensajes MDN. Los mensajes MDN deben recibirse en un puerto de recepción unidireccional. El empleo de un puerto de recepción de solicitud-respuesta para un MDN devuelto de forma asíncrona evitaría que un mensaje 200OK se devolviese en respuesta al MDN entrante, lo que generaría reintentos innecesarios de la transmisión MDN.  
  
## <a name="how-the-as2-receive-pipelines-work"></a>Cómo funcionan las canalizaciones de recepción de AS2  
 Los pasos que usan las canalizaciones de recepción de AS2 en el procesamiento de un mensaje entrante de AS2 son los siguientes:  
  
-   Determina la entidad remitente mediante la correspondencia de AS2-de valor en el encabezado de AS2 del mensaje con el valor para AS2-de lista en la **identificadores** página de la ficha de acuerdo AS2 unidireccional de la **propiedades del acuerdo de** cuadro de diálogo. Si ese proceso no se lleva a cabo correctamente, intenta determinar la entidad de envío haciendo coincidir la propiedad de contexto AS2-From que se haya establecido para el mensaje entrante con el nombre de una entidad. Si se encuentra una coincidencia y el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad está seleccionada en la ficha de acuerdo AS2 unidireccional de la **propiedades del acuerdo de** cuadro de diálogo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará las propiedades de AS2 asociadas con el acuerdo para la entidad para procesar el mensaje AS2. Si la propiedad no está seleccionada, la canalización de recepción utilizará las etiquetas del encabezado de AS2 en el mensaje entrante. Si no se encuentra el acuerdo, la canalización anula el procesamiento, suspende el mensaje y genera una excepción.  
  
    > [!NOTE]
    >  El **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad le permite validar que un mensaje entrante tiene propiedades de firma, cifrado y compresión (si las propiedades se especifican en el acuerdo en el **validación** ficha del acuerdo unidireccional) y si no es así, suspender el mensaje y generar un error. Estos cambios deben negociarse con el acuerdo para la entidad remitente. Para obtener más información, consulte [configurar propiedades de AS2](../core/configuring-as2-properties.md).  
  
-   Si el acuerdo para la entidad remitente se ha determinado, pero se genera un error cuando la canalización de recepción intenta procesar el mensaje AS2, la canalización definirá la propiedad de contexto MessageDestination en el mensaje AS2 como SuspendQueue. La canalización de recepción suspenderá el mensaje en el cuadro de mensaje. La canalización de recepción también definirá la propiedad de contexto `EdiIntAS.IsAS2FailedMessage` como True. Si se habilita un MDN estableciendo **solicitar MDN** en el **configuración de MDN de remitente** página de la ficha de acuerdo AS2 unidireccional de la **propiedades del acuerdo** le de cuadro de diálogo, la canalización a continuación, devolver el MDN adecuado al remitente. La canalización siempre intentará devolver un MDN si se solicita.  
  
-   Determina si el mensaje es un duplicado, si la **comprobar mensajes duplicados dentro de** opción está seleccionada en el **validación** página de la ficha de acuerdo AS2 unidireccional de la **acuerdo Propiedades** cuadro de diálogo. La detección de mensajes duplicados se lleva a cabo haciendo coincidir los valores AS2-From, AS2-To y Message-ID del mensaje entrante con los valores existentes en los mensajes recibidos con anterioridad. Si coinciden los tres valores, la canalización de recepción establecerá el valor de la propiedad de contexto `EdiIntAs.IsAS2MessageDuplicate` en true. Si el **suspender mensajes duplicados** también se selecciona la opción en la **validación** página, se suspenderá el mensaje y registra un error.  
  
-   Recupera el nombre de archivo, si lo hubiera, de cada archivo de datos adjuntos y lo promueve en las propiedades de contexto.  
  
-   Realiza una copia del mensaje (en su formato correspondiente) y la almacena en la base de datos de recepción sin repudio, si esta opción está habilitada en las propiedades de acuerdo AS2 unidireccional.  
  
-   Lleva a cabo el procesamiento MIME, que incluye la comprobación de la firma y el descifrado del mensaje (basándose en las etiquetas del encabezado).  
  
-   Descomprime el mensaje recibido si estaba comprimido.  
  
-   Genera una respuesta HTTP anexa al MDN en modo de solicitud-respuesta sincrónico, o enviada como respuesta independiente en modo asíncrono.  
  
-   Genera una respuesta MDN si se solicita. La canalización generará un MDN basándose en las propiedades del acuerdo, si la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad está establecida, o de propiedades de contexto, si no se establece esta propiedad. Si los parámetros de configuración y los encabezados en el mensaje entrante son incoherentes, la canalización generará un MDN negativo.  
  
-   El Desensamblador EDI de la canalización de recepción AS2EdiReceive genera una confirmación de EDI si el mensaje tenía codificación EDI y se había habilitado una confirmación. La canalización enrutará la confirmación de EDI al cuadro de mensajes, desde donde un puerto de envío dinámico la seleccionará o la enviará de forma asíncrona. Las confirmaciones de EDI siempre se envían de forma asíncrona a través del transporte AS2 porque tanto las respuestas de MDN como de HTTP se envían de forma sincrónica.  
  
-   Realiza una copia del MDN y la almacena en la base de datos de recepción sin repudio, si esta opción está habilitada en las propiedades de acuerdo AS2 unidireccional.  
  
-   Realiza una copia del mensaje descodificado y la almacena en la base de datos de recepción sin repudio, si esta opción está habilitada en las propiedades de acuerdo AS2 unidireccional.  
  
 Si se produce un error de AS2, no se llevará a cabo más procesamiento en el mensaje recibido. Sin embargo, la canalización de recepción generará una respuesta de MDN.  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md)   
 [Mensajes de AS2](../core/as2-messages.md)   
 [Mensajes MDN](../core/mdn-messages.md)