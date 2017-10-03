---
title: Vocabulario | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, vocabulary
- vocabularies
ms.assetid: c5df05dd-4af8-4e48-8509-e692b04adf3c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c77247054914097131103fe33d86fc78551d8cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="vocabulary"></a>Vocabulario
HL7 versión 2 proporciona cierta compatibilidad para vocabularios para elementos codificados, pero en su mayor parte, proporciona una estructura que transmite códigos procedentes de sistemas locales de codificación.  
  
 En HL7 versión 2, una tabla de segmento vincula todos los campos codificados. La tabla segmento incluye el identificador de la tabla que utiliza el campo. Hay tres tipos de tablas: definen HL7, definidos externamente y definido por el usuario. En algunos casos, el estándar proporciona los valores de ejemplo para una tabla definida por el usuario. Debe tratar estos tal y como ha etiquetado el estándar HL7 ellos.  
  
 En las nuevas versiones, no se puede quitar códigos de tablas de HL7 definido, pero puede agregar nuevos códigos. Puede cambiar las tablas definidas por el usuario como desee.  
  
 Las siguientes funciones de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) compatible con estos requisitos:  
  
-   Puede usar todas las tablas de HL7 definido.  
  
-   Puede importar y usar externamente definido conjuntos de código como ICD9 y LOINC.  
  
-   Puede proporcionar los valores para las tablas definidas por el usuario.  
  
-   En casos donde los sistemas son compatibles con diferentes conjuntos de códigos, puede configurar las asignaciones que permiten conjuntos de códigos diferentes interoperar. Si es necesario, puede definir varias instancias de una sola tabla definida por el usuario para ir junto con la asignación de intermediaria.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)