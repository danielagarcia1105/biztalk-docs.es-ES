---
title: 'Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje) | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, trigger events
- trigger events
ms.assetid: 5d21a923-fc2c-4d50-b146-daca0aa26e2a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf96bdc546223b68677b642944265c22d2ce4b14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-project"></a><span data-ttu-id="06d51-102">Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje)</span><span class="sxs-lookup"><span data-stu-id="06d51-102">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>
<span data-ttu-id="06d51-103">En este paso, creará el esquema para el mensaje de evento de desencadenador.</span><span class="sxs-lookup"><span data-stu-id="06d51-103">In this step, you create the schema for your trigger event message.</span></span> <span data-ttu-id="06d51-104">Por ejemplo, es posible que el sistema de admisión de descarga y la transferencia (ADT) que envía un mensaje para el sistema de información de Hospital (HIS).</span><span class="sxs-lookup"><span data-stu-id="06d51-104">For example, you might be the Admissions Discharge and Transfer system (ADT) who sends a message to the Hospital Information System (HIS).</span></span> <span data-ttu-id="06d51-105">Necesita este esquema para definir el formato del mensaje.</span><span class="sxs-lookup"><span data-stu-id="06d51-105">You need this schema to define the format of your message.</span></span>  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a><span data-ttu-id="06d51-106">Para crear el proyecto para el mensaje de evento de desencadenador</span><span class="sxs-lookup"><span data-stu-id="06d51-106">To create the project for the trigger event message</span></span>  
  
1.  <span data-ttu-id="06d51-107">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="06d51-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, then click **Project**.</span></span>  
  
2.  <span data-ttu-id="06d51-108">En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, haga clic en **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="06d51-108">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="06d51-109">En la sección plantillas, haga clic en **proyecto vacío de BTAHL7**, en la **nombre** , escriba **BTAHL7V231Body proyecto**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="06d51-109">In the Templates section, click **Empty BTAHL7 Project**, in the **Name** box, type **BTAHL7V231Body Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="06d51-110">En el Explorador de soluciones, bajo el nodo para el proyecto nuevo, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="06d51-110">In Solution Explorer, under the node for your new project, right-click **References**, and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="06d51-111">En el cuadro de diálogo Agregar referencia, en la **proyectos** ficha, seleccione **BTAHL7V231Common Proyecto1**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="06d51-111">In the Add Reference dialog box, on the **Projects** tab, select **BTAHL7V231Common Project1**, click **Add**, and then click **OK**.</span></span>  
  
## <a name="step-3a-add-the-schema"></a><span data-ttu-id="06d51-112">Paso 3A: agregue el esquema</span><span class="sxs-lookup"><span data-stu-id="06d51-112">Step 3A: Add the Schema</span></span>  
 <span data-ttu-id="06d51-113">Utilice el procedimiento siguiente para agregar el nuevo esquema al proyecto.</span><span class="sxs-lookup"><span data-stu-id="06d51-113">Use the following procedure to add the new schema to the project.</span></span>  
  
#### <a name="to-add-the-schema-to-the-project"></a><span data-ttu-id="06d51-114">Para agregar el esquema al proyecto</span><span class="sxs-lookup"><span data-stu-id="06d51-114">To add the schema to the project</span></span>  
  
1.  <span data-ttu-id="06d51-115">En el Explorador de soluciones, haga clic en **BTAHL7V231Body proyecto**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="06d51-115">In Solution Explorer, right-click **BTAHL7V231Body Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="06d51-116">En Agregar nuevo elemento cuadro de diálogo, en la **categorías** sección, expanda **elementos de proyecto de BizTalk**y, a continuación, seleccione **BTAHL7 esquemas**.</span><span class="sxs-lookup"><span data-stu-id="06d51-116">In the Add New Item dialog box, in the **Categories** section, expand **BizTalk Project Items**, and then select **BTAHL7 Schemas**.</span></span>  
  
3.  <span data-ttu-id="06d51-117">En la sección de plantillas, haga doble clic en **BTAHL7 esquemas**.</span><span class="sxs-lookup"><span data-stu-id="06d51-117">In the Templates section, double-click **BTAHL7 Schemas**.</span></span>  
  
4.  <span data-ttu-id="06d51-118">En el cuadro de diálogo Selector de esquema HL7, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="06d51-118">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="06d51-119">Use</span><span class="sxs-lookup"><span data-stu-id="06d51-119">Use this</span></span>|<span data-ttu-id="06d51-120">Para</span><span class="sxs-lookup"><span data-stu-id="06d51-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="06d51-121">**Message (clase)**</span><span class="sxs-lookup"><span data-stu-id="06d51-121">**Message Class**</span></span>|<span data-ttu-id="06d51-122">Deje el valor predeterminado de **V2.X** seleccionado.</span><span class="sxs-lookup"><span data-stu-id="06d51-122">Leave the default of **V2.X** selected.</span></span>|  
    |<span data-ttu-id="06d51-123">**Versión**</span><span class="sxs-lookup"><span data-stu-id="06d51-123">**Version**</span></span>|<span data-ttu-id="06d51-124">Seleccione **2.3.1**.</span><span class="sxs-lookup"><span data-stu-id="06d51-124">Select **2.3.1**.</span></span>|  
    |<span data-ttu-id="06d51-125">**Tipo de mensaje**</span><span class="sxs-lookup"><span data-stu-id="06d51-125">**Message Type**</span></span>|<span data-ttu-id="06d51-126">Seleccione **ADT**.</span><span class="sxs-lookup"><span data-stu-id="06d51-126">Select **ADT**.</span></span>|  
    |<span data-ttu-id="06d51-127">**Evento de desencadenador**</span><span class="sxs-lookup"><span data-stu-id="06d51-127">**Trigger Event**</span></span>|<span data-ttu-id="06d51-128">Seleccione **A03**.</span><span class="sxs-lookup"><span data-stu-id="06d51-128">Select **A03**.</span></span>|  
  
5.  <span data-ttu-id="06d51-129">Haga clic en **finalizar** para agregar el esquema al proyecto.</span><span class="sxs-lookup"><span data-stu-id="06d51-129">Click **Finish** to add the schema to the project.</span></span>  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="06d51-130">Paso 3B: asignar una clave segura para el ensamblado e implementar</span><span class="sxs-lookup"><span data-stu-id="06d51-130">Step 3B: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="06d51-131">Utilice el procedimiento siguiente para asignar una clave segura para el ensamblado y, a continuación, implemente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="06d51-131">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="06d51-132">Para asignar una clave segura e implementar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="06d51-132">To assign a strong key and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="06d51-133">En el Explorador de soluciones, haga clic en **BTAHL7V231Body proyecto**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="06d51-133">In Solution Explorer, right-click **BTAHL7V231Body Project**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="06d51-134">En la página de páginas de propiedades de proyecto, haga clic en **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="06d51-134">In the Project Property Pages page, click **Assembly**.</span></span>  
  
3.  <span data-ttu-id="06d51-135">En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo de clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="06d51-135">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="06d51-136">En el cuadro de diálogo de archivo de clave de ensamblado, vaya a \< *unidad*>: \Program BizTalk \<versión > Accelerator for Tutorial HL7\SDK\End-to-End, haga clic en **key.snk**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="06d51-136">In the Assembly Key File dialog box, browse to \<*drive*>:\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\End-to-End Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="06d51-137">En el cuadro de diálogo páginas de propiedades de proyecto, haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="06d51-137">In the Project Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
6.  <span data-ttu-id="06d51-138">En el Explorador de soluciones, haga clic en **BTAHL7V231Body proyecto**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="06d51-138">In Solution Explorer right-click **BTAHL7V231Body Project**, and then click **Deploy**.</span></span> <span data-ttu-id="06d51-139">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="06d51-139">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="06d51-140">Si no aparece ningún mensaje de implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.</span><span class="sxs-lookup"><span data-stu-id="06d51-140">If a successful deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="06d51-141">Continúe con [paso 4: crear el puerto de recepción para aceptar ADT ^ A03 mensajes desde sistemas ADT usa el adaptador MLLP](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md).</span><span class="sxs-lookup"><span data-stu-id="06d51-141">Proceed to [Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md).</span></span>