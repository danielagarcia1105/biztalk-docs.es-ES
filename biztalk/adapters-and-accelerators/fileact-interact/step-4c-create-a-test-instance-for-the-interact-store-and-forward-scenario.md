---
title: 'Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64a69dcc-d307-47c0-87e8-b0cb2a4d655b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44addc30191dd9541d7f5964a3de0eec244c9993
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225164"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario"></a>Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de reenvío
Antes de comenzar este paso, debe completar [paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y reenviar escenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md).  
  
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
  
2.  Guarde el archivo con el nombre ExchangeReqSimple.xml.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Probar el almacén de interacción y el escenario de reenvío-to-End](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)   
 [El paso 4A: iniciar el servicio SWIFTNet para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)   
 [Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)