---
title: 'Paso 7: Crear un puerto de envío para entregar el ADT ^ A03 mensaje para su uso del adaptador de MLLP | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: d9e7f281-3d25-4675-a13e-0e2057f5e69a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540a8745da811e7f14ab6ac5c1909bffe057c5f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006109"
---
# <a name="step-7-create-a-send-port-to-deliver-the-adta03-message-to-his-using-the-mllp-adapter"></a><span data-ttu-id="046c6-102">Paso 7: Crear un puerto de envío para entregar el ADT ^ A03 mensaje para su uso del adaptador de MLLP</span><span class="sxs-lookup"><span data-stu-id="046c6-102">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>
<span data-ttu-id="046c6-103">En este paso, creará el puerto de envío para enviar el mensaje a del sistema de información de Hospital (HIS) mediante el adaptador de MLLP.</span><span class="sxs-lookup"><span data-stu-id="046c6-103">In this step, you create the send port to send the message to the Hospital Information System (HIS) using the MLLP adapter.</span></span>  

### <a name="to-create-the-tutorialmllpsend-send-port"></a><span data-ttu-id="046c6-104">Para crear el puerto de envío Tutorial_MllpSend</span><span class="sxs-lookup"><span data-stu-id="046c6-104">To create the Tutorial_MllpSend send port</span></span>  

1. <span data-ttu-id="046c6-105">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="046c6-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="046c6-106">En el cuadro de diálogo Propiedades de puerto de envío, realice las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="046c6-106">In the Send Port Properties dialog box, do the following actions:</span></span>  


   |      <span data-ttu-id="046c6-107">Use</span><span class="sxs-lookup"><span data-stu-id="046c6-107">Use this</span></span>      |                                <span data-ttu-id="046c6-108">Para</span><span class="sxs-lookup"><span data-stu-id="046c6-108">To do this</span></span>                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      <span data-ttu-id="046c6-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="046c6-109">**Name**</span></span>      |                        <span data-ttu-id="046c6-110">Tipo **Tutorial_MllpSend**.</span><span class="sxs-lookup"><span data-stu-id="046c6-110">Type **Tutorial_MllpSend**.</span></span>                        |
   | <span data-ttu-id="046c6-111">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="046c6-111">**Transport type**</span></span> |                 <span data-ttu-id="046c6-112">Seleccione **MLLP** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="046c6-112">Select **MLLP** from the drop-down list.</span></span>                  |
   |   <span data-ttu-id="046c6-113">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="046c6-113">**Configure**</span></span>    | <span data-ttu-id="046c6-114">Haga clic en **configurar** para abrir el **propiedades de transporte de MLLP** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="046c6-114">Click **Configure** to open the **MLLP Transport Properties** dialog box.</span></span> |


3. <span data-ttu-id="046c6-115">En el cuadro de diálogo Propiedades de transporte de MLLP, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="046c6-115">In the MLLP Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  


   |      <span data-ttu-id="046c6-116">Use</span><span class="sxs-lookup"><span data-stu-id="046c6-116">Use this</span></span>       |     <span data-ttu-id="046c6-117">Para</span><span class="sxs-lookup"><span data-stu-id="046c6-117">To do this</span></span>      |
   |---------------------|---------------------|
   | <span data-ttu-id="046c6-118">**Nombre de conexión**</span><span class="sxs-lookup"><span data-stu-id="046c6-118">**Connection Name**</span></span> | <span data-ttu-id="046c6-119">Tipo **1WaySend**.</span><span class="sxs-lookup"><span data-stu-id="046c6-119">Type **1WaySend**.</span></span>  |
   |      <span data-ttu-id="046c6-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="046c6-120">**Host**</span></span>       | <span data-ttu-id="046c6-121">Tipo **localhost**.</span><span class="sxs-lookup"><span data-stu-id="046c6-121">Type **localhost**.</span></span> |
   |      <span data-ttu-id="046c6-122">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="046c6-122">**Port**</span></span>       |   <span data-ttu-id="046c6-123">Tipo **14000**.</span><span class="sxs-lookup"><span data-stu-id="046c6-123">Type **14000**.</span></span>   |


4. <span data-ttu-id="046c6-124">En el cuadro de diálogo Propiedades de puerto de envío para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="046c6-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="046c6-125">En el panel izquierdo, seleccione **filtros**, y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="046c6-125">In the left pane, select **Filters**, and then do the following:</span></span>  

   |<span data-ttu-id="046c6-126">Use</span><span class="sxs-lookup"><span data-stu-id="046c6-126">Use this</span></span>|<span data-ttu-id="046c6-127">Para</span><span class="sxs-lookup"><span data-stu-id="046c6-127">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="046c6-128">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="046c6-128">**Property**</span></span>|<span data-ttu-id="046c6-129">Seleccione **BTS. ReceivePortName** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="046c6-129">Select **BTS.ReceivePortName** from the drop-down list.</span></span>|  
   |<span data-ttu-id="046c6-130">**Operador**</span><span class="sxs-lookup"><span data-stu-id="046c6-130">**Operator**</span></span>|<span data-ttu-id="046c6-131">Seleccione **==** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="046c6-131">Select **==** from the drop-down list.</span></span>|  
   |<span data-ttu-id="046c6-132">**Value**</span><span class="sxs-lookup"><span data-stu-id="046c6-132">**Value**</span></span>|<span data-ttu-id="046c6-133">Tipo **Tutorial_1WayReceive**.</span><span class="sxs-lookup"><span data-stu-id="046c6-133">Type **Tutorial_1WayReceive**.</span></span>|  

   > [!NOTE]
   >  <span data-ttu-id="046c6-134">El puerto realizará escuchas para el puerto especificado en 1WayReceive para todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="046c6-134">The port will listen to the port specified in 1WayReceive for any messages.</span></span>  

6. <span data-ttu-id="046c6-135">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="046c6-135">Click **Apply**, and then click **OK.**</span></span>  

7. <span data-ttu-id="046c6-136">En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_MllpSend**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="046c6-136">In the Administration Console, click **Send Ports**, right-click **Tutorial_MllpSend**, and then click **Start**.</span></span>  

   <span data-ttu-id="046c6-137">Continúe con [paso 8: configurar la información de entidad](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md).</span><span class="sxs-lookup"><span data-stu-id="046c6-137">Proceed to [Step 8: Configure Party Information](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md).</span></span>