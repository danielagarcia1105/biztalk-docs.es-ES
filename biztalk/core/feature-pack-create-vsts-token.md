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
# <a name="step-2-create-the-token--install-the-agent"></a>Paso 2: Crear el token e instalar el agente

Se crea un token de acceso personal (PAT) en Visual Studio Team Services. Este token es su contraseña y se usa el agente de compilación VSTS para autenticar. El token solo se muestra al crearla. Después de eso, no se muestra ya. Así que después de crearlo, guardarlo en otro archivo en una ubicación capaz de recordar. 

Obtener más información sobre PAT en [autenticar el acceso con tokens de acceso personal para VSTS y TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate). 

Después de crear el token, instale al agente de compilación y configúrelo para utilizar este token. 

## <a name="before-you-begin"></a>Antes de comenzar
Completa [paso 1: proyecto de aplicación agregue y actualice los json](feature-pack-add-application-project.md).

## <a name="sign-into-vsts-and-create-the-token"></a>Inicie sesión en VSTS y crear el token
1. Vaya a [ https://app.vsaex.visualstudio.com/go/profile ](https://app.vsaex.visualstudio.com/go/profile)e inicie sesión con su cuenta profesional o educativa. Después de iniciar sesión, se muestra la cuenta de VSTS. En el ejemplo siguiente, la cuenta es **mandiaprojects.visualstudio.com**.  

    ![Cuenta de VSTS](../core/media/team-services-accounts.png)

    Si no tiene una cuenta, seleccione **crear nueva cuenta**y escriba un nombre. Para administrar el código, elija su preferencia personal entre **Git o Team Foundation Version Control**. Cuando termine, se crea la nueva cuenta y un sitio similar a *https://YourAccountName.visualstudio.com/MyFirstProject* abre:  

    ![GIT o TFS](../core/media/git-or-team-foundation.png)

2. Abra su cuenta de VSTS (https://<em>YourAccountName</em>. visualstudio.com). Seleccione el icono en la parte superior derecha y seleccione **seguridad**: 

    ![Abra la seguridad de la cuenta](../core/media/vsts-account-security.png)

3. **Tokens de acceso personal** se abre automáticamente. Si tiene un agente existente, selecciónelo y confirmar **grupos de agentes (leer, administrar)** está seleccionado:

    ![-Grupos de agentes de lectura y administración](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > Debe conocer el token de acceso. Si no y no tenga en cuenta en cualquier lugar, no se puede recuperar. En esta situación, cree a un nuevo agente. 

    Si no tiene un agente existente, seleccione **agregar**, escriba una descripción, establecer la fecha de expiración y seleccione su cuenta. En **seleccionado ámbitos**, seleccione **grupos de agentes (leer, administrar)**: 

    ![Crear a nuevo agente: leer y administrar](../core/media/vsts-new-build-agent.png)

    Seleccione **crear Token**. **Tenga en cuenta el valor del token; se necesita en el futuro de pasos.**

4. Seleccione **código**y seleccione **clonar en Visual Studio**:  

    ![En el proyecto, seleccione el código](../core/media/vsts-project-code.png)  

    ![Clonar en Visual Studio](../core/media/vsts-clone-in-visual-studio.png)

5. Se abre Visual Studio. En Visual Studio, abra la solución de BizTalk. 

## <a name="install-the-build-agent"></a>Instalar al agente de compilación

El agente de compilación está instalado en el equipo de desarrollo de BizTalk. Si usa grupos de implementación, el agente de compilación se instala en todos los servidores de BizTalk que desea implementar en. Los pasos siguientes muestran cómo instalar al agente de compilación en un único equipo. Para obtener más información sobre el uso de grupos de implementación, consulte [grupos de implementación](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index).

1. Abra su cuenta de VSTS y un proyecto, que es algo como *https://YourAccountName.visualstudio.com/MyFirstProject*. Seleccione el icono de configuración y seleccione **colas de agentes**:  

    ![Configuración > colas de agentes](../core/media/vsts-settings-agent-queues.png)

2. Seleccione el **predeterminado** agente y seleccione **descargar agente**. Seleccione el **descargar** botón y guarde el archivo para su **descargas** carpetas.

3. Los pasos de instalación se abrirán automáticamente. Siga estos pasos para la información más actualizada. Aquí tiene algunas instrucciones: 

   1. Abra Windows PowerShell como administrador.

   2. Para crear al agente, escriba: 

       ```powershell
       PS C:\> mkdir agent ; cd agent  

       PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
       ```

       Los cambios de versión del archivo de agente de vsts. Por lo tanto, siga los pasos de instalación VSTS para obtener detalles concretos. Una vez alcanzado escriba, puede tardar unos minutos para el símbolo del sistema devolver. 

   3. Para configurar al agente, escriba: 

       ```powershell
       PS C:\agent> .\config.cmd
       ```

   4. Escriba la siguiente información:  


      |        Property        |                                                                      Valor                                                                       |
      |------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
      |       Dirección URL del servidor       |                                                     https://{Your-Account}.VisualStudio.com                                                      |
      |  Tipo de autenticación   |                                                                       PAT                                                                        |
      | Token de acceso personal  |                                                              Pegue el token VSTS                                                               |
      |       Grupo de agentes       |                                                              Escriba el valor predeterminado                                                               |
      |       Nombre del agente       |                                                              Escriba el valor predeterminado                                                               |
      |        Reemplazar         |                                                  *Muestra solo si tiene un agente existente*                                                   |
      |      Carpeta de trabajo       |                                                              Escriba el valor predeterminado                                                               |
      | Ejecutar a agente como un servicio |                                                                        S                                                                         |
      |      Cuenta de usuario      | Esto depende de usted, pero experimenta un problema de permisos. <br/><br/>Considere la posibilidad de escribir su actual ha iniciado la sesión cuenta, que es un administrador local. |


   5. Cuando termine, la ventana de PowerShell es similar a la siguiente:  

       ![Instalación del agente](../core/media/vsts-agent-powershell-install.png)

4. Abra services.msc para ver el nuevo servicio. Debe estar ejecutando:  

    ![Se está ejecutando el servicio](../core/media/vsts-service.png)

    Si el servicio no se inicia, [quitar y volver a configurar un agente](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) con una cuenta con más privilegios.


## <a name="what-you-did"></a>Lo que hizo

Se ha iniciado sesión en su cuenta de VSTS y crea un token de seguridad. Este token de seguridad es como una contraseña y proporciona acceso a su proyecto de VSTS. Solo se muestra una vez, por lo que se está seguro de que lo ha guardado. También clona el proyecto de VSTS en Visual Studio y crea a un agente que se ejecuta como un servicio en el equipo de desarrollo de BizTalk. Este agente utiliza el token de seguridad. 

## <a name="next-steps"></a>Pasos siguientes
[Paso 3: Crear la compilación y definiciones de versión](feature-pack-add-build-release-definitions.md)  
[Configurar las variables y los tokens de entorno](configure-environmental-tokens-and-variables-for-automatic-deployment.md)