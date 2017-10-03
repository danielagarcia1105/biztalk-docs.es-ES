---
title: "Paso 5: Crear un puerto de envío para entregar confirmaciones al sistema ADT usando el adaptador de archivo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: 565a2adf-fd86-46e3-8035-7e4748aefffc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 926a13d443e7002a71e2b9f6509c3a377f0af0be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-create-a-send-port-to-deliver-acknowledgments-to-the-adt-system-using-the-file-adapter"></a><span data-ttu-id="d7c9b-102">Paso 5: Crear un puerto de envío para entregar confirmaciones al sistema ADT usando el adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="d7c9b-102">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>
<span data-ttu-id="d7c9b-103">En este paso, creará el puerto de envío para generar confirmaciones mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-103">In this step, you create the send port to generate acknowledgments using the File adapter.</span></span>  
  
### <a name="to-create-the-tutorialsendackadt-send-port"></a><span data-ttu-id="d7c9b-104">Para crear el puerto de envío Tutorial_sendAck_ADT</span><span class="sxs-lookup"><span data-stu-id="d7c9b-104">To create the Tutorial_sendAck_ADT send port</span></span>  
  
1.  <span data-ttu-id="d7c9b-105">Usando [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, crear el \< *unidad*: > \Program BizTalk \<versión > Accelerator for carpeta Tutorial\Tutorial_sendAck_ADT HL7\SDK\End-to-End.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-105">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, create the \<*drive*:>\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT folder.</span></span>  
  
2.  <span data-ttu-id="d7c9b-106">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-106">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="d7c9b-107">En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d7c9b-107">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="d7c9b-108">Use</span><span class="sxs-lookup"><span data-stu-id="d7c9b-108">Use this</span></span>|<span data-ttu-id="d7c9b-109">Para</span><span class="sxs-lookup"><span data-stu-id="d7c9b-109">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d7c9b-110">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-110">**Name**</span></span>|<span data-ttu-id="d7c9b-111">Tipo de **Tutorial_sendAck_ADT**.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-111">Type **Tutorial_sendAck_ADT**.</span></span>|  
    |<span data-ttu-id="d7c9b-112">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-112">**Transport type**</span></span>|<span data-ttu-id="d7c9b-113">Seleccione **archivo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-113">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d7c9b-114">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-114">**Configure**</span></span>|<span data-ttu-id="d7c9b-115">Haga clic en **configurar** para abrir el **propiedades de transporte de archivo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-115">Click **Configure** to open the **File Transport Properties** dialog box.</span></span>|  
  
4.  <span data-ttu-id="d7c9b-116">En el cuadro de diálogo Propiedades de transporte de archivo, realice lo siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-116">In the FILE Transport Properties dialog box, do the following and then click **OK**.</span></span>  
  
    |<span data-ttu-id="d7c9b-117">Use</span><span class="sxs-lookup"><span data-stu-id="d7c9b-117">Use this</span></span>|<span data-ttu-id="d7c9b-118">Para</span><span class="sxs-lookup"><span data-stu-id="d7c9b-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d7c9b-119">**Carpeta de destino**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-119">**Destination folder**</span></span>|<span data-ttu-id="d7c9b-120">Vaya a  **\<**  *unidad***: > \Program BizTalk \<versión > Accelerator for Tutorial\Tutorial_sendAck_ADT HL7\SDK\End-to-End** .</span><span class="sxs-lookup"><span data-stu-id="d7c9b-120">Browse to **\<***drive***:>\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT**.</span></span>|  
    |<span data-ttu-id="d7c9b-121">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-121">**File name**</span></span>|<span data-ttu-id="d7c9b-122">Tipo de **%MessageID%.txt** (reemplazar la extensión .xml con la extensión .txt).</span><span class="sxs-lookup"><span data-stu-id="d7c9b-122">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
  
5.  <span data-ttu-id="d7c9b-123">En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-123">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
6.  <span data-ttu-id="d7c9b-124">En el panel izquierdo, haga clic en **filtros**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d7c9b-124">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7c9b-125">El primer filtro significa que se va a suscribir para el mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-125">The first filter means that you are subscribing for the acknowledgment message.</span></span> <span data-ttu-id="d7c9b-126">El segundo filtro significa que se está suscribiendo a la confirmación que se destina el publicador Tutorial_ADTSystem.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-126">The second filter means that you are subscribing to the acknowledgment that is destined for the publisher Tutorial_ADTSystem.</span></span>  
  
     <span data-ttu-id="d7c9b-127">Haga clic en **Aceptar** cuando esté listo para continuar.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-127">Click **OK** when you are ready to continue.</span></span>  
  
    |<span data-ttu-id="d7c9b-128">Use</span><span class="sxs-lookup"><span data-stu-id="d7c9b-128">Use this</span></span>|<span data-ttu-id="d7c9b-129">Para</span><span class="sxs-lookup"><span data-stu-id="d7c9b-129">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d7c9b-130">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-130">**Property**</span></span>|<span data-ttu-id="d7c9b-131">Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-131">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d7c9b-132">**Operador**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-132">**Operator**</span></span>|<span data-ttu-id="d7c9b-133">Seleccione  **==**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-133">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d7c9b-134">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-134">**Value**</span></span>|<span data-ttu-id="d7c9b-135">Tipo de **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-135">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="d7c9b-136">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-136">**Group By**</span></span>|<span data-ttu-id="d7c9b-137">Seleccione **o** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-137">Select **OR** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d7c9b-138">**Propiedad (segunda línea)**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-138">**Property (second line)**</span></span>|<span data-ttu-id="d7c9b-139">Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-139">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d7c9b-140">**Operador**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-140">**Operator**</span></span>|<span data-ttu-id="d7c9b-141">Seleccione  **==**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-141">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d7c9b-142">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-142">**Value**</span></span>|<span data-ttu-id="d7c9b-143">Tipo de **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-143">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span></span>|  
    |<span data-ttu-id="d7c9b-144">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-144">**Group By**</span></span>|<span data-ttu-id="d7c9b-145">Seleccione **AND** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-145">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d7c9b-146">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-146">**Property**</span></span>|<span data-ttu-id="d7c9b-147">En la primera propiedad, haga clic en el cuadro en blanco y, a continuación, seleccione **BTAHL7Schemas.MSH5_1**.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-147">Under the first property, click the blank box, and then select **BTAHL7Schemas.MSH5_1**.</span></span>|  
    |<span data-ttu-id="d7c9b-148">**Operador**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-148">**Operator**</span></span>|<span data-ttu-id="d7c9b-149">Seleccione  **==**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-149">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d7c9b-150">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-150">**Value**</span></span>|<span data-ttu-id="d7c9b-151">Tipo de **Tutorial_ADTSystem**.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-151">Type **Tutorial_ADTSystem**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d7c9b-152">Para el puerto de envío Tutorial_sendAck_ADT BTAHL7 quita las confirmaciones en la ubicación de destino de archivo \< *unidad*>: programa FilesMicrosoft BizTalk <version> Acelerador para TutorialTutorial HL7SDKEnd-to-End _sendAck_ADT.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-152">For the send port Tutorial_sendAck_ADT, BTAHL7 drops the acknowledgments at the file drop location \<*drive*>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendAck_ADT.</span></span>  
  
7.  <span data-ttu-id="d7c9b-153">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="d7c9b-153">Click **Apply**, and then click **OK.**</span></span>  
  
8.  <span data-ttu-id="d7c9b-154">En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_sendAck_ADT**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="d7c9b-154">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendAck_ADT**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="d7c9b-155">Continúe con [paso 6: crear un puerto de envío para entregar el ADT ^ A03 mensaje en el sistema de recepción mediante el adaptador de archivo](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md).</span><span class="sxs-lookup"><span data-stu-id="d7c9b-155">Proceed to [Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md).</span></span>