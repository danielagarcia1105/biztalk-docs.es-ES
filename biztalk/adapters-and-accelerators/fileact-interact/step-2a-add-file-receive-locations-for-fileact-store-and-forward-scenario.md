---
title: 'Paso 2A: agregar ubicaciones de recepción de archivo | Documentos de Microsoft'
description: 'Paso 2A: Agregar archivo ubicaciones de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct en BizTalk Server'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13720ebb-fbe4-4fe1-a095-9ae14c62def1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e297a85f309445c3caf569d2d752be58997e9754
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224076"
---
# <a name="step-2a-add-file-receive-locations-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="3c41b-103">Paso 2A: Agregar archivo ubicaciones de recepción para el escenario de reenvío (extracción) y el almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="3c41b-103">Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="3c41b-104">Antes de comenzar este paso, debe completar [paso 1: configurar el adaptador de SWIFT para el escenario de reenvío (extracción) y el almacenamiento de FileAct](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="3c41b-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward (Pull) Scenario](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md).</span></span>  
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="3c41b-105">Agregar una ubicación de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="3c41b-105">Add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="3c41b-106">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3c41b-107">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="3c41b-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="3c41b-108">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**</span><span class="sxs-lookup"><span data-stu-id="3c41b-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="3c41b-109">En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, **Tutorial_FA_InputRequest_SnF**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-109">In the **Receive Port Properties** window, name the receive port, **Tutorial_FA_InputRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="3c41b-110">En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-110">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="3c41b-111">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-111">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="3c41b-112">En el **propiedades de transporte de archivo** cuadro de diálogo, escriba **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-112">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="3c41b-113">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c41b-113">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="3c41b-114">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="3c41b-114">**Use this**</span></span>|<span data-ttu-id="3c41b-115">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="3c41b-115">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3c41b-116">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="3c41b-116">**Receive handler**</span></span>|<span data-ttu-id="3c41b-117">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-117">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="3c41b-118">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="3c41b-118">**Receive pipeline**</span></span>|<span data-ttu-id="3c41b-119">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-119">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="3c41b-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-120">Click **OK**.</span></span>  
  
10. <span data-ttu-id="3c41b-121">Repita los pasos 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="3c41b-121">Repeat steps 1 and 2.</span></span>  
  
11. <span data-ttu-id="3c41b-122">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**</span><span class="sxs-lookup"><span data-stu-id="3c41b-122">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
12. <span data-ttu-id="3c41b-123">En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, **Tutorial_ FA_InputRequest_PullMode**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-123">In the **Receive Port Properties** window, name the receive port, **Tutorial_ FA_InputRequest_PullMode**.</span></span>  
  
13. <span data-ttu-id="3c41b-124">En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-124">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
14. <span data-ttu-id="3c41b-125">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **archivo**, y a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-125">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
15. <span data-ttu-id="3c41b-126">En el **propiedades de transporte de archivo** cuadro de diálogo, escriba **C:\SWIFTAdapterTutorial\Interact\PullRequest**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-126">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\PullRequest**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="3c41b-127">En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c41b-127">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="3c41b-128">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="3c41b-128">**Use this**</span></span>|<span data-ttu-id="3c41b-129">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="3c41b-129">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3c41b-130">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="3c41b-130">**Receive handler**</span></span>|<span data-ttu-id="3c41b-131">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-131">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="3c41b-132">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="3c41b-132">**Receive pipeline**</span></span>|<span data-ttu-id="3c41b-133">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-133">From the drop-down list, select **XMLReceive**.</span></span>|  
  
17. <span data-ttu-id="3c41b-134">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c41b-134">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3c41b-135">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3c41b-135">Next steps</span></span>
-  [<span data-ttu-id="3c41b-136">Paso 2B: agregar puertos de envío de archivo para capturar la Sw:HandleFileRequest y Sw:HandleSnFRequest mensajes para el almacenamiento de FileAct y el reenvío de escenario (extracción)</span><span class="sxs-lookup"><span data-stu-id="3c41b-136">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>](step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
-  [<span data-ttu-id="3c41b-137">Paso 2c: agregar un puerto de envío de FILEACT para el escenario de avance (extracción) y el almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="3c41b-137">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>](step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)