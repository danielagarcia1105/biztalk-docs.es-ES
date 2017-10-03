---
title: "Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de avance (extracción) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c937edd-9524-4f8f-9bd1-68e24f2eebdc
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5d0908593110b04f6e5cd0f5912b66264dc7a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-pull-scenario"></a>Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de avance (extracción)
Antes de comenzar este paso, debe completar [paso 3B: enlazar la orquestación con el puerto de envío dinámico para interactuar almacén y escenario de reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-port-for-interact-scenario.md).  
  
### <a name="to-create-a-test-instance"></a>Para crear una instancia de prueba  
  
1.  Abra un nuevo archivo en un editor de texto, como el Bloc de notas y pegue lo siguiente:  
  
    ```  
    SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
  
    ```  
  
2.  Guarde el archivo con el nombre ExchangeReqSimple.xml.  
  
3.  Abra un nuevo archivo en un editor de texto, como el Bloc de notas y pegue lo siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Sw-ExchangeSnFRequest>  
    <Sw-SnFRequest>  
    <Sw-SnFOpRequest>  
    <Sw-AcquireSnFRequest>  
    <SwInt-Queue>ptsguspp_genericfa!x</SwInt-Queue>  
    <Sw-SessionMode>Pull</Sw-SessionMode>  
    <Sw-ForceAcquire>TRUE</Sw-ForceAcquire>  
    <Sw-OrderBy>FileAct</Sw-OrderBy>  
    <Sw-RecoveryMode>TRUE</Sw-RecoveryMode>  
    </Sw-AcquireSnFRequest>  
    </Sw-SnFOpRequest>  
    </Sw-SnFRequest>  
    </Sw-ExchangeSnFRequest>  
  
    ```  
  
4.  Guarde el archivo con el nombre acquirequeue.xml.  
  
## <a name="see-also"></a>Vea también  
 [El paso 4A: iniciar el servicio SWIFTNet para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)