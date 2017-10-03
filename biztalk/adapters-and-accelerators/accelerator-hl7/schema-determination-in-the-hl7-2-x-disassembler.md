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
# <a name="schema-determination-in-the-hl7-2x-disassembler"></a>Determinación del esquema en el Desensamblador 2.X HL7
Mensajes de HL7 2.X contienen un segmento de encabezado (MSH), seguido de un número de segmentos de cuerpo y un número opcional de segmentos de Z. MSH contiene 21 campos.  
  
 Cuando llega un mensaje, el motor 2.X lee el encabezado para determinar el esquema a utilizar para analizar el cuerpo del mensaje. Se produce la siguiente secuencia de eventos:  
  
1.  El Desensamblador lee el valor de MSH3 (entidad de origen) para determinar las siguientes opciones de validación:  
  
    1.  Si se debe realizar la validación de XML para el cuerpo  
  
    2.  Si se debe validar datos personalizados escriba campos en los datos de cuerpo  
  
    3.  Si desea permitir delimitadores en el cuerpo finales  
  
    4.  ¿Qué es el espacio de nombres de destino del esquema de cuerpo (**TargetNS**)  
  
2.  El desensamblador, a continuación, lee MSH9 y MSH12 para determinar el nombre del nodo raíz del cuerpo. El algoritmo es como sigue:  
  
    ```  
    Body schema type = TargetNS + "#" + MSH9.1 + MSH9.2 + MSH12.1 (with dots removed) + MSH12.2 (or GLO if the value is blank) + MSH12.3 (or DEF if the value is blank)  
    ```  
  
     [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) siempre permite finales delimitadores en un encabezado del mensaje. El motor examina el identificador de segmento que se los tres primeros caracteres de cada línea. Mantiene generar XML para todos los segmentos que define el esquema de cuerpo. Cuando encuentra un segmento no definido, trata ese segmento como un segmento de Z. Desde ese momento, todos los segmentos indefinidos constituyen la parte Z del mensaje. El siguiente MSH marca el final de este mensaje. Para los mensajes por lotes, el siguiente MSH o BTS (la etiqueta de segmento de finalizador de lote) marca el final de un mensaje. Un segmento de Z solo puede contener segmentos que son no declarados en un esquema. Es un error que encuentre un segmento declarado.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Procesamiento de archivo sin formato BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)