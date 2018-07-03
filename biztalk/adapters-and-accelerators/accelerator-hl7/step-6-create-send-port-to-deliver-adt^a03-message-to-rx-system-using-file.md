---
title: 'Paso 6: Crear un puerto de envío para entregar el ADT ^ A03 mensaje al sistema RX mediante el adaptador de archivo | Microsoft Docs'
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
ms.assetid: 66c4b524-c8ff-43b5-9c44-6d7bc759ae2c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95a9200d4c03f11f2feca89042bfb57ba36de345
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004381"
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a><span data-ttu-id="6ff62-102">Paso 6: Crear un puerto de envío para entregar el ADT ^ A03 mensaje al sistema RX mediante el adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="6ff62-102">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>
<span data-ttu-id="6ff62-103">En este paso, creará el puerto de envío para la farmacia del sistema (RX) mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="6ff62-103">In this step, you create the send port for the Pharmacy System (RX) using the File adapter.</span></span>  

### <a name="to-create-the-tutorialsendmsgrx-send-port"></a><span data-ttu-id="6ff62-104">Para crear el puerto de envío Tutorial_sendMsg_RX</span><span class="sxs-lookup"><span data-stu-id="6ff62-104">To create the Tutorial_sendMsg_RX send port</span></span>  

1. <span data-ttu-id="6ff62-105">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="6ff62-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="6ff62-106">En el **propiedades de puerto de envío** diálogo cuadro, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ff62-106">In the **Send Port Properties** dialog box, do the following actions and then click **OK**.</span></span>  


   |      <span data-ttu-id="6ff62-107">Use</span><span class="sxs-lookup"><span data-stu-id="6ff62-107">Use this</span></span>      |                                <span data-ttu-id="6ff62-108">Para</span><span class="sxs-lookup"><span data-stu-id="6ff62-108">To do this</span></span>                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      <span data-ttu-id="6ff62-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6ff62-109">**Name**</span></span>      |                       <span data-ttu-id="6ff62-110">Tipo **Tutorial_sendMsg_RX**.</span><span class="sxs-lookup"><span data-stu-id="6ff62-110">Type **Tutorial_sendMsg_RX**.</span></span>                       |
   | <span data-ttu-id="6ff62-111">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="6ff62-111">**Transport type**</span></span> |                 <span data-ttu-id="6ff62-112">Seleccione **archivo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6ff62-112">Select **FILE** from the drop-down list.</span></span>                  |
   |   <span data-ttu-id="6ff62-113">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="6ff62-113">**Configure**</span></span>    | <span data-ttu-id="6ff62-114">Haga clic en **configurar** para abrir el **propiedades de transporte File** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6ff62-114">Click **Configure** to open the **File Transport Properties** dialog box.</span></span> |


3. <span data-ttu-id="6ff62-115">En el cuadro de diálogo Propiedades de transporte de archivo, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ff62-115">In the FILE Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  


   |        <span data-ttu-id="6ff62-116">Use</span><span class="sxs-lookup"><span data-stu-id="6ff62-116">Use this</span></span>        |                                                                     <span data-ttu-id="6ff62-117">Para</span><span class="sxs-lookup"><span data-stu-id="6ff62-117">To do this</span></span>                                                                     |
   |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="6ff62-118">**Carpeta de destino**</span><span class="sxs-lookup"><span data-stu-id="6ff62-118">**Destination folder**</span></span> | <span data-ttu-id="6ff62-119">Vaya a **\<** <em>unidad</em>**:\>\Program Files\Microsoft BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_sendMsg_RX**.</span><span class="sxs-lookup"><span data-stu-id="6ff62-119">Browse to **\<**<em>drive</em>**:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX**.</span></span> |
   |     <span data-ttu-id="6ff62-120">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="6ff62-120">**File name**</span></span>      |                                   <span data-ttu-id="6ff62-121">Tipo **%MessageID%.txt** (reemplace la extensión .xml con la extensión .txt).</span><span class="sxs-lookup"><span data-stu-id="6ff62-121">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>                                   |


4. <span data-ttu-id="6ff62-122">En el **propiedades de puerto de envío** cuadro de diálogo para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="6ff62-122">In the **Send Port Properties** dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="6ff62-123">En el panel izquierdo, seleccione **filtros**, y, a continuación, realice las acciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="6ff62-123">In the left pane, select **Filters**, and then do the following actions.</span></span> <span data-ttu-id="6ff62-124">Haga clic en **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="6ff62-124">Click **OK** to continue.</span></span>  


   |          <span data-ttu-id="6ff62-125">Use</span><span class="sxs-lookup"><span data-stu-id="6ff62-125">Use this</span></span>          |                                            <span data-ttu-id="6ff62-126">Para</span><span class="sxs-lookup"><span data-stu-id="6ff62-126">To do this</span></span>                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="6ff62-127">**Propiedad** (primero en línea)</span><span class="sxs-lookup"><span data-stu-id="6ff62-127">**Property** (first line)</span></span>  |                       <span data-ttu-id="6ff62-128">Seleccione **BTS. MessageType** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6ff62-128">Select **BTS.MessageType** from the drop-down list.</span></span>                        |
   |        <span data-ttu-id="6ff62-129">**Operador**</span><span class="sxs-lookup"><span data-stu-id="6ff62-129">**Operator**</span></span>        |                              <span data-ttu-id="6ff62-130">Seleccione **! =** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6ff62-130">Select **!=** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="6ff62-131">**Value**</span><span class="sxs-lookup"><span data-stu-id="6ff62-131">**Value**</span></span>          |                <span data-ttu-id="6ff62-132">Tipo **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.</span><span class="sxs-lookup"><span data-stu-id="6ff62-132">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.</span></span>                 |
   |        <span data-ttu-id="6ff62-133">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="6ff62-133">**Group By**</span></span>        |                              <span data-ttu-id="6ff62-134">Seleccione **o** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6ff62-134">Select **OR** from the drop-down list.</span></span>                              |
   | <span data-ttu-id="6ff62-135">**Propiedad** (segunda línea)</span><span class="sxs-lookup"><span data-stu-id="6ff62-135">**Property** (second line)</span></span> | <span data-ttu-id="6ff62-136">Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6ff62-136">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span> |
   |        <span data-ttu-id="6ff62-137">**Operador**</span><span class="sxs-lookup"><span data-stu-id="6ff62-137">**Operator**</span></span>        |                              <span data-ttu-id="6ff62-138">Seleccione **! =** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6ff62-138">Select **!=** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="6ff62-139">**Value**</span><span class="sxs-lookup"><span data-stu-id="6ff62-139">**Value**</span></span>          |                <span data-ttu-id="6ff62-140">Tipo  **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**</span><span class="sxs-lookup"><span data-stu-id="6ff62-140">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**</span></span>                 |
   |        <span data-ttu-id="6ff62-141">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="6ff62-141">**Group By**</span></span>        |                             <span data-ttu-id="6ff62-142">Seleccione **AND** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6ff62-142">Select **AND** from the drop-down list.</span></span>                              |
   | <span data-ttu-id="6ff62-143">**Propiedad** (tercera línea)</span><span class="sxs-lookup"><span data-stu-id="6ff62-143">**Property** (third line)</span></span>  |                                 <span data-ttu-id="6ff62-144">Seleccione **BTAHL7Schemas.MSH3_1**.</span><span class="sxs-lookup"><span data-stu-id="6ff62-144">Select **BTAHL7Schemas.MSH3_1**.</span></span>                                 |
   |        <span data-ttu-id="6ff62-145">**Operador**</span><span class="sxs-lookup"><span data-stu-id="6ff62-145">**Operator**</span></span>        |                              <span data-ttu-id="6ff62-146">Seleccione **==** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6ff62-146">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="6ff62-147">**Value**</span><span class="sxs-lookup"><span data-stu-id="6ff62-147">**Value**</span></span>          |                                   <span data-ttu-id="6ff62-148">Tipo **Tutorial_ADTSystem**.</span><span class="sxs-lookup"><span data-stu-id="6ff62-148">Type **Tutorial_ADTSystem**.</span></span>                                   |

   > [!NOTE]
   >  <span data-ttu-id="6ff62-149">El primer filtro significa que el sistema de información de Hospital (HIS) se está suscribiendo a un mensaje, no una confirmación.</span><span class="sxs-lookup"><span data-stu-id="6ff62-149">The first filter means that the Hospital Information System (HIS) is subscribing to a message, not an acknowledgment.</span></span> <span data-ttu-id="6ff62-150">El segundo filtro significa que su está suscribiendo a los mensajes cuyo origen es la admisión de descarga y el sistema de transferencia (ADT).</span><span class="sxs-lookup"><span data-stu-id="6ff62-150">The second filter means that HIS is subscribing to messages whose source is the Admissions Discharge and Transfer (ADT) System.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6ff62-151">BTAHL7 coloca el mensaje en la ubicación de destino de archivo \< *unidad*\>: programa FilesMicrosoft BizTalk <version> Acelerador para TutorialTutorial_sendMsg_RX HL7SDKEnd-to-End.</span><span class="sxs-lookup"><span data-stu-id="6ff62-151">BTAHL7 drops the message at the file drop location \<*drive*\>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendMsg_RX.</span></span>  

6. <span data-ttu-id="6ff62-152">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="6ff62-152">Click **Apply**, and then click **OK.**</span></span>  

7. <span data-ttu-id="6ff62-153">En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_sendMsg_RX**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="6ff62-153">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendMsg_RX**, and then click **Start**.</span></span>  

   <span data-ttu-id="6ff62-154">Continúe con [paso 7: crear un puerto de envío para entregar el ADT ^ mensaje A03 a HIS mediante el adaptador MLLP](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="6ff62-154">Proceed to [Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).</span></span>