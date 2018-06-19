---
title: 'Paso 4c: crear una instancia de prueba para el escenario de avance (extracción) y el almacenamiento de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50fc72f0-ec00-46f9-b24b-fe8d5e5079ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c991dd980df9e19f036b3872289f9d0d8aa82d6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223860"
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-pull-scenario"></a>Paso 4c: crear una instancia de prueba para el escenario de avance (extracción) y el almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md).  
  
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
  
    > [!NOTE]
    >  Debe reemplazar *PhysicalFolderName %* con el nombre real de la carpeta que has configurado en el FILEACT la ubicación de recepción.  
  
2.  Guarde el archivo con el nombre ExchangeReqSimple.xml.  
  
3.  Abra un nuevo archivo en un editor de texto, como el Bloc de notas y pegue lo siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Sw-ExchangeSnFRequest>  
    <Sw-SnFRequest>  
    <Sw-SnFOpRequest>  
    <Sw-AcquireSnFRequest>  
    <SwInt-Queue Type the queue name, based on your provisioning with SWIFT </SwInt-Queue>  
    <Sw-SessionMode>Pull</Sw-SessionMode>  
    <Sw-ForceAcquire>TRUE</Sw-ForceAcquire>  
    <Sw-OrderBy>InterAct</Sw-OrderBy>  
    <Sw-RecoveryMode>TRUE</Sw-RecoveryMode>  
    </Sw-AcquireSnFRequest>  
    </Sw-SnFOpRequest>  
    </Sw-SnFRequest>  
    </Sw-ExchangeSnFRequest>  
  
    ```  
  
4.  Guarde el archivo con el nombre acquirequeue.xml.  
  
## <a name="see-also"></a>Vea también  
 [El paso 4A: iniciar el servicio SWIFTNet para el escenario de avance (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [Paso 4d: probar una instancia válida para el escenario de avance (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)