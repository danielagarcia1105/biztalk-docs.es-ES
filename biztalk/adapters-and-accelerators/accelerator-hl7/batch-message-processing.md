---
title: Procesamiento de mensajes por lotes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, batching
- batching, examples
- batching, batch types
ms.assetid: 264f91b5-3e33-4b87-9da3-866eaa464b0f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aad80bb8fe9a59163ee17e7862bece728fdc52b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="batch-message-processing"></a>Procesamiento de mensajes por lotes
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) controla tres tipos de HL7 2.X escenarios de lote:  
  
-   Escenario de fragmentados por lotes entrantes. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]estos lotes se analiza en mensajes de salida independientes. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]envía la confirmación (ACK) para cada mensaje en un lote fragmentado.  
  
-   Procesar por lotes en / lote escenario. Se trata de entrada que procesa por lotes [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no fragmentar, pero pasa a través y envía un lote intactos. Si [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación para el lote, la confirmación incluye un identificador de versión.  
  
-   Escenario de lote crear. En este escenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] combina separar los mensajes de entrada en un lote de salida.  
  
 Puede dar formato a los lotes de dos maneras:  
  
-   Con un encabezado de archivo y finalizador (FHS/FTS) y un lote encabezado y finalizador (BHS/BTS).  
  
-   Con ningún archivo o proceso por lotes encabezados/finalizadores.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento por lotes de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
 [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [Parte 1: Escenario de fragmentados por lotes entrantes](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [Parte 2: Lote / escenario de lote](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [Parte 3: Escenario de lote crear](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)