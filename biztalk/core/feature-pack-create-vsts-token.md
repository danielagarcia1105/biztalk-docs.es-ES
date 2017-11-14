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
# <a name="step-2-create-the-token--install-the-agent"></a>Paso 2: Crear el token e instalar el agente

Se crea un token de acceso personal (PAT) en Visual Studio Team Services. Este token es su contraseña y es utilizado por el agente de compilación VSTS para autenticar. El token solo se muestra cuando la cree. Después de eso, no se muestra ya. Por lo que una vez creada, guardarlo en otro archivo en una ubicación capaz de recordar. 

Obtener más información sobre PAT en [autenticar el acceso con tokens de acceso personal para VSTS y TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate). 

Después de crear el token, instalar al agente de compilación y configúrelo para utilizar este token. 

## <a name="sign-into-vsts-and-create-the-token"></a>Iniciar sesión en VSTS y crear el token
1. Vaya a [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile)e inicie sesión con su cuenta profesional o educativa. Después de iniciar la sesión, se muestra la cuenta VSTS. En el ejemplo siguiente, la cuenta es **mandiaprojects.visualstudio.com**.  

    ![Cuenta VSTS](../core/media/team-services-accounts.png)

    Si no tiene una cuenta, seleccione **crear nueva cuenta**y escriba un nombre. Para administrar el código, elija su preferencia personal entre **Git o Team Foundation Version Control**. Cuando termine, se crea la nueva cuenta y un sitio similar a *https://YourAccountName.visualstudio.com/MyFirstProject* abre:  

    ![GIT o TFS](../core/media/git-or-team-foundation.png)

2. Abra su cuenta VSTS (https://*YourAccountName*. visualstudio.com). Seleccione el icono en la esquina superior de la derecha y seleccione **seguridad**: 

    ![Abra la seguridad de la cuenta](../core/media/vsts-account-security.png)

3. **Tokens de acceso personal** se abre automáticamente. Si tiene un agente existente, selecciónelo y confirmar **grupos de agente (lectura, administrar)** está seleccionado:

    ![Grupos de agente: lectura y administración](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > Debe conocer el token de acceso. Si no y no tenga en cuenta en cualquier lugar, no se puede recuperar. En esta situación, cree a un nuevo agente. 

    Si no tiene un agente existente, seleccione **agregar**, escriba una descripción, establecer la fecha de expiración y seleccione su cuenta. En **seleccionado ámbitos**, seleccione **grupos de agente (lectura, administrar)**: 

    ![Crear a nuevo agente: leer y administrar](../core/media/vsts-new-build-agent.png)

    Seleccione **crear Token**. **Tenga en cuenta el valor del token; en el futuro necesita pasos.**

4. Seleccione **código**y seleccione **clon en Visual Studio**:  

    ![En el proyecto, seleccione el código](../core/media/vsts-project-code.png)  

    ![Clonar en Visual Studio](../core/media/vsts-clone-in-visual-studio.png)

5. Visual Studio abre. En Visual Studio, abra la solución de BizTalk. 

## <a name="install-the-build-agent"></a>Instalar al agente de compilación

El agente de compilación está instalado en el equipo de desarrollo de BizTalk. 

1. Abra su cuenta VSTS y el proyecto, que es algo como *https://YourAccountName.visualstudio.com/MyFirstProject*. Seleccione el icono de configuración y seleccione **agente colas**:  

    ![Configuración > colas de agente](../core/media/vsts-settings-agent-queues.png)

2. Seleccione el **predeterminado** agente y seleccione **descargar agente**. Seleccione el **descargar** botón y guarde el archivo para su **descarga** carpetas.

3. Los pasos de instalación se abrirán automáticamente. Siga estos pasos para obtener la información más actualizada. Aquí tiene algunas instrucciones: 

    1. Abra Windows PowerShell como administrador.

    2. Para crear al agente, escriba: 

        ```powershell
        PS C:\> mkdir agent ; cd agent  

        PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
        ```
    
        Los cambios de versión del archivo de vsts-agent. Por lo tanto, siga los pasos de instalación VSTS para obtener detalles específicos. Después de llegar a escribir, puede tardar unos minutos para el símbolo del sistema devolver. 

    3. Para configurar al agente, escriba: 

        ```powershell
        PS C:\agent> .\config.cmd
        ```

    4. Escriba la siguiente información:  
        
        | Propiedad | Valor |
        | --- | --- |
        | Dirección URL del servidor| https://{Your-Account}.VisualStudio.com |
        | Tipo de autenticación | NURIA |
        | Token de acceso personal | Pegue el token VSTS |
        | Grupo de agente | Escriba para el valor predeterminado |
        | Nombre del agente | Escriba para el valor predeterminado |
        | Reemplazar | *Solo se muestran si tiene un agente existente* |
        | Carpeta de trabajo | Escriba para el valor predeterminado |
        | Ejecutar a agente como un servicio | S |
        | Cuenta de usuario | Esto depende de usted, pero puede encontrarse con un problema de permisos. <br/><br/>Considere la posibilidad de escribir su actual cuenta con sesión iniciada, que es un administrador local. |

    5. Cuando termine, la ventana de PowerShell es similar a la siguiente:  
    
        ![Instalación del agente](../core/media/vsts-agent-powershell-install.png)

4. Abra services.msc para ver el nuevo servicio. Debe estar ejecutando:  

    ![Servicio se está ejecutando](../core/media/vsts-service.png)

    Si el servicio no se inicia, [quitar y volver a configurar un agente](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) con una cuenta con más privilegios.


## <a name="what-you-did"></a>Lo que hizo

Que se inicie sesión en su cuenta VSTS y ha creado un token de seguridad. Este token de seguridad es como una contraseña y le da acceso a su proyecto VSTS. Solo se muestra una vez, por lo que estar seguro de que ha guardado. También clona el proyecto VSTS en Visual Studio y crear a un agente que se ejecuta como un servicio en el equipo de desarrollo de BizTalk. Este agente utiliza el token de seguridad. 

## <a name="next-steps"></a>Pasos siguientes
[Paso 3: Crear la compilación y las definiciones de la versión](feature-pack-add-build-release-definitions.md)  
[Configurar las variables y tokens de entorno](configure-environmental-tokens-and-variables-for-automatic-deployment.md)