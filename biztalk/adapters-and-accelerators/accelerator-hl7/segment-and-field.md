---
title: Segmento y el campo | Documentos de Microsoft
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
ms.openlocfilehash: 6ca948748bc30f8c8a56f7c257b775b37a990625
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206484"
---
# <a name="segment-and-field"></a>Segmento y el campo
Una tabla de segmento define un segmento de HL7. Cada definición de segmento sigue el patrón que se muestra a continuación.  
  
|SEQ|LEN|DT|PARTICIPACIÓN|RP / #|TBL #|ELEMENTO #|NOMBRE DEL ELEMENTO|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1|4|SI|O|||00104|Establecer Id.: PID|  
|2|20|CX|B|||00105|Id. de pacientes|  
|3|250|CX|L|S||00106|Lista de identificadores de pacientes|  
|4|20|CX|B|S||00107|Identificador del paciente alternativo - PID|  
|5|250|XPN|L|S||00108|Nombre del paciente|  
|..||||||||  
|..||||||||  
|37|80|ST|O|||01541|Demanda|  
|38|250|CE|O|2|0429|01542|Código de la clase de producción|  
  
 HL7 también incluye las definiciones de texto para cada campo. La etiqueta de segmento de tres caracteres y el número de secuencia identifican cada campo dentro de un segmento. Por ejemplo, en el caso del segmento de identificación del paciente, la etiqueta PID y el número de secuencia "5" identifican el campo nombre del paciente. La documentación de codificación y la interfaz XML usan esta convención para identificar los campos de segmentos. La definición de segmento también incluye la declaración de tipos de datos para cada campo, así como el número de tabla que se aplica a elementos codificados.  
  
 En las nuevas versiones, sólo puede agregar campos al final de un segmento y no se puede quitar campos. Si un campo agregado reemplaza la funcionalidad de un campo existente, el primer campo permanece por compatibilidad con versiones anteriores. (Esto puede verse mediante la "B" en la columna opcionalmente anteriormente para PID.2 y PID.3.)  
  
 Las siguientes funciones de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) compatible con estos requisitos:  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]es compatible con los segmentos estándares para todas las versiones de HL7 desde V2.1 en.  
  
-   Al crear especificaciones de la interfaz e implementar interfaces, puede etiquetar campos que son opcionales en el estándar como obligatoria o no es compatible, en función de los requisitos funcionales.  
  
-   Puede crear Z segmentos cuando sea necesario para la localización.  
  
-   Puede volver a definir la semántica de los campos o agregar campos a segmentos cuando sea necesario para la localización. Tenga en cuenta que este se encuentra bajo el encabezado de localización no legítimo. Sin embargo, en algunos casos se necesita esta funcionalidad para admitir interfaces heredadas o a sistemas heredados.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)