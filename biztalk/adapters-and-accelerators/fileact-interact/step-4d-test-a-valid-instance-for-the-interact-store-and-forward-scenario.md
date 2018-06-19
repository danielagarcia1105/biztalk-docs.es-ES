---
title: 'Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa49df8-ccf6-455a-99ff-38879d2b7bf9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5d27b23195adffc5915d8cb2170dca9e975ec94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224284"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="d015a-102">Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="d015a-102">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="d015a-103">Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el almacén de interacción y reenviar escenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="d015a-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="d015a-104">Para probar una instancia válida</span><span class="sxs-lookup"><span data-stu-id="d015a-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="d015a-105">Coloque el archivo ExchangeReqSimple.xml en c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span><span class="sxs-lookup"><span data-stu-id="d015a-105">Drop the file ExchangeReqSimple.xml into c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span></span>  
  
2.  <span data-ttu-id="d015a-106">Compruebe que, tras unos instantes, el archivo ExchangeReqSimple.xml desaparece de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="d015a-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="d015a-107">Vaya a C:\SWIFTAdapterTutorial\Interact\HandleRequest.</span><span class="sxs-lookup"><span data-stu-id="d015a-107">Browse to C:\SWIFTAdapterTutorial\Interact\HandleRequest.</span></span> <span data-ttu-id="d015a-108">Compruebe que Sw:HandleRequest está en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="d015a-108">Verify that Sw:HandleRequest is in the folder.</span></span>  
  
4.  <span data-ttu-id="d015a-109">Abra el mensaje de Sw:HandleRequest en un editor de texto, como el Bloc de notas y compruebe que la sección de carga es el mismo que el archivo ExchangeReqSimple.xml.</span><span class="sxs-lookup"><span data-stu-id="d015a-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d015a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d015a-110">See Also</span></span>  
 <span data-ttu-id="d015a-111">[Paso 4: Probar el almacén de interacción y el escenario de reenvío-to-End](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d015a-111">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="d015a-112">[El paso 4A: iniciar el servicio SWIFTNet para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d015a-112">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="d015a-113">[Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="d015a-113">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="d015a-114">Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="d015a-114">Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)