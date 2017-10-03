---
title: Desensamblador XML y ensamblador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, XML
- assembler, XML
ms.assetid: 242a7a96-2342-4ab5-9d3f-1acbcc7ffd14
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4978484f888290377986ee4ae8bf049c14a1b31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xml-disassembler-and-assembler"></a>Ensamblador y desensamblador XML
El desensamblador XML y el ensamblador de asegurarse de que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) no solo es compatible con mensajes con codificación HL7, pero también admite mensajes XML entrantes o salientes.  
  
## <a name="xml-disassembler"></a>Desensamblador XML  
 El desensamblador XML analiza mensajes XML entrantes en segmentos XML para su procesamiento. A medida que analiza los mensajes, el Desensamblador realiza las tareas siguientes:  
  
-   Identificadores de secuencias de escape  
  
-   Controla las comprobaciones de propiedades obligatorias y opcionales  
  
-   Identificadores declarados segmentos Z  
  
 A medida que analiza los mensajes, el Desensamblador realiza lo siguiente:  
  
-   Validación sintáctica  
  
-   Validación del esquema (si está habilitado)  
  
## <a name="xml-assembler"></a>ensamblador XML.  
 El ensamblador XML serializa los segmentos XML en un mensaje XML saliente. El ensamblador XML admite y crea el siguiente reconocimiento de mensajes (ACK):  
  
-   Estático  
  
-   Modo original  
  
-   Modo mejorado  
  
 El ensamblador XML también tiene la capacidad para enrutar los mensajes de confirmación diferidos.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de BTAHL72XML](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [Acelerador de BizTalk para HL7 componentes](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)