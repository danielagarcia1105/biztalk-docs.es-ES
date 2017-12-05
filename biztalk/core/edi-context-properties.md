---
title: Propiedades de contexto EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6a408af-daf5-4e9e-afb3-9fd1795e8c16
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36e2f9fcc839625cc0b1ac01ec6e70b53eb2a6e2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="edi-context-properties"></a>Propiedades de contexto de EDI
Las propiedades de contexto del mensaje del esquema de propiedades global de EDI están expuestos públicamente, lo que permite a los usuarios utilizarlos en operaciones como el enrutamiento de mensajes. Estas propiedades de contexto están definidas en el archivo PropertySchema.xsd del ensamblado Microsoft.BizTalk.Edi.BaseArtifacts. El espacio de nombres para las propiedades es `http://schemas.microsoft.com/ Edi/PropertySchema`. Si se promocionan, estas propiedades de contexto de mensaje están disponibles como Edi. \< *Nombre de la propiedad* \> en el **filtros** página de la **cuadro de diálogo de propiedades de puerto de envío** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].


## <a name="context-properties-list"></a>Lista de propiedades de contexto  
 Las propiedades de contexto de EDI también están disponibles en una orquestación, siempre que la referencia al ensamblado Microsoft.BizTalk.Edi.BaseArtifacts se haya agregado al proyecto de la orquestación.
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|AK901|string|Indica si el grupo funcional identificado en el segmento AK1 de la confirmación se ha aceptado o rechazado (sólo confirmación 997 de X12).|  
|AttachmentId|String|El identificador de los datos adjuntos del mensaje.|  
|AgreementID|int|Escrito por la canalización de recepción de EDI. Especifica el identificador del contrato en el que se resuelve el mensaje entrante. Para un contrato de reserva, este valor es 0.|  
|AgreementName|String|Escrito por la canalización de recepción de EDI. Especifica el nombre del contrato en el que se resuelve el mensaje entrante. Para un acuerdo de reserva este valor es **BTSGuestParty**.|  
|AgreementNameForSend|String|Lo usa la canalización de envío EDI para la resolución de contrato del documento de salida.|  
|AgreementPartIDForSend|int|Lo usa la canalización de envío EDI para la resolución de contrato del documento de salida. Este valor lo escribe la orquestación de procesamiento por lotes.|  
|AgreementPartIDOnReceive|int|Escrito por la canalización de recepción de EDI. Especifica el identificador de contrato unidireccional del contrato al que se ha resuelto el mensaje entrante. Para un contrato de reserva, este valor es 0.|  
|BatchElementValidationFailure|boolean|Indicación de que el sistema de procesamiento por lotes ha promovido un error cuando un elemento por lotes no ha podido efectuar una validación.|  
|BatchEncodingType|string|El tipo de codificación que BizTalk Server debe usar para codificar un intercambio por lotes saliente.|  
|BatchId|int|El identificador de lote de la configuración de lotes que se debe usar al procesar este documento, si este último únicamente coincide con un filtro de lote.|  
|BatchIds|String|Una lista de identificadores de lotes de los conjuntos de filtros de lotes coincidentes, si el documento coincide con más de un filtro de lote.|  
|BatchingError|string|Una descripción del error que el sistema de procesamiento por lotes ha promovido al suspender un elemento por lotes.|  
|BatchName|String|El nombre de la configuración del lote que se usará al procesar este documento.|  
|CodePage|string|La página de códigos que se usará para validar el intercambio.|  
|CONTRL_UCI4|string|El campo de código de acción de una confirmación CONTRL, que indica si el intercambio se ha aceptado (con el valor "8") o rechazado a causa de un error en el segmento UNA o UNB (con el valor "4") (sólo confirmación de CONTRL de EDIFACT).|  
|DestinationPartyID (en desuso en BizTalk Server)|int|El Id. de la entidad de destino a la que debe enviarse el mensaje.|  
|DestinationPartyName (en desuso en BizTalk Server)|string|El nombre de la entidad de destino a la que debe enviarse el mensaje.|  
|DestinationPartyReceiver<br />Identificador|string|El identificador de la entidad de destino a la que debe enviarse el mensaje. Esta propiedad puede promocionarse en un componente personalizado para habilitar la resolución de entidades en la canalización de envío.|  
|DestinationPartyReceiver<br />Qualifier|string|El calificador de la entidad de destino a la que debe enviarse el mensaje. Esta propiedad puede promocionarse en un componente personalizado para habilitar la resolución de entidades en la canalización de envío.|  
|DestinationPartySender<br />Identificador|string|El identificador de la entidad que envía el mensaje a la entidad de destino. Esta propiedad puede promocionarse en un componente personalizado para habilitar la resolución de entidades en la canalización de envío.|  
|DestinationPartySender<br />Qualifier|string|El calificador de la entidad que envía el mensaje a la entidad de destino. Esta propiedad puede promocionarse en un componente personalizado para habilitar la resolución de entidades en la canalización de envío.|  
|EncodingType|short|El tipo de codificación que BizTalk Server debe usar para codificar un mensaje saliente.|  
|ErrorDescription|string|En un mensaje suspendido, contiene una copia del mensaje de error (similar al mensaje del Visor de eventos).|  
|GS_Segment|string|El segmento GS completo (grupo funcional) (X12).<br /><br /> La canalización de recepción EDI escribe esta propiedad en el contexto cuando se ha dividido el intercambio en conjuntos de transacciones, y no cuando se conserva el intercambio.|  
|GS01|string|El código de identificador funcional (X12).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|GS02|string|El código de remitente de la aplicación (X12).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|GS03|string|El código de receptor de la aplicación (X12).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|GS07|string|La agencia responsable (X12).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|GS08|string|El código de identificador de la versión, el lanzamiento o la industria (X12).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|ISA_Segment|string|El segmento ISA completo (encabezado de control de intercambio) (X12).<br /><br /> El servidor BizTalk Server escribe esta propiedad en el contexto cuando se ha dividido el intercambio en conjuntos de transacciones, y no cuando se conserva el intercambio.<br /><br /> Esta propiedad contiene información de autorización o seguridad (ISA2, Información de autorización, e ISA4, Información de seguridad) que puede dar lugar a la divulgación de información. Puede utilizar la propiedad enmascarar información de autorización y seguridad de contraseña (en la **validación y generación de confirmación** página) para reemplazar cada carácter en los campos ISA2 e ISA4 con un carácter "#". Se trata de un proceso unidireccional: los caracteres "#" no se puede convertir en caracteres reales.<br /><br /> La canalización de recepción EDI escribe esta propiedad en el contexto cuando se ha dividido el intercambio en conjuntos de transacciones, y no cuando se conserva el intercambio.|  
|ISA05|string|El calificador del remitente del intercambio (X12).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|ISA06|string|El identificador del remitente del intercambio (X12).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|ISA07|string|El calificador del receptor del intercambio (X12).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|ISA08|string|El identificador del receptor del intercambio (X12).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|ISA15|string|El indicador de uso (X12).<br /><br /> La canalización de recepción EDI promociona esta propiedad en el contexto si el intercambio no es un intercambio por lotes que se conserva.|  
|IsResendControlMessage|int|Lo usa el motor AS2 para indicar que se debe retransmitir el envío de un mensaje AS2, ya que no se ha recibido ninguna respuesta MDN dentro del tiempo configurado.|  
|IsSystemGeneratedACK|boolean|Indica que el mensaje es una confirmación (TA1 o 997 de X12, o bien CONTRL de EDIFACT) generada por el sistema. Se puede establecer como True o False.<br /><br /> Se trata de una propiedad de contexto de mensaje que está disponible como EDI. IsSystemGeneratedACK en la **filtros** página de la **propiedades de puerto de envío** cuadro de diálogo.|  
|ReceiverPartyName|String|Escrito por la canalización de recepción de EDI. Especifica el nombre del socio de destino proporcionado en el acuerdo en el que se resuelve el mensaje. Para un acuerdo de reserva este valor es **RECEIVE-PARTNER**.|  
|ReceiverPartyNameForSend|String|Lo usa la canalización de envío EDI para la resolución de contrato de documentos de salida.|  
|ReuseEnvelope|boolean|Indica si un intercambio se conserva o se divide. Si el intercambio se conserva, BizTalk Server reutilizará el sobre al procesar el intercambio para su envío.|  
|SenderPartyName|String|Escrito por la canalización de recepción de EDI. Especifica el nombre del socio de origen proporcionado en el acuerdo en el que se resuelve el mensaje entrante. Para un acuerdo de reserva este valor sería **BTS-SENDER**.|  
|SenderPartyNameForSend|String|Lo usa la canalización de envío EDI para la resolución de contrato de documentos de salida.|  
|ST01|string|El código de identificador del conjunto de transacciones (X12).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|ST03|string|El código de identificador de la versión, el lanzamiento o la industria (X12).<br /><br /> Puede escribir y promocionar esta propiedad para el contexto y usarla para el enrutamiento de mensajes.|  
|TA1_TA104|string|El campo de comportamiento del motor de una confirmación TA104, que indica si el intercambio se ha aceptado (con el valor "A"), aceptado con errores (con el valor "E") o si se ha rechazado o suspendido (con el valor "R") (sólo confirmación TA1 de X12).|  
|ToBeBatched|boolean|Indica si la orquestación de procesamiento por lotes debe procesar el mensaje por lotes con otros mensajes.<br /><br /> Después de procesar por lotes un intercambio, la orquestación de procesamiento por lotes establece esta propiedad como "False".|  
|ToBeRouted|boolean|Indica si la orquestación de enrutamiento debe elegir el mensaje para crear tantas copias del elemento por lotes como número de suscripciones posea dicho elemento y enrutar las copias al cuadro de mensajes.|  
|UNA_Segment|string|El segmento UNA completo (aviso de cadena de servicio) (EDIFACT).<br /><br /> La canalización de recepción EDI escribe esta propiedad en el contexto cuando se ha dividido el intercambio en conjuntos de transacciones, y no cuando se conserva el intercambio.|  
|UNB_Segment|string|El segmento UNB completo (encabezado de control de intercambio) (EDIFACT).<br /><br /> La canalización de recepción EDI escribe esta propiedad en el contexto cuando se ha dividido el intercambio en conjuntos de transacciones, y no cuando se conserva el intercambio.<br /><br /> Esta propiedad contiene información de autorización o seguridad (UNB6.1 y UNB6.2) que puede dar lugar a la divulgación de información. Puede usar la propiedad Enmascarar información de seguridad, de autorización y de contraseña para reemplazar los campos UNB6.1 y UNB6.2 con un carácter “#”. Tenga en cuenta que el carácter “#” no puede convertirse en caracteres reales.|  
|UNB11|string|El indicador de uso (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNB2_1|string|El Id. del remitente del intercambio (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNB2_2|string|El calificador del código de remitente del intercambio (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNB2_3|string|La dirección para el enrutamiento invertido (EDIFACT)<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNB3_1|string|El Id. del destinatario del intercambio (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNB3_2|string|El calificador del código de destinatario del intercambio (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNG_Segment|string|El segmento UNG completo (grupo funcional) (X12).<br /><br /> La canalización de recepción EDI escribe esta propiedad en el contexto cuando se ha dividido el intercambio en conjuntos de transacciones, y no cuando se conserva el intercambio.|  
|UNG1|string|La identificación de grupo funcional (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNG2_1|string|La identificación del remitente de la aplicación (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNG3_1|string|La identificación del destinatario de la aplicación (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNH2_1|string|El tipo de mensaje (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNH2_2|string|El número de versión del mensaje (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
|UNH2_3|string|El número de versión de mensaje (EDIFACT).<br /><br /> La recepción de EDI canalización promociona esta propiedad en el contexto (si el intercambio no es un intercambio por lotes que se va a conservar).|  
  
## <a name="extracting-individual-fields-from-the-segment-context-properties"></a>Extraer campos individuales de las propiedades de contexto de segmento  
 Las canalizaciones de recepción EDI no escriben ni promocionan algunas propiedades en el contexto de mensaje como propiedades individuales, sino únicamente como parte de la cadena del segmento. Esto se lleva a cabo por razones de rendimiento, ya que la promoción de propiedades afecta al rendimiento. Por ejemplo, las canalizaciones de recepción promocionan los campos ISA5, ISA6, ISA7, ISA8 e ISA15 del segmento ISA como propiedades individuales, mientras que el resto de campos ISA solo se escriben en el contexto como parte de la propiedad ISA_Segment. Estas propiedades se escriben o promocionan sólo cuando **ReuseEnvelope** no está establecido en True, lo que indica que no se va a conservar un intercambio por lotes recibido.  
  
 Si necesita que un campo individual de uno de los segmentos (ISA, GS, UNB, UNG o UNA) se escriba en el contexto del mensaje, pero la escritura no se lleva a cabo de forma predeterminada, tendrá que escribir un componente personalizado para escribirla en el contexto de mensaje. Este componente personalizado debe analizar los campos del segmento y escribir un campo individual en el contexto del mensaje.  
  
 El ejemplo Message Enrichment muestra cómo utilizar un analizador para extraer los campos individuales de los segmentos y escribirlos en el contexto. En este ejemplo se incluye en el \<unidad\>: \Program BizTalk Server\SDK\Samples\EDI\MessageEnrichment. Para obtener más información, consulte [ejemplo de enriquecimiento de mensajes (ejemplo de BizTalk Server)](../core/message-enrichment-sample-biztalk-server-sample.md).  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo y configuración de soluciones EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md)