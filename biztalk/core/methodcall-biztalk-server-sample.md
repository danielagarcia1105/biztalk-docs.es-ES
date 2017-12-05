---
title: MethodCall (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, calling
- examples, orchestrations
- orchestrations, methods
ms.assetid: 6bdc72da-9478-403a-b706-3089b7374ac7
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16b97b7c81b36774bcf2eaff53a1a4ff91b6f9e8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="methodcall-biztalk-server-sample"></a><span data-ttu-id="56c80-102">MethodCall (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="56c80-102">MethodCall (BizTalk Server Sample)</span></span>
<span data-ttu-id="56c80-103">El ejemplo de MethodCall muestra cómo llamar a un método basado en .NET desde una orquestación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="56c80-103">The MethodCall sample demonstrates how to call a .NET-based method from a BizTalk Server orchestration.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="56c80-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="56c80-104">What This Sample Does</span></span>  
 <span data-ttu-id="56c80-105">Este ejemplo interactúa con un método basado en .NET que utiliza la siguiente secuencia de pasos:</span><span class="sxs-lookup"><span data-stu-id="56c80-105">This sample interacts with a .NET-based method using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="56c80-106">La orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recupera un archivo de entrada XML de la carpeta In.</span><span class="sxs-lookup"><span data-stu-id="56c80-106">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration retrieves an XML input file from the In folder.</span></span> <span data-ttu-id="56c80-107">Este archivo contiene información acerca de las sumas y restas que desea que realice la biblioteca matemática.</span><span class="sxs-lookup"><span data-stu-id="56c80-107">This file contains information about an addition or subtraction you want the math library to perform.</span></span>  
  
2.  <span data-ttu-id="56c80-108">La orquestación llama a la biblioteca matemática incluida para realizar la suma o la resta especificada en el archivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="56c80-108">The orchestration calls the included math library to perform the addition or subtraction specified in the XML input file.</span></span>  
  
3.  <span data-ttu-id="56c80-109">El caso método de la biblioteca matemática, ya sea **agregar** o **restar**, realiza el cálculo solicitado y guarda el resultado como un documento XML.</span><span class="sxs-lookup"><span data-stu-id="56c80-109">The appropriate math library method, either **Add** or **Subtract**, performs the requested calculation and packages the result as an XML document.</span></span>  
  
4.  <span data-ttu-id="56c80-110">La orquestación coloca el archivo resultante .xml en la carpeta Out.</span><span class="sxs-lookup"><span data-stu-id="56c80-110">The orchestration places the resulting .xml file in the Out folder.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="56c80-111">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="56c80-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="56c80-112">El siguiente ejemplo muestra las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="56c80-112">This sample demonstrates the following functionalities:</span></span>  
  
-   <span data-ttu-id="56c80-113">Aprovechar las propiedades promocionadas en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="56c80-113">Leveraging the promoted properties in an orchestration.</span></span> <span data-ttu-id="56c80-114">Los tres elementos en InputSchema.xsd se promueven como campos distintivos.</span><span class="sxs-lookup"><span data-stu-id="56c80-114">The three elements in InputSchema.xsd are promoted as distinguished fields.</span></span> <span data-ttu-id="56c80-115">Cuando la orquestación recibe el mensaje de entrada, obtiene los valores de estos tres campos y los asigna a las variables correspondientes declaradas en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="56c80-115">When the orchestration receives the input message, it gets the values of these three fields and assigns them to the corresponding variables declared in the orchestration.</span></span>  
  
-   <span data-ttu-id="56c80-116">Mediante el **decidir** forma para expresar la lógica "if-then-else" en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="56c80-116">Using the **Decide** shape to express "if-then-else" logic in an orchestration.</span></span> <span data-ttu-id="56c80-117">Después de la orquestación asigna los valores de los campos distintivos a variables internas, entra en el **decidir** forma para comprobar si se debe realizar una suma o resta.</span><span class="sxs-lookup"><span data-stu-id="56c80-117">After the orchestration assigns the values of distinguished fields to internal variables, it enters the **Decide** shape to check whether an addition or subtraction should be performed.</span></span> <span data-ttu-id="56c80-118">Si no se debe realizar ninguna operación, se interrumpe la orquestación.</span><span class="sxs-lookup"><span data-stu-id="56c80-118">If no operation needs to be performed, the orchestration terminates.</span></span>  
  
-   <span data-ttu-id="56c80-119">Llamar a un ensamblado externo desde una orquestación.</span><span class="sxs-lookup"><span data-stu-id="56c80-119">Calling an external assembly from an orchestration.</span></span> <span data-ttu-id="56c80-120">Si se va a realizar una suma, la orquestación llama a un ensamblado externo de C# y pasa en dos parámetros para realizar la suma.</span><span class="sxs-lookup"><span data-stu-id="56c80-120">If an addition is to be performed, the orchestration calls an external C# assembly and passes in two parameters to perform the addition.</span></span> <span data-ttu-id="56c80-121">Los mismos procedimientos se aplican a una resta.</span><span class="sxs-lookup"><span data-stu-id="56c80-121">The same procedures apply to a subtraction.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56c80-122">Debe instalar el ensamblado a la caché de ensamblados global antes de poder llamar al ensamblado desde la orquestación. De lo contrario, recibirá un error XLANG durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="56c80-122">You need to install the assembly to the global assembly cache before you can call it from the orchestration; otherwise you will receive an XLANG error during run time.</span></span>  
  
-   <span data-ttu-id="56c80-123">Mediante el **asignación de mensajes** forma para construir el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="56c80-123">Using the **Message Assignment** shape to construct the output message.</span></span>  
  
-   <span data-ttu-id="56c80-124">Coloque el siguiente código en la forma Expresión para depurar la orquestación:</span><span class="sxs-lookup"><span data-stu-id="56c80-124">Debugging the orchestration by putting the following code in the Expression shape:</span></span>  
  
    ```  
    System.Diagnostics.Debug.WriteLine(iResult);  
    ```  
  
     <span data-ttu-id="56c80-125">También puede escribir el resultado en el registro de eventos utilizando:</span><span class="sxs-lookup"><span data-stu-id="56c80-125">You can also write the result to the event log by using:</span></span>  
  
    ```  
    System.Diagnostics.EventLog.WriteEntry("MethodCall SDK Sample Debug", System.String.Format("Result = {0}", iResult);  
    ```  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="56c80-126">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="56c80-126">Where to Find This Sample</span></span>  
 <span data-ttu-id="56c80-127">\<*Ejemplos de ruta de acceso*\>\Orchestrations\MethodCall\\</span><span class="sxs-lookup"><span data-stu-id="56c80-127">\<*Samples Path*\>\Orchestrations\MethodCall\\</span></span>  
  
 <span data-ttu-id="56c80-128">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="56c80-128">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="56c80-129">Archivos</span><span class="sxs-lookup"><span data-stu-id="56c80-129">File(s)</span></span>|<span data-ttu-id="56c80-130">Description</span><span class="sxs-lookup"><span data-stu-id="56c80-130">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56c80-131">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="56c80-131">Cleanup.bat</span></span>|<span data-ttu-id="56c80-132">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="56c80-132">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="56c80-133">Quita los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="56c80-133">Removes send and receive ports.</span></span> <span data-ttu-id="56c80-134">Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="56c80-134">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="56c80-135">Input.xml</span><span class="sxs-lookup"><span data-stu-id="56c80-135">Input.xml</span></span>|<span data-ttu-id="56c80-136">Archivo de entrada de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="56c80-136">Sample input file.</span></span>|  
|<span data-ttu-id="56c80-137">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="56c80-137">Setup.bat</span></span>|<span data-ttu-id="56c80-138">Se utiliza para crear e iniciar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="56c80-138">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="56c80-139">En la carpeta \MathLibrary:</span><span class="sxs-lookup"><span data-stu-id="56c80-139">In the \MathLibrary folder:</span></span><br /><br /> <span data-ttu-id="56c80-140">AssemblyInfo.cs, MathHelper.cs, MathLibrary.csproj</span><span class="sxs-lookup"><span data-stu-id="56c80-140">AssemblyInfo.cs, MathHelper.cs, MathLibrary.csproj</span></span>|<span data-ttu-id="56c80-141">Archivos de proyecto y de origen para la biblioteca matemática utilizada en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="56c80-141">Project and source files for the math library used by this sample.</span></span>|  
|<span data-ttu-id="56c80-142">En la carpeta \MethodCallSample:</span><span class="sxs-lookup"><span data-stu-id="56c80-142">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="56c80-143">InputSchema.xsd, OutputSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="56c80-143">InputSchema.xsd, OutputSchema.xsd</span></span>|<span data-ttu-id="56c80-144">Esquemas para los archivos de entrada y de salida .xml respectivamente.</span><span class="sxs-lookup"><span data-stu-id="56c80-144">Schemas for the input and output .xml files, respectively.</span></span>|  
|<span data-ttu-id="56c80-145">En la carpeta \MethodCallSample:</span><span class="sxs-lookup"><span data-stu-id="56c80-145">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="56c80-146">MethodCallSample.btproj, MethodCallSample.sln</span><span class="sxs-lookup"><span data-stu-id="56c80-146">MethodCallSample.btproj, MethodCallSample.sln</span></span>|<span data-ttu-id="56c80-147">Archivos de proyectos y de soluciones de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="56c80-147">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="56c80-148">En la carpeta \MethodCallSample:</span><span class="sxs-lookup"><span data-stu-id="56c80-148">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="56c80-149">MethodCallSampleBinding.xml</span><span class="sxs-lookup"><span data-stu-id="56c80-149">MethodCallSampleBinding.xml</span></span>|<span data-ttu-id="56c80-150">Se utiliza para la instalación automatizada, como el enlace de puerto.</span><span class="sxs-lookup"><span data-stu-id="56c80-150">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="56c80-151">En la carpeta \MethodCallSample:</span><span class="sxs-lookup"><span data-stu-id="56c80-151">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="56c80-152">MethodCallService.odx</span><span class="sxs-lookup"><span data-stu-id="56c80-152">MethodCallService.odx</span></span>|<span data-ttu-id="56c80-153">Orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que llama a la biblioteca matemática para realizar el cálculo solicitado.</span><span class="sxs-lookup"><span data-stu-id="56c80-153">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that calls the math library to perform the requested calculation.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="56c80-154">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="56c80-154">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-methodcall-sample"></a><span data-ttu-id="56c80-155">Para crear e iniciar el ejemplo MethodCall</span><span class="sxs-lookup"><span data-stu-id="56c80-155">To build and initialize the MethodCall sample</span></span>  
  
1.  <span data-ttu-id="56c80-156">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="56c80-156">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="56c80-157">\<*Ejemplos de ruta de acceso*\>\orchestrations\methodcall\\</span><span class="sxs-lookup"><span data-stu-id="56c80-157">\<*Samples Path*\>\Orchestrations\MethodCall</span></span>  
  
2.  <span data-ttu-id="56c80-158">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="56c80-158">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="56c80-159">Crea las carpetas de entrada (In) y de salida (Out) de este ejemplo en la carpeta MethodCall.</span><span class="sxs-lookup"><span data-stu-id="56c80-159">Creates the input (In) and output (Out) folders for this sample in the MethodCall folder.</span></span>  
  
    -   <span data-ttu-id="56c80-160">Compila los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo e implementa los ensamblados resultantes.</span><span class="sxs-lookup"><span data-stu-id="56c80-160">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, and deploys the resulting assemblies.</span></span>  
  
    -   <span data-ttu-id="56c80-161">Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="56c80-161">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports to the orchestration.</span></span>  
  
    -   <span data-ttu-id="56c80-162">Habilita la ubicación de recepción e inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="56c80-162">Enables the receive location, and starts the send port.</span></span> <span data-ttu-id="56c80-163">Se da de alta e inicia la orquestación.</span><span class="sxs-lookup"><span data-stu-id="56c80-163">Enlists and starts orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56c80-164">Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="56c80-164">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="56c80-165">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="56c80-165">Running This Sample</span></span>  
  
#### <a name="to-run-the-methodcall-sample"></a><span data-ttu-id="56c80-166">Para ejecutar el ejemplo de MethodCall</span><span class="sxs-lookup"><span data-stu-id="56c80-166">To run the MethodCall sample</span></span>  
  
1.  <span data-ttu-id="56c80-167">Pegue una copia del archivo Input.xml en la carpeta In.</span><span class="sxs-lookup"><span data-stu-id="56c80-167">Paste a copy of the file Input.xml into the In folder.</span></span>  
  
2.  <span data-ttu-id="56c80-168">Observe el archivo .xml que se ha creado en la carpeta Out.</span><span class="sxs-lookup"><span data-stu-id="56c80-168">Observe the .xml file created in the Out folder.</span></span> <span data-ttu-id="56c80-169">Este archivo contiene el resultado del cálculo solicitado de suma o resta.</span><span class="sxs-lookup"><span data-stu-id="56c80-169">This file contains the result of the requested addition or subtraction calculation.</span></span> <span data-ttu-id="56c80-170">El formato del nombre de este archivo es \< *MessageID*\>.xml, donde  *\<MessageID\>*  es el GUID generado para identificar de forma única el mensaje .</span><span class="sxs-lookup"><span data-stu-id="56c80-170">The format of the name of this file is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  
  
3.  <span data-ttu-id="56c80-171">Puede modificar el archivo de entrada para solicitar que se realicen cálculos de suma o resta diferentes.</span><span class="sxs-lookup"><span data-stu-id="56c80-171">You can modify the input file to request different addition or subtraction calculations.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="56c80-172">Desinstalar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="56c80-172">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-methodcall-sample"></a><span data-ttu-id="56c80-173">Para desinstalar el ejemplo MethodCall</span><span class="sxs-lookup"><span data-stu-id="56c80-173">To uninstall the MethodCall sample</span></span>  
  
1.  <span data-ttu-id="56c80-174">En un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a \< *ruta de ejemplos*\>\orchestrations\methodcall\\\.</span><span class="sxs-lookup"><span data-stu-id="56c80-174">At a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to \<*Samples Path*\>\Orchestrations\MethodCall\\.</span></span>  
  
2.  <span data-ttu-id="56c80-175">Ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="56c80-175">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56c80-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="56c80-176">See Also</span></span>  
 [<span data-ttu-id="56c80-177">Orquestaciones (carpetas de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="56c80-177">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)