---
title: Generar un MDN saliente | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12d7da1c-0d3c-42d4-9388-29f499353d13
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9fdd5b5d52d5d741b71ec46be276b4926528a67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984477"
---
# <a name="generating-an-outgoing-mdn"></a>Generar un MDN saliente
Las canalizaciones de recepción AS2 generan una respuesta MDN (Message Disposition Notification) para un mensaje entrante. Esto lo realiza el componente de la canalización del desensamblador EDI en la canalización de recepción AS2EReceive (en respuesta a un mensaje cifrado de EDI) o el componente de canalización del desensamblador AS2 en la canalización de recepción AS2Receive (en respuesta a un mensaje cifrado que no sea EDI).  
  
## <a name="when-and-how-an-mdn-is-generated"></a>Cuándo y cómo se genera un MDN  
 Un MDN se genera normalmente según los encabezados AS2 en el mensaje AS2 original, del siguiente modo:  
  
- Se enviará un MDN si el encabezado Disposition-Notification-To está presente en el mensaje AS2.  
  
- Si los encabezados Disposition-Notification-To y Receipt-Delivery-Option están presentes en el mensaje, el MDN se enviará de forma asíncrona. Se enviará a la URL en el encabezado Receipt-Delivery-Option, a través de una conexión distinta del mensaje original.  
  
- Si el encabezado Disposition-Notification-To está presente en el mensaje pero el encabezado Receipt-Delivery-Option no lo está, se enviará el MDN de forma sincrónica a través de la misma conexión que el mensaje original.  
  
  El desensamblador crea el encabezado AS2-From en el MDN a partir del encabezado AS2-To en el mensaje AS2 recibido y cree el encabezado AS2-To en el MDN a partir del encabezado AS2-From en el mensaje AS2 recibido.  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite anular estos valores, especificando si se generará un MDN y cómo se generará según las propiedades de acuerdo AS2 de una entidad. Invalidar la configuración del encabezado AS2 en el mensaje mediante la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad en la ficha de acuerdo AS2 unidireccional del **las propiedades del acuerdo**cuadro de diálogo. Esta propiedad le permite enviar un MDN aunque el encabezado AS2 no llame a ninguno, o enviar el MDN de forma asíncrona aunque el encabezado AS2 especifique una conexión sincrónica.  
  
  Si establece la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad, los valores de la **solicitar MDN** sección de la **configuración de MDN de remitente** página en la ficha de acuerdo AS2 unidireccional del **las propiedades del acuerdo** cuadro de diálogo se usará para el MDN, como sigue:  
  
- Se enviará un MDN si la **solicitar MDN** propiedad está seleccionada.  
  
- Si el **solicitar MDN** propiedad está seleccionada y el **solicitar MDN asíncrono** propiedad está activada, el MDN se enviará de forma asincrónica. El MDN se enviará a la dirección URL que el **Receipt-Delivery-Option (URL)** propiedad está establecida en, a través de una conexión distinta del mensaje original.  
  
- Si el **solicitar MDN** propiedad está seleccionada, pero el **solicitar MDN asíncrono** propiedad no está activada, el MDN se enviará de forma sincrónica a través de la misma conexión que el mensaje original.  
  
  Si el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad está establecida, AS2-de propiedad en el mensaje de encabezado se usará en la generación del MDN pero AS2-a se tomará de las propiedades del acuerdo, y la canalización firmará el MDN según la **solicitar MDN firmado** propiedad. Los encabezados AS2 corresponden a las propiedades de acuerdo como se muestran a continuación:  
  
|Propiedad de acuerdo|Encabezado AS2 en el mensaje.|  
|------------------------|-------------------------------|  
|Generar MDN|Disposition-Notification-To|  
|Firmar MDN|Signed-Receipt-Protocol|  
|Receipt-Delivery-Option|Receipt-Delivery-Option|  
  
 Si se habilita un MDN, la canalización de recepción promocionará las siguientes propiedades de contexto:  
  
- `EdiIntAS.DispositionMode`  
  
- `EdiIntAS.DispositionType`  
  
  Estas propiedades de contexto deben estar promocionadas para que el MDN se genere. Para obtener más información acerca de estas propiedades de contexto, vea [propiedades de contexto AS2](../core/as2-context-properties.md).  
  
  Si los parámetros de configuración y los encabezados en el mensaje entrante son incoherentes, la canalización generará un MDN negativo.  
  
  Si se solicita el MDN en las propiedades de acuerdo, la canalización de recepción intentará enviar un MDN incluso si se produce un error en el procesamiento AS2.  
  
## <a name="how-the-receive-pipeline-processes-a-generated-mdn"></a>Cómo la canalización de recepción procesa un MDN generado  
 Si un MDN se genera de acuerdo con las reglas anteriores, la canalización de recepción AS2EDIReceive o AS2Receive procesará el MDN de la siguiente forma:  
  
-   Realiza una copia del MDN (en formato de mensaje) y la almacena en la base de datos sin repudio, si esta opción está habilitada en las propiedades de acuerdo AS2 unidireccional.  
  
-   Realiza un procesamiento MIME, incluida la aplicación de una firma digital, si esta opción está habilitada en las propiedades del acuerdo de AS2 unidireccional.  
  
-   Calcula la MIC (Message Integrity Check) para la carga del mensaje AS2 y la anexa al campo de extensión Received-content-MIC del MDN. El algoritmo que se aplicará para el MIC se determina mediante el encabezado signed-receipt-micalg del mensaje entrante o el **algoritmo de firma** propiedad en el **configuración de MDN de remitente** página de la unidireccional pestaña del acuerdo de la **las propiedades del acuerdo** cuadro de diálogo (cuando se invalidan las propiedades del mensaje entrante). Puede ser SHA1 o MD5. El valor del algoritmo también se incluye en el MDN.  
  
-   Realiza entradas de correlación en la base de datos sin repudio.  
  
-   Realiza una copia del mensaje MDN.  
  
-   Si se va a transmitir el MDN de forma sincrónica, la canalización establece la propiedad `EdiIntAS.IsAS2AsynchronousMDN` en False; si se va a transmitir de forma asíncrona, establece la propiedad en True.  
  
-   Si el MDN se va a transmitir de forma sincrónica, la canalización de envío AS2Send asociada al puerto de recepción bidireccional recogerá el MDN que se base en la propiedad `EdiIntAS.IsAS2AsynchronousMDN` (establecida en False) y los token de correlación.  
  
    > [!NOTE]
    >  También puede establecer un puerto de envío que se suscribe al MDN sincrónico saliente. Para hacerlo, establezca el filtro de puerto de envío en `EdiIntAS.IsAS2MdnResponseMessage==True`.  
  
-   Si se va a transmitir el MDN de forma asíncrona, la canalización de recepción enruta el MDN en el cuadro de mensajes. Debe establecer un puerto de envío para subscribirse al MDN, estableciendo el puerto de envío en `IsAS2AsynchronousMdn==True`. La canalización de envío AS2Send recoge el mensaje que se basa en esta propiedad y los token de correlación. Si el puerto de envío es dinámico, enrutará el MDN que se basa en la dirección en la línea Receipt-Delivery-Notification en el encabezado del mensaje. Si el puerto de envío es estático, enrutará el mensaje en función de la propiedad Transporte URI del puerto de envío.  
  
## <a name="mdn-generation-rules"></a>Reglas de generación MDN  
 Las siguientes reglas se aplican a la generación de MDN:  
  
-   Cuando un remitente del mensaje solicita de forma específica una recepción firmada pero hay un error en el procesamiento de los contenidos del mensaje, el remitente del mensaje debe devolver una recepción firmada incluso si la transacción no es válida. El motivo del error en el procesamiento de los contenidos del mensaje debe establecerse en “disposition-field”.  
  
-   Cuando la solicitud para la recepción MDN especifica de forma explícita que la recepción se va a firmar pero el receptor del mensaje original no puede satisfacer el formato de protocolo solicitado o el algoritmo MIC solicitado, se devolverá una recepción firmada o sin firmar.  
  
-   Cuando una firma no se solicita de forma explícita, o si el acuerdo de la entidad de recepción no reconoce el parámetro de solicitud de recepción firmada, la entidad de recepción puede devolver una recepción sin firmar, sin firmar o no enviarla.  
  
## <a name="mic-generation"></a>Generación de MIC  
 Cuando es necesario un MDN, el receptor del mensaje original genera una MIC (Message Integrity Check) y la agrega al MDN. Cuando el intercambio EDI forma parte de un tipo de contenido MIME de varias partes, la MIC debe calcularse a través del contenido de varias partes completo, incluido el intercambio EDI y los encabezados MIME. Para los mensajes sin firmar y cifrados, el MIC que se va a devolver se calcula en el encabezado MIME descifrado y el contenido. Para los mensajes sin cifrar y sin firmar, debe calcularse la MIC a través de los contenidos de mensaje sin los encabezados MIME.  
  
## <a name="see-also"></a>Vea también  
 [Cómo recibe BizTalk Server los mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md)