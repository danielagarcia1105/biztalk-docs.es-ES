---
title: "Orquestación de lote | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, acknowledgements
- acknowledgements, batching
- batch orchestration
- orchestrations, batch orchestration
- messages, batching
- batching, batch orchestration
- batching, messages
ms.assetid: b449d8d5-72a2-46c8-a2b1-380431175f4d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9db6ee8b4fd3dec8e2902642634b701889866cf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="batch-orchestration"></a>Orquestación del lote
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) proporciona una orquestación (BatchOrchestration.dll) que puede usar para procesar lotes. Esta orquestación puede procesar lotes de mensajes con codificación HL7 (2.X) o confirmaciones (ACK). La orquestación es nativo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orquestación agregada por [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el programa de instalación para el conjunto de orquestaciones de BizTalk (como se muestra en las orquestaciones en el Explorador de BizTalk).  
  
 La orquestación funciona con la activación por lotes, la terminación de lotes, y los mensajes de temporizador de lote que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] usa para controlar los lotes. La orquestación también funciona con el puerto de control de lote, que es una operación de recepción que el puerto [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] programa de instalación instala para controlar los mensajes de control de lote.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [Acelerador de BizTalk para HL7 componentes](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)