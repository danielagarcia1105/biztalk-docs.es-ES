---
title: HL7 Desensamblador y ensamblador | Documentos de Microsoft
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
ms.openlocfilehash: e81d621656fc678196f7f6fb709b29de87a3aaf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204932"
---
# <a name="hl7-disassembler-and-assembler"></a>HL7 Desensamblador y ensamblador
El Desensamblador de HL7 y de ensamblador proporcionan compatibilidad para mensajes con codificación HL7. Puesto que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] procesa los mensajes de forma nativa en formato XML, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) usa el Desensamblador de HL7 y de ensamblador para realizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] un motor de integración de HL7.  
  
## <a name="hl7-disassembler"></a>Desensamblador de HL7  
 El Desensamblador de HL7 analiza los mensajes entrantes con codificación HL7 en segmentos XML para su procesamiento. Realiza la validación del encabezado del mensaje y una validación básica del cuerpo. Determina el esquema que usa para analizar el mensaje HL7 (vea [determinación del esquema en el HL7 2.X Desensamblador](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)), determina la entidad de origen para el mensaje y lleva a cabo una validación adicional del cuerpo (si habilitado para el entidad).  
  
## <a name="hl7-assembler"></a>Ensamblador de HL7  
 El ensamblador de HL7 serializa los segmentos XML en un mensaje saliente de HL7. Determina el esquema que utiliza para serializar el mensaje HL7 (vea [determinación del esquema en el HL7 2.X ensamblador](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)), determina la entidad de destino para el mensaje y realiza la validación del cuerpo (si está habilitado para la entidad).  
  
 El ensamblador puede serializar los mensajes de confirmación (ACK) siguientes:  
  
-   Estático  
  
-   Modo original  
  
-   Modo mejorado  
  
 El ensamblador de HL7 también tiene la capacidad de enrutar los mensajes de confirmación diferidos.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de archivo sin formato BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [Acelerador de BizTalk para HL7 componentes](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)