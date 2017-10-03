---
title: "Creación e implementación de las canalizaciones de A4SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- deploying, pipelines
- pipelines, deploying
- pipelines, creating
ms.assetid: 2a614510-7e15-4e88-9012-fc019d3aefee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bec21ebd5a3b32986969676a78109cad55d870cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-deploying-a4swift-pipelines"></a><span data-ttu-id="07819-102">Creación e implementación de las canalizaciones de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="07819-102">Creating and Deploying A4SWIFT Pipelines</span></span>
<span data-ttu-id="07819-103">Realice los pasos siguientes para crear e implementar canalizaciones SWIFT reparación de mensajes y nuevo envío, tal como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="07819-103">Perform the following steps to create and deploy SWIFT pipelines for message repair and new submission, as shown in the following figure.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")  
  
 <span data-ttu-id="07819-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="07819-104">**Summary**</span></span>  
  
 <span data-ttu-id="07819-105">Implementar los siguientes esquemas:</span><span class="sxs-lookup"><span data-stu-id="07819-105">Deploy the following schemas:</span></span>  
  
-   <span data-ttu-id="07819-106">Canalización con el Desensamblador de SWIFT de recepción personalizada.</span><span class="sxs-lookup"><span data-stu-id="07819-106">Custom receive pipeline with the SWIFT Disassembler.</span></span> <span data-ttu-id="07819-107">Establecer propiedades de validación de XML y validación de BRE en True y la propiedad de esquema de encabezado de SWIFT en (None).</span><span class="sxs-lookup"><span data-stu-id="07819-107">Set BRE Validation and XML Validation properties to True, and the SWIFT Header Schema property to (None).</span></span>  
  
-   <span data-ttu-id="07819-108">Canalización con el ensamblador de SWIFT de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="07819-108">Custom send pipeline with the SWIFT Assembler</span></span>  
  
### <a name="to-create-a-pipeline-project"></a><span data-ttu-id="07819-109">Para crear un proyecto de canalización</span><span class="sxs-lookup"><span data-stu-id="07819-109">To create a pipeline project</span></span>  
  
1.  <span data-ttu-id="07819-110">En Visual Studio, haga clic en **archivo**, seleccione **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="07819-110">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="07819-111">En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** panel, seleccione la **proyectos de BizTalk** carpeta.</span><span class="sxs-lookup"><span data-stu-id="07819-111">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  
  
3.  <span data-ttu-id="07819-112">En el **plantillas** panel, seleccione **proyecto vacío de servidor BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="07819-112">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  
  
4.  <span data-ttu-id="07819-113">En el **nombre** , escriba el nombre que desea para el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="07819-113">In the **Name** box, type the name you want for the project name.</span></span>  
  
5.  <span data-ttu-id="07819-114">En el **solución** cuadro, seleccione **agregar a solución**.</span><span class="sxs-lookup"><span data-stu-id="07819-114">In the **Solution** box, select **Add to Solution**.</span></span> <span data-ttu-id="07819-115">En el **ubicación** cuadro, escriba la ubicación del objeto de esquema que ha creado en [implementar esquemas de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="07819-115">In the **Location** box, enter the location of the schema project that you created in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  
  
6.  <span data-ttu-id="07819-116">Haga clic en **Aceptar** para abrir el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="07819-116">Click **OK** to open the new project.</span></span>  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="07819-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]Agrega un nuevo proyecto en el Explorador de soluciones y crea la carpeta del proyecto y los archivos en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="07819-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] adds a new project to Solution Explorer, and creates the project folder and files in the folder specified.</span></span>  
  
7.  <span data-ttu-id="07819-118">Crear y asignar un archivo de clave seguro al proyecto.</span><span class="sxs-lookup"><span data-stu-id="07819-118">Create and assign a strong key file to the project.</span></span> <span data-ttu-id="07819-119">Para obtener más información, vea "para crear un proyecto SWIFT con nombre seguro" en [implementar esquemas de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="07819-119">For more information, see "To create a strong-named SWIFT project" in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  
  
### <a name="to-add-a-custom-receive-pipeline"></a><span data-ttu-id="07819-120">Para agregar una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="07819-120">To add a custom receive pipeline</span></span>  
  
1.  <span data-ttu-id="07819-121">En el Explorador de soluciones, haga clic en el proyecto de canalización, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="07819-121">In Solution Explorer, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="07819-122">En el cuadro de diálogo Agregar nuevo elemento, haga clic en **archivos de canalización** en el panel de categorías y, a continuación, seleccione **canalización de recepción** desde el panel de plantillas.</span><span class="sxs-lookup"><span data-stu-id="07819-122">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="07819-123">En el **nombre** , escriba un nombre para la canalización.</span><span class="sxs-lookup"><span data-stu-id="07819-123">In the **Name** box, type a name for the pipeline.</span></span>  
  
4.  <span data-ttu-id="07819-124">Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="07819-124">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
5.  <span data-ttu-id="07819-125">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="07819-125">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  
  
6.  <span data-ttu-id="07819-126">Desde el **cuadro de herramientas de componentes de canalizaciones de BizTalk**, arrastre el **SWIFT Desensamblador** a la **Coloque aquí los** cuadro siguiente la **desensamblar** fase forma de **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="07819-126">From the **BizTalk Pipeline Components Toolbox**, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in **BizTalk Pipeline Designer**.</span></span> <span data-ttu-id="07819-127">Deje el **SWIFT Desensamblador** seleccionado en el **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="07819-127">Leave the **SWIFT Disassembler** as selected in the **BizTalk Pipeline Designer**.</span></span>  
  
7.  <span data-ttu-id="07819-128">En **propiedades**, compruebe que la **BRE validación** y **validación XML** propiedades se establecen en **True**.</span><span class="sxs-lookup"><span data-stu-id="07819-128">In **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07819-129">La propiedad de esquema de encabezado de SWIFT debe establecerse en **(ninguno)**.</span><span class="sxs-lookup"><span data-stu-id="07819-129">The SWIFT Header Schema property should be set to **(None)**.</span></span>  
  
8.  <span data-ttu-id="07819-130">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **archivo**y, a continuación, **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="07819-130">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then **Save All**.</span></span>  
  
### <a name="to-add-a-custom-send-pipeline"></a><span data-ttu-id="07819-131">Para agregar una canalización de envío personalizada</span><span class="sxs-lookup"><span data-stu-id="07819-131">To add a custom send pipeline</span></span>  
  
1.  <span data-ttu-id="07819-132">En el Explorador de soluciones, haga clic en el **SWIFTPipelines** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="07819-132">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="07819-133">En el cuadro de diálogo Agregar nuevo elemento, compruebe que **archivos de canalización** está seleccionado en el panel de categorías y, a continuación, seleccione **canalización de envío** desde el panel de plantillas.</span><span class="sxs-lookup"><span data-stu-id="07819-133">In the Add New Item dialog box, verify that **Pipeline Files** is selected in the Categories pane, and then select **Send Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="07819-134">En el **nombre** , escriba un nombre para la canalización.</span><span class="sxs-lookup"><span data-stu-id="07819-134">In the **Name** box, type a name for the pipeline.</span></span>  
  
4.  <span data-ttu-id="07819-135">Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="07819-135">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07819-136">Una canalización vacía aparece en el Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="07819-136">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="07819-137">Agrega la nueva canalización al explorador de soluciones bajo el proyecto SWIFTPipelines.</span><span class="sxs-lookup"><span data-stu-id="07819-137"> adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
5.  <span data-ttu-id="07819-138">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="07819-138">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  
  
6.  <span data-ttu-id="07819-139">En el **cuadro de herramientas de componentes de canalizaciones de BizTalk**, arrastre **SWIFT ensamblador** a la **Coloque aquí los** cuadro siguiente la **ensamblar** fase forma en **Diseñador de canalizaciones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="07819-139">In the **BizTalk Pipeline Components Toolbox**, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  
  
7.  <span data-ttu-id="07819-140">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **archivo**y, a continuación, **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="07819-140">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then **Save All**.</span></span>  
  
8.  <span data-ttu-id="07819-141">Haga clic en el proyecto de canalizaciones y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="07819-141">Right click the pipelines project, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07819-142">Durante el proceso de compilación, no debería ver los errores.</span><span class="sxs-lookup"><span data-stu-id="07819-142">During the compilation process, you should not see any failures.</span></span> <span data-ttu-id="07819-143">Si lo hace, compruebe el origen del error, corríjalo y, a continuación, volver a compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="07819-143">If you do, check the source of the error, correct it and then re-build the project.</span></span> <span data-ttu-id="07819-144">Sin embargo, es podrán, vea las advertencias.</span><span class="sxs-lookup"><span data-stu-id="07819-144">You may, however, see warnings.</span></span> <span data-ttu-id="07819-145">Puede corregir la condición que conduce a las advertencias.</span><span class="sxs-lookup"><span data-stu-id="07819-145">You can correct the condition leading to the warnings.</span></span> <span data-ttu-id="07819-146">Para obtener más información, vea "Crear un proyecto de canalización podrían producir advertencias de" en [varios problemas conocidos](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span><span class="sxs-lookup"><span data-stu-id="07819-146">For more information, see "Building a pipeline project may result in warnings" in [Miscellaneous Known Issues](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span></span>  
  
9. <span data-ttu-id="07819-147">Haga clic en el proyecto de canalizaciones y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="07819-147">Right click the pipelines project, and then click **Deploy**.</span></span>