---
title: Ampliar asignador (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Mapper, examples
- XML tools
- BizTalk Mapper, extending
- examples, BizTalk Mapper
- examples, XML tools
ms.assetid: 6010a13f-b715-4766-ad91-5aa9b98589e3
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f24f7f55e752e25ed06ec68c8eca40d2e7509683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="extending-mapper-biztalk-server-sample"></a><span data-ttu-id="e1fec-102">Ampliar asignador (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="e1fec-102">Extending Mapper (BizTalk Server Sample)</span></span>
<span data-ttu-id="e1fec-103">El ejemplo de ampliación de asignador muestra cómo usar y ampliar el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1fec-103">The Extending Mapper sample demonstrates how to use and extend BizTalk Mapper.</span></span> <span data-ttu-id="e1fec-104">El ejemplo incluye varios archivos de asignación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (.btm), cada uno de los cuales muestra distintas características de Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1fec-104">The sample includes several [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] map files (.btm), each of which illustrates different features of BizTalk Mapper.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e1fec-105">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1fec-105">What This Sample Does</span></span>  
 <span data-ttu-id="e1fec-106">El ejemplo de ampliación de asignador usa el enrutamiento por contenidos (CBR) y no utiliza una orquestación.</span><span class="sxs-lookup"><span data-stu-id="e1fec-106">The Extending Mapper sample uses content-based routing (CBR) and does not use an orchestration.</span></span> <span data-ttu-id="e1fec-107">Mediante la especificación de un filtro en el puerto de envío de ejemplo, se conecta directamente al puerto de recepción de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-107">By specifying a filter on the sample send port, it is connected directly to the sample receive port.</span></span> <span data-ttu-id="e1fec-108">Se especifica una asignación en el puerto de envío que se va a aplicar al documento procesado.</span><span class="sxs-lookup"><span data-stu-id="e1fec-108">A map is specified on the send port to be applied to the processed document.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e1fec-109">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1fec-109">Where to Find This Sample</span></span>  
 <span data-ttu-id="e1fec-110">*\<Ejemplos de ruta de acceso >*\XmlTools\ExtendingMapper</span><span class="sxs-lookup"><span data-stu-id="e1fec-110">*\<Samples Path>*\XmlTools\ExtendingMapper</span></span>  
  
 <span data-ttu-id="e1fec-111">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="e1fec-111">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e1fec-112">Archivos</span><span class="sxs-lookup"><span data-stu-id="e1fec-112">File(s)</span></span>|<span data-ttu-id="e1fec-113">Description</span><span class="sxs-lookup"><span data-stu-id="e1fec-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1fec-114">MapperClassLibrary\AssemblyInfo.cs, MapperClassLibrary\MapperClassLibrary.csproj, MapperClassLibrary\MapperHelper.cs, MapperClassLibrary\MapperClassLibrary.sln</span><span class="sxs-lookup"><span data-stu-id="e1fec-114">MapperClassLibrary\AssemblyInfo.cs, MapperClassLibrary\MapperClassLibrary.csproj, MapperClassLibrary\MapperHelper.cs, MapperClassLibrary\MapperClassLibrary.sln</span></span>|<span data-ttu-id="e1fec-115">Archivo de proyecto de Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]® y archivos de origen de Visual C#®.</span><span class="sxs-lookup"><span data-stu-id="e1fec-115">Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]® project file and Visual C#® source files.</span></span>|  
|<span data-ttu-id="e1fec-116">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="e1fec-116">Cleanup.bat</span></span>|<span data-ttu-id="e1fec-117">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="e1fec-117">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span>|  
|<span data-ttu-id="e1fec-118">Destination.xsd</span><span class="sxs-lookup"><span data-stu-id="e1fec-118">Destination.xsd</span></span>|<span data-ttu-id="e1fec-119">Archivo de esquema.</span><span class="sxs-lookup"><span data-stu-id="e1fec-119">Schema file.</span></span>|  
|<span data-ttu-id="e1fec-120">ExtendingMapper.btproj, ExtendingMapper.sln</span><span class="sxs-lookup"><span data-stu-id="e1fec-120">ExtendingMapper.btproj, ExtendingMapper.sln</span></span>|<span data-ttu-id="e1fec-121">Proyecto de BizTalk y archivos de solución para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-121">BizTalk project and solution files for this sample.</span></span>|  
|<span data-ttu-id="e1fec-122">ExtendingMapper.xml</span><span class="sxs-lookup"><span data-stu-id="e1fec-122">ExtendingMapper.xml</span></span>|<span data-ttu-id="e1fec-123">XML de origen.</span><span class="sxs-lookup"><span data-stu-id="e1fec-123">Source XML.</span></span>|  
|<span data-ttu-id="e1fec-124">ExtendingMapperBinding.xml</span><span class="sxs-lookup"><span data-stu-id="e1fec-124">ExtendingMapperBinding.xml</span></span>|<span data-ttu-id="e1fec-125">XML de enlace.</span><span class="sxs-lookup"><span data-stu-id="e1fec-125">Binding XML.</span></span>|  
|<span data-ttu-id="e1fec-126">ExternalAssembly.xml</span><span class="sxs-lookup"><span data-stu-id="e1fec-126">ExternalAssembly.xml</span></span>|<span data-ttu-id="e1fec-127">XML de ensamblado externo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-127">External assembly XML.</span></span>|  
|<span data-ttu-id="e1fec-128">OverridingMapXslt.btm</span><span class="sxs-lookup"><span data-stu-id="e1fec-128">OverridingMapXslt.btm</span></span>|<span data-ttu-id="e1fec-129">Archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="e1fec-129">Map file.</span></span>|  
|<span data-ttu-id="e1fec-130">OverridingMapXslt.xml</span><span class="sxs-lookup"><span data-stu-id="e1fec-130">OverridingMapXslt.xml</span></span>|<span data-ttu-id="e1fec-131">XML de asignación de reemplazos.</span><span class="sxs-lookup"><span data-stu-id="e1fec-131">Overriding Map XML.</span></span>|  
|<span data-ttu-id="e1fec-132">OverridingMapXslt.xslt</span><span class="sxs-lookup"><span data-stu-id="e1fec-132">OverridingMapXslt.xslt</span></span>|<span data-ttu-id="e1fec-133">Hoja de estilo de asignación de invalidación.</span><span class="sxs-lookup"><span data-stu-id="e1fec-133">Overriding Map style sheet.</span></span>|  
|<span data-ttu-id="e1fec-134">Scriptor_CallExternalAssembly.btm</span><span class="sxs-lookup"><span data-stu-id="e1fec-134">Scriptor_CallExternalAssembly.btm</span></span>|<span data-ttu-id="e1fec-135">Archivo de asignación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-135">Sample map file.</span></span>|  
|<span data-ttu-id="e1fec-136">Scriptor_GlobalVariableInInlineScript.btm</span><span class="sxs-lookup"><span data-stu-id="e1fec-136">Scriptor_GlobalVariableInInlineScript.btm</span></span>|<span data-ttu-id="e1fec-137">Archivo de asignación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-137">Sample map file.</span></span>|  
|<span data-ttu-id="e1fec-138">Scriptor_InlineScripts.btm</span><span class="sxs-lookup"><span data-stu-id="e1fec-138">Scriptor_InlineScripts.btm</span></span>|<span data-ttu-id="e1fec-139">Archivo de asignación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-139">Sample map file.</span></span>|  
|<span data-ttu-id="e1fec-140">Scriptor_InlineXslt.btm</span><span class="sxs-lookup"><span data-stu-id="e1fec-140">Scriptor_InlineXslt.btm</span></span>|<span data-ttu-id="e1fec-141">Archivo de asignación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-141">Sample map file.</span></span>|  
|<span data-ttu-id="e1fec-142">Scriptor_InlineXsltCallingExternalAssembly.btm</span><span class="sxs-lookup"><span data-stu-id="e1fec-142">Scriptor_InlineXsltCallingExternalAssembly.btm</span></span>|<span data-ttu-id="e1fec-143">Archivo de asignación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-143">Sample map file.</span></span>|  
|<span data-ttu-id="e1fec-144">Scriptor_XsltCalltemplate.btm</span><span class="sxs-lookup"><span data-stu-id="e1fec-144">Scriptor_XsltCalltemplate.btm</span></span>|<span data-ttu-id="e1fec-145">Archivo de asignación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-145">Sample map file.</span></span>|  
|<span data-ttu-id="e1fec-146">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="e1fec-146">Setup.bat</span></span>|<span data-ttu-id="e1fec-147">Se utiliza para crear e inicializar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-147">Used to build and initialize the sample.</span></span>|  
|<span data-ttu-id="e1fec-148">Source.xsd</span><span class="sxs-lookup"><span data-stu-id="e1fec-148">Source.xsd</span></span>|<span data-ttu-id="e1fec-149">Archivo de esquema.</span><span class="sxs-lookup"><span data-stu-id="e1fec-149">Schema file.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="e1fec-150">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1fec-150">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="e1fec-151">Utilice el siguiente procedimiento para crear e inicializar el ejemplo de ampliación de asignador.</span><span class="sxs-lookup"><span data-stu-id="e1fec-151">Use the following procedure to build and initialize the Extending Mapper sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="e1fec-152">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1fec-152">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="e1fec-153">En una ventana de comandos, cambie el directorio (**cd**) a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="e1fec-153">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="e1fec-154">*\<Ejemplos de ruta de acceso >*\XmlTools\ExtendingMapper</span><span class="sxs-lookup"><span data-stu-id="e1fec-154">*\<Samples Path>*\XmlTools\ExtendingMapper</span></span>  
  
2.  <span data-ttu-id="e1fec-155">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e1fec-155">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="e1fec-156">Crea las carpetas de entrada (\In) y de salida (\Out) para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-156">Creates the input (\In) and output (\Out) folders for this sample.</span></span>  
  
    -   <span data-ttu-id="e1fec-157">Compila e implementa el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-157">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
    -   <span data-ttu-id="e1fec-158">Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="e1fec-158">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
     <span data-ttu-id="e1fec-159">Si desea usar las asignaciones Scriptor_CallExternalAssembly.btm o Scriptor_InlineXsltCallingExternalAssembly.btm, abra ExtendingMapper.sln en Visual Studio y realice las siguientes modificaciones (de lo contrario, vaya al paso 3):</span><span class="sxs-lookup"><span data-stu-id="e1fec-159">If you want to use the Scriptor_CallExternalAssembly.btm or Scriptor_InlineXsltCallingExternalAssembly.btm maps, open ExtendingMapper.sln in Visual Studio and make the following modifications (otherwise go to step 3):</span></span>  
  
    1.  <span data-ttu-id="e1fec-160">En el Explorador de soluciones, abra Scriptor_CallExternalAssembly.btm.</span><span class="sxs-lookup"><span data-stu-id="e1fec-160">In Solution Explorer, open Scriptor_CallExternalAssembly.btm.</span></span>  
  
    2.  <span data-ttu-id="e1fec-161">En la cuadrícula de asignador, seleccione el functoid de secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="e1fec-161">On the mapper grid, select the Scripting functoid.</span></span>  
  
    3.  <span data-ttu-id="e1fec-162">En la cuadrícula de propiedades, seleccione la **Script** propiedad y haga clic en el botón de puntos suspensivos (...) para configurar la secuencia de comandos de functoid.</span><span class="sxs-lookup"><span data-stu-id="e1fec-162">In the property grid, select the **Script** property, and click the ellipsis (...) button to configure the functoid script.</span></span>  
  
    4.  <span data-ttu-id="e1fec-163">En el **configurar Functoid de secuencias de comandos** cuadro de diálogo, seleccione la **configuración de Functoid de secuencia de comandos**y especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1fec-163">In the **Configure Scripting Functoid** dialog box, select the **Script Functoid Configuration**, and specify the following:</span></span>  
  
        |<span data-ttu-id="e1fec-164">Establezca</span><span class="sxs-lookup"><span data-stu-id="e1fec-164">Set this</span></span>|<span data-ttu-id="e1fec-165">Para esto</span><span class="sxs-lookup"><span data-stu-id="e1fec-165">To this</span></span>|  
        |--------------|-------------|  
        |<span data-ttu-id="e1fec-166">**Tipo de secuencia de comandos**</span><span class="sxs-lookup"><span data-stu-id="e1fec-166">**Script Type**</span></span>|<span data-ttu-id="e1fec-167">Ensamblado externo</span><span class="sxs-lookup"><span data-stu-id="e1fec-167">External assembly</span></span>|  
        |<span data-ttu-id="e1fec-168">**Ensamblado de script**</span><span class="sxs-lookup"><span data-stu-id="e1fec-168">**Script Assembly**</span></span>|<span data-ttu-id="e1fec-169">Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary</span><span class="sxs-lookup"><span data-stu-id="e1fec-169">Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary</span></span>|  
        |<span data-ttu-id="e1fec-170">**Clase de secuencia de comandos**</span><span class="sxs-lookup"><span data-stu-id="e1fec-170">**Script Class**</span></span>|<span data-ttu-id="e1fec-171">Microsoft.Samples.BizTalk.ExtendingMapper.MapperHelper</span><span class="sxs-lookup"><span data-stu-id="e1fec-171">Microsoft.Samples.BizTalk.ExtendingMapper.MapperHelper</span></span>|  
        |<span data-ttu-id="e1fec-172">**Método de script**</span><span class="sxs-lookup"><span data-stu-id="e1fec-172">**Script Method**</span></span>|<span data-ttu-id="e1fec-173">MyConcat</span><span class="sxs-lookup"><span data-stu-id="e1fec-173">MyConcat</span></span>|  
  
    5.  <span data-ttu-id="e1fec-174">Desde el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] **archivo** menú, elija **guardar** para guardar los cambios en el archivo de asignación y cierre la solución.</span><span class="sxs-lookup"><span data-stu-id="e1fec-174">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**File** menu, choose **Save** to save changes to the map file, and close the solution.</span></span>  
  
3.  <span data-ttu-id="e1fec-175">Presione cualquier tecla para continuar con Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="e1fec-175">Press any key to continue with Setup.bat.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e1fec-176">Si desea usar Scriptor_InlineXsltCallingExternalAssembly.btm, debe editar el archivo ExternalAssembly.xml.</span><span class="sxs-lookup"><span data-stu-id="e1fec-176">If you want to use Scriptor_InlineXsltCallingExternalAssembly.btm, you must edit the ExternalAssembly.xml file.</span></span> <span data-ttu-id="e1fec-177">BizTalk usa ExternalAssembly.xml para asignar un espacio de nombres registrado de objeto de extensión de asignador a un ensamblado .NET.</span><span class="sxs-lookup"><span data-stu-id="e1fec-177">ExternalAssembly.xml is used by BizTalk to map a mapper extension object registered namespace to a .NET assembly.</span></span> <span data-ttu-id="e1fec-178">Puesto que se hace referencia al ensamblado dependiente por su nombre completo (incluido el token de clave pública, que se genera de forma automática), debe actualizar este valor.</span><span class="sxs-lookup"><span data-stu-id="e1fec-178">Because the dependent assembly is referenced by its fully qualified name (including its public key token, which is automatically generated), you must update this value.</span></span> <span data-ttu-id="e1fec-179">Si no desea usar Scriptor_InlineXsltCallingExternalAssembly.btm, no es necesario completar los pasos de la a a la e.</span><span class="sxs-lookup"><span data-stu-id="e1fec-179">If you do not want to use Scriptor_InlineXsltCallingExternalAssembly.btm, you do not need to complete steps a through e.</span></span>  
  
4.  <span data-ttu-id="e1fec-180">En el Explorador de Windows, vaya a \<carpeta Windows > \assembly\\.</span><span class="sxs-lookup"><span data-stu-id="e1fec-180">In Windows Explorer, navigate to \<Windows folder>\assembly\\.</span></span>  
  
    1.  <span data-ttu-id="e1fec-181">Haga clic en **Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e1fec-181">Right-click **Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary** and select **Properties**.</span></span>  
  
    2.  <span data-ttu-id="e1fec-182">Copie el valor del token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="e1fec-182">Copy the public key token value.</span></span>  
  
    3.  <span data-ttu-id="e1fec-183">En un editor de texto, abra  *\<ruta de ejemplos >*\XML Tools\ExtendingMapper\ExternalAssembly.xml.</span><span class="sxs-lookup"><span data-stu-id="e1fec-183">In a text editor, open *\<Samples Path>*\XML Tools\ExtendingMapper\ExternalAssembly.xml.</span></span>  
  
    4.  <span data-ttu-id="e1fec-184">Seleccione el **AssemblyName, Version = 1.0.0.0, referencia cultural = neutral, PublicKeyToken = 68496d20c737d84b "**de atributo y reemplace el  **PublicKeyToken** valor con el token de clave pública valor que copió en el paso c..</span><span class="sxs-lookup"><span data-stu-id="e1fec-184">Select the **AssemblyName="Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary, Version=1.0.0.0, Culture=neutral, PublicKeyToken=68496d20c737d84b"**attribute, and replace the **PublicKeyToken** value with the public key token value you copied in step c.</span></span>  
  
    5.  <span data-ttu-id="e1fec-185">Guarde y cierre ExternalAssembly.xml.</span><span class="sxs-lookup"><span data-stu-id="e1fec-185">Save and close ExternalAssembly.xml.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1fec-186">Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-186">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
#### <a name="to-configure-enlist-and-start-the-send-port"></a><span data-ttu-id="e1fec-187">Para configurar, dé de alta e inicie el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="e1fec-187">To configure, enlist, and start the send port</span></span>  
  
1.  <span data-ttu-id="e1fec-188">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, seleccione **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e1fec-188">Click **Start**, select **All Programs**, select **Microsoft BizTalk Server**, and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e1fec-189">En la consola de administración de BizTalk Server, haga clic para expandir **administración de BizTalk Server**, haga clic para expandir **grupo de BizTalk [\<nombreDeServidor >:\<base de datos de administración >]**y haga clic para expandir **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="e1fec-189">In the BizTalk Server Administration console, click to expand **BizTalk Server Administration**, click to expand **BizTalk Group [\<servername>:\<management database>]**, and click to expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="e1fec-190">Haga clic para expandir **ExtendingMapperApplication**y, a continuación, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="e1fec-190">Click to expand **ExtendingMapperApplication**, and then click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="e1fec-191">En el panel derecho, haga clic en **puertos de envío**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e1fec-191">In the right pane, right-click **Send Ports**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="e1fec-192">En el **ExtendingMapperSP – propiedades de puerto de envío** cuadro de diálogo, haga clic en el **asignaciones de salida** página.</span><span class="sxs-lookup"><span data-stu-id="e1fec-192">In the **ExtendingMapperSP – Send Port Properties** dialog box, click the **Outbound Maps** page.</span></span>  
  
     <span data-ttu-id="e1fec-193">En el **mapa** columna, seleccione la asignación requerida de la lista desplegable y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e1fec-193">In the **Map** column, select the required map from the drop-down list, and then click **OK**.</span></span> <span data-ttu-id="e1fec-194">Las asignaciones se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="e1fec-194">The maps are described in the following table.</span></span>  
  
    |<span data-ttu-id="e1fec-195">Asignar para aplicar propiedad</span><span class="sxs-lookup"><span data-stu-id="e1fec-195">Map to apply Property</span></span>|<span data-ttu-id="e1fec-196">Description</span><span class="sxs-lookup"><span data-stu-id="e1fec-196">Description</span></span>|  
    |---------------------------|-----------------|  
    |<span data-ttu-id="e1fec-197">Microsoft.Samples.BizTalk.ExtendingMapper.</span><span class="sxs-lookup"><span data-stu-id="e1fec-197">Microsoft.Samples.BizTalk.ExtendingMapper.</span></span> <span data-ttu-id="e1fec-198">Scriptor_CallExternalAssembly</span><span class="sxs-lookup"><span data-stu-id="e1fec-198">Scriptor_CallExternalAssembly</span></span>|<span data-ttu-id="e1fec-199">Muestra cómo llamar a una función en un ensamblado .NET externo desde una **secuencias de comandos** functoid en una asignación, en función de los parámetros de entrada para este functoid.</span><span class="sxs-lookup"><span data-stu-id="e1fec-199">Demonstrates how to call into a function in an external .NET assembly from a **Scripting** functoid in a map, based on the input parameters to this functoid.</span></span> <span data-ttu-id="e1fec-200">Esto ayuda a separar de forma clara la lógica de procesamiento del archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="e1fec-200">This helps cleanly separate any processing logic from the map file.</span></span> <span data-ttu-id="e1fec-201">Este archivo de asignación usa el ensamblado MapperClassLibrary.dll que se proporciona con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1fec-201">This map file uses the assembly MapperClassLibrary.dll that ships with this sample.</span></span>|  
    |<span data-ttu-id="e1fec-202">Microsoft.Samples.BizTalk.ExtendingMapper.</span><span class="sxs-lookup"><span data-stu-id="e1fec-202">Microsoft.Samples.BizTalk.ExtendingMapper.</span></span> <span data-ttu-id="e1fec-203">Scriptor_InlineScripts</span><span class="sxs-lookup"><span data-stu-id="e1fec-203">Scriptor_InlineScripts</span></span>|<span data-ttu-id="e1fec-204">Muestra cómo escribir secuencias de comandos simple dentro de **secuencias de comandos** functoids en un archivo de asignación con lenguajes .NET como C#, Visual Basic.NET y JScript.NET.</span><span class="sxs-lookup"><span data-stu-id="e1fec-204">Demonstrates how to write simple inline scripts inside **Scripting** functoids in a map file using .NET languages such as C#, Visual Basic.NET, and JScript.NET.</span></span>|  
    |<span data-ttu-id="e1fec-205">Microsoft.Samples.BizTalk.ExtendingMapper.</span><span class="sxs-lookup"><span data-stu-id="e1fec-205">Microsoft.Samples.BizTalk.ExtendingMapper.</span></span> <span data-ttu-id="e1fec-206">Scriptor_GlobalVariableInInlineScript</span><span class="sxs-lookup"><span data-stu-id="e1fec-206">Scriptor_GlobalVariableInInlineScript</span></span>|<span data-ttu-id="e1fec-207">Muestra cómo utilizar las variables globales en las secuencias de comandos de **secuencias de comandos** functoids.</span><span class="sxs-lookup"><span data-stu-id="e1fec-207">Demonstrates how to use global variables in the inline scripts of **Scripting** functoids.</span></span> <span data-ttu-id="e1fec-208">Las variables globales se usan normalmente para mantener la información de estado en un archivo de asignación en distintos **secuencias de comandos** functoids.</span><span class="sxs-lookup"><span data-stu-id="e1fec-208">Global variables are usually used to maintain state information in a map file across different **Scripting** functoids.</span></span>|  
    |<span data-ttu-id="e1fec-209">Microsoft.Samples.BizTalk.ExtendingMapper.</span><span class="sxs-lookup"><span data-stu-id="e1fec-209">Microsoft.Samples.BizTalk.ExtendingMapper.</span></span> <span data-ttu-id="e1fec-210">Scriptor_InlineXslt</span><span class="sxs-lookup"><span data-stu-id="e1fec-210">Scriptor_InlineXslt</span></span>|<span data-ttu-id="e1fec-211">Muestra cómo construir la estructura del documento de destino con XSLT en línea sin formato dentro de un **secuencias de comandos** functoid en el mapa.</span><span class="sxs-lookup"><span data-stu-id="e1fec-211">Demonstrates how to construct structure in the destination document using raw inline XSLT inside a **Scripting** functoid in the map.</span></span> <span data-ttu-id="e1fec-212">Puede construir algunas partes del documento de destino mediante **secuencias de comandos** functoids con XSLT en línea siempre que no sea posible hacerlo en el asignador de BizTalk con otros functoids.</span><span class="sxs-lookup"><span data-stu-id="e1fec-212">You can construct some parts of the destination document using **Scripting** functoids with inline XSLT whenever it is not possible to do that in BizTalk Mapper using other functoids.</span></span>|  
    |<span data-ttu-id="e1fec-213">Microsoft.Samples.BizTalk.ExtendingMapper.</span><span class="sxs-lookup"><span data-stu-id="e1fec-213">Microsoft.Samples.BizTalk.ExtendingMapper.</span></span> <span data-ttu-id="e1fec-214">Scriptor_XsltCalltemplate</span><span class="sxs-lookup"><span data-stu-id="e1fec-214">Scriptor_XsltCalltemplate</span></span>|<span data-ttu-id="e1fec-215">Muestra cómo crear la estructura del documento de destino mediante una plantilla de llamada XSLT en un **secuencias de comandos** functoid en el mapa.</span><span class="sxs-lookup"><span data-stu-id="e1fec-215">Demonstrates how to create structure in the destination document using an XSLT Call template inside a **Scripting** functoid in the map.</span></span> <span data-ttu-id="e1fec-216">La ventaja de una plantilla de llamada XSLT en XSLT en línea es que la plantilla de llamada puede aceptar parámetros, por lo que puede crear la estructura basándose en parámetros de entrada para el **secuencias de comandos** functoid.</span><span class="sxs-lookup"><span data-stu-id="e1fec-216">The advantage of an XSLT Call template over inline XSLT is that the call template can accept parameters, so you can create the structure based on input parameters to the **Scripting** functoid.</span></span> <span data-ttu-id="e1fec-217">Puede construir algunas partes del documento de destino mediante **secuencias de comandos** functoids con XSLT en línea siempre que no sea posible hacerlo en el asignador de BizTalk con otros functoids.</span><span class="sxs-lookup"><span data-stu-id="e1fec-217">You can construct some parts of the destination document using **Scripting** functoids with inline XSLT whenever it is not possible to do that in BizTalk Mapper using other functoids.</span></span>|  
    |<span data-ttu-id="e1fec-218">Microsoft.Samples.BizTalk.ExtendingMapper.</span><span class="sxs-lookup"><span data-stu-id="e1fec-218">Microsoft.Samples.BizTalk.ExtendingMapper.</span></span> <span data-ttu-id="e1fec-219">Scriptor_InlineXsltCallingExternalAssembly</span><span class="sxs-lookup"><span data-stu-id="e1fec-219">Scriptor_InlineXsltCallingExternalAssembly</span></span>|<span data-ttu-id="e1fec-220">Muestra cómo llamar a un ensamblado .NET externo desde dentro el XSLT en línea de un **secuencias de comandos** functoid en un mapa.</span><span class="sxs-lookup"><span data-stu-id="e1fec-220">Demonstrates how to call into an external .NET assembly from inside The inline XSLT of a **Scripting** functoid in a map.</span></span> <span data-ttu-id="e1fec-221">Explica cómo puede invalidar la **XML de extensión personalizada** propiedad de la cuadrícula del asignador de BizTalk con el archivo de extensión personalizada ExternalAssembly_extxml.xml que contiene los detalles del ensamblado .NET externo para invocar.</span><span class="sxs-lookup"><span data-stu-id="e1fec-221">Explains how you can override the **Custom Extension XML** property of the BizTalk Mapper grid with the custom extension file ExternalAssembly_extxml.xml that contains the details of the external .NET assembly to invoke.</span></span> <span data-ttu-id="e1fec-222">Puede construir algunas partes del documento de destino mediante **secuencias de comandos** functoids con XSLT en línea siempre que no sea posible hacerlo en la interfaz de usuario del asignador mediante otros functoids.</span><span class="sxs-lookup"><span data-stu-id="e1fec-222">You can construct some parts of the destination document using **Scripting** functoids with inline XSLT whenever it is not possible to do that in the Mapper UI using other functoids.</span></span>|  
    |<span data-ttu-id="e1fec-223">Microsoft.Samples.BizTalk.ExtendingMapper.</span><span class="sxs-lookup"><span data-stu-id="e1fec-223">Microsoft.Samples.BizTalk.ExtendingMapper.</span></span> <span data-ttu-id="e1fec-224">OverridingMapXslt</span><span class="sxs-lookup"><span data-stu-id="e1fec-224">OverridingMapXslt</span></span>|<span data-ttu-id="e1fec-225">Muestra cómo invalidar por completo el XSLT compilado del archivo de Asignador de BizTalk con un archivo XSLT personalizado.</span><span class="sxs-lookup"><span data-stu-id="e1fec-225">Demonstrates how to completely override the compiled XSLT of the BizTalk Mapper file with a custom XSLT file.</span></span> <span data-ttu-id="e1fec-226">Puede hacerlo mediante el reemplazo de la **ruta de XSL personalizada**propiedad y, opcionalmente, el **XML de extensión personalizada** propiedad de la cuadrícula del asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1fec-226">You can do this by overriding the **Custom XSL Path**property and optionally the **Custom Extension XML** property of the BizTalk Mapper grid.</span></span> <span data-ttu-id="e1fec-227">El archivo XSLT personalizado proporcionado se incluye en el ensamblado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] compilado del proyecto que desee usar en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e1fec-227">The custom XSLT file that you provide is included in the compiled [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly of the project you want to use at run time.</span></span> <span data-ttu-id="e1fec-228">En este caso, se omite el contenido del archivo de asignación (.btm).</span><span class="sxs-lookup"><span data-stu-id="e1fec-228">In this case, the contents of the map file (.btm) are ignored.</span></span> <span data-ttu-id="e1fec-229">Este archivo de asignación usa OverridingMapXslt.xslt y OverridingMapXslt.xml para el **ruta de XSL personalizada** y **XML de extensión personalizada** propiedades, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e1fec-229">This map file uses OverridingMapXslt.xslt and OverridingMapXslt.xml for the **Custom XSL Path** and **Custom Extension XML** properties, respectively.</span></span><br /><br /> <span data-ttu-id="e1fec-230">Es posible validar un archivo de asignación en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="e1fec-230">You can validate a map file in Solution Explorer.</span></span> <span data-ttu-id="e1fec-231">A continuación, puede usar como un archivo de plantilla que puede modificar y utilizar para la **ruta de XSL personalizada** propiedad de la cuadrícula del asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1fec-231">You can then use it as a template file that you can edit and use for the **Custom XSL Path** property of the BizTalk Mapper grid.</span></span> <span data-ttu-id="e1fec-232">Puede recurrir a esta opción siempre que no sea posible producir este XSLT mediante el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1fec-232">You can resort to this option whenever it is not possible to produce this XSLT using BizTalk Mapper.</span></span>|  
  
## <a name="running-this-sample"></a><span data-ttu-id="e1fec-233">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1fec-233">Running This Sample</span></span>  
 <span data-ttu-id="e1fec-234">Utilice el siguiente procedimiento para ejecutar el ejemplo de ampliación de asignador.</span><span class="sxs-lookup"><span data-stu-id="e1fec-234">Use the following procedure to run the Extending Mapper sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="e1fec-235">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1fec-235">To run this sample</span></span>  
  
1.  <span data-ttu-id="e1fec-236">Copia del archivo de la entrada ExtendingMapper.xml en la carpeta de entrada en  *\<ruta de ejemplos >*\XmlTools\ExtendingMapper\In.</span><span class="sxs-lookup"><span data-stu-id="e1fec-236">Copy the input file ExtendingMapper.xml into the input folder at *\<Samples Path>*\XmlTools\ExtendingMapper\In.</span></span>  
  
2.  <span data-ttu-id="e1fec-237">Observe que el archivo se transforman y enrutan a la  *\<ruta de ejemplos >*carpeta \XmlTools\ExtendingMapper\Out.</span><span class="sxs-lookup"><span data-stu-id="e1fec-237">Notice how the file is transformed and routed to the *\<Samples Path>*\XmlTools\ExtendingMapper\Out folder.</span></span> <span data-ttu-id="e1fec-238">La transformación que se produce se basa en la asignación que ha aplicado.</span><span class="sxs-lookup"><span data-stu-id="e1fec-238">The transformation that occurs is based on the map you applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1fec-239">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1fec-239">See Also</span></span>  
 [<span data-ttu-id="e1fec-240">Herramientas XML (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="e1fec-240">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)