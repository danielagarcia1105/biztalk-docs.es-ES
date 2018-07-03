---
title: Orquestación de lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2271170d91990e5874168a18ed274c1502a93158
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971597"
---
# <a name="batch-orchestration"></a>Orquestación del lote
Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) proporciona una orquestación (BatchOrchestration.dll) que puede usar para procesar lotes. Esta orquestación puede procesar lotes de mensajes con codificación HL7 (2.X) o la confirmación (ACK). La orquestación es nativo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orquestación agregada [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] de instalación para el conjunto de orquestaciones de BizTalk (como se muestra en las orquestaciones en el Explorador de BizTalk).  
  
 La orquestación funciona con la activación por lotes, la terminación de lotes, y los mensajes de temporizador de lote que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] usa para controlar los lotes. La orquestación también funciona con el puerto de control de proceso por lotes, que es una recepción de puerto que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] programa de instalación instala para controlar los mensajes de control de proceso por lotes.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [Acelerador de BizTalk para componentes de HL7](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)