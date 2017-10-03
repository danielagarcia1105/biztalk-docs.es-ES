---
title: 'Paso 3: Probar el lote en lote escenario | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c487d39d-b2be-41d4-963e-d0ee9ba169fb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eec20b86b3e921fba8d1636a0aab7803ec1615d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a>Paso 3: Probar el lote / escenario de lote
En este paso, comprobará que el lote en / lote Out tutorial quitar por una instancia de prueba del lote en / lote mensaje en una carpeta. El puerto de envío que configuró enviará el mensaje, el puerto de recepción recibirá y la canalización de recepción lo procesará y lo coloque en la carpeta de destino.  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a>Para probar el lote en / escenario de lote  
  
1.  Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\<* unidad*>: \Batching Tutorial\Instances** carpeta.  
  
2.  Haga clic en **BatchInBatchOut.txt**y, a continuación, haga clic en **copia**.  
  
3.  Vaya a la  **\<* unidad*>: \Program BizTalk \<versión > Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp ** carpeta.  
  
4.  Haga clic en la carpeta y, a continuación, haga clic en **pegar**.  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a>Para comprobar los resultados del lote en / lote tutorial  
  
-   Usando [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\<* unidad*>: \Program BizTalk \<versión > Accelerator for Tutorial\ HL7\SDK\End-to-End Tutorial_BTAHL7Drop ** carpeta. Tras un breve período, debe ver la instancia del mensaje por lotes y una confirmación procesada, aparecen en la carpeta. Si no aparecen, compruebe el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para un mensaje de error. Cada archivo debe tener un nombre diferente en el formulario \< *Guid*> .txt.  
  
     El primer mensaje debe ser el lote que consta de dos mensajes. Acelerador de BizTalk para HL7 (BTAHL7) se incluyen estos dos mensajes secuencialmente en el archivo .txt. Este lote no contiene etiquetas BHS/BTS y FHS/FT. Un lote debe contener cualquier todas las etiquetas FHS/FT y BHS/BTS o como este mensaje por lotes, no FHS/FT y sin etiquetas BHS/BTS.  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT ^ A03|000001|Tutorial_BatchSource|MESA_IS|  
    |ADT ^ A03|000002|Tutorial_BatchSource|MESA_IS|  
  
     El segundo mensaje debe ser una confirmación de aplicación único enviada como respuesta al mensaje por lotes, con los siguientes campos:  
  
    |MSH.9|MSH.3|MSH.5|MSA.1|MSA.2|  
    |-----------|-----------|-----------|-----------|-----------|  
    |CONFIRMACIÓN ^ A03 ^ CONFIRMACIÓN|MESA_IS|Tutorial_BatchSource|AA|000001|  
  
## <a name="see-also"></a>Vea también  
 [Parte 1: Escenario de fragmentados por lotes entrantes](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [Parte 3: Escenario de lote crear](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)