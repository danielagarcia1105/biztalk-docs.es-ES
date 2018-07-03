---
title: Tipos de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, messages
- messages, data types
ms.assetid: 7a758289-1629-48a0-843d-6f6773bd5ba6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a7b8d75be35be01e9c961d6bd054dcaed6d3aee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984677"
---
# <a name="data-types"></a>Tipos de datos
La especificación de tipo de datos es una herramienta importante para la partición de la complejidad del estándar HL7 y es fundamental para entender el contenido de datos de un campo de HL7. Algunos tipos de datos son simples y contienen solo un componente, y algunos contienen muchos componentes y subcomponentes. Por ejemplo, nombre de paciente PID.5 tiene el tipo de datos XPN en la versión 2.4. Este tipo de datos es compatible con las subdivisiones comunes de un nombre de idioma inglés, por ejemplo, apellido, nombre, segundo nombre, así como sufijo, prefijo, el código de tipo de nombre e intervalo de validez (fecha) de nombre.  
  
 En nuevas versiones de HL7, puede agregar, pero no quitar tipos de datos. Si agrega contenido a un tipo de datos mediante la adición de nuevos componentes o subcomponentes, solo se puede agregar al final de la estructura en la que están anidados. En algunos casos, la organización de HL7 combina existentes de los tipos de datos para formar otros nuevos. Esto se llevó a la necesidad de admitir los elementos que estaban anteriormente subcomponentes dentro de los tipos de datos original.  
  
 Las siguientes funciones del Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admiten estos requisitos:  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] admite los tipos de datos estándar para todas las versiones de HL7 desde V2.1 en.  
  
- Puede restringir los tipos de datos cuando sea apropiado al desarrollar interfaces.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Id. de tipo de datos en HL7 2.1](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)