---
redirect_url: /biztalk/core/feature-pack-add-build-release-definitions/
redirect_document_id: true
ROBOTS: NOINDEX
title: Configurar Visual Studio Team Services para implementar soluciones de BizTalk Server o los proyectos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2555712a-dfe4-420e-9a61-1d1a6d98c322
caps.latest.revision: 6
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 95d8e9fc274793471335fc03bc38c82c1b3e3469
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2017
ms.locfileid: "24054588"
---
# <a name="configure-visual-studio-team-services-to-deploy-biztalk-server-solutions-or-projects"></a><span data-ttu-id="d2278-102">Configurar Visual Studio Team Services para implementar soluciones de BizTalk Server o los proyectos</span><span class="sxs-lookup"><span data-stu-id="d2278-102">Configure Visual Studio Team Services to deploy BizTalk Server solutions or projects</span></span>
<span data-ttu-id="d2278-103">Configurar VSTS para implementar automáticamente [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] proyectos.</span><span class="sxs-lookup"><span data-stu-id="d2278-103">Set up VSTS to automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] projects.</span></span> 

<span data-ttu-id="d2278-104">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , puede generar automáticamente su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] soluciones mediante Visual Studio Team Services (VSTS).</span><span class="sxs-lookup"><span data-stu-id="d2278-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can automatically build your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] solutions using Visual Studio Team Services (VSTS).</span></span> 

<span data-ttu-id="d2278-105">En este tema se muestra cómo instalar y configurar Visual Studio Team Service (VSTS) para usar la implementación automática de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d2278-105">This topic shows you how to set up and configure Visual Studio Team Service (VSTS) to use automatic deployment for BizTalk.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d2278-106">El agente VSTS solo puede instalarse en uno [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo.</span><span class="sxs-lookup"><span data-stu-id="d2278-106">The VSTS agent can only be installed on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d2278-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d2278-107">Prerequisites</span></span>

* <span data-ttu-id="d2278-108">Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2278-108">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="d2278-109">Algunos experiencia y conocimientos de crear y trabajar con definiciones de VSTS.</span><span class="sxs-lookup"><span data-stu-id="d2278-109">Some experience and knowledge with creating and working with definitions in VSTS.</span></span> <span data-ttu-id="d2278-110">Si está familiarizado en VSTS, puede tratarse de buenos recursos:</span><span class="sxs-lookup"><span data-stu-id="d2278-110">If you're brand new to VSTS, these may be good resources:</span></span> 

  [<span data-ttu-id="d2278-111">Introducción a Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="d2278-111">Visual Studio Team Services overview</span></span>](https://www.visualstudio.com/docs/overview)  
  [<span data-ttu-id="d2278-112">Elemento de configuración/CD para principiantes</span><span class="sxs-lookup"><span data-stu-id="d2278-112">CI/CD for newbies</span></span>](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)
  

## <a name="create-a-vsts-account-and-create-a-definition"></a><span data-ttu-id="d2278-113">Cree una cuenta VSTS y crear una definición</span><span class="sxs-lookup"><span data-stu-id="d2278-113">Create a VSTS account and create a definition</span></span>

1. <span data-ttu-id="d2278-114">En un explorador web, vaya a su [perfil en línea de Visual Studio](https://app.vsaex.visualstudio.com/go/profile), inicie sesión y seleccione un **crear nueva cuenta**:</span><span class="sxs-lookup"><span data-stu-id="d2278-114">In a web browser, go to your [Visual Studio online profile](https://app.vsaex.visualstudio.com/go/profile), sign in, and select a **Create new account**:</span></span>

    ![Crear nueva cuenta](../core/media/create-a-new-account.png)

2. <span data-ttu-id="d2278-116">Escriba un nombre para la cuenta, seleccione el repositorio de código fuente preferida y seleccione **continuar**:</span><span class="sxs-lookup"><span data-stu-id="d2278-116">Enter a name for the account, select your preferred source code repository, and select **Continue**:</span></span>

    ![Crear un nuevo proyecto](../core/media/create-a-new-project.png)

3. <span data-ttu-id="d2278-118">Se crea la nueva cuenta y un sitio similar a `https://YourAccountName.visualstudio.com/MyFirstProject` se abre.</span><span class="sxs-lookup"><span data-stu-id="d2278-118">Your new account is created, and a site similar to `https://YourAccountName.visualstudio.com/MyFirstProject` opens.</span></span>
    
4. <span data-ttu-id="d2278-119">Instalar el [servicio de implementar la aplicación de BizTalk](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application) a la cuenta que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="d2278-119">Install the [Deploy BizTalk Application service](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application) to the account you just created.</span></span>

    ![Nueva versión de compilación](../core/media/build-new-release.png)

5. <span data-ttu-id="d2278-121">Es posible que obtenga algunos mensajes.</span><span class="sxs-lookup"><span data-stu-id="d2278-121">You may get some prompts.</span></span> <span data-ttu-id="d2278-122">Confirmar para continuar.</span><span class="sxs-lookup"><span data-stu-id="d2278-122">Confirm to continue.</span></span> <span data-ttu-id="d2278-123">Asegúrese de que ha iniciado sesión el proyecto en VSTS.</span><span class="sxs-lookup"><span data-stu-id="d2278-123">Be sure you're signed in to your project in VSTS.</span></span>

6. <span data-ttu-id="d2278-124">Seleccione **compilación y versión**y crear un **New** definición de compilación:</span><span class="sxs-lookup"><span data-stu-id="d2278-124">Select **Build and release**, and create a **New** build definition:</span></span>

    ![Seleccione la compilación y versión](../core/media/select-build-and-release.png)

    > [!TIP]
    > <span data-ttu-id="d2278-126">Asegúrese de que está en `https://YourAccountName.visualstudio.com/MyFirstProject`.</span><span class="sxs-lookup"><span data-stu-id="d2278-126">Be sure you're at `https://YourAccountName.visualstudio.com/MyFirstProject`.</span></span> <span data-ttu-id="d2278-127">En caso contrario, el **New** o **nueva definición** botones no pueden estar no existe.</span><span class="sxs-lookup"><span data-stu-id="d2278-127">Otherwise, the **New** or **New definition** buttons may not be there.</span></span> 
    
7. <span data-ttu-id="d2278-128">Seleccione el **Visual Studio** plantilla y seleccione **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="d2278-128">Select the **Visual Studio** template, and select **Next**:</span></span>

    ![Seleccione visual studio y haga clic en siguiente](../core/media/select-visual-studio-and-click-next.png)

8. <span data-ttu-id="d2278-130">Revise la configuración y seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="d2278-130">Review your settings, and select **Create**.</span></span>

9. <span data-ttu-id="d2278-131">Eliminar los pasos que no es necesario.</span><span class="sxs-lookup"><span data-stu-id="d2278-131">Delete the steps you don't need.</span></span> <span data-ttu-id="d2278-132">Para este tutorial, se pueden eliminar los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2278-132">For this tutorial, you can delete the following:</span></span> 
* <span data-ttu-id="d2278-133">Restauración de NuGet</span><span class="sxs-lookup"><span data-stu-id="d2278-133">NuGet Restore</span></span>
* <span data-ttu-id="d2278-134">Ensamblados de prueba</span><span class="sxs-lookup"><span data-stu-id="d2278-134">Test assemblies</span></span>
* <span data-ttu-id="d2278-135">Publicar la ruta de acceso de símbolos</span><span class="sxs-lookup"><span data-stu-id="d2278-135">Publish symbols path</span></span> 

    ![Eliminar los pasos que no sea necesarios](../core/media/delete-steps-not-needed.png)

10. <span data-ttu-id="d2278-137">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="d2278-137">**Optional**.</span></span> <span data-ttu-id="d2278-138">Si desea habilitar la integración continua (CI), seleccione **desencadenadores** en el menú y verificación **integración continua (CI)**.</span><span class="sxs-lookup"><span data-stu-id="d2278-138">If you want to enable Continous Integration (CI), select **Triggers** in the menu, and check **Continous integration (CI)**.</span></span>

<span data-ttu-id="d2278-139">A continuación, instale el agente en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2278-139">Next, install the agent on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

## <a name="install-the-agent"></a><span data-ttu-id="d2278-140">Instalar el agente</span><span class="sxs-lookup"><span data-stu-id="d2278-140">Install the Agent</span></span>

<span data-ttu-id="d2278-141">Para que funcione la solución, habilitar a un agente de Windows privada en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="d2278-141">For the solution to work, enable a private Windows Agent on your local machine.</span></span> <span data-ttu-id="d2278-142">Recuerde que **el agente debe instalarse en una [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo**.</span><span class="sxs-lookup"><span data-stu-id="d2278-142">Remember, **the agent must be installed on only one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group**.</span></span> 

1. <span data-ttu-id="d2278-143">En la definición, seleccione la **General** pestaña (en la parte superior).</span><span class="sxs-lookup"><span data-stu-id="d2278-143">In your definition, select the **General** tab (at the top).</span></span>
2. <span data-ttu-id="d2278-144">Para el **cola predeterminada del agente** propiedad, seleccione la **predeterminado** agente desde la lista.</span><span class="sxs-lookup"><span data-stu-id="d2278-144">For the **Default agent queue** property, select the **Default** agent from the list.</span></span> 
3. <span data-ttu-id="d2278-145">Seleccione **administrar** junto a la **cola predeterminada del agente** propiedad.</span><span class="sxs-lookup"><span data-stu-id="d2278-145">Select **Manage** next to the **Default agent queue** property.</span></span> <span data-ttu-id="d2278-146">Se abre una nueva pestaña de explorador.</span><span class="sxs-lookup"><span data-stu-id="d2278-146">A new browser tab opens.</span></span>

    ![Crear a nuevo agente de administración](../core/media/create-new-management-agent.png)

4. <span data-ttu-id="d2278-148">En el panel izquierdo, está seleccionada la cola de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d2278-148">In the left pane, the Default queue is selected.</span></span> <span data-ttu-id="d2278-149">Si un agente ya está lista y, a continuación, en línea, a continuación, ha terminado.</span><span class="sxs-lookup"><span data-stu-id="d2278-149">If an agent is already listed, and online, then you're done.</span></span> <span data-ttu-id="d2278-150">Tiene un agente instalado y ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="d2278-150">You have an agent installed, and running.</span></span> 

    <span data-ttu-id="d2278-151">Si no se incluye un agente, a continuación, seleccione **descargar agente**y continuar con la instalación en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2278-151">If an agent is not listed, then select **Download agent**, and continue with the installation on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d2278-152">**Vaya a [implementar un agente en Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows) para todos los pasos** para instalar el agente e iniciar un agente.</span><span class="sxs-lookup"><span data-stu-id="d2278-152">**Go to [Deploy an agent on Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows) for the complete steps** to install the agent, and start an agent.</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="d2278-153">Siga los pasos descritos en [implementar un agente en Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows).</span><span class="sxs-lookup"><span data-stu-id="d2278-153">Follow all the steps at [Deploy an agent on Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows).</span></span> <span data-ttu-id="d2278-154">No omita este paso.</span><span class="sxs-lookup"><span data-stu-id="d2278-154">Do not skip this step.</span></span> 

5. <span data-ttu-id="d2278-155">Con el agente predeterminado **en línea**, vuelva a la **General** pestaña en la definición y confirme **predeterminado** está seleccionada para el **cola predeterminada del agente**.</span><span class="sxs-lookup"><span data-stu-id="d2278-155">With the default agent **Online**, go back to the **General** tab in your definition, and confirm **Default** is selected for the **Default agent queue**.</span></span>
6. <span data-ttu-id="d2278-156">**Guardar** y **poner nueva compilación en cola**.</span><span class="sxs-lookup"><span data-stu-id="d2278-156">**Save** and **Queue new build**.</span></span>

<span data-ttu-id="d2278-157">A continuación, cree la definición de la implementación de aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d2278-157">Next, create the BizTalk Server Application Deployment definition.</span></span>

## <a name="create-the-biztalk-deployment-definition"></a><span data-ttu-id="d2278-158">Crear la definición de la implementación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d2278-158">Create the BizTalk deployment definition</span></span>

1. <span data-ttu-id="d2278-159">Seleccione el **compilaciones** ficha, seleccione **todas las definiciones de**y seleccione **New**:</span><span class="sxs-lookup"><span data-stu-id="d2278-159">Select the **Builds** tab, select **All Definitions**, and select **New**:</span></span>

    ![Crear definición de la nueva versión](../core/media/create-new-release-defintion.png)

2. <span data-ttu-id="d2278-161">Seleccione el **vacía** plantilla y seleccione **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="d2278-161">Select the **Empty** template, and select **Next**:</span></span>

    ![Crear nueva definición de una plantilla vacía](../core/media/create-new-defintion-from-an-empty-template.png)

3. <span data-ttu-id="d2278-163">Seleccione el **repositorio** origen y **bifurcación** para la definición.</span><span class="sxs-lookup"><span data-stu-id="d2278-163">Select your **Repository** source and **Branch** for the definition.</span></span>
4. <span data-ttu-id="d2278-164">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="d2278-164">**Optional**.</span></span> <span data-ttu-id="d2278-165">Seleccione **integración continua**.</span><span class="sxs-lookup"><span data-stu-id="d2278-165">Select **Continous Integration**.</span></span>
5. <span data-ttu-id="d2278-166">Seleccione el **predeterminado** agente en la lista de la cola y seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="d2278-166">Select the **Default** agent from the queue list, and select **Create**.</span></span>
6. <span data-ttu-id="d2278-167">**Agregar el paso de compilación**, seleccione la **implementación de aplicación de BizTalk Server** de tareas y seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="d2278-167">**Add build step**, select the **BizTalk Server Application Deployment** task, and select **Add**.</span></span> <span data-ttu-id="d2278-168">**Cerrar** el catálogo de la tarea.</span><span class="sxs-lookup"><span data-stu-id="d2278-168">**Close** the task catalog.</span></span>

    ![Agregar nuevo implementar definición](../core/media/add-new-deploy-definition.png)

7. <span data-ttu-id="d2278-170">Seleccione el **nombre de la operación** que desea usar:</span><span class="sxs-lookup"><span data-stu-id="d2278-170">Select the **Operation Name** you want to use:</span></span>
    * <span data-ttu-id="d2278-171">**Crear nueva aplicación de BizTalk** implementa una nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="d2278-171">**Create new BizTalk Application** deploys a new application.</span></span> <span data-ttu-id="d2278-172">Si la aplicación ya existe, desinstala las aplicaciones actuales (detención completa) e instala la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="d2278-172">If the application already exsist, it uninstalls the current applications (full stop), and installs the new application.</span></span> <span data-ttu-id="d2278-173">Si está habilitada la integración continua, lo automáticamente vuelve a implementar la aplicación cuando se actualiza en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="d2278-173">If continous integration is enabled, it automatically redeploys the application when it is updated in the repository.</span></span>
    * <span data-ttu-id="d2278-174">**Actualizar una aplicación de BizTalk existente** anexa los cambios, como **esquemas** a una aplicación ya se está ejecuta.</span><span class="sxs-lookup"><span data-stu-id="d2278-174">**Update an exsisting BizTalk Application** appends changes, such as **Schemas** to an already running application.</span></span> <span data-ttu-id="d2278-175">No se requiere una nueva implementación completa de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d2278-175">It does not require a full redeploy of the application.</span></span>
8. <span data-ttu-id="d2278-176">Escriba el **nombre de la aplicación** en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="d2278-176">Enter the **Application name** in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>
9. <span data-ttu-id="d2278-177">En **ruta de acceso de paquete de implementación**, seleccione la ruta de acceso al archivo zip en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="d2278-177">In **Deployment package path**, select the path to the zip file in your repository.</span></span>
10. <span data-ttu-id="d2278-178">Seleccione **desencadenadores** en el menú, habilitar **integración continua**y seleccione el valor correcto **bifurcación** para la compilación.</span><span class="sxs-lookup"><span data-stu-id="d2278-178">Select **Triggers** from the menu, enable **Continous Integration**, and select the correct **Branch** for the build.</span></span>
11. <span data-ttu-id="d2278-179">Seleccione **guardar**:</span><span class="sxs-lookup"><span data-stu-id="d2278-179">Select **Save**:</span></span>

    ![Guarde la nueva definición de compilación](../core/media/save-the-new-build-definition.png)

12. <span data-ttu-id="d2278-181">Nombre de la nueva **definición**y establezca la ruta de acceso correcta.</span><span class="sxs-lookup"><span data-stu-id="d2278-181">Name the new **Definition**, and set the correct path.</span></span> 
13. <span data-ttu-id="d2278-182">Una vez que se guarda la definición, seleccione **la nueva compilación en cola**.</span><span class="sxs-lookup"><span data-stu-id="d2278-182">Once the definition is saved, select **Queue the new build**.</span></span> <span data-ttu-id="d2278-183">A continuación, seleccione la **agente cola**y agregar un comentario a la confirmación.</span><span class="sxs-lookup"><span data-stu-id="d2278-183">Then, select the **Queue agent**, and add a comment to the commit.</span></span>
