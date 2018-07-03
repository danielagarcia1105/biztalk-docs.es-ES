---
title: Segmento de confirmación del mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, acknowledgements
- acknowledgements, segments
ms.assetid: 6f2b9f6f-a328-4a0f-9e7d-edba32cc045a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f771968e6d7c7f58ccd8d3e68b43aac0eb64e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968501"
---
# <a name="message-acknowledgment-segment"></a>Segmento de confirmación del mensaje
El segmento de confirmación del mensaje (MSA) de un mensaje de confirmación (ACK) identifica qué tipo de confirmación, el sistema está enviando e indica qué mensaje está confirmando la confirmación. Consta de dos segmentos de necesarias: identificador de control de un código de confirmación y un mensaje  

## <a name="acknowledgment-code-msa1"></a>Código de confirmación: MSA1  
 En la tabla siguiente se enumera los valores de campo MSA1 disponibles que indica el resultado de la recepción del mensaje.  

|Valor|Significado|Descripción|  
|-----------|-------------|-----------------|  
|AA|Confirmación de la aplicación|El sistema ha recibido el mensaje y se procesan sin problemas.|  
|AE|Error de la aplicación|Se ha producido un problema de procesamiento relacionado con el mensaje o su estructura en la aplicación receptora. El sistema de envío debe diagnosticar y corregir el problema antes de intentar volver a enviar el mensaje.|  
|CUENTAS POR COBRAR|Rechazo de la aplicación|Se ha producido un problema en la ubicación de recepción relacionadas con el valor en MSH9 (tipo de mensaje), MSH11 (Id. de procesamiento), o MSH12 (Id. de versión), en cuyo caso debe diagnosticar y corregir el problema antes de volver a enviar el mensaje; el sistema de envío o bien se produjo un problema en el sistema de recepción que estaba relacionado con el mensaje o su estructura, en el que caso el sistema de envío debe reenviar el mensaje después de un período adecuado, sin cambios al mensaje.|  

## <a name="message-control-id-msa2"></a>Id. de Control de mensajes (MSA2)  
 El campo MSA2 identifica el mensaje que se está confirmando la confirmación. Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) genera el valor en MSA2 según el modo de confirmación. Este valor permite que las aplicaciones emisoras y receptoras mantener el mensaje y sincronizada de la confirmación. En la tabla siguiente se enumera los valores disponibles para el campo MSA2.  


|            Modo de confirmación            |                                                           Valor de MSA2                                                            |
|-------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|               Modo original               |                  Un valor del valor de la MSH10 transpuesto (Id. de control de mensajes) campo del mensaje original                   |
|   Modo mejorado: Confirmación de confirmación    |                  Un valor del valor de la MSH10 transpuesto (Id. de control de mensajes) campo del mensaje original                   |
| Modo mejorado: Confirmación de la aplicación | Un GUID generado por [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] para la confirmación |

## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Tipos de esquema de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [Configurar un puerto de envío para recibir confirmaciones](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [Condiciones de error de confirmación](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)