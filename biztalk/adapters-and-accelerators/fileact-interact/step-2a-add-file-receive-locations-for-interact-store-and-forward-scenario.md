---
title: "Paso 2A: Agregar archivo ubicaciones de recepción para el almacén de interacción y el escenario de avance (extracción) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acdc30e1-d80c-40bf-864d-bf136c77a2b8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195480b616437eea7b1cfafa703d4ec5d0bd2b54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2a-add-file-receive-locations-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="1d346-102">Paso 2A: Agregar archivo ubicaciones de recepción para el almacén de interacción y el escenario de avance (extracción)</span><span class="sxs-lookup"><span data-stu-id="1d346-102">Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="1d346-103">Antes de comenzar este paso, debe completar [paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de hacia delante y almacén de InterAct](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md).</span><span class="sxs-lookup"><span data-stu-id="1d346-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="1d346-104">Para agregar una ubicación de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="1d346-104">To add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="1d346-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="1d346-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="1d346-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="1d346-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="1d346-107">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**</span><span class="sxs-lookup"><span data-stu-id="1d346-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="1d346-108">En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, **Tutorial_IA_InputRequest_SnF**.</span><span class="sxs-lookup"><span data-stu-id="1d346-108">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="1d346-109">En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1d346-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="1d346-110">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="1d346-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="1d346-111">En el **propiedades de transporte de archivo** cuadro de diálogo, escriba **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d346-111">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="1d346-112">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d346-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="1d346-113">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="1d346-113">**Use this**</span></span>|<span data-ttu-id="1d346-114">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="1d346-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="1d346-115">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="1d346-115">**Receive handler**</span></span>|<span data-ttu-id="1d346-116">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="1d346-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="1d346-117">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="1d346-117">**Receive pipeline**</span></span>|<span data-ttu-id="1d346-118">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="1d346-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="1d346-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d346-119">Click **OK**.</span></span>  
  
10. <span data-ttu-id="1d346-120">Repita los pasos 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="1d346-120">Repeat steps 1 and 2.</span></span>  
  
11. <span data-ttu-id="1d346-121">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**</span><span class="sxs-lookup"><span data-stu-id="1d346-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
12. <span data-ttu-id="1d346-122">En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, **Tutorial_IA_InputRequest_PullMode**.</span><span class="sxs-lookup"><span data-stu-id="1d346-122">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_PullMode**.</span></span>  
  
13. <span data-ttu-id="1d346-123">En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1d346-123">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
14. <span data-ttu-id="1d346-124">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="1d346-124">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
15. <span data-ttu-id="1d346-125">En el **propiedades de transporte de archivo** cuadro de diálogo, escriba **C:\SWIFTAdapterTutorial\Interact\PullRequest**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d346-125">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\PullRequest**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="1d346-126">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d346-126">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="1d346-127">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="1d346-127">**Use this**</span></span>|<span data-ttu-id="1d346-128">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="1d346-128">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="1d346-129">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="1d346-129">**Receive handler**</span></span>|<span data-ttu-id="1d346-130">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="1d346-130">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="1d346-131">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="1d346-131">**Receive pipeline**</span></span>|<span data-ttu-id="1d346-132">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="1d346-132">From the drop-down list, select **XMLReceive**.</span></span>|  
  
17. <span data-ttu-id="1d346-133">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d346-133">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d346-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d346-134">See Also</span></span>  
 <span data-ttu-id="1d346-135">[Paso 2B: agregar puertos de envío de archivo para capturar el mensaje Sw:HandleRequest para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="1d346-135">[Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md) </span></span>  
 [<span data-ttu-id="1d346-136">Paso 2c: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de avance (extracción)</span><span class="sxs-lookup"><span data-stu-id="1d346-136">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)