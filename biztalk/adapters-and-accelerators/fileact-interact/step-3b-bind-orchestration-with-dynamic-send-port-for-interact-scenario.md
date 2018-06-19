---
title: 'Paso 3B: enlazar la orquestación con el puerto de envío dinámico para interactuar almacén y escenario de reenvío (extracción) | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55eec1f3-b920-48f8-946a-9ad7afa36fd6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b289d8478eb020067d9231fb1d4f135c7b43b289
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223300"
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="e5f95-102">Paso 3B: enlazar la orquestación con el puerto de envío dinámico para interactuar almacén y escenario de reenvío (extracción)</span><span class="sxs-lookup"><span data-stu-id="e5f95-102">Step 3B: Bind the orchestration with dynamic send port for InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="e5f95-103">Antes de comenzar este paso, debe completar [paso 3A: crear una orquestación para el puerto de envío dinámico para el almacén de interacción y escenario de reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md).</span><span class="sxs-lookup"><span data-stu-id="e5f95-103">Before you begin this step, you must complete [Step 3A: Create an orchestration for dynamic send port for InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="e5f95-104">Para agregar una ubicación de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="e5f95-104">To add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="e5f95-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e5f95-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e5f95-106">En la consola de administración de BizTalk Server, en el panel izquierdo, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, Haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="e5f95-106">In the BizTalk Server Administration Console, in the left pane, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="e5f95-107">Compruebe que el estado de la **BizTalkServerApplication** instancia e instancia de host de interacción de host es **ejecutando**.</span><span class="sxs-lookup"><span data-stu-id="e5f95-107">Verify that the status for the **BizTalkServerApplication** host instance and Interact host instance is **running**.</span></span> <span data-ttu-id="e5f95-108">Si no es así, haga clic en las instancias de host y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="e5f95-108">If not, right-click the host instances, and click **Start**.</span></span>  
  
3.  <span data-ttu-id="e5f95-109">En el panel izquierdo, expanda aplicaciones y, a continuación, expanda BizTalk Application 1.</span><span class="sxs-lookup"><span data-stu-id="e5f95-109">In the left pane, expand Applications, and then expand BizTalk Application 1.</span></span> <span data-ttu-id="e5f95-110">Haga clic en orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="e5f95-110">Click Orchestrations.</span></span>  
  
4.  <span data-ttu-id="e5f95-111">Haga clic en **DynamicSendOrchestration** y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e5f95-111">Right-click **DynamicSendOrchestration** and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="e5f95-112">En el **propiedades de orquestación** cuadro de diálogo, en el panel izquierdo, haga clic en **enlaces** y realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f95-112">In the **Orchestration Properties** dialog box, in the left pane, click **Bindings** and do the following:</span></span>  
  
    |<span data-ttu-id="e5f95-113">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="e5f95-113">**Use this**</span></span>|<span data-ttu-id="e5f95-114">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="e5f95-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="e5f95-115">**Host**</span><span class="sxs-lookup"><span data-stu-id="e5f95-115">**Host**</span></span>|<span data-ttu-id="e5f95-116">En la lista desplegable, seleccione **aplicación de servidor BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e5f95-116">From the drop-down list, select **BizTalkServer Application**.</span></span>|  
    |<span data-ttu-id="e5f95-117">**Extracción dinámica**</span><span class="sxs-lookup"><span data-stu-id="e5f95-117">**Dynamic Pull**</span></span>|<span data-ttu-id="e5f95-118">En la lista desplegable, seleccione **Tutorial_IA_DynamicSendPort**.</span><span class="sxs-lookup"><span data-stu-id="e5f95-118">From the drop-down list, select **Tutorial_IA_DynamicSendPort**.</span></span>|  
    |<span data-ttu-id="e5f95-119">**SendPullResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="e5f95-119">**SendPullResponseToSender**</span></span>|<span data-ttu-id="e5f95-120">En la lista desplegable, seleccione **Tutorial_IA_SendPullResponsetoReceiver**.</span><span class="sxs-lookup"><span data-stu-id="e5f95-120">From the drop-down list, select **Tutorial_IA_SendPullResponsetoReceiver**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5f95-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5f95-121">See Also</span></span>  
 [<span data-ttu-id="e5f95-122">Paso 3A: crear una orquestación para el puerto de envío dinámico para el almacén de interacción y escenario de reenvío (extracción)</span><span class="sxs-lookup"><span data-stu-id="e5f95-122">Step 3A: Create an orchestration for dynamic send port for InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md)