---
redirect_url: /biztalk/core/feature-pack-add-application-project/
redirect_document_id: True
ROBOTS: NOINDEX
title: "Configurar la plantilla JSON para la implementación automática | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 0b7755a6-5a5a-4a6b-8f99-ac12a5fbf3d4
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 10d85b625d759af675ecc1a38d540da8a304ba43
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2017
---
# <a name="configure-the-json-template-for-automatic-deployment"></a>Configurar la plantilla JSON para la implementación automática


Al compilar las aplicaciones mediante Visual Studio Team Services, se crea un nuevo archivo de proyecto de BizTalk – (.btaproj). Este nuevo proyecto contiene todas las aplicaciones de BizTalk que se generación mediante VSTS. 

El proyecto incluye el `BizTalkServerInventory.json` archivo. En este archivo, agregue los ensamblados de BizTalk, agregue los archivos de enlace de la aplicación de BizTalk y establecer una secuencia de implementación. 

En este tema se muestra cómo actualizar el archivo json. 

## <a name="add-assemblies-binding-files-and-deployment-sequence"></a>Agregar ensamblados, archivos de enlace y la secuencia de implementación

1. Abra la `BizTalkServerInventory.json` un archivo en su **aplicación de BizTalk Server** proyecto (.btaproj).

2. La plantilla incluye las siguientes secciones: 

    | | |
    |---|---|
    |BizTalkAssemblies | Los ensamblados utilizados en las aplicaciones |
    |BindingFiles | Los archivos de enlace que se hace referencia|
    | DeploymentSequence | La secuencia para los elementos que se va a instalar|
    
    Plantilla de ejemplo: 
    
    ![Imagen de plantilla Json FP1 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > Según la complejidad de la solución, se deben hacer referencia a los elementos que desee en la compilación de este archivo de plantilla JSON.

3. En `BizTalkAssemblies`, agregue los ensamblados utilizados por las aplicaciones de BizTalk: 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName"
            "Path": "PathToAssembly
        }
    ]
    ```

4. En `BindingsFiles`, agregue los archivos de enlace para las aplicaciones de BizTalk: 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name"
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
    
6. **Guardar** los cambios. 

Una vez completado, la tarea de implementación de Visual Studio Team Service respeta los archivos necesarios y la secuencia de instalación. 

## <a name="next-step"></a>Paso siguiente
[Configurar las variables y los tokens](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md) en el archivo de enlace para implementar la misma aplicación de BizTalk a varios [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s.

 