---
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
ms.openlocfilehash: dba2870a2a7f9aeaaa627dba00afca85f3ca71c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-json-template-for-automatic-deployment"></a><span data-ttu-id="6cc80-102">Configurar la plantilla JSON para la implementación automática</span><span class="sxs-lookup"><span data-stu-id="6cc80-102">Configure the JSON template for automatic deployment</span></span>


<span data-ttu-id="6cc80-103">Al compilar las aplicaciones mediante Visual Studio Team Services, se crea un nuevo archivo de proyecto de BizTalk – (.btaproj).</span><span class="sxs-lookup"><span data-stu-id="6cc80-103">When you build your applications using Visual Studio Team Services, a new BizTalk project file is created – (.btaproj).</span></span> <span data-ttu-id="6cc80-104">Este nuevo proyecto contiene todas las aplicaciones de BizTalk que se generación mediante VSTS.</span><span class="sxs-lookup"><span data-stu-id="6cc80-104">This new project holds all the BizTalk applications that you build using VSTS.</span></span> 

<span data-ttu-id="6cc80-105">El proyecto incluye el `BizTalkServerInventory.json` archivo.</span><span class="sxs-lookup"><span data-stu-id="6cc80-105">Your project includes the `BizTalkServerInventory.json` file.</span></span> <span data-ttu-id="6cc80-106">En este archivo, agregue los ensamblados de BizTalk, agregue los archivos de enlace de la aplicación de BizTalk y establecer una secuencia de implementación.</span><span class="sxs-lookup"><span data-stu-id="6cc80-106">In this file, add your BizTalk assemblies, add the binding files for your BizTalk application, and set a deployment sequence.</span></span> 

<span data-ttu-id="6cc80-107">En este tema se muestra cómo actualizar el archivo json.</span><span class="sxs-lookup"><span data-stu-id="6cc80-107">This topic shows you how to update the json file.</span></span> 

## <a name="add-assemblies-binding-files-and-deployment-sequence"></a><span data-ttu-id="6cc80-108">Agregar ensamblados, archivos de enlace y la secuencia de implementación</span><span class="sxs-lookup"><span data-stu-id="6cc80-108">Add assemblies, binding files, and deployment sequence</span></span>

1. <span data-ttu-id="6cc80-109">Abra la `BizTalkServerInventory.json` un archivo en su **aplicación de BizTalk Server** proyecto (.btaproj).</span><span class="sxs-lookup"><span data-stu-id="6cc80-109">Open the `BizTalkServerInventory.json` file in your **BizTalk Server Application** project (.btaproj).</span></span>

2. <span data-ttu-id="6cc80-110">La plantilla incluye las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="6cc80-110">The template includes the following sections:</span></span> 

    | | |
    |---|---|
    |<span data-ttu-id="6cc80-111">BizTalkAssemblies</span><span class="sxs-lookup"><span data-stu-id="6cc80-111">BizTalkAssemblies</span></span> | <span data-ttu-id="6cc80-112">Los ensamblados utilizados en las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="6cc80-112">The assemblies used in your applications</span></span> |
    |<span data-ttu-id="6cc80-113">BindingFiles</span><span class="sxs-lookup"><span data-stu-id="6cc80-113">BindingFiles</span></span> | <span data-ttu-id="6cc80-114">Los archivos de enlace que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="6cc80-114">The binding files you are referencing</span></span>|
    | <span data-ttu-id="6cc80-115">DeploymentSequence</span><span class="sxs-lookup"><span data-stu-id="6cc80-115">DeploymentSequence</span></span> | <span data-ttu-id="6cc80-116">La secuencia para los elementos que se va a instalar</span><span class="sxs-lookup"><span data-stu-id="6cc80-116">The sequence for the elements to be installed</span></span>|
    
    <span data-ttu-id="6cc80-117">Plantilla de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6cc80-117">Sample template:</span></span> 
    
    ![Imagen de plantilla Json FP1 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > <span data-ttu-id="6cc80-119">Según la complejidad de la solución, se deben hacer referencia a los elementos que desee en la compilación de este archivo de plantilla JSON.</span><span class="sxs-lookup"><span data-stu-id="6cc80-119">Depending on the complexity of your solution, the elements you want in the build must be referenced in this JSON template file.</span></span>

3. <span data-ttu-id="6cc80-120">En `BizTalkAssemblies`, agregue los ensamblados utilizados por las aplicaciones de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="6cc80-120">In `BizTalkAssemblies`, add the assemblies used by your BizTalk applications:</span></span> 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName"
            "Path": "PathToAssembly
        }
    ]
    ```

4. <span data-ttu-id="6cc80-121">En `BindingsFiles`, agregue los archivos de enlace para las aplicaciones de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="6cc80-121">In `BindingsFiles`, add the binding files for your BizTalk applications:</span></span> 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name"
            "Path": "PathToBindingFile
        }
    ]
    ```

5. <span data-ttu-id="6cc80-122">En `DeploymentSequence`, agregue los nombres de aplicación en el orden que desea implementar e instalar en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6cc80-122">In `DeploymentSequence`, add the application names in the order you want them deployed and installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span></span> 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```
    
6. <span data-ttu-id="6cc80-123">**Guardar** los cambios.</span><span class="sxs-lookup"><span data-stu-id="6cc80-123">**Save** your changes.</span></span> 

<span data-ttu-id="6cc80-124">Una vez completado, la tarea de implementación de Visual Studio Team Service respeta los archivos necesarios y la secuencia de instalación.</span><span class="sxs-lookup"><span data-stu-id="6cc80-124">Once completed, the Visual Studio Team Service deployment task honors the required files and the install sequence.</span></span> 

## <a name="next-step"></a><span data-ttu-id="6cc80-125">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="6cc80-125">Next step</span></span>
<span data-ttu-id="6cc80-126">[Configurar las variables y los tokens](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md) en el archivo de enlace para implementar la misma aplicación de BizTalk a varios [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s.</span><span class="sxs-lookup"><span data-stu-id="6cc80-126">[Configure tokens and variables](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md) in your binding file to deploy the same BizTalk application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s.</span></span>

 