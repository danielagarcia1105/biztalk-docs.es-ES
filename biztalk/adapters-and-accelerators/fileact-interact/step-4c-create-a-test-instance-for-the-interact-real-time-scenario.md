---
title: 'Paso 4c: crear una instancia de prueba para el escenario en tiempo real de interactuar | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3557acdc-eb3f-4c70-b64a-3f523a1ba650
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c0035074eba0eec6994aa7ab024afbcec10984
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-interact-real-time-scenario"></a><span data-ttu-id="83025-102">Paso 4c: crear una instancia de prueba para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="83025-102">Step 4C: Create a Test Instance for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="83025-103">Antes de comenzar este paso, debe completar [paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="83025-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="83025-104">Para crear una instancia de prueba</span><span class="sxs-lookup"><span data-stu-id="83025-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="83025-105">Abra un nuevo archivo en un editor de texto, como el Bloc de notas y pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83025-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  <span data-ttu-id="83025-106">Guarde el archivo con el nombre **ExchangeReqSimple.xml**.</span><span class="sxs-lookup"><span data-stu-id="83025-106">Save the file with the name **ExchangeReqSimple.xml**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83025-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="83025-107">See Also</span></span>  
 <span data-ttu-id="83025-108">[Paso 4: Probar el escenario de extremo a extremo en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="83025-108">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="83025-109">[El paso 4A: iniciar el servicio SWIFTNet](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="83025-109">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="83025-110">[Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="83025-110">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="83025-111">Paso 4d: probar una instancia válida para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="83025-111">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)