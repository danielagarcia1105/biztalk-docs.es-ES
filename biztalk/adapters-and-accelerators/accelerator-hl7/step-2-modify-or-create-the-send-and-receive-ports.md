---
title: "Paso 2: Modificar o crear el envío y puertos de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d96d02c-b75d-4d18-a127-37002c5ff138
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa94183f0eb83dc51fc0add22ba50484f7282fb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="step-2-modify-or-create-the-send-and-receive-ports"></a><span data-ttu-id="5e0da-102">Paso 2: Modificar o crear el envío y puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="5e0da-102">Step 2: Modify or Create the Send and Receive Ports</span></span>
<span data-ttu-id="5e0da-103">Necesitará envío de archivos y los puertos de recepción para el lote en / lote tutorial.</span><span class="sxs-lookup"><span data-stu-id="5e0da-103">You need FILE send and receive ports for the Batch In/Batch Out tutorial.</span></span> <span data-ttu-id="5e0da-104">Si hace clic en el **iniciar Tutorial** botón al final de la instalación de la edición Enterprise de [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] crea estos puertos: un puerto de envío denominado Tutorial_BTAHL7Drop y un puerto de recepción denominado Tutorial_BTAHL7PickUp.</span><span class="sxs-lookup"><span data-stu-id="5e0da-104">If you clicked the **Launch Tutorial** button at the end of installing the Enterprise Edition of [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] created these ports for you: a send port named Tutorial_BTAHL7Drop, and a receive port named Tutorial_BTAHL7PickUp.</span></span> <span data-ttu-id="5e0da-105">Si dispone de estos puertos, deberá modificar el puerto de envío Tutorial_BTAHL7Drop.</span><span class="sxs-lookup"><span data-stu-id="5e0da-105">If you have these ports, you still need to modify the send port Tutorial_BTAHL7Drop.</span></span>  
  
 <span data-ttu-id="5e0da-106">Si [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el programa de instalación no crear el envío y puertos de recepción para usted, vea el procedimiento "Para crear el BIBOTutorialPickup puerto de recepción" en este tema y, a continuación, consulte el procedimiento "Para crear el BIBOTutorialDrop puerto de envío" también en este tema.</span><span class="sxs-lookup"><span data-stu-id="5e0da-106">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup did not create the send and receive ports for you, see "To create the BIBOTutorialPickup receive port" procedure in this topic, and then see "To create the BIBOTutorialDrop send port" procedure also in this topic.</span></span>  
  
### <a name="to-modify-the-tutorialbtahl7drop-send-port"></a><span data-ttu-id="5e0da-107">Para modificar el puerto de envío Tutorial_BTAHL7Drop</span><span class="sxs-lookup"><span data-stu-id="5e0da-107">To modify the Tutorial_BTAHL7Drop send port</span></span>  
  
1.  <span data-ttu-id="5e0da-108">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-108">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5e0da-109">En la consola de administración, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda  **Aplicación de BizTalk 1**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-109">In the Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="5e0da-110">Haga clic en **puertos de envío**, haga clic en **Tutorial_BTAHL7Drop**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-110">Click **Send Ports**, right-click **Tutorial_BTAHL7Drop**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="5e0da-111">En el árbol de consola, haga clic en **filtros**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-111">In the console tree, click **Filters**.</span></span>  
  
5.  <span data-ttu-id="5e0da-112">En el **filtros** panel, en la segunda fila, seleccione **BTAHL7Schemas.MessageClass** para **propiedades**, seleccione  **==**  para **Operador**y el tipo de **MessageClass2X** para **valor**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-112">In the **Filters** pane, in the second row, select **BTAHL7Schemas.MessageClass** for **Properties**, select **==** for **Operator**, and type **MessageClass2X** for **Value**.</span></span> <span data-ttu-id="5e0da-113">Haga clic en **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-113">Click **Enter**.</span></span>  
  
6.  <span data-ttu-id="5e0da-114">Establecer **Agrupar por** en el **BTS. ReceivePortName** línea a **o**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-114">Set **Group By** on the **BTS.ReceivePortName** line to **Or**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="5e0da-115">En el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ventana de administración, expanda **configuración de plataforma**y expanda **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-115">In the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration window, expand **Platform Settings**, and expand **Host Instances**.</span></span> <span data-ttu-id="5e0da-116">Haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-116">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e0da-117">Solo use los procedimientos siguientes si ha instalado la edición Standard de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], o si no hizo clic en el **iniciar Tutorial** botón al configurar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e0da-117">Only use the following procedures if you installed the Standard Edition of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], or if you did not click the **Launch Tutorial** button when you set up [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span>  
  
### <a name="to-create-the-tutorialbtahl7pickup-receive-port-and-location"></a><span data-ttu-id="5e0da-118">Para crear el Tutorial_BTAHL7Pickup puerto de recepción y ubicación</span><span class="sxs-lookup"><span data-stu-id="5e0da-118">To create the Tutorial_BTAHL7Pickup receive port and location</span></span>  
  
1.  <span data-ttu-id="5e0da-119">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-119">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5e0da-120">En la consola de administración, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda  **Aplicación de BizTalk 1**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-120">In the Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="5e0da-121">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="5e0da-122">En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba **Tutorial_BTAHL7PickUp**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-122">In the Receive Port Properties dialog box, in the **Name** box, type **Tutorial_BTAHL7PickUp**.</span></span>  
  
5.  <span data-ttu-id="5e0da-123">Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-123">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="5e0da-124">Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-124">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="5e0da-125">En el, seleccione un cuadro de diálogo de puerto de recepción, haga clic en **Tutorial_BTAHL7PickUp**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-125">In the Select a Receive Port dialog box, click **Tutorial_BTAHL7PickUp**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="5e0da-126">En el cuadro de diálogo Propiedades de la ubicación de recepción, en el **nombre** , escriba **Tutorial_FileReceiveLoc**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-126">In the Receive Location Properties dialog box, in the **Name** box, type **Tutorial_FileReceiveLoc**.</span></span>  
  
9. <span data-ttu-id="5e0da-127">En el **transporte** sección, para la **tipo** cuadro de texto, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-127">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="5e0da-128">Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.</span><span class="sxs-lookup"><span data-stu-id="5e0da-128">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="5e0da-129">En el cuadro de diálogo Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e0da-129">In the FILE Transport Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="5e0da-130">Use</span><span class="sxs-lookup"><span data-stu-id="5e0da-130">Use this</span></span>|<span data-ttu-id="5e0da-131">Para</span><span class="sxs-lookup"><span data-stu-id="5e0da-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5e0da-132">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="5e0da-132">**Receive Folder**</span></span>|<span data-ttu-id="5e0da-133">Vaya a  **\<**  *unidad***\>: \Program BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_BTAHL7PickUp**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-133">Browse to **\<***drive***\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp**.</span></span> <span data-ttu-id="5e0da-134">**Nota:** trata la ruta de acceso a la ubicación en el sistema de archivos o un recurso compartido público desde donde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] recogerá el archivo.</span><span class="sxs-lookup"><span data-stu-id="5e0da-134">**Note:**  This is the path to the location on the file system or public share from where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will pick up the file.</span></span>|  
    |<span data-ttu-id="5e0da-135">**Máscara de archivo**</span><span class="sxs-lookup"><span data-stu-id="5e0da-135">**File mask**</span></span>|<span data-ttu-id="5e0da-136">Tipo de  **\*.txt**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-136">Type **\*.txt**.</span></span>|  
  
12. <span data-ttu-id="5e0da-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-137">Click **OK**.</span></span>  
  
13. <span data-ttu-id="5e0da-138">En el cuadro de diálogo Propiedades de la ubicación de recepción, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e0da-138">In the Receive Location Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="5e0da-139">Use</span><span class="sxs-lookup"><span data-stu-id="5e0da-139">Use this</span></span>|<span data-ttu-id="5e0da-140">Para</span><span class="sxs-lookup"><span data-stu-id="5e0da-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5e0da-141">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="5e0da-141">**Receive Handler**</span></span>|<span data-ttu-id="5e0da-142">Mantener **BizTalkServerApplication** como seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5e0da-142">Keep **BizTalkServerApplication** as selected.</span></span>|  
    |<span data-ttu-id="5e0da-143">**Canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="5e0da-143">**Receive Pipeline**</span></span>|<span data-ttu-id="5e0da-144">Seleccione **BTAHL72XPipelines.BTAHL72XReceivePipeline**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-144">Select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.</span></span>|  
  
14. <span data-ttu-id="5e0da-145">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-145">Click **OK**.</span></span>  
  
15. <span data-ttu-id="5e0da-146">En el Explorador de BizTalk, haga clic en **Tutorial_FileReceiveLoc**y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-146">In BizTalk Explorer, right-click **Tutorial_FileReceiveLoc**, and then click **Enable**.</span></span>  
  
### <a name="to-create-the-tutorialbtahl7drop-send-port"></a><span data-ttu-id="5e0da-147">Para crear el puerto de envío Tutorial_BTAHL7Drop</span><span class="sxs-lookup"><span data-stu-id="5e0da-147">To create the Tutorial_BTAHL7Drop send port</span></span>  
  
1.  <span data-ttu-id="5e0da-148">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-148">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="5e0da-149">En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e0da-149">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="5e0da-150">Use</span><span class="sxs-lookup"><span data-stu-id="5e0da-150">Use this</span></span>|<span data-ttu-id="5e0da-151">Para</span><span class="sxs-lookup"><span data-stu-id="5e0da-151">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5e0da-152">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5e0da-152">**Name**</span></span>|<span data-ttu-id="5e0da-153">Tipo de **Tutorial_BTAHL7Drop**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-153">Type **Tutorial_BTAHL7Drop**.</span></span>|  
    |<span data-ttu-id="5e0da-154">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5e0da-154">**Type**</span></span>|<span data-ttu-id="5e0da-155">Seleccione **archivo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5e0da-155">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="5e0da-156">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="5e0da-156">**Configure**</span></span>|<span data-ttu-id="5e0da-157">Haga clic en **configurar** para abrir el **propiedades de transporte de archivo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5e0da-157">Click **Configure** to open the **FILE Transport Properties** dialog box.</span></span>|  
  
3.  <span data-ttu-id="5e0da-158">En el cuadro de diálogo Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e0da-158">In the FILE Transport Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="5e0da-159">Use</span><span class="sxs-lookup"><span data-stu-id="5e0da-159">Use this</span></span>|<span data-ttu-id="5e0da-160">Para</span><span class="sxs-lookup"><span data-stu-id="5e0da-160">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5e0da-161">**Carpeta de destino**</span><span class="sxs-lookup"><span data-stu-id="5e0da-161">**Destination folder**</span></span>|<span data-ttu-id="5e0da-162">Vaya a  **\<**  *unidad***:\>\Program BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_BTAHL7Drop**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-162">Browse to **\<***drive***:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop**.</span></span> <span data-ttu-id="5e0da-163">**Nota:** se trata de la ruta de acceso a la ubicación en el sistema de archivos o un recurso compartido público al que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] escribirá el archivo.</span><span class="sxs-lookup"><span data-stu-id="5e0da-163">**Note:**  This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file.</span></span>|  
    |<span data-ttu-id="5e0da-164">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="5e0da-164">**File name**</span></span>|<span data-ttu-id="5e0da-165">Tipo de **%MessageID%.txt** (tenga en cuenta que la extensión txt, xml no).</span><span class="sxs-lookup"><span data-stu-id="5e0da-165">Type **%MessageID%.txt** (note that the extension is txt, not xml).</span></span>|  
  
4.  <span data-ttu-id="5e0da-166">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-166">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="5e0da-167">En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5e0da-167">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline** from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="5e0da-168">En el árbol de consola, haga clic en **filtros**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e0da-168">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="5e0da-169">Use</span><span class="sxs-lookup"><span data-stu-id="5e0da-169">Use this</span></span>|<span data-ttu-id="5e0da-170">Para</span><span class="sxs-lookup"><span data-stu-id="5e0da-170">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5e0da-171">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="5e0da-171">**Property**</span></span>|<span data-ttu-id="5e0da-172">Seleccione **BTS. ReceivePortName** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5e0da-172">Select **BTS.ReceivePortName** from the drop-down list.</span></span>|  
    |<span data-ttu-id="5e0da-173">**Operador**</span><span class="sxs-lookup"><span data-stu-id="5e0da-173">**Operator**</span></span>|<span data-ttu-id="5e0da-174">Deje  **==**  como el operador.</span><span class="sxs-lookup"><span data-stu-id="5e0da-174">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="5e0da-175">**Valor**</span><span class="sxs-lookup"><span data-stu-id="5e0da-175">**Value**</span></span>|<span data-ttu-id="5e0da-176">Tipo de **Tutorial_BTAHL7PickUp**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-176">Type **Tutorial_BTAHL7PickUp**.</span></span>|  
    |<span data-ttu-id="5e0da-177">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="5e0da-177">**Group By**</span></span>|<span data-ttu-id="5e0da-178">Seleccione **o** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5e0da-178">Select **Or** from the drop-down list.</span></span>|  
    |<span data-ttu-id="5e0da-179">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="5e0da-179">**Property**</span></span>|<span data-ttu-id="5e0da-180">Seleccione **BTAHL7Schemas.MessageClass**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-180">Select **BTAHL7Schemas.MessageClass**.</span></span>|  
    |<span data-ttu-id="5e0da-181">**Operador**</span><span class="sxs-lookup"><span data-stu-id="5e0da-181">**Operator**</span></span>|<span data-ttu-id="5e0da-182">Deje  **==**  como el operador.</span><span class="sxs-lookup"><span data-stu-id="5e0da-182">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="5e0da-183">**Valor**</span><span class="sxs-lookup"><span data-stu-id="5e0da-183">**Value**</span></span>|<span data-ttu-id="5e0da-184">Tipo de **MessageClass2X**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-184">Type **MessageClass2X**.</span></span>|  
  
7.  <span data-ttu-id="5e0da-185">Haga clic en **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-185">Click **Enter**.</span></span> <span data-ttu-id="5e0da-186">En el panel en la parte inferior del cuadro de diálogo, compruebe que la expresión de filtro es correcta.</span><span class="sxs-lookup"><span data-stu-id="5e0da-186">Verify in the pane at the bottom of the dialog box that the filter expression is correct.</span></span>  
  
8.  <span data-ttu-id="5e0da-187">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-187">Click **OK**.</span></span>  
  
9. <span data-ttu-id="5e0da-188">En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_BTAHL7Drop**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-188">In the Administration Console, click **Send Ports**, right-click **Tutorial_BTAHL7Drop**, and then click **Start**.</span></span>  
  
10. <span data-ttu-id="5e0da-189">Expanda **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-189">Expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="5e0da-190">Haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="5e0da-190">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
 <span data-ttu-id="5e0da-191">Continúe con [paso 3: probar el lote / lote escenario](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="5e0da-191">Proceed to [Step 3: Test the Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md).</span></span>