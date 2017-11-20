---
title: "Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes de Sw:HandleRequest para el escenario en tiempo real de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc0a9173-20df-4c73-80ee-755987d639d2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3705f0b649e7f8d1c85898677ddc0301851dd302
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-add-a-file-send-port-to-capture-swhandlerequest-message-for-the-fileact-real-time-scenario"></a><span data-ttu-id="d9de5-102">Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes de Sw:HandleRequest para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="d9de5-102">Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="d9de5-103">Antes de comenzar este paso, debe completar [paso 3B: agregar una ubicación de recepción de FILEACT para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="d9de5-103">Before you begin this step, you must complete [Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlefilerequest-message"></a><span data-ttu-id="d9de5-104">Para agregar un archivo de puerto de envío para capturar Sw:HandleFileRequest mensaje</span><span class="sxs-lookup"><span data-stu-id="d9de5-104">To add a FILE send port to capture Sw:HandleFileRequest message</span></span>  
  
1.  <span data-ttu-id="d9de5-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d9de5-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d9de5-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="d9de5-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="d9de5-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**</span><span class="sxs-lookup"><span data-stu-id="d9de5-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="d9de5-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_FA_SendResponseToReceiver.</span><span class="sxs-lookup"><span data-stu-id="d9de5-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="d9de5-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="d9de5-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="d9de5-110">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba C:\SWIFTAdapterTutorial\Fileact\ResponseServer y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d9de5-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ResponseServer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="d9de5-111">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9de5-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="d9de5-112">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="d9de5-112">**Use this**</span></span>|<span data-ttu-id="d9de5-113">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="d9de5-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d9de5-114">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="d9de5-114">**Send handler**</span></span>|<span data-ttu-id="d9de5-115">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="d9de5-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="d9de5-116">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="d9de5-116">**Send pipeline**</span></span>|<span data-ttu-id="d9de5-117">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="d9de5-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="d9de5-118">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9de5-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="d9de5-119">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="d9de5-119">**Use this**</span></span>|<span data-ttu-id="d9de5-120">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="d9de5-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d9de5-121">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="d9de5-121">**Property**</span></span>|<span data-ttu-id="d9de5-122">En la lista desplegable, seleccione **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="d9de5-122">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="d9de5-123">**Operador**</span><span class="sxs-lookup"><span data-stu-id="d9de5-123">**Operator**</span></span>|<span data-ttu-id="d9de5-124">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="d9de5-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="d9de5-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d9de5-125">**Value**</span></span>|<span data-ttu-id="d9de5-126">Tipo de **Sw-HandleFileRequest**.</span><span class="sxs-lookup"><span data-stu-id="d9de5-126">Type **Sw-HandleFileRequest**.</span></span>|  
    |<span data-ttu-id="d9de5-127">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="d9de5-127">**Group by**</span></span>|<span data-ttu-id="d9de5-128">Deje el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="d9de5-128">Leave the default value</span></span>|  
  
9. <span data-ttu-id="d9de5-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d9de5-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9de5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9de5-130">See Also</span></span>  
 <span data-ttu-id="d9de5-131">[Paso 3: Crear los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d9de5-131">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="d9de5-132">[Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d9de5-132">[Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="d9de5-133">[Paso 3B: agregar un FILEACT ubicación de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d9de5-133">[Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="d9de5-134">[Paso 3D: agregar un puerto de envío de FILEACT para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d9de5-134">[Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="d9de5-135">Paso 3E: agregar un puerto de envío de archivo para capturar los mensajes de Sw:ExchangeFileResponse para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="d9de5-135">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)