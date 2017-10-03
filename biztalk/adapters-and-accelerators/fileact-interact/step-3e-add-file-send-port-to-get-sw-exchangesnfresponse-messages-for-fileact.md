---
title: "Paso 3E: agregar un puerto de envío de archivo para el almacenamiento de FileAct y reenviar escenario para capturar los mensajes de Sw-ExchangeSnFResponse | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04bad2ab-1ea4-4602-9dee-5b9af9be3b93
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44cf320f22f5acc2511d6327c36c54cda8f0dd1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3e-add-a-file-send-port-for-the-fileact-store-and-forward-scenario-to-capture-sw-exchangesnfresponse-messages"></a><span data-ttu-id="55fb9-102">Paso 3E: agregar un puerto de envío de archivo para el escenario de hacia delante para capturar los mensajes de Sw-ExchangeSnFResponse y el almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="55fb9-102">Step 3E: Add a FILE Send Port for the FileAct Store and Forward Scenario to capture Sw-ExchangeSnFResponse messages</span></span>
<span data-ttu-id="55fb9-103">Antes de comenzar este paso, debe completar [paso 3D: agregar un puerto de envío de FILEACT para el escenario de al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="55fb9-103">Before you begin this step, you must complete [Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a><span data-ttu-id="55fb9-104">Para agregar un puerto de envío de archivo para capturar los eventos de estado:</span><span class="sxs-lookup"><span data-stu-id="55fb9-104">To add a FILE send port to capture Status Events:</span></span>  
  
1.  <span data-ttu-id="55fb9-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="55fb9-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="55fb9-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="55fb9-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="55fb9-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="55fb9-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
4.  <span data-ttu-id="55fb9-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_ GetStatusReports.</span><span class="sxs-lookup"><span data-stu-id="55fb9-108">In the **Send Port Properties** window, name the send port, Tutorial_ GetStatusReports.</span></span>  
  
5.  <span data-ttu-id="55fb9-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="55fb9-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="55fb9-110">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba C:\SWIFTAdapterTutorial\Fileact\ StatusEvents y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="55fb9-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ StatusEvents, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="55fb9-111">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55fb9-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="55fb9-112">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="55fb9-112">**Use this**</span></span>|<span data-ttu-id="55fb9-113">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="55fb9-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="55fb9-114">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="55fb9-114">**Send handler**</span></span>|<span data-ttu-id="55fb9-115">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="55fb9-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="55fb9-116">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="55fb9-116">**Send pipeline**</span></span>|<span data-ttu-id="55fb9-117">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="55fb9-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="55fb9-118">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55fb9-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="55fb9-119">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="55fb9-119">**Use this**</span></span>|<span data-ttu-id="55fb9-120">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="55fb9-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="55fb9-121">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="55fb9-121">**Property**</span></span>|<span data-ttu-id="55fb9-122">Seleccione BTS. MessageType</span><span class="sxs-lookup"><span data-stu-id="55fb9-122">Select BTS.MessageType</span></span>|  
    |<span data-ttu-id="55fb9-123">**Operador**</span><span class="sxs-lookup"><span data-stu-id="55fb9-123">**Operator**</span></span>|<span data-ttu-id="55fb9-124">Seleccione ==</span><span class="sxs-lookup"><span data-stu-id="55fb9-124">Select ==</span></span>|  
    |<span data-ttu-id="55fb9-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="55fb9-125">**Value**</span></span>|<span data-ttu-id="55fb9-126">Tipo Sw-HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="55fb9-126">Type Sw-HandleFileEventRequest</span></span>|  
    |<span data-ttu-id="55fb9-127">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="55fb9-127">**Group**</span></span>|<span data-ttu-id="55fb9-128">O bien</span><span class="sxs-lookup"><span data-stu-id="55fb9-128">Or</span></span>|  
    |<span data-ttu-id="55fb9-129">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="55fb9-129">**Property**</span></span>|<span data-ttu-id="55fb9-130">Seleccione BTS.</span><span class="sxs-lookup"><span data-stu-id="55fb9-130">Select BTS.</span></span> <span data-ttu-id="55fb9-131">MessageType</span><span class="sxs-lookup"><span data-stu-id="55fb9-131">MessageType</span></span>|  
    |<span data-ttu-id="55fb9-132">**Operador**</span><span class="sxs-lookup"><span data-stu-id="55fb9-132">**Operator**</span></span>|<span data-ttu-id="55fb9-133">Seleccione ==</span><span class="sxs-lookup"><span data-stu-id="55fb9-133">Select ==</span></span>|  
    |<span data-ttu-id="55fb9-134">**Valor**</span><span class="sxs-lookup"><span data-stu-id="55fb9-134">**Value**</span></span>|<span data-ttu-id="55fb9-135">Tipo Sw-ExchangeSnFResponse</span><span class="sxs-lookup"><span data-stu-id="55fb9-135">Type Sw-ExchangeSnFResponse</span></span>|