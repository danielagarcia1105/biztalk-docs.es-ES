---
title: Procesamiento de BTAHL72XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML messages, processing
- acknowledgements, 2.XML messages
- 2.XML messages, message modes
- message modes, 2.XML message
- 2.XML messages
- validating, 2.XML messages
- 2.XML messages, acknowledgements
- 2.XML messages, validating
ms.assetid: 2f12cb44-816c-4773-9db0-9cbc3d1b1aee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77bf987966e7f52b103c205298d8bf07c1fc1a5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977293"
---
# <a name="btahl72xml-processing"></a>Procesamiento de BTAHL72XML
Los siguientes componentes en el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) procesar HL7 2.xml XML (XML) los mensajes codificados:  
  
- Las canalizaciones y las bibliotecas de core: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineCommon.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineMessageCore.dll  
  
- Bibliotecas de ensamblador y desensamblador: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72XmlAsm.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72XmlDAsm.dll  
  
- Adaptador de envío de la biblioteca de validación de confirmación (ACK) usada para el MLLP bidireccional: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL7ACKHelper.dll  
  
## <a name="xml-message-modes"></a>Modos de mensaje XML  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] admite los siguientes modos de mensaje para los mensajes XML de 2.:  
  
- Modo de publicación-suscripción (pub-sub)  
  
   El publicador se difunde a una entidad de los suscriptores, de forma declarativas o un no solicitados update. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporcionan flexibilidad de este modo, ya que puede administrar las suscripciones y las partes después de tiempo de diseño.  
  
- Modo de solicitud y respuesta  
  
   Intercambio de mensajes un interrogative o consulta en el que da como resultado una solicitud específica de una entidad específica en un mensaje de respuesta.  
  
## <a name="xml-validation"></a>Validación de XML  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporciona la siguiente validación de 2. los mensajes XML:  
  
- Lector de XML  
  
- Esquema  
  
   Habilitar o deshabilitar la validación esquemática de la entidad. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] utiliza los esquemas de HL7 2.XML directamente para este procesamiento, según lo determinado por el campo de encabezado MSH9.3 estructura de mensaje y el campo de Id. de versión MSH12 (2.3.1 2.4 y 2.5). [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] usa las capacidades de procesamiento XML estándares en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
- Segmento de Z  
  
   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] valida que ningún segmento declarado se incluye en un segmento de Z no declarado.  
  
## <a name="ack-generation"></a>Generación de confirmación  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] admite los siguientes tipos de confirmación (ACK) para los mensajes de 2. XML. Tanto el tipo de error de HL7 y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se utiliza el tipo de error (alternativo):  
  
-   Mensajes de confirmación originales de HL7  
  
-   HL7 mejorado confirmaciones  
  
     Acepte la confirmación y la aplicación acepte  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Uso de esquemas de HL7 2.XML](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)