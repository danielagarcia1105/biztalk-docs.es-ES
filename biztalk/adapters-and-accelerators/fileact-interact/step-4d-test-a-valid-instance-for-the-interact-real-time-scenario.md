---
title: "Paso 4d: probar una instancia válida para el escenario en tiempo real de interactuar | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e163c3ac-a00d-40cf-b1b8-4a38f74ab0e8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94bdb2acd8147ec5041df7d6a1c4324ca833d9e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-real-time-scenario"></a><span data-ttu-id="9ba19-102">Paso 4d: probar una instancia válida para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="9ba19-102">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="9ba19-103">Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el escenario de en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="9ba19-104">Para probar una instancia válida</span><span class="sxs-lookup"><span data-stu-id="9ba19-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="9ba19-105">Coloque el archivo ExchangeReqSimple.xml en C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime.</span><span class="sxs-lookup"><span data-stu-id="9ba19-105">Drop the file ExchangeReqSimple.xml into C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime.</span></span>  
  
2.  <span data-ttu-id="9ba19-106">Compruebe que, tras unos instantes, el archivo ExchangeReqSimple.xml desaparece de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="9ba19-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="9ba19-107">Vaya a C:\SWIFTAdapterTutorial\Interact\HandleRequest para ver el mensaje de solicitud de identificador, Sw:HandleRequest.</span><span class="sxs-lookup"><span data-stu-id="9ba19-107">Browse to C:\SWIFTAdapterTutorial\Interact\HandleRequest to view the handle request message, Sw:HandleRequest.</span></span>  
  
4.  <span data-ttu-id="9ba19-108">Vaya a C:\SWIFTAdapterTutorial\Interact\Response para ver el mensaje de respuesta de identificador, Sw:HandleResponse.</span><span class="sxs-lookup"><span data-stu-id="9ba19-108">Browse to C:\SWIFTAdapterTutorial\Interact\Response to view the handle response message, Sw:HandleResponse.</span></span>  
  
5.  <span data-ttu-id="9ba19-109">Abra el mensaje de Sw:HandleRequest en un editor de texto, como el Bloc de notas y compruebe que la sección de carga es el mismo que el archivo ExchangeReqSimple.xml.</span><span class="sxs-lookup"><span data-stu-id="9ba19-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba19-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ba19-110">See Also</span></span>  
 <span data-ttu-id="9ba19-111">[Paso 4: Probar el escenario de extremo a extremo en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9ba19-111">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="9ba19-112">[El paso 4A: iniciar el servicio SWIFTNet](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="9ba19-112">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="9ba19-113">[Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9ba19-113">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="9ba19-114">Paso 4c: crear una instancia de prueba para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="9ba19-114">Step 4C: Create a Test Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)