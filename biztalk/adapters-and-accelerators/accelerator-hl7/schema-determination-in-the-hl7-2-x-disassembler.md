---
title: "Determinación del esquema en el Desensamblador 2.X HL7 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- header segments [2.X]
- 2.X messages, header segments
- messages, parsing messages
- MSH
- disassembler, parsing messages
- 2.X messages, MSH
ms.assetid: afd45c4c-2feb-44eb-b3bd-49fe114eb893
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6314f9651d09dbb041d2e8851565e904366c9efe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-determination-in-the-hl7-2x-disassembler"></a><span data-ttu-id="4c18c-102">Determinación del esquema en el Desensamblador 2.X HL7</span><span class="sxs-lookup"><span data-stu-id="4c18c-102">Schema Determination in the HL7 2.X Disassembler</span></span>
<span data-ttu-id="4c18c-103">Mensajes de HL7 2.X contienen un segmento de encabezado (MSH), seguido de un número de segmentos de cuerpo y un número opcional de segmentos de Z.</span><span class="sxs-lookup"><span data-stu-id="4c18c-103">HL7 2.X messages contain a header segment (MSH), followed by a number of body segments and an optional number of Z segments.</span></span> <span data-ttu-id="4c18c-104">MSH contiene 21 campos.</span><span class="sxs-lookup"><span data-stu-id="4c18c-104">MSH contains 21 fields.</span></span>  
  
 <span data-ttu-id="4c18c-105">Cuando llega un mensaje, el motor 2.X lee el encabezado para determinar el esquema a utilizar para analizar el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4c18c-105">When a message arrives, the 2.X engine reads the header to determine the schema to use to parse the message body.</span></span> <span data-ttu-id="4c18c-106">Se produce la siguiente secuencia de eventos:</span><span class="sxs-lookup"><span data-stu-id="4c18c-106">The following sequence of events occurs:</span></span>  
  
1.  <span data-ttu-id="4c18c-107">El Desensamblador lee el valor de MSH3 (entidad de origen) para determinar las siguientes opciones de validación:</span><span class="sxs-lookup"><span data-stu-id="4c18c-107">The disassembler reads the value of MSH3 (source party) to determine the following validation options:</span></span>  
  
    1.  <span data-ttu-id="4c18c-108">Si se debe realizar la validación de XML para el cuerpo</span><span class="sxs-lookup"><span data-stu-id="4c18c-108">Whether to perform XML validation for the body</span></span>  
  
    2.  <span data-ttu-id="4c18c-109">Si se debe validar datos personalizados escriba campos en los datos de cuerpo</span><span class="sxs-lookup"><span data-stu-id="4c18c-109">Whether to validate custom data type fields in the body data</span></span>  
  
    3.  <span data-ttu-id="4c18c-110">Si desea permitir delimitadores en el cuerpo finales</span><span class="sxs-lookup"><span data-stu-id="4c18c-110">Whether to allow trailing delimiters in the body</span></span>  
  
    4.  <span data-ttu-id="4c18c-111">¿Qué es el espacio de nombres de destino del esquema de cuerpo (**TargetNS**)</span><span class="sxs-lookup"><span data-stu-id="4c18c-111">What the target namespace of the body schema is (**TargetNS**)</span></span>  
  
2.  <span data-ttu-id="4c18c-112">El desensamblador, a continuación, lee MSH9 y MSH12 para determinar el nombre del nodo raíz del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="4c18c-112">The disassembler then reads MSH9 and MSH12 to determine the root node name of the body.</span></span> <span data-ttu-id="4c18c-113">El algoritmo es como sigue:</span><span class="sxs-lookup"><span data-stu-id="4c18c-113">The algorithm is as follows:</span></span>  
  
    ```  
    Body schema type = TargetNS + "#" + MSH9.1 + MSH9.2 + MSH12.1 (with dots removed) + MSH12.2 (or GLO if the value is blank) + MSH12.3 (or DEF if the value is blank)  
    ```  
  
     [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="4c18c-114">Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) siempre permite finales delimitadores en un encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4c18c-114"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) always allows trailing delimiters in a message header.</span></span> <span data-ttu-id="4c18c-115">El motor examina el identificador de segmento que se los tres primeros caracteres de cada línea.</span><span class="sxs-lookup"><span data-stu-id="4c18c-115">The engine examines the segment identifier that is the first three characters of each line.</span></span> <span data-ttu-id="4c18c-116">Mantiene generar XML para todos los segmentos que define el esquema de cuerpo.</span><span class="sxs-lookup"><span data-stu-id="4c18c-116">It keeps on generating XML for all segments that the body schema defines.</span></span> <span data-ttu-id="4c18c-117">Cuando encuentra un segmento no definido, trata ese segmento como un segmento de Z.</span><span class="sxs-lookup"><span data-stu-id="4c18c-117">When it encounters an undefined segment, it treats that segment as a Z segment.</span></span> <span data-ttu-id="4c18c-118">Desde ese momento, todos los segmentos indefinidos constituyen la parte Z del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4c18c-118">From that point on, all undefined segments constitute the Z part of the message.</span></span> <span data-ttu-id="4c18c-119">El siguiente MSH marca el final de este mensaje.</span><span class="sxs-lookup"><span data-stu-id="4c18c-119">The next MSH marks the end of this message.</span></span> <span data-ttu-id="4c18c-120">Para los mensajes por lotes, el siguiente MSH o BTS (la etiqueta de segmento de finalizador de lote) marca el final de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="4c18c-120">For batch messages, the next MSH or BTS (the batch trailer segment tag) marks the end of a message.</span></span> <span data-ttu-id="4c18c-121">Un segmento de Z solo puede contener segmentos que son no declarados en un esquema.</span><span class="sxs-lookup"><span data-stu-id="4c18c-121">A Z segment can only contain segments that are undeclared in a schema.</span></span> <span data-ttu-id="4c18c-122">Es un error que encuentre un segmento declarado.</span><span class="sxs-lookup"><span data-stu-id="4c18c-122">It is an error to encounter a declared segment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c18c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c18c-123">See Also</span></span>  
 <span data-ttu-id="4c18c-124">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="4c18c-124">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="4c18c-125">Procesamiento de archivo sin formato BTAHL72X</span><span class="sxs-lookup"><span data-stu-id="4c18c-125">BTAHL72X Flat File Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)