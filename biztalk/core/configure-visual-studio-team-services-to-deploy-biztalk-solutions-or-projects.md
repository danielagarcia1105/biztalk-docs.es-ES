---
redirect_url: /biztalk/core/feature-pack-add-build-release-definitions/
redirect_document_id: true
ROBOTS: NOINDEX
title: Configurar Visual Studio Team Services para implementar soluciones de BizTalk Server o proyectos | Microsoft Docs
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
ms.openlocfilehash: 7178f85bce4087e5bc740810050817676a6c8996
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992477"
---
# <a name="configure-visual-studio-team-services-to-deploy-biztalk-server-solutions-or-projects"></a><span data-ttu-id="f44b4-102">Configurar Visual Studio Team Services para implementar proyectos o soluciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f44b4-102">Configure Visual Studio Team Services to deploy BizTalk Server solutions or projects</span></span>
<span data-ttu-id="f44b4-103">Configurar VSTS para implementar automáticamente [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] proyectos.</span><span class="sxs-lookup"><span data-stu-id="f44b4-103">Set up VSTS to automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] projects.</span></span> 

<span data-ttu-id="f44b4-104">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , puede generar automáticamente su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] soluciones mediante Visual Studio Team Services (VSTS).</span><span class="sxs-lookup"><span data-stu-id="f44b4-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can automatically build your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] solutions using Visual Studio Team Services (VSTS).</span></span> 

<span data-ttu-id="f44b4-105">Este tema muestra cómo instalar y configurar Visual Studio Team Service (VSTS) para usar la implementación automática de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f44b4-105">This topic shows you how to set up and configure Visual Studio Team Service (VSTS) to use automatic deployment for BizTalk.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f44b4-106">El agente VSTS solo puede instalarse en uno [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo.</span><span class="sxs-lookup"><span data-stu-id="f44b4-106">The VSTS agent can only be installed on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f44b4-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f44b4-107">Prerequisites</span></span>

* <span data-ttu-id="f44b4-108">Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f44b4-108">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="f44b4-109">Algo de experiencia y conocimientos sobre crear y trabajar con definiciones en VSTS.</span><span class="sxs-lookup"><span data-stu-id="f44b4-109">Some experience and knowledge with creating and working with definitions in VSTS.</span></span> <span data-ttu-id="f44b4-110">Si está familiarizado con VSTS, pueden ser buenos recursos:</span><span class="sxs-lookup"><span data-stu-id="f44b4-110">If you're brand new to VSTS, these may be good resources:</span></span> 

  [<span data-ttu-id="f44b4-111">Información general de Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="f44b4-111">Visual Studio Team Services overview</span></span>](https://www.visualstudio.com/docs/overview)  
  [<span data-ttu-id="f44b4-112">CI/CD para principiantes</span><span class="sxs-lookup"><span data-stu-id="f44b4-112">CI/CD for newbies</span></span>](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)
  

## <a name="create-a-vsts-account-and-create-a-definition"></a><span data-ttu-id="f44b4-113">Crear una cuenta de VSTS y crear una definición</span><span class="sxs-lookup"><span data-stu-id="f44b4-113">Create a VSTS account and create a definition</span></span>

1. <span data-ttu-id="f44b4-114">En un explorador web, vaya a su [perfil de Visual Studio online](https://app.vsaex.visualstudio.com/go/profile), inicie sesión y seleccione un **crear nueva cuenta**:</span><span class="sxs-lookup"><span data-stu-id="f44b4-114">In a web browser, go to your [Visual Studio online profile](https://app.vsaex.visualstudio.com/go/profile), sign in, and select a **Create new account**:</span></span>

    ![Crear nueva cuenta](../core/media/create-a-new-account.png)

2. <span data-ttu-id="f44b4-116">Escriba un nombre para la cuenta, seleccione el repositorio de código fuente preferido y seleccione **continuar**:</span><span class="sxs-lookup"><span data-stu-id="f44b4-116">Enter a name for the account, select your preferred source code repository, and select **Continue**:</span></span>

    ![Crear un nuevo proyecto](../core/media/create-a-new-project.png)

3. <span data-ttu-id="f44b4-118">Se crea la nueva cuenta y un sitio similar a `https://YourAccountName.visualstudio.com/MyFirstProject` se abre.</span><span class="sxs-lookup"><span data-stu-id="f44b4-118">Your new account is created, and a site similar to `https://YourAccountName.visualstudio.com/MyFirstProject` opens.</span></span>
    
4. <span data-ttu-id="f44b4-119">Instalar el [servicios de implementación de la aplicación BizTalk](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application) a la cuenta que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="f44b4-119">Install the [Deploy BizTalk Application service](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application) to the account you just created.</span></span>

    ![Crear nueva versión](../core/media/build-new-release.png)

5. <span data-ttu-id="f44b4-121">Puede obtener algunas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="f44b4-121">You may get some prompts.</span></span> <span data-ttu-id="f44b4-122">Confirmar para continuar.</span><span class="sxs-lookup"><span data-stu-id="f44b4-122">Confirm to continue.</span></span> <span data-ttu-id="f44b4-123">Asegúrese de que ha iniciado sesión el proyecto en VSTS.</span><span class="sxs-lookup"><span data-stu-id="f44b4-123">Be sure you're signed in to your project in VSTS.</span></span>

6. <span data-ttu-id="f44b4-124">Seleccione **compilación y versión**y crear un **New** definición de compilación:</span><span class="sxs-lookup"><span data-stu-id="f44b4-124">Select **Build and release**, and create a **New** build definition:</span></span>

    ![Seleccione la compilación y versión](../core/media/select-build-and-release.png)

    > [!TIP]
    > <span data-ttu-id="f44b4-126">Asegúrese de estar en `https://YourAccountName.visualstudio.com/MyFirstProject`.</span><span class="sxs-lookup"><span data-stu-id="f44b4-126">Be sure you're at `https://YourAccountName.visualstudio.com/MyFirstProject`.</span></span> <span data-ttu-id="f44b4-127">En caso contrario, el **New** o **nueva definición** botones no pueden estar allí.</span><span class="sxs-lookup"><span data-stu-id="f44b4-127">Otherwise, the **New** or **New definition** buttons may not be there.</span></span> 
    
7. <span data-ttu-id="f44b4-128">Seleccione el **Visual Studio** plantilla y seleccione **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="f44b4-128">Select the **Visual Studio** template, and select **Next**:</span></span>

    ![Seleccione visual studio y haga clic en siguiente](../core/media/select-visual-studio-and-click-next.png)

8. <span data-ttu-id="f44b4-130">Revise la configuración y seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-130">Review your settings, and select **Create**.</span></span>

9. <span data-ttu-id="f44b4-131">Eliminar los pasos que no es necesario.</span><span class="sxs-lookup"><span data-stu-id="f44b4-131">Delete the steps you don't need.</span></span> <span data-ttu-id="f44b4-132">Para este tutorial, puede eliminar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f44b4-132">For this tutorial, you can delete the following:</span></span> 
10. <span data-ttu-id="f44b4-133">Restauración de NuGet</span><span class="sxs-lookup"><span data-stu-id="f44b4-133">NuGet Restore</span></span>
11. <span data-ttu-id="f44b4-134">Ensamblados de prueba</span><span class="sxs-lookup"><span data-stu-id="f44b4-134">Test assemblies</span></span>
12. <span data-ttu-id="f44b4-135">Publicar ruta de acceso de símbolos</span><span class="sxs-lookup"><span data-stu-id="f44b4-135">Publish symbols path</span></span> 

      ![Eliminar los pasos que no sea necesarios](../core/media/delete-steps-not-needed.png)

13. <span data-ttu-id="f44b4-137">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-137">**Optional**.</span></span> <span data-ttu-id="f44b4-138">Si desea habilitar la integración continua (CI), seleccione **desencadenadores** en el menú y verificación **integración continua (CI)**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-138">If you want to enable Continous Integration (CI), select **Triggers** in the menu, and check **Continous integration (CI)**.</span></span>

<span data-ttu-id="f44b4-139">A continuación, instale el agente en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f44b4-139">Next, install the agent on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

## <a name="install-the-agent"></a><span data-ttu-id="f44b4-140">Instalar el agente</span><span class="sxs-lookup"><span data-stu-id="f44b4-140">Install the Agent</span></span>

<span data-ttu-id="f44b4-141">Para que funcione la solución, habilite a un agente privado de Windows en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f44b4-141">For the solution to work, enable a private Windows Agent on your local machine.</span></span> <span data-ttu-id="f44b4-142">Recuerde, **el agente debe instalarse en una [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-142">Remember, **the agent must be installed on only one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group**.</span></span> 

1. <span data-ttu-id="f44b4-143">En la definición, seleccione el **General** pestaña (en la parte superior).</span><span class="sxs-lookup"><span data-stu-id="f44b4-143">In your definition, select the **General** tab (at the top).</span></span>
2. <span data-ttu-id="f44b4-144">Para el **cola de agentes predeterminada** propiedad, seleccione el **predeterminado** agente desde la lista.</span><span class="sxs-lookup"><span data-stu-id="f44b4-144">For the **Default agent queue** property, select the **Default** agent from the list.</span></span> 
3. <span data-ttu-id="f44b4-145">Seleccione **administrar** junto a la **cola de agentes predeterminada** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f44b4-145">Select **Manage** next to the **Default agent queue** property.</span></span> <span data-ttu-id="f44b4-146">Se abre una nueva pestaña del explorador.</span><span class="sxs-lookup"><span data-stu-id="f44b4-146">A new browser tab opens.</span></span>

    ![Crear a nuevo agente de administración](../core/media/create-new-management-agent.png)

4. <span data-ttu-id="f44b4-148">En el panel izquierdo, se selecciona la cola predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f44b4-148">In the left pane, the Default queue is selected.</span></span> <span data-ttu-id="f44b4-149">Si un agente ya está activa y en línea, a continuación, ya ha terminado.</span><span class="sxs-lookup"><span data-stu-id="f44b4-149">If an agent is already listed, and online, then you're done.</span></span> <span data-ttu-id="f44b4-150">Tiene un agente instalado y ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="f44b4-150">You have an agent installed, and running.</span></span> 

    <span data-ttu-id="f44b4-151">Si un agente no aparece, seleccione **descargar agente**y continuar con la instalación en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f44b4-151">If an agent is not listed, then select **Download agent**, and continue with the installation on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f44b4-152">**Vaya a [implementar un agente en Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows) para conocer los pasos completos** para instalar el agente e iniciar un agente.</span><span class="sxs-lookup"><span data-stu-id="f44b4-152">**Go to [Deploy an agent on Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows) for the complete steps** to install the agent, and start an agent.</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="f44b4-153">Siga los pasos descritos en [implementar un agente en Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows).</span><span class="sxs-lookup"><span data-stu-id="f44b4-153">Follow all the steps at [Deploy an agent on Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows).</span></span> <span data-ttu-id="f44b4-154">No omita este paso.</span><span class="sxs-lookup"><span data-stu-id="f44b4-154">Do not skip this step.</span></span> 

5. <span data-ttu-id="f44b4-155">Con el agente de forma predeterminada **Online**, vuelva a la **General** pestaña en la definición y confirme **predeterminada** está seleccionada para la **cola de agentes predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-155">With the default agent **Online**, go back to the **General** tab in your definition, and confirm **Default** is selected for the **Default agent queue**.</span></span>
6. <span data-ttu-id="f44b4-156">**Guardar** y **poner nueva compilación en cola**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-156">**Save** and **Queue new build**.</span></span>

<span data-ttu-id="f44b4-157">A continuación, cree la definición de implementación de aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f44b4-157">Next, create the BizTalk Server Application Deployment definition.</span></span>

## <a name="create-the-biztalk-deployment-definition"></a><span data-ttu-id="f44b4-158">Crear la definición de implementación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f44b4-158">Create the BizTalk deployment definition</span></span>

1. <span data-ttu-id="f44b4-159">Seleccione el **compilaciones** ficha, seleccione **todas las definiciones de**y seleccione **New**:</span><span class="sxs-lookup"><span data-stu-id="f44b4-159">Select the **Builds** tab, select **All Definitions**, and select **New**:</span></span>

    ![Crear nueva definición de versión](../core/media/create-new-release-defintion.png)

2. <span data-ttu-id="f44b4-161">Seleccione el **vacía** plantilla y seleccione **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="f44b4-161">Select the **Empty** template, and select **Next**:</span></span>

    ![Crear nueva definición de una plantilla vacía](../core/media/create-new-defintion-from-an-empty-template.png)

3. <span data-ttu-id="f44b4-163">Seleccione su **repositorio** origen y **rama** para la definición.</span><span class="sxs-lookup"><span data-stu-id="f44b4-163">Select your **Repository** source and **Branch** for the definition.</span></span>
4. <span data-ttu-id="f44b4-164">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-164">**Optional**.</span></span> <span data-ttu-id="f44b4-165">Seleccione **integración continua**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-165">Select **Continous Integration**.</span></span>
5. <span data-ttu-id="f44b4-166">Seleccione el **predeterminado** agente desde la lista de la cola y seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-166">Select the **Default** agent from the queue list, and select **Create**.</span></span>
6. <span data-ttu-id="f44b4-167">**Agregar paso de compilación**, seleccione el **implementación de aplicación de BizTalk Server** de tareas y seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-167">**Add build step**, select the **BizTalk Server Application Deployment** task, and select **Add**.</span></span> <span data-ttu-id="f44b4-168">**Cerrar** el catálogo de tareas.</span><span class="sxs-lookup"><span data-stu-id="f44b4-168">**Close** the task catalog.</span></span>

    ![Agregar definición puede implementar](../core/media/add-new-deploy-definition.png)

7. <span data-ttu-id="f44b4-170">Seleccione el **nombre de la operación** que desea usar:</span><span class="sxs-lookup"><span data-stu-id="f44b4-170">Select the **Operation Name** you want to use:</span></span>
    * <span data-ttu-id="f44b4-171">**Crear nueva aplicación de BizTalk** implementa una nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="f44b4-171">**Create new BizTalk Application** deploys a new application.</span></span> <span data-ttu-id="f44b4-172">Si la aplicación ya existe, desinstala las aplicaciones actuales (detención completa) e instala la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="f44b4-172">If the application already exsist, it uninstalls the current applications (full stop), and installs the new application.</span></span> <span data-ttu-id="f44b4-173">Si está habilitada la integración continua, lo automáticamente vuelve a implementar la aplicación cuando se actualizan en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="f44b4-173">If continous integration is enabled, it automatically redeploys the application when it is updated in the repository.</span></span>
    * <span data-ttu-id="f44b4-174">**Actualizar una aplicación de BizTalk existente** anexa los cambios, como **esquemas** a una aplicación ya se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f44b4-174">**Update an exsisting BizTalk Application** appends changes, such as **Schemas** to an already running application.</span></span> <span data-ttu-id="f44b4-175">No se requiere una reimplementación completa de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f44b4-175">It does not require a full redeploy of the application.</span></span>
8. <span data-ttu-id="f44b4-176">Escriba el **nombre de la aplicación** en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="f44b4-176">Enter the **Application name** in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>
9. <span data-ttu-id="f44b4-177">En **ruta de acceso de paquete de implementación**, seleccione la ruta de acceso al archivo zip del repositorio.</span><span class="sxs-lookup"><span data-stu-id="f44b4-177">In **Deployment package path**, select the path to the zip file in your repository.</span></span>
10. <span data-ttu-id="f44b4-178">Seleccione **desencadenadores** en el menú, habilitar **integración continua**y seleccione el valor correcto **rama** para la compilación.</span><span class="sxs-lookup"><span data-stu-id="f44b4-178">Select **Triggers** from the menu, enable **Continous Integration**, and select the correct **Branch** for the build.</span></span>
11. <span data-ttu-id="f44b4-179">Seleccione **guardar**:</span><span class="sxs-lookup"><span data-stu-id="f44b4-179">Select **Save**:</span></span>

    ![Guarde la nueva definición de compilación](../core/media/save-the-new-build-definition.png)

12. <span data-ttu-id="f44b4-181">El nombre del nuevo **definición**y establezca la ruta de acceso correcta.</span><span class="sxs-lookup"><span data-stu-id="f44b4-181">Name the new **Definition**, and set the correct path.</span></span> 
13. <span data-ttu-id="f44b4-182">Una vez que se guarda la definición, seleccione **poner en cola la nueva compilación**.</span><span class="sxs-lookup"><span data-stu-id="f44b4-182">Once the definition is saved, select **Queue the new build**.</span></span> <span data-ttu-id="f44b4-183">A continuación, seleccione el **agente cola**y agregue un comentario a la confirmación.</span><span class="sxs-lookup"><span data-stu-id="f44b4-183">Then, select the **Queue agent**, and add a comment to the commit.</span></span>
