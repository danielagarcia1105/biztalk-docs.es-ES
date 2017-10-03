---
title: "Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de interactuar | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dffee9a6-5877-4744-9b46-12ca4f8fa959
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3391f966fb1033ec1886f44b62158f910179d72f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-real-time-scenario"></a>Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de interactuar
Antes de comenzar este paso, debe completar [paso 4A: iniciar el SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md).  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>Para iniciar los puertos de envío y puertos de recepción  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk en la que creó los puertos de envío.  
  
3.  Para cada uno de los siguientes puertos de envío, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**:  
  
    -   **Tutorial_IA_SendResponseToReceiver**  
  
    -   **Tutorial_IA_SendResponseToSender**  
  
    -   **Tutorial_IA_SendRequest_RealTime**  
  
4.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk donde se ha creado las ubicaciones de recepción.  
  
5.  Para cada una de las siguientes ubicaciones de recepción, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**:  
  
    -   **Tutorial_IA_InputRequest_RealTime**  
  
    -   **Tutorial_IA_HandleRequestOneWay_RealTime**  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Probar el escenario de extremo a extremo en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [El paso 4A: iniciar el servicio SWIFTNet](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [Paso 4c: crear una instancia de prueba para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)   
 [Paso 4d: probar una instancia válida para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)