---
title: Propiedades de contexto de invalidación EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d78cd56f-1e34-4503-8ee1-93b52137097f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 182ddc6a243a578a890a47dc70faa427b4f6df88
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22243244"
---
# <a name="edi-override-context-properties"></a>Propiedades de contexto de invalidación de EDI
Las propiedades de contexto de mensaje del esquema de propiedad global EdiOverride se pueden usar para invalidar los valores de sobre EDI en tiempo de ejecución. Estas propiedades de contexto de mensaje se definen en edi-properties.xsd en el ensamblado Microsoft.BizTalk.Edi.BaseArtifacts. El espacio de nombres para las propiedades es `http://schemas.microsoft.com/BizTalk/2006/edi-properties`.  
  
 Las propiedades de contexto EDIOverride también están disponibles en una orquestación, siempre que la referencia al ensamblado Microsoft.BizTalk.Edi.BaseArtifacts se haya agregado al proyecto de la orquestación.  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|OverrideEDIHeader|boolean|Si es true, la canalización de envío de EDI intentará construir el sobre EDI con los valores de la recopilación de propiedades EdiOverride.|  
|ISA01|string|El calificador de información de autorización (X12)|  
|ISA02|string|La información de autorización (X12)|  
|ISA03|string|El calificador de información de seguridad (X12)|  
|ISA04|string|La información de seguridad (X12)|  
|ISA05|string|El calificador del remitente del intercambio (X12).|  
|ISA06|string|El identificador del remitente del intercambio (X12).|  
|ISA07|string|El calificador del receptor del intercambio (X12).|  
|ISA08|string|El identificador del receptor del intercambio (X12).|  
|ISA09|string|La fecha de intercambio (X12)<br /><br /> Este campo debe contener el valor de fecha real en lugar del formato de fecha.|  
|ISA10|string|El período de intercambio (X12)<br /><br /> Este campo debe contener el valor de tiempo real en lugar del valor de fecha.|  
|ISA11|string|El identificador de estándares de control de intercambio (X12)|  
|ISA12|string|El número de versión de control de intercambio (X12)|  
|ISA13|string|El número de control de intercambio (X12)<br /><br /> Si se invalida el número de control de intercambio, el segmento correspondiente de finalizador de intercambio (IEA) se establecerá para que coincida con el valor especificado.|  
|ISA14|string|La confirmación solicitada (X12)|  
|ISA15|string|El indicador de prueba (X12)|  
|ISA16|string|El separador de elementos de componentes (X12)|  
|GS01|string|El código de identificador funcional (X12).|  
|GS02|string|El código de remitente de la aplicación (X12)|  
|GS03|string|El código de destinatario de la aplicación (X12)|  
|GS04|string|La fecha (X12)<br /><br /> Este campo debe contener el valor de fecha real en lugar del formato de fecha.<br /><br /> Este valor debe estar en formato SSAAMMDD o AAMMDD. Se usará la fecha proporcionada aunque se proporcione en un formato diferente que el seleccionado en las propiedades de entidad.|  
|GS05|string|La hora (X12)<br /><br /> Este campo debe contener el valor de hora real en lugar del formato de hora.<br /><br /> Este valor debe estar en formato HHMM, HHMMSS o HHMMSSdd. Se usará la hora proporcionada aunque se proporcione en un formato diferente que el seleccionado en las propiedades de entidad.|  
|GS06|string|El número de control de grupo (X12)<br /><br /> Cuando se invalida el número de control de grupo, el campo correspondiente del segmento GE se establecerá para que coincida con el valor especificado.|  
|GS07|string|El código de agencia responsable (X12)|  
|GS08|string|El código de identificador de la versión, el lanzamiento o la industria (X12).|  
|ST02|string|El número de control de conjunto de transacciones (X12)<br /><br /> Si se invalida el número de control de conjunto de transacciones, el campo correspondiente del segmento de finalizador de conjunto de transacciones (SE) se establecerá para que coincida con este valor.|  
|GenerateUNA|boolean|Determina si la canalización de envío de EDI creará un segmento UNA para el documento EDIFACT saliente.<br /><br /> Si OverrideEdiHeader es true y GenerateUNA es true, se generará un segmento UNA. Si OverrideEdiHeader es true, y GenerateUNA es false, no se generará ningún segmento UNA.<br /><br /> Los valores para el segmento UNA se determinan en el orden siguiente:<br /><br /> -Las propiedades de contexto EdiOverride, si están presentes todas las propiedades UNA.<br />-Si no están presentes todas las propiedades de contexto y generación de segmento UNA está activada en las propiedades de entidad, una combinación de propiedades de contexto y propiedades de la entidad.<br />-Si no están presentes todas las propiedades de contexto y generación de segmento UNA está activada en las propiedades de entidad, una combinación de propiedades de contexto y valores UNA estándar **Nota:** este campo no tiene ningún efecto si OverrideEdiHeader es false.|  
|UNA1|string|El separador de elementos de datos de componentes (EDIFACT)|  
|UNA2|string|El separador de elementos de datos (EDIFACT)|  
|UNA3|string|La marca de decimal (EDIFACT)|  
|UNA4|string|El carácter de versión (EDIFACT)|  
|UNA5|string|El separador de repeticiones (EDIFACT)|  
|UNA6|string|El terminador de segmento (EDIFACT)|  
|UNA6Suffix|string|El sufijo de terminador de segmento (EDIFACT)|  
|UNB1_1|string|El identificador de la sintaxis (EDIFACT)|  
|UNB1_2|string|El número de versión de sintaxis (EDIFACT).|  
|UNB10|string|El identificador del contrato de comunicaciones (EDIFACT)|  
|UNB11|string|El indicador de prueba (EDIFACT)|  
|UNB2_1|string|La identificación del remitente (EDIFACT)|  
|UNB2_2|string|El calificador del código de identificación de socio (EDIFACT)|  
|UNB2_3|string|La dirección para el enrutamiento invertido (EDIFACT)|  
|UNB3_1|string|La identificación del destinatario (EDIFACT)|  
|UNB3_2|string|El calificador del código de identificación de socio (EDIFACT)|  
|UNB3_3|string|La dirección de enrutamiento (EDIFACT)|  
|UNB4_1|string|La fecha (EDIFACT)<br /><br /> Este campo debe contener el valor de fecha real en lugar del formato de fecha.|  
|UNB4_2|string|La hora (EDIFACT)<br /><br /> Este campo debe contener el valor de hora real en lugar del formato de hora.|  
|UNB5|string|La referencia de control de intercambio (EDIFACT)<br /><br /> Cuando se invalida la referencia de control de intercambio, el número de control de segmento finalizador de intercambio (UNZ) se establecerá para que coincida con el valor especificado.|  
|UNB6_1|string|La referencia o contraseña del destinatario (EDIFACT)|  
|UNB7|string|La referencia de la aplicación (EDIFACT)|  
|UNB8|string|El código de prioridad de procesamiento (EDIFACT)|  
|UNB9|string|La solicitud de confirmación (EDIFACT)|  
|GenerateUNG|boolean|Determina si la canalización de envío de EDI creará un segmento UNG para el documento EDIFACT saliente.<br /><br /> Si OverrideEdiHeader es true y GenerateUNG es true, se generará un segmento UNG. Si OverrideEdiHeader es true, y GenerateUNG es false, no se generará ningún segmento UNG.<br /><br /> Los valores para el segmento UNG se determinan en el orden siguiente:<br /><br /> -Las propiedades de contexto EdiOverride, si están presentes todas las propiedades UNG.<br />-Si no están presentes todas las propiedades de contexto y generación de segmento UNG está activada en las propiedades de entidad, una combinación de propiedades de contexto y propiedades de la entidad.<br />-Si no están presentes todas las propiedades de contexto y generación de segmento UNG está activada en las propiedades de entidad, una combinación de propiedades de contexto y valores UNA estándar **Nota:** este campo no tiene ningún efecto si OverrideEdiHeader es false.|  
|UNG1|string|La identificación de grupo de mensajes (EDIFACT).|  
|UNG2_1|string|La identificación del remitente de la aplicación (EDIFACT)|  
|UNG2_2|string|El calificador del código de identificación (EDIFACT)|  
|UNG3_1|string|La identificación del destinatario de la aplicación (EDIFACT)|  
|UNG3_2|string|El calificador del código de identificación (EDIFACT)|  
|UNG4_1|string|La fecha de preparación (EDIFACT)<br /><br /> Este campo debe contener el valor de fecha real en lugar del formato de fecha.|  
|UNG4_2|string|La hora de preparación (EDIFACT)<br /><br /> Este campo debe contener el valor de hora real en lugar del formato de hora.|  
|UNG5|string|El número de referencia de grupo (EDIFACT)<br /><br /> Si se invalida el número de referencia de grupo, el campo correspondiente del segmento finalizador de grupo (UNE) se establecerá para que coincida con el valor especificado.|  
|UNG6|string|La agencia de control codificada (EDIFACT)|  
|UNG7_1|string|El número de versión del mensaje (EDIFACT).|  
|UNG7_2|string|El número de versión de mensaje (EDIFACT).|  
|UNG7_3|string|El código asignado a la asociación (EDIFACT)|  
|UNG8|string|La contraseña de la aplicación (EDIFACT)|  
|UNH1|string|El número de referencia del mensaje (EDIFACT).<br /><br /> Cuando se invalida el número de referencia de mensaje, el campo correspondiente del segmento finalizador de mensaje (UNT) se establecerá para que coincida con este valor.|  
  
## <a name="edioverride-context-property-usage"></a>Uso de la propiedad de contexto EDIOverride  
 Si el **OverrideEdiHeader** propiedad de contexto es true, los valores especificados en las propiedades de contexto EDIOverride se usará para crear el sobre EDI para el mensaje saliente. Si no se especifica ningún valor para una propiedad de contexto EDIOverride, se usará la propiedad Entidad o Global correspondiente.  
  
 Los valores especificados para las propiedades de contexto EDIOverride deben ser válidos según los estándares X12 o EDIFACT y cualquier extensión de esquema de servicio.  
  
-   Los campos deben contener valores válidos para este tipo de campo, incluidas las extensiones del esquema de servicio.  
  
-   Los números de control deben ser de tipo válido, pero no es necesario que estén en secuencia con los valores de entidad existentes.  
  
-   Los campos de fecha y hora deben contener valores de fecha y hora, y ser válidos según el estándar EDI correspondiente aunque el formato de valor no coincida con el formato definido en los valores de entidad.  
  
 Algunas propiedades de contexto EDIOverride únicamente se admiten cuando el mensaje que se envía mediante la canalización de envío EDI es una única transacción o un lote. En la siguiente tabla se enumeran las propiedades de contexto admitidas para cada tipo de mensaje:  
  
|Transacciones EDI que se envían|Propiedades de contexto EDIOverride admitidas|  
|--------------------------------|----------------------------------------------|  
|Conjunto único de transacciones|-Todos los ISA<br />-Todos los GS<br />-ST02<br />-GenerateUNA<br />-Todos los una<br />-Todos los UNB<br />-GenerateUNG<br />-Todos los Ung<br />-UNH1|  
|El conjunto de transacciones de lotes que publica la orquestación de procesamiento por lotes o la transacción Batch-in-Batch-Out que publica la canalización de recepción de EDI.|-Todos los ISA<br />-GS04<br />-GS05<br />-GenerateUNA<br />-Todos los una<br />-Todos los UNB<br />-GenerateUNG<br />: UNG4.1<br />: UNG4.2|  
  
 Las propiedades de contexto EDIOverride también se pueden aplicar a mensajes que se procesarán por lotes. Sin embargo, la orquestación de procesamiento por lotes únicamente admite las propiedades de contexto EDIOverride ST01 y UNH1.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md)