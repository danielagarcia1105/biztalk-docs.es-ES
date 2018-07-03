---
title: Vocabulario | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, vocabulary
- vocabularies
ms.assetid: c5df05dd-4af8-4e48-8509-e692b04adf3c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e72b51e327581c0a17f18582b0511218b556a7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979037"
---
# <a name="vocabulary"></a>Vocabulario
HL7 versión 2 proporciona compatibilidad para vocabularios para elementos codificados, pero en su mayor parte, proporciona una estructura que transmite códigos procedentes de los sistemas locales de codificación.  
  
 De HL7 versión 2, una tabla de segmentos vincula todos los campos codificados. La tabla segmento incluye el identificador de la tabla que usa el campo. Hay tres tipos de tablas: HL7 definido, definido externamente y definido por el usuario. En algunos casos, el estándar proporciona los valores de ejemplo para una tabla definida por el usuario. Debe tratar estos según el estándar HL7 ha etiquetado en ellos.  
  
 En las nuevas versiones, no se puede quitar los códigos de las tablas de HL7 definido, pero puede agregar nuevos códigos. Puede cambiar las tablas definidas por el usuario a voluntad.  
  
 Las siguientes funciones del Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admiten estos requisitos:  
  
-   Puede usar todas las tablas de HL7 definido.  
  
-   Puede importar y conjuntos de código como ICD9 y LOINC define el uso externamente.  
  
-   Puede proporcionar los valores para las tablas definidas por el usuario.  
  
-   En casos donde los sistemas son compatibles con diferentes conjuntos de códigos, puede configurar las asignaciones que permiten conjuntos dispares de código interoperar. Si es necesario, puede definir varias instancias de una sola tabla definido por el usuario que acompañan a la asignación intermedia.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)