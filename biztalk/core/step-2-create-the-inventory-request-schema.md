---
title: 'Paso 2: Crear el esquema de solicitud de inventario | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fa9ad9f-b815-4baf-8299-556869b8dde7
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5199b20a75b82e12ad76b96903538487a3128668
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-the-inventory-request-schema"></a><span data-ttu-id="9c84a-102">Paso 2: Crear el esquema de solicitud de inventario</span><span class="sxs-lookup"><span data-stu-id="9c84a-102">Step 2: Create the Inventory Request Schema</span></span>
<span data-ttu-id="9c84a-103">![Paso 2 de 5](../core/media/step-2of5.gif "Step_2of5")</span><span class="sxs-lookup"><span data-stu-id="9c84a-103">![Step 2 of 5](../core/media/step-2of5.gif "Step_2of5")</span></span>  
  
 <span data-ttu-id="9c84a-104">**Tiempo en completarse:** 7 minutos</span><span class="sxs-lookup"><span data-stu-id="9c84a-104">**Time to complete:** 7 minutes</span></span>  
  
 <span data-ttu-id="9c84a-105">**Objetivo:** en este paso, se define el esquema del mensaje de reposición de inventario.</span><span class="sxs-lookup"><span data-stu-id="9c84a-105">**Objective:** In this step, you define the schema of the inventory replenishment message.</span></span>  <span data-ttu-id="9c84a-106">El sistema del almacén envía este mensaje para solicitar la reposición del inventario.</span><span class="sxs-lookup"><span data-stu-id="9c84a-106">The warehouse system sends this message for requesting inventory replenishment.</span></span>  <span data-ttu-id="9c84a-107">Es uno de los dos esquemas que debe crear para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c84a-107">This is one of the two schemas you must create for this project.</span></span>  
  
 <span data-ttu-id="9c84a-108">**Propósito:** XML no solo las estructuras e identifica información con códigos de lenguaje de marcado normalizados, pero también tiene la capacidad de utilizar los esquemas.</span><span class="sxs-lookup"><span data-stu-id="9c84a-108">**Purpose:** XML not only structures and identifies information with standardized markup codes, but also has the ability to use schemas.</span></span> <span data-ttu-id="9c84a-109">Un esquema es un documento XML que funciona como un diccionario y que otros documentos XML utilizan como referencia.</span><span class="sxs-lookup"><span data-stu-id="9c84a-109">A schema is an XML document that works like a dictionary and is used as a reference by other XML documents.</span></span> <span data-ttu-id="9c84a-110">El código del esquema define la ortografía de los elementos XML y el tipo de datos que esos elementos contienen.</span><span class="sxs-lookup"><span data-stu-id="9c84a-110">The schema code defines the spelling of XML elements and the type of data enclosed by those elements.</span></span> <span data-ttu-id="9c84a-111">Los esquemas proporcionan una manera fácil para que un programa procese documentos XML y garantizan que la estructura y tipo de información son correctos.</span><span class="sxs-lookup"><span data-stu-id="9c84a-111">Using schemas provides an easy way for a program to process XML documents and ensures that the structure and type of information is correct.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c84a-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9c84a-112">Prerequisites</span></span>  
 <span data-ttu-id="9c84a-113">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="9c84a-113">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="9c84a-114">Antes de comenzar este paso debe completar [paso 1: crear el proyecto de EAISchemas](../core/step-1-create-eaischemas-project.md).</span><span class="sxs-lookup"><span data-stu-id="9c84a-114">Before you begin this step you must complete [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9c84a-115">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9c84a-115">Procedures</span></span>  
 <span data-ttu-id="9c84a-116">En [paso 1: crear el proyecto de EAISchemas](../core/step-1-create-eaischemas-project.md), creó un nuevo [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c84a-116">In [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md), you created a new [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project.</span></span>  <span data-ttu-id="9c84a-117">Si cierra la ventana de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], puede utilizar el siguiente procedimiento para abrir el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c84a-117">If you close the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, you can use the following procedure to open the project.</span></span>  <span data-ttu-id="9c84a-118">En caso contrario, puede omitir el procedimiento "Abrir el proyecto de Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="9c84a-118">Otherwise, you can skip this procedure, “To open the Visual Studio project”.</span></span>  
  
#### <a name="to-open-the-visual-studio-project"></a><span data-ttu-id="9c84a-119">Abrir el proyecto de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9c84a-119">To open the Visual Studio project</span></span>  
  
1.  <span data-ttu-id="9c84a-120">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-120">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="9c84a-121">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **abiertos**y, a continuación, haga clic en **proyecto/solución**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-121">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="9c84a-122">En el **Abrir proyecto** cuadro de diálogo, vaya a la **C:\BTSTutorials\EAISolution\EAISolution.sln** archivo de solución y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-122">In the **Open Project** dialog box, browse to the **C:\BTSTutorials\EAISolution\EAISolution.sln** solution file, and then click **Open**.</span></span>  
  
 <span data-ttu-id="9c84a-123">En el siguiente procedimiento, agregará un nuevo archivo de esquema al proyecto para el mensaje de reposición del inventario.</span><span class="sxs-lookup"><span data-stu-id="9c84a-123">In the following procedure, you add a new schema file to the project for the inventory replenishment message.</span></span>  
  
#### <a name="to-add-a-new-schema-to-the-project"></a><span data-ttu-id="9c84a-124">Para agregar un nuevo esquema al proyecto</span><span class="sxs-lookup"><span data-stu-id="9c84a-124">To add a new schema to the project</span></span>  
  
1.  <span data-ttu-id="9c84a-125">En el Explorador de soluciones, haga clic en el **EAISchemas** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-125">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="9c84a-126">En el **Agregar nuevo elemento - EAISchemas** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c84a-126">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="9c84a-127">Use</span><span class="sxs-lookup"><span data-stu-id="9c84a-127">Use this</span></span>|<span data-ttu-id="9c84a-128">Para</span><span class="sxs-lookup"><span data-stu-id="9c84a-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9c84a-129">**Plantillas instaladas**</span><span class="sxs-lookup"><span data-stu-id="9c84a-129">**Installed Templates**</span></span>|<span data-ttu-id="9c84a-130">Haga clic en **archivos de esquema**, a continuación, haga clic en **esquema**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-130">Click **Schema Files**, then click **Schema**.</span></span>|  
    |<span data-ttu-id="9c84a-131">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9c84a-131">**Name**</span></span>|<span data-ttu-id="9c84a-132">Tipo de **Request.xsd**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-132">Type **Request.xsd**.</span></span>|  
  
3.  <span data-ttu-id="9c84a-133">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-133">Click **Add**.</span></span> <span data-ttu-id="9c84a-134">Aparecerán el árbol de esquema y el panel de XSD.</span><span class="sxs-lookup"><span data-stu-id="9c84a-134">The schema tree and XSD pane appear.</span></span> <span data-ttu-id="9c84a-135">Esta parte de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] se denomina Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9c84a-135">This area of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is referred to as BizTalk Editor.</span></span> <span data-ttu-id="9c84a-136">Además, aparece el nuevo esquema en el Explorador de soluciones bajo el proyecto EAISchemas.</span><span class="sxs-lookup"><span data-stu-id="9c84a-136">In addition, your new schema appears in Solution Explorer below the EAISchemas project.</span></span>  
  
     <span data-ttu-id="9c84a-137">![Diferentes partes del proyecto de BizTalk](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span><span class="sxs-lookup"><span data-stu-id="9c84a-137">![Different Parts of BizTalk Project](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span></span>  
  
#### <a name="to-add-elements-to-the-schema"></a><span data-ttu-id="9c84a-138">Agregar elementos al esquema</span><span class="sxs-lookup"><span data-stu-id="9c84a-138">To add elements to the schema</span></span>  
  
1.  <span data-ttu-id="9c84a-139">En el árbol de esquema, haga clic en el **raíz** nodo.</span><span class="sxs-lookup"><span data-stu-id="9c84a-139">In schema tree, click the **Root** node.</span></span>  
  
2.  <span data-ttu-id="9c84a-140">En el panel Propiedades, cambie el valor de la **nombre de nodo** propiedad `Request`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="9c84a-140">In the Properties pane, change the value of the **Node Name** property to `Request`, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="9c84a-141">En el árbol de esquema, haga clic en el **solicitar** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-141">In schema tree, right-click the **Request** node, point to **Insert Schema Node**, and then click **Child Record**.</span></span>  
  
4.  <span data-ttu-id="9c84a-142">Tipo `Header` como el nuevo nombre para el registro secundario y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="9c84a-142">Type `Header` as the new name for the child record, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="9c84a-143">Repita los pasos 3 y 4 para crear un segundo nodo secundario registro para el **solicitar** nodo y asígnele el nombre `Items`.</span><span class="sxs-lookup"><span data-stu-id="9c84a-143">Repeat step 3 and 4 to create a second child record for the **Request** node, and name it `Items`.</span></span>  
  
6.  <span data-ttu-id="9c84a-144">En el árbol de esquema, haga clic en el **encabezado** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-144">In schema tree, right-click the **Header** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  
  
7.  <span data-ttu-id="9c84a-145">Tipo `ReqID` como el nuevo nombre para el elemento y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="9c84a-145">Type `ReqID` as the new name for the element, and then press ENTER.</span></span>  
  
8.  <span data-ttu-id="9c84a-146">Elemento de campo Repita el paso 6 y 7 para crear un segundo nodo secundario para el **encabezado** nodo y asígnele el nombre `OrderDate`.</span><span class="sxs-lookup"><span data-stu-id="9c84a-146">Repeat step 6 and 7 to create a second child field element for the **Header** node, and name it `OrderDate`.</span></span>  
  
9. <span data-ttu-id="9c84a-147">En el árbol de esquema, haga clic en el **elementos** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-147">In schema tree, right-click the **Items** node, point to **Insert Schemas Node**, and then click **Child Record**.</span></span>  
  
10. <span data-ttu-id="9c84a-148">Tipo `Item` como el nuevo nombre para el registro secundario y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="9c84a-148">Type `Item` as the new name for the child record, and then press ENTER.</span></span>  
  
11. <span data-ttu-id="9c84a-149">En el árbol de esquema, haga clic en el **elemento** nodo y agregue los elementos de campo secundarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c84a-149">In schema tree, right-click the **Item** node, and add the following child field elements:</span></span>  
  
    -   `Description`  
  
    -   `Quantity`  
  
    -   `UnitPrice`  
  
     <span data-ttu-id="9c84a-150">El Request.xsd finalizado debería parecerse al de la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="9c84a-150">The completed Request.xsd should look similar to the following figure.</span></span>  
  
     <span data-ttu-id="9c84a-151">![El Explorador de soluciones con el esquema de solicitud](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")</span><span class="sxs-lookup"><span data-stu-id="9c84a-151">![Solution Explorer with the Request Schema](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")</span></span>  
  
 <span data-ttu-id="9c84a-152">Al agregar nodos a un esquema, el Editor de BizTalk proporciona un conjunto de valores predeterminado para las propiedades.</span><span class="sxs-lookup"><span data-stu-id="9c84a-152">When you add nodes to a schema, BizTalk Editor gives a set of default values for their properties.</span></span>  <span data-ttu-id="9c84a-153">Debe configurarlos en función de los requisitos.</span><span class="sxs-lookup"><span data-stu-id="9c84a-153">You must configure them based on the requirements.</span></span>  
  
#### <a name="to-configure-the-elements"></a><span data-ttu-id="9c84a-154">Configurar los elementos</span><span class="sxs-lookup"><span data-stu-id="9c84a-154">To configure the elements</span></span>  
  
1.  <span data-ttu-id="9c84a-155">En el árbol de esquema, haga clic en **OrderDate** para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="9c84a-155">In schema tree, click **OrderDate** to select it.</span></span>  
  
2.  <span data-ttu-id="9c84a-156">En el panel Propiedades, cambie **tipo de datos** a **xs: DateTime**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-156">In the Properties pane, change **Data Type** to **xs:dateTime**.</span></span>  
  
3.  <span data-ttu-id="9c84a-157">Repita los pasos 1 y 2 para configurar las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9c84a-157">Repeat step 1 and 2 to configure the following properties:</span></span>  
  
    |<span data-ttu-id="9c84a-158">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c84a-158">Element</span></span>|<span data-ttu-id="9c84a-159">Propiedad</span><span class="sxs-lookup"><span data-stu-id="9c84a-159">Property</span></span>|<span data-ttu-id="9c84a-160">Valor</span><span class="sxs-lookup"><span data-stu-id="9c84a-160">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="9c84a-161">**GrandTotal**</span><span class="sxs-lookup"><span data-stu-id="9c84a-161">**GrandTotal**</span></span>|<span data-ttu-id="9c84a-162">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9c84a-162">**Data Type**</span></span>|<span data-ttu-id="9c84a-163">**Xs: decimal**</span><span class="sxs-lookup"><span data-stu-id="9c84a-163">**Xs:decimal**</span></span>|  
    |<span data-ttu-id="9c84a-164">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="9c84a-164">**Item**</span></span>|<span data-ttu-id="9c84a-165">**Número máximo de instancias**</span><span class="sxs-lookup"><span data-stu-id="9c84a-165">**Max Occurs**</span></span>|<span data-ttu-id="9c84a-166">**Sin enlazar**</span><span class="sxs-lookup"><span data-stu-id="9c84a-166">**Unbounded**</span></span>|  
    |<span data-ttu-id="9c84a-167">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="9c84a-167">**Item**</span></span>|<span data-ttu-id="9c84a-168">**Número mínimo de instancias**</span><span class="sxs-lookup"><span data-stu-id="9c84a-168">**Min Occurs**</span></span>|<span data-ttu-id="9c84a-169">**1**</span><span class="sxs-lookup"><span data-stu-id="9c84a-169">**1**</span></span>|  
    |<span data-ttu-id="9c84a-170">**Cantidad**</span><span class="sxs-lookup"><span data-stu-id="9c84a-170">**Quantity**</span></span>|<span data-ttu-id="9c84a-171">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9c84a-171">**Data Type**</span></span>|<span data-ttu-id="9c84a-172">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="9c84a-172">**xs:unsignedInt**</span></span>|  
  
 <span data-ttu-id="9c84a-173">Un esquema puede tener muchos elementos, pero la aplicación puede necesitar que solo se utilicen algunos de ellos para el procesamiento de los datos.</span><span class="sxs-lookup"><span data-stu-id="9c84a-173">A schema can have many elements, but your application may only require that you use a few of them for your data processing.</span></span> <span data-ttu-id="9c84a-174">Para conservar los recursos del equipo, BizTalk Server no lee automáticamente todos los elementos de esquema.</span><span class="sxs-lookup"><span data-stu-id="9c84a-174">To save computer resources, BizTalk Server doesn't automatically read each schema element.</span></span> <span data-ttu-id="9c84a-175">Si desea que BizTalk Server lea los datos de un elemento concreto, debe identificar ese elemento con el Editor de BizTalk para promocionar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="9c84a-175">If you want BizTalk Server to read data from a specific element, you must identify that element by using BizTalk Editor to promote its properties.</span></span>  
  
 <span data-ttu-id="9c84a-176">La orquestación que crearemos en [lección 2: definir el proceso empresarial](../core/lesson-2-define-the-business-process.md) estará basada en el campo GrandTotal para enrutar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="9c84a-176">The orchestration that we will create in [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md) will base on the GrandTotal field to route messages.</span></span>  <span data-ttu-id="9c84a-177">En consecuencia, debemos promocionar el campo GrandTotal.</span><span class="sxs-lookup"><span data-stu-id="9c84a-177">So we must promote the GrandTotal field.</span></span>  
  
#### <a name="to-promote-an-element"></a><span data-ttu-id="9c84a-178">Promocionar un elemento</span><span class="sxs-lookup"><span data-stu-id="9c84a-178">To promote an element</span></span>  
  
1.  <span data-ttu-id="9c84a-179">En el árbol de esquema, haga clic en **GrandTotal**, seleccione **promover**y, a continuación, haga clic en **promociones rápidas**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-179">In Schema tree, right-click **GrandTotal**, point to **Promote**, and then click **Quick Promotions**.</span></span>  
  
2.  <span data-ttu-id="9c84a-180">Haga clic en **Aceptar** para confirmar la adición de un esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9c84a-180">Click **OK** to acknowledge adding a property schema.</span></span>  
  
3.  <span data-ttu-id="9c84a-181">En el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="9c84a-181">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="9c84a-182">Síntesis</span><span class="sxs-lookup"><span data-stu-id="9c84a-182">What did I just do?</span></span>  
 <span data-ttu-id="9c84a-183">En este paso, ha definido el esquema del mensaje para la reposición del inventario de almacén.</span><span class="sxs-lookup"><span data-stu-id="9c84a-183">In this step, you defined the warehouse inventory replenishment message schema.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9c84a-184">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9c84a-184">Next Steps</span></span>  
 <span data-ttu-id="9c84a-185">Debe definir el esquema del mensaje de declinación de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9c84a-185">You define the request decline message schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c84a-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c84a-186">See Also</span></span>  
 <span data-ttu-id="9c84a-187">[Paso 1: Crear el proyecto EAISchemas](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="9c84a-187">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="9c84a-188">[Paso 3: Crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="9c84a-188">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="9c84a-189">[Paso 4: Crear el mapa](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="9c84a-189">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="9c84a-190">[Paso 5: Generar el proyecto EAISchemas](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="9c84a-190">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 <span data-ttu-id="9c84a-191">[Crear esquemas con el Editor de BizTalk](../core/creating-schemas-using-biztalk-editor.md) </span><span class="sxs-lookup"><span data-stu-id="9c84a-191">[Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md) </span></span>  
 [<span data-ttu-id="9c84a-192">Acerca de las propiedades de contexto de mensaje de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9c84a-192">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)