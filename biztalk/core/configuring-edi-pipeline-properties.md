---
title: Configurar propiedades de canalización EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edir2.edi.pipeline.properties
ms.assetid: 1b6229b6-a8b0-4824-86bd-39021844c5a8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c810b8507a98b91c0b906131e127f189f0a4fd0f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969434"
---
# <a name="configuring-edi-pipeline-properties"></a>Configurar propiedades de canalización de EDI
Las propiedades de canalización se usan en el procesamiento de un intercambio EDI entrante o saliente, si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede determinar el acuerdo al que resuelve el intercambio entrante o saliente. En algunos casos, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa la propiedad de canalización para procesar el intercambio; en otros, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el acuerdo de reserva. Para obtener más información, consulte [cómo validar un EDI del intercambio está configurado](../core/how-validation-of-an-edi-interchange-is-configured.md).  
  
 Esta regla tiene algunas excepciones:  
  
-   Para X12, la propiedad de canalización determina el juego de caracteres que se usa en tiempo de ejecución, incluso si se ha determinado el acuerdo. El juego de caracteres que se describe en el acuerdo de caracteres solo se usa para validar los valores de propiedades del acuerdo.  
  
-   En el caso de EDIFACT, si un intercambio entrante no tiene un segmento UNA, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa los delimitadores especificados en la propiedad de canalización EfactDelimiters; [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no usa las propiedades definidas en el acuerdo en que se resuelve el mensaje ni en el acuerdo de reserva.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="edi-pipeline-properties"></a>Propiedades de canalización de EDI  
 Se pueden establecer las siguientes propiedades en las canalizaciones de EDI:  
  
|Propiedad|Utilice|Valores|Canalización - Fase|  
|--------------|---------|------------|-----------------------|  
|AllowTrailingDelimiters|Genera separadores finales en el intercambio recibido.|False (predeterminado)<br /><br /> True|EdiReceive - desensamblar<br /><br /> AS2EdiReceive-desensamblar<br /><br /> EdiSend - Assemble<br /><br /> AS2EdiSend - Assemble|  
|CharacterSet|Especifica el juego de caracteres que se va a utilizar durante la validación del tiempo de ejecución de los intercambios EDI salientes.<br /><br /> Esta propiedad se utiliza solo para el procesamiento de X12, no para EDIFACT.|UTF8 (predeterminado)<br /><br /> Básico<br /><br /> Extendido|EdiReceive - Disassemble<br /><br /> AS2EdiReceive-desensamblar<br /><br /> EdiSend - Assemble<br /><br /> AS2EdiSend - Assemble|  
|ConvertToImpliedDecimal|Para un intercambio entrante, convierta un número de EDI que se especifique con el formato Nn en un valor numérico de base 10 en el XML intermedio de BizTalk Server.<br /><br /> Esta propiedad se utiliza solo para el procesamiento de X12, no para EDIFACT.|False (predeterminado)<br /><br /> True|EdiReceive - Disassemble<br /><br /> AS2EdiReceive - Disassemble|  
|CreateXMLTagForTrailingSeparators|Crea etiquetas XML vacías para cada uno de los separadores finales (si se ha establecido **AllowTrailingDelimiters** en true).|False (predeterminado)<br /><br /> True|EdiReceive - Disassemble<br /><br /> AS2EdiReceive - Disassemble|  
|DetectMID|Habilita el desensamblador EDI para que analice varios intercambios en un único mensaje.|True (predeterminado)<br /><br /> False|EdiReceive - Disassemble<br /><br /> AS2EdiReceive - Disassemble|  
|EdiDataValidation|Habilita la validación del tipo de EDI (elementos de datos) de intercambios EDI salientes, incluida la validación de la longitud del campo, la opcionalidad y el número de repeticiones, además de la validación de elemento de datos de EDI.|True (predeterminado)<br /><br /> False|EdiReceive - Disassemble<br /><br /> AS2EdiReceive - Disassemble<br /><br /> EdiSend - Assemble<br /><br /> AS2EdiSend - Assemble|  
|EfactDelimiters|Indica los delimitadores que se van a utilizar en el procesamiento de un intercambio entrante. Se utiliza si éste no tiene un segmento UNA.<br /><br /> Los delimitadores incluyen lo siguiente:<br /><br /> -UNA1 (separador de elementos de datos de componente)<br />-UNA2 (separador de elementos de datos)<br />-UNA3 (notación Decimal)<br />-UNA4 (indicador de versión)<br />-UNA5 (separador de repetición)<br />-UNA6 (terminador de segmento) **Nota:** esta propiedad se utiliza para procesar únicamente, no para X12 EDIFACT.|0x3A, 0x2B, 0x2C, 0x3F, 0 x 20, 0 x 27 (valores predeterminados)|EdiReceive - Disassemble<br /><br /> AS2EdiReceive - Disassemble|  
IgnoreMessageEncoding|Especifica que el componente BatchMarker no establecerá EDI. Propiedad de contexto EncodingType \<X12\> o \<EDIFACT\>. Esto se aplica a canalizaciones personalizadas cuando se procesan mensajes que no sean EDI.|False (predeterminado)<br /><br /> True|EdiReceive - ResolveParty<br /><br /> AS2EdiReceive - ResolveParty|  
|MaskSecurityInformation|Enmascare la información de seguridad de autorización y de contraseña en la propiedad de contexto de un intercambio EDI entrante para prevenir la divulgación de información. Se aplica a los campos ISA1, ISA2, ISA3 e ISA4 para intercambios X12 y los campos UNB6 para intercambios EDIFACT.|True (predeterminado)<br /><br /> False|EdiReceive - Disassemble<br /><br /> AS2EdiReceive - Disassemble|  
|PreserveInterchange|Especifica que se procesará un lote recibido como una única unidad.|False (predeterminado)<br /><br /> True|EdiReceive - Disassemble<br /><br /> AS2EdiReceive - Disassemble|  
|RouteAckOn2WayPort|Devuelve una confirmación EDI por la conexión abierta de un puerto de recepción de solicitud-respuesta bidireccional.|True (predeterminado)<br /><br /> False|EdiReceive - Disassemble<br /><br /> AS2EdiReceive - Disassemble|  
|UseDotAsDecimalSeperator|Cuando se establece en True, la recepción de EDI canalización usa una notación decimal de "." en lugar de la notación decimal del documento entrante.|False (predeterminado)<br /><br /> True|EdiReceive – Disassemble<br /><br /> AS2EdiReceive - Disassemble|  
|UseIsa11AsRepetitionSeparator|Especifica que ISA11 se utiliza como un separador de repeticiones en lugar de un identificador estándar. **Nota:** esta propiedad se utiliza para X12 procesamiento solo, no para EDIFACT.|False (predeterminado)<br /><br /> True|EdiReceive - Disassemble<br /><br /> AS2EdiReceive - Disassemble|  
|XmlSchemaValidation|Activa la validación extendida (BTS-XSD) de los intercambios EDI salientes. Esto se aplica solo si el esquema se ha personalizado con elementos cuyos tipos de datos no sean de tipo EDI. Estos elementos agregados no se validarán mediante la validación de EDI, por lo que se cubrirán mediante la validación extendida.|False (predeterminado)<br /><br /> True|EdiReceive - Disassemble<br /><br /> AS2EdiReceive - Disassemble<br /><br /> EdiSend - Assemble<br /><br /> AS2EdiSend - Assemble|  
  
### <a name="to-set-a-pipeline-property"></a>Para establecer una propiedad de canalización  
  
1.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la ubicación de recepción o puerto de envío mediante la canalización que desea establecer las propiedades de y, a continuación, haga clic en **propiedades**.  
  
2.  Haga clic en el botón de elipsis (…) junto a la canalización para la que desee establecer las propiedades.  
  
3.  En el **configurar canalización** cuadro de diálogo, escriba el valor de la propiedad y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo se configura la validación de un intercambio EDI](../core/how-validation-of-an-edi-interchange-is-configured.md)