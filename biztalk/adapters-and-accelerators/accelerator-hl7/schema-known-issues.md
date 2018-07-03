---
title: Problemas conocidos de esquemas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, schemas
- schemas, known issues
ms.assetid: 17651462-baa9-448a-954c-c09e70640f17
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ced040dab48f455e5af5a7731a319173fa27ca5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983069"
---
# <a name="schema-known-issues"></a>Problemas conocidos de esquemas
Esta sección contiene información útil que puede ayudarle a evitar errores de esquema.  
  
## <a name="mcf21glodefxsd-schema"></a>Esquema MCF_21_GLO_DEF.xsd  
 En la carpeta templates\schemas\2.1, esquema MCF_21_GLO_DEF.xsd no es una parte del proyecto Common231.  
  
## <a name="miscellaneous-errors-can-result-from-undeployed-schemas"></a>Varios errores pueden deberse a partir de esquemas no implementados  
 Si no se puede identificar un error en analizar o serializar, asegúrese de que ha implementado esquemas de propiedades y los esquemas comunes (MSH/ACK). Esquemas de propiedades no implementadas y los esquemas comunes pueden provocar errores varios.  
  
## <a name="if-the-starter-project-is-installed-but-the-hl7-2x-schemas-are-not-installed-running-the-schema-wizard-generates-an-error"></a>Si está instalado el proyecto de inicio, pero el HL7 2.X esquemas no están instalados, ejecute el Asistente para esquemas genera un error  
 Si ejecuta una instalación personalizada de Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) en que se instala el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proyecto de inicio, pero no no instalar la HL7 2.X esquemas y, a continuación, intente ejecutar el Asistente para esquemas, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generará una error. La solución para este problema es volver a ejecutar el proceso de instalación personalizada para instalar el HL7 2.X esquemas.  
  
## <a name="msh91-enumeration-list-needs-to-be-updated"></a>Lista de enumeración MSH9.1 debe actualizarse  
 El esquema MSH_25_GLO_DEF instalado por [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] tras la instalación no contiene las listas de enumeración completa para MSH9.1 (MessageType) y MSH9.2 (EventTrigger), la medida indicada en el HL72. X estándar. La tabla siguiente muestra el mensaje desencadenador y el tipo de valores de evento que tendrá que agregar a su tabla asociada, si desea usar un esquema cuyo tipo de mensaje contiene el valor. Por ejemplo, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no procesará un QBP ^ Z99 mensaje hasta que agregue "QBP" a la enumeración para Table76 en MSH_25_GLO_DEF y no procesará un QBP ^ Z99 mensaje hasta que agregue "Z99" a la enumeración para Table3 en MSH_25_GLO_DEF.  
  
 Para agregar un valor a la enumeración MSH9.1 o MSH9.2, consulte el procedimiento "para agregar un valor de enumeración a un esquema de encabezado del mensaje" en [extender las enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).  
  
|Campo o tabla|Valor que se agregarán a la enumeración|  
|------------------|--------------------------------------|  
|MessageType/Table76|DESCARTAR, RDO, RRO|  
|TriggerEvent/Table3|K11, K13, K15, MFA, O22, P11, RESPUESTA A P13, RESPUESTA A P15, P26, Q27, Q28, P29, R0R, Z73, Z74, Z75, Z76, Z77, Z78, Z79, Z80, Z81, Z82, Z83, Z84, Z85, Z86, Z87, Z88, Z89, Z90, Z91, Z92, Z93, Z94, Z95, Z96, Z97, Z98, Z99|  
|MessageStructure/Table354|ARD_A19, ORL_O22|  
  
## <a name="btahl7-does-not-support-schemas-with-an-ambiguous-structure"></a>BTAHL7 no admite esquemas con una estructura ambigua  
 El motor de BTAHL7 no puede procesar instancias de mensaje que se ajuste a los esquemas de HL7 que tienen una estructura ambigua. Una estructura de esquema ambigua es aquella que no está completamente definido por el estándar HL7. Estos esquemas incluyen para los tipos de mensaje CSU, OMD, ORD y SUR.  
  
## <a name="btahl7-will-return-a-segment-sequence-error-for-some-messages"></a>BTAHL7 devolverá un error de secuencia de segmento para algunos mensajes  
 BTAHL7 no puede procesar los mensajes sean conformes a los esquemas que se enumeran a continuación. Análisis del cuerpo de estos mensajes se producirá un error, lo que produce el siguiente error: "Error en la secuencia (segmento no válido encontrado después de este segmento) de segmento." Los identificadores de segmento afectado en los mensajes se enumeran a continuación. Los números de secuencia afectados todos estos errores es "2".  
  
|Versión|Tipo de mensaje|Evento de desencadenador|Identificador de segmento|  
|-------------|------------------|-------------------|----------------|  
|V2.3|CSU|C09|ORC_CommonOrderSegment|  
|V2.3|CSU|C10|ORC_CommonOrderSegment|  
|V2.3|CSU|C11|ORC_CommonOrderSegment|  
|V2.3|CSU|C12|ORC_CommonOrderSegment|  
|V2.3|SUR|P09|PSH_ProductSummaryHeader|  
|V2.3.1|CSU|C09|ORC_CommonOrderSegment|  
|V2.3.1|CSU|C10|ORC_CommonOrderSegment|  
|V2.3.1|CSU|C11|ORC_CommonOrderSegment|  
|V2.3.1|CSU|C12|ORC_CommonOrderSegment|  
|V2.3.1|SUR|P09|PSH_ProductSummaryHeader<br />Segment|  
|V2.4|CSU|C09|ORC_CommonOrder|  
|V2.4|CSU|C10|ORC_CommonOrder|  
|V2.4|CSU|C11|ORC_CommonOrder|  
|V2.4|CSU|C12|ORC_CommonOrder|  
|V2.4|OMD|O03|ORC_CommonOrder|  
|V2.4|ORD|O04|ORC_CommonOrder|  
|V2.4|SUR|P09|PSH_ProductSummaryHeader|  
|VERSIÓN 2.5|CSU|C09|ORC_CommonOrder|  
|VERSIÓN 2.5|CSU|C10|ORC_CommonOrder|  
|VERSIÓN 2.5|CSU|C11|ORC_CommonOrder|  
|VERSIÓN 2.5|CSU|C12|ORC_CommonOrder|  
|VERSIÓN 2.5|OMD|O03|ORC_CommonOrder|  
|VERSIÓN 2.5|ORD|O04|ORC_CommonOrder|  
|VERSIÓN 2.5|SUR|P09|PSH_ProductSummaryHeader"|  
|VERSIÓN 2.5|RDE|025|PSH_ProductSummaryHeader"|  
|VERSIÓN 2.5|OUL|R24|PSH_ProductSummaryHeader"|  
|VERSIÓN 2.5|OML|035|PSH_ProductSummaryHeader"|  
|VERSIÓN 2.5|ORL|034|PSH_ProductSummaryHeader"|  
  
> [!NOTE]
>  La lista anterior para la versión 2.5 no es exhaustiva y puede incluir tipos de mensajes adicionales que se producirá el Error"segmento secuencia".  
  
## <a name="btahl7-does-not-support-some-v231-schemas"></a>BTAHL7 no admite algunos esquemas v2.3.1  
 El programa de instalación de BTAHL7 no instala los siguientes esquemas v2.3.1:  
  
-   OMD_O01_231_GLO_DEF  
  
-   OMN_O01_231_GLO_DEF  
  
-   OMS_O01_231_GLO_DEF  
  
-   ORD_O02_231_GLO_DEF  
  
-   ORN_O02_231_GLO_DEF  
  
-   ORS_O02_231_GLO_DEF  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)