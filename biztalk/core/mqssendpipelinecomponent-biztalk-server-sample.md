---
title: MQSSendPipelineComponent (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- pipelines, examples
- MQSeries adapters, examples
- examples, pipelines
ms.assetid: ac709e45-524b-45ab-9673-060790ecbed2
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc89b19f1e493c46e6128d390774479eb59bc6b0
ms.sourcegitcommit: e172dedfd00d4de3a40c8289f3a97ef65cdadd3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2018
ms.locfileid: "36975917"
---
# <a name="mqssendpipelinecomponent-biztalk-server-sample"></a><span data-ttu-id="ea79b-102">MQSSendPipelineComponent (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="ea79b-102">MQSSendPipelineComponent (BizTalk Server Sample)</span></span>
<span data-ttu-id="ea79b-103">En este ejemplo se muestra cómo escribir un componente de canalización que lea un conjunto de valores de propiedades de MQSeries a partir de un archivo XML y que los aplique a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ea79b-103">This sample demonstrates how to write a pipeline component that reads a set of MQSeries property values from an XML file and applies them to a message.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ea79b-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea79b-104">What This Sample Does</span></span>  
 <span data-ttu-id="ea79b-105">Este ejemplo se compone de dos proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], un proyecto del componente de canalización y un proyecto de canalización que hace uso del componente.</span><span class="sxs-lookup"><span data-stu-id="ea79b-105">This sample is composed of two [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects, a pipeline component project and a pipeline project that makes use of the pipeline component.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ea79b-106">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea79b-106">Where to Find This Sample</span></span>  
  
- <span data-ttu-id="ea79b-107">*\<Ruta de ejemplos\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyComponent</span><span class="sxs-lookup"><span data-stu-id="ea79b-107">*\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyComponent</span></span>  
  
- <span data-ttu-id="ea79b-108">*\<Ruta de ejemplos\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyPipeline</span><span class="sxs-lookup"><span data-stu-id="ea79b-108">*\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyPipeline</span></span>  
  
  <span data-ttu-id="ea79b-109">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="ea79b-109">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|                                                                              <span data-ttu-id="ea79b-110">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="ea79b-110">**File**</span></span>                                                                               |                                         <span data-ttu-id="ea79b-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ea79b-111">**Description**</span></span>                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ea79b-112">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln,</span><span class="sxs-lookup"><span data-stu-id="ea79b-112">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln,</span></span><br /><br /> <span data-ttu-id="ea79b-113">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.csproj</span><span class="sxs-lookup"><span data-stu-id="ea79b-113">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.csproj</span></span> |                    <span data-ttu-id="ea79b-114">Archivos de proyectos y soluciones para el componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="ea79b-114">The project and solution files for the pipeline component.</span></span>                    |
|                                              <span data-ttu-id="ea79b-115">SetMQSeriesHeaderPropertyComponent\CSetMQSeriesHeaderPropertyComponent.cs</span><span class="sxs-lookup"><span data-stu-id="ea79b-115">SetMQSeriesHeaderPropertyComponent\CSetMQSeriesHeaderPropertyComponent.cs</span></span>                                              |                      <span data-ttu-id="ea79b-116">Archivo de origen de Visual C#® para el componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="ea79b-116">The Visual C#® source file for the pipeline component.</span></span>                      |
|                                                      <span data-ttu-id="ea79b-117">SetMQSeriesHeaderPropertyComponent\SetMQSMQMDHdrProps.xml</span><span class="sxs-lookup"><span data-stu-id="ea79b-117">SetMQSeriesHeaderPropertyComponent\SetMQSMQMDHdrProps.xml</span></span>                                                      |                 <span data-ttu-id="ea79b-118">Propiedades de MQSeries leídas y usadas por el componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="ea79b-118">The MQSeries properties read and used by the pipeline component.</span></span>                 |
|   <span data-ttu-id="ea79b-119">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btproj,</span><span class="sxs-lookup"><span data-stu-id="ea79b-119">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btproj,</span></span><br /><br /> <span data-ttu-id="ea79b-120">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln</span><span class="sxs-lookup"><span data-stu-id="ea79b-120">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln</span></span>   |                     <span data-ttu-id="ea79b-121">Archivos de proyectos y soluciones para la canalización de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ea79b-121">The project and solution files for the BizTalk pipeline.</span></span>                     |
|                                               <span data-ttu-id="ea79b-122">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.snk</span><span class="sxs-lookup"><span data-stu-id="ea79b-122">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.snk</span></span>                                               |                   <span data-ttu-id="ea79b-123">Archivo de clave de nombre seguro para el proyecto de canalización de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ea79b-123">The strong naming key file for the BizTalk pipeline project.</span></span>                   |
|                                               <span data-ttu-id="ea79b-124">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="ea79b-124">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btp</span></span>                                               | <span data-ttu-id="ea79b-125">La canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea79b-125">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline.</span></span> |
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="ea79b-126">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea79b-126">How to Use This Sample</span></span>  
 <span data-ttu-id="ea79b-127">Para crear la aplicación, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="ea79b-127">To create the application, you must complete the following steps:</span></span>  
  
1. <span data-ttu-id="ea79b-128">Crear las carpetas para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ea79b-128">Create the folders for the application.</span></span>  
  
2. <span data-ttu-id="ea79b-129">Modificar y compilar el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para el componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="ea79b-129">Modify and compile the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the pipeline component.</span></span>  
  
3. <span data-ttu-id="ea79b-130">Copiar el ensamblado compilado y el archivo de encabezado en las carpetas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="ea79b-130">Copy the compiled assembly and the header file to the appropriate folders.</span></span>  
  
4. <span data-ttu-id="ea79b-131">Modificar el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para la canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea79b-131">Modify the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline.</span></span>  
  
5. <span data-ttu-id="ea79b-132">Compilar e implementar el proyecto de canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea79b-132">Compile and deploy the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline project.</span></span>  
  
6. <span data-ttu-id="ea79b-133">Configurar una ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea79b-133">Set up a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location.</span></span>  
  
7. <span data-ttu-id="ea79b-134">Crear una cola de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="ea79b-134">Create a MQSeries queue.</span></span>  
  
8. <span data-ttu-id="ea79b-135">Configurar un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ea79b-135">Set up a send port.</span></span>  
  
9. <span data-ttu-id="ea79b-136">Habilitar la ubicación de recepción e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ea79b-136">Enable the receive location and start the send port.</span></span>  
  
## <a name="creating-the-folders-for-the-application"></a><span data-ttu-id="ea79b-137">Crear las carpetas para la aplicación</span><span class="sxs-lookup"><span data-stu-id="ea79b-137">Creating the Folders for the Application</span></span>  
 <span data-ttu-id="ea79b-138">Este procedimiento crea las carpetas correspondientes para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ea79b-138">This procedure creates the appropriate folders for the application.</span></span>  
  
#### <a name="to-create-the-folders-for-the-application"></a><span data-ttu-id="ea79b-139">Para crear las carpetas para la aplicación</span><span class="sxs-lookup"><span data-stu-id="ea79b-139">To create the folders for the application</span></span>  
  
1.  <span data-ttu-id="ea79b-140">Cree una carpeta denominada **temp** en la unidad C:\ si aún no existe.</span><span class="sxs-lookup"><span data-stu-id="ea79b-140">Create a folder named **temp** on your C:\ drive if it does not already exist.</span></span>  
  
2.  <span data-ttu-id="ea79b-141">Cree una carpeta bajo la **C:\temp** directorio denominado **Pickup3**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-141">Create a folder under the **C:\temp** directory named **Pickup3**.</span></span>  
  
## <a name="modifying-and-compiling-the-project-for-the-pipeline-component"></a><span data-ttu-id="ea79b-142">Modificar y compilar el proyecto para el componente de canalización</span><span class="sxs-lookup"><span data-stu-id="ea79b-142">Modifying and Compiling the Project for the Pipeline Component</span></span>  
 <span data-ttu-id="ea79b-143">Este procedimiento modifica y compila el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para el componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="ea79b-143">This procedure modifies and compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the pipeline component.</span></span>  
  
#### <a name="to-modify-and-compile-the-project-for-the-pipeline-component"></a><span data-ttu-id="ea79b-144">Para modificar y compilar el proyecto para el componente de canalización</span><span class="sxs-lookup"><span data-stu-id="ea79b-144">To modify and compile the project for the pipeline component</span></span>  
  
1. <span data-ttu-id="ea79b-145">Haga doble clic en el archivo de solución, **Setmqseriesheaderpropertycomponent\setmqseriesheaderpropertycomponent** para abrir la solución en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea79b-145">Double-click the solution file, **SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln** to open the solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="ea79b-146">Haga doble clic en el archivo de clase **CSetMQSeriesHeaderPropertyComponent.cs** para abrir el archivo de clase en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea79b-146">Double-click the class file **CSetMQSeriesHeaderPropertyComponent.cs** to open the class file in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
3. <span data-ttu-id="ea79b-147">Busque la variable **samplesDir**, compruebe que esta variable se establece en la ubicación **C:\temp**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-147">Locate the variable **samplesDir**, verify that this variable is set to the location **C:\temp**.</span></span>  
  
4. <span data-ttu-id="ea79b-148">Haga clic en la solución en el Explorador de soluciones y haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-148">Right-click the solution in the Solution Explorer and click **Build**.</span></span> <span data-ttu-id="ea79b-149">Esto compilará el proyecto en un dll ubicado en el **SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent\bin\Debug\\**  directory.</span><span class="sxs-lookup"><span data-stu-id="ea79b-149">This will compile the project into a dll located in the **SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent\bin\Debug\\** directory.</span></span>  
  
## <a name="copying-the-assembly-and-header-file-to-appropriate-folders"></a><span data-ttu-id="ea79b-150">Copiar el ensamblado y el archivo de encabezado en las carpetas adecuadas</span><span class="sxs-lookup"><span data-stu-id="ea79b-150">Copying the Assembly and Header File to Appropriate Folders</span></span>  
 <span data-ttu-id="ea79b-151">Este procedimiento copia el ensamblado compilado y el archivo de encabezado en las carpetas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="ea79b-151">This procedure copies the compiled assembly and the header file to the appropriate folders.</span></span>  
  
#### <a name="to-copy-the-compiled-assembly-and-header-file-to-the-appropriate-folders"></a><span data-ttu-id="ea79b-152">Para copiar el ensamblado compilado y el archivo de encabezado en las carpetas adecuadas</span><span class="sxs-lookup"><span data-stu-id="ea79b-152">To copy the compiled assembly and header file to the appropriate folders</span></span>  
  
1. <span data-ttu-id="ea79b-153">Copie el ensamblado compilado **SetMQSeriesHeaderPropertyComponent.dll** a la carpeta de componentes de canalización de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ea79b-153">Copy the compiled assembly **SetMQSeriesHeaderPropertyComponent.dll** to the BizTalk pipeline components folder.</span></span> <span data-ttu-id="ea79b-154">La ubicación predeterminada para la carpeta de componentes de canalización de BizTalk es [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components.</span><span class="sxs-lookup"><span data-stu-id="ea79b-154">The default location for the BizTalk pipeline components folder is [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components.</span></span>  
  
2. <span data-ttu-id="ea79b-155">Copie el archivo de propiedades MQHeader **SetMQSMQMDHdrProps.xml** a la **C:\temp** directory.</span><span class="sxs-lookup"><span data-stu-id="ea79b-155">Copy the MQHeader properties file **SetMQSMQMDHdrProps.xml** to the **C:\temp** directory.</span></span>  
  
## <a name="modifying-the-project-for-the-biztalk-server-pipeline"></a><span data-ttu-id="ea79b-156">Modificar el proyecto para la canalización de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ea79b-156">Modifying the Project for the BizTalk Server Pipeline</span></span>  
 <span data-ttu-id="ea79b-157">Este procedimiento modifica el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para la canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea79b-157">This procedure modifies the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline.</span></span>  
  
#### <a name="to-modify-the-project-for-the-biztalk-server-pipeline"></a><span data-ttu-id="ea79b-158">Para modificar el proyecto para la canalización de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ea79b-158">To modify the project for the BizTalk Server pipeline</span></span>  
  
1. <span data-ttu-id="ea79b-159">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra la solución haciendo doble clic en el archivo de solución, **Setmqseriesheaderpropertypipeline\setmqseriesheaderpropertypipeline**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-159">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution by double-clicking the solution file, **SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln**.</span></span>  
  
2. <span data-ttu-id="ea79b-160">Cree un archivo de clave de nombre seguro para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ea79b-160">Create a strong name key file for the project.</span></span> <span data-ttu-id="ea79b-161">Para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ea79b-161">To do that, do the following:</span></span>  
  
   1. <span data-ttu-id="ea79b-162">Abra un símbolo del sistema de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea79b-162">Open a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command prompt.</span></span>  
  
   2. <span data-ttu-id="ea79b-163">Cambie los directorios a \<ruta de ejemplos\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent.</span><span class="sxs-lookup"><span data-stu-id="ea79b-163">Change directories to \<SamplesPath\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent.</span></span>  
  
   3. <span data-ttu-id="ea79b-164">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ea79b-164">Type the following:</span></span>  
  
       `sn -k MQSSendPipelineComponent.snk`  
  
   4. <span data-ttu-id="ea79b-165">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ea79b-165">Press ENTER.</span></span> <span data-ttu-id="ea79b-166">Al hacerlo, se creará el archivo de clave.</span><span class="sxs-lookup"><span data-stu-id="ea79b-166">This will create the key file.</span></span>  
  
3. <span data-ttu-id="ea79b-167">En **el Explorador de soluciones**, haga clic en el proyecto y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto (en la ventana central).</span><span class="sxs-lookup"><span data-stu-id="ea79b-167">In **Solution Explorer**, right-click the project and click **Properties** to launch Project Designer for the project (in the center window).</span></span>  
  
   1.  <span data-ttu-id="ea79b-168">En el Diseñador de proyectos, haga clic en **firma** ficha.</span><span class="sxs-lookup"><span data-stu-id="ea79b-168">In the Project Designer, click **Signing** tab.</span></span>  
  
   2.  <span data-ttu-id="ea79b-169">En el panel derecho, seleccione el **firmar el ensamblado** opción...</span><span class="sxs-lookup"><span data-stu-id="ea79b-169">In the right-hand pane, select the **Sign the assembly** option..</span></span>  
  
   3.  <span data-ttu-id="ea79b-170">Haga clic en la lista desplegable para la **elegir un archivo de clave de nombre seguro** opción y haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-170">Click drop-down list for the **Choose a strong name key file** option, and click **Browse**.</span></span>  
  
   4.  <span data-ttu-id="ea79b-171">Vaya a \<ruta de ejemplos\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\MQSSendPipelineComponent.snk, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-171">Browse to \<SamplesPath\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\MQSSendPipelineComponent.snk, click **Open**.</span></span>  
  
4. <span data-ttu-id="ea79b-172">El componente de canalización que creó anteriormente se ha agregado a la **preensamblar** fase de este proyecto de canalización.</span><span class="sxs-lookup"><span data-stu-id="ea79b-172">The pipeline component that you created earlier is already added to the **Pre-Assemble** stage of this pipeline project.</span></span> <span data-ttu-id="ea79b-173">En caso de que no se haya agregado, debería completar los pasos siguientes para agregarlo:</span><span class="sxs-lookup"><span data-stu-id="ea79b-173">If this component was not already added you would need to complete the following steps to add it:</span></span>  
  
   1. <span data-ttu-id="ea79b-174">En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] IDE, haga clic en el **cuadro de herramientas** ficha en el lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="ea79b-174">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] IDE, click the **Toolbox** tab on the left side.</span></span>  
  
   2. <span data-ttu-id="ea79b-175">Haga clic en el **cuadro de herramientas**y haga clic en **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-175">Right-click the **Toolbox**, and click **Choose Items**.</span></span>  
  
   3. <span data-ttu-id="ea79b-176">En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, haga clic en el **componentes de canalización de BizTalk** ficha, seleccione el **componente personalizado para las propiedades de encabezado de MQseries establece**componente, y a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-176">In the **Choose Toolbox Items** dialog box, click the **BizTalk Pipeline Components** tab, select the **Custom Component to Set MQseries header properties**component, and then click **OK**.</span></span>  
  
   4. <span data-ttu-id="ea79b-177">Arrastre el **componente personalizado para las propiedades de encabezado de MQseries establece**componente a la **preensamblar** fase de esta canalización.</span><span class="sxs-lookup"><span data-stu-id="ea79b-177">Drag the **Custom Component to Set MQseries header properties**component to the **Pre-Assemble** stage of this pipeline.</span></span>  
  
## <a name="compiling-and-deploying-the-pipeline-project"></a><span data-ttu-id="ea79b-178">Compilar e implantar el proyecto de canalización</span><span class="sxs-lookup"><span data-stu-id="ea79b-178">Compiling and Deploying the Pipeline Project</span></span>  
 <span data-ttu-id="ea79b-179">Este procedimiento compila e implementa el proyecto de canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea79b-179">This procedure compiles and deploys the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline project.</span></span>  
  
#### <a name="to-compile-and-deploy-the-pipeline-project"></a><span data-ttu-id="ea79b-180">Para compilar e implantar el proyecto de canalización</span><span class="sxs-lookup"><span data-stu-id="ea79b-180">To compile and deploy the pipeline project</span></span>  
  
1.  <span data-ttu-id="ea79b-181">En la ventana Explorador de soluciones, haga clic en la solución y, a continuación, haga clic en **implementar solución**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-181">In the Solution Explorer window, right-click the solution, and then click **Deploy Solution**.</span></span> <span data-ttu-id="ea79b-182">Así se genera la solución y se implementa el ensamblado en la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ea79b-182">This builds the solution and deploys the assembly to the BizTalk Management database.</span></span>  
  
2.  <span data-ttu-id="ea79b-183">Verifique si el ensamblado se ha implementado en la base de datos de administración de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="ea79b-183">Verify the Assembly was deployed to the BizTalk Management database:</span></span>  
  
    1.  <span data-ttu-id="ea79b-184">Abra la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ea79b-184">Open the BizTalk Administration Console.</span></span>  
  
    2.  <span data-ttu-id="ea79b-185">Haga clic para expandir **grupo de BizTalk [\<servername\>:\<base de datos de administración\>]** y, a continuación, haga clic para expandir el **ensamblados** carpeta.</span><span class="sxs-lookup"><span data-stu-id="ea79b-185">Click to expand **BizTalk Group [\<servername\>:\<management database\>]**, and then click to expand the **Assemblies** folder.</span></span>  
  
         <span data-ttu-id="ea79b-186">El ensamblado de canalización implementado debe verse en el **ensamblados** carpeta.</span><span class="sxs-lookup"><span data-stu-id="ea79b-186">The deployed pipeline assembly should be visible under the **Assemblies** folder.</span></span>  
  
## <a name="creating-the-receive-location"></a><span data-ttu-id="ea79b-187">Crear la ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="ea79b-187">Creating the Receive Location</span></span>  
 <span data-ttu-id="ea79b-188">Este procedimiento crea una ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea79b-188">This procedure creates a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location.</span></span>  
  
#### <a name="to-create-the-receive-location"></a><span data-ttu-id="ea79b-189">Para crear la ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="ea79b-189">To create the receive location</span></span>  
  
1.  <span data-ttu-id="ea79b-190">En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-190">In the BizTalk Server Administration Console, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="ea79b-191">En el **propiedades del puerto de recepción unidireccional** cuadro de diálogo el **nombre** cuadro, escriba "MQReply" y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-191">In the **One-way Receive Port Properties** dialog box, in the **Name** box type "MQReply" and click **OK**.</span></span>  
  
3.  <span data-ttu-id="ea79b-192">En el panel izquierdo, haga clic en **ubicaciones de recepción** pestaña y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-192">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="ea79b-193">En el **propiedades de ubicación de recepción** cuadro de diálogo el **nombre** , escriba "ReceiveFile".</span><span class="sxs-lookup"><span data-stu-id="ea79b-193">In the **Receive Location Properties** dialog box, in the **Name** field, type "ReceiveFile".</span></span>  
  
5.  <span data-ttu-id="ea79b-194">En el **tipo de transporte** cuadro, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-194">In the **Transport Type** box, select **FILE**.</span></span>  
  
6.  <span data-ttu-id="ea79b-195">En el **controlador de recepción** campos, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-195">In the **Receive Handler** field, select **BizTalkServerApplication**.</span></span>  
  
7.  <span data-ttu-id="ea79b-196">En el **canalización de recepción** campos, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-196">In the **Receive pipeline** field, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
8.  <span data-ttu-id="ea79b-197">En el **carpeta recepción** , escriba "C:\temp\Pickup3".</span><span class="sxs-lookup"><span data-stu-id="ea79b-197">In the **Receive folder** field, type "C:\temp\Pickup3".</span></span>  
  
9. <span data-ttu-id="ea79b-198">En el **máscara de archivo** , escriba "\*.\*".</span><span class="sxs-lookup"><span data-stu-id="ea79b-198">In the **File mask** field, type "\*.\*".</span></span>  
  
10. <span data-ttu-id="ea79b-199">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo para salir del **propiedades de ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ea79b-199">Click **OK**, and then click **OK** again to exit the **Receive Location Properties** dialog box.</span></span>  
  
## <a name="creating-a-mqseries-queue-through-the-mqseries-explorer"></a><span data-ttu-id="ea79b-200">Crear una cola de MQSeries mediante el explorador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="ea79b-200">Creating a MQSeries Queue Through the MQSeries Explorer</span></span>  
 <span data-ttu-id="ea79b-201">Si dispone de los permisos necesarios para la instalación de MQSeries Server para Windows, puede crear la cola de MQSeries mediante los cuadros de diálogo del adaptador y puede omitir el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="ea79b-201">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip this next procedure.</span></span>  
  
 <span data-ttu-id="ea79b-202">Si no dispone de este acceso, puede usar el procedimiento siguiente para crear la cola mediante IBM WebSphere MQ Explorer.</span><span class="sxs-lookup"><span data-stu-id="ea79b-202">If you do not have such access, you can use the following procedure to create the queue using the IBM WebSphere MQ Explorer.</span></span>  
  
#### <a name="to-create-a-mqseries-queue-through-the-mqseries-explorer"></a><span data-ttu-id="ea79b-203">Para crear una cola de MQSeries mediante el explorador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="ea79b-203">To create a MQSeries queue through the MQSeries Explorer</span></span>  
  
1.  <span data-ttu-id="ea79b-204">Haga clic en **iniciar**, apunte a **programas**, apunte a **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-204">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="ea79b-205">Haga doble clic en **administradores de cola**y, a continuación, haga doble clic en el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ea79b-205">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="ea79b-206">El Administrador de cola predeterminado se denomina normalmente **QM_**\<*nombre_equipo* \> donde *nombre_equipo* es el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="ea79b-206">The default queue manager is typically named **QM_**\<*machine_name*\> where *machine_name* is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="ea79b-207">Haga clic en **colas**, apunte a **New**y, a continuación, haga clic en **cola Local**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-207">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="ea79b-208">En **Create Local Queue** cuadro de diálogo **nombre de la cola**, tipo **SETHEADER**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-208">In **Create Local Queue** dialog box, in **Queue Name**, type **SETHEADER**, and then click **OK**.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="ea79b-209">Crear el puerto de envío y la cola MQSeries</span><span class="sxs-lookup"><span data-stu-id="ea79b-209">Creating the Send Port and MQSeries Queue</span></span>  
 <span data-ttu-id="ea79b-210">Este procedimiento crea el puerto de envío para el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="ea79b-210">This procedure creates the send port for the output message.</span></span> <span data-ttu-id="ea79b-211">También se crea la cola de MQSeries al crear el puerto de envío si no lo ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ea79b-211">The MQSeries queue is also created when you create the send port if you have not already created it.</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="ea79b-212">Para crear el puerto de envío y la cola MQSeries</span><span class="sxs-lookup"><span data-stu-id="ea79b-212">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="ea79b-213">Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-213">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="ea79b-214">En el **propiedades de puerto de envío** cuadro de diálogo el **nombre** , escriba "MQSolicitResponse".</span><span class="sxs-lookup"><span data-stu-id="ea79b-214">In the **Send Port Properties** dialog box, in the **Name** box, type "MQSolicitResponse".</span></span>  
  
3.  <span data-ttu-id="ea79b-215">En el **tipo de transporte** cuadro, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-215">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="ea79b-216">En el **canalización de envío** cuadro, seleccione **SetMQSeriesHeaderPropertyPipeline.SetMQSeriesHeadersSendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-216">In the **Send pipeline** box, select **SetMQSeriesHeaderPropertyPipeline.SetMQSeriesHeadersSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="ea79b-217">En **filtros**, agregue una nueva entrada con los siguientes pares de nombre/valor:</span><span class="sxs-lookup"><span data-stu-id="ea79b-217">In **Filters**, add a new entry with the following name/value pairs:</span></span>  
  
    -   <span data-ttu-id="ea79b-218">Establecer **propiedad** a "BTS. ReceivePortName".</span><span class="sxs-lookup"><span data-stu-id="ea79b-218">Set **Property** to "BTS.ReceivePortName".</span></span>  
  
    -   <span data-ttu-id="ea79b-219">Establecer **operador** como "==".</span><span class="sxs-lookup"><span data-stu-id="ea79b-219">Set **Operator** to "==".</span></span>  
  
    -   <span data-ttu-id="ea79b-220">Establecer **valor** como "ReceiveFile".</span><span class="sxs-lookup"><span data-stu-id="ea79b-220">Set **Value** to "ReceiveFile".</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ea79b-221">De este modo, se establece el puerto de envío para suscribirse a mensajes que se reciban en el puerto de recepción ReceiveFile.</span><span class="sxs-lookup"><span data-stu-id="ea79b-221">This sets the send port to subscribe to messages that arrive on the ReceiveFile receive port.</span></span>  
  
6.  <span data-ttu-id="ea79b-222">Haga clic en **transporte**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-222">Click **Transport**.</span></span>  
  
7.  <span data-ttu-id="ea79b-223">En el **dirección (URI)** , a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="ea79b-223">In the **Address (URI)** field, click the ellipsis (…) button.</span></span>  
  
8.  <span data-ttu-id="ea79b-224">En el **propiedades de transporte MQSeries** cuadro de diálogo el **definición de la cola** , a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="ea79b-224">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** field, click the ellipsis (…) button.</span></span>  
  
9. <span data-ttu-id="ea79b-225">En el **definición de la cola** cuadro de diálogo el **nombre del servidor** , escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="ea79b-225">In the **Queue Definition** dialog box, in the **Server Name** field, type your computer name.</span></span>  
  
10. <span data-ttu-id="ea79b-226">En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ea79b-226">In the **Queue Manager** field, select the default queue manager.</span></span>  
  
11. <span data-ttu-id="ea79b-227">En el campo de la cola, escriba "SETHEADER" y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-227">In the Queue field, type "SETHEADER", and then click **Export**.</span></span>  
  
12. <span data-ttu-id="ea79b-228">En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** o **realiza** hasta que haya salido todas del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ea79b-228">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog.</span></span>  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a><span data-ttu-id="ea79b-229">Habilitar la ubicación de recepción e iniciar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="ea79b-229">Enabling the Receive Location and Starting the Send Port</span></span>  
 <span data-ttu-id="ea79b-230">Este procedimiento habilita la ubicación de recepción e inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ea79b-230">This procedure enables the receive location and start the send port.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="ea79b-231">Para habilitar la ubicación de recepción e iniciar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="ea79b-231">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="ea79b-232">En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-232">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="ea79b-233">En el panel de detalles, haga clic en el **MQIn** ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-233">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="ea79b-234">En el panel de detalles, haga clic en el **SetMQHeader** puerto de envío y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-234">In the details pane, right-click the **SetMQHeader** send port and click **Start**.</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="ea79b-235">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="ea79b-235">Testing the Application</span></span>  
 <span data-ttu-id="ea79b-236">Este procedimiento comprueba la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ea79b-236">This procedure tests the application.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="ea79b-237">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="ea79b-237">To test the application</span></span>  
  
1.  <span data-ttu-id="ea79b-238">Coloque un archivo en el **C:\Temp\Pickup3** carpeta.</span><span class="sxs-lookup"><span data-stu-id="ea79b-238">Put a file into the **C:\Temp\Pickup3** folder.</span></span>  
  
2.  <span data-ttu-id="ea79b-239">Inicie WebSphere MQ Explorer y haga doble clic en la cola SETHEADER para examinar los mensajes de dicha cola.</span><span class="sxs-lookup"><span data-stu-id="ea79b-239">Launch the WebSphere MQ Explorer and double-click the SETHEADER queue to examine the message(s) in the SETHEADER queue.</span></span>  
  
     <span data-ttu-id="ea79b-240">Para ver todas las propiedades de contexto correspondientes a los mensajes de la cola SETHEADER, debe llevar a cabo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ea79b-240">To see all of the context properties for the messages in the SETHEADER queue, complete the following steps:</span></span>  
  
    1.  <span data-ttu-id="ea79b-241">Haga doble clic en el **SETHEADER** cola para mostrar el **Message Browser** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ea79b-241">Double-click the **SETHEADER** queue to display the **Message Browser** dialog box.</span></span>  
  
    2.  <span data-ttu-id="ea79b-242">En el **Message Browser** cuadro de diálogo, haga clic en **columnas** para mostrar el **Show/Hide Columns for Messages** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ea79b-242">In the **Message Browser** dialog box, click **Columns** to display the **Show/Hide Columns for Messages** dialog box.</span></span>  
  
    3.  <span data-ttu-id="ea79b-243">En **columnas disponibles**, haga doble clic en cada entrada para que sea visible en el **Message Browser** cuadro de diálogo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ea79b-243">Under **Available Columns**, double-click each entry to make it visible in the **Message Browser** dialog box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ea79b-244">Las propiedades de contexto de mensaje para cada mensaje deben estar visibles en el **Message Browser** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ea79b-244">The message context properties for each message should be visible in the **Message Browser** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea79b-245">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea79b-245">See Also</span></span>  
 [<span data-ttu-id="ea79b-246">Ejemplos del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="ea79b-246">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)