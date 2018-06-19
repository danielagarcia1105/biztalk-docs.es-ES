---
title: 'Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de interactuar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dffee9a6-5877-4744-9b46-12ca4f8fa959
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3391f966fb1033ec1886f44b62158f910179d72f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224324"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-real-time-scenario"></a><span data-ttu-id="e89be-102">Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="e89be-102">Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="e89be-103">Antes de comenzar este paso, debe completar [paso 4A: iniciar el SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md).</span><span class="sxs-lookup"><span data-stu-id="e89be-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="e89be-104">Para iniciar los puertos de envío y puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="e89be-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="e89be-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e89be-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e89be-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk en la que creó los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="e89be-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="e89be-107">Para cada uno de los siguientes puertos de envío, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**:</span><span class="sxs-lookup"><span data-stu-id="e89be-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="e89be-108">**Tutorial_IA_SendResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="e89be-108">**Tutorial_IA_SendResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="e89be-109">**Tutorial_IA_SendResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="e89be-109">**Tutorial_IA_SendResponseToSender**</span></span>  
  
    -   <span data-ttu-id="e89be-110">**Tutorial_IA_SendRequest_RealTime**</span><span class="sxs-lookup"><span data-stu-id="e89be-110">**Tutorial_IA_SendRequest_RealTime**</span></span>  
  
4.  <span data-ttu-id="e89be-111">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk donde se ha creado las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="e89be-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="e89be-112">Para cada una de las siguientes ubicaciones de recepción, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**:</span><span class="sxs-lookup"><span data-stu-id="e89be-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="e89be-113">**Tutorial_IA_InputRequest_RealTime**</span><span class="sxs-lookup"><span data-stu-id="e89be-113">**Tutorial_IA_InputRequest_RealTime**</span></span>  
  
    -   <span data-ttu-id="e89be-114">**Tutorial_IA_HandleRequestOneWay_RealTime**</span><span class="sxs-lookup"><span data-stu-id="e89be-114">**Tutorial_IA_HandleRequestOneWay_RealTime**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e89be-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e89be-115">See Also</span></span>  
 <span data-ttu-id="e89be-116">[Paso 4: Probar el escenario de extremo a extremo en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="e89be-116">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="e89be-117">[El paso 4A: iniciar el servicio SWIFTNet](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="e89be-117">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="e89be-118">[Paso 4c: crear una instancia de prueba para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="e89be-118">[Step 4C: Create a Test Instance for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="e89be-119">Paso 4d: probar una instancia válida para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="e89be-119">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)