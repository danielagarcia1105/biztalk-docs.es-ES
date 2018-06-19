---
title: Cómo probar el nodo HTTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP node, testing
- testing HTTP node
ms.assetid: f6881e8f-9f92-4312-bb5e-06bbfb9fe0bb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2790a4e3fa0ff1ed9a9b9b0c2018108c9cbb1282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255532"
---
# <a name="how-to-test-the-http-node"></a><span data-ttu-id="3e71d-102">Cómo probar el nodo HTTP</span><span class="sxs-lookup"><span data-stu-id="3e71d-102">How to Test the HTTP Node</span></span>
<span data-ttu-id="3e71d-103">Para probar el nodo HTTP, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3e71d-103">Follow these steps to test the HTTP node.</span></span>  
  
### <a name="to-test-the-http-node"></a><span data-ttu-id="3e71d-104">Para probar el nodo HTTP</span><span class="sxs-lookup"><span data-stu-id="3e71d-104">To test the HTTP node</span></span>  
  
1.  <span data-ttu-id="3e71d-105">En PeopleSoft Enterprise, vaya a **PeopleTools**, **Integration Broker**, **Monitor**, **Monitor Message**.</span><span class="sxs-lookup"><span data-stu-id="3e71d-105">In PeopleSoft Enterprise, navigate to **PeopleTools**, **Integration Broker**, **Monitor**, **Monitor Message**.</span></span>  
  
     ![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")  
  
2.  <span data-ttu-id="3e71d-106">Haga clic en el **estado del nodo** ficha.</span><span class="sxs-lookup"><span data-stu-id="3e71d-106">Click the **Node Status** tab.</span></span>  
  
3.  <span data-ttu-id="3e71d-107">En el **Message Node Name** , escriba `MSEXTERNAL`y, a continuación, haga clic en el **búsqueda** icono.</span><span class="sxs-lookup"><span data-stu-id="3e71d-107">In the **Message Node Name** field, enter `MSEXTERNAL`, and then click the **Lookup** icon.</span></span>  
  
4.  <span data-ttu-id="3e71d-108">En **Message Node Name**, seleccione **MSEXTERNAL**.</span><span class="sxs-lookup"><span data-stu-id="3e71d-108">Under **Message Node Name**, select **MSEXTERNAL**.</span></span>  
  
     <span data-ttu-id="3e71d-109">Aparecerá un mensaje que indica que PeopleSoft se está comunicando a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="3e71d-109">A message appears and indicates that PeopleSoft is communicating through HTTP.</span></span>  
  
     ![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")  
  
     <span data-ttu-id="3e71d-110">Si no recibe el mensaje, compruebe que:</span><span class="sxs-lookup"><span data-stu-id="3e71d-110">If you do not receive the message, verify the following:</span></span>  
  
    1.  <span data-ttu-id="3e71d-111">Los puertos y las direcciones IP coinciden con el puerto de recepción y el nodo.</span><span class="sxs-lookup"><span data-stu-id="3e71d-111">The IP addresses and ports match between the receive port and the node.</span></span>  
  
    2.  <span data-ttu-id="3e71d-112">BizTalk Server se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="3e71d-112">BizTalk Server is running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e71d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e71d-113">See Also</span></span>  
 [<span data-ttu-id="3e71d-114">Crear un Host de HTTP de PeopleSoft y puerto</span><span class="sxs-lookup"><span data-stu-id="3e71d-114">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)