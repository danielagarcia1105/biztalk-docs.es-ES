---
title: "Paso 4d: probar una instancia válida para el escenario de avance (extracción) y el almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33c7aabe-206f-4b89-b739-ac1e63675451
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf6f53257ff2a9194cf85597d0806780f15c8e52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="02601-102">Paso 4d: probar una instancia válida para el escenario de avance (extracción) y el almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="02601-102">Step 4D: Test a Valid Instance for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="02601-103">Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="02601-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="02601-104">Para probar una instancia válida</span><span class="sxs-lookup"><span data-stu-id="02601-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="02601-105">Coloque el archivo PutReqSimple.xml en **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**.</span><span class="sxs-lookup"><span data-stu-id="02601-105">Drop the file PutReqSimple.xml into **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**.</span></span>  
  
2.  <span data-ttu-id="02601-106">Compruebe que, tras unos instantes, el archivo PutReqSimple.xml desaparece de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="02601-106">Verify that after a moment, the PutReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="02601-107">Quitar el fileactcquirequeue.xml de archivo en **C:\SWIFTAdapterTutorial\FileAct\PullRequest**.</span><span class="sxs-lookup"><span data-stu-id="02601-107">Drop the file fileactcquirequeue.xml into **C:\SWIFTAdapterTutorial\FileAct\PullRequest**.</span></span>  
  
4.  <span data-ttu-id="02601-108">Compruebe que el archivo Sample_Put.txt se transfiere desde **C:\SWIFTAdapterTutorial\Fileact\ClientLocation** a **C:\SWIFTAdapterTutorial\Fileact\ServerLocation**, y que las respuestas aparecen en **C:\SWIFTAdapterTutorial\PullResponse**.</span><span class="sxs-lookup"><span data-stu-id="02601-108">Verify that the Sample_Put.txt file is transferred from **C:\SWIFTAdapterTutorial\Fileact\ClientLocation** to **C:\SWIFTAdapterTutorial\Fileact\ServerLocation**, and that responses appear in **C:\SWIFTAdapterTutorial\PullResponse**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02601-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="02601-109">See Also</span></span>  
 <span data-ttu-id="02601-110">[El paso 4A: iniciar el servicio SWIFTNet para el escenario de avance (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="02601-110">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span></span>  
 <span data-ttu-id="02601-111">[Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="02601-111">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="02601-112">Paso 4c: crear una instancia de prueba para el escenario de avance (extracción) y el almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="02601-112">Step 4C: Create a Test Instance for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)