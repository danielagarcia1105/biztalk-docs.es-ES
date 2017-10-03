---
title: "Paso 7: Crear un puerto de envío para entregar el ADT ^ A03 mensaje a su usa el adaptador MLLP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: d9e7f281-3d25-4675-a13e-0e2057f5e69a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc122ab37ee0d618c3bd75792a5b88571dd49162
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-create-a-send-port-to-deliver-the-adta03-message-to-his-using-the-mllp-adapter"></a><span data-ttu-id="722af-102">Paso 7: Crear un puerto de envío para entregar el ADT ^ A03 mensaje a su usa el adaptador MLLP</span><span class="sxs-lookup"><span data-stu-id="722af-102">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>
<span data-ttu-id="722af-103">En este paso, creará el puerto de envío para enviar el mensaje para el sistema de información Hospital (HIS) que se usa el adaptador MLLP.</span><span class="sxs-lookup"><span data-stu-id="722af-103">In this step, you create the send port to send the message to the Hospital Information System (HIS) using the MLLP adapter.</span></span>  
  
### <a name="to-create-the-tutorialmllpsend-send-port"></a><span data-ttu-id="722af-104">Para crear el puerto de envío Tutorial_MllpSend</span><span class="sxs-lookup"><span data-stu-id="722af-104">To create the Tutorial_MllpSend send port</span></span>  
  
1.  <span data-ttu-id="722af-105">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="722af-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="722af-106">En el cuadro de diálogo Propiedades de puerto de envío, realice las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="722af-106">In the Send Port Properties dialog box, do the following actions:</span></span>  
  
    |<span data-ttu-id="722af-107">Use</span><span class="sxs-lookup"><span data-stu-id="722af-107">Use this</span></span>|<span data-ttu-id="722af-108">Para</span><span class="sxs-lookup"><span data-stu-id="722af-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="722af-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="722af-109">**Name**</span></span>|<span data-ttu-id="722af-110">Tipo de **Tutorial_MllpSend**.</span><span class="sxs-lookup"><span data-stu-id="722af-110">Type **Tutorial_MllpSend**.</span></span>|  
    |<span data-ttu-id="722af-111">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="722af-111">**Transport type**</span></span>|<span data-ttu-id="722af-112">Seleccione **MLLP** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="722af-112">Select **MLLP** from the drop-down list.</span></span>|  
    |<span data-ttu-id="722af-113">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="722af-113">**Configure**</span></span>|<span data-ttu-id="722af-114">Haga clic en **configurar** para abrir el **propiedades de transporte de MLLP** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="722af-114">Click **Configure** to open the **MLLP Transport Properties** dialog box.</span></span>|  
  
3.  <span data-ttu-id="722af-115">En el cuadro de diálogo Propiedades de transporte de MLLP, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="722af-115">In the MLLP Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  
  
    |<span data-ttu-id="722af-116">Use</span><span class="sxs-lookup"><span data-stu-id="722af-116">Use this</span></span>|<span data-ttu-id="722af-117">Para</span><span class="sxs-lookup"><span data-stu-id="722af-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="722af-118">**Nombre de conexión**</span><span class="sxs-lookup"><span data-stu-id="722af-118">**Connection Name**</span></span>|<span data-ttu-id="722af-119">Tipo de **1WaySend**.</span><span class="sxs-lookup"><span data-stu-id="722af-119">Type **1WaySend**.</span></span>|  
    |<span data-ttu-id="722af-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="722af-120">**Host**</span></span>|<span data-ttu-id="722af-121">Tipo de **localhost**.</span><span class="sxs-lookup"><span data-stu-id="722af-121">Type **localhost**.</span></span>|  
    |<span data-ttu-id="722af-122">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="722af-122">**Port**</span></span>|<span data-ttu-id="722af-123">Tipo de **14000**.</span><span class="sxs-lookup"><span data-stu-id="722af-123">Type **14000**.</span></span>|  
  
4.  <span data-ttu-id="722af-124">En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="722af-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="722af-125">En el panel izquierdo, seleccione **filtros**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="722af-125">In the left pane, select **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="722af-126">Use</span><span class="sxs-lookup"><span data-stu-id="722af-126">Use this</span></span>|<span data-ttu-id="722af-127">Para</span><span class="sxs-lookup"><span data-stu-id="722af-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="722af-128">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="722af-128">**Property**</span></span>|<span data-ttu-id="722af-129">Seleccione **BTS. ReceivePortName** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="722af-129">Select **BTS.ReceivePortName** from the drop-down list.</span></span>|  
    |<span data-ttu-id="722af-130">**Operador**</span><span class="sxs-lookup"><span data-stu-id="722af-130">**Operator**</span></span>|<span data-ttu-id="722af-131">Seleccione  **==**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="722af-131">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="722af-132">**Valor**</span><span class="sxs-lookup"><span data-stu-id="722af-132">**Value**</span></span>|<span data-ttu-id="722af-133">Tipo de **Tutorial_1WayReceive**.</span><span class="sxs-lookup"><span data-stu-id="722af-133">Type **Tutorial_1WayReceive**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="722af-134">El puerto realizará escuchas para el puerto especificado en 1WayReceive para los mensajes.</span><span class="sxs-lookup"><span data-stu-id="722af-134">The port will listen to the port specified in 1WayReceive for any messages.</span></span>  
  
6.  <span data-ttu-id="722af-135">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="722af-135">Click **Apply**, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="722af-136">En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_MllpSend**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="722af-136">In the Administration Console, click **Send Ports**, right-click **Tutorial_MllpSend**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="722af-137">Continúe con [paso 8: configurar la información de entidad](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md).</span><span class="sxs-lookup"><span data-stu-id="722af-137">Proceed to [Step 8: Configure Party Information](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md).</span></span>