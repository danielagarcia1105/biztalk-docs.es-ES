---
title: "Error en la lista de tareas de compilación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bfd5b9f7b974b00d63831484ecbaa44e2568fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="build-errors-in-the-task-list"></a><span data-ttu-id="4e112-102">Error en la lista de tareas de compilación</span><span class="sxs-lookup"><span data-stu-id="4e112-102">Build Errors in the Task List</span></span>
<span data-ttu-id="4e112-103">Al generar un proyecto o una solución, los resultados aparecen en la ventana Resultados, y los errores y las advertencias, en la lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="4e112-103">When you build your project, or solution, the results will appear in the Output window, while individual errors and warnings will appear in the task list.</span></span>  
  
 <span data-ttu-id="4e112-104">Los errores y las advertencias se muestran en la lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="4e112-104">Errors and warnings appear in the task list.</span></span> <span data-ttu-id="4e112-105">Puede hacer doble clic en el error para que se aplique el foco al objeto que no esté configurado correctamente. </span><span class="sxs-lookup"><span data-stu-id="4e112-105">You can double-click the error, and the focus will be applied to the object that is not correctly configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e112-106">Durante el proceso de generación, el compilador no valida los XPath.</span><span class="sxs-lookup"><span data-stu-id="4e112-106">When you build, the compiler does not validate XPaths.</span></span> <span data-ttu-id="4e112-107">Recuerde usar una sintaxis válida de XPath.</span><span class="sxs-lookup"><span data-stu-id="4e112-107">Take care to use valid XPath syntax.</span></span>  
  
## <a name="insufficient-configuration-action"></a><span data-ttu-id="4e112-108">Acción de configuración incompleta</span><span class="sxs-lookup"><span data-stu-id="4e112-108">Insufficient configuration Action</span></span>  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!CAUTION]
>  <span data-ttu-id="4e112-109">Aunque el Diseñador de orquestaciones proporciona advertencias de configuración incompleta en los casos que puede, la falta de tales advertencias no garantiza la compilación correcta de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="4e112-109">While Orchestration Designer will provide insufficient configuration warnings where it can, there is no guarantee that your orchestration will compile correctly in the absence of such warnings.</span></span>  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a><span data-ttu-id="4e112-110">El compilador pregunta si falta una referencia de ensamblado</span><span class="sxs-lookup"><span data-stu-id="4e112-110">Compiler asks if you are missing an assembly reference</span></span>  
  
### <a name="problem"></a><span data-ttu-id="4e112-111">Problema</span><span class="sxs-lookup"><span data-stu-id="4e112-111">Problem</span></span>  
 <span data-ttu-id="4e112-112">Al compilar la orquestación recibe un mensaje de error que termina con la pregunta "¿falta una referencia de ensamblado?"</span><span class="sxs-lookup"><span data-stu-id="4e112-112">When you compile your orchestration you get an error message that ends with the question "are you missing an assembly reference?"</span></span> <span data-ttu-id="4e112-113">Dos de los mensajes más comunes son:</span><span class="sxs-lookup"><span data-stu-id="4e112-113">Two of the more common messages are:</span></span>  
  
-   <span data-ttu-id="4e112-114">El tipo o el nombre del espacio de nombres 'X' no existe en el espacio de nombres 'Y' (¿falta una referencia de ensamblado?)</span><span class="sxs-lookup"><span data-stu-id="4e112-114">The type or namespace name 'X' does not exist in the namespace 'Y' (are you missing an assembly reference?)</span></span>  
  
-   <span data-ttu-id="4e112-115">El identificador 'X' no existe en 'Y'; (¿falta una referencia de ensamblado?)</span><span class="sxs-lookup"><span data-stu-id="4e112-115">Identifier 'X' does not exist in 'Y'; are you missing an assembly reference?</span></span>  
  
### <a name="cause"></a><span data-ttu-id="4e112-116">Causa</span><span class="sxs-lookup"><span data-stu-id="4e112-116">Cause</span></span>  
 <span data-ttu-id="4e112-117">La causa de este error puede ser cualquiera de las siguientes.</span><span class="sxs-lookup"><span data-stu-id="4e112-117">Any of the following could be the cause of this error.</span></span>  
  
-   <span data-ttu-id="4e112-118">El proyecto no hace referencia a uno o varios ensamblados necesarios.</span><span class="sxs-lookup"><span data-stu-id="4e112-118">Your project does not reference one or more required assemblies.</span></span>  
  
-   <span data-ttu-id="4e112-119">El proyecto tiene una asignación u otro tipo de objeto que tiene el mismo nombre que el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4e112-119">Your project has a map or other object type that has the same name as the project.</span></span>  
  
-   <span data-ttu-id="4e112-120">El proyecto usa esquemas de Proceso de Interfaz de Socio (PIP) basados en el lenguaje de definición de esquemas XML (XSD) y contiene esquemas XSD en una subcarpeta cuyo nombre es System.</span><span class="sxs-lookup"><span data-stu-id="4e112-120">Your project uses XML Schema definition language (XSD)-based Partner Interface Process (PIP) schemas and contains XSD schemas in a subfolder that is named System.</span></span>  
  
-   <span data-ttu-id="4e112-121">El proyecto usa una propiedad global cuyo espacio de nombres es un subconjunto del espacio de nombres actual del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4e112-121">Your project is using a Global Property whose namespace is a subset of the current project's namespace.</span></span> <span data-ttu-id="4e112-122">Un ejemplo de ello es el uso del espacio de nombres "File.ReceivedFileName" de propiedad global en una orquestación contenida en el proyecto "Accounts.FILE".</span><span class="sxs-lookup"><span data-stu-id="4e112-122">For example, using the Global Property namespace "File.ReceivedFileName" in an orchestration contained in the project "Accounts.FILE".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="4e112-123">Solución</span><span class="sxs-lookup"><span data-stu-id="4e112-123">Resolution</span></span>  
 <span data-ttu-id="4e112-124">Según la causa del problema, la solución podría ser cualquiera de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e112-124">Depending upon the cause of the problem, the resolution could be any of the following:</span></span>  
  
-   <span data-ttu-id="4e112-125">Agregar una referencia a los ensamblados que faltan que el proyecto necesita.</span><span class="sxs-lookup"><span data-stu-id="4e112-125">Add a reference to the missing assemblies your project requires.</span></span>  
  
-   <span data-ttu-id="4e112-126">Cambiar el nombre de la asignación o del objeto de otro tipo por otro distinto del nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4e112-126">Change the name of the map or other object to something other than the project name.</span></span> <span data-ttu-id="4e112-127">Normalmente, puede hacerlo usando la página de propiedades del objeto (por ejemplo, la página de propiedades de asignación contiene una propiedad Nombre).</span><span class="sxs-lookup"><span data-stu-id="4e112-127">This can typically be done through the object's property page (for example, the Map property page contains a Name property).</span></span>  
  
-   <span data-ttu-id="4e112-128">Cambiar el espacio de nombres correspondiente a los esquemas en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4e112-128">Change the namespace for the schemas in Visual Studio.</span></span> <span data-ttu-id="4e112-129">Para hacer esto con Visual Studio, haga clic en **mostrar todos los archivos** en el **proyecto** menú y, a continuación, expanda el **System** nodo en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="4e112-129">To do this using Visual Studio, click **Show All Files** on the **Project** menu, and then expand the **System** node in Solution Explorer.</span></span> <span data-ttu-id="4e112-130">Haga clic en cada archivo en la carpeta del sistema y en todas las subcarpetas y, a continuación, cambie la entrada de espacio de nombres en la ventana Propiedades de forma que cualquier aparición de **System** se conviertan en _**System**.</span><span class="sxs-lookup"><span data-stu-id="4e112-130">Click each file in the System folder and in any subfolders, and then change the namespace entry in the Properties window so that any occurrence of **System** becomes _**System**.</span></span> <span data-ttu-id="4e112-131">Por ejemplo, cambiar el **MyProject.System.SubFolder** espacio de nombres **el MyProject._System.Subfolder** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4e112-131">For example, change the **MyProject.System.SubFolder** namespace to **the MyProject._System.Subfolder** namespace.</span></span> <span data-ttu-id="4e112-132">Para obtener más información acerca de este problema, consulte el artículo de KB [916649](http://support.microsoft.com/?kbid=916649).</span><span class="sxs-lookup"><span data-stu-id="4e112-132">For more information about this issue, see KB article [916649](http://support.microsoft.com/?kbid=916649).</span></span>  
  
-   <span data-ttu-id="4e112-133">Quite del proyecto el espacio de nombres de la propiedad global objeto de conflicto.</span><span class="sxs-lookup"><span data-stu-id="4e112-133">Remove the conflicting Global Property namespace from the project.</span></span>  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a><span data-ttu-id="4e112-134">Se recibe el error "no se ha inicializado mensaje en la instrucción de construcción" al generar el proyecto</span><span class="sxs-lookup"><span data-stu-id="4e112-134">You receive a "Message has not been initialized in construct statement" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="4e112-135">Problema</span><span class="sxs-lookup"><span data-stu-id="4e112-135">Problem</span></span>  
 <span data-ttu-id="4e112-136">Al compilar la aplicación de BizTalk, recibe el error "no se ha inicializado mensaje en la instrucción de construcción".</span><span class="sxs-lookup"><span data-stu-id="4e112-136">When you compile your BizTalk application, you get the error "Message has not been initialized in construct statement".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="4e112-137">Causa</span><span class="sxs-lookup"><span data-stu-id="4e112-137">Cause</span></span>  
 <span data-ttu-id="4e112-138">Al construir un mensaje, se especifican todas las variables de éste.</span><span class="sxs-lookup"><span data-stu-id="4e112-138">When you construct a message, you specify all the message variables.</span></span> <span data-ttu-id="4e112-139">A continuación, se realizan asignaciones al mensaje o las partes que lo componen.</span><span class="sxs-lookup"><span data-stu-id="4e112-139">Then you make assignments to the message or its parts.</span></span> <span data-ttu-id="4e112-140">Si parte de una asignación de mensajes específico se incluye en otro **construir mensaje** forma, puede recibir el mensaje de error de inicialización.</span><span class="sxs-lookup"><span data-stu-id="4e112-140">If part of a specific message assignment is included in a separate **Construct Message** shape, you may receive the initialization error message.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="4e112-141">Solución</span><span class="sxs-lookup"><span data-stu-id="4e112-141">Resolution</span></span>  
 <span data-ttu-id="4e112-142">Para resolver este comportamiento, asegúrese de que incluye todas las partes de una asignación de mensaje específica en la misma **construir mensaje** forma.</span><span class="sxs-lookup"><span data-stu-id="4e112-142">To resolve this behavior, make sure that you include all parts of a specific message assignment in the same **Construct Message** shape.</span></span> <span data-ttu-id="4e112-143">Un problema de soporte relacionada, consulte el artículo de KB [870606](http://support.microsoft.com/?kbid=870606).</span><span class="sxs-lookup"><span data-stu-id="4e112-143">For a related support issue, see KB article [870606](http://support.microsoft.com/?kbid=870606).</span></span>  
  
 <span data-ttu-id="4e112-144">También puede resolver este comportamiento creando el mensaje en una **construir** forma antes de utilizar una instancia del mismo en un **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="4e112-144">You can also resolve this behavior by creating your message in a **Construct** shape before using an instance of it in an **Expression** shape.</span></span> <span data-ttu-id="4e112-145">Por ejemplo, el código siguiente producirá un error si se coloca en un **expresión** forma:</span><span class="sxs-lookup"><span data-stu-id="4e112-145">For example, the following code will cause an error if placed in an **Expression** shape:</span></span>  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 <span data-ttu-id="4e112-146">Para solucionar el problema, cree la instancia de XMLDOM en una **construir** forma y, a continuación, realice la asignación en un nivel inferior **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="4e112-146">To fix, create the instance of XMLDOM in a **Construct** shape, and then do the assignment in a downstream **Expression** shape.</span></span>  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a><span data-ttu-id="4e112-147">Se recibe el error "utilización de mensaje no construido" al generar el proyecto</span><span class="sxs-lookup"><span data-stu-id="4e112-147">You receive a "use of unconstructed message" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="4e112-148">Problema</span><span class="sxs-lookup"><span data-stu-id="4e112-148">Problem</span></span>  
 <span data-ttu-id="4e112-149">Cuando se compila el proyecto de BizTalk, recibe el error "el uso de mensaje no construido '\<mensaje >'".</span><span class="sxs-lookup"><span data-stu-id="4e112-149">When you compile your BizTalk project, you receive the error "use of unconstructed message '\<message>'".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="4e112-150">Causa</span><span class="sxs-lookup"><span data-stu-id="4e112-150">Cause</span></span>  
 <span data-ttu-id="4e112-151">Este error se produce cuando se usa un mensaje no construido un **enviar** forma.</span><span class="sxs-lookup"><span data-stu-id="4e112-151">This error occurs when an unconstructed message is used in a **Send** shape.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="4e112-152">Solución</span><span class="sxs-lookup"><span data-stu-id="4e112-152">Resolution</span></span>  
 <span data-ttu-id="4e112-153">Para resolver este problema, agregue un **construir mensaje** forma a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="4e112-153">To resolve this issue, add a **Construct Message** shape to the orchestration.</span></span> <span data-ttu-id="4e112-154">Incluir el **construir mensaje** forma antes de la **enviar** forma a la que está enlazado al servicio Web.</span><span class="sxs-lookup"><span data-stu-id="4e112-154">Include the **Construct Message** shape before the **Send** shape that is bound to the Web service.</span></span>  
  
 <span data-ttu-id="4e112-155">Para obtener más información sobre este error y los servicios Web, consulte el artículo de KB [921043](http://support.microsoft.com/?kbid=921043).</span><span class="sxs-lookup"><span data-stu-id="4e112-155">For more information about this error and Web services, see KB article [921043](http://support.microsoft.com/?kbid=921043).</span></span>  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a><span data-ttu-id="4e112-156">Al establecer un nivel de transacción para un ámbito se produce un error</span><span class="sxs-lookup"><span data-stu-id="4e112-156">Setting a transaction level for a scope results in an error</span></span>  
  
### <a name="problem"></a><span data-ttu-id="4e112-157">Problema</span><span class="sxs-lookup"><span data-stu-id="4e112-157">Problem</span></span>  
 <span data-ttu-id="4e112-158">Después de configurar el tipo de transacción para un ámbito u otra entidad que admite transacciones en una orquestación, se recibe el error "Una orquestación no transaccional no puede contener ninguna otra transacción".</span><span class="sxs-lookup"><span data-stu-id="4e112-158">After configuring the transaction type for a scope or other entity supporting transactions in an orchestration, you receive the error "A Non-transactional Orchestration cannot contain any other Transactions".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="4e112-159">Causa</span><span class="sxs-lookup"><span data-stu-id="4e112-159">Cause</span></span>  
 <span data-ttu-id="4e112-160">Este error se produce cuando se intenta establecer el tipo de transacción de un ámbito (u otra entidad) de una orquestación en "Atómica" o "Larga ejecución" pero el tipo de transacción de la propia orquestación es "Ninguna".</span><span class="sxs-lookup"><span data-stu-id="4e112-160">This error occurs when you try to configure the transaction type of a scope (or other entity) in an orchestration to "Atomic" or "Long-Running" when the orchestration itself has a transaction type of "None".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="4e112-161">Solución</span><span class="sxs-lookup"><span data-stu-id="4e112-161">Resolution</span></span>  
 <span data-ttu-id="4e112-162">Asegurarse de que la configuración de tipos de transacción de la orquestación y de los objetos que la componen sean compatibles.</span><span class="sxs-lookup"><span data-stu-id="4e112-162">Ensure that the transaction type settings of your orchestration and constituent objects are compatible.</span></span>  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a><span data-ttu-id="4e112-163">Al generar el proyecto se produce el error "debe especificar al menos una correlación ya inicializada establecida para una recepción de no activación de un puerto no autocorrelacionado"</span><span class="sxs-lookup"><span data-stu-id="4e112-163">Project build results in the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port"</span></span>  
  
### <a name="problem"></a><span data-ttu-id="4e112-164">Problema</span><span class="sxs-lookup"><span data-stu-id="4e112-164">Problem</span></span>  
 <span data-ttu-id="4e112-165">Al compilar el proyecto de BizTalk, se recibe el error "debe especificar al menos una correlación ya inicializada establecida para una recepción de no activación de un puerto no autocorrelacionado".</span><span class="sxs-lookup"><span data-stu-id="4e112-165">When you compile your BizTalk project, you receive the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="4e112-166">Causa</span><span class="sxs-lookup"><span data-stu-id="4e112-166">Cause</span></span>  
 <span data-ttu-id="4e112-167">Este error puede producirse si la orquestación no tiene activar **recepción** formas (activar = true) o no tiene ningún activar **recepción** formas y no se llama directamente por otra orquestación.</span><span class="sxs-lookup"><span data-stu-id="4e112-167">This error can occur if your orchestration has no activating **Receive** shapes (Activate = true) or has no activating **Receive** shapes and is not called directly by another orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="4e112-168">Solución</span><span class="sxs-lookup"><span data-stu-id="4e112-168">Resolution</span></span>  
 <span data-ttu-id="4e112-169">Si no se llama a la orquestación otra orquestación, debe configurar uno de los **recepción** formas se recepciones de activación.</span><span class="sxs-lookup"><span data-stu-id="4e112-169">If your orchestration is not called by another orchestration, you must configure one of the **Receive** shapes to be an activated receive.</span></span> <span data-ttu-id="4e112-170">Para obtener más información acerca de cómo configurar el **recepción** forma, incluidos los vínculos a correlaciones, vea [cómo configurar la forma recepción](../core/how-to-configure-the-receive-shape.md).</span><span class="sxs-lookup"><span data-stu-id="4e112-170">For more information about configuring the **Receive** shape, including links to correlation, see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a><span data-ttu-id="4e112-171">Recibe el error "Error al generar el ensamblado--hace referencia el ensamblado '\<ensamblado >' no tiene un nombre seguro" al compilar la solución</span><span class="sxs-lookup"><span data-stu-id="4e112-171">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly>' does not have a strong name" when building your solution</span></span>  
  
### <a name="problem"></a><span data-ttu-id="4e112-172">Problema</span><span class="sxs-lookup"><span data-stu-id="4e112-172">Problem</span></span>  
 <span data-ttu-id="4e112-173">Recibe el error "Error al generar el ensamblado--hace referencia el ensamblado '\<ensamblado >' no tiene un nombre seguro" al generar una solución que tiene una orquestación.</span><span class="sxs-lookup"><span data-stu-id="4e112-173">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly>' does not have a strong name" when building your solution that has an orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="4e112-174">Causa</span><span class="sxs-lookup"><span data-stu-id="4e112-174">Cause</span></span>  
 <span data-ttu-id="4e112-175">Este problema se produce cuando se usa un tipo de un ensamblado sin firmar al que se hace referencia en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="4e112-175">This problem occurs when a type from an unsigned referenced assembly is used within an orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="4e112-176">Solución</span><span class="sxs-lookup"><span data-stu-id="4e112-176">Resolution</span></span>  
 <span data-ttu-id="4e112-177">Aplicar un nombre seguro al ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="4e112-177">Apply a strong name to the referenced assembly.</span></span> <span data-ttu-id="4e112-178">Si se trata de un ensamblado personalizado que es posible volver a compilar, use la herramienta de nombre seguro para crear un archivo .snk (de clave) y, a continuación, haga referencia a este archivo de clave en las propiedades de ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4e112-178">If it is a custom assembly that you can recompile, use the strong name tool to create an .snk (key) file and then reference that key file in the assembly properties for the project.</span></span> <span data-ttu-id="4e112-179">Para obtener más información sobre nombres seguros de un ensamblado, vea [cómo configurar un archivo de clave de ensamblado de nombre seguro](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span><span class="sxs-lookup"><span data-stu-id="4e112-179">For more information about strong naming an assembly, see [How to Configure a Strong Name Assembly Key File](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span></span>  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a><span data-ttu-id="4e112-180">El error "No se pudieron agregar los recursos.</span><span class="sxs-lookup"><span data-stu-id="4e112-180">The error "Failed to add resource(s).</span></span> <span data-ttu-id="4e112-181">Error en las solicitudes de cambio de algunos recursos" se produce al implementar una orquestación</span><span class="sxs-lookup"><span data-stu-id="4e112-181">Change requests failed for some resources" occurs when deploying an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="4e112-182">Problema</span><span class="sxs-lookup"><span data-stu-id="4e112-182">Problem</span></span>  
 <span data-ttu-id="4e112-183">Al implementar una orquestación, aparece un error parecido al siguiente y no se puede continuar con la implementación de la orquestación:</span><span class="sxs-lookup"><span data-stu-id="4e112-183">When deploying an orchestration, an error similar to the following is displayed and deployment of the orchestration fails:</span></span>  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a><span data-ttu-id="4e112-184">Causa</span><span class="sxs-lookup"><span data-stu-id="4e112-184">Cause</span></span>  
 <span data-ttu-id="4e112-185">Este error puede producirse si la orquestación contiene cualquier objeto que use palabras clave de C#.</span><span class="sxs-lookup"><span data-stu-id="4e112-185">This error can occur if the orchestration contains any objects that use C# keywords.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="4e112-186">Solución</span><span class="sxs-lookup"><span data-stu-id="4e112-186">Resolution</span></span>  
 <span data-ttu-id="4e112-187">Quitar todas las palabras clave de C# de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="4e112-187">Remove any C# keywords from the orchestration.</span></span> <span data-ttu-id="4e112-188">Para obtener una lista de palabras clave de C#, vea [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346).</span><span class="sxs-lookup"><span data-stu-id="4e112-188">For a list of C# keywords, see [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346).</span></span>  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a><span data-ttu-id="4e112-189">Se recibe un error "Valor de propiedad no válido" al compilar la orquestación</span><span class="sxs-lookup"><span data-stu-id="4e112-189">You receive an "invalid property value" error when compiling your orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="4e112-190">Problema</span><span class="sxs-lookup"><span data-stu-id="4e112-190">Problem</span></span>  
 <span data-ttu-id="4e112-191">Se recibe el cuadro de diálogo de error "Valor de propiedad no válido" al generar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="4e112-191">You receive the error dialog "Invalid property value" when building your orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="4e112-192">Causa</span><span class="sxs-lookup"><span data-stu-id="4e112-192">Cause</span></span>  
 <span data-ttu-id="4e112-193">Uno o varios de los objetos de la solución tiene el mismo nombre que otro objeto.</span><span class="sxs-lookup"><span data-stu-id="4e112-193">One or more of the objects in your solution has the same name as another object.</span></span> <span data-ttu-id="4e112-194">Por ejemplo, un nombre de mensaje es igual que un nombre de puerto.</span><span class="sxs-lookup"><span data-stu-id="4e112-194">For example, a message name is the same as a port name.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="4e112-195">Solución</span><span class="sxs-lookup"><span data-stu-id="4e112-195">Resolution</span></span>  
 <span data-ttu-id="4e112-196">Asegurarse de que todos los objetos de la solución tengan un nombre único.</span><span class="sxs-lookup"><span data-stu-id="4e112-196">Ensure that every object in your solution has a unique name.</span></span> <span data-ttu-id="4e112-197">Puede minimizar el riesgo de que se produzca este error respetando una convención de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="4e112-197">You can minimize the risk of this error by adhering to a naming convention.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e112-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e112-198">See Also</span></span>  
 [<span data-ttu-id="4e112-199">Cómo generar orquestaciones</span><span class="sxs-lookup"><span data-stu-id="4e112-199">How to Build Orchestrations</span></span>](../core/how-to-build-orchestrations.md)