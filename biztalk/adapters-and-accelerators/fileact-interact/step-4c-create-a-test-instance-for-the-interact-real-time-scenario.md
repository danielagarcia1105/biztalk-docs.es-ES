---
title: 'Paso 4c: crear una instancia de prueba para el escenario en tiempo real de interactuar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3557acdc-eb3f-4c70-b64a-3f523a1ba650
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c0035074eba0eec6994aa7ab024afbcec10984
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224420"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-real-time-scenario"></a>Paso 4c: crear una instancia de prueba para el escenario en tiempo real de interactuar
Antes de comenzar este paso, debe completar [paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md).  
  
### <a name="to-create-a-test-instance"></a>Para crear una instancia de prueba  
  
1.  Abra un nuevo archivo en un editor de texto, como el Bloc de notas y pegue lo siguiente:  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  Guarde el archivo con el nombre **ExchangeReqSimple.xml**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Probar el escenario de extremo a extremo en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [El paso 4A: iniciar el servicio SWIFTNet](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)   
 [Paso 4d: probar una instancia válida para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)