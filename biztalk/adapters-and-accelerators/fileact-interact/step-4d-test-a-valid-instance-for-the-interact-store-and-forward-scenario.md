---
title: "Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aa49df8-ccf6-455a-99ff-38879d2b7bf9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5d27b23195adffc5915d8cb2170dca9e975ec94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario"></a>Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de reenvío
Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el almacén de interacción y reenviar escenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md).  
  
### <a name="to-test-a-valid-instance"></a>Para probar una instancia válida  
  
1.  Coloque el archivo ExchangeReqSimple.xml en c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF  
  
2.  Compruebe que, tras unos instantes, el archivo ExchangeReqSimple.xml desaparece de la carpeta.  
  
3.  Vaya a C:\SWIFTAdapterTutorial\Interact\HandleRequest. Compruebe que Sw:HandleRequest está en la carpeta.  
  
4.  Abra el mensaje de Sw:HandleRequest en un editor de texto, como el Bloc de notas y compruebe que la sección de carga es el mismo que el archivo ExchangeReqSimple.xml.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Probar el almacén de interacción y el escenario de reenvío-to-End](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)   
 [El paso 4A: iniciar el servicio SWIFTNet para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)   
 [Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)