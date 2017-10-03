---
title: Mensajes MDN | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16ac6253-0be5-4636-b102-bf5af8956261
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a6600237961b59e440a460263a8f4315b2c4773
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mdn-messages"></a>Mensajes MDN
La notificación de disposición de mensaje (MDN) es la confirmación enviada en respuesta a un mensaje AS2. Si se habilita un MDN, la transmisión AS2 no se completa hasta que se comprueba y recibe el MDN. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]siempre intentará devolver un MDN para indicar el estado de procesamiento de mensajes, incluso si se produjo un error en el procesamiento del mensaje AS2.  
  
 El MDN proporciona comprobación de que:  
  
-   **Que el mensaje original ha recibido correctamente por la parte receptora**. El remitente del mensaje original lo comprueba comparando el identificador de mensaje del mensaje original enviado con el campo original-message-id que el receptor ha incluido en el MDN.  
  
-   **Que el socio receptor ha comprobado la integridad de los datos intercambiados**. El remitente del mensaje original lo comprueba mediante la comparación de la MIC que se calcula a partir de la carga del mensaje original enviado, con la MIC que el receptor ha calculado en la carga del mensaje recibido e incluido en el campo Received-content-MIC del MDN (si está firmado).  
  
-   **Que no hay repudio de recepción**. El remitente lo realiza mediante la comprobación del MDN firmado con la clave pública del socio receptor y la comprobación de que el valor MIC devuelto en el MDN es el mismo que la MIC para la carga del mensaje original almacenada en una base de datos sin repudio.  
  
    > [!NOTE]
    >  Un MDN sincrónico que sirve como una respuesta HTTP, por ejemplo, 200 OK.  
  
    > [!NOTE]
    >  Para obtener más información sobre el procesamiento de recepción de los MDN, vea [procesamiento de MDN entrante](../core/processing-an-incoming-mdn.md). Para obtener más información sobre el procesamiento de envío de MDN, vea [enviar un MDN saliente](../core/sending-an-outgoing-mdn.md).  
  
## <a name="properties-used-to-generate-the-mdn"></a>Propiedades usadas para generar el MDN  
 Recibir el AS2Receive canalización generará un MDN mediante las propiedades de acuerdo de AS2 de la entidad si la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad está seleccionada en la ficha de acuerdo unidireccional en el  **Propiedades del acuerdo de** cuadro de diálogo. En esta instancia, la propiedad AS2-From en el encabezado de mensaje se usará en la generación del MDN pero se tomarán otras propiedades de la configuración de acuerdo AS2 de la entidad.  
  
 Si la opción para invalidad la propiedad de AS2 no se selecciona o el acuerdo de AS2 de la entidad no está disponible, la canalización de recepción generará el MDN mediante las etiquetas de encabezados de AS2 en el mensaje entrante.  
  
 Puede firmarse un MDN pero no puede cifrarse o comprimirse.  
  
## <a name="mdn-context-properties"></a>Propiedades de contexto de MDN  
 Las propiedades de contexto utilizadas en el procesamiento de mensajes MDN incluyen propiedades que se pueden ser promocionadas así como propiedades que no se exponen públicamente pero pueden verse un mensajes de seguimiento o suspendidos. Para obtener una lista de estas propiedades de contexto, vea [propiedades de contexto AS2](../core/as2-context-properties.md).  
  
 Las propiedades de contexto de DispositionMode y DispositionType deben promocionarse en orden para que se genere un MDN. Si se produce un error en la carga EDI o AS2, la propiedad DispositionType indicará el error. Puede ver esta propiedad en el **detalles del mensaje** cuadro de diálogo que se muestra (a través del cuadro de diálogo Detalles de servicio) en instancias de servicio suspendidas en la **concentrador de grupo** página de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Consola de administración. Si se produce un error en el encabezado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] indicará el error en la propiedad DispositionType e intentará enviar el MDN pero, dependiendo del error, puede que no pueda hacerlo.  
  
## <a name="mdn-headers"></a>Encabezados MDN  
 El MDN contiene los encabezados siguientes:  
  
-   **Encabezados HTTP/AS2**. Para obtener más información, consulte [mensajes AS2](../core/as2-messages.md).  
  
-   **Capa de transferencia**. esto incluye el encabezado Content-Type que incluye el mensaje con varias partes firmado, el algoritmo para la MIC, el protocolo de formato de firma y encabezados secundarios de límites de varias partes más externos.  
  
-   **Primera parte**. la primera parte del mensaje firmado con varias partes es el MDN integrado. Es legible por el usuario.  
  
-   **Segunda parte**. la segunda parte del mensaje firmado con varias partes contiene la firma digital, una referencia al mensaje original, el estado y tipo de disposición y el valor MIC. Es legible por el equipo.  
  
 La propiedad de contexto MessageID, el encabezado AS2-From y el encabezado AS2-To se usan para correlacionar un MDN a un mensaje AS2 al que se está respondiendo. El encabezado Original-Message-ID en un MDN viene del encabezado Message-ID del mensaje AS2 al que el MDN está respondiendo.  
  
## <a name="mic"></a>MIC  
 La comprobación de integridad del mensaje (MIC) se usa para comprobar si un MDN correlaciona con la carga del mensaje original enviado. La síntesis de MIC se incluye en el campo de extensión Received-Content-MIC en la segunda parte del mensaje MDN firmado con varias partes.  
  
 Si se habilita un MDN, cuando la canalización de envío AS2 procesa un mensaje saliente, se calcula MICHashValue a partir de la carga del mensaje. La canalización de envío guarda el valor hash en la tabla EdiInt_Mic de la base de datos BizTalkMsgBoxDb. En esta tabla se realiza el seguimiento de los mensajes AS2, se identifican de forma única mediante los valores S2From, AS2To y MessageID, junto con la columna MICHashValue. El receptor del mensaje calcula el valor hash de MIC cuando procesa la carga del mensaje e incluye el valor hash en el MDN que devuelve. El remitente del mensaje original comparará el valor hash de MIC en el MDN que recibe con el valor hash que almacena. Si coinciden, elimina el MDN y la entrada en la tabla EdiInt_Mic y se completa la transmisión.  
  
 La MIC es de codificación base64. El algoritmo que se va a aplicar a la MIC puede ser SHA1 o MD5. Se determina a partir del **algoritmo de firma** desplegable (habilitado si **solicitar MDN firmado** propiedad está activada) en el **configuración de MDN de remitente** página del acuerdo unidireccional pestaña en el **propiedades del acuerdo de** cuadro de diálogo. También se determina a partir del encabezado Signed-Receipt-MICalg AS2 del mensaje original.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes de AS2](../core/as2-messages.md)   
 [Procesamiento de MDN entrante](../core/processing-an-incoming-mdn.md)   
 [Enviar un MDN saliente](../core/sending-an-outgoing-mdn.md)