---
title: Tipos de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data types, messages
- messages, data types
ms.assetid: 7a758289-1629-48a0-843d-6f6773bd5ba6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8580b4f6c2a3f1a9f461b112bb4125f1a11ebbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-types"></a>Tipos de datos
La especificación de tipo de datos es una herramienta importante para crear particiones de la complejidad del estándar HL7 y es fundamental para entender el contenido de datos de un campo de HL7. Algunos tipos de datos son sencillos y contienen solo un componente, y algunos contienen muchos componentes y subcomponentes. Por ejemplo, PID.5 Patient Name tiene el tipo de datos XPN en la versión 2.4. Este tipo de datos admite las subdivisiones comunes de un nombre de idioma inglés, por ejemplo, apellido, nombre, segundo nombre, así como sufijo, prefijo, el código de tipo de nombre e intervalo de validez (fecha) de nombre.  
  
 En versiones nuevas de HL7, puede agregar pero no quitar tipos de datos. Si agrega contenido a un tipo de datos, mediante la adición de nuevos componentes o subcomponentes, solo puede agregarlos al final de la estructura en la que están anidados. En algunos casos, la organización de HL7 combinado existente tipos de datos para formar otros nuevos. Esto causaba la necesidad de admitir elementos que anteriormente estaban subcomponentes dentro de los tipos de datos original.  
  
 Las siguientes funciones de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) compatible con estos requisitos:  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]admite tipos de datos estándar para todas las versiones de HL7 desde V2.1 en.  
  
-   Puede restringir los tipos de datos donde corresponda al desarrollar interfaces.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Id. de tipo de datos de HL7 2.1](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)