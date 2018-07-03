---
title: Control de segmentos de Z no declarados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z segments, 2.X schemas
- 2.X schemas, undeclared Z segments
- segments, undeclared [Z objects]
- Z objects, undeclared segments
ms.assetid: 8878bc93-1833-4bfc-b80e-305e4144739e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 633c1d338a87bef7c0fe53ff5df7f53438eac843
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990021"
---
# <a name="handling-undeclared-z-segments"></a><span data-ttu-id="33619-102">Control de segmentos de Z no declarados</span><span class="sxs-lookup"><span data-stu-id="33619-102">Handling Undeclared Z Segments</span></span>
<span data-ttu-id="33619-103">Hay dos tipos de segmentos de Z: declara los segmentos de Z y Z no declarados.</span><span class="sxs-lookup"><span data-stu-id="33619-103">There are two types of Z segments: declared Z segments and undeclared Z segments.</span></span> <span data-ttu-id="33619-104">Aunque son similares en que usarlos para fines locales, son muy diferentes en cómo usarlos.</span><span class="sxs-lookup"><span data-stu-id="33619-104">While they are similar in that you use them for local purposes, they are very different in how you use them.</span></span>  
  
 <span data-ttu-id="33619-105">Incluir la definición de un segmento de Z declarado en un esquema de mensaje y el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) lo usa para procesar un mensaje, al igual que un esquema definido por el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="33619-105">You include the definition of a declared Z segment in a message schema, and Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses it to process a message, just like a schema defined by the HL7 standard.</span></span> <span data-ttu-id="33619-106">No hay ningún esquema define un segmento de Z no declarado.</span><span class="sxs-lookup"><span data-stu-id="33619-106">No schema defines an undeclared Z segment.</span></span> <span data-ttu-id="33619-107">Incluir un segmento de Z no declarado al final de un mensaje, y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] atraviesa sin procesarlo con un esquema.</span><span class="sxs-lookup"><span data-stu-id="33619-107">You include an undeclared Z segment at the end of a message, and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] passes through without processing it against a schema.</span></span> <span data-ttu-id="33619-108">El analizador y el serializador no validarlo.</span><span class="sxs-lookup"><span data-stu-id="33619-108">The parser and serializer do not validate it.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="33619-109"> lo trata como un objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="33619-109"> treats it as a binary large object (BLOB).</span></span> <span data-ttu-id="33619-110">Compruebe el único que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does en una Z no declarados segmento es comprobar que el BLOB no incluye cualquier etiqueta de esquema de tres caracteres existentes.</span><span class="sxs-lookup"><span data-stu-id="33619-110">The only check that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does on an undeclared Z segment is verifying that the BLOB does not include any existing three-character schema tag.</span></span>  
  
 <span data-ttu-id="33619-111">Incluir el segmento de Z no declarado como la tercera parte, o como parte de la Z, de un mensaje de varias partes.</span><span class="sxs-lookup"><span data-stu-id="33619-111">You include the undeclared Z segment as the third part, or Z part, of a multi-part message.</span></span> <span data-ttu-id="33619-112">El mensaje incluye el encabezado, el cuerpo y la parte de la Z.</span><span class="sxs-lookup"><span data-stu-id="33619-112">The message includes the header, the body, and the Z part.</span></span> <span data-ttu-id="33619-113">La parte Z tiene un identificador de segmento empezando por la letra "Z".</span><span class="sxs-lookup"><span data-stu-id="33619-113">The Z part has a segment ID starting with the letter "Z".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33619-114">El Zpart siempre debe contener datos.</span><span class="sxs-lookup"><span data-stu-id="33619-114">The Zpart must always contain data.</span></span> <span data-ttu-id="33619-115">Especificar null para los resultados del flujo en una condición de error.</span><span class="sxs-lookup"><span data-stu-id="33619-115">Specifying null for the stream results in an error condition.</span></span> <span data-ttu-id="33619-116">Si no se incluye ningún dato en el Zpart, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] inserta la palabra "Empty" en el Zpart.</span><span class="sxs-lookup"><span data-stu-id="33619-116">If no data is included in the Zpart, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] inserts the word "Empty" in the Zpart.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="33619-117"> usa la propiedad de contexto **ZPartPresent** para determinar si se debe serializar la parte de la Z.</span><span class="sxs-lookup"><span data-stu-id="33619-117"> uses the context property **ZPartPresent** to determine whether to serialize the Z part.</span></span>  
> 
> [!CAUTION]
>  <span data-ttu-id="33619-118">Microsoft ha probado Zsegments con juegos de caracteres ANSI, con lo que es predecible comportamiento Zsegment con caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="33619-118">Microsoft has tested Zsegments with ANSI character sets, with the result that Zsegment behavior with ANSI characters is predictable.</span></span> <span data-ttu-id="33619-119">Sin embargo, el uso de otros juegos de caracteres en Zsegments puede provocar un comportamiento imprevisible.</span><span class="sxs-lookup"><span data-stu-id="33619-119">However, using other character sets in Zsegments may result in unpredictable behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33619-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="33619-120">See Also</span></span>  
 <span data-ttu-id="33619-121">[Extender esquemas HL7 2.X con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="33619-121">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="33619-122">[Creación de segmentos Z declarados](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="33619-122">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="33619-123">[Creación de tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="33619-123">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 [<span data-ttu-id="33619-124">Creación de tablas personalizadas en esquemas</span><span class="sxs-lookup"><span data-stu-id="33619-124">Creating Custom Tables in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)