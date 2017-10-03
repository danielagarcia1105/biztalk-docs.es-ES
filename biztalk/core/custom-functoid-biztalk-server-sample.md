---
title: Functoid personalizado (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functoids, customizing
- examples, functoids
- functoids, examples
- XML tools
- examples, XML tools
ms.assetid: 9f1eb260-ff62-46f5-a517-57f4e9172b35
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5117bed6ea1116047052359eadcd11754e9f85d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="custom-functoid-biztalk-server-sample"></a><span data-ttu-id="ef030-102">Functoid personalizado (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="ef030-102">Custom Functoid (BizTalk Server Sample)</span></span>
<span data-ttu-id="ef030-103">El ejemplo de functoid personalizado muestra cómo escribir un functoid personalizado para el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ef030-103">The Custom Functoid sample demonstrates how to write a custom functoid for BizTalk Mapper.</span></span> <span data-ttu-id="ef030-104">Puede agregar el functoid al cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef030-104">You can add the functoid to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span> <span data-ttu-id="ef030-105">El functoid se mostrará en el cuadro de herramientas cuando el asignador de BizTalk esté en el foco.</span><span class="sxs-lookup"><span data-stu-id="ef030-105">The functoid will be displayed in the Toolbox when BizTalk Mapper is in focus.</span></span>  
  
 <span data-ttu-id="ef030-106">Un functoid personalizado debe residir en un ensamblado del asignador de BizTalk para reconocerlo.</span><span class="sxs-lookup"><span data-stu-id="ef030-106">A custom functoid should reside in a BizTalk Mapper assembly to recognize it.</span></span> <span data-ttu-id="ef030-107">Puede escribirse en cualquier lenguaje compatible con .NET, como C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ef030-107">It can be written in any .NET-compliant language, such as C# or Visual Basic.</span></span>  
  
 <span data-ttu-id="ef030-108">Asimismo, un functoid personalizado debe derivarse de la clase `Microsoft.BizTalk.BaseFunctoids` y debe proporcionar implementación para algunos métodos mediante su anulación.</span><span class="sxs-lookup"><span data-stu-id="ef030-108">Also, a custom functoid must derive from the `Microsoft.BizTalk.BaseFunctoids` class, and it must provide implementation for some methods by overriding them.</span></span> <span data-ttu-id="ef030-109">(La clase `BaseFunctoid` se define en el ensamblado Microsoft.BizTalk.BaseFunctoids.dll incluido con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ef030-109">(The `BaseFunctoid` class is defined in the Microsoft.BizTalk.BaseFunctoids.dll assembly included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ef030-110">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef030-110">What This Sample Does</span></span>  
 <span data-ttu-id="ef030-111">El ejemplo de functoid personalizado implementa varios functoids, cada uno se deriva de la clase `BaseFunctoid` y anula varios métodos.</span><span class="sxs-lookup"><span data-stu-id="ef030-111">The Custom Functoid sample implements several functoids, each deriving from the `BaseFunctoid` class and overriding several methods.</span></span>  
  
 <span data-ttu-id="ef030-112">Al implementar un functoid personalizado, puede exponer su código interno.</span><span class="sxs-lookup"><span data-stu-id="ef030-112">When implementing a custom functoid, you can expose its code inline.</span></span> <span data-ttu-id="ef030-113">El código interno es el que lleva a cabo el cálculo del functoid.</span><span class="sxs-lookup"><span data-stu-id="ef030-113">The inline code is what performs the computation for the functoid.</span></span> <span data-ttu-id="ef030-114">El compilador del asignador de BizTalk extrae el código interno y los integra en el XSLT compilado cuando se genera el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ef030-114">The BizTalk Mapper compiler extracts inline code from a functoid and embeds it in the compiled XSLT when you build the project.</span></span>  
  
 <span data-ttu-id="ef030-115">Si el functoid personalizado no expone ningún código interno, el asignador de BizTalk genera un XSLT que llama al ensamblado en el que reside el functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef030-115">If your custom functoid does not expose any inline code, BizTalk Mapper generates XSLT that calls into the assembly where the custom functoid resides.</span></span> <span data-ttu-id="ef030-116">En este caso, debe asegurarse de que el ensamblado del functoid personalizado está disponible en la caché de ensamblados global (GAC) para que el motor de XSLT pueda encontrarla.</span><span class="sxs-lookup"><span data-stu-id="ef030-116">In this case, you must be sure your custom functoid assembly is available in the global assembly cache (GAC) so the XSLT engine can find it.</span></span> <span data-ttu-id="ef030-117">Un functoid personalizado también debe tener un atributo de GUID único.</span><span class="sxs-lookup"><span data-stu-id="ef030-117">A custom functoid must also have a unique GUID attribute.</span></span> <span data-ttu-id="ef030-118">El asignador de BizTalk utiliza el GUID para identificar qué ensamblado cargar.</span><span class="sxs-lookup"><span data-stu-id="ef030-118">BizTalk Mapper uses the GUID to identify which assembly to load.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ef030-119">Si reutiliza el código de ejemplo del functoid personalizado para implementar su propio functoid, debe asegurarse de cambiar el atributo de GUID a uno que sea único.</span><span class="sxs-lookup"><span data-stu-id="ef030-119">If you reuse the Custom Functoid sample code to implement your own functoid(s), you must be sure to change the GUID attribute to one that is unique.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ef030-120">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef030-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="ef030-121">*\<Ejemplos de ruta de acceso >*\XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="ef030-121">*\<Samples Path>*\XmlTools\CustomFunctoid</span></span>  
  
 <span data-ttu-id="ef030-122">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="ef030-122">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="ef030-123">Archivos</span><span class="sxs-lookup"><span data-stu-id="ef030-123">File(s)</span></span>|<span data-ttu-id="ef030-124">Description</span><span class="sxs-lookup"><span data-stu-id="ef030-124">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef030-125">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="ef030-125">AssemblyInfo.cs</span></span>|<span data-ttu-id="ef030-126">Código de origen de C# de información de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ef030-126">Assembly information C# source code.</span></span>|  
|<span data-ttu-id="ef030-127">CBuildArray.bmp</span><span class="sxs-lookup"><span data-stu-id="ef030-127">CBuildArray.bmp</span></span>|<span data-ttu-id="ef030-128">Mapa de bits del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="ef030-128">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="ef030-129">CConcat.bmp</span><span class="sxs-lookup"><span data-stu-id="ef030-129">CConcat.bmp</span></span>|<span data-ttu-id="ef030-130">Mapa de bits del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="ef030-130">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="ef030-131">CExtractArray.bmp</span><span class="sxs-lookup"><span data-stu-id="ef030-131">CExtractArray.bmp</span></span>|<span data-ttu-id="ef030-132">Mapa de bits del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="ef030-132">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="ef030-133">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="ef030-133">Cleanup.bat</span></span>|<span data-ttu-id="ef030-134">Se utiliza para anular la implementación de ensamblados y eliminarlos de la caché de ensamblados global (GAC), así como para eliminar CustomFunctoid.dll.</span><span class="sxs-lookup"><span data-stu-id="ef030-134">Used to undeploy assemblies and remove them from the global assembly cache (GAC) and to delete CustomFunctoid.dll.</span></span>|  
|<span data-ttu-id="ef030-135">CLongestString.bmp</span><span class="sxs-lookup"><span data-stu-id="ef030-135">CLongestString.bmp</span></span>|<span data-ttu-id="ef030-136">Mapa de bits del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="ef030-136">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="ef030-137">CMultiply.bmp</span><span class="sxs-lookup"><span data-stu-id="ef030-137">CMultiply.bmp</span></span>|<span data-ttu-id="ef030-138">Mapa de bits del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="ef030-138">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="ef030-139">CustomFunctoid.cs</span><span class="sxs-lookup"><span data-stu-id="ef030-139">CustomFunctoid.cs</span></span>|<span data-ttu-id="ef030-140">Código de origen de C# del functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef030-140">Custom functoid C# source code.</span></span>|  
|<span data-ttu-id="ef030-141">CustomFunctoid.csproj</span><span class="sxs-lookup"><span data-stu-id="ef030-141">CustomFunctoid.csproj</span></span>|<span data-ttu-id="ef030-142">Proyecto de C# del functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef030-142">Custom functoid C# project.</span></span>|  
|<span data-ttu-id="ef030-143">CustomFunctoid.sln</span><span class="sxs-lookup"><span data-stu-id="ef030-143">CustomFunctoid.sln</span></span>|<span data-ttu-id="ef030-144">Solución de functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef030-144">Custom functoid solution.</span></span>|  
|<span data-ttu-id="ef030-145">CustomFunctoidResources.resx</span><span class="sxs-lookup"><span data-stu-id="ef030-145">CustomFunctoidResources.resx</span></span>|<span data-ttu-id="ef030-146">Recursos del functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef030-146">Custom functoid resources.</span></span>|  
|<span data-ttu-id="ef030-147">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="ef030-147">Setup.bat</span></span>|<span data-ttu-id="ef030-148">Se utiliza para generar, implementar e iniciar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ef030-148">Used to build, deploy, and start the sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="ef030-149">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef030-149">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="ef030-150">Utilice el siguiente procedimiento para crear e inicializar el ejemplo del functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef030-150">Use the following procedure to build and initialize the Custom Functoid sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="ef030-151">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef030-151">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="ef030-152">En una ventana de comandos, cambie el directorio (**cd**) a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="ef030-152">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="ef030-153">\<*Ejemplos de ruta de acceso*> \XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="ef030-153">\<*Samples Path*>\XmlTools\CustomFunctoid</span></span>  
  
2.  <span data-ttu-id="ef030-154">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef030-154">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="ef030-155">Genera el proyecto de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ef030-155">Builds the sample project.</span></span>  
  
    -   <span data-ttu-id="ef030-156">Copia el ensamblado generado en el directorio Herramientas de programador\Extensiones de asignador.</span><span class="sxs-lookup"><span data-stu-id="ef030-156">Copies the generated assembly to the Developer Tools\Mapper Extensions directory.</span></span>  
  
    -   <span data-ttu-id="ef030-157">Agrega el ensamblado generado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="ef030-157">Adds the generated assembly to the GAC.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ef030-158">Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ef030-158">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="ef030-159">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef030-159">Running This Sample</span></span>  
 <span data-ttu-id="ef030-160">Utilice el siguiente procedimiento para ejecutar el ejemplo del functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef030-160">Use the following procedure to run the Custom Functoid sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="ef030-161">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef030-161">To run this sample</span></span>  
  
1.  <span data-ttu-id="ef030-162">Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, haga clic en el **herramientas** menú y seleccione **elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ef030-162">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Tools** menu, and select **Choose Toolbox Items**.</span></span>  
  
2.  <span data-ttu-id="ef030-163">En el **elementos de cuadro de herramientas elija** cuadro de diálogo, seleccione la **Functoids del asignador de BizTalk** ficha.</span><span class="sxs-lookup"><span data-stu-id="ef030-163">In the **Choose Toolbox items** dialog box, select the **BizTalk Mapper Functoids** tab.</span></span>  
  
3.  <span data-ttu-id="ef030-164">Haga clic en **restablecer**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ef030-164">Click **Reset**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef030-165">Si su functoid personalizado no expone ningún código en línea, asegúrese de que su ensamblado está disponible en la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="ef030-165">If your custom functoid does not expose any inline code, make sure its assembly is made available in the GAC.</span></span>  
  
4.  <span data-ttu-id="ef030-166">Desde el **archivo** menú, seleccione **Exit** para cerrar [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef030-166">From the **File** menu, select **Exit** to close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="ef030-167">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="ef030-167">Start **Visual Studio Command Prompt**.</span></span>  
  
6.  <span data-ttu-id="ef030-168">En el símbolo del sistema, escriba **devenv /setup**.</span><span class="sxs-lookup"><span data-stu-id="ef030-168">At the command prompt, type **devenv /setup**.</span></span>  
  
7.  <span data-ttu-id="ef030-169">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="ef030-169">Start **Microsoft Visual Studio**.</span></span>  
  
     <span data-ttu-id="ef030-170">Personalizado functoids (functoid de concatenación personalizada, cadena más larga, functoid de matriz de compilación y extraer el functoid de matriz) aparecen en la **Functoids de cadena** ficha del cuadro de herramientas, mientras que el functoid de multiplicación acumulada aparece en el **Functoids acumulativos** ficha.</span><span class="sxs-lookup"><span data-stu-id="ef030-170">The custom functoids (Custom concatenate functoid, Longest String, Build array functoid, and Extract array functoid) appear on the **String Functoids** tab of the Toolbox, and the Cumulative Multiply functoid appears on the **Cumulative Functoids** tab.</span></span>  
  
## <a name="removing-this-sample"></a><span data-ttu-id="ef030-171">Eliminar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef030-171">Removing This Sample</span></span>  
 <span data-ttu-id="ef030-172">Utilice el siguiente procedimiento para eliminar el ejemplo del functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef030-172">Use the following procedure to remove the Custom Functoid sample.</span></span>  
  
#### <a name="to-remove-this-sample"></a><span data-ttu-id="ef030-173">Para quitar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef030-173">To remove this sample</span></span>  
  
1.  <span data-ttu-id="ef030-174">Quite los functoids del cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef030-174">Remove the functoids from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="ef030-175">Si, después de ejecutar Cleanup.bat, sigue viendo los functoids personalizados obsoletos en el cuadro de herramientas (probablemente debido a la memoria caché interna de Visual Studio), siga los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef030-175">If after running Cleanup.bat, you still see the stale custom functoids in the toolbox (probably due to internal caching by Visual Studio), then follow the procedures below:</span></span>  
  
    1.  <span data-ttu-id="ef030-176">Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, haga clic en el **herramientas** menú y seleccione **elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ef030-176">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Tools** menu, and select **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="ef030-177">En el **elementos de cuadro de herramientas elija** cuadro de diálogo, seleccione la **Functoids del asignador de BizTalk** ficha.</span><span class="sxs-lookup"><span data-stu-id="ef030-177">In the **Choose Toolbox items** dialog box, select the **BizTalk Mapper Functoids** tab.</span></span>  
  
    3.  <span data-ttu-id="ef030-178">Busque en la lista los functoids personalizados (de concatenación personalizada, de cadena más larga, de generación de matriz, de extracción de matriz y de multiplicación acumulada).</span><span class="sxs-lookup"><span data-stu-id="ef030-178">Find the custom functoids (Custom concatenate functoid, Longest String, Build array functoid, Extract array functoid, and Cumulative Multiply) in the list.</span></span> <span data-ttu-id="ef030-179">Haga clic en los respectivos **casilla de verificación** para quitar los functoids y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ef030-179">Click the respective **check box** to remove the functoids, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ef030-180">Si no funciona el procedimiento anterior, siga el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef030-180">If the above procedure does not work, follow the below procedure.</span></span>  
  
    1.  <span data-ttu-id="ef030-181">Desde el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, haga clic en el **cuadro de herramientas** ficha mientras edita una asignación para abrir la paleta de cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="ef030-181">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Toolbox** tab while editing a map to bring up the Toolbox Palette.</span></span>  
  
    2.  <span data-ttu-id="ef030-182">Haga clic en el cuadro de herramientas y seleccione **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="ef030-182">Right-click the tool box and select **Choose Items**.</span></span>  
  
    3.  <span data-ttu-id="ef030-183">En el cuadro de diálogo Elegir elementos, haga clic en **restablecer**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ef030-183">In the Choose Items dialog box, click **Reset**, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="ef030-184">Cierre todas las instancias de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef030-184">Close all instances of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
     <span data-ttu-id="ef030-185">Si no funciona el procedimiento anterior, siga el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef030-185">If the above procedure does not work, follow the below procedure.</span></span>  
  
    1.  <span data-ttu-id="ef030-186">Iniciar **Visual Studio Command Prompt** como administrador.</span><span class="sxs-lookup"><span data-stu-id="ef030-186">Start **Visual Studio Command Prompt** as an administrator.</span></span>  
  
    2.  <span data-ttu-id="ef030-187">Cierre todas las instancias en ejecución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ef030-187">Close all the running instances of Visual Studio.</span></span>  
  
    3.  <span data-ttu-id="ef030-188">Escriba los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef030-188">Give the following commands:</span></span>  
  
         `devenv /resetsettings`  
  
         `devenv /setup`  
  
    4.  <span data-ttu-id="ef030-189">Puede seleccionar manualmente los functoids no deseados en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="ef030-189">You can manually select the unwanted functoids from the toolbox.</span></span> <span data-ttu-id="ef030-190">A continuación, haga clic con el functoid y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ef030-190">Then, right click the functoid, and click **Delete**.</span></span>  
  
     <span data-ttu-id="ef030-191">Si no funciona el procedimiento anterior, siga el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef030-191">If the above procedure does not work, follow the below procedure.</span></span>  
  
    1.  <span data-ttu-id="ef030-192">En un proyecto de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], haga clic en la pestaña Cuadro de herramientas mientras edita una asignación para abrir la paleta de cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="ef030-192">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the Toolbox tab while editing a map to bring up the Toolbox Palette.</span></span>  
  
    2.  <span data-ttu-id="ef030-193">Haga clic en el **Functoids acumulativos** grupo.</span><span class="sxs-lookup"><span data-stu-id="ef030-193">Click the **Cumulative Functoids** group.</span></span>  
  
    3.  <span data-ttu-id="ef030-194">Haga clic con el functoid que desea quitar y, a continuación, elija **eliminar** o presione la tecla SUPR.</span><span class="sxs-lookup"><span data-stu-id="ef030-194">Right click the functoid you want to remove and then choose **Delete** or press the delete key.</span></span>  
  
    4.  <span data-ttu-id="ef030-195">Haga clic en el **Functoids de cadena** grupo.</span><span class="sxs-lookup"><span data-stu-id="ef030-195">Click the **String Functoids** group.</span></span>  
  
    5.  <span data-ttu-id="ef030-196">Haga clic con el functoid que desea quitar y, a continuación, elija **eliminar** o presione la tecla SUPR.</span><span class="sxs-lookup"><span data-stu-id="ef030-196">Right click the functoid you want to remove and then choose **Delete** or press the delete key.</span></span>  
  
2.  <span data-ttu-id="ef030-197">En una ventana de comandos, cambie el directorio (**cd**) a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="ef030-197">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="ef030-198">\<*Ejemplos de ruta de acceso*> \XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="ef030-198">\<*Samples Path*>\XmlTools\CustomFunctoid</span></span>  
  
3.  <span data-ttu-id="ef030-199">Ejecute el archivo Cleanup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef030-199">Run the file Cleanup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="ef030-200">Elimina el ensamblado del directorio Herramientas de programador\Extensiones de asignador.</span><span class="sxs-lookup"><span data-stu-id="ef030-200">Deletes the assembly from the Developer Tools\Mapper Extensions directory.</span></span>  
  
    -   <span data-ttu-id="ef030-201">Elimina el ensamblado de la GAC.</span><span class="sxs-lookup"><span data-stu-id="ef030-201">Removes the assembly from the GAC.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="ef030-202">Clases o métodos usados en el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef030-202">Classes or Methods Used in This Sample</span></span>  
 [<span data-ttu-id="ef030-203">Microsoft.BizTalk.BaseFunctoids.BaseFunctoid</span><span class="sxs-lookup"><span data-stu-id="ef030-203">Microsoft.BizTalk.BaseFunctoids.BaseFunctoid</span></span>](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.basefunctoid.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="ef030-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef030-204">See Also</span></span>  
 <span data-ttu-id="ef030-205">[Utilizar BaseFunctoid](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="ef030-205">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 [<span data-ttu-id="ef030-206">Herramientas XML (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="ef030-206">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)