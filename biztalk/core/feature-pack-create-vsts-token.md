---
title: 'Paso 2: crear el token VSTS e instale el agente | Documentos de Microsoft'
description: "Crear el clon de símbolo (token), de acceso de seguridad VSTS el proyecto VSTS en Visual Studio e instalar el agente de compilación para automatizar la implementación de los proyectos de BizTalk Server"
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
ms.openlocfilehash: 46047f0bb6a536642d503d68bb4f9161ecdf7fc5
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2017
---
# <a name="step-2-create-the-token--install-the-agent"></a><span data-ttu-id="c100c-103">Paso 2: Crear el token e instalar el agente</span><span class="sxs-lookup"><span data-stu-id="c100c-103">Step 2: Create the token & install the agent</span></span>

<span data-ttu-id="c100c-104">Se crea un token de acceso personal (PAT) en Visual Studio Team Services.</span><span class="sxs-lookup"><span data-stu-id="c100c-104">A personal access token (PAT) is created in Visual Studio Team Services.</span></span> <span data-ttu-id="c100c-105">Este token es su contraseña y es utilizado por el agente de compilación VSTS para autenticar.</span><span class="sxs-lookup"><span data-stu-id="c100c-105">This token is your password, and is used by the VSTS build agent to authenticate.</span></span> <span data-ttu-id="c100c-106">El token solo se muestra cuando la cree.</span><span class="sxs-lookup"><span data-stu-id="c100c-106">The token is only displayed when you create it.</span></span> <span data-ttu-id="c100c-107">Después de eso, no se muestra ya.</span><span class="sxs-lookup"><span data-stu-id="c100c-107">After that, it isn't displayed anymore.</span></span> <span data-ttu-id="c100c-108">Por lo que una vez creada, guardarlo en otro archivo en una ubicación capaz de recordar.</span><span class="sxs-lookup"><span data-stu-id="c100c-108">So once you create it, save it to another file in a remember-able location.</span></span> 

<span data-ttu-id="c100c-109">Obtener más información sobre PAT en [autenticar el acceso con tokens de acceso personal para VSTS y TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span><span class="sxs-lookup"><span data-stu-id="c100c-109">More info on PAT at [Authenticate access with personal access tokens for VSTS and TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span></span> 

<span data-ttu-id="c100c-110">Después de crear el token, instalar al agente de compilación y configúrelo para utilizar este token.</span><span class="sxs-lookup"><span data-stu-id="c100c-110">After you create the token, you install the build agent, and configure it to use this token.</span></span> 

## <a name="sign-into-vsts-and-create-the-token"></a><span data-ttu-id="c100c-111">Iniciar sesión en VSTS y crear el token</span><span class="sxs-lookup"><span data-stu-id="c100c-111">Sign into VSTS, and create the token</span></span>
1. <span data-ttu-id="c100c-112">Vaya a [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile)e inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c100c-112">Go to [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile), and sign-in with your work or school account.</span></span> <span data-ttu-id="c100c-113">Después de iniciar la sesión, se muestra la cuenta VSTS.</span><span class="sxs-lookup"><span data-stu-id="c100c-113">After you sign in, your VSTS account is listed.</span></span> <span data-ttu-id="c100c-114">En el ejemplo siguiente, la cuenta es **mandiaprojects.visualstudio.com**.</span><span class="sxs-lookup"><span data-stu-id="c100c-114">In the following example, the account is **mandiaprojects.visualstudio.com**.</span></span>  

    ![Cuenta VSTS](../core/media/team-services-accounts.png)

    <span data-ttu-id="c100c-116">Si no tiene una cuenta, seleccione **crear nueva cuenta**y escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="c100c-116">If you don’t have an account, select **Create new account**, and enter a name.</span></span> <span data-ttu-id="c100c-117">Para administrar el código, elija su preferencia personal entre **Git o Team Foundation Version Control**.</span><span class="sxs-lookup"><span data-stu-id="c100c-117">To manage your code, choose your personal preference between **Git or Team Foundation Version Control**.</span></span> <span data-ttu-id="c100c-118">Cuando termine, se crea la nueva cuenta y un sitio similar a *https://YourAccountName.visualstudio.com/MyFirstProject* abre:</span><span class="sxs-lookup"><span data-stu-id="c100c-118">When finished, your new account is created, and a site similar to *https://YourAccountName.visualstudio.com/MyFirstProject* opens:</span></span>  

    ![GIT o TFS](../core/media/git-or-team-foundation.png)

2. <span data-ttu-id="c100c-120">Abra su cuenta VSTS (https://*YourAccountName*. visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="c100c-120">Open your VSTS account (https://*YourAccountName*.visualstudio.com).</span></span> <span data-ttu-id="c100c-121">Seleccione el icono en la esquina superior de la derecha y seleccione **seguridad**:</span><span class="sxs-lookup"><span data-stu-id="c100c-121">Select your icon in the top right-side corner, and select **Security**:</span></span> 

    ![Abra la seguridad de la cuenta](../core/media/vsts-account-security.png)

3. <span data-ttu-id="c100c-123">**Tokens de acceso personal** se abre automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c100c-123">**Personal access tokens** automatically opens.</span></span> <span data-ttu-id="c100c-124">Si tiene un agente existente, selecciónelo y confirmar **grupos de agente (lectura, administrar)** está seleccionado:</span><span class="sxs-lookup"><span data-stu-id="c100c-124">If you have an existing agent, select it, and confirm **Agent Pools (read, manage)** is selected:</span></span>

    ![Grupos de agente: lectura y administración](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > <span data-ttu-id="c100c-126">Debe conocer el token de acceso.</span><span class="sxs-lookup"><span data-stu-id="c100c-126">You must know the access token.</span></span> <span data-ttu-id="c100c-127">Si no y no tenga en cuenta en cualquier lugar, no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="c100c-127">If you don’t, and didn’t note it anywhere, it cannot be retrieved.</span></span> <span data-ttu-id="c100c-128">En esta situación, cree a un nuevo agente.</span><span class="sxs-lookup"><span data-stu-id="c100c-128">In this situation, create a new agent.</span></span> 

    <span data-ttu-id="c100c-129">Si no tiene un agente existente, seleccione **agregar**, escriba una descripción, establecer la fecha de expiración y seleccione su cuenta.</span><span class="sxs-lookup"><span data-stu-id="c100c-129">If you don’t have an existing agent, select **Add**, enter a description, set the expiration date, and select your account.</span></span> <span data-ttu-id="c100c-130">En **seleccionado ámbitos**, seleccione **grupos de agente (lectura, administrar)**:</span><span class="sxs-lookup"><span data-stu-id="c100c-130">In **Selected scopes**, select **Agent Pools (read, manage)**:</span></span> 

    ![Crear a nuevo agente: leer y administrar](../core/media/vsts-new-build-agent.png)

    <span data-ttu-id="c100c-132">Seleccione **crear Token**.</span><span class="sxs-lookup"><span data-stu-id="c100c-132">Select **Create Token**.</span></span> <span data-ttu-id="c100c-133">**Tenga en cuenta el valor del token; en el futuro necesita pasos.**</span><span class="sxs-lookup"><span data-stu-id="c100c-133">**Note the token value; you need in future steps.**</span></span>

4. <span data-ttu-id="c100c-134">Seleccione **código**y seleccione **clon en Visual Studio**:</span><span class="sxs-lookup"><span data-stu-id="c100c-134">Select **Code**, and select **Clone in Visual Studio**:</span></span>  

    ![En el proyecto, seleccione el código](../core/media/vsts-project-code.png)  

    ![Clonar en Visual Studio](../core/media/vsts-clone-in-visual-studio.png)

5. <span data-ttu-id="c100c-137">Visual Studio abre.</span><span class="sxs-lookup"><span data-stu-id="c100c-137">Visual Studio opens.</span></span> <span data-ttu-id="c100c-138">En Visual Studio, abra la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c100c-138">Within Visual Studio, open your BizTalk solution.</span></span> 

## <a name="install-the-build-agent"></a><span data-ttu-id="c100c-139">Instalar al agente de compilación</span><span class="sxs-lookup"><span data-stu-id="c100c-139">Install the Build Agent</span></span>

<span data-ttu-id="c100c-140">El agente de compilación está instalado en el equipo de desarrollo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c100c-140">The build agent is installed on the BizTalk development computer.</span></span> 

1. <span data-ttu-id="c100c-141">Abra su cuenta VSTS y el proyecto, que es algo como *https://YourAccountName.visualstudio.com/MyFirstProject*.</span><span class="sxs-lookup"><span data-stu-id="c100c-141">Open your VSTS account and project, which is something like *https://YourAccountName.visualstudio.com/MyFirstProject*.</span></span> <span data-ttu-id="c100c-142">Seleccione el icono de configuración y seleccione **agente colas**:</span><span class="sxs-lookup"><span data-stu-id="c100c-142">Select the settings icon, and select **Agent Queues**:</span></span>  

    ![Configuración > colas de agente](../core/media/vsts-settings-agent-queues.png)

2. <span data-ttu-id="c100c-144">Seleccione el **predeterminado** agente y seleccione **descargar agente**.</span><span class="sxs-lookup"><span data-stu-id="c100c-144">Select the **Default** agent, and select **Download Agent**.</span></span> <span data-ttu-id="c100c-145">Seleccione el **descargar** botón y guarde el archivo para su **descarga** carpetas.</span><span class="sxs-lookup"><span data-stu-id="c100c-145">Select the **Download** button, and save the file to your **Downloads** folders.</span></span>

3. <span data-ttu-id="c100c-146">Los pasos de instalación se abrirán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c100c-146">The install steps automatically open.</span></span> <span data-ttu-id="c100c-147">Siga estos pasos para obtener la información más actualizada.</span><span class="sxs-lookup"><span data-stu-id="c100c-147">Follow those steps for the most up-to-date details.</span></span> <span data-ttu-id="c100c-148">Aquí tiene algunas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="c100c-148">Here is some guidance:</span></span> 

    1. <span data-ttu-id="c100c-149">Abra Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="c100c-149">Open Windows PowerShell as Administrator.</span></span>

    2. <span data-ttu-id="c100c-150">Para crear al agente, escriba:</span><span class="sxs-lookup"><span data-stu-id="c100c-150">To create the agent, enter:</span></span> 

        ```powershell
        PS C:\> mkdir agent ; cd agent  

        PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
        ```
    
        <span data-ttu-id="c100c-151">Los cambios de versión del archivo de vsts-agent.</span><span class="sxs-lookup"><span data-stu-id="c100c-151">The vsts-agent file version changes.</span></span> <span data-ttu-id="c100c-152">Por lo tanto, siga los pasos de instalación VSTS para obtener detalles específicos.</span><span class="sxs-lookup"><span data-stu-id="c100c-152">So follow the VSTS install steps for specific details.</span></span> <span data-ttu-id="c100c-153">Después de llegar a escribir, puede tardar unos minutos para el símbolo del sistema devolver.</span><span class="sxs-lookup"><span data-stu-id="c100c-153">After you hit enter, it may take a couple of minutes for the prompt to return.</span></span> 

    3. <span data-ttu-id="c100c-154">Para configurar al agente, escriba:</span><span class="sxs-lookup"><span data-stu-id="c100c-154">To configure the agent, enter:</span></span> 

        ```powershell
        PS C:\agent> .\config.cmd
        ```

    4. <span data-ttu-id="c100c-155">Escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c100c-155">Enter the following details:</span></span>  
        
        | <span data-ttu-id="c100c-156">Propiedad</span><span class="sxs-lookup"><span data-stu-id="c100c-156">Property</span></span> | <span data-ttu-id="c100c-157">Valor</span><span class="sxs-lookup"><span data-stu-id="c100c-157">Value</span></span> |
        | --- | --- |
        | <span data-ttu-id="c100c-158">Dirección URL del servidor</span><span class="sxs-lookup"><span data-stu-id="c100c-158">Server URL</span></span>| <span data-ttu-id="c100c-159">https://{Your-Account}.VisualStudio.com</span><span class="sxs-lookup"><span data-stu-id="c100c-159">https://{your-account}.visualstudio.com</span></span> |
        | <span data-ttu-id="c100c-160">Tipo de autenticación</span><span class="sxs-lookup"><span data-stu-id="c100c-160">Authentication Type</span></span> | <span data-ttu-id="c100c-161">NURIA</span><span class="sxs-lookup"><span data-stu-id="c100c-161">PAT</span></span> |
        | <span data-ttu-id="c100c-162">Token de acceso personal</span><span class="sxs-lookup"><span data-stu-id="c100c-162">Personal access token</span></span> | <span data-ttu-id="c100c-163">Pegue el token VSTS</span><span class="sxs-lookup"><span data-stu-id="c100c-163">Paste your VSTS token</span></span> |
        | <span data-ttu-id="c100c-164">Grupo de agente</span><span class="sxs-lookup"><span data-stu-id="c100c-164">Agent pool</span></span> | <span data-ttu-id="c100c-165">Escriba para el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="c100c-165">Enter for the default</span></span> |
        | <span data-ttu-id="c100c-166">Nombre del agente</span><span class="sxs-lookup"><span data-stu-id="c100c-166">Agent name</span></span> | <span data-ttu-id="c100c-167">Escriba para el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="c100c-167">Enter for the default</span></span> |
        | <span data-ttu-id="c100c-168">Reemplazar</span><span class="sxs-lookup"><span data-stu-id="c100c-168">Replace</span></span> | <span data-ttu-id="c100c-169">*Solo se muestran si tiene un agente existente*</span><span class="sxs-lookup"><span data-stu-id="c100c-169">*Only displays if you have an existing agent*</span></span> |
        | <span data-ttu-id="c100c-170">Carpeta de trabajo</span><span class="sxs-lookup"><span data-stu-id="c100c-170">Work folder</span></span> | <span data-ttu-id="c100c-171">Escriba para el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="c100c-171">Enter for the default</span></span> |
        | <span data-ttu-id="c100c-172">Ejecutar a agente como un servicio</span><span class="sxs-lookup"><span data-stu-id="c100c-172">Run agent as a service</span></span> | <span data-ttu-id="c100c-173">S</span><span class="sxs-lookup"><span data-stu-id="c100c-173">Y</span></span> |
        | <span data-ttu-id="c100c-174">Cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="c100c-174">User account</span></span> | <span data-ttu-id="c100c-175">Esto depende de usted, pero puede encontrarse con un problema de permisos.</span><span class="sxs-lookup"><span data-stu-id="c100c-175">This is up to you, but you may run into a permissions issue.</span></span> <br/><br/><span data-ttu-id="c100c-176">Considere la posibilidad de escribir su actual cuenta con sesión iniciada, que es un administrador local.</span><span class="sxs-lookup"><span data-stu-id="c100c-176">Consider entering your current logged-on account, which is a local Admin.</span></span> |

    5. <span data-ttu-id="c100c-177">Cuando termine, la ventana de PowerShell es similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c100c-177">When finished, your PowerShell window looks like the following:</span></span>  
    
        ![Instalación del agente](../core/media/vsts-agent-powershell-install.png)

4. <span data-ttu-id="c100c-179">Abra services.msc para ver el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="c100c-179">Open services.msc to see the new service.</span></span> <span data-ttu-id="c100c-180">Debe estar ejecutando:</span><span class="sxs-lookup"><span data-stu-id="c100c-180">It should be running:</span></span>  

    ![Servicio se está ejecutando](../core/media/vsts-service.png)

    <span data-ttu-id="c100c-182">Si el servicio no se inicia, [quitar y volver a configurar un agente](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) con una cuenta con más privilegios.</span><span class="sxs-lookup"><span data-stu-id="c100c-182">If the service fails to start, [remove and re-configure an agent](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) using an account with more privilages.</span></span>


## <a name="what-you-did"></a><span data-ttu-id="c100c-183">Lo que hizo</span><span class="sxs-lookup"><span data-stu-id="c100c-183">What you did</span></span>

<span data-ttu-id="c100c-184">Que se inicie sesión en su cuenta VSTS y ha creado un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c100c-184">You signed into your VSTS account, and created a security token.</span></span> <span data-ttu-id="c100c-185">Este token de seguridad es como una contraseña y le da acceso a su proyecto VSTS.</span><span class="sxs-lookup"><span data-stu-id="c100c-185">This security token is like a password, and gives you access to your VSTS project.</span></span> <span data-ttu-id="c100c-186">Solo se muestra una vez, por lo que estar seguro de que ha guardado.</span><span class="sxs-lookup"><span data-stu-id="c100c-186">It's only displayed once, so be sure you saved it.</span></span> <span data-ttu-id="c100c-187">También clona el proyecto VSTS en Visual Studio y crear a un agente que se ejecuta como un servicio en el equipo de desarrollo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c100c-187">You also cloned your VSTS project into Visual Studio, and created an agent that runs as a service on your BizTalk development computer.</span></span> <span data-ttu-id="c100c-188">Este agente utiliza el token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c100c-188">This agent uses the security token.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="c100c-189">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c100c-189">Next steps</span></span>
[<span data-ttu-id="c100c-190">Paso 3: Crear la compilación y las definiciones de la versión</span><span class="sxs-lookup"><span data-stu-id="c100c-190">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="c100c-191">Configurar las variables y tokens de entorno</span><span class="sxs-lookup"><span data-stu-id="c100c-191">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)