---
title: Desensamblador XML y ensamblador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, XML
- assembler, XML
ms.assetid: 242a7a96-2342-4ab5-9d3f-1acbcc7ffd14
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d8dfaf91d9b0d3d058c4d3e31cd67c652235eff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983045"
---
# <a name="xml-disassembler-and-assembler"></a>Ensamblador y desensamblador XML
El desensamblador XML y el ensamblador de asegurarse de que el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) no solo es compatible con los mensajes codificados en HL7, pero también admite mensajes XML entrantes o salientes.  
  
## <a name="xml-disassembler"></a>Desensamblador XML  
 El desensamblador XML analiza los mensajes XML entrantes en segmentos XML para su procesamiento. A medida que analiza los mensajes, el Desensamblador realiza las siguientes tareas:  
  
- Identificadores de secuencias de escape  
  
- Controla las comprobaciones de propiedades obligatorias y opcionales  
  
- Identificadores declarados segmentos de Z  
  
  A medida que analiza los mensajes, el Desensamblador realiza lo siguiente:  
  
- Validación sintáctica  
  
- Validación del esquema (si está habilitado)  
  
## <a name="xml-assembler"></a>ensamblador XML.  
 El ensamblador XML serializa los segmentos XML en un mensaje XML saliente. El ensamblador XML admite y crea la siguiente confirmación de mensajes (ACK):  
  
- Estático  
  
- Modo original  
  
- Modo mejorado  
  
  El ensamblador XML también tiene la capacidad para enrutar los mensajes de confirmación diferidos.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de BTAHL72XML](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [Acelerador de BizTalk para componentes de HL7](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)