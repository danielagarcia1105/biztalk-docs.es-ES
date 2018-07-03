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
# <a name="handling-undeclared-z-segments"></a>Control de segmentos de Z no declarados
Hay dos tipos de segmentos de Z: declara los segmentos de Z y Z no declarados. Aunque son similares en que usarlos para fines locales, son muy diferentes en cómo usarlos.  
  
 Incluir la definición de un segmento de Z declarado en un esquema de mensaje y el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) lo usa para procesar un mensaje, al igual que un esquema definido por el estándar HL7. No hay ningún esquema define un segmento de Z no declarado. Incluir un segmento de Z no declarado al final de un mensaje, y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] atraviesa sin procesarlo con un esquema. El analizador y el serializador no validarlo. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] lo trata como un objeto binario grande (BLOB). Compruebe el único que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does en una Z no declarados segmento es comprobar que el BLOB no incluye cualquier etiqueta de esquema de tres caracteres existentes.  
  
 Incluir el segmento de Z no declarado como la tercera parte, o como parte de la Z, de un mensaje de varias partes. El mensaje incluye el encabezado, el cuerpo y la parte de la Z. La parte Z tiene un identificador de segmento empezando por la letra "Z".  
  
> [!NOTE]
>  El Zpart siempre debe contener datos. Especificar null para los resultados del flujo en una condición de error. Si no se incluye ningún dato en el Zpart, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] inserta la palabra "Empty" en el Zpart. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] usa la propiedad de contexto **ZPartPresent** para determinar si se debe serializar la parte de la Z.  
> 
> [!CAUTION]
>  Microsoft ha probado Zsegments con juegos de caracteres ANSI, con lo que es predecible comportamiento Zsegment con caracteres ANSI. Sin embargo, el uso de otros juegos de caracteres en Zsegments puede provocar un comportamiento imprevisible.  
  
## <a name="see-also"></a>Vea también  
 [Extender esquemas HL7 2.X con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [Creación de segmentos Z declarados](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [Creación de tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [Creación de tablas personalizadas en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)