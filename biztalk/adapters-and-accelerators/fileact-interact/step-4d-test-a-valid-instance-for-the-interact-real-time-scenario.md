---
title: "Paso 4d: probar una instancia válida para el escenario en tiempo real de interactuar | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e163c3ac-a00d-40cf-b1b8-4a38f74ab0e8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94bdb2acd8147ec5041df7d6a1c4324ca833d9e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-real-time-scenario"></a>Paso 4d: probar una instancia válida para el escenario en tiempo real de interactuar
Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el escenario de en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md).  
  
### <a name="to-test-a-valid-instance"></a>Para probar una instancia válida  
  
1.  Coloque el archivo ExchangeReqSimple.xml en C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime.  
  
2.  Compruebe que, tras unos instantes, el archivo ExchangeReqSimple.xml desaparece de la carpeta.  
  
3.  Vaya a C:\SWIFTAdapterTutorial\Interact\HandleRequest para ver el mensaje de solicitud de identificador, Sw:HandleRequest.  
  
4.  Vaya a C:\SWIFTAdapterTutorial\Interact\Response para ver el mensaje de respuesta de identificador, Sw:HandleResponse.  
  
5.  Abra el mensaje de Sw:HandleRequest en un editor de texto, como el Bloc de notas y compruebe que la sección de carga es el mismo que el archivo ExchangeReqSimple.xml.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Probar el escenario de extremo a extremo en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [El paso 4A: iniciar el servicio SWIFTNet](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)   
 [Paso 4c: crear una instancia de prueba para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)