---
title: Procesamiento de archivos planos BTAHL72X | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ACKs
- 2.X messages, disassembler
- property promotion, MSH-header schemas
- disassembler, validating messages
- HL7, errors
- 2.X messages, validating headers
- acknowledgements, generating
- assembler, validating messages
- messages, multi-part messages
- property promotion, property schemas
- generating aknowledgements
- messages, 2.X messages
- schemas, MSH-header schemas
- 2.X messages, validating message bodies
- 2.X messages
- schemas, property schemas
- message modes, 2.X messages
- errors, HL7 error format
- flat files
- validating, messages
- schemas, property promotion
- headers, validating
- 2.X messages, message modes
- 2.X messages, header validation
- 2.X messages, parsing flat files
ms.assetid: c92e2f70-0bfa-4bc8-8044-4a6e62cabee3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a0220d44386eed94efbddc1a5a22fe6704a7780
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975557"
---
# <a name="btahl72x-flat-file-processing"></a>Procesamiento de archivos planos BTAHL72X
Los siguientes componentes en el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) mensajes de proceso HL7 2.X (codificada HL7):  
  
- Las canalizaciones y las bibliotecas de core: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineCommon.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineMessageCore.dll  
  
- Bibliotecas de ensamblador y desensamblador: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72fAsm.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72fDAsm.dll  
  
- Adaptador de envío de la biblioteca de validación de confirmación (ACK) usada para el MLLP bidireccional: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL7ACKHelper.dll  
  
## <a name="hl7-message-modes"></a>HL7 Modos de mensaje  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] admite los siguientes modos de mensaje para mensajes 2.X:  
  
- Modo de publicación-suscripción (pub-sub)  
  
   El publicador se difunde a una entidad de los suscriptores, de forma declarativas o un no solicitados update. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporcionan flexibilidad de este modo, ya que puede administrar las suscripciones y las partes después de tiempo de diseño.  
  
- Modo de solicitud y respuesta  
  
   Intercambio de mensajes un interrogative o consulta en el que da como resultado una solicitud específica de una entidad específica en un mensaje de respuesta.  
  
## <a name="flat-file-parsing"></a>Análisis de archivo sin formato  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analiza HL7 2.X mensajes varias partes en tres partes:  
  
-   Parte de encabezado MSH  
  
-   Parte del cuerpo  
  
-   Parte de la Z  
  
## <a name="hl7-header-validation"></a>HL7 Validación de encabezados  
 El Desensamblador HL7 y ensamblador de realizan la validación estructural y esquemática del encabezado de un mensaje 2.X, con el fin de comprobar que puede procesar el mensaje. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] bases de la validación de esquema en el esquema de encabezado común, MSH_25_GLO_DEF.  
  
 Por ejemplo, el analizador determina que los campos MSH1 y MSH2 están bien formados. MSH1 debe tener un solo carácter. MSH2 debe estar comprendido entre dos y cuatro caracteres y no puede repetir ningún carácter.  
  
## <a name="hl7-body-validation"></a>HL7 Validación de cuerpo  
 El Desensamblador HL7 y ensamblador realizan validación estructural básica del cuerpo de un mensaje 2.X y validación de esquema, si habilita esta opción.  
  
 La validación estructural básica del cuerpo, que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] siempre lleva a cabo, incluye la comprobación de los siguientes:  
  
- Hay tres caracteres en segmentos  
  
- Que es el delimitador de segmento \<CR\> o \<CR\>\<LF\> (opcional para el último segmento)  
  
- Que son adecuados los delimitadores de campo  
  
- Que no hay ningún segmento declarado (con una etiqueta de segmento de tres caracteres definido) en un segmento de Z no declarado  
  
  Validación de esquema más extensa del cuerpo de la incluye lo siguiente:  
  
- Delimitadores de campo al final  
  
   En el segmento de encabezado MSH y segmentos de cuerpo  
  
- Segmento de Z  
  
- Tipo de datos de XSD compatibles y personalizadas  
  
   XSD compatibles y los tipos de XSD no (TS (marca de tiempo), DT (fecha), TM (tiempo) y TN (número de teléfono)  
  
- Enumeraciones  
  
   Id. (las tablas definidas por HL7) e IS (tablas definidas por el usuario)  
  
- Opcionalidad  
  
   Obligatorios y opcionales  
  
- Repetición  
  
   Segmento y campo  
  
- Secuencias de escape  
  
   Codificación de caracteres, el formato y los juegos de caracteres  
  
  Habilitar o deshabilitar la validación de esquema para todos los mensajes recibidos o enviados a una entidad específica (entidad de origen para el desensamblador, la entidad de destino para el ensamblador). [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] usa el HL7 2.X esquemas directamente para este procesamiento, según lo determinado por el campo de encabezado MSH9.3 estructura de mensaje, el campo de Id. de versión MSH12 (2.3.1 2.4 y 2.5) y el espacio de nombres en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.  
  
## <a name="hl7-disassembler-processing"></a>HL7 Procesamiento de desensamblador  
 El Desensamblador HL7 analiza los mensajes entrantes de HL7 en segmentos XML para su procesamiento. A medida que analiza los mensajes, el Desensamblador realiza las siguientes tareas:  
  
-   Identificadores de secuencias de escape  
  
-   Controla las comprobaciones de las propiedades obligatorias y opcionales  
  
-   Identificadores definen segmentos e indefinidos o inesperados Z (para obtener una descripción de los segmentos de Z, consulte [personalizar mensajes a través de objetos de Z](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)).  
  
-   Omite los segmentos inesperados al final de una instancia (que se convierten en segmentos de Z no declarados)  
  
## <a name="error-reporting"></a>Informes de errores  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] notifica la mayoría de los errores en el formato de error estándar HL7, que incluyen el código de segmento, secuencia, campo y error. Sin embargo, la condición de error puede ser que no todos ellos están disponibles, por ejemplo, si no hay ningún esquema. Para controlar estos casos, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede informar sobre errores en uno alternativo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] formato de error. El segmento en un mensaje de error incluye dos partes: una para el error de HL7 y otra para la alternativa [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error.  
  
## <a name="ack-generation"></a>Generación de confirmación  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] admite los siguientes tipos de confirmación (ACK) para los mensajes 2.X. Tanto el tipo de error de HL7 y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se utiliza el tipo de error (alternativo):  
  
-   Asignación de confirmación y del mensaje original  
  
-   Mensajes de confirmación originales de HL7  
  
-   HL7 mejorado confirmaciones  
  
     Acepte la confirmación y la aplicación acepte  
  
-   Confirmación de proxy/estático  
  
     Confirmación o NAK  
  
## <a name="property-promotion"></a>Promoción de propiedades  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] admite la promoción de las siguientes propiedades 2.X:  
  
-   Esquema de propiedad  
  
-   Esquema de encabezado de MSH  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Determinación del esquema en el desensamblador HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)  
  
-   [Determinación del esquema en el ensamblador HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)