---
title: "Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de avance (extracción) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00ab119d-ed44-4f4a-84ea-20f2c41e5a92
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b747c76b30b9f7d04bef379be9eaccaaeca063ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-pull-scenario"></a>Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de avance (extracción)
Antes de comenzar este paso, debe completar[paso 4: probar el almacén de interacción y hacia delante de un extremo a otro escenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md).  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>Para iniciar los puertos de envío y puertos de recepción  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk en la que creó los puertos de envío.  
  
3.  Para cada uno de los siguientes puertos de envío, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**:  
  
    -   **Tutorial_ IA_SendPullResponseToReceiver**  
  
    -   **Tutorial_IA_SendRequest_SnF**  
  
    -   **Tutorial_IA_DynamicSendPort**  
  
4.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk donde se ha creado las ubicaciones de recepción.  
  
5.  Para cada una de las siguientes ubicaciones de recepción, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**:  
  
    -   **Tutorial_IA_InputRequest_SnF**  
  
    -   **Tutorial_ IA_InputRequest_PullMode**  
  
## <a name="see-also"></a>Vea también  
 [El paso 4A: iniciar el servicio SWIFTNet para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)   
 [Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)