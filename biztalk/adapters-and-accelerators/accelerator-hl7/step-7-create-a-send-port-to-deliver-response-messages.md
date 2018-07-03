---
title: 'Paso 7: Crear un puerto de envío para entregar los mensajes de respuesta | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: 5edaefb6-72f2-4317-9477-f3a0d0027e0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4139e07c5ca503a8cb58b1aa88fe8e602a92ee07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987829"
---
# <a name="step-7-create-a-send-port-to-deliver-response-messages"></a><span data-ttu-id="1b06c-102">Paso 7: Crear un puerto de envío para entregar los mensajes de respuesta</span><span class="sxs-lookup"><span data-stu-id="1b06c-102">Step 7: Create a Send Port to Deliver Response Messages</span></span>
<span data-ttu-id="1b06c-103">En este paso, creará el puerto de envío para entregar las respuestas de consulta a los pacientes, descarga y transferir (ADT) sistema.</span><span class="sxs-lookup"><span data-stu-id="1b06c-103">In this step, you create the send port to deliver the query responses back to the Admissions, Discharge, and Transfer (ADT) system.</span></span>  

### <a name="to-create-the-adtsend-send-port"></a><span data-ttu-id="1b06c-104">Para crear el puerto de envío ADT_Send</span><span class="sxs-lookup"><span data-stu-id="1b06c-104">To create the ADT_Send send port</span></span>  

1. <span data-ttu-id="1b06c-105">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, seleccione **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then select **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="1b06c-106">En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b06c-106">In the Send Port Properties dialog box, do the following:</span></span>  


   |      <span data-ttu-id="1b06c-107">Use</span><span class="sxs-lookup"><span data-stu-id="1b06c-107">Use this</span></span>      |                        <span data-ttu-id="1b06c-108">Para</span><span class="sxs-lookup"><span data-stu-id="1b06c-108">To do this</span></span>                        |
   |--------------------|----------------------------------------------------------|
   |      <span data-ttu-id="1b06c-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1b06c-109">**Name**</span></span>      |                    <span data-ttu-id="1b06c-110">Tipo **ADT_Send**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-110">Type **ADT_Send**.</span></span>                    |
   | <span data-ttu-id="1b06c-111">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="1b06c-111">**Transport type**</span></span> |                     <span data-ttu-id="1b06c-112">Seleccione **MLLP**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-112">Select **MLLP**.</span></span>                     |
   |   <span data-ttu-id="1b06c-113">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="1b06c-113">**Configure**</span></span>    | <span data-ttu-id="1b06c-114">Haga clic en el **configurar** situado a la derecha de **tipo**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-114">Click the **Configure** button to the right of **Type**.</span></span> |


3. <span data-ttu-id="1b06c-115">En el cuadro de diálogo Propiedades de transporte de MLLP, escriba la información siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-115">In the MLLP Transport Properties dialog box, enter the following information, and then click **OK**.</span></span>  


   |      <span data-ttu-id="1b06c-116">Use</span><span class="sxs-lookup"><span data-stu-id="1b06c-116">Use this</span></span>       |       <span data-ttu-id="1b06c-117">Para</span><span class="sxs-lookup"><span data-stu-id="1b06c-117">To do this</span></span>       |
   |---------------------|------------------------|
   | <span data-ttu-id="1b06c-118">**Nombre de conexión**</span><span class="sxs-lookup"><span data-stu-id="1b06c-118">**Connection Name**</span></span> | <span data-ttu-id="1b06c-119">Tipo **ADT_SendMLLP**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-119">Type **ADT_SendMLLP**.</span></span> |
   |      <span data-ttu-id="1b06c-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="1b06c-120">**Host**</span></span>       |  <span data-ttu-id="1b06c-121">Tipo **localhost**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-121">Type **localhost**.</span></span>   |
   |      <span data-ttu-id="1b06c-122">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="1b06c-122">**Port**</span></span>       |    <span data-ttu-id="1b06c-123">Tipo **25000**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-123">Type **25000**.</span></span>     |


4. <span data-ttu-id="1b06c-124">En el cuadro de diálogo Propiedades de puerto de envío para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="1b06c-125">En el árbol de consola, haga clic en **filtros**, y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b06c-125">In the Console Tree, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="1b06c-126">Use</span><span class="sxs-lookup"><span data-stu-id="1b06c-126">Use this</span></span>   |                                        <span data-ttu-id="1b06c-127">Para</span><span class="sxs-lookup"><span data-stu-id="1b06c-127">To do this</span></span>                                        |
   |--------------|------------------------------------------------------------------------------------------|
   | <span data-ttu-id="1b06c-128">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1b06c-128">**Property**</span></span> |                               <span data-ttu-id="1b06c-129">Seleccione **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-129">Select **BTS.MessageType**.</span></span>                                |
   | <span data-ttu-id="1b06c-130">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1b06c-130">**Operator**</span></span> |                          <span data-ttu-id="1b06c-131">Seleccione **==** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1b06c-131">Select **==** from the drop-down list.</span></span>                          |
   |  <span data-ttu-id="1b06c-132">**Value**</span><span class="sxs-lookup"><span data-stu-id="1b06c-132">**Value**</span></span>   |          <span data-ttu-id="1b06c-133">Tipo **<http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF>**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-133">Type **<http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF>**.</span></span>           |
   | <span data-ttu-id="1b06c-134">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="1b06c-134">**Group By**</span></span> |                         <span data-ttu-id="1b06c-135">Seleccione **AND** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1b06c-135">Select **AND** from the drop-down list.</span></span>                          |
   | <span data-ttu-id="1b06c-136">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="1b06c-136">**Property**</span></span> | <span data-ttu-id="1b06c-137">En la primera propiedad, haga clic en el cuadro en blanco y, a continuación, seleccione **BTAHL7Schemas.MSH5_1**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-137">Under the first property, click the blank box, and then select **BTAHL7Schemas.MSH5_1**.</span></span> |
   | <span data-ttu-id="1b06c-138">**Operador**</span><span class="sxs-lookup"><span data-stu-id="1b06c-138">**Operator**</span></span> |                          <span data-ttu-id="1b06c-139">Seleccione **==** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1b06c-139">Select **==** from the drop-down list.</span></span>                          |
   |  <span data-ttu-id="1b06c-140">**Value**</span><span class="sxs-lookup"><span data-stu-id="1b06c-140">**Value**</span></span>   |                                      <span data-ttu-id="1b06c-141">Tipo **ADT**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-141">Type **ADT**.</span></span>                                       |

   > [!NOTE]
   >  <span data-ttu-id="1b06c-142">El primer filtro especifica que el puerto de envío solo selecciona los mensajes sean conformes al DSR ^ esquema Q01 que creó en el paso 3A.</span><span class="sxs-lookup"><span data-stu-id="1b06c-142">The first filter specifies that the send port only selects messages conforming to the DSR^Q01 schema you created in step 3A.</span></span> <span data-ttu-id="1b06c-143">El segundo filtro especifica el destino al que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor interfaz envía estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="1b06c-143">The second filter specifies the destination to which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine sends these messages.</span></span>  

6. <span data-ttu-id="1b06c-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-144">Click **OK**.</span></span>  

7. <span data-ttu-id="1b06c-145">En la consola de administración, haga clic en **puertos de envío**, haga clic en **ADT_Send**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="1b06c-145">In the Administration Console, click **Send Ports**, right-click **ADT_Send**, and then click **Start**.</span></span>  

   <span data-ttu-id="1b06c-146">Continúe con [paso 8: configurar la información de entidad](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md).</span><span class="sxs-lookup"><span data-stu-id="1b06c-146">Proceed to [Step 8: Configure Party Information](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md).</span></span>