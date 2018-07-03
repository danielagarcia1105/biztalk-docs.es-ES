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
- validating, messages
- messages, validating
ms.assetid: 720ab16a-7ab4-4741-9951-9ab10a2c4c24
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b4c94b7a7122572724060b2a45447699e15c1a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970197"
---
# <a name="message-validation"></a>Validación de mensajes
Mensaje de validación se produce para los mensajes entrantes y salientes de HL7 con HL7 2.X canalizaciones de envío y recepción. Puede configurar la validación solo del segmento de MSH (encabezado), o para el cuerpo del mensaje completo. Además, es posible validar con respecto a versiones localizadas únicas del esquema. Esto se consigue mediante la definición de un valor de espacio de nombres único y usa este valor de espacio de nombres dentro de la configuración de mensajería de HL7 (en el nivel de entidad) y la propiedad de espacio de nombres de destino del esquema que define el mensaje real. En tiempo de ejecución, el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) usa la combinación de espacio de nombres y la propiedad referencia raíz para el esquema para seleccionar el esquema adecuado para analizar el mensaje y la validación.  
  
 El analizador y el serializador realizan la validación según la configuración de la entidad asociada al mensaje. Otros valores de entidad, incluidos la invalidación de procesamiento por lotes, la confirmación y el encabezado del mensaje afecta a cómo el analizador o serializador realiza la validación.  
  
> [!NOTE]
>  El serializador realiza una serie de pasos, incluida (si procede) realizar reemplazos de encabezado de una asignación de MSH y realizar la validación de XML. Si los procesos de invalidación y la validación de encabezado son ambos habilitados y el proceso de reemplazo de encabezado, escribe un valor incorrecto en un campo de encabezado, el mensaje se producirá un error de validación, incluso si el mensaje pasar la validación del cuerpo.  
  
## <a name="see-also"></a>Vea también  
 [Invalidación de MSH](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)