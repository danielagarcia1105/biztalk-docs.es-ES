---
title: 'Paso 4d: probar una instancia válida para el escenario de avance (extracción) y el almacenamiento de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c7aabe-206f-4b89-b739-ac1e63675451
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf6f53257ff2a9194cf85597d0806780f15c8e52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223700"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-pull-scenario"></a>Paso 4d: probar una instancia válida para el escenario de avance (extracción) y el almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md).  
  
### <a name="to-test-a-valid-instance"></a>Para probar una instancia válida  
  
1.  Coloque el archivo PutReqSimple.xml en **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**.  
  
2.  Compruebe que, tras unos instantes, el archivo PutReqSimple.xml desaparece de la carpeta.  
  
3.  Quitar el fileactcquirequeue.xml de archivo en **C:\SWIFTAdapterTutorial\FileAct\PullRequest**.  
  
4.  Compruebe que el archivo Sample_Put.txt se transfiere desde **C:\SWIFTAdapterTutorial\Fileact\ClientLocation** a **C:\SWIFTAdapterTutorial\Fileact\ServerLocation**, y que las respuestas aparecen en **C:\SWIFTAdapterTutorial\PullResponse**.  
  
## <a name="see-also"></a>Vea también  
 [El paso 4A: iniciar el servicio SWIFTNet para el escenario de avance (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [Paso 4c: crear una instancia de prueba para el escenario de avance (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)