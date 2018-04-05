---
title: 'Paso 3: Crear e implementar un Project_hl7_main (mensaje) del evento de desencadenador | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, trigger events
ms.assetid: 90b65ad1-7953-4009-a1eb-1c2a85c7980a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ba388eef1f5dbfb885e33c6263c4e0f8ef4be29
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-projecthl7main"></a><span data-ttu-id="891b1-102">Paso 3: Crear e implementar un Project_hl7_main (mensaje) del evento de desencadenador</span><span class="sxs-lookup"><span data-stu-id="891b1-102">Step 3: Create and Deploy a Trigger Event (Message) Project_hl7_main</span></span>
<span data-ttu-id="891b1-103">En este paso, creará el esquema utilizado por un mensaje de evento de desencadenador.</span><span class="sxs-lookup"><span data-stu-id="891b1-103">In this step, you create the schema used by a trigger event message.</span></span> <span data-ttu-id="891b1-104">Por ejemplo, el sistema de admisión de descarga y la transferencia (ADT) envía un mensaje para el sistema de información de Hospital (HIS).</span><span class="sxs-lookup"><span data-stu-id="891b1-104">For example, the Admissions Discharge and Transfer system (ADT) that sends a message to the Hospital Information System (HIS).</span></span> <span data-ttu-id="891b1-105">Utilice este esquema para definir el formato del mensaje.</span><span class="sxs-lookup"><span data-stu-id="891b1-105">You use this schema to define the format of your message.</span></span>  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a><span data-ttu-id="891b1-106">Para crear el proyecto para el mensaje de evento de desencadenador</span><span class="sxs-lookup"><span data-stu-id="891b1-106">To create the project for the trigger event message</span></span>  
  
1.  <span data-ttu-id="891b1-107">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="891b1-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="891b1-108">En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** lista, expanda **proyectos de BizTalk**y, a continuación, haga clic en **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="891b1-108">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="891b1-109">En el **plantillas** lista, haga clic en **proyecto vacío de BTAHL7**.</span><span class="sxs-lookup"><span data-stu-id="891b1-109">In the **Templates** list, click **Empty BTAHL7 Project**.</span></span>  
  
4.  <span data-ttu-id="891b1-110">En el **nombre** , escriba **BTAHL7V24Body proyecto**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="891b1-110">In the **Name** field, type **BTAHL7V24Body Project**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="891b1-111">En el Explorador de soluciones, bajo el nodo para el nuevo **BTAHL7V24Body** proyecto de equipo y haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="891b1-111">In Solution Explorer, under the node for your new **BTAHL7V24Body** project, right-click **References**, and then click **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="891b1-112">En el cuadro de diálogo Agregar referencia, haga clic en el **proyectos** ficha, seleccione **Interrogative_24Schemas**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="891b1-112">In the Add Reference dialog box, click the **Projects** tab, select **Interrogative_24Schemas**, click **Add**, and then click **OK**.</span></span>  
  
## <a name="step-3a-add-the-schemas"></a><span data-ttu-id="891b1-113">Paso 3A: agregue los esquemas</span><span class="sxs-lookup"><span data-stu-id="891b1-113">Step 3A: Add the Schemas</span></span>  
 <span data-ttu-id="891b1-114">Utilice el procedimiento siguiente para agregar los nuevos esquemas al proyecto.</span><span class="sxs-lookup"><span data-stu-id="891b1-114">Use the following procedure to add the new schemas to the project.</span></span>  
  
#### <a name="to-add-the-schemas-to-the-project"></a><span data-ttu-id="891b1-115">Para agregar los esquemas al proyecto</span><span class="sxs-lookup"><span data-stu-id="891b1-115">To add the schemas to the project</span></span>  
  
1.  <span data-ttu-id="891b1-116">En el Explorador de soluciones, haga clic en **BTAHL7V24Body proyecto**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="891b1-116">In Solution Explorer, right-click **BTAHL7V24Body Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="891b1-117">En el cuadro de diálogo Agregar nuevo elemento, expanda **elementos de proyecto de BizTalk**y, a continuación, haga doble clic en **BTAHL7 esquemas** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="891b1-117">In the Add New Item dialog box, expand **BizTalk Project Items**, and then double-click **BTAHL7 Schemas** in the right pane.</span></span>  
  
3.  <span data-ttu-id="891b1-118">En el cuadro de diálogo Selector de esquema HL7, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="891b1-118">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="891b1-119">Use</span><span class="sxs-lookup"><span data-stu-id="891b1-119">Use this</span></span>|<span data-ttu-id="891b1-120">Para</span><span class="sxs-lookup"><span data-stu-id="891b1-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="891b1-121">**Message (clase)**</span><span class="sxs-lookup"><span data-stu-id="891b1-121">**Message Class**</span></span>|<span data-ttu-id="891b1-122">Mantener **V2.X** seleccionado.</span><span class="sxs-lookup"><span data-stu-id="891b1-122">Keep **V2.X** selected.</span></span>|  
    |<span data-ttu-id="891b1-123">**Versión**</span><span class="sxs-lookup"><span data-stu-id="891b1-123">**Version**</span></span>|<span data-ttu-id="891b1-124">Seleccione **2.4**.</span><span class="sxs-lookup"><span data-stu-id="891b1-124">Select **2.4**.</span></span>|  
    |<span data-ttu-id="891b1-125">**Tipo de mensaje**</span><span class="sxs-lookup"><span data-stu-id="891b1-125">**Message Type**</span></span>|<span data-ttu-id="891b1-126">Seleccione **consulta**.</span><span class="sxs-lookup"><span data-stu-id="891b1-126">Select **QRY**.</span></span>|  
    |<span data-ttu-id="891b1-127">**Evento de desencadenador**</span><span class="sxs-lookup"><span data-stu-id="891b1-127">**Trigger Event**</span></span>|<span data-ttu-id="891b1-128">Seleccione **Q01**.</span><span class="sxs-lookup"><span data-stu-id="891b1-128">Select **Q01**.</span></span>|  
  
4.  <span data-ttu-id="891b1-129">Haga clic en **finalizar** para agregar el esquema al proyecto.</span><span class="sxs-lookup"><span data-stu-id="891b1-129">Click **Finish** to add the schema to the project.</span></span>  
  
     <span data-ttu-id="891b1-130">Esto crea el archivo de esquema de la consulta QRY_Q01_24_GLO_DEF.xsd.</span><span class="sxs-lookup"><span data-stu-id="891b1-130">This creates the query schema file QRY_Q01_24_GLO_DEF.xsd.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="891b1-131">No cierre el cuadro de diálogo Selector de esquema HL7.</span><span class="sxs-lookup"><span data-stu-id="891b1-131">Do not close the HL7 Schema Selector dialog box.</span></span>  
  
5.  <span data-ttu-id="891b1-132">En el cuadro de diálogo Selector de esquema HL7, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="891b1-132">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="891b1-133">Use</span><span class="sxs-lookup"><span data-stu-id="891b1-133">Use this</span></span>|<span data-ttu-id="891b1-134">Para</span><span class="sxs-lookup"><span data-stu-id="891b1-134">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="891b1-135">**Message (clase)**</span><span class="sxs-lookup"><span data-stu-id="891b1-135">**Message Class**</span></span>|<span data-ttu-id="891b1-136">Mantener **V2.X** seleccionado.</span><span class="sxs-lookup"><span data-stu-id="891b1-136">Keep **V2.X** selected.</span></span>|  
    |<span data-ttu-id="891b1-137">**Versión**</span><span class="sxs-lookup"><span data-stu-id="891b1-137">**Version**</span></span>|<span data-ttu-id="891b1-138">Seleccione **2.4**.</span><span class="sxs-lookup"><span data-stu-id="891b1-138">Select **2.4**.</span></span>|  
    |<span data-ttu-id="891b1-139">**Tipo de mensaje**</span><span class="sxs-lookup"><span data-stu-id="891b1-139">**Message Type**</span></span>|<span data-ttu-id="891b1-140">Seleccione **DSR**.</span><span class="sxs-lookup"><span data-stu-id="891b1-140">Select **DSR**.</span></span>|  
    |<span data-ttu-id="891b1-141">**Evento de desencadenador**</span><span class="sxs-lookup"><span data-stu-id="891b1-141">**Trigger Event**</span></span>|<span data-ttu-id="891b1-142">Seleccione **Q01**.</span><span class="sxs-lookup"><span data-stu-id="891b1-142">Select **Q01**.</span></span>|  
  
6.  <span data-ttu-id="891b1-143">Haga clic en **finalizar** para agregar el esquema al proyecto.</span><span class="sxs-lookup"><span data-stu-id="891b1-143">Click **Finish** to add the schema to the project.</span></span>  
  
     <span data-ttu-id="891b1-144">Esto crea el archivo de esquema de respuesta DSR_Q01_24_GLO_DEF.xsd.</span><span class="sxs-lookup"><span data-stu-id="891b1-144">This creates the response schema file DSR_Q01_24_GLO_DEF.xsd.</span></span>  
  
7.  <span data-ttu-id="891b1-145">Haga clic en **cancelar** para cerrar el **Selector de esquema HL7** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="891b1-145">Click **Cancel** to close the **HL7 Schema Selector** dialog box.</span></span>  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="891b1-146">Paso 3B: asignar una clave segura para el ensamblado e implementar</span><span class="sxs-lookup"><span data-stu-id="891b1-146">Step 3B: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="891b1-147">Utilice el procedimiento siguiente para asignar una clave segura para el ensamblado y, a continuación, implemente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="891b1-147">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="891b1-148">Para asignar una clave segura e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="891b1-148">To assign a strong key and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="891b1-149">En el Explorador de soluciones, haga clic en **BTAHL7V24Body** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="891b1-149">In Solution Explorer, right-click **BTAHL7V24Body** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="891b1-150">En el **páginas de propiedades de BTAHL7V24Body** cuadro de diálogo, haga clic en **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="891b1-150">In the **BTAHL7V24Body Property Pages** dialog box, click **Assembly**.</span></span>  
  
3.  <span data-ttu-id="891b1-151">En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo de clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="891b1-151">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
4.  <span data-ttu-id="891b1-152">En el **archivo de clave de ensamblado** cuadro de diálogo, vaya a \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\>Acelerador para HL7\SDK\Interrogative Tutorial, haga clic en **key.snk**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="891b1-152">In the **Assembly Key File** dialog box, browse to \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="891b1-153">En el **páginas de propiedades de BTAHL7V24Body** cuadro de diálogo, haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="891b1-153">In the **BTAHL7V24Body Property Pages** dialog box, click **OK** to save your changes.</span></span>  
  
6.  <span data-ttu-id="891b1-154">En el Explorador de soluciones, haga clic en **BTAHL7V24Body proyecto**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="891b1-154">In Solution Explorer right-click **BTAHL7V24Body Project**, and then click **Deploy**.</span></span> <span data-ttu-id="891b1-155">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="891b1-155">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="891b1-156">Si no aparece ningún mensaje de implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.</span><span class="sxs-lookup"><span data-stu-id="891b1-156">If a successful deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="891b1-157">Continúe con [paso 4: crear el puerto de recepción para aceptar mensajes de consulta ADT](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md).</span><span class="sxs-lookup"><span data-stu-id="891b1-157">Proceed to [Step 4: Create the Receive Port for Accepting ADT Query Messages](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md).</span></span>