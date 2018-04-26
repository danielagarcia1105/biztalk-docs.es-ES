---
title: 'Paso 1: Agregar aplicación json de proyecto y actualice | Documentos de Microsoft'
description: Agregue el proyecto de aplicación de BizTalk Server en Visual Studio y actualizar el archivo BizTalkServerInventory.json con los archivos DLL, archivos de enlace y la secuencia de implementación de las aplicaciones - Visual Studio Team Services
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
ms.openlocfilehash: da1c4bb3cb12cf67e84bab7aa7f38c1a893eca00
ms.sourcegitcommit: 770523695b34cc54db81f7ab7eba46f2bc19baec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a>Paso 1: Agregar el proyecto de aplicación de BizTalk Server en Visual Studio

Al compilar las aplicaciones mediante Visual Studio Team Services, se crea un nuevo archivo de proyecto de BizTalk: .btaproj. Este nuevo proyecto contiene todas las aplicaciones de BizTalk de compilación y la implementación con la compilación VSTS y características de la versión. 

El proyecto de aplicación de BizTalk incluye la `BizTalkServerInventory.json` archivo. En este archivo, agregue los ensamblados de BizTalk, agregue los archivos de enlace de la aplicación de BizTalk y, a continuación, establezca una secuencia de implementación. 

## <a name="before-you-begin"></a>Antes de empezar

* Estos pasos se supone que tiene un proyecto de BizTalk existente. Si no es así, puede usar el ejemplo HelloWorld SDK (\Program Files (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld). 
* Tiene la ruta de acceso al archivo de enlace XML al proyecto de BizTalk listo. 
* Conocer su cuenta VSTS, la colección y los detalles del proyecto de equipo.
* Estar familiarizado con conceptos de git, incluye la clonación y el trabajo con repositorios. 
* Asegúrese de [Feature Pack 2](https://aka.ms/bts2016fp2) está instalado.

## <a name="add-the-application-project"></a>Agregue el proyecto de aplicación

1. En el servidor BizTalk Server, abra la solución (ProjectName.sln) en Visual Studio. No seleccione Blend de Visual Studio.

2. En el Explorador de soluciones, haga clic en el proyecto y seleccione **generar**. Asegúrese de que la compilación se realiza correctamente. Haga clic en el proyecto y seleccione **implementar**. Asegúrese de que la implementación se realiza correctamente.

3. Haga clic en la solución, seleccione **agregar**y seleccione **Agregar nuevo proyecto**.

4. Seleccione el **proyectos de BizTalk** ficha, seleccione **.NET Framework 4.6.1** en la lista desplegable y seleccione **proyecto de aplicación de BizTalk Server**. Escriba un nombre (por ejemplo, appProjectHelloWorld) y seleccione **Aceptar**:  

    ![Agregar proyecto de aplicación](../core/media/add-application-project.png)

5. En el Explorador de soluciones, haga clic en el proyecto de aplicación recién agregado (.btaproj), seleccione **agregar**, seleccione **referencia**. Expanda el **proyectos** y a comprobar el proyecto de BizTalk (el proyecto en el que se va a implementar mediante VSTS). Seleccione **Aceptar**.  
    Una vez agregado, expanda **referencias** bajo el proyecto de aplicación (por ejemplo, appProjectHelloWorld) para ver el proyecto de BizTalk que acaba de agregar. 

6. En el Explorador de soluciones, haga clic en el proyecto de aplicación (.btaproj), seleccione **agregar**, seleccione **elemento existente**, y **agregar** el archivo de enlace XML.

7. Abra las propiedades de binding.xml y establezca **copiar en el directorio de salida** a **copiar siempre**. **Guardar** los cambios:  

    ![Propiedades de archivo de enlace](../core/media/xml-binding-file-properties.png)

8. Opcional. Haga clic en el proyecto de aplicación recién agregado y seleccione **propiedades**. Personalizar la **nombre de la aplicación** que desea mostrar en administración de BizTalk:  

    ![Nombre de la aplicación](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a>Configurar la plantilla JSON

1. En Visual Studio, en el proyecto de aplicación (.btaproj), abra el `BizTalkServerInventory.json` archivo. 

2. La plantilla incluye las siguientes secciones: 

    | | |
    |---|---|
    |BizTalkAssemblies | Los ensamblados utilizados en las aplicaciones |
    |BindingFiles | Los archivos de enlace que se hace referencia|
    |DeploymentSequence | La secuencia para los elementos que se va a instalar|
    
    Plantilla de ejemplo: 
    
    ![Imagen de plantilla Json FP1 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > Según la complejidad de la solución, se deben hacer referencia a los elementos que desee en la compilación de este archivo de plantilla JSON.

3. En `BizTalkAssemblies`, agregue los ensamblados utilizados por el proyecto de BizTalk: 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName",
            "Path": "PathToAssembly
        }
    ]
    ```

4. En `BindingsFiles`, agregue los archivos de enlace para el proyecto de BizTalk: 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name",
            "Path": "PathToBindingFile
        }
    ]
    ```

5. En `DeploymentSequence`, agregue los nombres de aplicación en el orden que desea implementar e instalar en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]: 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```


6. **Guardar** los cambios. Cuando termine, el archivo .json es similar a la siguiente: 

    ```
    {
      "$schema": "C:\\Program Files (x86)\\Microsoft BizTalk Server 2016\\Developer Tools\\BizTalkServerAppplicationSchema.json",
      "BizTalkAssemblies": [
        {
          "Name": "HelloWorld",
          "Path": "HelloWorld\\bin\\Release\\HelloWorld.dll"
        }
      ],
      "BindingsFiles": [
        {
          "Name": "HelloWorldBinding",
          "Path": "HelloWorld\\HelloWorldBinding.xml"
        }
      ],
      "DeploymentSequence": [
        "HelloWorld", "HelloWorldBinding"
      ]
    }
    ```

7. **Opcional**. Haga clic en el proyecto de aplicación (por ejemplo, appProjectHelloWorld) y seleccione **propiedades**. Puede establecer la versión de depuración o lanzamiento a un nuevo valor. Tenemos no en estos pasos, pero tenga en cuenta que puede hacer esto.  

    ![Establezca la versión debug o release](../core/media/application-project-version.png)

8. Haga clic en el proyecto de aplicación (por ejemplo, appProjectHelloWorld) y seleccione **generar**. Si se realiza correctamente, se crea un archivo zip en ***yourApplicationProject * \bin\debug** carpeta:  

    ![Compilar el archivo zip](../core/media/application-project-zip-file.png)

9. Seleccione la solución y seleccione la **Team Explorer** ficha. En VSTS, seleccione **conectar**.  

    ![Conectarse a Team Services](../core/media/connect-team-services.png)

10. Seleccione su cuenta VSTS, la colección y el proyecto de equipo. Seleccione **Aceptar**. Si no creó una cuenta VSTS aún, cree uno ([paso 2: crear el token VSTS](feature-pack-create-vsts-token.md) proporciona alguna orientación). Una vez creado, vuelva a este paso y conectarse.  

    ![Seleccione la colección y el proyecto](../core/media/team-collections-projects.png)

11. Cuando se conecte, obtendrá un símbolo del sistema para clonar el repositorio. Seleccione el **clonar este repositorio** vínculo.  

    ![Clonar el repositorio](../core/media/vsts-clone-repository.png)

12. Tenga en cuenta la dirección URL y las rutas de acceso y seleccione **clon**:  

    ![Rutas de acceso de repositorio](../core/media/clone-repo-paths.png)

Una vez completado, la tarea de implementación de Visual Studio Team Service respeta los archivos necesarios y la secuencia de instalación. 

> [!TIP]
> Si realiza cambios en el proyecto después de realizar la clonación de git, puede **fase** los cambios y, a continuación, **Push**, todo ello en Visual Studio. 

## <a name="what-you-did"></a>Lo que hizo

En el proyecto de BizTalk, ha agregado un proyecto de aplicación de BizTalk (.btaproj). Este proyecto se usa para automatizar las implementaciones de los proyectos de BizTalk Server mediante VSTS. Una vez creado el proyecto de aplicación, ha agregado una referencia al proyecto de BizTalk. A continuación, se actualiza un archivo JSON que indica la implementación automatizada de qué archivos DLL se implementa, qué archivo de enlace que se utiliza y el orden para implementar las aplicaciones. 

## <a name="next-steps"></a>Pasos siguientes
[Paso 2: Crear el token VSTS](feature-pack-create-vsts-token.md)  
[Paso 3: Crear la compilación y las definiciones de la versión](feature-pack-add-build-release-definitions.md)  
[Configurar las variables y tokens de entorno](configure-environmental-tokens-and-variables-for-automatic-deployment.md)
