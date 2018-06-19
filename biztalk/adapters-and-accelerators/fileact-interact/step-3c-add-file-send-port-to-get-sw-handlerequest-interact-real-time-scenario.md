---
title: 'Paso 3c: Agregar puerto de envío de archivo para obtener Sw:HandleRequest-interactuar en tiempo real escenario | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31e9c942-ba74-4ae2-b6e1-5266d0fbcb14
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ddc38913b8bf9ea5c9450334e58dfaeb5ff4ad3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224196"
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-real-time-scenario"></a><span data-ttu-id="2b511-102">Paso 3c: Agregar puerto de envío de archivo para obtener Sw:HandleRequest-interactuar escenario en tiempo real</span><span class="sxs-lookup"><span data-stu-id="2b511-102">Step 3C: Add FILE send port to get Sw:HandleRequest-InterAct real-time scenario</span></span>
<span data-ttu-id="2b511-103">Cuando se envía un mensaje al socio, SWIFT transforma el encabezado del mensaje y reenvía el mensaje al socio como un mensaje Sw:HandleRequest.</span><span class="sxs-lookup"><span data-stu-id="2b511-103">When you send a message to your partner, SWIFT transforms the message header and forwards the message to your partner as a Sw:HandleRequest message.</span></span> <span data-ttu-id="2b511-104">Antes de comenzar este paso, debe completar [paso 3B: agregar una ubicación de recepción interactuar para el escenario de en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="2b511-104">Before you begin this step, you must complete [Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlerequest-message"></a><span data-ttu-id="2b511-105">Para agregar un archivo de puerto de envío para capturar Sw:HandleRequest mensaje</span><span class="sxs-lookup"><span data-stu-id="2b511-105">To add a FILE send port to capture Sw:HandleRequest message</span></span>  
  
1.  <span data-ttu-id="2b511-106">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2b511-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2b511-107">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="2b511-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="2b511-108">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**</span><span class="sxs-lookup"><span data-stu-id="2b511-108">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="2b511-109">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_IA_SendResponseToReceiver**.</span><span class="sxs-lookup"><span data-stu-id="2b511-109">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendResponseToReceiver**.</span></span>  
  
5.  <span data-ttu-id="2b511-110">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="2b511-110">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="2b511-111">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba C:\SWIFTAdapterTutorial\Interact\HandleRequest y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b511-111">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Interact\HandleRequest, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="2b511-112">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b511-112">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="2b511-113">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="2b511-113">**Use this**</span></span>|<span data-ttu-id="2b511-114">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="2b511-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="2b511-115">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="2b511-115">**Send handler**</span></span>|<span data-ttu-id="2b511-116">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="2b511-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="2b511-117">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="2b511-117">**Send pipeline**</span></span>|<span data-ttu-id="2b511-118">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="2b511-118">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="2b511-119">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b511-119">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="2b511-120">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="2b511-120">**Use this**</span></span>|<span data-ttu-id="2b511-121">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="2b511-121">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="2b511-122">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="2b511-122">**Property**</span></span>|<span data-ttu-id="2b511-123">En la lista desplegable, seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="2b511-123">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="2b511-124">**Operador**</span><span class="sxs-lookup"><span data-stu-id="2b511-124">**Operator**</span></span>|<span data-ttu-id="2b511-125">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="2b511-125">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="2b511-126">**Valor**</span><span class="sxs-lookup"><span data-stu-id="2b511-126">**Value**</span></span>|<span data-ttu-id="2b511-127">Tipo de **Tutorial_IA_HandleRequestOneWay_RealTime.**</span><span class="sxs-lookup"><span data-stu-id="2b511-127">Type **Tutorial_IA_HandleRequestOneWay_RealTime.**</span></span>|  
    |<span data-ttu-id="2b511-128">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="2b511-128">**Group by**</span></span>|<span data-ttu-id="2b511-129">Dejar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2b511-129">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="2b511-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b511-130">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b511-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b511-131">See Also</span></span>  
 <span data-ttu-id="2b511-132">[Paso 3: Crear el envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2b511-132">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2b511-133">[Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2b511-133">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2b511-134">[Paso 3B: agregar un INTERACTÚE ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2b511-134">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2b511-135">[Paso 3D: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleResponse para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="2b511-135">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="2b511-136">Paso 3E: agregar un puerto de envío de interacción para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="2b511-136">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)