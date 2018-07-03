---
title: 'Paso 2: Habilitar la orquestación por lotes | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4badf807-f461-4d0a-a3b6-9f671e580d91
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b44dd71c44f2510b6ccd80a731dd21739ed7055
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996173"
---
# <a name="step-2-enable-the-batch-orchestration"></a>Paso 2: Habilitar la orquestación del lote
La orquestación del lote controla el proceso por lotes de crear. Mantiene las referencias de todos los mensajes que se incluirán en el lote, controla la transacción por lotes saliente, genera el mensaje de lote, enruta el lote saliente y procesa por lotes confirmación entrantes. Deberá dar de alta la orquestación del lote para el proceso por lotes de crear para que funcione.  
  
### <a name="to-enable-the-batch-orchestration"></a>Para habilitar la orquestación del lote  
  
1. En la consola de administración de BizTalk, haga clic en **orquestaciones**, haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, haga clic en **propiedades**.  
  
2. En el cuadro de diálogo Propiedades de orquestación, en el árbol de consola, haga clic en **enlaces**.  
  
3. En el **enlaces** panel, para **Host**, seleccione **BizTalkServerApplication**. Haga clic en **Aceptar**.  
  
4. En la consola de administración de BizTalk, haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, haga clic en **Enlist**.  
  
   Continúe con [paso 3: crear y configurar una entidad de destino](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md).