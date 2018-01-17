---
title: 'Paso 4: Crear los esquemas | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, schemas
- creating, schemas
- schemas, creating
ms.assetid: 81b1f538-9743-433a-87f9-a423dcb868c8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ce9ea850632327e257909e1c7d4b60117865e46
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="step-4-create-the-schemas"></a><span data-ttu-id="f300f-102">Paso 4: Crear los esquemas</span><span class="sxs-lookup"><span data-stu-id="f300f-102">Step 4: Create the Schemas</span></span>
<span data-ttu-id="f300f-103">En este paso, creará un nuevo proyecto (**BTAHL7 proyecto**) que contiene los artefactos para este proyecto: los esquemas, el mapa y la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f300f-103">In this step, you create a new project (**BTAHL7 Project**) that contains the artifacts for this project: the schemas, map, and orchestration.</span></span> <span data-ttu-id="f300f-104">A continuación, cree un esquema (**Doorbell.xsd**) para el mensaje entrante de codificación XML y seleccione un esquema existente (**ADT_A04_22_GLO_DEF.xsd**) para el mensaje saliente con codificación HL7.</span><span class="sxs-lookup"><span data-stu-id="f300f-104">You then create a schema (**Doorbell.xsd**) for the incoming XML-encoded message, and select an existing schema (**ADT_A04_22_GLO_DEF.xsd**) for the outgoing HL7-encoded message.</span></span> <span data-ttu-id="f300f-105">Use estos esquemas para definir la estructura de los mensajes que intercambian en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f300f-105">You use these schemas to define the structure of the messages that you exchange within the orchestration.</span></span>  
  
### <a name="to-create-the-schemas"></a><span data-ttu-id="f300f-106">Para crear los esquemas</span><span class="sxs-lookup"><span data-stu-id="f300f-106">To create the schemas</span></span>  
  
1.  <span data-ttu-id="f300f-107">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="f300f-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="f300f-108">En el cuadro de diálogo nuevo proyecto, expanda el **proyectos de BizTalk** carpeta y, a continuación, haga clic en el **BTAHL7Projects** carpeta.</span><span class="sxs-lookup"><span data-stu-id="f300f-108">In the New Project dialog box, expand the **BizTalk Projects** folder, and then click the **BTAHL7Projects** folder.</span></span>  
  
3.  <span data-ttu-id="f300f-109">En el **plantillas** panel, haga clic en **proyecto vacío de BTAHL7**.</span><span class="sxs-lookup"><span data-stu-id="f300f-109">In the **Templates** pane, click **Empty BTAHL7 Project**.</span></span>  
  
4.  <span data-ttu-id="f300f-110">En el **nombre** , escriba **BTAHL7 proyecto** como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f300f-110">In the **Name** field, type **BTAHL7 Project** as the project name.</span></span>  
  
5.  <span data-ttu-id="f300f-111">En el **solución** campo, seleccione **agregar a solución**.</span><span class="sxs-lookup"><span data-stu-id="f300f-111">In the **Solution** field, select **Add to Solution**.</span></span>  
  
6.  <span data-ttu-id="f300f-112">En el **ubicación** , a continuación, compruebe que  **\< *unidad*\>: \Tutorial\BTAHL7V22Common** es la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f300f-112">In the **Location** field, verify that **\<*drive*\>:\Tutorial\BTAHL7V22Common** is the path.</span></span>  
  
7.  <span data-ttu-id="f300f-113">Haga clic en **Aceptar** para abrir el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="f300f-113">Click **OK** to open the new project.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="f300f-114">Agrega un nuevo proyecto en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="f300f-114"> adds a new project to Solution Explorer.</span></span> <span data-ttu-id="f300f-115">También agrega la carpeta del proyecto y crea archivos de la \< *unidad*\>: \Tutorial\\**BTAHL7V22Common** carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f300f-115">It also adds the project folder and creates files in the \<*drive*\>:\Tutorial\\**BTAHL7V22Common** Project folder.</span></span>  
  
8.  <span data-ttu-id="f300f-116">En el Explorador de soluciones, haga clic en el **BTAHL7 proyecto** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="f300f-116">In Solution Explorer, right-click the **BTAHL7 Project** project, point to **Add**, and then click **New Item**.</span></span>  
  
9. <span data-ttu-id="f300f-117">En Agregar nuevo elemento - proyecto BTAHL7 cuadro de diálogo, en la **categorías** panel, haga clic en **archivos de esquema**y en el **plantillas** panel, haga clic en **esquema**.</span><span class="sxs-lookup"><span data-stu-id="f300f-117">In the Add New Item - BTAHL7 Project dialog box, in the **Categories** pane, click **Schema Files**, and in the **Templates** pane, click **Schema**.</span></span>  
  
10. <span data-ttu-id="f300f-118">En el **nombre** , escriba **Doorbell.xsd** al nombre del esquema.</span><span class="sxs-lookup"><span data-stu-id="f300f-118">In the **Name** field, type **Doorbell.xsd** to name the schema.</span></span>  
  
11. <span data-ttu-id="f300f-119">Haga clic en **agregar** para abrir el esquema en blanco en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f300f-119">Click **Add** to open the blank schema in BizTalk Editor.</span></span>  
  
12. <span data-ttu-id="f300f-120">En el  **\<esquema\>**  de árbol, haga clic en el **raíz** nodo y, a continuación, haga clic en **cambiar el nombre de**.</span><span class="sxs-lookup"><span data-stu-id="f300f-120">In the **\<Schema\>** tree, right-click the **Root** node, and then click **Rename**.</span></span>  
  
13. <span data-ttu-id="f300f-121">Tipo de **DoorbellRoot** como nuevo nombre y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f300f-121">Type **DoorbellRoot** as the new name, and then press **Enter**.</span></span>  
  
14. <span data-ttu-id="f300f-122">Haga clic en el **DoorbellRoot** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario** para agregar los campos siguientes (Repita este paso para cada campo elemento):</span><span class="sxs-lookup"><span data-stu-id="f300f-122">Right-click the **DoorbellRoot** node, point to **Insert Schema Node**, and then click **Child Field Element** to add the following fields (repeat this step for each field element):</span></span>  
  
    -   <span data-ttu-id="f300f-123">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="f300f-123">**FirstName**</span></span>  
  
    -   <span data-ttu-id="f300f-124">**MiddleName**</span><span class="sxs-lookup"><span data-stu-id="f300f-124">**MiddleName**</span></span>  
  
    -   <span data-ttu-id="f300f-125">**LastName**</span><span class="sxs-lookup"><span data-stu-id="f300f-125">**LastName**</span></span>  
  
    -   <span data-ttu-id="f300f-126">**SSN**</span><span class="sxs-lookup"><span data-stu-id="f300f-126">**SSN**</span></span>  
  
15. <span data-ttu-id="f300f-127">En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="f300f-127">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  
  
16. <span data-ttu-id="f300f-128">En Agregar nuevo elemento - proyecto BTAHL7 cuadro de diálogo, en la **categorías** panel, haga clic en **BTAHL7 esquemas**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="f300f-128">In the Add New Item - BTAHL7 Project dialog box, in the **Categories** pane, click **BTAHL7 Schemas**, and then click **Add**.</span></span>  
  
17. <span data-ttu-id="f300f-129">En el cuadro de diálogo Selector de esquema HL7, en la **Message (clase)** cuadro, seleccione **V2.X**y en el **detalles del esquema** panel, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f300f-129">In the HL7 Schema Selector dialog box, in the **Message Class** box, select **V2.X**, and in the **Schema Details** pane, do the following:</span></span>  
  
    |<span data-ttu-id="f300f-130">Use</span><span class="sxs-lookup"><span data-stu-id="f300f-130">Use this</span></span>|<span data-ttu-id="f300f-131">Para</span><span class="sxs-lookup"><span data-stu-id="f300f-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f300f-132">**Versión**</span><span class="sxs-lookup"><span data-stu-id="f300f-132">**Version**</span></span>|<span data-ttu-id="f300f-133">Seleccione el número de versión del mensaje HL7.</span><span class="sxs-lookup"><span data-stu-id="f300f-133">Select the version number of the HL7 message.</span></span> <span data-ttu-id="f300f-134">En este tutorial, usará **2.2**.</span><span class="sxs-lookup"><span data-stu-id="f300f-134">In this tutorial, use **2.2**.</span></span>|  
    |<span data-ttu-id="f300f-135">**Tipo de mensaje**</span><span class="sxs-lookup"><span data-stu-id="f300f-135">**Message Type**</span></span>|<span data-ttu-id="f300f-136">Seleccione el tipo de mensaje HL7.</span><span class="sxs-lookup"><span data-stu-id="f300f-136">Select the type of HL7 message.</span></span> <span data-ttu-id="f300f-137">En este tutorial, usará **ADT**.</span><span class="sxs-lookup"><span data-stu-id="f300f-137">In this tutorial, use **ADT**.</span></span>|  
    |<span data-ttu-id="f300f-138">**Evento de desencadenador**</span><span class="sxs-lookup"><span data-stu-id="f300f-138">**Trigger Event**</span></span>|<span data-ttu-id="f300f-139">Seleccione el valor de evento de desencadenador para el mensaje HL7.</span><span class="sxs-lookup"><span data-stu-id="f300f-139">Select the Trigger Event value for the HL7 message.</span></span> <span data-ttu-id="f300f-140">En este tutorial, usará **A04**.</span><span class="sxs-lookup"><span data-stu-id="f300f-140">In this tutorial, use **A04**.</span></span>|  
  
18. <span data-ttu-id="f300f-141">Haga clic en **finalizar** para agregar el esquema ADT_A04_22_GLO_DEF.xsd (registrar paciente) a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="f300f-141">Click **Finish** to add the ADT_A04_22_GLO_DEF.xsd (Register Patient) schema to your project.</span></span> <span data-ttu-id="f300f-142">Cierre el cuadro de diálogo Selector de esquema HL7.</span><span class="sxs-lookup"><span data-stu-id="f300f-142">Close the HL7 Schema Selector dialog box.</span></span>  
  
19. <span data-ttu-id="f300f-143">En el Explorador de soluciones, bajo **BTAHL7 proyecto**, haga clic en **referencias** y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="f300f-143">In Solution Explorer, under **BTAHL7 Project**, right-click **References** and then click **Add Reference**.</span></span>  
  
20. <span data-ttu-id="f300f-144">En el cuadro de diálogo Agregar referencia, en la **proyectos** ficha, seleccione la **BTAHL7V22Common** proyecto de equipo y haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f300f-144">In the Add Reference dialog box, on the **Projects** tab, select the **BTAHL7V22Common** project, click **Add**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f300f-145">Esto agrega una referencia al proyecto original para que [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] reconoce los esquemas de HL7 correctamente.</span><span class="sxs-lookup"><span data-stu-id="f300f-145">This adds a reference to the original project so that [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] recognizes the HL7 schemas correctly.</span></span>  
  
21. <span data-ttu-id="f300f-146">En el Explorador de soluciones, bajo **BTAHL7 proyecto**, haga clic en **referencias** y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="f300f-146">In Solution Explorer, under **BTAHL7 Project**, right-click **References** and then click **Add Reference**.</span></span>  
  
22. <span data-ttu-id="f300f-147">En el cuadro de diálogo Agregar referencia, haga clic en el **examinar** ficha. En el **buscar en** cuadro, pase a \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para Tutorial HL7\SDK\End-to-End \Tutorial_BTAHL7Drop\Bin.</span><span class="sxs-lookup"><span data-stu-id="f300f-147">In the Add Reference dialog box, click the **Browse** tab. In the **Look In** box, move to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop\Bin.</span></span> <span data-ttu-id="f300f-148">Haga clic en **Microsoft.Solutions.BTAHL7.HL7Schemas.dll**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f300f-148">Click **Microsoft.Solutions.BTAHL7.HL7Schemas.dll**, click **Add**, and then click **OK**.</span></span>  
  
 <span data-ttu-id="f300f-149">Continúe con [paso 5: promocionar las propiedades de esquema](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f300f-149">Proceed to [Step 5: Promote Schema Properties](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f300f-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="f300f-150">See Also</span></span>  
 [<span data-ttu-id="f300f-151">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="f300f-151">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)