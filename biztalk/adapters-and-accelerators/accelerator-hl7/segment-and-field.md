---
title: Segmento y campo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- segments, messages
ms.assetid: e68864e6-590c-47f3-8c9e-81831aec2642
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbe45a252b650bd3b5f4d2990d0c66e5a54e1e07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985109"
---
# <a name="segment-and-field"></a>Segmento y campo
Una tabla de segmento define un segmento de HL7. Cada definición de segmento sigue el patrón que se muestra a continuación.  
  
|SEQ|LEN|DT|PARTICIPAR|RP / #|TBL #|ELEMENTO #|NOMBRE DEL ELEMENTO|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1|4|SI|O|||00104|Establecer PID de Id.:|  
|2|20|CX|B|||00105|Id. de pacientes|  
|3|250|CX|R|S||00106|Lista de identificador de paciente|  
|4|20|CX|B|S||00107|Identificador de paciente alternativo - PID|  
|5|250|XPN|R|S||00108|Nombre del paciente|  
|.||||||||  
|.||||||||  
|37|80|ST|O|||01541|Presión|  
|38|250|CE|O|2|0429|01542|Código de la clase de producción|  
  
 HL7 también incluye las definiciones de texto para cada campo. La etiqueta de segmento de tres caracteres y el número de secuencia identifican de forma única cada campo dentro de un segmento. Por ejemplo, en el caso del segmento de identificación del paciente, la etiqueta PID y el número de secuencia "5" identifican de forma exclusiva el campo nombre del paciente. La documentación XML, codificación y la interfaz ambos usan esta convención para identificar los campos de segmentos. La definición de segmento también incluye la declaración de tipos de datos para cada campo, así como el número de tabla que se aplica a elementos codificados.  
  
 En las nuevas versiones, sólo puede agregar campos al final de un segmento y no se puede quitar campos. Si un campo agregado reemplaza la funcionalidad de un campo existente, sigue siendo el primer campo por razones de compatibilidad. (Esto se puede ver en la "B" en la columna opcionalmente anterior para PID.2 y PID.3.)  
  
 Las siguientes funciones del Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admiten estos requisitos:  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] es compatible con los segmentos estándares para todas las versiones de HL7 desde V2.1 en.  
  
- Cuando las especificaciones de la interfaz de construir e implementar interfaces, puede etiquetar los campos que son opcionales en el estándar como obligatorio o no es compatible, según los requisitos funcionales.  
  
- Puede crear Z segmentos donde sea necesario para la localización.  
  
- Puede volver a definir la semántica de los campos o agregar campos a segmentos donde sea necesario para la localización. Tenga en cuenta que este se encuentra bajo el encabezado de localización ilegítimo. Sin embargo, en algunos casos, se necesita esta funcionalidad para admitir las interfaces heredadas o a sistemas heredados.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)