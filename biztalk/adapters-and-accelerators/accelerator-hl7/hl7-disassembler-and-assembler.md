---
title: HL7 Desensamblador y ensamblador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, HL7
- disassembler, HL7
ms.assetid: 54e83a04-86c8-482f-bea3-dbbdeb4584d6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d603e74defeac983b1287f16c7f562b706b8c54d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994997"
---
# <a name="hl7-disassembler-and-assembler"></a>HL7 Desensamblador y ensamblador
El Desensamblador HL7 y ensamblador proporcionan compatibilidad para mensajes con codificación HL7. Desde Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] procesa los mensajes de forma nativa en formato XML, el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) utiliza el Desensamblador HL7 y ensamblador para realizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] un motor de integración de HL7.  
  
## <a name="hl7-disassembler"></a>Desensamblador HL7  
 El Desensamblador HL7 analiza los mensajes entrantes con codificación HL7 en segmentos XML para su procesamiento. Realiza la validación del encabezado del mensaje y la validación básica del cuerpo. Lo determina el esquema que usa para analizar el mensaje de HL7 (vea [determinación del esquema en el HL7 2.X Desensamblador](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)), determina la entidad de origen para el mensaje y lleva a cabo una validación adicional del cuerpo (si habilitada para el la entidad).  
  
## <a name="hl7-assembler"></a>Ensamblador de HL7  
 El ensamblador HL7 serializa los segmentos XML en un mensaje saliente de HL7. Determina el esquema que usa para serializar el mensaje de HL7 (consulte [determinación del esquema en el HL7 2.X ensamblador](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)), determina la entidad de destino para el mensaje y realiza la validación del cuerpo (si está habilitado para la entidad).  
  
 El ensamblador puede serializar los mensajes de confirmación (ACK) siguiente:  
  
- Estático  
  
- Modo original  
  
- Modo mejorado  
  
  El ensamblador HL7 también tiene la capacidad para enrutar los mensajes de confirmación diferidos.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de archivos planos BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [Acelerador de BizTalk para componentes de HL7](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)