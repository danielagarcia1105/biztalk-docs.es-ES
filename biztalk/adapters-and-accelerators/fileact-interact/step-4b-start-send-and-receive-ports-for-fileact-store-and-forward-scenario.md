---
title: 'Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea2215c5-fb43-4c7e-a42d-5d131a6dee38
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad4c6b9d17ab1ea55c1f8378f1cb481a07b09e34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224396"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="6d528-102">Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="6d528-102">Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="6d528-103">Antes de comenzar este paso, debe completar [paso 4A: iniciar el SWIFTNet Service para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="6d528-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="6d528-104">Para iniciar los puertos de envío y puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="6d528-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="6d528-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="6d528-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6d528-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk en la que creó los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="6d528-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="6d528-107">Para cada uno de los siguientes puertos de envío, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**:</span><span class="sxs-lookup"><span data-stu-id="6d528-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="6d528-108">**Tutorial_ FA_SendPullResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="6d528-108">**Tutorial_ FA_SendPullResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="6d528-109">**Tutorial_ FA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="6d528-109">**Tutorial_ FA_SendRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="6d528-110">**Tutorial_ FA_DynamicSendPort**</span><span class="sxs-lookup"><span data-stu-id="6d528-110">**Tutorial_ FA_DynamicSendPort**</span></span>  
  
4.  <span data-ttu-id="6d528-111">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk donde se ha creado las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="6d528-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="6d528-112">Para cada una de las siguientes ubicaciones de recepción, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**:</span><span class="sxs-lookup"><span data-stu-id="6d528-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="6d528-113">**Tutorial_ FA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="6d528-113">**Tutorial_ FA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="6d528-114">**Tutorial_ FA_InputRequest_PullMode**</span><span class="sxs-lookup"><span data-stu-id="6d528-114">**Tutorial_ FA_InputRequest_PullMode**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d528-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d528-115">See Also</span></span>  
 <span data-ttu-id="6d528-116">[El paso 4A: iniciar el servicio SWIFTNet para el escenario de avance (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6d528-116">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span></span>  
 <span data-ttu-id="6d528-117">[Paso 4c: crear una instancia de prueba para el escenario de avance (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6d528-117">[Step 4C: Create a Test Instance for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md) </span></span>  
 [<span data-ttu-id="6d528-118">Paso 4d: probar una instancia válida para el escenario de avance (extracción) y el almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="6d528-118">Step 4D: Test a Valid Instance for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)