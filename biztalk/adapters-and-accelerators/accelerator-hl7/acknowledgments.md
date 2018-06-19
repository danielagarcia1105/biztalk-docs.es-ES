---
title: Confirmaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, acknowledgements
- parties, acknowledgements
- acknowledgements, about acknowledgements
- acknowledgements, messages
- acknowledgements, parties
ms.assetid: d25352a4-bae9-4de9-a504-2339bea25c4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c519ec4649ee1fbcfbc51edb7e3e8fe6ba6b5871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204348"
---
# <a name="acknowledgments"></a>Confirmaciones
Configurar confirmaciones HL7 en el nivel entidad con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) el Explorador de configuración. Confirmaciones que se aplican a las partes que están enviando mensajes HL7 a través de una ubicación de recepción (posiblemente el adaptador MLLP) y el HL7 2.X canalización de recepción. Cuando un mensaje completa el análisis y la validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede crear un mensaje de confirmación que contiene el resultado (éxito o error) del proceso de validación. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]puede devolver mensajes de confirmación de una de dos maneras. Si la entidad remitente original enviado el mensaje original a través de dos sentidos recibe la configuración del puerto, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] devuelve el mensaje de confirmación a través de esa ubicación de puerto original. Si el puerto envío original enviado el mensaje original a través de un sentido puerto de recepción [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía el mensaje de confirmación en la base de datos de cuadro de mensajes y los enruta mediante el modelo de suscripción.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] realiza la asociación de la entidad para recibir el mensaje procesar automáticamente según el valor del campo de aplicación remitente del mensaje HL7 (MSH 3.1).  
  
## <a name="see-also"></a>Vea también  
 [Flujo de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-flow.md)