---
title: "Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de avance (extracción) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c2933d0-bbe3-4486-832e-5009b2d760ac
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9c8ea24eeb5541cf84448363ca91fcb8171f19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-pull-scenario"></a>Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de avance (extracción)
Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md).  
  
### <a name="to-test-a-valid-instance"></a>Para probar una instancia válida  
  
1.  Coloque el archivo ExchangeReqSimple.xml en c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF.  
  
2.  Compruebe que, tras unos instantes, el archivo ExchangeReqSimple.xml desaparece de la carpeta.  
  
3.  Coloque el archivo acquirequeue.xml en c:\SWIFTAdapterTutorial\Interact\PullRequest.  
  
4.  Vaya a C:\SWIFTAdapterTutorial\Interact\PullResponse Compruebe que Sw:HandleRequest está en la carpeta.  
  
5.  Abra el mensaje de Sw:HandleRequest en un editor de texto, como el Bloc de notas y compruebe que la sección de carga es el mismo que el archivo ExchangeReqSimple.xml.  
  
## <a name="see-also"></a>Vea también  
 [El paso 4A: iniciar el servicio SWIFTNet para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)