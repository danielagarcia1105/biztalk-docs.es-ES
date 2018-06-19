---
title: 'Paso 3F: agregar un puerto de envío de archivos para el escenario en tiempo real de FileAct capturar los mensajes de Sw-HandleFileEventRequest | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b7594b0-0443-41b7-ae04-55b2cc8bf90e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1d70c338696f1c4455161a88c8d2988e0ea0ccb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225532"
---
# <a name="step-3f-add-a-file-send-port-for-the-fileact-real-time-scenario-to-capture-sw-handlefileeventrequest-messages"></a><span data-ttu-id="cebe0-102">Paso 3F: agregar un puerto de envío de archivos para el escenario en tiempo real de FileAct capturar los mensajes de Sw-HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="cebe0-102">Step 3F: Add a FILE Send Port for the FileAct Real-Time Scenario to Capture Sw-HandleFileEventRequest Messages</span></span>
<span data-ttu-id="cebe0-103">Antes de comenzar este paso, debe completar [paso 3E: agregar un puerto de envío de archivo para capturar Sw:ExchangeFileResponse mensaje para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)</span><span class="sxs-lookup"><span data-stu-id="cebe0-103">Before you begin this step, you must complete [Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a><span data-ttu-id="cebe0-104">Para agregar un puerto de envío de archivo para capturar los eventos de estado:</span><span class="sxs-lookup"><span data-stu-id="cebe0-104">To add a FILE send port to capture Status Events:</span></span>  
  
1.  <span data-ttu-id="cebe0-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="cebe0-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="cebe0-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="cebe0-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="cebe0-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="cebe0-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
4.  <span data-ttu-id="cebe0-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_ GetStatusReports.</span><span class="sxs-lookup"><span data-stu-id="cebe0-108">In the **Send Port Properties** window, name the send port, Tutorial_ GetStatusReports.</span></span>  
  
5.  <span data-ttu-id="cebe0-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="cebe0-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="cebe0-110">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba C:\SWIFTAdapterTutorial\Fileact\ StatusEvents y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cebe0-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ StatusEvents, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="cebe0-111">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cebe0-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="cebe0-112">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="cebe0-112">**Use this**</span></span>|<span data-ttu-id="cebe0-113">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="cebe0-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="cebe0-114">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="cebe0-114">**Send handler**</span></span>|<span data-ttu-id="cebe0-115">En la lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="cebe0-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="cebe0-116">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="cebe0-116">**Send pipeline**</span></span>|<span data-ttu-id="cebe0-117">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="cebe0-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="cebe0-118">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cebe0-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="cebe0-119">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="cebe0-119">**Use this**</span></span>|<span data-ttu-id="cebe0-120">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="cebe0-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="cebe0-121">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="cebe0-121">**Property**</span></span>|<span data-ttu-id="cebe0-122">Seleccione BTS.</span><span class="sxs-lookup"><span data-stu-id="cebe0-122">Select BTS.</span></span> <span data-ttu-id="cebe0-123">MessageType</span><span class="sxs-lookup"><span data-stu-id="cebe0-123">MessageType</span></span>|  
    |<span data-ttu-id="cebe0-124">**Operador**</span><span class="sxs-lookup"><span data-stu-id="cebe0-124">**Operator**</span></span>|<span data-ttu-id="cebe0-125">Seleccione ==</span><span class="sxs-lookup"><span data-stu-id="cebe0-125">Select ==</span></span>|  
    |<span data-ttu-id="cebe0-126">**Valor**</span><span class="sxs-lookup"><span data-stu-id="cebe0-126">**Value**</span></span>|<span data-ttu-id="cebe0-127">Tipo Sw-HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="cebe0-127">Type Sw-HandleFileEventRequest</span></span>|  
    |<span data-ttu-id="cebe0-128">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="cebe0-128">**Group**</span></span>|<span data-ttu-id="cebe0-129">O bien</span><span class="sxs-lookup"><span data-stu-id="cebe0-129">Or</span></span>|  
    |<span data-ttu-id="cebe0-130">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="cebe0-130">**Property**</span></span>|<span data-ttu-id="cebe0-131">Seleccione BTS.</span><span class="sxs-lookup"><span data-stu-id="cebe0-131">Select BTS.</span></span> <span data-ttu-id="cebe0-132">MessageType</span><span class="sxs-lookup"><span data-stu-id="cebe0-132">MessageType</span></span>|  
    |<span data-ttu-id="cebe0-133">**Operador**</span><span class="sxs-lookup"><span data-stu-id="cebe0-133">**Operator**</span></span>|<span data-ttu-id="cebe0-134">Seleccione ==</span><span class="sxs-lookup"><span data-stu-id="cebe0-134">Select ==</span></span>|  
    |<span data-ttu-id="cebe0-135">**Valor**</span><span class="sxs-lookup"><span data-stu-id="cebe0-135">**Value**</span></span>|<span data-ttu-id="cebe0-136">Tipo Sw-ExchangeSnFResponse</span><span class="sxs-lookup"><span data-stu-id="cebe0-136">Type Sw-ExchangeSnFResponse</span></span>|