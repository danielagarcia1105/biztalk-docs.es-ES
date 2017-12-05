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
ms.openlocfilehash: 62581310d4260ecb5b1162df1f52b0170d791d57
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a><span data-ttu-id="121e4-102">Paso 6: Crear un puerto de envío para entregar el ADT ^ A03 mensaje en el sistema de recepción mediante el adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="121e4-102">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>
<span data-ttu-id="121e4-103">En este paso, creará el puerto de envío para la farmacia sistema (RX) mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="121e4-103">In this step, you create the send port for the Pharmacy System (RX) using the File adapter.</span></span>  
  
### <a name="to-create-the-tutorialsendmsgrx-send-port"></a><span data-ttu-id="121e4-104">Para crear el puerto de envío Tutorial_sendMsg_RX</span><span class="sxs-lookup"><span data-stu-id="121e4-104">To create the Tutorial_sendMsg_RX send port</span></span>  
  
1.  <span data-ttu-id="121e4-105">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="121e4-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="121e4-106">En el **propiedades de puerto de envío** diálogo cuadro, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="121e4-106">In the **Send Port Properties** dialog box, do the following actions and then click **OK**.</span></span>  
  
    |<span data-ttu-id="121e4-107">Use</span><span class="sxs-lookup"><span data-stu-id="121e4-107">Use this</span></span>|<span data-ttu-id="121e4-108">Para</span><span class="sxs-lookup"><span data-stu-id="121e4-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="121e4-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="121e4-109">**Name**</span></span>|<span data-ttu-id="121e4-110">Tipo de **Tutorial_sendMsg_RX**.</span><span class="sxs-lookup"><span data-stu-id="121e4-110">Type **Tutorial_sendMsg_RX**.</span></span>|  
    |<span data-ttu-id="121e4-111">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="121e4-111">**Transport type**</span></span>|<span data-ttu-id="121e4-112">Seleccione **archivo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="121e4-112">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="121e4-113">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="121e4-113">**Configure**</span></span>|<span data-ttu-id="121e4-114">Haga clic en **configurar** para abrir el **propiedades de transporte de archivo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="121e4-114">Click **Configure** to open the **File Transport Properties** dialog box.</span></span>|  
  
3.  <span data-ttu-id="121e4-115">En el cuadro de diálogo Propiedades de transporte de archivo, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="121e4-115">In the FILE Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  
  
    |<span data-ttu-id="121e4-116">Use</span><span class="sxs-lookup"><span data-stu-id="121e4-116">Use this</span></span>|<span data-ttu-id="121e4-117">Para</span><span class="sxs-lookup"><span data-stu-id="121e4-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="121e4-118">**Carpeta de destino**</span><span class="sxs-lookup"><span data-stu-id="121e4-118">**Destination folder**</span></span>|<span data-ttu-id="121e4-119">Vaya a  **\<**  *unidad***:\>\Program BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_sendMsg_RX**.</span><span class="sxs-lookup"><span data-stu-id="121e4-119">Browse to **\<***drive***:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX**.</span></span>|  
    |<span data-ttu-id="121e4-120">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="121e4-120">**File name**</span></span>|<span data-ttu-id="121e4-121">Tipo de **%MessageID%.txt** (reemplazar la extensión .xml con la extensión .txt).</span><span class="sxs-lookup"><span data-stu-id="121e4-121">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
  
4.  <span data-ttu-id="121e4-122">En el **propiedades de puerto de envío** cuadro de diálogo para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="121e4-122">In the **Send Port Properties** dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="121e4-123">En el panel izquierdo, seleccione **filtros**, y, a continuación, realice las siguientes acciones.</span><span class="sxs-lookup"><span data-stu-id="121e4-123">In the left pane, select **Filters**, and then do the following actions.</span></span> <span data-ttu-id="121e4-124">Haga clic en **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="121e4-124">Click **OK** to continue.</span></span>  
  
    |<span data-ttu-id="121e4-125">Use</span><span class="sxs-lookup"><span data-stu-id="121e4-125">Use this</span></span>|<span data-ttu-id="121e4-126">Para</span><span class="sxs-lookup"><span data-stu-id="121e4-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="121e4-127">**Propiedad** (primera línea)</span><span class="sxs-lookup"><span data-stu-id="121e4-127">**Property** (first line)</span></span>|<span data-ttu-id="121e4-128">Seleccione **BTS. MessageType** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="121e4-128">Select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="121e4-129">**Operador**</span><span class="sxs-lookup"><span data-stu-id="121e4-129">**Operator**</span></span>|<span data-ttu-id="121e4-130">Seleccione **! =** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="121e4-130">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="121e4-131">**Valor**</span><span class="sxs-lookup"><span data-stu-id="121e4-131">**Value**</span></span>|<span data-ttu-id="121e4-132">Tipo de **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span><span class="sxs-lookup"><span data-stu-id="121e4-132">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="121e4-133">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="121e4-133">**Group By**</span></span>|<span data-ttu-id="121e4-134">Seleccione **o** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="121e4-134">Select **OR** from the drop-down list.</span></span>|  
    |<span data-ttu-id="121e4-135">**Propiedad** (segunda línea)</span><span class="sxs-lookup"><span data-stu-id="121e4-135">**Property** (second line)</span></span>|<span data-ttu-id="121e4-136">Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="121e4-136">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="121e4-137">**Operador**</span><span class="sxs-lookup"><span data-stu-id="121e4-137">**Operator**</span></span>|<span data-ttu-id="121e4-138">Seleccione **! =** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="121e4-138">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="121e4-139">**Valor**</span><span class="sxs-lookup"><span data-stu-id="121e4-139">**Value**</span></span>|<span data-ttu-id="121e4-140">Tipo de **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span><span class="sxs-lookup"><span data-stu-id="121e4-140">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span></span>|  
    |<span data-ttu-id="121e4-141">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="121e4-141">**Group By**</span></span>|<span data-ttu-id="121e4-142">Seleccione **AND** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="121e4-142">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="121e4-143">**Propiedad** (tercera línea)</span><span class="sxs-lookup"><span data-stu-id="121e4-143">**Property** (third line)</span></span>|<span data-ttu-id="121e4-144">Seleccione **BTAHL7Schemas.MSH3_1**.</span><span class="sxs-lookup"><span data-stu-id="121e4-144">Select **BTAHL7Schemas.MSH3_1**.</span></span>|  
    |<span data-ttu-id="121e4-145">**Operador**</span><span class="sxs-lookup"><span data-stu-id="121e4-145">**Operator**</span></span>|<span data-ttu-id="121e4-146">Seleccione  **==**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="121e4-146">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="121e4-147">**Valor**</span><span class="sxs-lookup"><span data-stu-id="121e4-147">**Value**</span></span>|<span data-ttu-id="121e4-148">Tipo de **Tutorial_ADTSystem**.</span><span class="sxs-lookup"><span data-stu-id="121e4-148">Type **Tutorial_ADTSystem**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="121e4-149">El primer filtro significa que el sistema de información de salud (HIS) se suscribe a un mensaje, no una confirmación.</span><span class="sxs-lookup"><span data-stu-id="121e4-149">The first filter means that the Hospital Information System (HIS) is subscribing to a message, not an acknowledgment.</span></span> <span data-ttu-id="121e4-150">El segundo filtro significa que su se suscribe a mensajes cuyo origen es la admisión de descarga y el sistema de transferencia (ADT).</span><span class="sxs-lookup"><span data-stu-id="121e4-150">The second filter means that HIS is subscribing to messages whose source is the Admissions Discharge and Transfer (ADT) System.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="121e4-151">BTAHL7 coloca el mensaje en la ubicación de destino de archivo \< *unidad*\>: programa FilesMicrosoft BizTalk <version> Acelerador para TutorialTutorial_sendMsg_RX HL7SDKEnd-to-End.</span><span class="sxs-lookup"><span data-stu-id="121e4-151">BTAHL7 drops the message at the file drop location \<*drive*\>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendMsg_RX.</span></span>  
  
6.  <span data-ttu-id="121e4-152">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="121e4-152">Click **Apply**, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="121e4-153">En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_sendMsg_RX**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="121e4-153">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendMsg_RX**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="121e4-154">Continúe con [paso 7: crear un puerto de envío para entregar el ADT ^ A03 mensaje para su uso del adaptador MLLP](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="121e4-154">Proceed to [Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).</span></span>