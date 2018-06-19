---
title: 'Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de avance (extracción) | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00ab119d-ed44-4f4a-84ea-20f2c41e5a92
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b747c76b30b9f7d04bef379be9eaccaaeca063ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223644"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="c8dc2-102">Paso 4B: iniciar los puertos de envío y puertos de recepción para el almacén de interacción y el escenario de avance (extracción)</span><span class="sxs-lookup"><span data-stu-id="c8dc2-102">Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="c8dc2-103">Antes de comenzar este paso, debe completar[paso 4: probar el almacén de interacción y hacia delante de un extremo a otro escenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="c8dc2-103">Before you begin this step, you must complete[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="c8dc2-104">Para iniciar los puertos de envío y puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="c8dc2-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="c8dc2-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c8dc2-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk en la que creó los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="c8dc2-107">Para cada uno de los siguientes puertos de envío, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**:</span><span class="sxs-lookup"><span data-stu-id="c8dc2-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="c8dc2-108">**Tutorial_ IA_SendPullResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="c8dc2-108">**Tutorial_ IA_SendPullResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="c8dc2-109">**Tutorial_IA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="c8dc2-109">**Tutorial_IA_SendRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="c8dc2-110">**Tutorial_IA_DynamicSendPort**</span><span class="sxs-lookup"><span data-stu-id="c8dc2-110">**Tutorial_IA_DynamicSendPort**</span></span>  
  
4.  <span data-ttu-id="c8dc2-111">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk donde se ha creado las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="c8dc2-112">Para cada una de las siguientes ubicaciones de recepción, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**:</span><span class="sxs-lookup"><span data-stu-id="c8dc2-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="c8dc2-113">**Tutorial_IA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="c8dc2-113">**Tutorial_IA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="c8dc2-114">**Tutorial_ IA_InputRequest_PullMode**</span><span class="sxs-lookup"><span data-stu-id="c8dc2-114">**Tutorial_ IA_InputRequest_PullMode**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8dc2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8dc2-115">See Also</span></span>  
 <span data-ttu-id="c8dc2-116">[El paso 4A: iniciar el servicio SWIFTNet para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="c8dc2-116">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="c8dc2-117">[Paso 4c: crear una instancia de prueba para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="c8dc2-117">[Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md) </span></span>  
 [<span data-ttu-id="c8dc2-118">Paso 4d: probar una instancia válida para el almacén de interacción y el escenario de avance (extracción)</span><span class="sxs-lookup"><span data-stu-id="c8dc2-118">Step 4D: Test a Valid Instance for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)