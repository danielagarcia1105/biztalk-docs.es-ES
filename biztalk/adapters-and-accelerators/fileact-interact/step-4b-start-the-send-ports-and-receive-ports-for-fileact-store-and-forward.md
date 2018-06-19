---
title: 'Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f8c34b1-24a5-4ac7-bb96-27834bc3c711
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb40a366a3c4952eaac9557ea04f5a84c846c81e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225412"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="9e723-102">Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="9e723-102">Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="9e723-103">Antes de comenzar este paso, debe completar [paso 4A: iniciar el SWIFTNet Service para el escenario de al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="9e723-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="9e723-104">Para iniciar los puertos de envío y puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="9e723-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="9e723-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="9e723-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9e723-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk en la que creó los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="9e723-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="9e723-107">Para cada uno de los siguientes puertos de envío, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**:</span><span class="sxs-lookup"><span data-stu-id="9e723-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="9e723-108">**Tutorial_FA_SendResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="9e723-108">**Tutorial_FA_SendResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="9e723-109">**Tutorial_FA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="9e723-109">**Tutorial_FA_SendRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="9e723-110">**Tutorial_ GetStatusReports**</span><span class="sxs-lookup"><span data-stu-id="9e723-110">**Tutorial_ GetStatusReports**</span></span>  
  
4.  <span data-ttu-id="9e723-111">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk donde se ha creado las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="9e723-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="9e723-112">Para cada una de las siguientes ubicaciones de recepción, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**:</span><span class="sxs-lookup"><span data-stu-id="9e723-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="9e723-113">**Tutorial_FA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="9e723-113">**Tutorial_FA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="9e723-114">**Tutorial_FA_HandleRequestOneWay_SnF**</span><span class="sxs-lookup"><span data-stu-id="9e723-114">**Tutorial_FA_HandleRequestOneWay_SnF**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e723-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e723-115">See Also</span></span>  
 <span data-ttu-id="9e723-116">[Paso 4: Probar el escenario de reenvío-to-End y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9e723-116">[Step 4: Test FileAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="9e723-117">[El paso 4A: iniciar el servicio SWIFTNet para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9e723-117">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="9e723-118">[Paso 4c: crear una instancia de prueba para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9e723-118">[Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="9e723-119">Paso 4d: probar una instancia válida para el escenario de reenvío y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="9e723-119">Step 4D: Test a Valid Instance for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario.md)