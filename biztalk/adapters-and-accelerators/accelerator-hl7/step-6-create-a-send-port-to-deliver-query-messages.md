---
title: "Paso 6: Crear un puerto de envío para entregar los mensajes de consulta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, send ports
ms.assetid: a3cfa2aa-888d-4a82-9eb3-2e9cc29ee582
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c373940d8ab1e847b66527d83ef24e952d84d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a><span data-ttu-id="10cb8-102">Paso 6: Crear un puerto de envío para entregar los mensajes de consulta</span><span class="sxs-lookup"><span data-stu-id="10cb8-102">Step 6: Create a Send Port to Deliver Query Messages</span></span>
<span data-ttu-id="10cb8-103">En este paso, creará el puerto de envío para entregar las consultas entrantes (consulta ^ Q01 mensajes) para el sistema de información de Hospital (HIS).</span><span class="sxs-lookup"><span data-stu-id="10cb8-103">In this step, you create the send port to deliver the incoming queries (QRY^Q01 messages) to the Hospital Information System (HIS).</span></span>  
  
### <a name="to-create-the-hissend-send-port"></a><span data-ttu-id="10cb8-104">Para crear el puerto de envío HIS_Send</span><span class="sxs-lookup"><span data-stu-id="10cb8-104">To create the HIS_Send send port</span></span>  
  
1.  <span data-ttu-id="10cb8-105">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, seleccione **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then select **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="10cb8-106">En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10cb8-106">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="10cb8-107">Use</span><span class="sxs-lookup"><span data-stu-id="10cb8-107">Use this</span></span>|<span data-ttu-id="10cb8-108">Para</span><span class="sxs-lookup"><span data-stu-id="10cb8-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="10cb8-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="10cb8-109">**Name**</span></span>|<span data-ttu-id="10cb8-110">Tipo de **HIS_Send**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-110">Type **HIS_Send**.</span></span>|  
    |<span data-ttu-id="10cb8-111">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="10cb8-111">**Transport type**</span></span>|<span data-ttu-id="10cb8-112">Seleccione **MLLP**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-112">Select **MLLP**.</span></span>|  
    |<span data-ttu-id="10cb8-113">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="10cb8-113">**Configure**</span></span>|<span data-ttu-id="10cb8-114">Haga clic en el **configurar** situado a la derecha de **tipo**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-114">Click the **Configure** button to the right of **Type**.</span></span>|  
  
3.  <span data-ttu-id="10cb8-115">En el cuadro de diálogo Propiedades de transporte de MLLP, escriba la información siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-115">In the MLLP Transport Properties dialog box, enter the following information and then click **OK**.</span></span>  
  
    |<span data-ttu-id="10cb8-116">Use</span><span class="sxs-lookup"><span data-stu-id="10cb8-116">Use this</span></span>|<span data-ttu-id="10cb8-117">Para</span><span class="sxs-lookup"><span data-stu-id="10cb8-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="10cb8-118">**Nombre de conexión**</span><span class="sxs-lookup"><span data-stu-id="10cb8-118">**Connection Name**</span></span>|<span data-ttu-id="10cb8-119">Tipo de **HIS_SendMLLP**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-119">Type **HIS_SendMLLP**.</span></span>|  
    |<span data-ttu-id="10cb8-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="10cb8-120">**Host**</span></span>|<span data-ttu-id="10cb8-121">Tipo de **localhost**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-121">Type **localhost**.</span></span>|  
    |<span data-ttu-id="10cb8-122">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="10cb8-122">**Port**</span></span>|<span data-ttu-id="10cb8-123">Tipo de **24000**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-123">Type **24000**.</span></span>|  
  
4.  <span data-ttu-id="10cb8-124">En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="10cb8-125">En el árbol de consola, haga clic en **filtros**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10cb8-125">In the Console Tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="10cb8-126">Use</span><span class="sxs-lookup"><span data-stu-id="10cb8-126">Use this</span></span>|<span data-ttu-id="10cb8-127">Para</span><span class="sxs-lookup"><span data-stu-id="10cb8-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="10cb8-128">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="10cb8-128">**Property**</span></span>|<span data-ttu-id="10cb8-129">Para **propiedad**, seleccione **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-129">For **Property**, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="10cb8-130">**Operador**</span><span class="sxs-lookup"><span data-stu-id="10cb8-130">**Operator**</span></span>|<span data-ttu-id="10cb8-131">Seleccione  **==**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="10cb8-131">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="10cb8-132">**Valor**</span><span class="sxs-lookup"><span data-stu-id="10cb8-132">**Value**</span></span>|<span data-ttu-id="10cb8-133">Tipo de **http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-133">Type **http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="10cb8-134">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="10cb8-134">**Group By**</span></span>|<span data-ttu-id="10cb8-135">Seleccione **AND** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="10cb8-135">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="10cb8-136">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="10cb8-136">**Property**</span></span>|<span data-ttu-id="10cb8-137">Para **propiedad** en la segunda línea, seleccione **BTAHL7Schemas.MSH5_1**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-137">For **Property** on the second line, select **BTAHL7Schemas.MSH5_1**.</span></span>|  
    |<span data-ttu-id="10cb8-138">**Operador**</span><span class="sxs-lookup"><span data-stu-id="10cb8-138">**Operator**</span></span>|<span data-ttu-id="10cb8-139">Seleccione  **==**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="10cb8-139">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="10cb8-140">**Valor**</span><span class="sxs-lookup"><span data-stu-id="10cb8-140">**Value**</span></span>|<span data-ttu-id="10cb8-141">Tipo de **HIS**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-141">Type **HIS**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="10cb8-142">El primer filtro especifica que el puerto de envío selecciona sólo mensajes sean conformes a la consulta ^ esquema Q01 que creó en el paso 3A.</span><span class="sxs-lookup"><span data-stu-id="10cb8-142">The first filter specifies that the send port only selects messages conforming to the QRY^Q01 schema you created in step 3A.</span></span> <span data-ttu-id="10cb8-143">El segundo filtro especifica el destino en el que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor interfaz envía estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="10cb8-143">The second filter specifies the destination to which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine sends these messages.</span></span>  
  
6.  <span data-ttu-id="10cb8-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-144">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="10cb8-145">En la consola de administración, seleccione **puertos de envío**, haga clic en **HIS_Send**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="10cb8-145">In the Administration console, select **Send Ports**, right-click **HIS_Send**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="10cb8-146">Continúe con [paso 7: crear un puerto de envío para entregar los mensajes de respuesta](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md).</span><span class="sxs-lookup"><span data-stu-id="10cb8-146">Proceed to [Step 7: Create a Send Port to Deliver Response Messages](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md).</span></span>