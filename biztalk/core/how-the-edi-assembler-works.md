---
title: Cómo funciona el ensamblador EDI | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3785870-08ab-4fc2-8f7e-7c5a37639a7a
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2ac76c3447ab0a9caf641b2b70b262ee84cf528
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982405"
---
# <a name="how-the-edi-assembler-works"></a>Cómo funciona el ensamblador EDI
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realiza la mayoría del procesamiento de intercambios codificados en EDI que se van a enviar en la canalización de envío de EDI (`Microsoft.BizTalk.DefaultPipelines.EDISendPipeline`). La canalización incluye el componente de canalización del ensamblador EDI que realiza el siguiente procesamiento:  
  
-   Serializa el intercambio EDI, convirtiendo los mensajes codificados en XML en conjuntos de transacciones EDI en el intercambio.  
  
-   Realiza la validación de esquemas EDI, validación de campos cruzados para mensajes con codificación X12 (si está configurado), validación estructural de EDI y validación de esquemas extendida (si el esquema se ha personalizado con un nodo que no sea de tipo EDI).  
  
-   Aplica un sobre al mensaje EDI.  
  
-   Procesa las confirmaciones técnicas y funcionales recibidas en respuesta a los mensajes EDI, anulando el procesamiento por lotes de las confirmaciones si está configurado para ello.  
  
## <a name="applying-an-envelope-to-an-outgoing-edi-message"></a>Aplicar un sobre a un mensaje EDI saliente  
 Cuando la canalización de envío EDI genera un mensaje EDI saliente a partir de un archivo XML intermedio, aplica un sobre que contiene encabezados de grupo y de intercambio para el mensaje según las propiedades de EDI establecidas para el acuerdo en el lado de recepción. Si la canalización de envío no ha podido determinar el acuerdo de recepción desde el puerto de envío, usará las propiedades de reserva para aplicar el sobre.  
  
 Si la propiedad de contexto `EdiOverride.OverrideEdiHeader` se establece en true, la canalización de envío EDI usará los valores especificados en la recopilación de la propiedad EdiOverride para construir el sobre. Si no hay ningún valor en la recopilación, se usará el valor de EDI correspondiente en las propiedades del acuerdo. Si no existe un valor en la recopilación EdiOverride o las propiedades del acuerdo, se usarán las propiedades del acuerdo EDI de reserva.  
  
 Si el archivo XML intermedio incluye una etiqueta reservada o la propiedad de contexto ReuseEnvelope, el mensaje es un lote conservado y la lógica de aplicación del sobre no se aplicará.  
  
### <a name="sources-for-x12-envelope-values"></a>Orígenes para valores de sobre X12  
 En la tabla siguiente se muestra de dónde toma la canalización de envío EDI la información que necesita para cada parte de un sobre X12:  
  
|Encabezado|Source|  
|------------|------------|  
|Encabezado de control de intercambio (ISA)|-Propiedades de contexto EdiOverride (si `EdiOverride.OverrideEdiHeader` es true).<br />-Si se ha definido un contrato, de segmento ISA de diferentes páginas bajo las definiciones de la **configuración de intercambio** sección en las propiedades del acuerdo unidireccional en el **las propiedades del acuerdo** cuadro de diálogo.<br />-Si se ha definido ningún acuerdo, de segmento ISA definiciones de diferentes páginas bajo la **configuración de intercambio** sección la **configuración de reserva de EDIFACT** cuadro de diálogo.|  
|Encabezados de grupo funcional (GS)|-Propiedades de contexto EdiOverride (si `EdiOverride.OverrideEdiHeader` es true)<br />-Si se ha definido un contrato, de las definiciones de segmento GS el **sobres** página (en **configuración del conjunto de transacciones** sección) en las propiedades del acuerdo unidireccional en el **las propiedades del acuerdo**  cuadro de diálogo<br />-Si se ha definido ningún acuerdo, de las definiciones de segmento GS el **sobres** página (en **configuración del conjunto de transacciones** sección) en el **X12 configuración de reserva** cuadro de diálogo<br /><br /> Si hay un acuerdo definido, los valores para los elementos de datos GS se determinan según la combinación del identificador del conjunto de transacciones (ST1), la versión y el espacio de nombres de destino. Estos valores se comparan con la cuadrícula en el **sobres** página (en **configuración del conjunto de transacciones** sección) de las propiedades del acuerdo (si se ha definido un acuerdo) o las propiedades del acuerdo de reserva (si se encuentra se ha definido ningún acuerdo):<br /><br /> -Si hay una fila coincidente, se usan los valores contenidos en la fila coincidente para el encabezado GS.<br />-Si no hay ninguna coincidencia, pero se define una fila de forma predeterminada, todos los elementos de datos GS, excepto GS01 se rellenan desde la fila predeterminada. GS01 se determina dinámicamente basándose en el valor de ST1.<br />-Si no hay ninguna fila coincidente y no hay ninguna fila de forma predeterminada, el mensaje se suspende. **Nota:** para que un grupo sea exclusivo de otros grupos, no todos estos valores pueden ser los mismos que los de otro grupo. <br /><br /> Si no hay ningún acuerdo definido, los elementos de datos GS se rellenan a partir de las propiedades de acuerdo de reserva.|  
  
### <a name="sources-for-edifact-envelope-values"></a>Orígenes para valores de sobre EDIFACT  
 En la tabla siguiente se muestra de dónde toma la canalización de envío EDI la información que necesita para cada parte de un sobre EDIFACT:  
  
|Encabezado|Source|  
|------------|------------|  
|Notificación del servicio (UNA)|-Propiedades de contexto EdiOverride (si `EdiOverride.OverrideEdiHeader` es true).<br />-Si se ha definido un contrato, de las definiciones de segmento UNA **juego de caracteres y separadores** página en las propiedades del acuerdo unidireccional en el **las propiedades del acuerdo** cuadro de diálogo.<br />-Si se ha definido ningún acuerdo, de las definiciones de segmento UNA **juego de caracteres y separadores** página en el **configuración de reserva de EDIFACT** cuadro de diálogo.|  
|Encabezado de control de intercambio (UNB)|-Propiedades de contexto EdiOverride (si `EdiOverride.OverrideEdiHeader` es true).<br />-Si se ha definido un contrato, las definiciones de diferentes páginas bajo de segmento UNB el **configuración de intercambio** sección en las propiedades del acuerdo unidireccional en el **las propiedades del acuerdo** cuadro de diálogo.<br />-Si se ha definido ningún acuerdo, de segmento UNB definiciones de diferentes páginas bajo la **configuración de intercambio** sección la **configuración de reserva de EDIFACT** cuadro de diálogo.|  
|Encabezados de grupo funcional (UNG)|-Propiedades de contexto EdiOverride (si `EdiOverride.OverrideEdiHeader` es true).<br />-Si se ha definido un contrato, las definiciones de segmento UNG y UNH el **sobres** página (en **configuración del conjunto de transacciones** sección) en las propiedades del acuerdo unidireccional en el **contrato Propiedades** cuadro de diálogo<br />-Si se ha definido ningún acuerdo, las definiciones de segmento UNG y UNH el **sobres** página (en **configuración del conjunto de transacciones** sección) en las propiedades del acuerdo unidireccional en el **contrato Propiedades** cuadro de diálogo en el **configuración de reserva de EDIFACT** cuadro de diálogo<br /><br /> Si hay un acuerdo definido, los valores de los elementos de datos UNG se determinan según la combinación del tipo de mensaje (UNH2.1), el número de versión del mensaje (UNH2.3), el código asignado (UNH2.5), la versión y el espacio de nombres de destino. **Nota:** para que un grupo sea exclusivo de otros grupos, no todos estos valores pueden ser los mismos que los de otro grupo.|  
  
### <a name="applying-transaction-set-header-and-trailer-segments"></a>Aplicar segmentos de encabezado y finalizador de conjuntos de transacciones  
 Un conjunto de transacciones XML que se va a serializar en un intercambio EDI saliente debe tener un encabezado y finalizador del conjunto de transacciones. No obstante, el ensamblador EDI procesará el mensaje si no tiene un encabezado o finalizador del conjunto de transacciones. Los segmentos de encabezado y finalizador del conjunto de transacciones en esquemas X12 y EDIFACT son opcionales para los conjuntos de transacciones XML. Si una transacción no tiene un encabezado ni un finalizador, el ensamblador EDI en la canalización de envío EDISend o AS2EDISend agregará los valores de encabezado y finalizador del conjunto de transacciones a ella. Estos valores se basarán en las asignaciones o los cálculos. El ensamblador EDI lo hará para el intercambio XML (un lote conservado), conjunto de transacciones procesado por lotes XML y un conjunto de transacciones XML.  
  
 Si la asignación origina un error de validación, el conjunto de transacciones XML o el XML de intercambio se suspende con el error correspondiente en el visor de eventos como, por ejemplo, que la longitud o el tipo de datos no es válido, o un código de agencia de control no válido.  
  
####  <a name="BKMK_X12"></a> X12 segmentos de finalizador y encabezado del conjunto de transacciones  
 En el caso de conjuntos de transacciones con codificación X12 que no tengan segmentos de encabezado y finalizador, el ensamblador EDI establecerá los segmentos ST y SE del siguiente modo:  
  
|Segmento de encabezado y pie de página|Valor|  
|----------------------------|-----------|  
|Código identificador del conjunto de transacciones (ST01)|Asignado a los últimos tres caracteres del nombre RootNode del conjunto de transacciones XML entrante. Por ejemplo, "855" de "X12_00401_855". En el caso de reclamaciones HIPAA cuyo código de identificador TS sea 837P, 837D o 837I, se usa "837".|  
|ST02 (número de Control del conjunto de transacciones)|El valor de `EdiOverride.ST02` (si `EdiOveride.OverrideEdiHeader` es true,) o asignado al valor de la **del conjunto de transacciones (ST02) del número de control** en el **configuración de Host Local** página (en **de intercambio Configuración de**) de la ficha de acuerdo unidireccional del **las propiedades del acuerdo** cuadro de diálogo.<br /><br /> Se aplica un número de control nuevo o aumentado independientemente de la configuración de la **aplicar Id. nuevo** propiedad.|  
|ST03 (identificador de versión)|Asignado al valor de ST03 desde el conjunto de transacciones XML entrante. Por ejemplo, “005010X218” para un documento 820 de 5010 HIPAA (deducción de nómina). ST03 se valida con el esquema que se usa para validar el conjunto de transacciones. **Nota:** ST03 es obligatorio para todas las transacciones de la versión 5010 HIPAA, excepto 835.|  
|Número de segmentos incluidos (SE01)|Establecido como el número total de segmentos del conjunto de transacciones, incluidos los segmentos ST y SE.|  
|Número de control de conjunto de transacciones (SE02)|Asignado al valor de ST02 del conjunto de transacciones.|  
  
 Los demás elementos de datos del encabezado del conjunto de transacciones, como ST03, son opcionales y, por lo tanto, no tienen ningún valor asignado en los segmentos generados.  
  
####  <a name="BKMK_EDIFACT"></a> Encabezado del conjunto de transacciones EDIFACT y segmentos de finalizador  
 En el caso de conjuntos de transacciones con codificación EDIFACT que no tengan segmentos de encabezado y finalizador, el ensamblador EDI establecerá los segmentos UNH y UNT del siguiente modo:  
  
|Segmento de encabezado y pie de página|Valor|  
|----------------------------|-----------|  
|Número de control de referencia de mensaje (UNH01)|El valor de `EdiOverride.UNH1` (si `EdiOverride.OverrideEdiHeader` es true,) o asignado al valor de **número de referencia (UNH1)** en el **configuración de Host Local** página (en **deconfiguracióndeintercambio**) de la pestaña del acuerdo unidireccional en el **las propiedades del acuerdo** cuadro de diálogo. Se aplica un número de control nuevo o aumentado independientemente de la configuración de la **aplicar Id. nuevo** propiedad.|  
|Tipo de mensaje (UNH2.1)|Asignado a los seis últimos caracteres del nombre RootNode del conjunto de transacciones XML entrante. Por ejemplo, "INVOIC" de "EFACT_D96A_INVOIC".|  
|Número de versión del mensaje (UNH2.2)|Asignado al séptimo carácter del nombre RootNode del conjunto de transacciones XML entrante. Por ejemplo, "D" de "EFACT_D96A_INVOIC".|  
|Número de versión del mensaje (UNH2.3)|Asignado a los caracteres octavo, noveno y décimo del nombre RootNode del conjunto de transacciones XML entrante. Por ejemplo, "96A" de "EFACT_D96A_INVOIC".|  
|Codificación de agencia de control (UNH2.4)|Siempre asignado a la cadena ‘UN’.|  
|Número de segmentos incluidos (UNT01)|Establecido como el número total de segmentos del conjunto de transacciones, incluidos los segmentos UNH y UNT.|  
|Número de control de referencia de mensaje (UNT02)|Asignado al valor de **número de referencia (UNH1)** en el **configuración de Host Local** página (en **configuración de intercambio**) de la ficha de acuerdo unidireccional en el  **Las propiedades del acuerdo** cuadro de diálogo|  
  
 Los demás elementos de datos del encabezado del conjunto de transacciones UNH, como UNH3 a UNH6, son opcionales y, por lo tanto, no tienen ningún valor asignado en los segmentos generados. Si alguno de estos campos es necesario, debe establecerlos con un valor en el conjunto de transacciones XML entrante.  
  
### <a name="additional-processing-on-envelope-of-an-outgoing-message"></a>Procesamiento adicional en el sobre de un mensaje saliente  
 La canalización de envío EDI lleva a cabo el siguiente procesamiento en el sobre de un mensaje saliente.  
  
#### <a name="control-numbers"></a>Números de control  
 La canalización de envío EDI especificará un número de control de intercambio, un número de control de grupo y un número de control (o referencia) del conjunto de transacciones en los segmentos del sobre de cada intercambio saliente. Estos números se muestran en la siguiente tabla:  
  
|Número de control|Campo X12|Campo EDIFACT|  
|--------------------|---------------|-------------------|  
|Número de control de intercambio.|ISA13|UNB5|  
|Número de control de grupo.|GS6|UNG5|  
|Número de control de conjunto de transacciones (X12)<br /><br /> Número de referencia de conjunto de transacciones (EDIFACT)|ST2|UNH1|  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] establecerá el número de control de intercambio para el siguiente intercambio enviado basándose en el intervalo de valores que escribió en el **número de control de intercambio (ISA13)** propiedad en el **configuración de Host Local** página () en **configuración de intercambio**) de la ficha de acuerdo unidireccional del **las propiedades del acuerdo** cuadro de diálogo. Incrementará este número para cada intercambio subsiguiente, hasta que se alcance el valor máximo.  
  
 Si el número de control de intercambio se especifica mediante las propiedades de contexto EdiOverride, se usará el valor especificado para este intercambio y no afectará el número de control de intercambio especificado en el acuerdo.  
  
> [!NOTE]
>  El número de control de grupo en EDIFACT sólo se incrementa si los **aplicar segmentos UNG** propiedad en el **sobres** está seleccionada la página de las propiedades del acuerdo EDIFACT. El valor del segundo campo (número de referencia) se incrementa; los campos de prefijo y sufijo no sufren ningún incremento. Sólo se incrementan los números de control de conjunto de transacciones si la **aplicar Id. nuevo** propiedad está seleccionada.  
  
> [!NOTE]
>  En un intercambio por lotes conservado, se puede crear un número de control de intercambio personalizado mediante el ejemplo de enriquecimiento de mensajes. Para obtener más información, consulte [Message Enrichment (ejemplo de BizTalk Server)](../core/message-enrichment-sample-biztalk-server-sample.md).  
  
 Si no se define ningún acuerdo, los números se toman de las mismas páginas del acuerdo de reserva. La canalización de envío almacena el último número de control usado y seguidamente especifica un número incrementado para el intercambio, grupo y conjunto de transacciones siguiente.  
  
> [!NOTE]
>  Si el número de control alcanza el valor máximo del intervalo especificado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] emitirá un error y suspenderá el intercambio. Puede restablecer el número de control manualmente o configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automáticamente restablecer al límite inferior, en la **configuración de Host Local** página en el **las propiedades del acuerdo** cuadro de diálogo para ambos X12 y Mensajes EDIFACT.  
> 
> [!NOTE]
>  Los números de control se guardan en la tabla dbo.EdiSequenceNumbers de la Base de datos de cuadro de mensajes de BizTalk. Debe administrar esta tabla de base de datos mediante la purga de los números de control de la tabla o el archivado de éstos, según corresponda.  
  
 En EDIFACT, los números de control consisten en valores alfanuméricos. Se admiten los formatos siguientes:  
  
- Números (por ejemplo, "1")  
  
- PrefixNumbersSuffix (por ejemplo, "WA1A")  
  
- PrefixNumbers (por ejemplo, "AA1")  
  
- NumbersSuffix (por ejemplo, "1AA")  
  
  En estos formatos, los caracteres numéricos pueden ir del "0" al "9", mientras que los caracteres de prefijo y sufijo pueden ser cualquier carácter distinto del número. Únicamente se incrementará el número hasta alcanzar el valor máximo.  
  
#### <a name="count-of-segments"></a>Recuento de segmentos  
 Para cada conjunto de transacciones de un intercambio, la canalización de envío EDI verificará el número de segmentos del conjunto de transacciones, como se indica en el elemento de datos SE01 para X12 y el elemento de datos UNT01 para EDIFACT. Si el valor del elemento de datos correspondiente no coincide con el número real, la canalización de envío actualizará el número para que refleje el número de segmentos real. Un número incorrecto no provocará el rechazo del conjunto de transacciones. La actualización del número se registrará en una advertencia en el visor de eventos. Esto no se aplica al procesamiento de los lotes conservados.  
  
## <a name="additional-steps-in-serializing-an-edi-interchange"></a>Pasos adicionales en la serialización de un intercambio EDI  
 La canalización de envío EDI también lleva a cabo los pasos siguientes durante la serialización.  
  
### <a name="serializing-the-release-indicator"></a>Serializar el indicador de versión  
 Durante la serialización de un mensaje EDIFACT, la canalización de envío EDI insertará cualquier indicador de versión necesario en el intercambio EDI. Se presupone que el XML intermedio enrutado a la canalización de envío no incluye datos con caracteres de escape. Por ejemplo, si los datos XML enrutados a la canalización de envío contienen un indicador de versión, la canalización agregará otro indicador delante del indicador existente para insertar un carácter de escape.  
  
 El indicador de versión no se incluirá en la validación EDI. La canalización de envío EDI no incluirá el indicador de versión cuando calcule las restricciones de longitud.  
  
### <a name="adding-trailing-zeroes-to-meet-implied-decimal-requirements"></a>Agregar ceros iniciales para cumplir los requisitos de cifras decimales implícitos  
 Si el ensamblador EDI detecta un número que tiene una cantidad de dígitos insuficiente después del separador de decimales, agregará ceros finales después del separador para cumplir los requisitos decimales implícitos. Por ejemplo, si el ensamblador EDI detecta la cifra "4.5" cuando el número debe tener el formato N2, el ensamblador cambiará la cifra a "4.50".  
  
### <a name="replacing-separators-in-payload-data"></a>Sustitución de separadores en datos de carga  
 Si los datos del mensaje saliente contienen caracteres que también están configurados como separadores de datos, segmentos o componentes, la canalización de envío EDI puede sustituir esos caracteres. Por ejemplo, si el mensaje contiene un valor de "prueba * data" y el separador de elementos de datos está configurado como\*', esto puede causar problemas de análisis en el sistema receptor.  
  
 La canalización de envío EDI puede configurarse para que sustituya este carácter habilitando la **reemplazar separadores de carga con** propiedad y especificar un carácter de reemplazo. Esta propiedad se encuentra en la **juego de caracteres y separadores** página en la pestaña del acuerdo unidireccional del **propiedades de acuerdo** cuadro de diálogo.  
  
### <a name="transform-hipaa-records-based-on-trigger-fields"></a>Transformación de registros HIPAA basados en campos desencadenadores  
 Si el documento de salida es un conjunto de transacciones HIPAA, el ensamblador EDI transformará cualquier registro XML único que contiene un campo desencadenador en el segmento EDI genérico coincidente (consulte [anotaciones del campo desencadenador del esquema HIPAA](../core/hipaa-schema-trigger-field-annotations.md)). Esto se consigue eliminando el sufijo del nombre de registro XML después del carácter “_”.  
  
 Por ejemplo, los dos elementos <N1_PayerIdentification_TS835W1_1000A> y <N1_PayeeIdentification_TS835W1_1000B> se convertirán en segmentos N1.  
  
## <a name="see-also"></a>Vea también  
 [Cómo envía BizTalk Server los mensajes EDI](../core/how-biztalk-server-sends-edi-messages.md)