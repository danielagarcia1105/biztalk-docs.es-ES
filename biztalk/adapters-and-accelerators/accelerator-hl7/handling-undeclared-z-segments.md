---
title: Control de segmentos de Z no declarado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Z segments, 2.X schemas
- 2.X schemas, undeclared Z segments
- segments, undeclared [Z objects]
- Z objects, undeclared segments
ms.assetid: 8878bc93-1833-4bfc-b80e-305e4144739e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff982aedee39ed60820a9f03db11d7e4d051a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="handling-undeclared-z-segments"></a><span data-ttu-id="706be-102">Control de segmentos de Z no declarado</span><span class="sxs-lookup"><span data-stu-id="706be-102">Handling Undeclared Z Segments</span></span>
<span data-ttu-id="706be-103">Hay dos tipos de segmentos de Z: declara segmentos de Z y Z no declarado.</span><span class="sxs-lookup"><span data-stu-id="706be-103">There are two types of Z segments: declared Z segments and undeclared Z segments.</span></span> <span data-ttu-id="706be-104">Mientras que son similares en cuanto utilizarlos para propósitos locales, son muy diferentes en cómo usarlos.</span><span class="sxs-lookup"><span data-stu-id="706be-104">While they are similar in that you use them for local purposes, they are very different in how you use them.</span></span>  
  
 <span data-ttu-id="706be-105">Incluir la definición de un segmento de Z declarado en un esquema de mensaje, y [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se utiliza para procesar un mensaje, como un esquema definido por el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="706be-105">You include the definition of a declared Z segment in a message schema, and [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses it to process a message, just like a schema defined by the HL7 standard.</span></span> <span data-ttu-id="706be-106">Ningún esquema define un segmento de Z no declarado.</span><span class="sxs-lookup"><span data-stu-id="706be-106">No schema defines an undeclared Z segment.</span></span> <span data-ttu-id="706be-107">Incluir un segmento de Z no declarado al final de un mensaje, y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] atraviesa sin procesar en un esquema.</span><span class="sxs-lookup"><span data-stu-id="706be-107">You include an undeclared Z segment at the end of a message, and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] passes through without processing it against a schema.</span></span> <span data-ttu-id="706be-108">El analizador y el serializador no validarlo.</span><span class="sxs-lookup"><span data-stu-id="706be-108">The parser and serializer do not validate it.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="706be-109">lo trata como un objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="706be-109"> treats it as a binary large object (BLOB).</span></span> <span data-ttu-id="706be-110">Compruebe el único que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does en un Z no declarado segmento consiste en comprobar que el BLOB no incluye cualquier etiqueta de tres caracteres esquema existente.</span><span class="sxs-lookup"><span data-stu-id="706be-110">The only check that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does on an undeclared Z segment is verifying that the BLOB does not include any existing three-character schema tag.</span></span>  
  
 <span data-ttu-id="706be-111">Incluir el segmento de Z no declarado como la tercera parte, o parte de la Z, de un mensaje de varias partes.</span><span class="sxs-lookup"><span data-stu-id="706be-111">You include the undeclared Z segment as the third part, or Z part, of a multi-part message.</span></span> <span data-ttu-id="706be-112">El mensaje incluye el encabezado, el cuerpo y la parte de Z.</span><span class="sxs-lookup"><span data-stu-id="706be-112">The message includes the header, the body, and the Z part.</span></span> <span data-ttu-id="706be-113">La parte de Z tiene un identificador de segmento que empiecen por la letra "Z".</span><span class="sxs-lookup"><span data-stu-id="706be-113">The Z part has a segment ID starting with the letter "Z".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="706be-114">El Zpart siempre debe contener datos.</span><span class="sxs-lookup"><span data-stu-id="706be-114">The Zpart must always contain data.</span></span> <span data-ttu-id="706be-115">Si se especifica null para los resultados del flujo en una condición de error.</span><span class="sxs-lookup"><span data-stu-id="706be-115">Specifying null for the stream results in an error condition.</span></span> <span data-ttu-id="706be-116">Si no se incluye ningún dato en el Zpart [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] inserta la palabra "Vacío" en la Zpart.</span><span class="sxs-lookup"><span data-stu-id="706be-116">If no data is included in the Zpart, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] inserts the word "Empty" in the Zpart.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="706be-117">usa la propiedad de contexto **ZPartPresent** para determinar si se debe serializar la parte de Z.</span><span class="sxs-lookup"><span data-stu-id="706be-117"> uses the context property **ZPartPresent** to determine whether to serialize the Z part.</span></span>  
  
> [!CAUTION]
>  [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="706be-118">ha probado Zsegments con juegos de caracteres ANSI, con lo que el comportamiento de Zsegment con caracteres ANSI es predecible.</span><span class="sxs-lookup"><span data-stu-id="706be-118"> has tested Zsegments with ANSI character sets, with the result that Zsegment behavior with ANSI characters is predictable.</span></span> <span data-ttu-id="706be-119">Sin embargo, el uso otros juegos de caracteres en Zsegments podría causar un comportamiento imprevisible.</span><span class="sxs-lookup"><span data-stu-id="706be-119">However, using other character sets in Zsegments may result in unpredictable behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="706be-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="706be-120">See Also</span></span>  
 <span data-ttu-id="706be-121">[Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="706be-121">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="706be-122">[Crear segmentos de Z declarado](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="706be-122">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="706be-123">[Crear tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="706be-123">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 [<span data-ttu-id="706be-124">Crear tablas personalizadas en esquemas</span><span class="sxs-lookup"><span data-stu-id="706be-124">Creating Custom Tables in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)