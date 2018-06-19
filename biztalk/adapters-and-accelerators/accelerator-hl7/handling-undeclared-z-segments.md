---
title: Control de segmentos de Z no declarado | Documentos de Microsoft
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
ms.openlocfilehash: 6ff982aedee39ed60820a9f03db11d7e4d051a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204676"
---
# <a name="handling-undeclared-z-segments"></a>Control de segmentos de Z no declarado
Hay dos tipos de segmentos de Z: declara segmentos de Z y Z no declarado. Mientras que son similares en cuanto utilizarlos para propósitos locales, son muy diferentes en cómo usarlos.  
  
 Incluir la definición de un segmento de Z declarado en un esquema de mensaje, y [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se utiliza para procesar un mensaje, como un esquema definido por el estándar HL7. Ningún esquema define un segmento de Z no declarado. Incluir un segmento de Z no declarado al final de un mensaje, y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] atraviesa sin procesar en un esquema. El analizador y el serializador no validarlo. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]lo trata como un objeto binario grande (BLOB). Compruebe el único que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does en un Z no declarado segmento consiste en comprobar que el BLOB no incluye cualquier etiqueta de tres caracteres esquema existente.  
  
 Incluir el segmento de Z no declarado como la tercera parte, o parte de la Z, de un mensaje de varias partes. El mensaje incluye el encabezado, el cuerpo y la parte de Z. La parte de Z tiene un identificador de segmento que empiecen por la letra "Z".  
  
> [!NOTE]
>  El Zpart siempre debe contener datos. Si se especifica null para los resultados del flujo en una condición de error. Si no se incluye ningún dato en el Zpart [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] inserta la palabra "Vacío" en la Zpart. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]usa la propiedad de contexto **ZPartPresent** para determinar si se debe serializar la parte de Z.  
  
> [!CAUTION]
>  [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ha probado Zsegments con juegos de caracteres ANSI, con lo que el comportamiento de Zsegment con caracteres ANSI es predecible. Sin embargo, el uso otros juegos de caracteres en Zsegments podría causar un comportamiento imprevisible.  
  
## <a name="see-also"></a>Vea también  
 [Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [Crear segmentos de Z declarado](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [Crear tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [Crear tablas personalizadas en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)