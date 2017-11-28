---
title: "Paso 1: Agregar aplicación json de proyecto y actualice | Documentos de Microsoft"
description: "Agregue el proyecto de aplicación de BizTalk Server en Visual Studio y actualizar el archivo BizTalkServerInventory.json con los archivos DLL, archivos de enlace y la secuencia de implementación de las aplicaciones - Visual Studio Team Services"
ms.custom: 
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d4b9773c9c7b23715b5ddae29c3c97f381da5e
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a><span data-ttu-id="fc3fe-103">Paso 1: Agregar el proyecto de aplicación de BizTalk Server en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fc3fe-103">Step 1: Add the BizTalk Server Application project in Visual Studio</span></span>

<span data-ttu-id="fc3fe-104">Al compilar las aplicaciones mediante Visual Studio Team Services, se crea un nuevo archivo de proyecto de BizTalk: .btaproj.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-104">When you build your applications using Visual Studio Team Services, a new BizTalk project file is created – .btaproj.</span></span> <span data-ttu-id="fc3fe-105">Este nuevo proyecto contiene todas las aplicaciones de BizTalk de compilación y la implementación con la compilación VSTS y características de la versión.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-105">This new project holds all the BizTalk applications that you build and deploy using the VSTS build and release features.</span></span> 

<span data-ttu-id="fc3fe-106">El proyecto de aplicación de BizTalk incluye la `BizTalkServerInventory.json` archivo.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-106">The BizTalk Application Project includes the `BizTalkServerInventory.json` file.</span></span> <span data-ttu-id="fc3fe-107">En este archivo, agregue los ensamblados de BizTalk, agregue los archivos de enlace de la aplicación de BizTalk y, a continuación, establezca una secuencia de implementación.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-107">In this file, add your BizTalk assemblies, add the binding files for your BizTalk application, and then set a deployment sequence.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="fc3fe-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="fc3fe-108">Before you begin</span></span>

* <span data-ttu-id="fc3fe-109">Estos pasos se supone que tiene un proyecto de BizTalk existente.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-109">These steps assume you have an existing BizTalk project.</span></span> <span data-ttu-id="fc3fe-110">Si no es así, puede usar el ejemplo HelloWorld SDK (\Program Files (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld).</span><span class="sxs-lookup"><span data-stu-id="fc3fe-110">If not, you can use the HelloWorld SDK sample (\Program Files (x86)\Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld).</span></span> 
* <span data-ttu-id="fc3fe-111">Tiene la ruta de acceso al archivo de enlace XML al proyecto de BizTalk listo.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-111">Have the path to the XML binding file to your BizTalk project ready.</span></span> 
* <span data-ttu-id="fc3fe-112">Conocer su cuenta VSTS, la colección y los detalles del proyecto de equipo.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-112">Know your VSTS account, your collection, and your team project details.</span></span>
* <span data-ttu-id="fc3fe-113">Estar familiarizado con conceptos de git, incluye la clonación y el trabajo con repositorios.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-113">Be familiar with git concepts, including cloning and working with repositories.</span></span> 
* <span data-ttu-id="fc3fe-114">Asegúrese de [Feature Pack 2](https://aka.ms/bts2016fp2) está instalado.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-114">Be sure [Feature Pack 2](https://aka.ms/bts2016fp2) is installed.</span></span>

## <a name="add-the-application-project"></a><span data-ttu-id="fc3fe-115">Agregue el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="fc3fe-115">Add the application project</span></span>

1. <span data-ttu-id="fc3fe-116">En el servidor BizTalk Server, abra la solución (ProjectName.sln) en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-116">On the BizTalk Server, open your solution (ProjectName.sln) in Visual Studio.</span></span> <span data-ttu-id="fc3fe-117">No seleccione Blend de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-117">Do not select Visual Studio Blend.</span></span>

2. <span data-ttu-id="fc3fe-118">En el Explorador de soluciones, haga clic en el proyecto y seleccione **generar**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-118">In solution explorer, right-click your project, and select **Build**.</span></span> <span data-ttu-id="fc3fe-119">Asegúrese de que la compilación se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-119">Be sure your build succeeds.</span></span> <span data-ttu-id="fc3fe-120">Haga clic en el proyecto y seleccione **implementar**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-120">Right-click your project, and select **Deploy**.</span></span> <span data-ttu-id="fc3fe-121">Asegúrese de que la implementación se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-121">Be sure your deploy succeeds.</span></span>

3. <span data-ttu-id="fc3fe-122">Haga clic en la solución, seleccione **agregar**y seleccione **Agregar nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-122">Right-click your solution, select **Add**, and select **Add New Project**.</span></span>

4. <span data-ttu-id="fc3fe-123">Seleccione el **proyectos de BizTalk** ficha, seleccione **.NET Framework 4.6.1** en la lista desplegable y seleccione **proyecto de aplicación de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-123">Select the **BizTalk Projects** tab, select **.NET Framework 4.6.1** from the drop-down list, and select **BizTalk Server Application Project**.</span></span> <span data-ttu-id="fc3fe-124">Escriba un nombre (por ejemplo, appProjectHelloWorld) y seleccione **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-124">Enter a name (e.g. appProjectHelloWorld), and select **OK**:</span></span>  

    ![Agregar proyecto de aplicación](../core/media/add-application-project.png)

5. <span data-ttu-id="fc3fe-126">En el Explorador de soluciones, haga clic en el proyecto de aplicación recién agregado (.btaproj), seleccione **agregar**, seleccione **referencia**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-126">In Solution Explorer, right-click your newly-added application project (.btaproj), select **Add**, select **Reference**.</span></span> <span data-ttu-id="fc3fe-127">Expanda el **proyectos** y a comprobar el proyecto de BizTalk (el proyecto en el que se va a implementar mediante VSTS).</span><span class="sxs-lookup"><span data-stu-id="fc3fe-127">Expand the **Projects** tab, and check your BizTalk project (the project you are deploying using VSTS).</span></span> <span data-ttu-id="fc3fe-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-128">Select **OK**.</span></span>  
    <span data-ttu-id="fc3fe-129">Una vez agregado, expanda **referencias** bajo el proyecto de aplicación (por ejemplo, appProjectHelloWorld) para ver el proyecto de BizTalk que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-129">Once added, expand **References** under your application project (e.g. appProjectHelloWorld) to see the BizTalk project you just added.</span></span> 

6. <span data-ttu-id="fc3fe-130">En el Explorador de soluciones, haga clic en el proyecto de aplicación (.btaproj), seleccione **agregar**, seleccione **elemento existente**, y **agregar** el archivo de enlace XML.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-130">In Solution Explorer, right-click your application project (.btaproj), select **Add**, select **Existing Item**, and **Add** your binding XML file.</span></span>

7. <span data-ttu-id="fc3fe-131">Abra las propiedades de binding.xml y establezca **copiar en el directorio de salida** a **copiar siempre**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-131">Open the properties of binding.xml, and set **Copy to Output Directory** to **Copy always**.</span></span> <span data-ttu-id="fc3fe-132">**Guardar** los cambios:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-132">**Save** your changes:</span></span>  

    ![Propiedades de archivo de enlace](../core/media/xml-binding-file-properties.png)

8. <span data-ttu-id="fc3fe-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-134">Optional.</span></span> <span data-ttu-id="fc3fe-135">Haga clic en el proyecto de aplicación recién agregado y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-135">Right-click your newly-added application project, and select **Properties**.</span></span> <span data-ttu-id="fc3fe-136">Personalizar la **nombre de la aplicación** que desea mostrar en administración de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-136">Customize the **Application Name** you want displayed in BizTalk Administration:</span></span>  

    ![Nombre de la aplicación](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a><span data-ttu-id="fc3fe-138">Configurar la plantilla JSON</span><span class="sxs-lookup"><span data-stu-id="fc3fe-138">Configure the JSON template</span></span>

1. <span data-ttu-id="fc3fe-139">En Visual Studio, en el proyecto de aplicación (.btaproj), abra el `BizTalkServerInventory.json` archivo.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-139">In Visual Studio, in your application project (.btaproj), open the `BizTalkServerInventory.json` file.</span></span> 

2. <span data-ttu-id="fc3fe-140">La plantilla incluye las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-140">The template includes the following sections:</span></span> 

    | | |
    |---|---|
    |<span data-ttu-id="fc3fe-141">BizTalkAssemblies</span><span class="sxs-lookup"><span data-stu-id="fc3fe-141">BizTalkAssemblies</span></span> | <span data-ttu-id="fc3fe-142">Los ensamblados utilizados en las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fc3fe-142">The assemblies used in your applications</span></span> |
    |<span data-ttu-id="fc3fe-143">BindingFiles</span><span class="sxs-lookup"><span data-stu-id="fc3fe-143">BindingFiles</span></span> | <span data-ttu-id="fc3fe-144">Los archivos de enlace que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="fc3fe-144">The binding files you are referencing</span></span>|
    |<span data-ttu-id="fc3fe-145">DeploymentSequence</span><span class="sxs-lookup"><span data-stu-id="fc3fe-145">DeploymentSequence</span></span> | <span data-ttu-id="fc3fe-146">La secuencia para los elementos que se va a instalar</span><span class="sxs-lookup"><span data-stu-id="fc3fe-146">The sequence for the elements to be installed</span></span>|
    
    <span data-ttu-id="fc3fe-147">Plantilla de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-147">Sample template:</span></span> 
    
    ![Imagen de plantilla Json FP1 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > <span data-ttu-id="fc3fe-149">Según la complejidad de la solución, se deben hacer referencia a los elementos que desee en la compilación de este archivo de plantilla JSON.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-149">Depending on the complexity of your solution, the elements you want in the build must be referenced in this JSON template file.</span></span>

3. <span data-ttu-id="fc3fe-150">En `BizTalkAssemblies`, agregue los ensamblados utilizados por el proyecto de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-150">In `BizTalkAssemblies`, add the assemblies used by your BizTalk project:</span></span> 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName"
            "Path": "PathToAssembly
        }
    ]
    ```

4. <span data-ttu-id="fc3fe-151">En `BindingsFiles`, agregue los archivos de enlace para el proyecto de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-151">In `BindingsFiles`, add the binding files for your BizTalk project:</span></span> 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name"
            "Path": "PathToBindingFile
        }
    ]
    ```

5. <span data-ttu-id="fc3fe-152">En `DeploymentSequence`, agregue los nombres de aplicación en el orden que desea implementar e instalar en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-152">In `DeploymentSequence`, add the application names in the order you want them deployed, and installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span></span> 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```


6. <span data-ttu-id="fc3fe-153">**Guardar** los cambios.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-153">**Save** your changes.</span></span> <span data-ttu-id="fc3fe-154">Cuando termine, el archivo .json es similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-154">When finished, your .json file looks like the following:</span></span> 

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

7. <span data-ttu-id="fc3fe-155">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-155">**Optional**.</span></span> <span data-ttu-id="fc3fe-156">Haga clic en el proyecto de aplicación (por ejemplo, appProjectHelloWorld) y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-156">Right-click your application project (e.g. appProjectHelloWorld), and select **Properties**.</span></span> <span data-ttu-id="fc3fe-157">Puede establecer la versión de depuración o lanzamiento a un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-157">You can set the Debug or Release version to a new value.</span></span> <span data-ttu-id="fc3fe-158">Tenemos no en estos pasos, pero tenga en cuenta que puede hacer esto.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-158">We don’t in these steps, but be aware you can do this.</span></span>  

    ![Establezca la versión debug o release](../core/media/application-project-version.png)

8. <span data-ttu-id="fc3fe-160">Haga clic en el proyecto de aplicación (por ejemplo, appProjectHelloWorld) y seleccione **generar**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-160">Right-click your application project (e.g. appProjectHelloWorld), and select **Build**.</span></span> <span data-ttu-id="fc3fe-161">Si se realiza correctamente, se crea un archivo zip en  ***yourApplicationProject*\bin\debug** carpeta:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-161">If it succeeds, a zip file is created in ***yourApplicationProject*\bin\debug** folder:</span></span>  

    ![Compilar el archivo zip](../core/media/application-project-zip-file.png)

9. <span data-ttu-id="fc3fe-163">Seleccione la solución y seleccione la **Team Explorer** ficha. En VSTS, seleccione **conectar**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-163">Select your solution, and select the **Team Explorer** tab. Under VSTS, select **Connect**.</span></span>  

    ![Conectarse a Team Services](../core/media/connect-team-services.png)

10. <span data-ttu-id="fc3fe-165">Seleccione su cuenta VSTS, la colección y el proyecto de equipo.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-165">Select your VSTS account, your collection, and your team project.</span></span> <span data-ttu-id="fc3fe-166">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-166">Select **OK**.</span></span> <span data-ttu-id="fc3fe-167">Si no creó una cuenta VSTS aún, cree uno ([paso 2: crear el token VSTS](feature-pack-create-vsts-token.md) proporciona alguna orientación).</span><span class="sxs-lookup"><span data-stu-id="fc3fe-167">If you didn’t create a VSTS account yet, then create one ([Step 2: Create the VSTS token](feature-pack-create-vsts-token.md) provides some guidance).</span></span> <span data-ttu-id="fc3fe-168">Una vez creado, vuelva a este paso y conectarse.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-168">Once it's created, come back to this step, and connect.</span></span>  

    ![Seleccione la colección y el proyecto](../core/media/team-collections-projects.png)

11. <span data-ttu-id="fc3fe-170">Cuando se conecte, obtendrá un símbolo del sistema para clonar el repositorio.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-170">When you connect, you may get a prompt to clone this repository.</span></span> <span data-ttu-id="fc3fe-171">Seleccione el **clonar este repositorio** vínculo.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-171">Select the **Clone this repository** link.</span></span>  

    ![Clonar el repositorio](../core/media/vsts-clone-repository.png)

12. <span data-ttu-id="fc3fe-173">Tenga en cuenta la dirección URL y las rutas de acceso y seleccione **clon**:</span><span class="sxs-lookup"><span data-stu-id="fc3fe-173">Note the URL and paths, and select **Clone**:</span></span>  

    ![Rutas de acceso de repositorio](../core/media/clone-repo-paths.png)

<span data-ttu-id="fc3fe-175">Una vez completado, la tarea de implementación de Visual Studio Team Service respeta los archivos necesarios y la secuencia de instalación.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-175">Once completed, the Visual Studio Team Service deployment task honors the required files and the install sequence.</span></span> 

> [!TIP]
> <span data-ttu-id="fc3fe-176">Si realiza cambios en el proyecto después de realizar la clonación de git, puede **fase** los cambios y, a continuación, **Push**, todo ello en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-176">If you make changes to your project after you clone in git, you can **Stage** your changes, and then **Push**, all within Visual Studio.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="fc3fe-177">Lo que hizo</span><span class="sxs-lookup"><span data-stu-id="fc3fe-177">What you did</span></span>

<span data-ttu-id="fc3fe-178">En el proyecto de BizTalk, ha agregado un proyecto de aplicación de BizTalk (.btaproj).</span><span class="sxs-lookup"><span data-stu-id="fc3fe-178">In your BizTalk project, you added a BizTalk Application project (.btaproj).</span></span> <span data-ttu-id="fc3fe-179">Este proyecto se usa para automatizar las implementaciones de los proyectos de BizTalk Server mediante VSTS.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-179">This project is used to automate deployments of your BizTalk Server projects using VSTS.</span></span> <span data-ttu-id="fc3fe-180">Una vez creado el proyecto de aplicación, ha agregado una referencia al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-180">After you created the application project, you added a reference to your BizTalk project.</span></span> <span data-ttu-id="fc3fe-181">A continuación, se actualiza un archivo JSON que indica la implementación automatizada de qué archivos DLL se implementa, qué archivo de enlace que se utiliza y el orden para implementar las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fc3fe-181">Then, you updated a JSON file that tells the automated deployment what DLLs to deploy, which binding file to use, and the order to deploy the applications.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="fc3fe-182">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fc3fe-182">Next steps</span></span>
[<span data-ttu-id="fc3fe-183">Paso 2: Crear el token VSTS</span><span class="sxs-lookup"><span data-stu-id="fc3fe-183">Step 2: Create the VSTS token</span></span>](feature-pack-create-vsts-token.md)  
[<span data-ttu-id="fc3fe-184">Paso 3: Crear la compilación y las definiciones de la versión</span><span class="sxs-lookup"><span data-stu-id="fc3fe-184">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="fc3fe-185">Configurar las variables y tokens de entorno</span><span class="sxs-lookup"><span data-stu-id="fc3fe-185">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)