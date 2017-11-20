---
title: "Paso 7: Crear un puerto de envío para entregar los mensajes de respuesta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, send ports
ms.assetid: 5edaefb6-72f2-4317-9477-f3a0d0027e0c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1260772f3b3df5f0dea96b0aa66023e107b9aa6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-create-a-send-port-to-deliver-response-messages"></a><span data-ttu-id="e14e3-102">Paso 7: Crear un puerto de envío para entregar los mensajes de respuesta</span><span class="sxs-lookup"><span data-stu-id="e14e3-102">Step 7: Create a Send Port to Deliver Response Messages</span></span>
<span data-ttu-id="e14e3-103">En este paso, creará el puerto de envío para entregar las respuestas de consulta a la admisión, descarga y transferir (ADT) sistema.</span><span class="sxs-lookup"><span data-stu-id="e14e3-103">In this step, you create the send port to deliver the query responses back to the Admissions, Discharge, and Transfer (ADT) system.</span></span>  
  
### <a name="to-create-the-adtsend-send-port"></a><span data-ttu-id="e14e3-104">Para crear el puerto de envío ADT_Send</span><span class="sxs-lookup"><span data-stu-id="e14e3-104">To create the ADT_Send send port</span></span>  
  
1.  <span data-ttu-id="e14e3-105">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, seleccione **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then select **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="e14e3-106">En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e14e3-106">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="e14e3-107">Use</span><span class="sxs-lookup"><span data-stu-id="e14e3-107">Use this</span></span>|<span data-ttu-id="e14e3-108">Para</span><span class="sxs-lookup"><span data-stu-id="e14e3-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e14e3-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e14e3-109">**Name**</span></span>|<span data-ttu-id="e14e3-110">Tipo de **ADT_Send**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-110">Type **ADT_Send**.</span></span>|  
    |<span data-ttu-id="e14e3-111">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="e14e3-111">**Transport type**</span></span>|<span data-ttu-id="e14e3-112">Seleccione **MLLP**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-112">Select **MLLP**.</span></span>|  
    |<span data-ttu-id="e14e3-113">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="e14e3-113">**Configure**</span></span>|<span data-ttu-id="e14e3-114">Haga clic en el **configurar** situado a la derecha de **tipo**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-114">Click the **Configure** button to the right of **Type**.</span></span>|  
  
3.  <span data-ttu-id="e14e3-115">En el cuadro de diálogo Propiedades de transporte de MLLP, escriba la información siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-115">In the MLLP Transport Properties dialog box, enter the following information, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="e14e3-116">Use</span><span class="sxs-lookup"><span data-stu-id="e14e3-116">Use this</span></span>|<span data-ttu-id="e14e3-117">Para</span><span class="sxs-lookup"><span data-stu-id="e14e3-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e14e3-118">**Nombre de conexión**</span><span class="sxs-lookup"><span data-stu-id="e14e3-118">**Connection Name**</span></span>|<span data-ttu-id="e14e3-119">Tipo de **ADT_SendMLLP**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-119">Type **ADT_SendMLLP**.</span></span>|  
    |<span data-ttu-id="e14e3-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="e14e3-120">**Host**</span></span>|<span data-ttu-id="e14e3-121">Tipo de **localhost**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-121">Type **localhost**.</span></span>|  
    |<span data-ttu-id="e14e3-122">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="e14e3-122">**Port**</span></span>|<span data-ttu-id="e14e3-123">Tipo de **25000**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-123">Type **25000**.</span></span>|  
  
4.  <span data-ttu-id="e14e3-124">En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="e14e3-125">En el árbol de consola, haga clic en **filtros**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e14e3-125">In the Console Tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="e14e3-126">Use</span><span class="sxs-lookup"><span data-stu-id="e14e3-126">Use this</span></span>|<span data-ttu-id="e14e3-127">Para</span><span class="sxs-lookup"><span data-stu-id="e14e3-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e14e3-128">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="e14e3-128">**Property**</span></span>|<span data-ttu-id="e14e3-129">Seleccione **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-129">Select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="e14e3-130">**Operador**</span><span class="sxs-lookup"><span data-stu-id="e14e3-130">**Operator**</span></span>|<span data-ttu-id="e14e3-131">Seleccione  **==**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e14e3-131">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="e14e3-132">**Valor**</span><span class="sxs-lookup"><span data-stu-id="e14e3-132">**Value**</span></span>|<span data-ttu-id="e14e3-133">Tipo de **http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-133">Type **http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="e14e3-134">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="e14e3-134">**Group By**</span></span>|<span data-ttu-id="e14e3-135">Seleccione **AND** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e14e3-135">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="e14e3-136">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="e14e3-136">**Property**</span></span>|<span data-ttu-id="e14e3-137">En la primera propiedad, haga clic en el cuadro en blanco y, a continuación, seleccione **BTAHL7Schemas.MSH5_1**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-137">Under the first property, click the blank box, and then select **BTAHL7Schemas.MSH5_1**.</span></span>|  
    |<span data-ttu-id="e14e3-138">**Operador**</span><span class="sxs-lookup"><span data-stu-id="e14e3-138">**Operator**</span></span>|<span data-ttu-id="e14e3-139">Seleccione  **==**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e14e3-139">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="e14e3-140">**Valor**</span><span class="sxs-lookup"><span data-stu-id="e14e3-140">**Value**</span></span>|<span data-ttu-id="e14e3-141">Tipo de **ADT**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-141">Type **ADT**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="e14e3-142">El primer filtro especifica que el puerto de envío selecciona sólo mensajes sean conformes al DSR ^ esquema Q01 que creó en el paso 3A.</span><span class="sxs-lookup"><span data-stu-id="e14e3-142">The first filter specifies that the send port only selects messages conforming to the DSR^Q01 schema you created in step 3A.</span></span> <span data-ttu-id="e14e3-143">El segundo filtro especifica el destino en el que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor interfaz envía estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="e14e3-143">The second filter specifies the destination to which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine sends these messages.</span></span>  
  
6.  <span data-ttu-id="e14e3-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-144">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="e14e3-145">En la consola de administración, haga clic en **puertos de envío**, haga clic en **ADT_Send**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="e14e3-145">In the Administration Console, click **Send Ports**, right-click **ADT_Send**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="e14e3-146">Continúe con [paso 8: configurar la información de entidad](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md).</span><span class="sxs-lookup"><span data-stu-id="e14e3-146">Proceed to [Step 8: Configure Party Information](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md).</span></span>