---
title: Validación de mensajes | Documentos de Microsoft
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
ms.openlocfilehash: 1edaffcab50d6a8af508cb16c9eede39c5ddb952
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206892"
---
# <a name="validating-messages"></a>Validación de mensajes
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admite el envío de confirmaciones (ACK) para los mensajes entrantes de una aplicación o socio en forma de una recepción de XML de HL7 que puedan necesitar la conversión a un HL7 codificado el mensaje de confirmación. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Normalmente genera una confirmación después de que comprueba el mensaje entrante con la especificación de documento de entrada relevantes (formato correspondiente al socio comercial). Cuando todos los segmentos supera la validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] devuelve una confirmación que indica la aceptación a la aplicación. En caso contrario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera una notificación que indica error o error o rechazar.  
  
 El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] transmisión de confirmación informa de los errores sintácticos y esquemáticos contra el estándar HL7. Si se produce un error en la validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] coloca el documento en la cola de mensajes suspendidos y devuelve una confirmación que detalla el rechazo. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analizador realiza la validación que implica la comprobación de tipos de datos, sintaxis y la validación del esquema. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]registra los errores de esquema que se producen en el análisis en el recibo junto con los detalles de ubicación.  
  
 En configurar el tiempo, deberá crear el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artefactos necesarios para responder con una confirmación. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analizador crea la instancia de ACK XML canónica HL7. BizTalk lo convierte en el formato de la versión necesaria en una asignación de BizTalk adecuado y valida el formato de destino. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador, a continuación, convierte el mensaje en una instancia con codificación HL7.  
  
> [!NOTE]
>  Si hay un conflicto entre los delimitadores de un mensaje entrante y aquellas especificadas en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración, a continuación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generará un mensaje de confirmación que usa los mismos delimitadores del mensaje entrante y reemplaza la configuración Configuración.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [Modos de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)