---
title: Desencadenar eventos y mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- health care organizations, HL7 messages
- trigger events
- messages, trigger events
- messages, about messages
ms.assetid: e93b397c-8cbe-4589-aa88-e474d7722174
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 188d7f1e09ae3f96c953c6a83bbad42ccdce3643
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="trigger-events-and-messages"></a>Desencadenar eventos y mensajes
En un sistema de atención sanitaria digital, las aplicaciones crear mensajes HL7 debido a un evento del mundo real, como la inclusión de un pedido de laboratorio o fármaco. La organización de HL7 ha escrito el estándar HL7 basado en la suposición de que un evento en el mundo real de atención médica crea la necesidad de los datos fluyan entre aplicaciones, incluso cuando estas aplicaciones incluyen sistemas heterogéneos. El estándar HL7 llama a este suceso reales un *eventos de desencadenador*. Un sistema automatizado sistemáticamente debe reconocer el evento de desencadenador.  
  
 Para expandir este concepto, considere el escenario siguiente. A la llegada en un hospital, un paciente se registra en un hospital mediante una aplicación de software de administración de pacientes. En confirmar los registros de los pacientes, la aplicación debe informar a otras aplicaciones hospital (por ejemplo, cuentas, laboratorios etc.) acerca del registro del paciente. Compartir esta información entre aplicaciones es necesario para que las entidades que utilizan estas aplicaciones pueden proporcionar al paciente con los servicios necesarios. El acto de registrar a un paciente es un tipo de evento de desencadenador. Normalmente, una aplicación Web crea este evento de desencadenador mediante la creación de un mensaje de HL7 que contiene los datos de registro del paciente.  
  
 Eventos de desencadenador siempre como resultado la creación de uno o varios mensajes que desencadenan una acción en la aplicación que procesa el mensaje. Eventos de desencadenador son relevantes en los escenarios de implementación donde ha incrustado personal de TI [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) dentro de la aplicación de línea de negocio de hospital. Incluso en estos escenarios de implementación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no es necesario tener en cuenta el evento de desencadenador, sólo los mensajes que genera el evento de desencadenador.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Uso de esquemas XML de HL7 2.](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [Mensajería HL7](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)