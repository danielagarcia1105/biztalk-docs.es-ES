---
title: Crear e implementar canalizaciones de A4SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- deploying, pipelines
- pipelines, deploying
- pipelines, creating
ms.assetid: 2a614510-7e15-4e88-9012-fc019d3aefee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d337b97dfb1973ef10c113ae0a206a51dcd63b1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002453"
---
# <a name="creating-and-deploying-a4swift-pipelines"></a><span data-ttu-id="4589f-102">Crear e implementar canalizaciones de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="4589f-102">Creating and Deploying A4SWIFT Pipelines</span></span>
<span data-ttu-id="4589f-103">Realice los pasos siguientes para crear e implementar canalizaciones SWIFT para reparación de mensajes y nuevo envío, tal como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="4589f-103">Perform the following steps to create and deploy SWIFT pipelines for message repair and new submission, as shown in the following figure.</span></span>  

 <span data-ttu-id="4589f-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")</span><span class="sxs-lookup"><span data-stu-id="4589f-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")</span></span>  

 <span data-ttu-id="4589f-105">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="4589f-105">**Summary**</span></span>  

 <span data-ttu-id="4589f-106">Implemente los siguientes esquemas:</span><span class="sxs-lookup"><span data-stu-id="4589f-106">Deploy the following schemas:</span></span>  

-   <span data-ttu-id="4589f-107">Canalización con el Desensamblador de SWIFT de recepción personalizada.</span><span class="sxs-lookup"><span data-stu-id="4589f-107">Custom receive pipeline with the SWIFT Disassembler.</span></span> <span data-ttu-id="4589f-108">Establecer propiedades de validación de XML y la validación del BRE en True y la propiedad de esquema de encabezado de SWIFT en (None).</span><span class="sxs-lookup"><span data-stu-id="4589f-108">Set BRE Validation and XML Validation properties to True, and the SWIFT Header Schema property to (None).</span></span>  

-   <span data-ttu-id="4589f-109">Canalización con el ensamblador de SWIFT de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="4589f-109">Custom send pipeline with the SWIFT Assembler</span></span>  

### <a name="to-create-a-pipeline-project"></a><span data-ttu-id="4589f-110">Para crear un proyecto de canalización</span><span class="sxs-lookup"><span data-stu-id="4589f-110">To create a pipeline project</span></span>  

1. <span data-ttu-id="4589f-111">En Visual Studio, haga clic en **archivo**, apunte a **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4589f-111">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  

2. <span data-ttu-id="4589f-112">En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** panel, seleccione el **proyectos de BizTalk** carpeta.</span><span class="sxs-lookup"><span data-stu-id="4589f-112">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  

3. <span data-ttu-id="4589f-113">En el **plantillas** panel, seleccione **proyecto vacío de servidor BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="4589f-113">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  

4. <span data-ttu-id="4589f-114">En el **nombre** , escriba el nombre que desee para el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4589f-114">In the **Name** box, type the name you want for the project name.</span></span>  

5. <span data-ttu-id="4589f-115">En el **solución** cuadro, seleccione **agregar a solución**.</span><span class="sxs-lookup"><span data-stu-id="4589f-115">In the **Solution** box, select **Add to Solution**.</span></span> <span data-ttu-id="4589f-116">En el **ubicación** , escriba la ubicación del proyecto de esquema que ha creado en [implementar esquemas de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="4589f-116">In the **Location** box, enter the location of the schema project that you created in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  

6. <span data-ttu-id="4589f-117">Haga clic en **Aceptar** para abrir el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="4589f-117">Click **OK** to open the new project.</span></span>  
   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="4589f-118">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Agrega un nuevo proyecto en el Explorador de soluciones y crea la carpeta de proyecto y archivos en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="4589f-118">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] adds a new project to Solution Explorer, and creates the project folder and files in the folder specified.</span></span>  

7. <span data-ttu-id="4589f-119">Crear y asignar un archivo de clave seguro al proyecto.</span><span class="sxs-lookup"><span data-stu-id="4589f-119">Create and assign a strong key file to the project.</span></span> <span data-ttu-id="4589f-120">Para obtener más información, vea "para crear un proyecto SWIFT con nombre seguro" en [implementar esquemas de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="4589f-120">For more information, see "To create a strong-named SWIFT project" in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  

### <a name="to-add-a-custom-receive-pipeline"></a><span data-ttu-id="4589f-121">Para agregar una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="4589f-121">To add a custom receive pipeline</span></span>  

1. <span data-ttu-id="4589f-122">En el Explorador de soluciones, haga clic en el proyecto de canalización, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="4589f-122">In Solution Explorer, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="4589f-123">En el cuadro de diálogo Agregar nuevo elemento, haga clic en **archivos de canalización** en el panel de categorías y, a continuación, seleccione **canalización de recepción** desde el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="4589f-123">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** from the Templates pane.</span></span>  

3. <span data-ttu-id="4589f-124">En el **nombre** , escriba un nombre para la canalización.</span><span class="sxs-lookup"><span data-stu-id="4589f-124">In the **Name** box, type a name for the pipeline.</span></span>  

4. <span data-ttu-id="4589f-125">Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4589f-125">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  

5. <span data-ttu-id="4589f-126">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="4589f-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  

6. <span data-ttu-id="4589f-127">Desde el **cuadro de herramientas de componentes de canalización de BizTalk**, arrastre el **Desensamblador de SWIFT** a la **Coloque aquí** cuadro a continuación el **desensamblar** fase en la forma **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="4589f-127">From the **BizTalk Pipeline Components Toolbox**, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in **BizTalk Pipeline Designer**.</span></span> <span data-ttu-id="4589f-128">Deje el **Desensamblador de SWIFT** seleccionado en el **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="4589f-128">Leave the **SWIFT Disassembler** as selected in the **BizTalk Pipeline Designer**.</span></span>  

7. <span data-ttu-id="4589f-129">En **propiedades**, compruebe que la **BRE validación** y **validación XML** propiedades se establecen en **True**.</span><span class="sxs-lookup"><span data-stu-id="4589f-129">In **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4589f-130">Debe establecerse la propiedad de esquema de encabezado de SWIFT **(ninguno)**.</span><span class="sxs-lookup"><span data-stu-id="4589f-130">The SWIFT Header Schema property should be set to **(None)**.</span></span>  

8. <span data-ttu-id="4589f-131">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **archivo**y, a continuación, **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="4589f-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then **Save All**.</span></span>  

### <a name="to-add-a-custom-send-pipeline"></a><span data-ttu-id="4589f-132">Para agregar una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="4589f-132">To add a custom send pipeline</span></span>  

1. <span data-ttu-id="4589f-133">En el Explorador de soluciones, haga clic en el **SWIFTPipelines** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="4589f-133">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="4589f-134">En el cuadro de diálogo Agregar nuevo elemento, compruebe que **archivos de canalización** está seleccionado en el panel de categorías y, a continuación, seleccione **canalización de envío** desde el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="4589f-134">In the Add New Item dialog box, verify that **Pipeline Files** is selected in the Categories pane, and then select **Send Pipeline** from the Templates pane.</span></span>  

3. <span data-ttu-id="4589f-135">En el **nombre** , escriba un nombre para la canalización.</span><span class="sxs-lookup"><span data-stu-id="4589f-135">In the **Name** box, type a name for the pipeline.</span></span>  

4. <span data-ttu-id="4589f-136">Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4589f-136">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4589f-137">Una canalización vacía aparece en el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4589f-137">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="4589f-138"> Agrega la nueva canalización al explorador de soluciones bajo el proyecto SWIFTPipelines.</span><span class="sxs-lookup"><span data-stu-id="4589f-138"> adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  

5. <span data-ttu-id="4589f-139">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="4589f-139">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  

6. <span data-ttu-id="4589f-140">En el **cuadro de herramientas de componentes de canalización de BizTalk**, arrastre **ensamblador de SWIFT** a la **Coloque aquí** cuadro a continuación el **ensamblar** en forma de fase **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="4589f-140">In the **BizTalk Pipeline Components Toolbox**, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  

7. <span data-ttu-id="4589f-141">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **archivo**y, a continuación, **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="4589f-141">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then **Save All**.</span></span>  

8. <span data-ttu-id="4589f-142">A la derecha, haga clic en el proyecto de canalizaciones y, a continuación, haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="4589f-142">Right click the pipelines project, and then click **Build**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4589f-143">Durante el proceso de compilación, no debería ver los errores.</span><span class="sxs-lookup"><span data-stu-id="4589f-143">During the compilation process, you should not see any failures.</span></span> <span data-ttu-id="4589f-144">Si lo hace, comprobar el origen del error, corríjalo y, a continuación, volver a compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4589f-144">If you do, check the source of the error, correct it and then re-build the project.</span></span> <span data-ttu-id="4589f-145">Sin embargo, es posible que, verá advertencias.</span><span class="sxs-lookup"><span data-stu-id="4589f-145">You may, however, see warnings.</span></span> <span data-ttu-id="4589f-146">Puede corregir la condición que conduce a las advertencias.</span><span class="sxs-lookup"><span data-stu-id="4589f-146">You can correct the condition leading to the warnings.</span></span> <span data-ttu-id="4589f-147">Para obtener más información, vea "Creación de un proyecto de canalización podrían producir advertencias de" en [varios problemas conocidos](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span><span class="sxs-lookup"><span data-stu-id="4589f-147">For more information, see "Building a pipeline project may result in warnings" in [Miscellaneous Known Issues](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span></span>  

9. <span data-ttu-id="4589f-148">A la derecha, haga clic en el proyecto de canalizaciones y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="4589f-148">Right click the pipelines project, and then click **Deploy**.</span></span>
