---
title: 'Paso 2: crear el token VSTS e instale el agente | Documentos de Microsoft'
description: Crear el clon de símbolo (token), de acceso de seguridad VSTS el proyecto VSTS en Visual Studio e instalar el agente de compilación para automatizar la implementación de los proyectos de BizTalk Server
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
ms.openlocfilehash: 77296d9f2325bebaba4f4fa1ce7c55034ef1ead6
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
ms.locfileid: "25497693"
---
# <a name="step-2-create-the-token--install-the-agent"></a><span data-ttu-id="a4bd8-103">Paso 2: Crear el token e instalar el agente</span><span class="sxs-lookup"><span data-stu-id="a4bd8-103">Step 2: Create the token & install the agent</span></span>

<span data-ttu-id="a4bd8-104">Se crea un token de acceso personal (PAT) en Visual Studio Team Services.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-104">A personal access token (PAT) is created in Visual Studio Team Services.</span></span> <span data-ttu-id="a4bd8-105">Este token es su contraseña y es utilizado por el agente de compilación VSTS para autenticar.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-105">This token is your password, and is used by the VSTS build agent to authenticate.</span></span> <span data-ttu-id="a4bd8-106">El token solo se muestra cuando la cree.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-106">The token is only displayed when you create it.</span></span> <span data-ttu-id="a4bd8-107">Después de eso, no se muestra ya.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-107">After that, it isn't displayed anymore.</span></span> <span data-ttu-id="a4bd8-108">Por lo que una vez creada, guardarlo en otro archivo en una ubicación capaz de recordar.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-108">So once you create it, save it to another file in a remember-able location.</span></span> 

<span data-ttu-id="a4bd8-109">Obtener más información sobre PAT en [autenticar el acceso con tokens de acceso personal para VSTS y TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span><span class="sxs-lookup"><span data-stu-id="a4bd8-109">More info on PAT at [Authenticate access with personal access tokens for VSTS and TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span></span> 

<span data-ttu-id="a4bd8-110">Después de crear el token, instalar al agente de compilación y configúrelo para utilizar este token.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-110">After you create the token, you install the build agent, and configure it to use this token.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="a4bd8-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="a4bd8-111">Before you begin</span></span>
<span data-ttu-id="a4bd8-112">Completa [paso 1: proyecto de aplicación para agregar y actualizar json](feature-pack-add-application-project.md).</span><span class="sxs-lookup"><span data-stu-id="a4bd8-112">Complete [Step 1 - Add Application project and update json](feature-pack-add-application-project.md).</span></span>

## <a name="sign-into-vsts-and-create-the-token"></a><span data-ttu-id="a4bd8-113">Iniciar sesión en VSTS y crear el token</span><span class="sxs-lookup"><span data-stu-id="a4bd8-113">Sign into VSTS, and create the token</span></span>
1. <span data-ttu-id="a4bd8-114">Vaya a [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile)e inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-114">Go to [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile), and sign-in with your work or school account.</span></span> <span data-ttu-id="a4bd8-115">Después de iniciar la sesión, se muestra la cuenta VSTS.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-115">After you sign in, your VSTS account is listed.</span></span> <span data-ttu-id="a4bd8-116">En el ejemplo siguiente, la cuenta es **mandiaprojects.visualstudio.com**.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-116">In the following example, the account is **mandiaprojects.visualstudio.com**.</span></span>  

    ![Cuenta VSTS](../core/media/team-services-accounts.png)

    <span data-ttu-id="a4bd8-118">Si no tiene una cuenta, seleccione **crear nueva cuenta**y escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-118">If you don’t have an account, select **Create new account**, and enter a name.</span></span> <span data-ttu-id="a4bd8-119">Para administrar el código, elija su preferencia personal entre **Git o Team Foundation Version Control**.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-119">To manage your code, choose your personal preference between **Git or Team Foundation Version Control**.</span></span> <span data-ttu-id="a4bd8-120">Cuando termine, se crea la nueva cuenta y un sitio similar a *https://YourAccountName.visualstudio.com/MyFirstProject* abre:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-120">When finished, your new account is created, and a site similar to *https://YourAccountName.visualstudio.com/MyFirstProject* opens:</span></span>  

    ![GIT o TFS](../core/media/git-or-team-foundation.png)

2. <span data-ttu-id="a4bd8-122">Abra su cuenta VSTS (https://*YourAccountName*. visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="a4bd8-122">Open your VSTS account (https://*YourAccountName*.visualstudio.com).</span></span> <span data-ttu-id="a4bd8-123">Seleccione el icono en la esquina superior de la derecha y seleccione **seguridad**:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-123">Select your icon in the top right-side corner, and select **Security**:</span></span> 

    ![Abra la seguridad de la cuenta](../core/media/vsts-account-security.png)

3. <span data-ttu-id="a4bd8-125">**Tokens de acceso personal** se abre automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-125">**Personal access tokens** automatically opens.</span></span> <span data-ttu-id="a4bd8-126">Si tiene un agente existente, selecciónelo y confirmar **grupos de agente (lectura, administrar)** está seleccionado:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-126">If you have an existing agent, select it, and confirm **Agent Pools (read, manage)** is selected:</span></span>

    ![Grupos de agente: lectura y administración](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > <span data-ttu-id="a4bd8-128">Debe conocer el token de acceso.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-128">You must know the access token.</span></span> <span data-ttu-id="a4bd8-129">Si no y no tenga en cuenta en cualquier lugar, no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-129">If you don’t, and didn’t note it anywhere, it cannot be retrieved.</span></span> <span data-ttu-id="a4bd8-130">En esta situación, cree a un nuevo agente.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-130">In this situation, create a new agent.</span></span> 

    <span data-ttu-id="a4bd8-131">Si no tiene un agente existente, seleccione **agregar**, escriba una descripción, establecer la fecha de expiración y seleccione su cuenta.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-131">If you don’t have an existing agent, select **Add**, enter a description, set the expiration date, and select your account.</span></span> <span data-ttu-id="a4bd8-132">En **seleccionado ámbitos**, seleccione **grupos de agente (lectura, administrar)**:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-132">In **Selected scopes**, select **Agent Pools (read, manage)**:</span></span> 

    ![Crear a nuevo agente: leer y administrar](../core/media/vsts-new-build-agent.png)

    <span data-ttu-id="a4bd8-134">Seleccione **crear Token**.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-134">Select **Create Token**.</span></span> <span data-ttu-id="a4bd8-135">**Tenga en cuenta el valor del token; en el futuro necesita pasos.**</span><span class="sxs-lookup"><span data-stu-id="a4bd8-135">**Note the token value; you need in future steps.**</span></span>

4. <span data-ttu-id="a4bd8-136">Seleccione **código**y seleccione **clon en Visual Studio**:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-136">Select **Code**, and select **Clone in Visual Studio**:</span></span>  

    ![En el proyecto, seleccione el código](../core/media/vsts-project-code.png)  

    ![Clonar en Visual Studio](../core/media/vsts-clone-in-visual-studio.png)

5. <span data-ttu-id="a4bd8-139">Visual Studio abre.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-139">Visual Studio opens.</span></span> <span data-ttu-id="a4bd8-140">En Visual Studio, abra la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-140">Within Visual Studio, open your BizTalk solution.</span></span> 

## <a name="install-the-build-agent"></a><span data-ttu-id="a4bd8-141">Instalar al agente de compilación</span><span class="sxs-lookup"><span data-stu-id="a4bd8-141">Install the Build Agent</span></span>

<span data-ttu-id="a4bd8-142">El agente de compilación está instalado en el equipo de desarrollo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-142">The build agent is installed on the BizTalk development computer.</span></span> <span data-ttu-id="a4bd8-143">Si utiliza grupos de implementación, el agente de compilación se instala en todos los servidores de BizTalk que desea implementar en.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-143">If using deployment groups, the build agent is installed on all the BizTalk servers you want to deploy to.</span></span> <span data-ttu-id="a4bd8-144">Los pasos siguientes muestran cómo instalar al agente de compilación en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-144">The following steps show you how to install the build agent on a single computer.</span></span> <span data-ttu-id="a4bd8-145">Para obtener más información sobre el uso de grupos de implementación, consulte [grupos de implementación](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index).</span><span class="sxs-lookup"><span data-stu-id="a4bd8-145">For details on using deployment groups, see [Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index).</span></span>

1. <span data-ttu-id="a4bd8-146">Abra su cuenta VSTS y el proyecto, que es algo como *https://YourAccountName.visualstudio.com/MyFirstProject*.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-146">Open your VSTS account and project, which is something like *https://YourAccountName.visualstudio.com/MyFirstProject*.</span></span> <span data-ttu-id="a4bd8-147">Seleccione el icono de configuración y seleccione **agente colas**:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-147">Select the settings icon, and select **Agent Queues**:</span></span>  

    ![Configuración > colas de agente](../core/media/vsts-settings-agent-queues.png)

2. <span data-ttu-id="a4bd8-149">Seleccione el **predeterminado** agente y seleccione **descargar agente**.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-149">Select the **Default** agent, and select **Download Agent**.</span></span> <span data-ttu-id="a4bd8-150">Seleccione el **descargar** botón y guarde el archivo para su **descarga** carpetas.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-150">Select the **Download** button, and save the file to your **Downloads** folders.</span></span>

3. <span data-ttu-id="a4bd8-151">Los pasos de instalación se abrirán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-151">The install steps automatically open.</span></span> <span data-ttu-id="a4bd8-152">Siga estos pasos para obtener la información más actualizada.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-152">Follow those steps for the most up-to-date details.</span></span> <span data-ttu-id="a4bd8-153">Aquí tiene algunas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-153">Here is some guidance:</span></span> 

    1. <span data-ttu-id="a4bd8-154">Abra Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-154">Open Windows PowerShell as Administrator.</span></span>

    2. <span data-ttu-id="a4bd8-155">Para crear al agente, escriba:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-155">To create the agent, enter:</span></span> 

        ```powershell
        PS C:\> mkdir agent ; cd agent  

        PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
        ```
    
        <span data-ttu-id="a4bd8-156">Los cambios de versión del archivo de vsts-agent.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-156">The vsts-agent file version changes.</span></span> <span data-ttu-id="a4bd8-157">Por lo tanto, siga los pasos de instalación VSTS para obtener detalles específicos.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-157">So follow the VSTS install steps for specific details.</span></span> <span data-ttu-id="a4bd8-158">Después de llegar a escribir, puede tardar unos minutos para el símbolo del sistema devolver.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-158">After you hit enter, it may take a couple of minutes for the prompt to return.</span></span> 

    3. <span data-ttu-id="a4bd8-159">Para configurar al agente, escriba:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-159">To configure the agent, enter:</span></span> 

        ```powershell
        PS C:\agent> .\config.cmd
        ```

    4. <span data-ttu-id="a4bd8-160">Escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-160">Enter the following details:</span></span>  
        
        | <span data-ttu-id="a4bd8-161">Propiedad</span><span class="sxs-lookup"><span data-stu-id="a4bd8-161">Property</span></span> | <span data-ttu-id="a4bd8-162">Valor</span><span class="sxs-lookup"><span data-stu-id="a4bd8-162">Value</span></span> |
        | --- | --- |
        | <span data-ttu-id="a4bd8-163">Dirección URL del servidor</span><span class="sxs-lookup"><span data-stu-id="a4bd8-163">Server URL</span></span>| <span data-ttu-id="a4bd8-164">https://{Your-Account}.VisualStudio.com</span><span class="sxs-lookup"><span data-stu-id="a4bd8-164">https://{your-account}.visualstudio.com</span></span> |
        | <span data-ttu-id="a4bd8-165">Tipo de autenticación</span><span class="sxs-lookup"><span data-stu-id="a4bd8-165">Authentication Type</span></span> | <span data-ttu-id="a4bd8-166">NURIA</span><span class="sxs-lookup"><span data-stu-id="a4bd8-166">PAT</span></span> |
        | <span data-ttu-id="a4bd8-167">Token de acceso personal</span><span class="sxs-lookup"><span data-stu-id="a4bd8-167">Personal access token</span></span> | <span data-ttu-id="a4bd8-168">Pegue el token VSTS</span><span class="sxs-lookup"><span data-stu-id="a4bd8-168">Paste your VSTS token</span></span> |
        | <span data-ttu-id="a4bd8-169">Grupo de agente</span><span class="sxs-lookup"><span data-stu-id="a4bd8-169">Agent pool</span></span> | <span data-ttu-id="a4bd8-170">Escriba para el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="a4bd8-170">Enter for the default</span></span> |
        | <span data-ttu-id="a4bd8-171">Nombre del agente</span><span class="sxs-lookup"><span data-stu-id="a4bd8-171">Agent name</span></span> | <span data-ttu-id="a4bd8-172">Escriba para el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="a4bd8-172">Enter for the default</span></span> |
        | <span data-ttu-id="a4bd8-173">Reemplazar</span><span class="sxs-lookup"><span data-stu-id="a4bd8-173">Replace</span></span> | <span data-ttu-id="a4bd8-174">*Solo se muestran si tiene un agente existente*</span><span class="sxs-lookup"><span data-stu-id="a4bd8-174">*Only displays if you have an existing agent*</span></span> |
        | <span data-ttu-id="a4bd8-175">Carpeta de trabajo</span><span class="sxs-lookup"><span data-stu-id="a4bd8-175">Work folder</span></span> | <span data-ttu-id="a4bd8-176">Escriba para el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="a4bd8-176">Enter for the default</span></span> |
        | <span data-ttu-id="a4bd8-177">Ejecutar a agente como un servicio</span><span class="sxs-lookup"><span data-stu-id="a4bd8-177">Run agent as a service</span></span> | <span data-ttu-id="a4bd8-178">S</span><span class="sxs-lookup"><span data-stu-id="a4bd8-178">Y</span></span> |
        | <span data-ttu-id="a4bd8-179">Cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="a4bd8-179">User account</span></span> | <span data-ttu-id="a4bd8-180">Esto depende de usted, pero puede encontrarse con un problema de permisos.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-180">This is up to you, but you may run into a permissions issue.</span></span> <br/><br/><span data-ttu-id="a4bd8-181">Considere la posibilidad de escribir su actual cuenta con sesión iniciada, que es un administrador local.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-181">Consider entering your current logged-on account, which is a local Admin.</span></span> |

    5. <span data-ttu-id="a4bd8-182">Cuando termine, la ventana de PowerShell es similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-182">When finished, your PowerShell window looks like the following:</span></span>  
    
        ![Instalación del agente](../core/media/vsts-agent-powershell-install.png)

4. <span data-ttu-id="a4bd8-184">Abra services.msc para ver el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-184">Open services.msc to see the new service.</span></span> <span data-ttu-id="a4bd8-185">Debe estar ejecutando:</span><span class="sxs-lookup"><span data-stu-id="a4bd8-185">It should be running:</span></span>  

    ![Servicio se está ejecutando](../core/media/vsts-service.png)

    <span data-ttu-id="a4bd8-187">Si el servicio no se inicia, [quitar y volver a configurar un agente](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) con una cuenta con más privilegios.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-187">If the service fails to start, [remove and re-configure an agent](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) using an account with more privilages.</span></span>


## <a name="what-you-did"></a><span data-ttu-id="a4bd8-188">Lo que hizo</span><span class="sxs-lookup"><span data-stu-id="a4bd8-188">What you did</span></span>

<span data-ttu-id="a4bd8-189">Que se inicie sesión en su cuenta VSTS y ha creado un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-189">You signed into your VSTS account, and created a security token.</span></span> <span data-ttu-id="a4bd8-190">Este token de seguridad es como una contraseña y le da acceso a su proyecto VSTS.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-190">This security token is like a password, and gives you access to your VSTS project.</span></span> <span data-ttu-id="a4bd8-191">Solo se muestra una vez, por lo que estar seguro de que ha guardado.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-191">It's only displayed once, so be sure you saved it.</span></span> <span data-ttu-id="a4bd8-192">También clona el proyecto VSTS en Visual Studio y crear a un agente que se ejecuta como un servicio en el equipo de desarrollo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-192">You also cloned your VSTS project into Visual Studio, and created an agent that runs as a service on your BizTalk development computer.</span></span> <span data-ttu-id="a4bd8-193">Este agente utiliza el token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a4bd8-193">This agent uses the security token.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a4bd8-194">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a4bd8-194">Next steps</span></span>
[<span data-ttu-id="a4bd8-195">Paso 3: Crear la compilación y las definiciones de la versión</span><span class="sxs-lookup"><span data-stu-id="a4bd8-195">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="a4bd8-196">Configurar las variables y tokens de entorno</span><span class="sxs-lookup"><span data-stu-id="a4bd8-196">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)