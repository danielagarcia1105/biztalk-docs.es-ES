---
title: "Cómo fluyen los mensajes a través de BTAHL7 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message processing
- messages, message flow
- BTAHL7, message flow
ms.assetid: dd4599af-500d-4e52-85b2-8b6a28fd3f0a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40ac6defd3b0cf99d2f0e53b3173b32e09efa0c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-messages-flow-through-btahl7"></a>Cómo fluyen los mensajes a través de BTAHL7
Al instalar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) en la parte superior de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], agregará [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] componentes para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] arquitectura. La siguiente ilustración muestra el sistema combinado, que proporciona una introducción a la arquitectura de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")  
  
## <a name="message-processing-flow"></a>Flujo de procesamiento de mensajes  
 Cuando una aplicación de línea de negocio envía un mensaje a la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ocurre de sistema, lo siguiente:  
  
1.  Si el mensaje es un mensaje HL7, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe a través de un adaptador (normalmente un adaptador MLLP). Si se trata de un mensaje XML, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe a través de un adaptador (normalmente un adaptador de HTTP).  
  
    > [!NOTE]
    >  Pueden transportar mensajes XML 2.X y 2. en cualquier adaptador; Sin embargo, normalmente se transportan V2. Mensajes de X a través de un adaptador MLLP y normalmente transportan los mensajes XML de 2. a través de un adaptador de HTTP.  
  
2.  El mensaje se enruta a través de la canalización de recepción para el análisis, el Desensamblador y validación.  
  
    1.  Si el mensaje entrante es un mensaje HL7, el Desensamblador de archivos sin formato (DASM) descompone en XML. Si el mensaje entrante es un mensaje XML, el XML DASM se desensambla.  
  
    2.  Si el mensaje entrante es un mensaje por lotes, el Desensamblador desensambla en mensajes individuales. (Para obtener más información, consulte [de procesamiento por lotes mensajes](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) y [el procesamiento por lotes de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)  
  
    3.  El DASM, a continuación, valida el mensaje.  
  
    4.  Si usas un bidireccional MLLP adaptador de recepción y si se ha validado el mensaje, el Desensamblador [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación (ACK) al remitente original del mensaje a través del mismo adaptador que recibió el mensaje original. Si no es así, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación negativa (NAK). (Cómo se lleva a cabo este paso depende de la configuración de confirmación. Para obtener más información, consulte [modos de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md).)  
  
    5.  Si no se utiliza en dos sentidos MLLP, a continuación, adaptador de recepción [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera una confirmación o confirmaciones (o NAK o NAKs) y los depósitos en la base de datos de cuadro de mensajes. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]a continuación, lo enruta a las personas adecuadas en función de la configuración de puerto de envío, que puede usar cualquiera de los demás adaptadores (además de MLLP).  
  
     Para obtener una lista más completa de los procesos se realiza en el archivo sin formato y desensambladores XML, vea [Acelerador de BizTalk para HL7 componentes](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).  
  
3.  Después de que el mensaje pasa por el adaptador y la canalización de recepción, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] pasa el mensaje en la base de datos de cuadro de mensajes. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]a continuación, determina dónde enviar el mensaje a continuación. Si el mensaje forma parte de una orquestación, envía el mensaje al motor de orquestación.  
  
4.  El motor de orquestación procesa el mensaje.  
  
    1.  Si una asignación influye en el mensaje, la asignación transforma el mensaje de acuerdo con sus reglas.  
  
    2.  Si ha configurado una regla de negocio, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] , se invoca el motor de reglas de negocios (BRE) fuera de las canalizaciones, posiblemente en el motor de orquestaciones.  
  
    3.  El motor de orquestación envía el mensaje a la base de datos de cuadro de mensajes y, a continuación, continúa procesando la orquestación.  
  
5.  En función de la suscripción, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enruta el mensaje al puerto de envío.  
  
6.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]enruta el mensaje a través de la canalización de envío para el procesamiento siguiente (si corresponde): ensamblado y la validación.  
  
    1.  Si el mensaje será un HL7 mensaje 2.X, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ensambla el mensaje de XML en HL7 el ensamblador de archivo sin formato (ASM). Si el mensaje entrante aparecerá el mensaje XML, el XML DASM ensambla.  
  
    2.  Si el mensaje va a formar parte de un mensaje por lotes, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ensambla cada mensaje en el mensaje de lote. (Para obtener más información, consulte [de procesamiento por lotes mensajes](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) y [el procesamiento por lotes de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)  
  
    3.  ASM valida el mensaje (si se habilita a través de los valores de configuración de la entidad de envío).  
  
     Para obtener una lista más completa de los procesos se realiza en el archivo sin formato y los ensambladores XML, vea [Acelerador de BizTalk para HL7 componentes](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).  
  
7.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]envía el mensaje a través de un adaptador.  
  
    > [!NOTE]
    >  Pueden transportar mensajes 2.X y 2. los mensajes XML a través de un número de adaptadores; Sin embargo, la mayoría de los sistemas de transporte 2.X mensajes a través de un adaptador MLLP y 2. los mensajes XML a través de un adaptador de HTTP.  
  
## <a name="see-also"></a>Vea también  
 [¿Cómo BTAHL7 enruta los mensajes](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)