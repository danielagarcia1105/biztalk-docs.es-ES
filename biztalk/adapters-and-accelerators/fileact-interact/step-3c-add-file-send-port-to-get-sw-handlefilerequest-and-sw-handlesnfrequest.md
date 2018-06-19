---
title: 'Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes Sw:HandleFileRequest y Sw:HandleSnFRequest para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc41e352-acc5-47eb-bb87-38990f0e76a7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6858164ee82f935c607246e7e93ffd86908f93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225948"
---
# <a name="step-3c-add-a-file-send-port-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="cf1a2-102">Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes Sw:HandleFileRequest y Sw:HandleSnFRequest para el escenario de reenvío y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="cf1a2-102">Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="cf1a2-103">Antes de comenzar este paso, debe completar [paso 3B: agregar una ubicación de recepción de FILEACT para el escenario de al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="cf1a2-103">Before you begin this step, you must complete [Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swresponseserver-message"></a><span data-ttu-id="cf1a2-104">Para agregar un archivo de puerto de envío para capturar Sw:ResponseServer mensaje</span><span class="sxs-lookup"><span data-stu-id="cf1a2-104">To add a FILE send port to capture Sw:ResponseServer message</span></span>  
  
1.  <span data-ttu-id="cf1a2-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="cf1a2-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="cf1a2-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="cf1a2-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_FA_SendResponseToReceiver.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="cf1a2-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="cf1a2-110">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba C:\SWIFTAdapterTutorial\Fileact\ResponseServer y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ResponseServer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="cf1a2-111">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf1a2-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="cf1a2-112">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-112">**Use this**</span></span>|<span data-ttu-id="cf1a2-113">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="cf1a2-114">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-114">**Send handler**</span></span>|<span data-ttu-id="cf1a2-115">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="cf1a2-116">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-116">**Send pipeline**</span></span>|<span data-ttu-id="cf1a2-117">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="cf1a2-118">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf1a2-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="cf1a2-119">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-119">**Use this**</span></span>|<span data-ttu-id="cf1a2-120">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="cf1a2-121">**Primera fila: propiedad**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-121">**First row: Property**</span></span>|<span data-ttu-id="cf1a2-122">En la lista desplegable, seleccione **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-122">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="cf1a2-123">**Primera fila: operador**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-123">**First row: Operator**</span></span>|<span data-ttu-id="cf1a2-124">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="cf1a2-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="cf1a2-125">**Primera fila: valor**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-125">**First row: Value**</span></span>|<span data-ttu-id="cf1a2-126">Tipo de **Sw-HandleFileRequest**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-126">Type **Sw-HandleFileRequest**.</span></span>|  
    |<span data-ttu-id="cf1a2-127">**Primera fila: Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-127">**First row: Group by**</span></span>|<span data-ttu-id="cf1a2-128">En la lista desplegable, seleccione **o**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-128">From the drop-down list, select **OR**.</span></span>|  
    |<span data-ttu-id="cf1a2-129">**Segunda fila: propiedad**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-129">**Second row: Property**</span></span>|<span data-ttu-id="cf1a2-130">En la lista desplegable, seleccione **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-130">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="cf1a2-131">**Segunda fila: operador**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-131">**Second row: Operator**</span></span>|<span data-ttu-id="cf1a2-132">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="cf1a2-132">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="cf1a2-133">**Segunda fila: valor**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-133">**Second row: Value**</span></span>|<span data-ttu-id="cf1a2-134">Tipo de **Sw-HandleSnFRequest**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-134">Type **Sw-HandleSnFRequest**.</span></span>|  
    |<span data-ttu-id="cf1a2-135">**Segunda fila: Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="cf1a2-135">**Second row: Group by**</span></span>|<span data-ttu-id="cf1a2-136">Dejar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-136">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="cf1a2-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cf1a2-137">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1a2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf1a2-138">See Also</span></span>  
 <span data-ttu-id="cf1a2-139">[Paso 3: Crear puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="cf1a2-139">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="cf1a2-140">[Paso 3A: agregar un archivo de ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cf1a2-140">[Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="cf1a2-141">[Paso 3B: agregar un FILEACT ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cf1a2-141">[Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="cf1a2-142">Paso 3D: agregar un puerto de envío de FILEACT para el escenario de reenvío y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="cf1a2-142">Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)