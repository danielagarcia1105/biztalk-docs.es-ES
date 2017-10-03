---
title: 'Paso 4c: crear una instancia de prueba para el escenario en tiempo real de FileAct | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80e0cb59-8b4f-4273-a7a4-db3446008061
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04952616f1b49eb30b4eb00462e4e5295ade0cfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-real-time-scenario"></a>Paso 4c: crear una instancia de prueba para el escenario en tiempo real de FileAct
Antes de comenzar este paso, debe completar [paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md).  
  
### <a name="to-create-a-test-instance"></a>Para crear una instancia de prueba  
  
1.  Abra un nuevo archivo en un editor de texto, como el Bloc de notas y pegue lo siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Sw-ExchangeFileRequest>  
    <Sw-FileRequest>  
    <Sw-FileOpRequest>  
    <Sw-PutFileRequest>  
    <Sw-PhysicalName>%PhysicalFolderName%\sample_put.txt</Sw-PhysicalName>  
    </Sw-PutFileRequest>  
    </Sw-FileOpRequest>  
    </Sw-FileRequest>  
    </Sw-ExchangeFileRequest>  
    ```  
  
2.  Guarde el archivo con el nombre "PutReqSimple.xml".  
  
3.  Asegúrese de que el archivo (Sample_put.txt) se encuentra en la carpeta de ubicación del cliente.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Probar el escenario de extremo a extremo en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [El paso 4A: iniciar el servicio SWIFTNet para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)   
 [Paso 4d: pruebe una instancia válida para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)