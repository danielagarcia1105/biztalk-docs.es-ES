---
title: Esquemas de HL7 2.X y 2.xml XML | Microsoft Docs
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
ms.openlocfilehash: 69dc39b3f61dbb564fc3ef128405b8721633dd2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994189"
---
# <a name="hl7-2x-and-2xml-schemas"></a>Esquemas de HL7 2.X y 2.xml XML
La organización de HL7 publica dos conjuntos de esquemas: HL7 2.X esquemas, utilizados para mensajes codificados en HL7 y esquemas de HL7 2.XML, para los mensajes codificados en XML.  

 Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] funciona de forma nativa con el HL7 2.X esquemas. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configurar archivos de esquema de carga el HL7 2.X en \< *unidad*\>: \program archivos\\Microsoft BizTalk \<versión\> Acelerador para HL7\Templates\Schemas\2.X. Como resultado, el HL7 2.X esquemas están disponibles en el Selector de esquema HL7. Ejecute el Selector de esquema HL7 en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  

 BTAHL7 funciona con los esquemas de HL7 2.XML, pero el programa de instalación de BTAHL7 no carga los esquemas de HL7 2.XML con los archivos de programa BTAHL7 y tendrá que modificar algunos de los esquemas de HL7 2.XML para que funcionen con BTAHL7. Para que estén disponibles en el Selector de esquema HL7 y realizar las modificaciones necesarias, descargar los esquemas 2.XML desde el sitio Web de la organización de HL7 y, a continuación, ejecute el **Update2XMLSchema** herramienta (para obtener más información, consulte [ Herramienta Update2XMLSchema](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)). La herramienta modificará los esquemas de HL7 2.XML según sea necesario para trabajar con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]y, a continuación, colocarlos en \< *unidad*\>: \program archivos\\Microsoft BizTalk \<versión\> Acelerador para HL7\Templates\Schemas.  

 Cada uno de estos conjuntos de esquemas incluye una serie de versiones. Versiones de esquema en vivo de HL7 2.X incluyen 2.1 a 2.5 (para obtener más información, consulte [versiones de HL7](../../adapters-and-accelerators/accelerator-hl7/hl7-versions.md)). HL72. Las versiones del esquema XML incluyen 2.3.1, 2.4 y 2.5. Versiones del esquema HL7 2.X son con versiones anteriores compatibles. Versiones de esquema XML de HL7 2.XML no son con versiones anteriores compatibles.  

> [!NOTE]
>  Dado que la versión 2.4 de 2. XML no es con versiones anteriores compatibles con 2.3.1 para 2.XML, puede producirse un error si implementa una versión 2.4 del esquema XML 2. y, a continuación, enviar una instancia de un mensaje que se ajuste a la 2.3.1 versión. Para corregir este problema, es posible que deba crear un espacio de nombres de destino diferente para tratar con 2.3.1 mensajes.  

 Cuando creas un varias partes HL7 2.X mensaje, debe establecer el tipo de la parte del cuerpo a un esquema específico. Si no es así, el serializador rechazará el mensaje.  

 En la tabla siguiente se describe los dos tipos básicos de esquemas con el que funciona BTAHL7.  


|            Tipo de esquema            |                                                                                                                                                                                                                                                                                                   Descripción                                                                                                                                                                                                                                                                                                    |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| HL7FF – ER7 codificado esquemas (2.X) | BTAHL7 proporciona HL7 esquemas 2.X derivados de la base de datos de Access de HL7, incluidos:<br /><br /> -Un conjunto de todos los esquemas específicos en función de la versión, tipo de mensaje o evento<br />: Los esquemas comunes para los segmentos, los tipos de datos, tablas, encabezados y la confirmación (ACK)<br /><br /> BTAHL7 admite las siguientes plantillas de esquema:<br /><br /> -V2.1<br />-V2.2<br />-V2.3<br />-V2.3.1<br />-V2.4<br />-V2.5<br /><br /> El programa de instalación de BTAHL7 instala V2. X esquemas en \< *unidad*\>archivos \Program\\Acelerador de Microsoft BizTalk para HL7\Templates\Schemas. |
|      HL7XML: codificación de XML 2.      |                                                                                                                                            BTAHL7 admite los siguientes esquemas:<br /><br /> -V2.3.1<br />-V2.4<br />-V2.5<br /><br /> Instalación de BTAHL7 no instala los esquemas 2.Xml. Para instalarlos y modificarlos para que funcione con el Editor de BizTalk, consulte [herramienta Update2XMLSchema](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md).                                                                                                                                            |

## <a name="common-schemas"></a>Esquemas comunes  
 BTAHL7 usa un esquema HL7 específico para un tipo de mensaje para crear y validar el cuerpo de una instancia de ese tipo de mensaje. También utiliza los esquemas comunes, además de los esquemas específicos. BTAHL7 usa esquemas de HL7 comunes para validar las confirmaciones y los encabezados del mensaje HL7. Estos archivos son MSH_25_GLO_DEF.xsd para encabezados y ACK_24_GLO_DEF para confirmaciones.  

 BTAHL7 también utiliza los esquemas comunes para validar los tipos de datos, segmentos y valores de tabla. Estos esquemas son específicos de cada versión de los estándares de HL7. Por ejemplo, los esquemas comunes para los mensajes V2.2 son datatype_22.xsd, segments_22.xsd y tablevalues_22.xsd. BTAHL7 utiliza estos esquemas para validar los tipos de datos, segmentos y valores de tabla para todos los mensajes V2.2.  

## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Procesamiento de archivos planos BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [Procesamiento de BTAHL72XML](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Uso de esquemas de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Uso de esquemas de HL7 2.XML](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)