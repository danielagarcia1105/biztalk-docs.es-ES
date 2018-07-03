---
title: Validación de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, acknowledgements
- messages, acknowledgements
- acknowledgements, validating
- validating, messages
- acknowledgements, messages
- messages, validating
ms.assetid: 7dba0f40-5e19-4598-82cb-22c71e9536c6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35894722d2c95f197a1fe4072c2229cf96fea64f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010061"
---
# <a name="validating-messages"></a>Validación de mensajes
Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admite el envío de confirmaciones (ACK) para los mensajes entrantes desde una aplicación o socio en forma de una recepción HL7 XML que podría necesitar la conversión a un HL7 codificado el mensaje de confirmación. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Normalmente genera una confirmación después de que comprueba el mensaje entrante con la especificación de documento de entrada correspondiente (formato socio comercial). Cuando todos los segmentos pasan la validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] devuelve una confirmación que indica la aceptación a la aplicación. En caso contrario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera una confirmación que indica error o un error o rechazar.  
  
 El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] transmisión ACK notifica errores sintácticos y esquemáticos contra el estándar HL7. Si se produce un error en la validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] coloca el documento en la cola de mensajes suspendidos y devuelve una confirmación que detalla el rechazo. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analizador realiza la validación que implica la comprobación de tipos de datos, la sintaxis y la validación del esquema. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] registra los errores de esquema que se producen en el análisis en la recepción, junto con los detalles de ubicación.  
  
 Al configurar la hora, deberá crear el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artefactos necesarios para responder con una confirmación. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analizador crea la instancia de ACK XML canónica HL7. BizTalk lo convierte en el formato de versión necesaria de un mapa de BizTalk adecuado y valida el formato de destino. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador, a continuación, convierte el mensaje en una instancia de HL7 codificado.  
  
> [!NOTE]
>  Si hay un conflicto entre los delimitadores de un mensaje entrante y aquellas especificadas en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración y, a continuación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generará un mensaje de confirmación que usa los mismos delimitadores del mensaje entrante e invalida la configuración Configuración.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [Modos de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)