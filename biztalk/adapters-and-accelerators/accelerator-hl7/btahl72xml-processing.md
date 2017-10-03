---
title: Procesamiento de BTAHL72XML | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e86697884c28d71fa9fb91c8b276293f7d36a588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="btahl72xml-processing"></a>Procesamiento de BTAHL72XML
Los componentes siguientes en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) procesar mensajes (codificación XML) de HL7 2. XML:  
  
-   Las canalizaciones y las bibliotecas principales: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineCommon.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineMessageCore.dll  
  
-   Bibliotecas de ensamblador y desensamblador: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72XmlAsm.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72XmlDAsm.dll  
  
-   Adaptador de envío de la biblioteca de validación de confirmación (ACK) utilizada para la MLLP bidireccional: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL7ACKHelper.dll  
  
## <a name="xml-message-modes"></a>Modos de mensaje de XML  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]admite los siguientes modos de mensaje para los mensajes de 2. XML:  
  
-   Modo de publicador y el suscriptor (publicación-suscripción)  
  
     El publicador se difunde a una entidad de suscriptores, como declarativas o un no solicitados update. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporcionar flexibilidad de este modo, ya que puede administrar las suscripciones y las entidades después de tiempo de diseño.  
  
-   Modo de solicitud-respuesta  
  
     Intercambio de mensajes un interrogative o consulta en la que da como resultado una solicitud específica de una entidad específica en un mensaje de respuesta.  
  
## <a name="xml-validation"></a>Validación de XML  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]proporciona las siguientes de validación de 2. los mensajes XML:  
  
-   Lector XML  
  
-   Representación esquemática  
  
     Habilitar o deshabilitar la validación de esquema por la entidad. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]utiliza los esquemas XML de 2. HL7 directamente para este procesamiento, según lo determinado por el campo de encabezado de la estructura de los mensajes MSH9.3 y el campo de Id. de versión MSH12 (2.3.1, 2.4 o 2.5). [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]usa las capacidades de procesamiento de XML estándares en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
-   Segmento de Z  
  
     [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]valida que ningún segmento declarado se incluye en un segmento de Z no declarado.  
  
## <a name="ack-generation"></a>Generación de confirmación  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]admite los siguientes tipos de confirmaciones (ACK) para los mensajes de 2. XML. El tipo de error de HL7 y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se utiliza el tipo de error (alternativo):  
  
-   Confirmaciones originales HL7  
  
-   HL7 mejorado confirmaciones  
  
     Acepte la confirmación y aplicación acepte  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Uso de esquemas XML de HL7 2.](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)