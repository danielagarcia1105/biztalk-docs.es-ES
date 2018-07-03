---
title: Cómo fluyen los mensajes a través de BTAHL7 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message processing
- messages, message flow
- BTAHL7, message flow
ms.assetid: dd4599af-500d-4e52-85b2-8b6a28fd3f0a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6bddae0d685d63772b5fd76f70ba19e0628cab5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000109"
---
# <a name="how-messages-flow-through-btahl7"></a>Cómo fluyen los mensajes a través de BTAHL7
Al instalar el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) sobre MicrosoftBizTalk Server, agrega [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] componentes para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] arquitectura. La siguiente ilustración muestra el sistema combinado, que proporciona una introducción a la arquitectura de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")  
  
## <a name="message-processing-flow"></a>Flujo de procesamiento de mensajes  
 Cuando una aplicación de línea de negocio envía un mensaje a la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system, ocurre lo siguiente:  
  
1. Si el mensaje es un mensaje de HL7 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] lo recibe a través de un adaptador (normalmente un adaptador MLLP). Si es un mensaje XML, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] lo recibe a través de un adaptador (normalmente un adaptador de HTTP).  
  
   > [!NOTE]
   >  Pueden transportar 2.X y 2.XML mensajes XML a través de cualquier adaptador; Sin embargo, normalmente haría transporte V2. X mensajes a través de un adaptador MLLP y normalmente harían transporte 2. los mensajes XML a través de un adaptador de HTTP.  
  
2. El mensaje se enruta a través de la canalización de recepción para el análisis mediante el Desensamblador y la validación.  
  
   1. Si el mensaje entrante es un mensaje de HL7, el Desensamblador de archivos (DASM) descompone en XML. Si el mensaje entrante es un mensaje XML, el DASM XML se desensambla.  
  
   2. Si el mensaje entrante es un mensaje por lotes, el Desensamblador desensambla en mensajes individuales. (Para obtener más información, consulte [mensaje de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) y [mensaje de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)  
  
   3. El DASM, a continuación, valida el mensaje.  
  
   4. Si usas un bidireccional adaptador de recepción de MLLP y si el Desensamblador ha validado el mensaje, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación (ACK) al remitente original del mensaje a través del mismo adaptador que recibió el mensaje original. Si no es así, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación negativa (NAK). (¿Cómo se realiza este paso depende de la configuración de confirmación. Para obtener más información, consulte [modos de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md).)  
  
   5. Si no usa un bidireccional, adaptador de recepción de MLLP, a continuación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera una confirmación o confirmaciones (o NAK o NAKs) y se deposita en la base de datos de cuadro de mensajes. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] a continuación, enruta a las personas adecuadas en función de la configuración de puerto de envío, que podría utilizarse cualquiera de los demás adaptadores (además de MLLP).  
  
      Para obtener una lista más completa de los procesos se realiza en el archivo sin formato y desensambladores XML, vea [Acelerador de BizTalk para HL7 componentes](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).  
  
3. Después de que el mensaje pasa por el adaptador y la canalización de recepción, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] pasa el mensaje en la base de datos de cuadro de mensajes. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] a continuación, determina dónde enviar el mensaje a continuación. Si el mensaje forma parte de una orquestación, envía el mensaje al motor de orquestación.  
  
4. El motor de orquestación procesa el mensaje.  
  
   1. Si un mapa afecta el mensaje, la asignación transforma el mensaje según sus reglas.  
  
   2. Si ha configurado una regla de negocios, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] invoca el motor de reglas de negocios (BRE) fuera de las canalizaciones, potencialmente en el motor de orquestaciones.  
  
   3. El motor de orquestación envía el mensaje a la base de datos de cuadro de mensajes y, a continuación, continúa procesando la orquestación.  
  
5. En función de la suscripción, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enruta el mensaje al puerto de envío.  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] enruta el mensaje a través de la canalización de envío para el procesamiento siguiente (si corresponde): ensamblado y la validación.  
  
   1. Si el mensaje será un HL7 2.X mensaje, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ensambla el mensaje de XML en HL7 el ensamblador de archivo sin formato (ASM). Si el mensaje entrante será un mensaje XML, el DASM XML ensambla.  
  
   2. Si el mensaje va a formar parte de un mensaje por lotes, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ensambla cada mensaje en el mensaje de lote. (Para obtener más información, consulte [mensaje de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) y [mensaje de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)  
  
   3. ASM valida el mensaje (si se habilita a través de los valores de configuración de la entidad de envío).  
  
      Para obtener una lista más completa de los procesos se realiza en el archivo sin formato y los ensambladores XML, vea [Acelerador de BizTalk para HL7 componentes](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).  
  
7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía el mensaje a través de un adaptador.  
  
   > [!NOTE]
   >  Pueden transportar mensajes 2.X y 2. los mensajes XML a través de un número de adaptadores; Sin embargo, la mayoría de los sistemas transporte 2.X mensajes a través de un adaptador MLLP y 2. los mensajes XML a través de un adaptador de HTTP.  
  
## <a name="see-also"></a>Vea también  
 [Cómo se enrutan los mensajes en BTAHL7](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)