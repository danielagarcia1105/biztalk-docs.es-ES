---
title: 'Paso 1: adición de json de proyecto y de actualización de aplicación | Microsoft Docs'
description: 'Agregue el proyecto de aplicación de BizTalk Server en Visual Studio y actualizar el archivo BizTalkServerInventory.json con los archivos DLL, los archivos de enlace y secuencia de implementación de sus aplicaciones: Visual Studio Team Services'
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
ms.openlocfilehash: e0230d0b280be412e3138ffbafd83d3810cf1163
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826364"
---
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a>Paso 1: Agregar el proyecto de aplicación de BizTalk Server en Visual Studio

Al compilar las aplicaciones con Visual Studio Team Services, se crea un nuevo archivo de proyecto de BizTalk – .btaproj. Este nuevo proyecto contiene todas las aplicaciones de BizTalk que compilar e implementa mediante la compilación VSTS y características de versión. 

El proyecto de aplicación de BizTalk incluye la `BizTalkServerInventory.json` archivo. En este archivo, agregue los ensamblados de BizTalk, agregue los archivos de enlace de la aplicación de BizTalk y, a continuación, establezca una secuencia de implementación. 

## <a name="before-you-begin"></a>Antes de comenzar

* Estos pasos se supone que tiene un proyecto de BizTalk existente. Si no, puede usar el ejemplo HelloWorld SDK (\Program Files (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld). 
* Tiene la ruta de acceso al archivo de enlace XML al proyecto de BizTalk preparado. 
* Conocer los detalles del proyecto de equipo, la colección y su cuenta de VSTS.
* Estar familiarizado con conceptos de git, como clonación y trabajar con repositorios. 
* Asegúrese de [Feature Pack 2](https://aka.ms/bts2016fp2) está instalado.

## <a name="add-the-application-project"></a>Agregar el proyecto de aplicación

1. En el servidor BizTalk Server, abra la solución (ProjectName.sln) en Visual Studio. No seleccione Blend de Visual Studio.

2. En el Explorador de soluciones, haga clic en el proyecto y seleccione **compilar**. Asegúrese de que la compilación se realiza correctamente. Haga clic en el proyecto y seleccione **implementar**. Asegúrese de que la implementación se realiza correctamente.

3. Haga clic en la solución, seleccione **agregar**y seleccione **Agregar nuevo proyecto**.

4. Seleccione el **proyectos de BizTalk** ficha, seleccione **.NET Framework 4.6.1** en la lista desplegable y seleccione **proyecto de aplicación de BizTalk Server**. Escriba un nombre (por ejemplo, appProjectHelloWorld) y seleccione **Aceptar**:  

    ![Agregar proyecto de aplicación](../core/media/add-application-project.png)

5. En el Explorador de soluciones, haga clic en el proyecto de aplicación recién agregada (.btaproj), seleccione **agregar**, seleccione **referencia**. Expanda el **proyectos** pestaña y compruebe el proyecto de BizTalk (el proyecto que se va a implementar mediante VSTS). Seleccione **Aceptar**.  
    Una vez agregado, expanda **referencias** bajo el proyecto de aplicación (por ejemplo, appProjectHelloWorld) para ver el proyecto de BizTalk que acaba de agregar. 

6. En el Explorador de soluciones, haga clic en el proyecto de aplicación (.btaproj), seleccione **agregar**, seleccione **elemento existente**, y **agregar** el archivo de enlace XML.

7. Abra las propiedades de binding.xml y establezca **Copy to Output Directory** a **copiar siempre**. **Guardar** los cambios:  

    ![Propiedades de archivo de enlace](../core/media/xml-binding-file-properties.png)

8. Opcional. Haga clic en el proyecto de aplicación recién agregada y seleccione **propiedades**. Personalizar el **nombre de la aplicación** que desea mostrar en la administración de BizTalk:  

    ![Nombre de la aplicación](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a>Configurar la plantilla de JSON

1. En Visual Studio, en el proyecto de aplicación (.btaproj), abra el `BizTalkServerInventory.json` archivo. 

2. La plantilla incluye las siguientes secciones: 

    | | |
    |---|---|
    |BizTalkAssemblies | Los ensamblados utilizados en las aplicaciones |
    |BindingFiles | Los archivos de enlace que se hace referencia|
    |DeploymentSequence | La secuencia para los elementos que se van a instalarse|
    
    Plantilla de ejemplo: 
    
    ![Imagen de plantilla Json FP1 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > Según la complejidad de la solución, se deben hacer referencia a los elementos que desee en la compilación en este archivo de plantilla JSON.

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

    ![Establezca la versión de depuración o lanzamiento](../core/media/application-project-version.png)

8. Haga clic en el proyecto de aplicación (por ejemplo, appProjectHelloWorld) y seleccione **compilar**. Si se realiza correctamente, se crea un archivo zip en  **_yourApplicationProject_\bin\debug** carpeta:  

    ![Compilar el archivo zip](../core/media/application-project-zip-file.png)

9. Seleccione la solución y seleccione el **Team Explorer** ficha. En VSTS, seleccione **Connect**.  

    ![Conectarse a Team Services](../core/media/connect-team-services.png)

10. Seleccione la cuenta de VSTS, la colección y el proyecto de equipo. Seleccione **Aceptar**. Si aún no creó una cuenta de VSTS, puede crear una ([paso 2: crear el token VSTS](feature-pack-create-vsts-token.md) proporcionan algunas directrices). Una vez creado, vuelva a este paso y conectarse.  

    ![Seleccione la colección y proyecto](../core/media/team-collections-projects.png)

11. Cuando se conecta, obtendrá un símbolo del sistema para clonar este repositorio. Seleccione el **clonar este repositorio** vínculo.  

    ![Clone el repositorio](../core/media/vsts-clone-repository.png)

12. Tenga en cuenta la dirección URL y rutas de acceso y seleccione **clon**:  

    ![Rutas de acceso de repositorio](../core/media/clone-repo-paths.png)

Una vez completado, la tarea de implementación de Visual Studio Team Service respeta los archivos necesarios y la secuencia de instalación. 

> [!TIP]
> Si realiza cambios en el proyecto después de clonar de git, puede **fase** los cambios y, a continuación, **Push**, todo ello en Visual Studio. 

## <a name="what-you-did"></a>Lo que hizo

En el proyecto de BizTalk, ha agregado un proyecto de aplicación de BizTalk (.btaproj). Este proyecto se usa para automatizar las implementaciones de los proyectos de BizTalk Server mediante VSTS. Una vez creado el proyecto de aplicación, ha agregado una referencia al proyecto de BizTalk. A continuación, actualiza un archivo JSON que se indica a la implementación automatizada cuáles dll para implementar, qué archivo de enlace debe usar y el orden para implementar las aplicaciones. 

## <a name="next-steps"></a>Pasos siguientes
[Paso 2: Crear el token de VSTS](feature-pack-create-vsts-token.md)  
[Paso 3: Crear la compilación y definiciones de versión](feature-pack-add-build-release-definitions.md)  
[Configurar las variables y los tokens de entorno](configure-environmental-tokens-and-variables-for-automatic-deployment.md)
