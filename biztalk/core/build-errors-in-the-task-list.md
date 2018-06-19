---
title: Error en la lista de tareas de compilación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aeef8ac3defc17f4c9bf0fbddedf6d389a1263e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967226"
---
# <a name="build-errors-in-the-task-list"></a><span data-ttu-id="e0908-102">Error en la lista de tareas de compilación</span><span class="sxs-lookup"><span data-stu-id="e0908-102">Build Errors in the Task List</span></span>
<span data-ttu-id="e0908-103">Al generar un proyecto o una solución, los resultados aparecen en la ventana Resultados, y los errores y las advertencias, en la lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="e0908-103">When you build your project, or solution, the results will appear in the Output window, while individual errors and warnings will appear in the task list.</span></span>  
  
 <span data-ttu-id="e0908-104">Los errores y las advertencias se muestran en la lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="e0908-104">Errors and warnings appear in the task list.</span></span> <span data-ttu-id="e0908-105">Puede hacer doble clic en el error para que se aplique el foco al objeto que no esté configurado correctamente. </span><span class="sxs-lookup"><span data-stu-id="e0908-105">You can double-click the error, and the focus will be applied to the object that is not correctly configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0908-106">Durante el proceso de generación, el compilador no valida los XPath.</span><span class="sxs-lookup"><span data-stu-id="e0908-106">When you build, the compiler does not validate XPaths.</span></span> <span data-ttu-id="e0908-107">Recuerde usar una sintaxis válida de XPath.</span><span class="sxs-lookup"><span data-stu-id="e0908-107">Take care to use valid XPath syntax.</span></span>  
  
## <a name="insufficient-configuration-action"></a><span data-ttu-id="e0908-108">Acción de configuración incompleta</span><span class="sxs-lookup"><span data-stu-id="e0908-108">Insufficient configuration Action</span></span>  
 <span data-ttu-id="e0908-109">![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")</span><span class="sxs-lookup"><span data-stu-id="e0908-109">![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e0908-110">Aunque el Diseñador de orquestaciones proporciona advertencias de configuración incompleta en los casos que puede, la falta de tales advertencias no garantiza la compilación correcta de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="e0908-110">While Orchestration Designer will provide insufficient configuration warnings where it can, there is no guarantee that your orchestration will compile correctly in the absence of such warnings.</span></span>  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a><span data-ttu-id="e0908-111">El compilador pregunta si falta una referencia de ensamblado</span><span class="sxs-lookup"><span data-stu-id="e0908-111">Compiler asks if you are missing an assembly reference</span></span>  
  
### <a name="problem"></a><span data-ttu-id="e0908-112">Problema</span><span class="sxs-lookup"><span data-stu-id="e0908-112">Problem</span></span>  
 <span data-ttu-id="e0908-113">Al compilar la orquestación recibe un mensaje de error que termina con la pregunta "¿falta una referencia de ensamblado?"</span><span class="sxs-lookup"><span data-stu-id="e0908-113">When you compile your orchestration you get an error message that ends with the question "are you missing an assembly reference?"</span></span> <span data-ttu-id="e0908-114">Dos de los mensajes más comunes son:</span><span class="sxs-lookup"><span data-stu-id="e0908-114">Two of the more common messages are:</span></span>  
  
-   <span data-ttu-id="e0908-115">El tipo o el nombre del espacio de nombres 'X' no existe en el espacio de nombres 'Y' (¿falta una referencia de ensamblado?)</span><span class="sxs-lookup"><span data-stu-id="e0908-115">The type or namespace name 'X' does not exist in the namespace 'Y' (are you missing an assembly reference?)</span></span>  
  
-   <span data-ttu-id="e0908-116">El identificador 'X' no existe en 'Y'; (¿falta una referencia de ensamblado?)</span><span class="sxs-lookup"><span data-stu-id="e0908-116">Identifier 'X' does not exist in 'Y'; are you missing an assembly reference?</span></span>  
  
### <a name="cause"></a><span data-ttu-id="e0908-117">Causa</span><span class="sxs-lookup"><span data-stu-id="e0908-117">Cause</span></span>  
 <span data-ttu-id="e0908-118">La causa de este error puede ser cualquiera de las siguientes.</span><span class="sxs-lookup"><span data-stu-id="e0908-118">Any of the following could be the cause of this error.</span></span>  
  
-   <span data-ttu-id="e0908-119">El proyecto no hace referencia a uno o varios ensamblados necesarios.</span><span class="sxs-lookup"><span data-stu-id="e0908-119">Your project does not reference one or more required assemblies.</span></span>  
  
-   <span data-ttu-id="e0908-120">El proyecto tiene una asignación u otro tipo de objeto que tiene el mismo nombre que el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0908-120">Your project has a map or other object type that has the same name as the project.</span></span>  
  
-   <span data-ttu-id="e0908-121">El proyecto usa esquemas de Proceso de Interfaz de Socio (PIP) basados en el lenguaje de definición de esquemas XML (XSD) y contiene esquemas XSD en una subcarpeta cuyo nombre es System.</span><span class="sxs-lookup"><span data-stu-id="e0908-121">Your project uses XML Schema definition language (XSD)-based Partner Interface Process (PIP) schemas and contains XSD schemas in a subfolder that is named System.</span></span>  
  
-   <span data-ttu-id="e0908-122">El proyecto usa una propiedad global cuyo espacio de nombres es un subconjunto del espacio de nombres actual del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0908-122">Your project is using a Global Property whose namespace is a subset of the current project's namespace.</span></span> <span data-ttu-id="e0908-123">Un ejemplo de ello es el uso del espacio de nombres "File.ReceivedFileName" de propiedad global en una orquestación contenida en el proyecto "Accounts.FILE".</span><span class="sxs-lookup"><span data-stu-id="e0908-123">For example, using the Global Property namespace "File.ReceivedFileName" in an orchestration contained in the project "Accounts.FILE".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="e0908-124">Solución</span><span class="sxs-lookup"><span data-stu-id="e0908-124">Resolution</span></span>  
 <span data-ttu-id="e0908-125">Según la causa del problema, la solución podría ser cualquiera de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0908-125">Depending upon the cause of the problem, the resolution could be any of the following:</span></span>  
  
-   <span data-ttu-id="e0908-126">Agregar una referencia a los ensamblados que faltan que el proyecto necesita.</span><span class="sxs-lookup"><span data-stu-id="e0908-126">Add a reference to the missing assemblies your project requires.</span></span>  
  
-   <span data-ttu-id="e0908-127">Cambiar el nombre de la asignación o del objeto de otro tipo por otro distinto del nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0908-127">Change the name of the map or other object to something other than the project name.</span></span> <span data-ttu-id="e0908-128">Normalmente, puede hacerlo usando la página de propiedades del objeto (por ejemplo, la página de propiedades de asignación contiene una propiedad Nombre).</span><span class="sxs-lookup"><span data-stu-id="e0908-128">This can typically be done through the object's property page (for example, the Map property page contains a Name property).</span></span>  
  
-   <span data-ttu-id="e0908-129">Cambiar el espacio de nombres correspondiente a los esquemas en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e0908-129">Change the namespace for the schemas in Visual Studio.</span></span> <span data-ttu-id="e0908-130">Para hacer esto con Visual Studio, haga clic en **mostrar todos los archivos** en el **proyecto** menú y, a continuación, expanda el **System** nodo en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="e0908-130">To do this using Visual Studio, click **Show All Files** on the **Project** menu, and then expand the **System** node in Solution Explorer.</span></span> <span data-ttu-id="e0908-131">Haga clic en cada archivo en la carpeta del sistema y en todas las subcarpetas y, a continuación, cambie la entrada de espacio de nombres en la ventana Propiedades de forma que cualquier aparición de **System** se conviertan en _**System**.</span><span class="sxs-lookup"><span data-stu-id="e0908-131">Click each file in the System folder and in any subfolders, and then change the namespace entry in the Properties window so that any occurrence of **System** becomes _**System**.</span></span> <span data-ttu-id="e0908-132">Por ejemplo, cambiar el **MyProject.System.SubFolder** espacio de nombres **el MyProject._System.Subfolder** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e0908-132">For example, change the **MyProject.System.SubFolder** namespace to **the MyProject._System.Subfolder** namespace.</span></span> <span data-ttu-id="e0908-133">Para obtener más información acerca de este problema, consulte el artículo de KB [916649](http://support.microsoft.com/?kbid=916649).</span><span class="sxs-lookup"><span data-stu-id="e0908-133">For more information about this issue, see KB article [916649](http://support.microsoft.com/?kbid=916649).</span></span>  
  
-   <span data-ttu-id="e0908-134">Quite del proyecto el espacio de nombres de la propiedad global objeto de conflicto.</span><span class="sxs-lookup"><span data-stu-id="e0908-134">Remove the conflicting Global Property namespace from the project.</span></span>  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a><span data-ttu-id="e0908-135">Se recibe el error "no se ha inicializado mensaje en la instrucción de construcción" al generar el proyecto</span><span class="sxs-lookup"><span data-stu-id="e0908-135">You receive a "Message has not been initialized in construct statement" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="e0908-136">Problema</span><span class="sxs-lookup"><span data-stu-id="e0908-136">Problem</span></span>  
 <span data-ttu-id="e0908-137">Al compilar la aplicación de BizTalk, recibe el error "no se ha inicializado mensaje en la instrucción de construcción".</span><span class="sxs-lookup"><span data-stu-id="e0908-137">When you compile your BizTalk application, you get the error "Message has not been initialized in construct statement".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="e0908-138">Causa</span><span class="sxs-lookup"><span data-stu-id="e0908-138">Cause</span></span>  
 <span data-ttu-id="e0908-139">Al construir un mensaje, se especifican todas las variables de éste.</span><span class="sxs-lookup"><span data-stu-id="e0908-139">When you construct a message, you specify all the message variables.</span></span> <span data-ttu-id="e0908-140">A continuación, se realizan asignaciones al mensaje o las partes que lo componen.</span><span class="sxs-lookup"><span data-stu-id="e0908-140">Then you make assignments to the message or its parts.</span></span> <span data-ttu-id="e0908-141">Si parte de una asignación de mensajes específico se incluye en otro **construir mensaje** forma, puede recibir el mensaje de error de inicialización.</span><span class="sxs-lookup"><span data-stu-id="e0908-141">If part of a specific message assignment is included in a separate **Construct Message** shape, you may receive the initialization error message.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="e0908-142">Solución</span><span class="sxs-lookup"><span data-stu-id="e0908-142">Resolution</span></span>  
 <span data-ttu-id="e0908-143">Para resolver este comportamiento, asegúrese de que incluye todas las partes de una asignación de mensaje específica en la misma **construir mensaje** forma.</span><span class="sxs-lookup"><span data-stu-id="e0908-143">To resolve this behavior, make sure that you include all parts of a specific message assignment in the same **Construct Message** shape.</span></span> <span data-ttu-id="e0908-144">Un problema de soporte relacionada, consulte el artículo de KB [870606](http://support.microsoft.com/?kbid=870606).</span><span class="sxs-lookup"><span data-stu-id="e0908-144">For a related support issue, see KB article [870606](http://support.microsoft.com/?kbid=870606).</span></span>  
  
 <span data-ttu-id="e0908-145">También puede resolver este comportamiento creando el mensaje en una **construir** forma antes de utilizar una instancia del mismo en un **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="e0908-145">You can also resolve this behavior by creating your message in a **Construct** shape before using an instance of it in an **Expression** shape.</span></span> <span data-ttu-id="e0908-146">Por ejemplo, el código siguiente producirá un error si se coloca en un **expresión** forma:</span><span class="sxs-lookup"><span data-stu-id="e0908-146">For example, the following code will cause an error if placed in an **Expression** shape:</span></span>  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 <span data-ttu-id="e0908-147">Para solucionar el problema, cree la instancia de XMLDOM en una **construir** forma y, a continuación, realice la asignación en un nivel inferior **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="e0908-147">To fix, create the instance of XMLDOM in a **Construct** shape, and then do the assignment in a downstream **Expression** shape.</span></span>  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a><span data-ttu-id="e0908-148">Se recibe el error "utilización de mensaje no construido" al generar el proyecto</span><span class="sxs-lookup"><span data-stu-id="e0908-148">You receive a "use of unconstructed message" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="e0908-149">Problema</span><span class="sxs-lookup"><span data-stu-id="e0908-149">Problem</span></span>  
 <span data-ttu-id="e0908-150">Cuando se compila el proyecto de BizTalk, recibe el error "el uso de mensaje no construido '\<mensaje\>'".</span><span class="sxs-lookup"><span data-stu-id="e0908-150">When you compile your BizTalk project, you receive the error "use of unconstructed message '\<message\>'".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="e0908-151">Causa</span><span class="sxs-lookup"><span data-stu-id="e0908-151">Cause</span></span>  
 <span data-ttu-id="e0908-152">Este error se produce cuando se usa un mensaje no construido un **enviar** forma.</span><span class="sxs-lookup"><span data-stu-id="e0908-152">This error occurs when an unconstructed message is used in a **Send** shape.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="e0908-153">Solución</span><span class="sxs-lookup"><span data-stu-id="e0908-153">Resolution</span></span>  
 <span data-ttu-id="e0908-154">Para resolver este problema, agregue un **construir mensaje** forma a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="e0908-154">To resolve this issue, add a **Construct Message** shape to the orchestration.</span></span> <span data-ttu-id="e0908-155">Incluir el **construir mensaje** forma antes de la **enviar** forma a la que está enlazado al servicio Web.</span><span class="sxs-lookup"><span data-stu-id="e0908-155">Include the **Construct Message** shape before the **Send** shape that is bound to the Web service.</span></span>  
  
 <span data-ttu-id="e0908-156">Para obtener más información sobre este error y los servicios Web, consulte el artículo de KB [921043](http://support.microsoft.com/?kbid=921043).</span><span class="sxs-lookup"><span data-stu-id="e0908-156">For more information about this error and Web services, see KB article [921043](http://support.microsoft.com/?kbid=921043).</span></span>  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a><span data-ttu-id="e0908-157">Al establecer un nivel de transacción para un ámbito se produce un error</span><span class="sxs-lookup"><span data-stu-id="e0908-157">Setting a transaction level for a scope results in an error</span></span>  
  
### <a name="problem"></a><span data-ttu-id="e0908-158">Problema</span><span class="sxs-lookup"><span data-stu-id="e0908-158">Problem</span></span>  
 <span data-ttu-id="e0908-159">Después de configurar el tipo de transacción para un ámbito u otra entidad que admite transacciones en una orquestación, se recibe el error "Una orquestación no transaccional no puede contener ninguna otra transacción".</span><span class="sxs-lookup"><span data-stu-id="e0908-159">After configuring the transaction type for a scope or other entity supporting transactions in an orchestration, you receive the error "A Non-transactional Orchestration cannot contain any other Transactions".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="e0908-160">Causa</span><span class="sxs-lookup"><span data-stu-id="e0908-160">Cause</span></span>  
 <span data-ttu-id="e0908-161">Este error se produce cuando se intenta establecer el tipo de transacción de un ámbito (u otra entidad) de una orquestación en "Atómica" o "Larga ejecución" pero el tipo de transacción de la propia orquestación es "Ninguna".</span><span class="sxs-lookup"><span data-stu-id="e0908-161">This error occurs when you try to configure the transaction type of a scope (or other entity) in an orchestration to "Atomic" or "Long-Running" when the orchestration itself has a transaction type of "None".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="e0908-162">Solución</span><span class="sxs-lookup"><span data-stu-id="e0908-162">Resolution</span></span>  
 <span data-ttu-id="e0908-163">Asegurarse de que la configuración de tipos de transacción de la orquestación y de los objetos que la componen sean compatibles.</span><span class="sxs-lookup"><span data-stu-id="e0908-163">Ensure that the transaction type settings of your orchestration and constituent objects are compatible.</span></span>  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a><span data-ttu-id="e0908-164">Al generar el proyecto se produce el error "debe especificar al menos una correlación ya inicializada establecida para una recepción de no activación de un puerto no autocorrelacionado"</span><span class="sxs-lookup"><span data-stu-id="e0908-164">Project build results in the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port"</span></span>  
  
### <a name="problem"></a><span data-ttu-id="e0908-165">Problema</span><span class="sxs-lookup"><span data-stu-id="e0908-165">Problem</span></span>  
 <span data-ttu-id="e0908-166">Al compilar el proyecto de BizTalk, se recibe el error "debe especificar al menos una correlación ya inicializada establecida para una recepción de no activación de un puerto no autocorrelacionado".</span><span class="sxs-lookup"><span data-stu-id="e0908-166">When you compile your BizTalk project, you receive the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="e0908-167">Causa</span><span class="sxs-lookup"><span data-stu-id="e0908-167">Cause</span></span>  
 <span data-ttu-id="e0908-168">Este error puede producirse si la orquestación no tiene activar **recepción** formas (activar = true) o no tiene ningún activar **recepción** formas y no se llama directamente por otra orquestación.</span><span class="sxs-lookup"><span data-stu-id="e0908-168">This error can occur if your orchestration has no activating **Receive** shapes (Activate = true) or has no activating **Receive** shapes and is not called directly by another orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="e0908-169">Solución</span><span class="sxs-lookup"><span data-stu-id="e0908-169">Resolution</span></span>  
 <span data-ttu-id="e0908-170">Si no se llama a la orquestación otra orquestación, debe configurar uno de los **recepción** formas se recepciones de activación.</span><span class="sxs-lookup"><span data-stu-id="e0908-170">If your orchestration is not called by another orchestration, you must configure one of the **Receive** shapes to be an activated receive.</span></span> <span data-ttu-id="e0908-171">Para obtener más información acerca de cómo configurar el **recepción** forma, incluidos los vínculos a correlaciones, vea [cómo configurar la forma recepción](../core/how-to-configure-the-receive-shape.md).</span><span class="sxs-lookup"><span data-stu-id="e0908-171">For more information about configuring the **Receive** shape, including links to correlation, see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a><span data-ttu-id="e0908-172">Recibe el error "Error al generar el ensamblado--hace referencia el ensamblado '\<ensamblado\>' no tiene un nombre seguro" al compilar la solución</span><span class="sxs-lookup"><span data-stu-id="e0908-172">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly\>' does not have a strong name" when building your solution</span></span>  
  
### <a name="problem"></a><span data-ttu-id="e0908-173">Problema</span><span class="sxs-lookup"><span data-stu-id="e0908-173">Problem</span></span>  
 <span data-ttu-id="e0908-174">Recibe el error "Error al generar el ensamblado--hace referencia el ensamblado '\<ensamblado\>' no tiene un nombre seguro" al generar una solución que tiene una orquestación.</span><span class="sxs-lookup"><span data-stu-id="e0908-174">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly\>' does not have a strong name" when building your solution that has an orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="e0908-175">Causa</span><span class="sxs-lookup"><span data-stu-id="e0908-175">Cause</span></span>  
 <span data-ttu-id="e0908-176">Este problema se produce cuando se usa un tipo de un ensamblado sin firmar al que se hace referencia en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="e0908-176">This problem occurs when a type from an unsigned referenced assembly is used within an orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="e0908-177">Solución</span><span class="sxs-lookup"><span data-stu-id="e0908-177">Resolution</span></span>  
 <span data-ttu-id="e0908-178">Aplicar un nombre seguro al ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e0908-178">Apply a strong name to the referenced assembly.</span></span> <span data-ttu-id="e0908-179">Si se trata de un ensamblado personalizado que es posible volver a compilar, use la herramienta de nombre seguro para crear un archivo .snk (de clave) y, a continuación, haga referencia a este archivo de clave en las propiedades de ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0908-179">If it is a custom assembly that you can recompile, use the strong name tool to create an .snk (key) file and then reference that key file in the assembly properties for the project.</span></span> <span data-ttu-id="e0908-180">Para obtener más información sobre nombres seguros de un ensamblado, vea [cómo configurar un archivo de clave de ensamblado de nombre seguro](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span><span class="sxs-lookup"><span data-stu-id="e0908-180">For more information about strong naming an assembly, see [How to Configure a Strong Name Assembly Key File](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span></span>  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a><span data-ttu-id="e0908-181">El error "No se pudieron agregar los recursos.</span><span class="sxs-lookup"><span data-stu-id="e0908-181">The error "Failed to add resource(s).</span></span> <span data-ttu-id="e0908-182">Error en las solicitudes de cambio de algunos recursos" se produce al implementar una orquestación</span><span class="sxs-lookup"><span data-stu-id="e0908-182">Change requests failed for some resources" occurs when deploying an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="e0908-183">Problema</span><span class="sxs-lookup"><span data-stu-id="e0908-183">Problem</span></span>  
 <span data-ttu-id="e0908-184">Al implementar una orquestación, aparece un error parecido al siguiente y no se puede continuar con la implementación de la orquestación:</span><span class="sxs-lookup"><span data-stu-id="e0908-184">When deploying an orchestration, an error similar to the following is displayed and deployment of the orchestration fails:</span></span>  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a><span data-ttu-id="e0908-185">Causa</span><span class="sxs-lookup"><span data-stu-id="e0908-185">Cause</span></span>  
 <span data-ttu-id="e0908-186">Este error puede producirse si la orquestación contiene cualquier objeto que use palabras clave de C#.</span><span class="sxs-lookup"><span data-stu-id="e0908-186">This error can occur if the orchestration contains any objects that use C# keywords.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="e0908-187">Solución</span><span class="sxs-lookup"><span data-stu-id="e0908-187">Resolution</span></span>  
 <span data-ttu-id="e0908-188">Quitar todas las palabras clave de C# de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="e0908-188">Remove any C# keywords from the orchestration.</span></span> <span data-ttu-id="e0908-189">Para obtener una lista de palabras clave de C#, vea [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346).</span><span class="sxs-lookup"><span data-stu-id="e0908-189">For a list of C# keywords, see [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346).</span></span>  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a><span data-ttu-id="e0908-190">Se recibe un error "Valor de propiedad no válido" al compilar la orquestación</span><span class="sxs-lookup"><span data-stu-id="e0908-190">You receive an "invalid property value" error when compiling your orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="e0908-191">Problema</span><span class="sxs-lookup"><span data-stu-id="e0908-191">Problem</span></span>  
 <span data-ttu-id="e0908-192">Se recibe el cuadro de diálogo de error "Valor de propiedad no válido" al generar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="e0908-192">You receive the error dialog "Invalid property value" when building your orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="e0908-193">Causa</span><span class="sxs-lookup"><span data-stu-id="e0908-193">Cause</span></span>  
 <span data-ttu-id="e0908-194">Uno o varios de los objetos de la solución tiene el mismo nombre que otro objeto.</span><span class="sxs-lookup"><span data-stu-id="e0908-194">One or more of the objects in your solution has the same name as another object.</span></span> <span data-ttu-id="e0908-195">Por ejemplo, un nombre de mensaje es igual que un nombre de puerto.</span><span class="sxs-lookup"><span data-stu-id="e0908-195">For example, a message name is the same as a port name.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="e0908-196">Solución</span><span class="sxs-lookup"><span data-stu-id="e0908-196">Resolution</span></span>  
 <span data-ttu-id="e0908-197">Asegurarse de que todos los objetos de la solución tengan un nombre único.</span><span class="sxs-lookup"><span data-stu-id="e0908-197">Ensure that every object in your solution has a unique name.</span></span> <span data-ttu-id="e0908-198">Puede minimizar el riesgo de que se produzca este error respetando una convención de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="e0908-198">You can minimize the risk of this error by adhering to a naming convention.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0908-199">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0908-199">See Also</span></span>  
 [<span data-ttu-id="e0908-200">Cómo generar orquestaciones</span><span class="sxs-lookup"><span data-stu-id="e0908-200">How to Build Orchestrations</span></span>](../core/how-to-build-orchestrations.md)