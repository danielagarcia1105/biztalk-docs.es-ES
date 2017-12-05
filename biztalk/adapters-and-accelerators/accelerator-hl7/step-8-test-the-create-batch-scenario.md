---
title: 'Paso 8: Probar el escenario de lote crear | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc7fac40-fd3e-413b-82cc-7ad08226094c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 865717858e27509a9f9e4af611b39ba10be212a5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-8-test-the-create-batch-scenario"></a>Paso 8: Probar el escenario de lote crear
En este paso, para probar el escenario de lote de crear, quitar instancias de prueba de los mensajes que desea procesar por lotes en la carpeta de origen Tutorial_BTAHL7Pickup. El puerto de envío que configuró recoge el mensaje desde la carpeta de origen y lo envía; el puerto de recepción recibe y la canalización de recepción, lo procesa y lo coloca en la carpeta de destino Tutorial_BTAHL7Drop.  
  
### <a name="to-test-the-create-batch-scenario"></a>Para probar el escenario de crear lote  
  
1.  Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\<* unidad*\>: \Batching Tutorial\Instances** carpeta.  
  
2.  Seleccione **CreateBatchMessage1.txt**, y **CreateBatchMessage2.txt**, haga clic en ellos y, a continuación, haga clic en **copia**.  
  
3.  Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\<* unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\ Carpeta Tutorial\Tutorial_BTAHL7Pickup ** SDK\End-to-End.  
  
4.  Haga clic en la carpeta y, a continuación, haga clic en **pegar**.  
  
### <a name="to-verify-the-results-of-the-create-batch-scenario"></a>Para comprobar los resultados del escenario Crear lote  
  
1.  Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\<* unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\ Carpeta Tutorial\Tutorial_BatchACKDrop ** SDK\End-to-End. Tras un breve período, debería ver la instancia procesada del lote de confirmación aparecen en la carpeta. Si no aparece, compruebe el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para los mensajes de error. El archivo debe tener el nombre \< *Guid*\>.txt. Este lote debe contener las dos confirmaciones generadas tras la recepción de los dos mensajes que se enviaron originalmente. Este lote debe tener los siguientes campos:  
  
    |FHS.5|BHS.5|BTS.1|FTS.1|  
    |-----------|-----------|-----------|-----------|  
    |Tutorial_BatchSource|Tutorial_BatchSource|2|1|  
  
     Las confirmaciones dentro del lote deben tener los siguientes campos:  
  
    |MSH.9|MSA.2|MSA.1|MSH.3|MSH.5|  
    |-----------|-----------|-----------|-----------|-----------|  
    |CONFIRMACIÓN ^ A03 ^ CONFIRMACIÓN|Msg01|AA|Tutorial_BatchDest|Tutorial_BatchSource|  
    |CONFIRMACIÓN ^ A03 ^ CONFIRMACIÓN|Msg02|AA|Tutorial_BatchDest|Tutorial_BatchSource|  
  
2.  Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\<* unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\ Carpeta Tutorial\Tutorial_BatchMsgDrop ** SDK\End-to-End. Después de una hora, debería ver la instancia procesada del lote de mensajes aparecen en la carpeta. Si no aparece, compruebe el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para los mensajes de error. El archivo debe tener el nombre \< *Guid*\>.txt. Este lote debe contener los dos mensajes que se enviaron originalmente. Este lote debe tener los siguientes campos:  
  
    |FHS.5|BHS.5|BTS.1|FTS.1|  
    |-----------|-----------|-----------|-----------|  
    |Tutorial_BatchDest|Tutorial_BatchDest|2|1|  
  
     Los mensajes dentro del lote deben tener los siguientes campos:  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT ^ A03|Msg01|Tutorial_BatchSource|Tutorial_BatchDest|  
    |ADT ^ A03|Msg02|Tutorial_BatchSource|Tutorial_BatchDest|  
  
     El lote se ajusta en dos conjuntos de encabezados y finalizadores específicos de lotes:  
  
    -   Un encabezado de archivo y el finalizador (FHS y ft), que se utiliza para adjuntar un archivo que puede incluir varios lotes. Tenga en cuenta la aplicación de recepción de archivo (**Tutorial_BatchDest**) en el campo FHS5 y la creación del archivo fecha y hora en FHS7. Tenga en cuenta el número de lotes de archivos (el número de lotes en el archivo) en FTS2 (1).  
  
    -   Un lote encabezado y finalizador (BHS y BTS), que se utilizan para delimitar cada lote. Tenga en cuenta el archivo que recibe la aplicación y lote fecha/hora de creación, como en el FHS y el número de mensajes por lotes (2) en BTS2.  
  
## <a name="see-also"></a>Vea también  
 [Parte 1: Escenario de fragmentados por lotes entrantes](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [Parte 3: Escenario de creación de lote](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)