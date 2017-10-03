---
title: "Paso 2: Habilitar la orquestación por lotes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4badf807-f461-4d0a-a3b6-9f671e580d91
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f8b18e41aacf61ac4e55e1c8047e9685179656a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-enable-the-batch-orchestration"></a>Paso 2: Habilitar la orquestación del lote
La orquestación del lote controla el proceso por lotes de crear. Mantiene las referencias para todos los mensajes que se incluirá en el lote, controla la transacción por lotes saliente, genera el mensaje de lote, enruta el lote saliente y procesa los lotes entrantes de confirmación. Debe dar de alta la orquestación del lote para el proceso por lotes de crear para que funcione.  
  
### <a name="to-enable-the-batch-orchestration"></a>Para habilitar la orquestación del lote  
  
1.  En la consola de administración de BizTalk, haga clic en **orquestaciones**, haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, haga clic en **propiedades**.  
  
2.  En el cuadro de diálogo Propiedades de orquestación, en el árbol de consola, haga clic en **enlaces**.  
  
3.  En el **enlaces** panel, para **Host**, seleccione **BizTalkServerApplication**. Haga clic en **Aceptar**.  
  
4.  En la consola de administración de BizTalk, haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, haga clic en **dar de alta**.  
  
 Continúe con [paso 3: crear y configurar una entidad de destino](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md).