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
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="897bf-102">Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="897bf-102">Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="897bf-103">Antes de comenzar este paso, debe completar [paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y reenviar escenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md).</span><span class="sxs-lookup"><span data-stu-id="897bf-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="897bf-104">Para crear una instancia de prueba</span><span class="sxs-lookup"><span data-stu-id="897bf-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="897bf-105">Abra un nuevo archivo en un editor de texto, como el Bloc de notas y pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="897bf-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  <span data-ttu-id="897bf-106">Guarde el archivo con el nombre ExchangeReqSimple.xml.</span><span class="sxs-lookup"><span data-stu-id="897bf-106">Save the File with the name ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="897bf-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="897bf-107">See Also</span></span>  
 <span data-ttu-id="897bf-108">[Paso 4: Probar el almacén de interacción y el escenario de reenvío-to-End](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="897bf-108">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="897bf-109">[El paso 4A: iniciar el servicio SWIFTNet para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="897bf-109">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="897bf-110">[Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="897bf-110">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="897bf-111">Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="897bf-111">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)