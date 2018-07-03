---
title: Desencadenar eventos y mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- health care organizations, HL7 messages
- trigger events
- messages, trigger events
- messages, about messages
ms.assetid: e93b397c-8cbe-4589-aa88-e474d7722174
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 309d420d97cdc22c4f0eaca30bb6426e295cbe33
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971613"
---
# <a name="trigger-events-and-messages"></a>Desencadenar eventos y mensajes
En un sistema de atención médica digital, las aplicaciones crean mensajes de HL7 debido a un evento reales, como la inclusión de un pedido de laboratorio o drogas. La organización de HL7 ha escrito el estándar HL7 según la suposición de que un evento en el mundo real de atención médica crea la necesidad de los datos fluyan entre aplicaciones, incluso cuando estas aplicaciones incluyen sistemas heterogéneos. El estándar HL7 llama a este evento reales un *eventos de desencadenador*. Un sistema automatizado sistemáticamente debe reconocer el evento de desencadenador.  
  
 Para expandir este concepto, considere el escenario siguiente. A la llegada en un hospital, un paciente se registra en un hospital mediante una aplicación de software de administración de pacientes. En confirmar los registros de pacientes, la aplicación debe informar a otras aplicaciones de hospital (por ejemplo, Contabilidad, laboratorios y así sucesivamente) sobre el registro del paciente. Compartir esta información entre aplicaciones es necesario para que las entidades que utilizan estas aplicaciones pueden proporcionar al paciente con los servicios necesarios. El acto de registrar a un paciente es un tipo de evento de desencadenador. Una aplicación Web crea normalmente este evento desencadenador mediante la creación de un mensaje de HL7 que contiene los datos de registro del paciente.  
  
 Desencadenar eventos siempre como resultado la creación de uno o más mensajes que desencadenan una acción en la aplicación que procesa el mensaje. Eventos de desencadenador son pertinentes en escenarios de implementación donde el personal de TI ha incrustado el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) dentro de la aplicación de línea de negocio del hospital. Incluso en estos escenarios de implementación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no necesita tener en cuenta el efecto desencadenante, sólo los mensajes que genera el evento de desencadenador.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Uso de esquemas de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Uso de esquemas de HL7 2.Xml](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [Mensajería de HL7](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)