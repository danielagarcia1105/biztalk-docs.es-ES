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
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a><span data-ttu-id="0e333-103">Paso 1: Agregar el proyecto de aplicación de BizTalk Server en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0e333-103">Step 1: Add the BizTalk Server Application project in Visual Studio</span></span>

<span data-ttu-id="0e333-104">Al compilar las aplicaciones con Visual Studio Team Services, se crea un nuevo archivo de proyecto de BizTalk – .btaproj.</span><span class="sxs-lookup"><span data-stu-id="0e333-104">When you build your applications using Visual Studio Team Services, a new BizTalk project file is created – .btaproj.</span></span> <span data-ttu-id="0e333-105">Este nuevo proyecto contiene todas las aplicaciones de BizTalk que compilar e implementa mediante la compilación VSTS y características de versión.</span><span class="sxs-lookup"><span data-stu-id="0e333-105">This new project holds all the BizTalk applications that you build and deploy using the VSTS build and release features.</span></span> 

<span data-ttu-id="0e333-106">El proyecto de aplicación de BizTalk incluye la `BizTalkServerInventory.json` archivo.</span><span class="sxs-lookup"><span data-stu-id="0e333-106">The BizTalk Application Project includes the `BizTalkServerInventory.json` file.</span></span> <span data-ttu-id="0e333-107">En este archivo, agregue los ensamblados de BizTalk, agregue los archivos de enlace de la aplicación de BizTalk y, a continuación, establezca una secuencia de implementación.</span><span class="sxs-lookup"><span data-stu-id="0e333-107">In this file, add your BizTalk assemblies, add the binding files for your BizTalk application, and then set a deployment sequence.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="0e333-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="0e333-108">Before you begin</span></span>

* <span data-ttu-id="0e333-109">Estos pasos se supone que tiene un proyecto de BizTalk existente.</span><span class="sxs-lookup"><span data-stu-id="0e333-109">These steps assume you have an existing BizTalk project.</span></span> <span data-ttu-id="0e333-110">Si no, puede usar el ejemplo HelloWorld SDK (\Program Files (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld).</span><span class="sxs-lookup"><span data-stu-id="0e333-110">If not, you can use the HelloWorld SDK sample (\Program Files (x86)\Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld).</span></span> 
* <span data-ttu-id="0e333-111">Tiene la ruta de acceso al archivo de enlace XML al proyecto de BizTalk preparado.</span><span class="sxs-lookup"><span data-stu-id="0e333-111">Have the path to the XML binding file to your BizTalk project ready.</span></span> 
* <span data-ttu-id="0e333-112">Conocer los detalles del proyecto de equipo, la colección y su cuenta de VSTS.</span><span class="sxs-lookup"><span data-stu-id="0e333-112">Know your VSTS account, your collection, and your team project details.</span></span>
* <span data-ttu-id="0e333-113">Estar familiarizado con conceptos de git, como clonación y trabajar con repositorios.</span><span class="sxs-lookup"><span data-stu-id="0e333-113">Be familiar with git concepts, including cloning and working with repositories.</span></span> 
* <span data-ttu-id="0e333-114">Asegúrese de [Feature Pack 2](https://aka.ms/bts2016fp2) está instalado.</span><span class="sxs-lookup"><span data-stu-id="0e333-114">Be sure [Feature Pack 2](https://aka.ms/bts2016fp2) is installed.</span></span>

## <a name="add-the-application-project"></a><span data-ttu-id="0e333-115">Agregar el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="0e333-115">Add the application project</span></span>

1. <span data-ttu-id="0e333-116">En el servidor BizTalk Server, abra la solución (ProjectName.sln) en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0e333-116">On the BizTalk Server, open your solution (ProjectName.sln) in Visual Studio.</span></span> <span data-ttu-id="0e333-117">No seleccione Blend de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0e333-117">Do not select Visual Studio Blend.</span></span>

2. <span data-ttu-id="0e333-118">En el Explorador de soluciones, haga clic en el proyecto y seleccione **compilar**.</span><span class="sxs-lookup"><span data-stu-id="0e333-118">In solution explorer, right-click your project, and select **Build**.</span></span> <span data-ttu-id="0e333-119">Asegúrese de que la compilación se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e333-119">Be sure your build succeeds.</span></span> <span data-ttu-id="0e333-120">Haga clic en el proyecto y seleccione **implementar**.</span><span class="sxs-lookup"><span data-stu-id="0e333-120">Right-click your project, and select **Deploy**.</span></span> <span data-ttu-id="0e333-121">Asegúrese de que la implementación se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e333-121">Be sure your deploy succeeds.</span></span>

3. <span data-ttu-id="0e333-122">Haga clic en la solución, seleccione **agregar**y seleccione **Agregar nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0e333-122">Right-click your solution, select **Add**, and select **Add New Project**.</span></span>

4. <span data-ttu-id="0e333-123">Seleccione el **proyectos de BizTalk** ficha, seleccione **.NET Framework 4.6.1** en la lista desplegable y seleccione **proyecto de aplicación de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="0e333-123">Select the **BizTalk Projects** tab, select **.NET Framework 4.6.1** from the drop-down list, and select **BizTalk Server Application Project**.</span></span> <span data-ttu-id="0e333-124">Escriba un nombre (por ejemplo, appProjectHelloWorld) y seleccione **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="0e333-124">Enter a name (e.g. appProjectHelloWorld), and select **OK**:</span></span>  

    ![Agregar proyecto de aplicación](../core/media/add-application-project.png)

5. <span data-ttu-id="0e333-126">En el Explorador de soluciones, haga clic en el proyecto de aplicación recién agregada (.btaproj), seleccione **agregar**, seleccione **referencia**.</span><span class="sxs-lookup"><span data-stu-id="0e333-126">In Solution Explorer, right-click your newly-added application project (.btaproj), select **Add**, select **Reference**.</span></span> <span data-ttu-id="0e333-127">Expanda el **proyectos** pestaña y compruebe el proyecto de BizTalk (el proyecto que se va a implementar mediante VSTS).</span><span class="sxs-lookup"><span data-stu-id="0e333-127">Expand the **Projects** tab, and check your BizTalk project (the project you are deploying using VSTS).</span></span> <span data-ttu-id="0e333-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e333-128">Select **OK**.</span></span>  
    <span data-ttu-id="0e333-129">Una vez agregado, expanda **referencias** bajo el proyecto de aplicación (por ejemplo, appProjectHelloWorld) para ver el proyecto de BizTalk que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="0e333-129">Once added, expand **References** under your application project (e.g. appProjectHelloWorld) to see the BizTalk project you just added.</span></span> 

6. <span data-ttu-id="0e333-130">En el Explorador de soluciones, haga clic en el proyecto de aplicación (.btaproj), seleccione **agregar**, seleccione **elemento existente**, y **agregar** el archivo de enlace XML.</span><span class="sxs-lookup"><span data-stu-id="0e333-130">In Solution Explorer, right-click your application project (.btaproj), select **Add**, select **Existing Item**, and **Add** your binding XML file.</span></span>

7. <span data-ttu-id="0e333-131">Abra las propiedades de binding.xml y establezca **Copy to Output Directory** a **copiar siempre**.</span><span class="sxs-lookup"><span data-stu-id="0e333-131">Open the properties of binding.xml, and set **Copy to Output Directory** to **Copy always**.</span></span> <span data-ttu-id="0e333-132">**Guardar** los cambios:</span><span class="sxs-lookup"><span data-stu-id="0e333-132">**Save** your changes:</span></span>  

    ![Propiedades de archivo de enlace](../core/media/xml-binding-file-properties.png)

8. <span data-ttu-id="0e333-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0e333-134">Optional.</span></span> <span data-ttu-id="0e333-135">Haga clic en el proyecto de aplicación recién agregada y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0e333-135">Right-click your newly-added application project, and select **Properties**.</span></span> <span data-ttu-id="0e333-136">Personalizar el **nombre de la aplicación** que desea mostrar en la administración de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="0e333-136">Customize the **Application Name** you want displayed in BizTalk Administration:</span></span>  

    ![Nombre de la aplicación](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a><span data-ttu-id="0e333-138">Configurar la plantilla de JSON</span><span class="sxs-lookup"><span data-stu-id="0e333-138">Configure the JSON template</span></span>

1. <span data-ttu-id="0e333-139">En Visual Studio, en el proyecto de aplicación (.btaproj), abra el `BizTalkServerInventory.json` archivo.</span><span class="sxs-lookup"><span data-stu-id="0e333-139">In Visual Studio, in your application project (.btaproj), open the `BizTalkServerInventory.json` file.</span></span> 

2. <span data-ttu-id="0e333-140">La plantilla incluye las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="0e333-140">The template includes the following sections:</span></span> 

    | | |
    |---|---|
    |<span data-ttu-id="0e333-141">BizTalkAssemblies</span><span class="sxs-lookup"><span data-stu-id="0e333-141">BizTalkAssemblies</span></span> | <span data-ttu-id="0e333-142">Los ensamblados utilizados en las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0e333-142">The assemblies used in your applications</span></span> |
    |<span data-ttu-id="0e333-143">BindingFiles</span><span class="sxs-lookup"><span data-stu-id="0e333-143">BindingFiles</span></span> | <span data-ttu-id="0e333-144">Los archivos de enlace que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="0e333-144">The binding files you are referencing</span></span>|
    |<span data-ttu-id="0e333-145">DeploymentSequence</span><span class="sxs-lookup"><span data-stu-id="0e333-145">DeploymentSequence</span></span> | <span data-ttu-id="0e333-146">La secuencia para los elementos que se van a instalarse</span><span class="sxs-lookup"><span data-stu-id="0e333-146">The sequence for the elements to be installed</span></span>|
    
    <span data-ttu-id="0e333-147">Plantilla de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e333-147">Sample template:</span></span> 
    
    ![Imagen de plantilla Json FP1 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > <span data-ttu-id="0e333-149">Según la complejidad de la solución, se deben hacer referencia a los elementos que desee en la compilación en este archivo de plantilla JSON.</span><span class="sxs-lookup"><span data-stu-id="0e333-149">Depending on the complexity of your solution, the elements you want in the build must be referenced in this JSON template file.</span></span>

3. <span data-ttu-id="0e333-150">En `BizTalkAssemblies`, agregue los ensamblados utilizados por el proyecto de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="0e333-150">In `BizTalkAssemblies`, add the assemblies used by your BizTalk project:</span></span> 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName",
            "Path": "PathToAssembly
        }
    ]
    ```

4. <span data-ttu-id="0e333-151">En `BindingsFiles`, agregue los archivos de enlace para el proyecto de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="0e333-151">In `BindingsFiles`, add the binding files for your BizTalk project:</span></span> 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name",
            "Path": "PathToBindingFile
        }
    ]
    ```

5. <span data-ttu-id="0e333-152">En `DeploymentSequence`, agregue los nombres de aplicación en el orden que desea implementar e instalar en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0e333-152">In `DeploymentSequence`, add the application names in the order you want them deployed, and installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span></span> 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```


6. <span data-ttu-id="0e333-153">**Guardar** los cambios.</span><span class="sxs-lookup"><span data-stu-id="0e333-153">**Save** your changes.</span></span> <span data-ttu-id="0e333-154">Cuando termine, el archivo .json es similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e333-154">When finished, your .json file looks like the following:</span></span> 

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

7. <span data-ttu-id="0e333-155">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="0e333-155">**Optional**.</span></span> <span data-ttu-id="0e333-156">Haga clic en el proyecto de aplicación (por ejemplo, appProjectHelloWorld) y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0e333-156">Right-click your application project (e.g. appProjectHelloWorld), and select **Properties**.</span></span> <span data-ttu-id="0e333-157">Puede establecer la versión de depuración o lanzamiento a un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="0e333-157">You can set the Debug or Release version to a new value.</span></span> <span data-ttu-id="0e333-158">Tenemos no en estos pasos, pero tenga en cuenta que puede hacer esto.</span><span class="sxs-lookup"><span data-stu-id="0e333-158">We don’t in these steps, but be aware you can do this.</span></span>  

    ![Establezca la versión de depuración o lanzamiento](../core/media/application-project-version.png)

8. <span data-ttu-id="0e333-160">Haga clic en el proyecto de aplicación (por ejemplo, appProjectHelloWorld) y seleccione **compilar**.</span><span class="sxs-lookup"><span data-stu-id="0e333-160">Right-click your application project (e.g. appProjectHelloWorld), and select **Build**.</span></span> <span data-ttu-id="0e333-161">Si se realiza correctamente, se crea un archivo zip en  **_yourApplicationProject_\bin\debug** carpeta:</span><span class="sxs-lookup"><span data-stu-id="0e333-161">If it succeeds, a zip file is created in **_yourApplicationProject_\bin\debug** folder:</span></span>  

    ![Compilar el archivo zip](../core/media/application-project-zip-file.png)

9. <span data-ttu-id="0e333-163">Seleccione la solución y seleccione el **Team Explorer** ficha. En VSTS, seleccione **Connect**.</span><span class="sxs-lookup"><span data-stu-id="0e333-163">Select your solution, and select the **Team Explorer** tab. Under VSTS, select **Connect**.</span></span>  

    ![Conectarse a Team Services](../core/media/connect-team-services.png)

10. <span data-ttu-id="0e333-165">Seleccione la cuenta de VSTS, la colección y el proyecto de equipo.</span><span class="sxs-lookup"><span data-stu-id="0e333-165">Select your VSTS account, your collection, and your team project.</span></span> <span data-ttu-id="0e333-166">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e333-166">Select **OK**.</span></span> <span data-ttu-id="0e333-167">Si aún no creó una cuenta de VSTS, puede crear una ([paso 2: crear el token VSTS](feature-pack-create-vsts-token.md) proporcionan algunas directrices).</span><span class="sxs-lookup"><span data-stu-id="0e333-167">If you didn’t create a VSTS account yet, then create one ([Step 2: Create the VSTS token](feature-pack-create-vsts-token.md) provides some guidance).</span></span> <span data-ttu-id="0e333-168">Una vez creado, vuelva a este paso y conectarse.</span><span class="sxs-lookup"><span data-stu-id="0e333-168">Once it's created, come back to this step, and connect.</span></span>  

    ![Seleccione la colección y proyecto](../core/media/team-collections-projects.png)

11. <span data-ttu-id="0e333-170">Cuando se conecta, obtendrá un símbolo del sistema para clonar este repositorio.</span><span class="sxs-lookup"><span data-stu-id="0e333-170">When you connect, you may get a prompt to clone this repository.</span></span> <span data-ttu-id="0e333-171">Seleccione el **clonar este repositorio** vínculo.</span><span class="sxs-lookup"><span data-stu-id="0e333-171">Select the **Clone this repository** link.</span></span>  

    ![Clone el repositorio](../core/media/vsts-clone-repository.png)

12. <span data-ttu-id="0e333-173">Tenga en cuenta la dirección URL y rutas de acceso y seleccione **clon**:</span><span class="sxs-lookup"><span data-stu-id="0e333-173">Note the URL and paths, and select **Clone**:</span></span>  

    ![Rutas de acceso de repositorio](../core/media/clone-repo-paths.png)

<span data-ttu-id="0e333-175">Una vez completado, la tarea de implementación de Visual Studio Team Service respeta los archivos necesarios y la secuencia de instalación.</span><span class="sxs-lookup"><span data-stu-id="0e333-175">Once completed, the Visual Studio Team Service deployment task honors the required files and the install sequence.</span></span> 

> [!TIP]
> <span data-ttu-id="0e333-176">Si realiza cambios en el proyecto después de clonar de git, puede **fase** los cambios y, a continuación, **Push**, todo ello en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0e333-176">If you make changes to your project after you clone in git, you can **Stage** your changes, and then **Push**, all within Visual Studio.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="0e333-177">Lo que hizo</span><span class="sxs-lookup"><span data-stu-id="0e333-177">What you did</span></span>

<span data-ttu-id="0e333-178">En el proyecto de BizTalk, ha agregado un proyecto de aplicación de BizTalk (.btaproj).</span><span class="sxs-lookup"><span data-stu-id="0e333-178">In your BizTalk project, you added a BizTalk Application project (.btaproj).</span></span> <span data-ttu-id="0e333-179">Este proyecto se usa para automatizar las implementaciones de los proyectos de BizTalk Server mediante VSTS.</span><span class="sxs-lookup"><span data-stu-id="0e333-179">This project is used to automate deployments of your BizTalk Server projects using VSTS.</span></span> <span data-ttu-id="0e333-180">Una vez creado el proyecto de aplicación, ha agregado una referencia al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0e333-180">After you created the application project, you added a reference to your BizTalk project.</span></span> <span data-ttu-id="0e333-181">A continuación, actualiza un archivo JSON que se indica a la implementación automatizada cuáles dll para implementar, qué archivo de enlace debe usar y el orden para implementar las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0e333-181">Then, you updated a JSON file that tells the automated deployment what DLLs to deploy, which binding file to use, and the order to deploy the applications.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="0e333-182">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0e333-182">Next steps</span></span>
[<span data-ttu-id="0e333-183">Paso 2: Crear el token de VSTS</span><span class="sxs-lookup"><span data-stu-id="0e333-183">Step 2: Create the VSTS token</span></span>](feature-pack-create-vsts-token.md)  
[<span data-ttu-id="0e333-184">Paso 3: Crear la compilación y definiciones de versión</span><span class="sxs-lookup"><span data-stu-id="0e333-184">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="0e333-185">Configurar las variables y los tokens de entorno</span><span class="sxs-lookup"><span data-stu-id="0e333-185">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)
