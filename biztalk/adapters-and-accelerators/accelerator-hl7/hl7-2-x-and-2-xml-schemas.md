---
title: Esquemas de HL7 2.X y 2. XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, schema types
- HL7-encoded messages
- 2.X schemas
- schemas, HL7 organization
- BTAHL7, HL7 schemas
- HL7, 2.XML schemas
- Update2XMLSchema tool
- schemas, common schemas
- 2.X schemas, about 2.X schemas
- 2.X schemas, compatibility
- 2.XML schemas, compatibility
- messages, HL7-encoded messages
- HL7 Schema Selector
- schemas, 2.XML schemas
- 2.XML schemas
- 2.XML schemas, about 2.XML schemas
- HL7, 2.X schemas
- schemas, compatibility
- common schemas
- schemas, 2.X schemas
ms.assetid: 02532d72-1948-48d8-a8ef-6b5a814eb573
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a02c8451dc0dc07b81a824f692203809d52b588
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961906"
---
# <a name="hl7-2x-and-2xml-schemas"></a>Esquemas XML de HL7 2.X y 2.
La organización de HL7 publica dos conjuntos de esquemas: HL7 2.X esquemas, utilizados para mensajes con codificación HL7 como HL7 2. XML, utilizado para mensajes codificados en XML.  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] funciona de forma nativa con la HL7 2.X esquemas. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]la instalación de archivos de esquema de carga el HL7 2.X en \< *unidad*\>: \program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Acelerador para HL7\Templates\ Schemas\2.X. Como resultado, el HL7 2.X esquemas están disponibles en el Selector de esquema HL7. Ejecute el Selector de esquema HL7 en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
 BTAHL7 funciona con los esquemas XML de 2. HL7, pero el programa de instalación de BTAHL7 no carga los esquemas XML de 2. HL7 con los archivos de programa BTAHL7 y tiene que modificar algunos de los esquemas XML de HL7 2. para que funcione con BTAHL7. Para que estén disponibles en el Selector de esquema HL7 y realizar las modificaciones necesarias, descargue los esquemas XML de 2. desde el sitio Web de la organización de HL7 y, a continuación, ejecute el **Update2XMLSchema** herramienta (para obtener más información, consulte [ Herramienta de Update2XMLSchema](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)). La herramienta modificará los esquemas XML de 2. HL7 como sea necesario para que funcione con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]y, a continuación, colóquelos en \< *unidad*\>: \program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \< versión\> Acelerador para HL7\Templates\Schemas.  
  
 Cada uno de estos conjuntos de esquemas incluye una serie de versiones. Las versiones de esquema en vivo de HL7 2.X incluyen 2.1 a través de 2.5 (para obtener más información, consulte [HL7 versiones](../../adapters-and-accelerators/accelerator-hl7/hl7-versions.md)). HL72. Versiones de esquema XML incluyen 2.3.1, 2.4 y 2.5. Versiones de esquema HL7 2.X son con versiones anteriores compatibles. HL7 2. las versiones de esquema XML no son con versiones anteriores compatibles.  
  
> [!NOTE]
>  Dado que la versión 2.4 de 2. XML no es con versiones anteriores compatibles con 2.3.1 para 2.XML, puede producirse un error si implementa una versión 2.4 del esquema XML de 2. y, a continuación, enviar una instancia de un mensaje conforme a la 2.3.1 versión. Para corregir este problema, puede que necesite crear un espacio de nombres de destino diferente para tratar con 2.3.1 mensajes.  
  
 Cuando creas un HL7 varias partes mensaje 2.X, debe establecer el tipo de la parte del cuerpo a un esquema específico. De lo contrario, el serializador rechazará el mensaje.  
  
 La tabla siguiente describen los dos tipos básicos de esquemas con el que funciona BTAHL7.  
  
|Tipo de esquema|Description|  
|-----------------|-----------------|  
|HL7FF – ER7 codificado esquemas (2.X)|BTAHL7 proporciona HL7 esquemas 2.X derivados de la base de datos de Access de HL7, incluidos:<br /><br /> -Un conjunto de todos los esquemas específicos en función de la versión, el tipo de mensaje o el evento<br />: Los esquemas comunes de segmentos, tipos de datos, tablas, encabezados y la confirmación (ACK)<br /><br /> BTAHL7 admite las siguientes plantillas de esquema:<br /><br /> -V2.1<br />-V2.2<br />-V2.3<br />-V2.3.1<br />-V2.4<br />-VERSIÓN 2.5<br /><br /> El programa de instalación de BTAHL7 instala V2. X esquemas en \< *unidad*\>archivos \Program\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7\Templates\Schemas.|  
|HL7XML: codificación de XML de 2.|BTAHL7 admite los siguientes esquemas:<br /><br /> -V2.3.1<br />-V2.4<br />-VERSIÓN 2.5<br /><br /> El programa de instalación de BTAHL7 no instala los esquemas XML de 2. Para instalarlos y modificarlas para trabajar con el Editor de BizTalk, consulte [Update2XMLSchema herramienta](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md).|  
  
## <a name="common-schemas"></a>Esquemas comunes  
 BTAHL7 utiliza un esquema HL7 específico de un tipo de mensaje para crear y validar el cuerpo de una instancia de ese tipo de mensaje. También utiliza los esquemas comunes, además de los esquemas específicos. BTAHL7 utiliza los esquemas de HL7 comunes para validar los encabezados del mensaje HL7 y confirmaciones. Estos archivos son MSH_25_GLO_DEF.xsd para encabezados y ACK_24_GLO_DEF para confirmaciones.  
  
 BTAHL7 también utiliza los esquemas comunes para validar los tipos de datos, segmentos y los valores de tabla. Estos esquemas son específicos para cada versión de los estándares de HL7. Por ejemplo, los esquemas comunes para los mensajes V2.2 son datatype_22.xsd, segments_22.xsd y tablevalues_22.xsd. BTAHL7 utiliza estos esquemas para validar los tipos de datos, segmentos y los valores de tabla para todos los mensajes V2.2.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Procesamiento de archivo sin formato BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [Procesamiento de BTAHL72XML](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Uso de esquemas de HL7 2.XML](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)