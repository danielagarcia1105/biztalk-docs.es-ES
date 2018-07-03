---
title: Id. de tipo de datos en HL7 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, data type ID
- data types, messages
- messages, data types
ms.assetid: d1412886-ff0b-4333-b01e-1c3ae45240e2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d7251ce1c041ebfd2f523e3304bd253fec22fb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983013"
---
# <a name="data-type-id-in-hl7"></a>Identificador de tipo de datos en HL7
En el caso de HL7 V2.1, el identificador de tipo de datos es un marcador de posición para los tipos de datos sin definir. Los siguientes son ejemplos de su uso:  
  
- El tipo de datos en forma de un campo ST es SI (Id. de secuencia).  
  
- El tipo de datos en forma de un campo NM es campos compuestos.  
  
  Los siguientes son ejemplos de tipos de datos compuesto definido específicamente:  
  
- CK: Identificador compuesto con el dígito de control. Por ejemplo:  
  
  ```  
  |128952^6^M11|  
  ```  
  
- CN: Número de identificador compuesto y nombre. Por ejemplo:  
  
  ```  
  |12372^RIGGINS^JOHN^""^MD|  
  |12372|  
  |^RIGGINS^JOHN^""^MD|  
  ```  
  
- CQ: La cantidad compuesta por unidades. Por ejemplo:  
  
  ```  
  |123.7^ML|  
  ```  
  
- CE: Elemento codificada. Por ejemplo:  
  
  ```  
  |54.21^Laparoscopy^I9C^42112^^AS4|  
  ```  
  
  Este tipo de datos está localizado y definido por el sitio. Además, HL7 V2.1 no proporciona la cobertura para este tipo de datos en la base de datos de Access de HL7. Para generar los esquemas, el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se da por supuesto que los tipos de datos de HL7 V2.2 son válidos y usa esta información para generar los esquemas. Dependiendo del uso en el esquema, se debe usar un tipo de datos adecuado, lo que significa que el tipo de datos debe reemplazarse por CK, CQ, CE, ST ^ SI y así sucesivamente.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../adapters-and-accelerators/accelerator-hl7/data-types.md)   
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)