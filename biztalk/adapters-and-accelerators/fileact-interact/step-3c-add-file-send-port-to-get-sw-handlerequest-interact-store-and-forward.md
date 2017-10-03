---
title: "Paso 3c: Agregar puerto de envío de archivo para obtener Sw:HandleRequest-interactuar almacenar y retransmitir | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c872b4be-ef8b-4e42-b5ef-63dfd120793f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b82c57f2f3a6e2fcfc199e56d34c44aa7667451d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-store-and-forward"></a><span data-ttu-id="d46fd-102">Paso 3c: Agregar puerto de envío de archivo para obtener Sw:HandleRequest-interactuar almacenamiento y reenvío</span><span class="sxs-lookup"><span data-stu-id="d46fd-102">Step 3C: Add FILE send port to get Sw:HandleRequest-InterAct Store and Forward</span></span>
<span data-ttu-id="d46fd-103">Antes de comenzar este paso, debe completar [paso 3B: agregar una ubicación de recepción interactuar para el escenario de hacia delante y almacén de InterAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="d46fd-103">Before you begin this step, you must complete [Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a><span data-ttu-id="d46fd-104">Para agregar un archivo de puerto de envío para capturar el mensaje Sw:HandleRequest</span><span class="sxs-lookup"><span data-stu-id="d46fd-104">To add a FILE send port to capture the Sw:HandleRequest message</span></span>  
  
1.  <span data-ttu-id="d46fd-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d46fd-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d46fd-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="d46fd-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="d46fd-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático.**</span><span class="sxs-lookup"><span data-stu-id="d46fd-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="d46fd-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_IA_SendResponseToReceiver.</span><span class="sxs-lookup"><span data-stu-id="d46fd-108">In the **Send Port Properties** window, name the send port, Tutorial_IA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="d46fd-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="d46fd-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="d46fd-110">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba C:\SWIFTAdapterTutorial\Interact\HandleRequest y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d46fd-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Interact\HandleRequest, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="d46fd-111">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d46fd-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="d46fd-112">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="d46fd-112">**Use this**</span></span>|<span data-ttu-id="d46fd-113">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="d46fd-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d46fd-114">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="d46fd-114">**Send handler**</span></span>|<span data-ttu-id="d46fd-115">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="d46fd-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="d46fd-116">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="d46fd-116">**Send pipeline**</span></span>|<span data-ttu-id="d46fd-117">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="d46fd-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="d46fd-118">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d46fd-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="d46fd-119">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="d46fd-119">**Use this**</span></span>|<span data-ttu-id="d46fd-120">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="d46fd-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d46fd-121">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="d46fd-121">**Property**</span></span>|<span data-ttu-id="d46fd-122">En la lista desplegable, seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="d46fd-122">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="d46fd-123">**Operador**</span><span class="sxs-lookup"><span data-stu-id="d46fd-123">**Operator**</span></span>|<span data-ttu-id="d46fd-124">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="d46fd-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="d46fd-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d46fd-125">**Value**</span></span>|<span data-ttu-id="d46fd-126">Tipo de **Tutorial_IA_InputRequest_SnF**.</span><span class="sxs-lookup"><span data-stu-id="d46fd-126">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="d46fd-127">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="d46fd-127">**Group by**</span></span>|<span data-ttu-id="d46fd-128">Dejar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d46fd-128">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="d46fd-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d46fd-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46fd-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d46fd-130">See Also</span></span>  
 <span data-ttu-id="d46fd-131">[Paso 3: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d46fd-131">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="d46fd-132">[Paso 3A: agregar un archivo de ubicación de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d46fd-132">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="d46fd-133">[Paso 3B: agregar un INTERACTÚE ubicación de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d46fd-133">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="d46fd-134">Paso 3D: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="d46fd-134">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)