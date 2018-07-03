---
title: 'Paso 6: Crear un puerto de envío para entregar los mensajes de consulta | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: a3cfa2aa-888d-4a82-9eb3-2e9cc29ee582
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e65ec7bc4e04850907609fc6d1d63e6f166593
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004053"
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a><span data-ttu-id="39bee-102">Paso 6: Crear un puerto de envío para entregar los mensajes de consulta</span><span class="sxs-lookup"><span data-stu-id="39bee-102">Step 6: Create a Send Port to Deliver Query Messages</span></span>
<span data-ttu-id="39bee-103">En este paso, creará el puerto de envío para entregar las consultas entrantes (QRY ^ Q01 mensajes) para el sistema de información de Hospital (HIS).</span><span class="sxs-lookup"><span data-stu-id="39bee-103">In this step, you create the send port to deliver the incoming queries (QRY^Q01 messages) to the Hospital Information System (HIS).</span></span>  

### <a name="to-create-the-hissend-send-port"></a><span data-ttu-id="39bee-104">Para crear el puerto de envío HIS_Send</span><span class="sxs-lookup"><span data-stu-id="39bee-104">To create the HIS_Send send port</span></span>  

1. <span data-ttu-id="39bee-105">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, seleccione **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="39bee-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then select **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="39bee-106">En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39bee-106">In the Send Port Properties dialog box, do the following:</span></span>  


   |      <span data-ttu-id="39bee-107">Use</span><span class="sxs-lookup"><span data-stu-id="39bee-107">Use this</span></span>      |                        <span data-ttu-id="39bee-108">Para</span><span class="sxs-lookup"><span data-stu-id="39bee-108">To do this</span></span>                        |
   |--------------------|----------------------------------------------------------|
   |      <span data-ttu-id="39bee-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="39bee-109">**Name**</span></span>      |                    <span data-ttu-id="39bee-110">Tipo **HIS_Send**.</span><span class="sxs-lookup"><span data-stu-id="39bee-110">Type **HIS_Send**.</span></span>                    |
   | <span data-ttu-id="39bee-111">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="39bee-111">**Transport type**</span></span> |                     <span data-ttu-id="39bee-112">Seleccione **MLLP**.</span><span class="sxs-lookup"><span data-stu-id="39bee-112">Select **MLLP**.</span></span>                     |
   |   <span data-ttu-id="39bee-113">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="39bee-113">**Configure**</span></span>    | <span data-ttu-id="39bee-114">Haga clic en el **configurar** situado a la derecha de **tipo**.</span><span class="sxs-lookup"><span data-stu-id="39bee-114">Click the **Configure** button to the right of **Type**.</span></span> |


3. <span data-ttu-id="39bee-115">En el cuadro de diálogo Propiedades de transporte de MLLP, escriba la información siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39bee-115">In the MLLP Transport Properties dialog box, enter the following information and then click **OK**.</span></span>  


   |      <span data-ttu-id="39bee-116">Use</span><span class="sxs-lookup"><span data-stu-id="39bee-116">Use this</span></span>       |       <span data-ttu-id="39bee-117">Para</span><span class="sxs-lookup"><span data-stu-id="39bee-117">To do this</span></span>       |
   |---------------------|------------------------|
   | <span data-ttu-id="39bee-118">**Nombre de conexión**</span><span class="sxs-lookup"><span data-stu-id="39bee-118">**Connection Name**</span></span> | <span data-ttu-id="39bee-119">Tipo **HIS_SendMLLP**.</span><span class="sxs-lookup"><span data-stu-id="39bee-119">Type **HIS_SendMLLP**.</span></span> |
   |      <span data-ttu-id="39bee-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="39bee-120">**Host**</span></span>       |  <span data-ttu-id="39bee-121">Tipo **localhost**.</span><span class="sxs-lookup"><span data-stu-id="39bee-121">Type **localhost**.</span></span>   |
   |      <span data-ttu-id="39bee-122">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="39bee-122">**Port**</span></span>       |    <span data-ttu-id="39bee-123">Tipo **24000**.</span><span class="sxs-lookup"><span data-stu-id="39bee-123">Type **24000**.</span></span>     |


4. <span data-ttu-id="39bee-124">En el cuadro de diálogo Propiedades de puerto de envío para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="39bee-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="39bee-125">En el árbol de consola, haga clic en **filtros**, y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39bee-125">In the Console Tree, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="39bee-126">Use</span><span class="sxs-lookup"><span data-stu-id="39bee-126">Use this</span></span>   |                              <span data-ttu-id="39bee-127">Para</span><span class="sxs-lookup"><span data-stu-id="39bee-127">To do this</span></span>                               |
   |--------------|-----------------------------------------------------------------------|
   | <span data-ttu-id="39bee-128">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="39bee-128">**Property**</span></span> |             <span data-ttu-id="39bee-129">Para **propiedad**, seleccione **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="39bee-129">For **Property**, select **BTS.MessageType**.</span></span>             |
   | <span data-ttu-id="39bee-130">**Operador**</span><span class="sxs-lookup"><span data-stu-id="39bee-130">**Operator**</span></span> |                <span data-ttu-id="39bee-131">Seleccione **==** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="39bee-131">Select **==** from the drop-down list.</span></span>                 |
   |  <span data-ttu-id="39bee-132">**Value**</span><span class="sxs-lookup"><span data-stu-id="39bee-132">**Value**</span></span>   | <span data-ttu-id="39bee-133">Tipo **<http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF>**.</span><span class="sxs-lookup"><span data-stu-id="39bee-133">Type **<http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF>**.</span></span> |
   | <span data-ttu-id="39bee-134">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="39bee-134">**Group By**</span></span> |                <span data-ttu-id="39bee-135">Seleccione **AND** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="39bee-135">Select **AND** from the drop-down list.</span></span>                |
   | <span data-ttu-id="39bee-136">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="39bee-136">**Property**</span></span> | <span data-ttu-id="39bee-137">Para **propiedad** en la segunda línea, seleccione **BTAHL7Schemas.MSH5_1**.</span><span class="sxs-lookup"><span data-stu-id="39bee-137">For **Property** on the second line, select **BTAHL7Schemas.MSH5_1**.</span></span> |
   | <span data-ttu-id="39bee-138">**Operador**</span><span class="sxs-lookup"><span data-stu-id="39bee-138">**Operator**</span></span> |                <span data-ttu-id="39bee-139">Seleccione **==** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="39bee-139">Select **==** from the drop-down list.</span></span>                 |
   |  <span data-ttu-id="39bee-140">**Value**</span><span class="sxs-lookup"><span data-stu-id="39bee-140">**Value**</span></span>   |                             <span data-ttu-id="39bee-141">Tipo **HIS**.</span><span class="sxs-lookup"><span data-stu-id="39bee-141">Type **HIS**.</span></span>                             |

   > [!NOTE]
   >  <span data-ttu-id="39bee-142">El primer filtro especifica que el puerto de envío solo selecciona los mensajes que cumplen el QRY ^ esquema Q01 que creó en el paso 3A.</span><span class="sxs-lookup"><span data-stu-id="39bee-142">The first filter specifies that the send port only selects messages conforming to the QRY^Q01 schema you created in step 3A.</span></span> <span data-ttu-id="39bee-143">El segundo filtro especifica el destino al que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor interfaz envía estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="39bee-143">The second filter specifies the destination to which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine sends these messages.</span></span>  

6. <span data-ttu-id="39bee-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39bee-144">Click **OK**.</span></span>  

7. <span data-ttu-id="39bee-145">En la consola de administración, seleccione **puertos de envío**, haga clic en **HIS_Send**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="39bee-145">In the Administration console, select **Send Ports**, right-click **HIS_Send**, and then click **Start**.</span></span>  

   <span data-ttu-id="39bee-146">Continúe con [paso 7: crear un puerto de envío para entregar los mensajes de respuesta](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md).</span><span class="sxs-lookup"><span data-stu-id="39bee-146">Proceed to [Step 7: Create a Send Port to Deliver Response Messages](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md).</span></span>