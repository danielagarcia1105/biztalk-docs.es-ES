---
title: 'Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de avance (extracción) | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c2933d0-bbe3-4486-832e-5009b2d760ac
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9c8ea24eeb5541cf84448363ca91fcb8171f19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223948"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="02a43-102">Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de avance (extracción)</span><span class="sxs-lookup"><span data-stu-id="02a43-102">Step 4D: Test a Valid Instance for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="02a43-103">Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="02a43-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="02a43-104">Para probar una instancia válida</span><span class="sxs-lookup"><span data-stu-id="02a43-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="02a43-105">Coloque el archivo ExchangeReqSimple.xml en c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF.</span><span class="sxs-lookup"><span data-stu-id="02a43-105">Drop the file ExchangeReqSimple.xml into c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF.</span></span>  
  
2.  <span data-ttu-id="02a43-106">Compruebe que, tras unos instantes, el archivo ExchangeReqSimple.xml desaparece de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="02a43-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="02a43-107">Coloque el archivo acquirequeue.xml en c:\SWIFTAdapterTutorial\Interact\PullRequest.</span><span class="sxs-lookup"><span data-stu-id="02a43-107">Drop the file acquirequeue.xml into c:\SWIFTAdapterTutorial\Interact\PullRequest.</span></span>  
  
4.  <span data-ttu-id="02a43-108">Vaya a C:\SWIFTAdapterTutorial\Interact\PullResponse Compruebe que Sw:HandleRequest está en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="02a43-108">Browse to C:\SWIFTAdapterTutorial\Interact\PullResponse Verify that Sw:HandleRequest is in the folder.</span></span>  
  
5.  <span data-ttu-id="02a43-109">Abra el mensaje de Sw:HandleRequest en un editor de texto, como el Bloc de notas y compruebe que la sección de carga es el mismo que el archivo ExchangeReqSimple.xml.</span><span class="sxs-lookup"><span data-stu-id="02a43-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a43-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="02a43-110">See Also</span></span>  
 <span data-ttu-id="02a43-111">[El paso 4A: iniciar el servicio SWIFTNet para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="02a43-111">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="02a43-112">[Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="02a43-112">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="02a43-113">Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de avance (extracción)</span><span class="sxs-lookup"><span data-stu-id="02a43-113">Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)