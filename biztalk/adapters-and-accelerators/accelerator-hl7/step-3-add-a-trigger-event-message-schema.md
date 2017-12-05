---
title: 'Paso 3: Agregar un esquema de desencadenador de eventos (mensaje) | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc4a67d9-9582-4f2b-9bc9-18fbff823d29
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 439caac8f1da151a9f203a1372039aaeedbfe83c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-add-a-trigger-event-message-schema"></a><span data-ttu-id="69cb5-102">Paso 3: Agregar un esquema de desencadenador de eventos (mensaje)</span><span class="sxs-lookup"><span data-stu-id="69cb5-102">Step 3: Add a Trigger Event (Message) Schema</span></span>
<span data-ttu-id="69cb5-103">En este paso, cree un nuevo proyecto basado en vacío [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] plantilla de proyecto.</span><span class="sxs-lookup"><span data-stu-id="69cb5-103">In this step, you create a new project based on the Empty [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Project template.</span></span> <span data-ttu-id="69cb5-104">Para este proyecto, agregue el esquema que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] usará para validar los mensajes del lote entrante (ADT ^ A03).</span><span class="sxs-lookup"><span data-stu-id="69cb5-104">To this project, you add the schema that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will use to validate the messages in the incoming batch (ADT^A03).</span></span> <span data-ttu-id="69cb5-105">Agregue una referencia al proyecto que contiene los esquemas comunes v2.3.1, asigne un nombre seguro al proyecto y, a continuación, implemente el proyecto.</span><span class="sxs-lookup"><span data-stu-id="69cb5-105">You add a reference to the project containing the v2.3.1 common schemas, assign the strong name to the project, and then deploy the project.</span></span>  
  
### <a name="to-add-the-project-containing-the-message-schema"></a><span data-ttu-id="69cb5-106">Para agregar el proyecto que contiene el esquema de mensaje</span><span class="sxs-lookup"><span data-stu-id="69cb5-106">To add the project containing the message schema</span></span>  
  
1.  <span data-ttu-id="69cb5-107">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="69cb5-108">En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-108">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="69cb5-109">En el **plantillas** sección, seleccione **proyecto vacío de BTAHL7**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-109">In the **Templates** section, select **Empty BTAHL7 Project**.</span></span>  
  
4.  <span data-ttu-id="69cb5-110">En el **nombre** cuadro, escriba **BTAHL7V231Body** como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="69cb5-110">In the **Name** box, enter **BTAHL7V231Body** as the project name.</span></span>  
  
5.  <span data-ttu-id="69cb5-111">En el **solución** cuadro, seleccione **agregar a solución**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-111">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6.  <span data-ttu-id="69cb5-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-112">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="69cb5-113">En el Explorador de soluciones, bajo el nodo para el proyecto nuevo, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-113">In Solution Explorer, under the node for your new project, right-click **References**, and then click **Add Reference**.</span></span>  
  
8.  <span data-ttu-id="69cb5-114">En el cuadro de diálogo Agregar referencia, en la **proyectos** , haga clic en **proyecto BTAHL7V231Common** en el **nombre del proyecto** columna, haga clic en **agregar**, y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-114">In the Add Reference dialog box, on the **Projects** tab, click **BTAHL7V231Common Project** in the **Project Name** column, click **Add**, and then click **OK**.</span></span>  
  
### <a name="to-add-the-schema-to-the-project"></a><span data-ttu-id="69cb5-115">Para agregar el esquema al proyecto</span><span class="sxs-lookup"><span data-stu-id="69cb5-115">To add the schema to the project</span></span>  
  
1.  <span data-ttu-id="69cb5-116">En el Explorador de soluciones, haga clic en **BTAHL7V231Body**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-116">In Solution Explorer, right-click **BTAHL7V231Body**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="69cb5-117">En el cuadro de diálogo Agregar nuevo elemento, expanda **elementos de proyecto de BizTalk**y, a continuación, haga clic en **BTAHL7 esquemas**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-117">In the Add New Item dialog box, expand **BizTalk Project Items**, and then click **BTAHL7 Schemas**.</span></span> <span data-ttu-id="69cb5-118">En el **plantillas** panel, haga clic en **BTAHL7 esquemas**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-118">In the **Templates** pane, click **BTAHL7 Schemas**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="69cb5-119">En el **Selector de esquema HL7** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69cb5-119">In the **HL7 Schema Selector** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="69cb5-120">Use</span><span class="sxs-lookup"><span data-stu-id="69cb5-120">Use this</span></span>|<span data-ttu-id="69cb5-121">Para</span><span class="sxs-lookup"><span data-stu-id="69cb5-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="69cb5-122">**Message (clase)**</span><span class="sxs-lookup"><span data-stu-id="69cb5-122">**Message Class**</span></span>|<span data-ttu-id="69cb5-123">Mantener **V2.X** como seleccionado.</span><span class="sxs-lookup"><span data-stu-id="69cb5-123">Keep **V2.X** as selected.</span></span>|  
    |<span data-ttu-id="69cb5-124">**Versión**</span><span class="sxs-lookup"><span data-stu-id="69cb5-124">**Version**</span></span>|<span data-ttu-id="69cb5-125">Seleccione **2.3.1**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-125">Select **2.3.1**.</span></span>|  
    |<span data-ttu-id="69cb5-126">**Tipo de mensaje**</span><span class="sxs-lookup"><span data-stu-id="69cb5-126">**Message Type**</span></span>|<span data-ttu-id="69cb5-127">Seleccione **ADT**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-127">Select **ADT**.</span></span>|  
    |<span data-ttu-id="69cb5-128">**Evento de desencadenador**</span><span class="sxs-lookup"><span data-stu-id="69cb5-128">**Trigger Event**</span></span>|<span data-ttu-id="69cb5-129">Seleccione **A03**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-129">Select **A03**.</span></span>|  
  
4.  <span data-ttu-id="69cb5-130">Haga clic en **crear** para agregar el esquema al proyecto, a continuación, haga clic en **cancelar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="69cb5-130">Click **Create** to add the schema to the project, then click **Cancel** to close the dialog box.</span></span> <span data-ttu-id="69cb5-131">Tenga en cuenta que el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se agrega el esquema ADT_A03_231_GLO_DEF.xsd al proyecto BTAHL7V231Body.</span><span class="sxs-lookup"><span data-stu-id="69cb5-131">Note that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) has added the ADT_A03_231_GLO_DEF.xsd schema to the BTAHL7V231Body project.</span></span>  
  
### <a name="to-assign-a-strong-key-and-deploy"></a><span data-ttu-id="69cb5-132">Para asignar una clave segura e implementar</span><span class="sxs-lookup"><span data-stu-id="69cb5-132">To assign a strong key and deploy</span></span>  
  
1.  <span data-ttu-id="69cb5-133">En el Explorador de soluciones, haga clic en **BTAHL7V231Body**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-133">In Solution Explorer, right-click **BTAHL7V231Body**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="69cb5-134">En el cuadro de diálogo página de propiedades de BTAHL7V231Body, haga clic en **firma**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-134">In the BTAHL7V231Body Property Page dialog box, click **Signing**.</span></span>  
  
3.  <span data-ttu-id="69cb5-135">Comprobar **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="69cb5-135">Check **Sign the assembly** check box.</span></span>  
  
4.  <span data-ttu-id="69cb5-136">En **elegir un archivo de clave de nombre seguro** de lista desplegable de la lista, seleccione  **\<Examinar... \>.**</span><span class="sxs-lookup"><span data-stu-id="69cb5-136">In **Choose a strong name key file** drop down list select **\<Browse…\>.**</span></span>  
  
5.  <span data-ttu-id="69cb5-137">Vaya a  **\<* unidad*\>: \Batching Tutorial **, seleccione **key.snk**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-137">Browse to **\<*drive*\>:\Batching Tutorial**, select **key.snk**, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="69cb5-138">En el Explorador de soluciones, haga clic en **BTAHL7V231Body**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="69cb5-138">In Solution Explorer, right-click **BTAHL7V231Body**, and then click **Deploy**.</span></span> <span data-ttu-id="69cb5-139">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="69cb5-139">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69cb5-140">Si no aparece ningún mensaje de successful-deploy, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.</span><span class="sxs-lookup"><span data-stu-id="69cb5-140">If a successful-deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="69cb5-141">Continúe con [paso 4: crear un puerto de recepción para aceptar el mensaje por lotes](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md).</span><span class="sxs-lookup"><span data-stu-id="69cb5-141">Proceed to [Step 4: Create a Receive Port for Accepting the Batch Message](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md).</span></span>