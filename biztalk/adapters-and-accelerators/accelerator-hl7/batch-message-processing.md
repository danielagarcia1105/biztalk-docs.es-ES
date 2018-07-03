---
title: Procesamiento de mensajes por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, batching
- batching, examples
- batching, batch types
ms.assetid: 264f91b5-3e33-4b87-9da3-866eaa464b0f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75cde12720ac67d74396c22282bddaf53e015960
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972373"
---
# <a name="batch-message-processing"></a>Procesamiento de mensajes por lotes
Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) controla tres tipos de HL7 2.X escenarios de batch:  
  
- Escenario de lote de entrada fragmentado. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analiza estos lotes en los mensajes de salida independientes. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía la confirmación (ACK) para cada mensaje en un lote fragmentado.  
  
- Procesar por lotes en / lote escenario. Se trata de en enlace procesa por lotes que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no fragmentar, pero pasa y envía como un lote intacto. Si [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación para el lote, la confirmación incluye un identificador de versión.  
  
- Escenario de creación de lote. En este escenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] combina distintos mensajes de entrada en un lote de salida.  
  
  Puede dar formato a los lotes de dos maneras:  
  
- Con un encabezado de archivo y finalizador (FHS/FTS) y un lote encabezado y finalizador (BHS/BTS).  
  
- Con ningún archivo o proceso por lotes encabezados/finalizadores.  
  
## <a name="see-also"></a>Vea también  
 [Mensaje de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
 [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [Parte 1: Escenario de lote de entrada fragmentado](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [Parte 2: Proceso por lotes en / escenario de lote](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [Parte 3: Escenario de creación de lote](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)