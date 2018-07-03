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
# <a name="message-validation"></a><span data-ttu-id="fe9e7-102">Validación de mensajes</span><span class="sxs-lookup"><span data-stu-id="fe9e7-102">Message Validation</span></span>
<span data-ttu-id="fe9e7-103">Mensaje de validación se produce para los mensajes entrantes y salientes de HL7 con HL7 2.X canalizaciones de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="fe9e7-103">Message validation occurs for incoming and outgoing HL7 messages with HL7 2.X receive and send pipelines.</span></span> <span data-ttu-id="fe9e7-104">Puede configurar la validación solo del segmento de MSH (encabezado), o para el cuerpo del mensaje completo.</span><span class="sxs-lookup"><span data-stu-id="fe9e7-104">You can configure validation for only the MSH (header) segment, or for the entire message body.</span></span> <span data-ttu-id="fe9e7-105">Además, es posible validar con respecto a versiones localizadas únicas del esquema.</span><span class="sxs-lookup"><span data-stu-id="fe9e7-105">In addition, it is possible to validate against unique localized versions of the schema.</span></span> <span data-ttu-id="fe9e7-106">Esto se consigue mediante la definición de un valor de espacio de nombres único y usa este valor de espacio de nombres dentro de la configuración de mensajería de HL7 (en el nivel de entidad) y la propiedad de espacio de nombres de destino del esquema que define el mensaje real.</span><span class="sxs-lookup"><span data-stu-id="fe9e7-106">You accomplish this by defining a unique namespace value, and using this namespace value within both the HL7 messaging configuration (at the party level) and the target namespace property of the actual schema that defines the message.</span></span> <span data-ttu-id="fe9e7-107">En tiempo de ejecución, el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) usa la combinación de espacio de nombres y la propiedad referencia raíz para el esquema para seleccionar el esquema adecuado para analizar el mensaje y la validación.</span><span class="sxs-lookup"><span data-stu-id="fe9e7-107">At run time, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the combination of namespace and the root reference property for the schema to select the appropriate schema for message parsing and validation.</span></span>  
  
 <span data-ttu-id="fe9e7-108">El analizador y el serializador realizan la validación según la configuración de la entidad asociada al mensaje.</span><span class="sxs-lookup"><span data-stu-id="fe9e7-108">The parser and serializer perform validation based on the settings for the party associated with a message.</span></span> <span data-ttu-id="fe9e7-109">Otros valores de entidad, incluidos la invalidación de procesamiento por lotes, la confirmación y el encabezado del mensaje afecta a cómo el analizador o serializador realiza la validación.</span><span class="sxs-lookup"><span data-stu-id="fe9e7-109">Other party settings, including batching, acknowledgment, and message-header override affect how the parser or serializer performs validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe9e7-110">El serializador realiza una serie de pasos, incluida (si procede) realizar reemplazos de encabezado de una asignación de MSH y realizar la validación de XML.</span><span class="sxs-lookup"><span data-stu-id="fe9e7-110">The serializer performs a series of steps, including (if applicable) performing header overrides from an MSH map, and performing XML validation.</span></span> <span data-ttu-id="fe9e7-111">Si los procesos de invalidación y la validación de encabezado son ambos habilitados y el proceso de reemplazo de encabezado, escribe un valor incorrecto en un campo de encabezado, el mensaje se producirá un error de validación, incluso si el mensaje pasar la validación del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="fe9e7-111">If the header override and validation processes are both enabled, and the header override process enters an incorrect value into a header field, the message will fail validation, even if the message were to pass body validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe9e7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe9e7-112">See Also</span></span>  
 [<span data-ttu-id="fe9e7-113">Invalidación de MSH</span><span class="sxs-lookup"><span data-stu-id="fe9e7-113">MSH Override</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)