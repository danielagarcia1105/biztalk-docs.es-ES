---
title: 'Paso 8: Probar el escenario de creación de lote | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc7fac40-fd3e-413b-82cc-7ad08226094c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d880d1f9d586878a28803ef5060cfb770bf67a7d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007813"
---
# <a name="step-8-test-the-create-batch-scenario"></a>Paso 8: Probar el escenario de creación de lote
En este paso, probará el escenario de lote crear colocando las instancias de prueba de los mensajes que desea que procese por lotes en la carpeta de origen Tutorial_BTAHL7Pickup. El puerto de envío que configuró recoge el mensaje de la carpeta de origen y lo envía; el puerto de recepción recibe y la canalización de recepción, lo procesa y lo coloca en la carpeta de destino Tutorial_BTAHL7Drop.  

### <a name="to-test-the-create-batch-scenario"></a>Para probar el escenario de creación de lote  

1. Uso de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\< *unidad*\>: \Batching Tutorial\Instances** carpeta.  

2. Seleccione **CreateBatchMessage1.txt**, y **CreateBatchMessage2.txt**, haga clic en ellos y, a continuación, haga clic en **copia**.  

3. Uso de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_BTAHL7Pickup** carpeta.  

4. Haga clic en la carpeta y, a continuación, haga clic en **pegar**.  

### <a name="to-verify-the-results-of-the-create-batch-scenario"></a>Para comprobar los resultados del escenario de creación de lote  

1. Uso de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_BatchACKDrop** carpeta. Tras un breve período, debería ver que la instancia del lote de confirmación procesada aparecen en la carpeta. Si no aparece, compruebe el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para los mensajes de error. El archivo debe tener el nombre \< *Guid*\>.txt. Este lote debe contener las dos confirmaciones que se genera tras la recepción de los dos mensajes que se enviaron originalmente. Este lote debe tener los siguientes campos:  

   |FHS.5|BHS.5|BTS.1|FTS.1|  
   |-----------|-----------|-----------|-----------|  
   |Tutorial_BatchSource|Tutorial_BatchSource|2|1|  

    Las confirmaciones en el lote deben tener los siguientes campos:  


   |    MSH.9    | MSA.2 | MSA.1 |       MSH.3        |        MSH.5         |
   |-------------|-------|-------|--------------------|----------------------|
   | CONFIRMACIÓN ^ A03 ^ ACK | Msg01 |  AA   | Tutorial_BatchDest | Tutorial_BatchSource |
   | CONFIRMACIÓN ^ A03 ^ ACK | Msg02 |  AA   | Tutorial_BatchDest | Tutorial_BatchSource |


2. Uso de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la  **\< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_BatchMsgDrop** carpeta. Después de una hora, debería ver que la instancia del lote procesada aparecen en la carpeta. Si no aparece, compruebe el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para los mensajes de error. El archivo debe tener el nombre \< *Guid*\>.txt. Este lote debe contener los dos mensajes que se enviaron originalmente. Este lote debe tener los siguientes campos:  

   |FHS.5|BHS.5|BTS.1|FTS.1|  
   |-----------|-----------|-----------|-----------|  
   |Tutorial_BatchDest|Tutorial_BatchDest|2|1|  

    Los mensajes dentro del lote deben tener los siguientes campos:  

   |MSH.9|MSH.10|MSH.3|MSH.5|  
   |-----------|------------|-----------|-----------|  
   |ADT ^ A03|Msg01|Tutorial_BatchSource|Tutorial_BatchDest|  
   |ADT ^ A03|Msg02|Tutorial_BatchSource|Tutorial_BatchDest|  

    El lote se encapsula en dos conjuntos de encabezados y finalizadores específicos de lotes:  

   -   Un archivo encabezado y finalizador (FHS y ft), que se usan para incluir un archivo que puede incluir varios lotes. Tenga en cuenta la aplicación de recepción de archivo (**Tutorial_BatchDest**) en el campo FHS5 y la creación del archivo fecha y hora en FHS7. Tenga en cuenta el número de lotes de archivos (el número de lotes en el archivo) en FTS2 (1).  

   -   Un lote encabezado y finalizador (BHS y BTS), que se utilizan para delimitar cada lote. Tenga en cuenta el archivo que recibe la aplicación y por lotes fecha y hora de creación, como se muestra en el FHS y el número de mensajes por lotes (2) en BTS2.  

## <a name="see-also"></a>Vea también  
 [Parte 1: Escenario de lote de entrada fragmentado](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [Parte 3: Escenario de creación de lote](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)