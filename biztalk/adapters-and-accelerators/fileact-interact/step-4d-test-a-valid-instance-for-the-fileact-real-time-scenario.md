---
title: "Paso 4d: pruebe una instancia válida para el escenario en tiempo real de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8975c90-462b-4c9b-8766-1272ab7ceaba
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 906a7eb08dc7542d7fa383aeb9035c0a5536cff3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario"></a>Paso 4d: pruebe una instancia válida para el escenario en tiempo real de FileAct
Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md).  
  
### <a name="to-test-a-valid-instance"></a>Para probar una instancia válida  
  
1.  Coloque el archivo PutReqSimple.xml en C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime.  
  
2.  Compruebe que, tras unos instantes, el archivo PutReqSimple.xml desaparece de la carpeta.  
  
3.  Compruebe que el archivo Sample_Put.txt se transfiere desde: C:\SWIFTAdapterTutorial\Fileact\ClientLocation a C:\SWIFTAdapterTutorial\Fileact\ServerLocation y que las respuestas aparecen en C:\SWIFTAdapterTutorial\Fileact\ResponseClient y C:\ SWIFTAdapterTutorial\Fileact\ResponseServer.  
  
4.  Compruebe la carpeta de eventos (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) de estado para los tres mensajes HandleFileEventRequest. Estos mensajes deben contener los siguientes estados de transferencia:  
  
     Mensaje de HandleFileEventRequest\<Sw-TransferStatus\>aceptado\</Sw-TransferStatus\>  
  
     Mensaje de HandleFileEventRequest \<Sw-TransferStatus\>inició\</Sw-TransferStatus\>  
  
     Mensaje de HandleFileEventRequest \<Sw-TransferStatus\>completado\</Sw-TransferStatus\>  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Probar el escenario de extremo a extremo en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [El paso 4A: iniciar el servicio SWIFTNet para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)   
 [Paso 4C: Crear una instancia de prueba para el escenario de FileAct en tiempo real](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)