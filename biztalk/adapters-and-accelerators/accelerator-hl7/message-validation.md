---
title: "Validación de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, messages
- messages, validating
ms.assetid: 720ab16a-7ab4-4741-9951-9ab10a2c4c24
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 940b6aa811cbee845b287c09a66c4b9753313ee0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-validation"></a>Validación del mensaje
Mensaje de validación se produce para los mensajes entrantes y salientes de HL7 con HL7 2.X canalizaciones de envío y recepción. Puede configurar la validación para un solo segmento de MSH (encabezado), o para el cuerpo del mensaje completo. Además, es posible validar con respecto a las versiones localizadas únicas del esquema. Para ello, si define un valor de espacio de nombres único y utilizando este valor de espacio de nombres dentro de la configuración de mensajería HL7 (en el nivel de entidad) y la propiedad de espacio de nombres de destino del esquema real que define el mensaje. En tiempo de ejecución [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) usa la combinación de espacio de nombres y la propiedad referencia raíz para el esquema para seleccionar el esquema adecuado para analizar el mensaje y la validación.  
  
 El analizador y el serializador de realizan la validación basada en la configuración de la entidad asociada con un mensaje. Otros valores de entidad, incluidos la invalidación de procesamiento por lotes, la confirmación y el encabezado del mensaje afecta a cómo el analizador o el serializador realiza la validación.  
  
> [!NOTE]
>  El serializador realiza una serie de pasos, incluido (si procede) realizar invalidaciones de encabezado de un mapa de MSH y realizar la validación de XML. Si los procesos de invalidación y validación de encabezado se activan los servicios y el proceso de invalidación de encabezado entre en un valor incorrecto en un campo de encabezado, el mensaje se considerará no válido, incluso si el mensaje se hubieran pasar la validación de cuerpo.  
  
## <a name="see-also"></a>Vea también  
 [Invalidación de MSH](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)