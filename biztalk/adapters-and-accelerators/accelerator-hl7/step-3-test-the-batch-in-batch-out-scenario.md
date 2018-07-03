---
title: 'Paso 3: Probar el proceso por lotes en lote escenario | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c487d39d-b2be-41d4-963e-d0ee9ba169fb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcbbed83d8828aeb7169ea5fcdbe11ad343c353e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999373"
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a>Paso 3: Probar el lote en / escenario de lote
En este paso, probará el lote en / Batch Out tutorial quitar por una instancia de prueba del lote en / mensaje de lotes en una carpeta. El puerto de envío que configuró enviará el mensaje, el puerto de recepción recibirá y la canalización de recepción lo procesará y colóquelo en la carpeta de destino.  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a>Para probar el lote en / escenario de lote  
  
1. Uso de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\< *unidad*\>: \Batching Tutorial\Instances** carpeta.  
  
2. Haga clic en **BatchInBatchOut.txt**y, a continuación, haga clic en **copia**.  
  
3. Vaya a la  **\< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp** carpeta.  
  
4. Haga clic en la carpeta y, a continuación, haga clic en **pegar**.  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a>Para comprobar los resultados del lote en / Tutorial de Batch  
  
- Uso de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_BTAHL7Drop** carpeta. Tras un breve período, debería ver la instancia del mensaje por lotes y una confirmación procesada, aparecen en la carpeta. Si no aparecen, compruebe el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para un mensaje de error. Cada archivo debe tener un nombre diferente en el formulario \< *Guid*\>.txt.  
  
   El primer mensaje debe ser el lote que consta de dos mensajes. Acelerador de BizTalk para HL7 (BTAHL7) ha incluido estos dos mensajes secuencialmente en el archivo txt. Este lote no contiene etiquetas BTS/BHS y FHS/FTS. Un lote debe contener ya sea todas las etiquetas FHS/FTS y BTS/BHS o como este mensaje por lotes, no FHS/FTS y no hay etiquetas BHS/BTS.  
  
  |MSH.9|MSH.10|MSH.3|MSH.5|  
  |-----------|------------|-----------|-----------|  
  |ADT ^ A03|000001|Tutorial_BatchSource|MESA_IS|  
  |ADT ^ A03|000002|Tutorial_BatchSource|MESA_IS|  
  
   El segundo mensaje debe ser una confirmación de la aplicación solo enviada como respuesta al mensaje de lote, con los siguientes campos:  
  
  |MSH.9|MSH.3|MSH.5|MSA.1|MSA.2|  
  |-----------|-----------|-----------|-----------|-----------|  
  |CONFIRMACIÓN ^ A03 ^ ACK|MESA_IS|Tutorial_BatchSource|AA|000001|  
  
## <a name="see-also"></a>Vea también  
 [Parte 1: Escenario de lote de entrada fragmentado](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [Parte 3: Escenario de creación de lote](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)