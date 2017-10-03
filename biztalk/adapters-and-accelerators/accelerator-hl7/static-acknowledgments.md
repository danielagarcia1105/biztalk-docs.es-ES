---
title: "Confirmaciones estáticas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- static acknowledgements
- acknowledgements, static acknowledgements
ms.assetid: 1cdd01fc-1dae-4851-917f-4f13a0f9595a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8081dc0f3c37c40cb1103567ae06f80037a12730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="static-acknowledgments"></a>Confirmaciones estáticas
Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admite los modos de original, mejorada, aplazada y estático confirmación (ACK). Si selecciona el modo de confirmación estático para una entidad en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generarán confirmaciones estáticas que contienen solo una indicación de éxito o error. La confirmación estática indica si el sistema de recepción recibe y procesa el mensaje de correcto y los valores de error configurados en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración.  
  
 En original, mejorado y diferidas modos, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera confirmaciones dinámicas. Están codificados para HL7 y contienen campos, tales como el campo de código de confirmación de MSA.1 y el segmento ERR. El campo MSA.1 de una confirmación dinámica indicará si una condición de error es un rechazo o Error, como resultado de procesamiento diferentes (consulte [segmento de confirmación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)). El segmento ERR proporciona información detallada sobre el error. Confirmaciones estáticos no proporcionan ninguna información.  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]procesa una confirmación estática de manera diferente a una confirmación dinámica. Si un puerto de envío bidireccional (que sólo enviará el mensaje siguiente después de recibir la confirmación) recibe la confirmación y la confirmación estática indica un error (o no es una confirmación válida), [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se mueve al transporte secundario o suspender el mensaje. No volverá a intentar el mensaje, tal y como lo haría si recibe una confirmación dinámica, dependiendo de la condición de error.  
  
 Cuando el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analizador procesa una confirmación estática, escribe el **IsStaticAck** propiedad booleana en el contexto del mensaje. El serializador utiliza este valor para determinar si debe procesar el mensaje como una confirmación estático.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Segmento de confirmación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)