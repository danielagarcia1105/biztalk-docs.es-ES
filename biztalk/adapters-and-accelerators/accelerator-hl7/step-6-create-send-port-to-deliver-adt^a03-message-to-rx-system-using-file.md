---
title: "Paso 6: Crear un puerto de envío para entregar el ADT ^ A03 mensaje en el sistema de recepción mediante el adaptador de archivo | Documentos de Microsoft"
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
ms.assetid: 66c4b524-c8ff-43b5-9c44-6d7bc759ae2c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c25a348fb739f4558f1507eda0d46d209cd44c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a><span data-ttu-id="2d8ac-102">Paso 6: Crear un puerto de envío para entregar el ADT ^ A03 mensaje en el sistema de recepción mediante el adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="2d8ac-102">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>
<span data-ttu-id="2d8ac-103">En este paso, creará el puerto de envío para la farmacia sistema (RX) mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-103">In this step, you create the send port for the Pharmacy System (RX) using the File adapter.</span></span>  
  
### <a name="to-create-the-tutorialsendmsgrx-send-port"></a><span data-ttu-id="2d8ac-104">Para crear el puerto de envío Tutorial_sendMsg_RX</span><span class="sxs-lookup"><span data-stu-id="2d8ac-104">To create the Tutorial_sendMsg_RX send port</span></span>  
  
1.  <span data-ttu-id="2d8ac-105">En el [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] consola de administración, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-105">In the [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="2d8ac-106">En el **propiedades de puerto de envío** diálogo cuadro, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-106">In the **Send Port Properties** dialog box, do the following actions and then click **OK**.</span></span>  
  
    |<span data-ttu-id="2d8ac-107">Use</span><span class="sxs-lookup"><span data-stu-id="2d8ac-107">Use this</span></span>|<span data-ttu-id="2d8ac-108">Para</span><span class="sxs-lookup"><span data-stu-id="2d8ac-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="2d8ac-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-109">**Name**</span></span>|<span data-ttu-id="2d8ac-110">Tipo de **Tutorial_sendMsg_RX**.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-110">Type **Tutorial_sendMsg_RX**.</span></span>|  
    |<span data-ttu-id="2d8ac-111">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-111">**Transport type**</span></span>|<span data-ttu-id="2d8ac-112">Seleccione **archivo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-112">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="2d8ac-113">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-113">**Configure**</span></span>|<span data-ttu-id="2d8ac-114">Haga clic en **configurar** para abrir el **propiedades de transporte de archivo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-114">Click **Configure** to open the **File Transport Properties** dialog box.</span></span>|  
  
3.  <span data-ttu-id="2d8ac-115">En el cuadro de diálogo Propiedades de transporte de archivo, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-115">In the FILE Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  
  
    |<span data-ttu-id="2d8ac-116">Use</span><span class="sxs-lookup"><span data-stu-id="2d8ac-116">Use this</span></span>|<span data-ttu-id="2d8ac-117">Para</span><span class="sxs-lookup"><span data-stu-id="2d8ac-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="2d8ac-118">**Carpeta de destino**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-118">**Destination folder**</span></span>|<span data-ttu-id="2d8ac-119">Vaya a  **\<**  *unidad***: > \Program BizTalk \<versión > Accelerator for Tutorial\Tutorial_sendMsg_RX HL7\SDK\End-to-End** .</span><span class="sxs-lookup"><span data-stu-id="2d8ac-119">Browse to **\<***drive***:>\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX**.</span></span>|  
    |<span data-ttu-id="2d8ac-120">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-120">**File name**</span></span>|<span data-ttu-id="2d8ac-121">Tipo de **%MessageID%.txt** (reemplazar la extensión .xml con la extensión .txt).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-121">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
  
4.  <span data-ttu-id="2d8ac-122">En el **propiedades de puerto de envío** cuadro de diálogo para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-122">In the **Send Port Properties** dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="2d8ac-123">En el panel izquierdo, seleccione **filtros**, y, a continuación, realice las siguientes acciones.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-123">In the left pane, select **Filters**, and then do the following actions.</span></span> <span data-ttu-id="2d8ac-124">Haga clic en **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-124">Click **OK** to continue.</span></span>  
  
    |<span data-ttu-id="2d8ac-125">Use</span><span class="sxs-lookup"><span data-stu-id="2d8ac-125">Use this</span></span>|<span data-ttu-id="2d8ac-126">Para</span><span class="sxs-lookup"><span data-stu-id="2d8ac-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="2d8ac-127">**Propiedad** (primera línea)</span><span class="sxs-lookup"><span data-stu-id="2d8ac-127">**Property** (first line)</span></span>|<span data-ttu-id="2d8ac-128">Seleccione **BTS. MessageType** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-128">Select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="2d8ac-129">**Operador**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-129">**Operator**</span></span>|<span data-ttu-id="2d8ac-130">Seleccione **! =** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-130">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="2d8ac-131">**Valor**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-131">**Value**</span></span>|<span data-ttu-id="2d8ac-132">Tipo de **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-132">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="2d8ac-133">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-133">**Group By**</span></span>|<span data-ttu-id="2d8ac-134">Seleccione **o** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-134">Select **OR** from the drop-down list.</span></span>|  
    |<span data-ttu-id="2d8ac-135">**Propiedad** (segunda línea)</span><span class="sxs-lookup"><span data-stu-id="2d8ac-135">**Property** (second line)</span></span>|<span data-ttu-id="2d8ac-136">Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-136">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="2d8ac-137">**Operador**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-137">**Operator**</span></span>|<span data-ttu-id="2d8ac-138">Seleccione **! =** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-138">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="2d8ac-139">**Valor**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-139">**Value**</span></span>|<span data-ttu-id="2d8ac-140">Tipo de **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-140">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span></span>|  
    |<span data-ttu-id="2d8ac-141">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-141">**Group By**</span></span>|<span data-ttu-id="2d8ac-142">Seleccione **AND** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-142">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="2d8ac-143">**Propiedad** (tercera línea)</span><span class="sxs-lookup"><span data-stu-id="2d8ac-143">**Property** (third line)</span></span>|<span data-ttu-id="2d8ac-144">Seleccione **BTAHL7Schemas.MSH3_1**.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-144">Select **BTAHL7Schemas.MSH3_1**.</span></span>|  
    |<span data-ttu-id="2d8ac-145">**Operador**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-145">**Operator**</span></span>|<span data-ttu-id="2d8ac-146">Seleccione  **==**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-146">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="2d8ac-147">**Valor**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-147">**Value**</span></span>|<span data-ttu-id="2d8ac-148">Tipo de **Tutorial_ADTSystem**.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-148">Type **Tutorial_ADTSystem**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="2d8ac-149">El primer filtro significa que el sistema de información de salud (HIS) se suscribe a un mensaje, no una confirmación.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-149">The first filter means that the Hospital Information System (HIS) is subscribing to a message, not an acknowledgment.</span></span> <span data-ttu-id="2d8ac-150">El segundo filtro significa que su se suscribe a mensajes cuyo origen es la admisión de descarga y el sistema de transferencia (ADT).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-150">The second filter means that HIS is subscribing to messages whose source is the Admissions Discharge and Transfer (ADT) System.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2d8ac-151">BTAHL7 coloca el mensaje en la ubicación de destino de archivo \< *unidad*>: programa FilesMicrosoft BizTalk <version> Acelerador para TutorialTutorial_sendMsg_RX HL7SDKEnd-to-End.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-151">BTAHL7 drops the message at the file drop location \<*drive*>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendMsg_RX.</span></span>  
  
6.  <span data-ttu-id="2d8ac-152">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-152">Click **Apply**, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="2d8ac-153">En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_sendMsg_RX**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-153">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendMsg_RX**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="2d8ac-154">Continúe con [paso 7: crear un puerto de envío para entregar el ADT ^ A03 mensaje para su uso del adaptador MLLP](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-154">Proceed to [Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).</span></span>