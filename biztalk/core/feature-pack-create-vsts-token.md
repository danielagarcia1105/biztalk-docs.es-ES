---
title: 'Paso 2: crear token VSTS e instale el agente | Microsoft Docs'
description: Crear el clon VSTS seguridad access token, el proyecto de VSTS en Visual Studio e instalar el agente de compilación para automatizar la implementación de los proyectos de BizTalk Server
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d26a218b6de83b1ab2e5a2dd46be215dcbb0f49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979349"
---
# <a name="step-2-create-the-token--install-the-agent"></a><span data-ttu-id="ef03c-103">Paso 2: Crear el token e instalar el agente</span><span class="sxs-lookup"><span data-stu-id="ef03c-103">Step 2: Create the token & install the agent</span></span>

<span data-ttu-id="ef03c-104">Se crea un token de acceso personal (PAT) en Visual Studio Team Services.</span><span class="sxs-lookup"><span data-stu-id="ef03c-104">A personal access token (PAT) is created in Visual Studio Team Services.</span></span> <span data-ttu-id="ef03c-105">Este token es su contraseña y se usa el agente de compilación VSTS para autenticar.</span><span class="sxs-lookup"><span data-stu-id="ef03c-105">This token is your password, and is used by the VSTS build agent to authenticate.</span></span> <span data-ttu-id="ef03c-106">El token solo se muestra al crearla.</span><span class="sxs-lookup"><span data-stu-id="ef03c-106">The token is only displayed when you create it.</span></span> <span data-ttu-id="ef03c-107">Después de eso, no se muestra ya.</span><span class="sxs-lookup"><span data-stu-id="ef03c-107">After that, it isn't displayed anymore.</span></span> <span data-ttu-id="ef03c-108">Así que después de crearlo, guardarlo en otro archivo en una ubicación capaz de recordar.</span><span class="sxs-lookup"><span data-stu-id="ef03c-108">So once you create it, save it to another file in a remember-able location.</span></span> 

<span data-ttu-id="ef03c-109">Obtener más información sobre PAT en [autenticar el acceso con tokens de acceso personal para VSTS y TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span><span class="sxs-lookup"><span data-stu-id="ef03c-109">More info on PAT at [Authenticate access with personal access tokens for VSTS and TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span></span> 

<span data-ttu-id="ef03c-110">Después de crear el token, instale al agente de compilación y configúrelo para utilizar este token.</span><span class="sxs-lookup"><span data-stu-id="ef03c-110">After you create the token, you install the build agent, and configure it to use this token.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="ef03c-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ef03c-111">Before you begin</span></span>
<span data-ttu-id="ef03c-112">Completa [paso 1: proyecto de aplicación agregue y actualice los json](feature-pack-add-application-project.md).</span><span class="sxs-lookup"><span data-stu-id="ef03c-112">Complete [Step 1 - Add Application project and update json](feature-pack-add-application-project.md).</span></span>

## <a name="sign-into-vsts-and-create-the-token"></a><span data-ttu-id="ef03c-113">Inicie sesión en VSTS y crear el token</span><span class="sxs-lookup"><span data-stu-id="ef03c-113">Sign into VSTS, and create the token</span></span>
1. <span data-ttu-id="ef03c-114">Vaya a [ https://app.vsaex.visualstudio.com/go/profile ](https://app.vsaex.visualstudio.com/go/profile)e inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="ef03c-114">Go to [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile), and sign-in with your work or school account.</span></span> <span data-ttu-id="ef03c-115">Después de iniciar sesión, se muestra la cuenta de VSTS.</span><span class="sxs-lookup"><span data-stu-id="ef03c-115">After you sign in, your VSTS account is listed.</span></span> <span data-ttu-id="ef03c-116">En el ejemplo siguiente, la cuenta es **mandiaprojects.visualstudio.com**.</span><span class="sxs-lookup"><span data-stu-id="ef03c-116">In the following example, the account is **mandiaprojects.visualstudio.com**.</span></span>  

    ![Cuenta de VSTS](../core/media/team-services-accounts.png)

    <span data-ttu-id="ef03c-118">Si no tiene una cuenta, seleccione **crear nueva cuenta**y escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="ef03c-118">If you don’t have an account, select **Create new account**, and enter a name.</span></span> <span data-ttu-id="ef03c-119">Para administrar el código, elija su preferencia personal entre **Git o Team Foundation Version Control**.</span><span class="sxs-lookup"><span data-stu-id="ef03c-119">To manage your code, choose your personal preference between **Git or Team Foundation Version Control**.</span></span> <span data-ttu-id="ef03c-120">Cuando termine, se crea la nueva cuenta y un sitio similar a *https://YourAccountName.visualstudio.com/MyFirstProject* abre:</span><span class="sxs-lookup"><span data-stu-id="ef03c-120">When finished, your new account is created, and a site similar to *https://YourAccountName.visualstudio.com/MyFirstProject* opens:</span></span>  

    ![GIT o TFS](../core/media/git-or-team-foundation.png)

2. <span data-ttu-id="ef03c-122">Abra su cuenta de VSTS (https://<em>YourAccountName</em>. visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="ef03c-122">Open your VSTS account (https://<em>YourAccountName</em>.visualstudio.com).</span></span> <span data-ttu-id="ef03c-123">Seleccione el icono en la parte superior derecha y seleccione **seguridad**:</span><span class="sxs-lookup"><span data-stu-id="ef03c-123">Select your icon in the top right-side corner, and select **Security**:</span></span> 

    ![Abra la seguridad de la cuenta](../core/media/vsts-account-security.png)

3. <span data-ttu-id="ef03c-125">**Tokens de acceso personal** se abre automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ef03c-125">**Personal access tokens** automatically opens.</span></span> <span data-ttu-id="ef03c-126">Si tiene un agente existente, selecciónelo y confirmar **grupos de agentes (leer, administrar)** está seleccionado:</span><span class="sxs-lookup"><span data-stu-id="ef03c-126">If you have an existing agent, select it, and confirm **Agent Pools (read, manage)** is selected:</span></span>

    ![-Grupos de agentes de lectura y administración](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > <span data-ttu-id="ef03c-128">Debe conocer el token de acceso.</span><span class="sxs-lookup"><span data-stu-id="ef03c-128">You must know the access token.</span></span> <span data-ttu-id="ef03c-129">Si no y no tenga en cuenta en cualquier lugar, no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="ef03c-129">If you don’t, and didn’t note it anywhere, it cannot be retrieved.</span></span> <span data-ttu-id="ef03c-130">En esta situación, cree a un nuevo agente.</span><span class="sxs-lookup"><span data-stu-id="ef03c-130">In this situation, create a new agent.</span></span> 

    <span data-ttu-id="ef03c-131">Si no tiene un agente existente, seleccione **agregar**, escriba una descripción, establecer la fecha de expiración y seleccione su cuenta.</span><span class="sxs-lookup"><span data-stu-id="ef03c-131">If you don’t have an existing agent, select **Add**, enter a description, set the expiration date, and select your account.</span></span> <span data-ttu-id="ef03c-132">En **seleccionado ámbitos**, seleccione **grupos de agentes (leer, administrar)**:</span><span class="sxs-lookup"><span data-stu-id="ef03c-132">In **Selected scopes**, select **Agent Pools (read, manage)**:</span></span> 

    ![Crear a nuevo agente: leer y administrar](../core/media/vsts-new-build-agent.png)

    <span data-ttu-id="ef03c-134">Seleccione **crear Token**.</span><span class="sxs-lookup"><span data-stu-id="ef03c-134">Select **Create Token**.</span></span> <span data-ttu-id="ef03c-135">**Tenga en cuenta el valor del token; se necesita en el futuro de pasos.**</span><span class="sxs-lookup"><span data-stu-id="ef03c-135">**Note the token value; you need in future steps.**</span></span>

4. <span data-ttu-id="ef03c-136">Seleccione **código**y seleccione **clonar en Visual Studio**:</span><span class="sxs-lookup"><span data-stu-id="ef03c-136">Select **Code**, and select **Clone in Visual Studio**:</span></span>  

    ![En el proyecto, seleccione el código](../core/media/vsts-project-code.png)  

    ![Clonar en Visual Studio](../core/media/vsts-clone-in-visual-studio.png)

5. <span data-ttu-id="ef03c-139">Se abre Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ef03c-139">Visual Studio opens.</span></span> <span data-ttu-id="ef03c-140">En Visual Studio, abra la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ef03c-140">Within Visual Studio, open your BizTalk solution.</span></span> 

## <a name="install-the-build-agent"></a><span data-ttu-id="ef03c-141">Instalar al agente de compilación</span><span class="sxs-lookup"><span data-stu-id="ef03c-141">Install the Build Agent</span></span>

<span data-ttu-id="ef03c-142">El agente de compilación está instalado en el equipo de desarrollo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ef03c-142">The build agent is installed on the BizTalk development computer.</span></span> <span data-ttu-id="ef03c-143">Si usa grupos de implementación, el agente de compilación se instala en todos los servidores de BizTalk que desea implementar en.</span><span class="sxs-lookup"><span data-stu-id="ef03c-143">If using deployment groups, the build agent is installed on all the BizTalk servers you want to deploy to.</span></span> <span data-ttu-id="ef03c-144">Los pasos siguientes muestran cómo instalar al agente de compilación en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="ef03c-144">The following steps show you how to install the build agent on a single computer.</span></span> <span data-ttu-id="ef03c-145">Para obtener más información sobre el uso de grupos de implementación, consulte [grupos de implementación](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index).</span><span class="sxs-lookup"><span data-stu-id="ef03c-145">For details on using deployment groups, see [Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index).</span></span>

1. <span data-ttu-id="ef03c-146">Abra su cuenta de VSTS y un proyecto, que es algo como *https://YourAccountName.visualstudio.com/MyFirstProject*.</span><span class="sxs-lookup"><span data-stu-id="ef03c-146">Open your VSTS account and project, which is something like *https://YourAccountName.visualstudio.com/MyFirstProject*.</span></span> <span data-ttu-id="ef03c-147">Seleccione el icono de configuración y seleccione **colas de agentes**:</span><span class="sxs-lookup"><span data-stu-id="ef03c-147">Select the settings icon, and select **Agent Queues**:</span></span>  

    ![Configuración > colas de agentes](../core/media/vsts-settings-agent-queues.png)

2. <span data-ttu-id="ef03c-149">Seleccione el **predeterminado** agente y seleccione **descargar agente**.</span><span class="sxs-lookup"><span data-stu-id="ef03c-149">Select the **Default** agent, and select **Download Agent**.</span></span> <span data-ttu-id="ef03c-150">Seleccione el **descargar** botón y guarde el archivo para su **descargas** carpetas.</span><span class="sxs-lookup"><span data-stu-id="ef03c-150">Select the **Download** button, and save the file to your **Downloads** folders.</span></span>

3. <span data-ttu-id="ef03c-151">Los pasos de instalación se abrirán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ef03c-151">The install steps automatically open.</span></span> <span data-ttu-id="ef03c-152">Siga estos pasos para la información más actualizada.</span><span class="sxs-lookup"><span data-stu-id="ef03c-152">Follow those steps for the most up-to-date details.</span></span> <span data-ttu-id="ef03c-153">Aquí tiene algunas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="ef03c-153">Here is some guidance:</span></span> 

   1. <span data-ttu-id="ef03c-154">Abra Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="ef03c-154">Open Windows PowerShell as Administrator.</span></span>

   2. <span data-ttu-id="ef03c-155">Para crear al agente, escriba:</span><span class="sxs-lookup"><span data-stu-id="ef03c-155">To create the agent, enter:</span></span> 

       ```powershell
       PS C:\> mkdir agent ; cd agent  

       PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
       ```

       <span data-ttu-id="ef03c-156">Los cambios de versión del archivo de agente de vsts.</span><span class="sxs-lookup"><span data-stu-id="ef03c-156">The vsts-agent file version changes.</span></span> <span data-ttu-id="ef03c-157">Por lo tanto, siga los pasos de instalación VSTS para obtener detalles concretos.</span><span class="sxs-lookup"><span data-stu-id="ef03c-157">So follow the VSTS install steps for specific details.</span></span> <span data-ttu-id="ef03c-158">Una vez alcanzado escriba, puede tardar unos minutos para el símbolo del sistema devolver.</span><span class="sxs-lookup"><span data-stu-id="ef03c-158">After you hit enter, it may take a couple of minutes for the prompt to return.</span></span> 

   3. <span data-ttu-id="ef03c-159">Para configurar al agente, escriba:</span><span class="sxs-lookup"><span data-stu-id="ef03c-159">To configure the agent, enter:</span></span> 

       ```powershell
       PS C:\agent> .\config.cmd
       ```

   4. <span data-ttu-id="ef03c-160">Escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="ef03c-160">Enter the following details:</span></span>  


      |        <span data-ttu-id="ef03c-161">Property</span><span class="sxs-lookup"><span data-stu-id="ef03c-161">Property</span></span>        |                                                                      <span data-ttu-id="ef03c-162">Valor</span><span class="sxs-lookup"><span data-stu-id="ef03c-162">Value</span></span>                                                                       |
      |------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
      |       <span data-ttu-id="ef03c-163">Dirección URL del servidor</span><span class="sxs-lookup"><span data-stu-id="ef03c-163">Server URL</span></span>       |                                                     <span data-ttu-id="ef03c-164">https://{Your-Account}.VisualStudio.com</span><span class="sxs-lookup"><span data-stu-id="ef03c-164">https://{your-account}.visualstudio.com</span></span>                                                      |
      |  <span data-ttu-id="ef03c-165">Tipo de autenticación</span><span class="sxs-lookup"><span data-stu-id="ef03c-165">Authentication Type</span></span>   |                                                                       <span data-ttu-id="ef03c-166">PAT</span><span class="sxs-lookup"><span data-stu-id="ef03c-166">PAT</span></span>                                                                        |
      | <span data-ttu-id="ef03c-167">Token de acceso personal</span><span class="sxs-lookup"><span data-stu-id="ef03c-167">Personal access token</span></span>  |                                                              <span data-ttu-id="ef03c-168">Pegue el token VSTS</span><span class="sxs-lookup"><span data-stu-id="ef03c-168">Paste your VSTS token</span></span>                                                               |
      |       <span data-ttu-id="ef03c-169">Grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="ef03c-169">Agent pool</span></span>       |                                                              <span data-ttu-id="ef03c-170">Escriba el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="ef03c-170">Enter for the default</span></span>                                                               |
      |       <span data-ttu-id="ef03c-171">Nombre del agente</span><span class="sxs-lookup"><span data-stu-id="ef03c-171">Agent name</span></span>       |                                                              <span data-ttu-id="ef03c-172">Escriba el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="ef03c-172">Enter for the default</span></span>                                                               |
      |        <span data-ttu-id="ef03c-173">Reemplazar</span><span class="sxs-lookup"><span data-stu-id="ef03c-173">Replace</span></span>         |                                                  <span data-ttu-id="ef03c-174">*Muestra solo si tiene un agente existente*</span><span class="sxs-lookup"><span data-stu-id="ef03c-174">*Only displays if you have an existing agent*</span></span>                                                   |
      |      <span data-ttu-id="ef03c-175">Carpeta de trabajo</span><span class="sxs-lookup"><span data-stu-id="ef03c-175">Work folder</span></span>       |                                                              <span data-ttu-id="ef03c-176">Escriba el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="ef03c-176">Enter for the default</span></span>                                                               |
      | <span data-ttu-id="ef03c-177">Ejecutar a agente como un servicio</span><span class="sxs-lookup"><span data-stu-id="ef03c-177">Run agent as a service</span></span> |                                                                        <span data-ttu-id="ef03c-178">S</span><span class="sxs-lookup"><span data-stu-id="ef03c-178">Y</span></span>                                                                         |
      |      <span data-ttu-id="ef03c-179">Cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="ef03c-179">User account</span></span>      | <span data-ttu-id="ef03c-180">Esto depende de usted, pero experimenta un problema de permisos.</span><span class="sxs-lookup"><span data-stu-id="ef03c-180">This is up to you, but you may run into a permissions issue.</span></span> <br/><br/><span data-ttu-id="ef03c-181">Considere la posibilidad de escribir su actual ha iniciado la sesión cuenta, que es un administrador local.</span><span class="sxs-lookup"><span data-stu-id="ef03c-181">Consider entering your current logged-on account, which is a local Admin.</span></span> |


   5. <span data-ttu-id="ef03c-182">Cuando termine, la ventana de PowerShell es similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef03c-182">When finished, your PowerShell window looks like the following:</span></span>  

       ![Instalación del agente](../core/media/vsts-agent-powershell-install.png)

4. <span data-ttu-id="ef03c-184">Abra services.msc para ver el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="ef03c-184">Open services.msc to see the new service.</span></span> <span data-ttu-id="ef03c-185">Debe estar ejecutando:</span><span class="sxs-lookup"><span data-stu-id="ef03c-185">It should be running:</span></span>  

    ![Se está ejecutando el servicio](../core/media/vsts-service.png)

    <span data-ttu-id="ef03c-187">Si el servicio no se inicia, [quitar y volver a configurar un agente](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) con una cuenta con más privilegios.</span><span class="sxs-lookup"><span data-stu-id="ef03c-187">If the service fails to start, [remove and re-configure an agent](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) using an account with more privilages.</span></span>


## <a name="what-you-did"></a><span data-ttu-id="ef03c-188">Lo que hizo</span><span class="sxs-lookup"><span data-stu-id="ef03c-188">What you did</span></span>

<span data-ttu-id="ef03c-189">Se ha iniciado sesión en su cuenta de VSTS y crea un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ef03c-189">You signed into your VSTS account, and created a security token.</span></span> <span data-ttu-id="ef03c-190">Este token de seguridad es como una contraseña y proporciona acceso a su proyecto de VSTS.</span><span class="sxs-lookup"><span data-stu-id="ef03c-190">This security token is like a password, and gives you access to your VSTS project.</span></span> <span data-ttu-id="ef03c-191">Solo se muestra una vez, por lo que se está seguro de que lo ha guardado.</span><span class="sxs-lookup"><span data-stu-id="ef03c-191">It's only displayed once, so be sure you saved it.</span></span> <span data-ttu-id="ef03c-192">También clona el proyecto de VSTS en Visual Studio y crea a un agente que se ejecuta como un servicio en el equipo de desarrollo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ef03c-192">You also cloned your VSTS project into Visual Studio, and created an agent that runs as a service on your BizTalk development computer.</span></span> <span data-ttu-id="ef03c-193">Este agente utiliza el token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ef03c-193">This agent uses the security token.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="ef03c-194">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ef03c-194">Next steps</span></span>
[<span data-ttu-id="ef03c-195">Paso 3: Crear la compilación y definiciones de versión</span><span class="sxs-lookup"><span data-stu-id="ef03c-195">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="ef03c-196">Configurar las variables y los tokens de entorno</span><span class="sxs-lookup"><span data-stu-id="ef03c-196">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)