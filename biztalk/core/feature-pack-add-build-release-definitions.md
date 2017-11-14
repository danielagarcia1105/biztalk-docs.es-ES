---
title: "Paso 3: crear las definiciones de compilación y la versión | Documentos de Microsoft"
description: "En VSTS, cree una definición de compilación para compilar los proyectos en el repositorio TFS o git, a continuación, crear una definición de la versión para implementar la aplicación de BizTalk Server"
ms.custom: 
ms.date: 11/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de86d35fd615d8c0f1eee1127804645067c4bf6e
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2017
---
# <a name="step-3-create-the-build-and-release-definition"></a><span data-ttu-id="71e7e-103">Paso 3: Crear la compilación y la versión de definición</span><span class="sxs-lookup"><span data-stu-id="71e7e-103">Step 3: Create the build and release definition</span></span>

<span data-ttu-id="71e7e-104">Las definiciones de compilación y la versión son tareas de Visual Studio Team Services y probablemente deben hacerse mediante un administrador de VSTS. La definición de compilación compila el proyecto en el repositorio git y las definiciones de versión lo implementa en el entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="71e7e-104">The build and release definitions are Visual Studio Team Services tasks, and should probably be done by a VSTS admin. The build definition builds your project within your git repository, and the release definitions deploys it to your BizTalk Server environment.</span></span> 

## <a name="add-the-build-tasks"></a><span data-ttu-id="71e7e-105">Agregue las tareas de compilación</span><span class="sxs-lookup"><span data-stu-id="71e7e-105">Add the Build tasks</span></span>
1. <span data-ttu-id="71e7e-106">En el proyecto, seleccione **de compilación y la versión**.</span><span class="sxs-lookup"><span data-stu-id="71e7e-106">In your project, select **Build and release**.</span></span> <span data-ttu-id="71e7e-107">Se abre la pestaña de compilaciones.</span><span class="sxs-lookup"><span data-stu-id="71e7e-107">The Builds tab opens.</span></span> <span data-ttu-id="71e7e-108">Crear un **New** definición:</span><span class="sxs-lookup"><span data-stu-id="71e7e-108">Create a **New** definition:</span></span>

    ![Nueva definición de compilación](../core/media/vsts-new-definition.png)

2. <span data-ttu-id="71e7e-110">Seleccione el **vacía** plantilla y seleccione **aplicar**:</span><span class="sxs-lookup"><span data-stu-id="71e7e-110">Select the **Empty** template, and select **Apply**:</span></span>  

    ![Seleccione la plantilla vacía](../core/media/vsts-emtpy-template.png)
 
3. <span data-ttu-id="71e7e-112">Establecer el **cola del agente** valores predeterminados:</span><span class="sxs-lookup"><span data-stu-id="71e7e-112">Set the **Agent Queue** to Default:</span></span> 

    ![Elija la cola de forma predeterminada](../core/media/vsts-select-agent-queue.png)

4. <span data-ttu-id="71e7e-114">En **fase 1**, agregue una tarea, seleccione **Visual Studio Build**y seleccione **agregar**:</span><span class="sxs-lookup"><span data-stu-id="71e7e-114">In **Phase 1**, add a task, select **Visual Studio Build**, and select **Add**:</span></span>

    ![Agregar la que tarea de compilación de VS](../core/media/vsts-add-visual-studio-task.png)

5. <span data-ttu-id="71e7e-116">Haga clic en la tarea de compilación de Visual Studio que acaba de agrega y establezca las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="71e7e-116">Click the Visual Studio Build task you just added, and set the following properties:</span></span>  

    | <span data-ttu-id="71e7e-117">Propiedad</span><span class="sxs-lookup"><span data-stu-id="71e7e-117">Property</span></span> | <span data-ttu-id="71e7e-118">Establecer en</span><span class="sxs-lookup"><span data-stu-id="71e7e-118">Set to</span></span> |
    | --- | --- | 
    | <span data-ttu-id="71e7e-119">Nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="71e7e-119">Display name</span></span> | <span data-ttu-id="71e7e-120">*NombreDeProyecto* compilar solución **\*.sln</span><span class="sxs-lookup"><span data-stu-id="71e7e-120">*YourProjectName* Build solution **\*.sln</span></span> | 
    | <span data-ttu-id="71e7e-121">Versión de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="71e7e-121">Visual Studio version</span></span> | <span data-ttu-id="71e7e-122">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="71e7e-122">Visual Studio 2015</span></span> | 
    | <span data-ttu-id="71e7e-123">Arquitectura de MSBuild</span><span class="sxs-lookup"><span data-stu-id="71e7e-123">MSBuild Architecture</span></span> | <span data-ttu-id="71e7e-124">MSBuild x86</span><span class="sxs-lookup"><span data-stu-id="71e7e-124">MSBuild x86</span></span> | 

6. <span data-ttu-id="71e7e-125">En **fase 1**, agregue una tarea, seleccione **publicar artefactos de compilación**y seleccione **agregar**:</span><span class="sxs-lookup"><span data-stu-id="71e7e-125">In **Phase 1**, add a task, select **Publish Build Artifacts**, and select **Add**:</span></span> 

    ![Agregar la que tarea de compilación de VS](../core/media/vsts-add-publish-build-task.png)

7. <span data-ttu-id="71e7e-127">Seleccione el **publicar artefacto** de tareas y escriba su preferido **nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="71e7e-127">Select the **Publish Artifact** task, and enter your preferred **Display name**.</span></span> <span data-ttu-id="71e7e-128">Para **ruta de acceso para publicar**, seleccione la **...**  botón y elija la carpeta de proyecto de aplicación (por ejemplo, appProjectHelloWorld).</span><span class="sxs-lookup"><span data-stu-id="71e7e-128">For **Path to publish**, select the **...**  button, and choose the application project folder (e.g. appProjectHelloWorld).</span></span> <span data-ttu-id="71e7e-129">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="71e7e-129">Select **OK**.</span></span>

8. <span data-ttu-id="71e7e-130">El **nombre del artefacto** puede ser cualquier cosa que desee.</span><span class="sxs-lookup"><span data-stu-id="71e7e-130">The **Artifact Name** can be anything you want.</span></span> <span data-ttu-id="71e7e-131">Seleccione **guardar**.</span><span class="sxs-lookup"><span data-stu-id="71e7e-131">Select **Save**.</span></span> 

9. <span data-ttu-id="71e7e-132">Vaya a **desencadenadores**y establezca el **desencadenar estado** a **habilitado**:</span><span class="sxs-lookup"><span data-stu-id="71e7e-132">Go to **Triggers**, and set the **Trigger status** to **Enabled**:</span></span>  

    ![Agregar la que tarea de compilación de VS](../core/media/vsts-continuous-integration.png)

10. <span data-ttu-id="71e7e-134">**Guardar y poner en cola** para probar la definición de compilación.</span><span class="sxs-lookup"><span data-stu-id="71e7e-134">**Save & Queue** to test your build definition.</span></span> <span data-ttu-id="71e7e-135">Cuando pone en cola, se le solicitará la cola del agente y la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="71e7e-135">When you queue, you are prompted for the agent queue and your branch.</span></span> <span data-ttu-id="71e7e-136">Seleccione el **predeterminado** agente de cola y elija la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="71e7e-136">Select the **Default** agent queue, and choose your branch.</span></span> <span data-ttu-id="71e7e-137">Seleccione **cola**.</span><span class="sxs-lookup"><span data-stu-id="71e7e-137">Select **Queue**.</span></span>  

11. <span data-ttu-id="71e7e-138">Se inicia una nueva compilación, y puede seleccionarlo para comprobar si un éxito o error.</span><span class="sxs-lookup"><span data-stu-id="71e7e-138">A new build is started, and you can select it to check for a success or failure.</span></span> 

## <a name="add-the-release-tasks"></a><span data-ttu-id="71e7e-139">Agregue las tareas de versión</span><span class="sxs-lookup"><span data-stu-id="71e7e-139">Add the release tasks</span></span>

<span data-ttu-id="71e7e-140">Cuando la compilación se realiza correctamente, la definición de la versión implementa la aplicación en el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="71e7e-140">When the build succeeds, the release definition deploys your application to your BizTalk Server.</span></span> 

1. <span data-ttu-id="71e7e-141">Seleccione el **versiones** ficha, seleccione **nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="71e7e-141">Select the **Releases** tab, select **New definition**.</span></span> 

2. <span data-ttu-id="71e7e-142">Seleccione el **vacía** plantilla y seleccione **aplicar**:</span><span class="sxs-lookup"><span data-stu-id="71e7e-142">Select the **Empty** template, and select **Apply**:</span></span>

    ![Agregar plantilla vacía](../core/media/vsts-empty-release-template.png)

3. <span data-ttu-id="71e7e-144">Cambiar el **nombre del entorno** a **Dev**, o todo lo que desees para que se llame.</span><span class="sxs-lookup"><span data-stu-id="71e7e-144">Change the **Environment name** to **Dev**, or whatever you want to call it.</span></span> 

4. <span data-ttu-id="71e7e-145">Seleccione **agregar artefactos**, seleccione el proyecto, la definición de compilación y seleccione **agregar**:</span><span class="sxs-lookup"><span data-stu-id="71e7e-145">Select **Add artifact**, select your project, your build definition, and select **Add**:</span></span> 

5. <span data-ttu-id="71e7e-146">Vaya a la **tareas** ficha, agregue una nueva tarea:</span><span class="sxs-lookup"><span data-stu-id="71e7e-146">Go to the **Tasks** tab, add a new task:</span></span> 

    ![Agregar la tarea de liberación](../core/media/vsts-new-release-tasks.png)

6. <span data-ttu-id="71e7e-148">En la lista, filtrar los resultados, seleccione la **implementación de aplicación de BizTalk Server** de tareas y seleccione **agregar**:</span><span class="sxs-lookup"><span data-stu-id="71e7e-148">From the list, filter the results, select the **BizTalk Server Application Deployment** task, and select **Add**:</span></span>  

    ![Agregar tareas de implementación de BizTalk](../core/media/vsts-biztalk-application-deployment-task.png)

    <span data-ttu-id="71e7e-150">Si **implementación de aplicación de BizTalk Server** ins't en la lista, vuelva a instalarlo después en [implementar aplicación de BizTalk](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application).</span><span class="sxs-lookup"><span data-stu-id="71e7e-150">If **BizTalk Server Application Deployment** ins't listed, then install it at [Deploy BizTalk Application](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application).</span></span>

7. <span data-ttu-id="71e7e-151">Seleccione el **implementar** , escriba los valores y de la tarea:</span><span class="sxs-lookup"><span data-stu-id="71e7e-151">Select the **Deploy** task, and enter the values:</span></span> 

    <span data-ttu-id="71e7e-152">**Nombre de la operación**: seleccione **crear nueva aplicación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="71e7e-152">**Operation Name**: Select **Create new BizTalk Application**.</span></span> <span data-ttu-id="71e7e-153">Esta opción implementa una nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="71e7e-153">This option deploys a new application.</span></span> <span data-ttu-id="71e7e-154">Si la aplicación ya existe, desinstala las aplicaciones actuales (detención completa) e instala la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="71e7e-154">If the application already exists, it uninstalls the current applications (full stop), and installs the new application.</span></span> <span data-ttu-id="71e7e-155">Si está habilitada la integración continua, lo automáticamente vuelve a implementar la aplicación cuando se actualiza en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="71e7e-155">If continuous integration is enabled, it automatically redeploys the application when it is updated in the repository.</span></span> <span data-ttu-id="71e7e-156">**Actualizar una aplicación de BizTalk existente** anexa los cambios, como esquemas, a una aplicación ya se está ejecuta.</span><span class="sxs-lookup"><span data-stu-id="71e7e-156">**Update an existing BizTalk Application** appends changes, such as schemas, to an already running application.</span></span> <span data-ttu-id="71e7e-157">No se requiere una nueva implementación completa de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="71e7e-157">It does not require a full redeploy of the application.</span></span>

    <span data-ttu-id="71e7e-158">**Nombre de la aplicación**: el texto que escriba será el nombre de aplicación de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="71e7e-158">**Application Name**: The text you enter will be the application name in BizTalk Administration.</span></span> <span data-ttu-id="71e7e-159">Hacer **no** escriba BizTalk Application 1.</span><span class="sxs-lookup"><span data-stu-id="71e7e-159">Do **not** enter BizTalk Application 1.</span></span>

    <span data-ttu-id="71e7e-160">**Paquete de implementación**: seleccione el archivo zip en el proyecto de aplicación y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="71e7e-160">**Deployment package**: Select the zip file to your application project, and select **OK**.</span></span> 

8. <span data-ttu-id="71e7e-161">Seleccione el **fase agente** tarea.</span><span class="sxs-lookup"><span data-stu-id="71e7e-161">Select the **Agent phase** task.</span></span> <span data-ttu-id="71e7e-162">Seleccione el **predeterminado** cola del agente.</span><span class="sxs-lookup"><span data-stu-id="71e7e-162">Select the **Default** Agent queue.</span></span> <span data-ttu-id="71e7e-163">**Guardar** los cambios.</span><span class="sxs-lookup"><span data-stu-id="71e7e-163">**Save** your changes.</span></span>

9. <span data-ttu-id="71e7e-164">Seleccione **versión** > **crear versión**:</span><span class="sxs-lookup"><span data-stu-id="71e7e-164">Select **Release** > **Create release**:</span></span>  

    ![La versión, crear versión](../core/media/vsts-create-release.png)

10. <span data-ttu-id="71e7e-166">Seleccione **cola**.</span><span class="sxs-lookup"><span data-stu-id="71e7e-166">Select **Queue**.</span></span> <span data-ttu-id="71e7e-167">Compruebe el estado haciendo clic en el vínculo de la versión.</span><span class="sxs-lookup"><span data-stu-id="71e7e-167">Check the status by clicking the release link.</span></span> <span data-ttu-id="71e7e-168">Si se produce un error, se muestra el error.</span><span class="sxs-lookup"><span data-stu-id="71e7e-168">If it fails, the error displays.</span></span> <span data-ttu-id="71e7e-169">Si se realiza correctamente, la aplicación se agrega a la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="71e7e-169">If it succeeds, the application is added to the BizTalk Administration console.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="71e7e-170">Lo que hizo</span><span class="sxs-lookup"><span data-stu-id="71e7e-170">What you did</span></span>

<span data-ttu-id="71e7e-171">En VSTS, ha creado una definición de compilación que compile su aplicación en Git o Team Foundation Version Control (lo que ha elegido).</span><span class="sxs-lookup"><span data-stu-id="71e7e-171">In VSTS, you created a build definition that builds your application within Git or Team Foundation Version Control (whatever you chose).</span></span> <span data-ttu-id="71e7e-172">Cuando se realizan cambios en el control de código fuente, los cambios se detectan automáticamente y puede insertarlas.</span><span class="sxs-lookup"><span data-stu-id="71e7e-172">When changes are made within the source control, the changes are automatically detected, and you can push them.</span></span> <span data-ttu-id="71e7e-173">Una vez finalizada la compilación, se crea una definición de la versión que implementa la aplicación en BizTalk Server, que puede ver en administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="71e7e-173">After the build completes, you created a release definition that deploys the application to BizTalk Server, which you can see in BizTalk Server Administration.</span></span> 

## <a name="next-step"></a><span data-ttu-id="71e7e-174">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="71e7e-174">Next step</span></span>
<span data-ttu-id="71e7e-175">En este paso, ha terminado.</span><span class="sxs-lookup"><span data-stu-id="71e7e-175">At this step, you're done.</span></span> <span data-ttu-id="71e7e-176">Si lo prefiere, puede crear tokens medioambientales dentro del archivo de enlace XML de BizTalk y crear variables del sistema en VSTS que coinciden con los tokens de entorno.</span><span class="sxs-lookup"><span data-stu-id="71e7e-176">If you prefer, you can create environmental tokens within your BizTalk XML binding file, and create variables within VSTS that match the environmental tokens.</span></span> <span data-ttu-id="71e7e-177">Vea [configurar tokens de entorno y variables](configure-environmental-tokens-and-variables-for-automatic-deployment.md) para obtener los detalles.</span><span class="sxs-lookup"><span data-stu-id="71e7e-177">See [Configure environmental tokens and variables](configure-environmental-tokens-and-variables-for-automatic-deployment.md) for the details.</span></span> 