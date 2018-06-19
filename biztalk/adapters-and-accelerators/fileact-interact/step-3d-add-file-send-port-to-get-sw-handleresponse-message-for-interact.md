---
title: 'Paso 3D: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleResponse para el escenario en tiempo real de interactuar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e05e4d20-4cf2-402f-aaea-66987cb6515a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a0c8c8721d9f7de7b1cd1e57537aa02d2ed8fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225892"
---
# <a name="step-3d-add-a-file-send-port-to-capture-the-swhandleresponse-message-for-the-interact-real-time-scenario"></a><span data-ttu-id="290ce-102">Paso 3D: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleResponse para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="290ce-102">Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="290ce-103">Completa [paso 3c: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleRequest para el escenario de en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) antes de comenzar este paso.</span><span class="sxs-lookup"><span data-stu-id="290ce-103">Complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) before you begin this step.</span></span>
  
## <a name="add-a-file-send-port-to-capture-swhandleresponse-message"></a><span data-ttu-id="290ce-104">Agregar un archivo de puerto de envío para capturar Sw:HandleResponse mensaje</span><span class="sxs-lookup"><span data-stu-id="290ce-104">Add a FILE send port to capture Sw:HandleResponse message</span></span>  
  
1.  <span data-ttu-id="290ce-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="290ce-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="290ce-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="290ce-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="290ce-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**</span><span class="sxs-lookup"><span data-stu-id="290ce-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="290ce-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_IA_SendResponseToSender**.</span><span class="sxs-lookup"><span data-stu-id="290ce-108">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendResponseToSender**.</span></span>  
  
5.  <span data-ttu-id="290ce-109">En el **propiedades de puerto de envío** ventana, desde el **Transporttype** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="290ce-109">In the **Send Port Properties** window, from the **Transporttype** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="290ce-110">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba **C:\SWIFTAdapterTutorial\Interact\Response**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="290ce-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\Interact\Response**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="290ce-111">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="290ce-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="290ce-112">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="290ce-112">**Use this**</span></span>|<span data-ttu-id="290ce-113">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="290ce-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="290ce-114">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="290ce-114">**Send handler**</span></span>|<span data-ttu-id="290ce-115">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="290ce-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="290ce-116">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="290ce-116">**Send pipeline**</span></span>|<span data-ttu-id="290ce-117">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="290ce-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="290ce-118">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="290ce-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="290ce-119">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="290ce-119">**Use this**</span></span>|<span data-ttu-id="290ce-120">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="290ce-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="290ce-121">Primera fila: **propiedad**</span><span class="sxs-lookup"><span data-stu-id="290ce-121">First row: **Property**</span></span>|<span data-ttu-id="290ce-122">En la lista desplegable, seleccione **BTS. SPName**.</span><span class="sxs-lookup"><span data-stu-id="290ce-122">From the drop-down list, select **BTS.SPName**.</span></span>|  
    |<span data-ttu-id="290ce-123">Primera fila: **(operador)**</span><span class="sxs-lookup"><span data-stu-id="290ce-123">First row: **Operator**</span></span>|<span data-ttu-id="290ce-124">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="290ce-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="290ce-125">Primera fila: **valor**</span><span class="sxs-lookup"><span data-stu-id="290ce-125">First row: **Value**</span></span>|<span data-ttu-id="290ce-126">Tipo de **Tutorial_IA_HandleRequest_RealTime**.</span><span class="sxs-lookup"><span data-stu-id="290ce-126">Type **Tutorial_IA_HandleRequest_RealTime**.</span></span>|  
    |<span data-ttu-id="290ce-127">Primera fila: **Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="290ce-127">First row: **Group by**</span></span>|<span data-ttu-id="290ce-128">En la lista desplegable, seleccione **o**.</span><span class="sxs-lookup"><span data-stu-id="290ce-128">From the drop-down list, select **OR**.</span></span>|  
    |<span data-ttu-id="290ce-129">Segunda fila: **propiedad**</span><span class="sxs-lookup"><span data-stu-id="290ce-129">Second row: **Property**</span></span>|<span data-ttu-id="290ce-130">En la lista desplegable, seleccione **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="290ce-130">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="290ce-131">Segunda fila: **(operador)**</span><span class="sxs-lookup"><span data-stu-id="290ce-131">Second row: **Operator**</span></span>|<span data-ttu-id="290ce-132">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="290ce-132">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="290ce-133">Segunda fila: **valor**</span><span class="sxs-lookup"><span data-stu-id="290ce-133">Second row: **Value**</span></span>|<span data-ttu-id="290ce-134">Tipo de **SwInt ExchangeResponse**.</span><span class="sxs-lookup"><span data-stu-id="290ce-134">Type **SwInt-ExchangeResponse**.</span></span>|  
    |<span data-ttu-id="290ce-135">Segunda fila: **Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="290ce-135">Second row: **Group by**</span></span>|<span data-ttu-id="290ce-136">Dejar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="290ce-136">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="290ce-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="290ce-137">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290ce-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="290ce-138">See Also</span></span>  
 <span data-ttu-id="290ce-139">[Paso 3: Crear el envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="290ce-139">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="290ce-140">[Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="290ce-140">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="290ce-141">[Paso 3B: agregar un INTERACTÚE ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="290ce-141">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="290ce-142">[Paso 3c: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleRequest para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="290ce-142">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="290ce-143">Paso 3E: agregar un puerto de envío de interacción para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="290ce-143">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)