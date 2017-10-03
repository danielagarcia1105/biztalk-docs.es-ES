---
title: "Segmento de confirmación del mensaje | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- segments, acknowledgements
- acknowledgements, segments
ms.assetid: 6f2b9f6f-a328-4a0f-9e7d-edba32cc045a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9547b6d8ddf3013facd94930b5d91ec42db0e5d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-acknowledgment-segment"></a>Segmento de confirmación del mensaje
El segmento de mensaje de confirmación (MSA) de un mensaje de confirmación (ACK) identifica qué tipo de confirmación, el sistema está enviando e indica qué mensajes reconoce la confirmación. Consta de dos segmentos requeridos: un código de confirmación y un mensaje de control de Id.  
  
## <a name="acknowledgment-code-msa1"></a>Código de confirmación: MSA1  
 En la tabla siguiente se enumera los valores de campo MSA1 disponibles que indica el resultado de la recepción de mensajes.  
  
|Valor|Significado|Description|  
|-----------|-------------|-----------------|  
|AA|Confirmación de la aplicación|El sistema recibió el mensaje y procesa sin problema.|  
|AE|Error de la aplicación|Se produjo un problema de procesamiento relacionado con el mensaje o su estructura a la aplicación receptora. El sistema de envío debe diagnosticar y corregir el problema antes de intentar reenviar el mensaje.|  
|AR|Rechazo de aplicación|Se ha producido un problema en la ubicación de recepción relacionadas con el valor en MSH9 (tipo de mensaje), MSH11 (procesar el Id.,) o MSH12 (Id. de versión), en cuyo caso el sistema de envío debe diagnosticar y corregir el problema antes de volver a enviar el mensaje; o se produjo un problema en el sistema receptor que estaba relacionado con el mensaje o su estructura, en el que el sistema de envío de caso debe reenviar el mensaje después de un período adecuado, sin cambios en el mensaje.|  
  
## <a name="message-control-id-msa2"></a>Id. de Control de mensajes (MSA2)  
 El campo MSA2 identifica el mensaje que reconoce la confirmación. [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) genera el valor de MSA2 en función del modo de confirmación. Este valor permite que las aplicaciones emisoras y receptoras mantener el mensaje y la confirmación sincronizada. En la tabla siguiente se enumera los valores disponibles para el campo MSA2.  
  
|Modo de confirmación|Valor de MSA2|  
|-------------------------|-------------------|  
|Modo original|Un valor transpuesto del valor en el MSH10 (Id. de control de mensajes) campo del mensaje original|  
|Modo mejorado: Confirmación de confirmación|Un valor transpuesto del valor en el MSH10 (Id. de control de mensajes) campo del mensaje original|  
|Modo mejorado: Confirmación de la aplicación|Un GUID generado por [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] para la confirmación|  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Tipos de esquema de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [Cómo configurar un puerto de envío para recibir mensajes de confirmación](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [Condiciones de Error de confirmación](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)