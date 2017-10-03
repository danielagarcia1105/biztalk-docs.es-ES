---
title: "Paso 4d: probar una instancia válida para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f47b1fd-a4ef-4b1d-812a-8c2fa946f98c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21ee5e3fb8c44825bab039e1066184881a62d998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario"></a>Paso 4d: probar una instancia válida para el escenario de reenvío y almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el escenario al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md).  
  
### <a name="to-test-a-valid-instance"></a>Para probar una instancia válida  
  
1.  Coloque el archivo PutReqSimple.xml en C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF.  
  
2.  Compruebe que, tras unos instantes, el archivo PutReqSimple.xml desaparece de la carpeta.  
  
3.  Compruebe que el archivo Sample_Put.txt se transfiere desde C:\SWIFTAdapterTurorial\Fileact\ClientLocation C:\SWIFTAdapterTutorial\Fileact\ServerLocation y que las respuestas aparecen en C:\SWIFTAdapterTutorial\ResponseServer.  
  
4.  Compruebe la carpeta de eventos (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) de estado para los tres mensajes HandleFileEventRequest. Estos mensajes deben contener los siguientes estados de transferencia:  
  
     Mensaje de HandleFileEventRequest\<Sw-TransferStatus > aceptado\</Sw-TransferStatus >  
  
     Mensaje de HandleFileEventRequest \<Sw-TransferStatus > inició\</Sw-TransferStatus >  
  
     Mensaje de HandleFileEventRequest \<Sw-TransferStatus > completado\</Sw-TransferStatus >  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Probar el escenario de reenvío-to-End y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)   
 [El paso 4A: iniciar el servicio SWIFTNet para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)   
 [Paso 4c: crear una instancia de prueba para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)