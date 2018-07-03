---
title: 'Paso 2B: agregar puertos de envío de archivos para capturar el mensaje SW: HandleRequest para el escenario InterAct Store y reenvío (extracción) | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa22d6e7-f1bd-43ad-9a0e-0b287057d20f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56cee834f5974d993dfeaa8fbfee8313eeb74064
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004445"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlerequest-message-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="f2324-102">Paso 2B: agregar puertos de envío de archivos para capturar el mensaje SW: HandleRequest para el escenario InterAct Store y reenvío (extracción)</span><span class="sxs-lookup"><span data-stu-id="f2324-102">Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="f2324-103">Antes de comenzar este paso, debe completar [paso 2A: Agregar archivo ubicaciones de recepción para la interacción Store y reenvío (extracción) de interact](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="f2324-103">Before you begin this step, you must complete [Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md).</span></span>  

### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a><span data-ttu-id="f2324-104">Para agregar un archivo de puerto de envío para capturar el mensaje SW: HandleRequest</span><span class="sxs-lookup"><span data-stu-id="f2324-104">To add a FILE send port to capture the Sw:HandleRequest message</span></span>  

1. <span data-ttu-id="f2324-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="f2324-105">Start **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f2324-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="f2324-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  

3. <span data-ttu-id="f2324-107">Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**</span><span class="sxs-lookup"><span data-stu-id="f2324-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  

4. <span data-ttu-id="f2324-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_IA_SendPullResponsetoReceiver**.</span><span class="sxs-lookup"><span data-stu-id="f2324-108">In the **Send Port Properties** window, name the send port, **Tutorial_IA_SendPullResponsetoReceiver**.</span></span>  

5. <span data-ttu-id="f2324-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="f2324-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="f2324-110">En el **propiedades de transporte de archivo** cuadro de diálogo el **carpeta de destino** , escriba **C:\SWIFTAdapterTutorial\Interact\PullResponse**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f2324-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\Interact\PullResponse**, and then click **OK**.</span></span>  

7. <span data-ttu-id="f2324-111">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2324-111">In the **Send Port Properties** window, do the following:</span></span>  


   |   <span data-ttu-id="f2324-112">**Úselo**</span><span class="sxs-lookup"><span data-stu-id="f2324-112">**Use this**</span></span>    |                        <span data-ttu-id="f2324-113">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="f2324-113">**To do this**</span></span>                         |
   |-------------------|---------------------------------------------------------------|
   | <span data-ttu-id="f2324-114">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="f2324-114">**Send handler**</span></span>  | <span data-ttu-id="f2324-115">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="f2324-115">From the drop-down list, select **BizTalkServerApplication**.</span></span> |
   | <span data-ttu-id="f2324-116">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="f2324-116">**Send pipeline**</span></span> |       <span data-ttu-id="f2324-117">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="f2324-117">From the drop-down list, select **XMLTransmit**.</span></span>        |


8. <span data-ttu-id="f2324-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f2324-118">Click **OK**.</span></span>  

9. <span data-ttu-id="f2324-119">Repita los pasos 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="f2324-119">Repeat step 1 and 2.</span></span>  

10. <span data-ttu-id="f2324-120">Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta dinámico**.</span><span class="sxs-lookup"><span data-stu-id="f2324-120">Right-click **Send Ports**, point to **New**, and then click **Dynamic Solicit-Response Send Port**.</span></span>  

11. <span data-ttu-id="f2324-121">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío<strong>, Tutorial_IA_DynamicSendPort</strong>.</span><span class="sxs-lookup"><span data-stu-id="f2324-121">In the **Send Port Properties** window, name the send port<strong>, Tutorial_IA_DynamicSendPort</strong>.</span></span>  

12. <span data-ttu-id="f2324-122">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2324-122">In the **Send Port Properties** window, do the following:</span></span>  


    |     <span data-ttu-id="f2324-123">**Úselo**</span><span class="sxs-lookup"><span data-stu-id="f2324-123">**Use this**</span></span>     |                  <span data-ttu-id="f2324-124">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="f2324-124">**To do this**</span></span>                  |
    |----------------------|--------------------------------------------------|
    |  <span data-ttu-id="f2324-125">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="f2324-125">**Send pipeline**</span></span>   | <span data-ttu-id="f2324-126">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="f2324-126">From the drop-down list, select **XMLTransmit**.</span></span> |
    | <span data-ttu-id="f2324-127">**Canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="f2324-127">**Receive pipeline**</span></span> | <span data-ttu-id="f2324-128">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="f2324-128">From the drop-down list, select **XMLReceive**.</span></span>  |


13. <span data-ttu-id="f2324-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f2324-129">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f2324-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2324-130">See Also</span></span>  
 <span data-ttu-id="f2324-131">[Paso 2A: Agregar archivo ubicaciones de recepción para el escenario InterAct Store y reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f2324-131">[Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="f2324-132">Paso 2C: Agregar un puerto de envío INTERACT para el escenario de almacenamiento y reenvío (extracción) de InterAct</span><span class="sxs-lookup"><span data-stu-id="f2324-132">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)