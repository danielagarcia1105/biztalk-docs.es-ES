---
title: "Configurar los tokens de entorno y variables para la implementación automática | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 7d148f79fceb68b24feb45882ab89767369ed7e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a><span data-ttu-id="567fb-102">Configurar los tokens de entorno y variables para la implementación automática</span><span class="sxs-lookup"><span data-stu-id="567fb-102">Configure environmental tokens and variables for automatic deployment</span></span>
<span data-ttu-id="567fb-103">Usar variables de Visual Studio Team Services (VSTS) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="567fb-103">Use Visual Studio Team Services (VSTS) variables in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] binding files.</span></span>

## <a name="overview"></a><span data-ttu-id="567fb-104">Información general</span><span class="sxs-lookup"><span data-stu-id="567fb-104">Overview</span></span>
<span data-ttu-id="567fb-105">En un entorno de VSTS, puede agregar las variables y establecerlos en un valor.</span><span class="sxs-lookup"><span data-stu-id="567fb-105">In a VSTS environment, you can add variables, and set them to a value.</span></span> <span data-ttu-id="567fb-106">Por ejemplo, puede crear un *sendPortPath* variable y establezca su valor en una carpeta física en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="567fb-106">For example, you can create a *sendPortPath* variable, and set its value to a physical folder on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="567fb-107">En el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] archivo de enlace de la aplicación, las variables configurables pueden ser cualquier elemento dentro de una etiqueta XML, como el nombre de la ubicación de recepción, host, URI del puerto de envío y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="567fb-107">Within the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] application binding file, the configurable variables can be anything within an XML tag, such as the receive location name, host, send port URI, and so on.</span></span> 

<span data-ttu-id="567fb-108">Estas variables son específicas de su entorno de VSTS y puede utilizarse para implementar la misma aplicación para varios [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos.</span><span class="sxs-lookup"><span data-stu-id="567fb-108">These variables are specific to your VSTS environment, and can be used to deploy the same application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span> 

<span data-ttu-id="567fb-109">En este tema, se muestra cómo se agrega la variable VSTS en el archivo de enlace y cómo crear la variable dentro de VSTS.</span><span class="sxs-lookup"><span data-stu-id="567fb-109">In this topic, we show you how add the VSTS variable in your binding file, and how to create the variable within VSTS.</span></span> 

## <a name="configure-the-variables-in-your-biztalk-binding-file"></a><span data-ttu-id="567fb-110">Configurar las variables en el archivo de enlace de BizTalk</span><span class="sxs-lookup"><span data-stu-id="567fb-110">Configure the variables in your BizTalk Binding file</span></span>

<span data-ttu-id="567fb-111">El ejemplo siguiente es una parte de una [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] el archivo de enlace y muestra cómo aplicar los tokens.</span><span class="sxs-lookup"><span data-stu-id="567fb-111">The following example is a part of a [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] binding file, and shows how to apply the tokens.</span></span>

1. <span data-ttu-id="567fb-112">Abra el archivo de enlace de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="567fb-112">Open the application binding file:</span></span>

    ![Paquete de características de BizTalk 1 enlace 1](../core/media/biztalk-feature-pack-1-binding-1.png)

2. <span data-ttu-id="567fb-114">Busque el elemento que desea cambiar:</span><span class="sxs-lookup"><span data-stu-id="567fb-114">Find the element you want to change:</span></span>

    ![Paquete de características de BizTalk 1 enlace 2](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. <span data-ttu-id="567fb-116">Quitar el valor rellenado y reemplazarlo con usted variables: `$(YourValue)`.</span><span class="sxs-lookup"><span data-stu-id="567fb-116">Remove the populated value, and replace it with you variables: `$(YourValue)`.</span></span> <span data-ttu-id="567fb-117">Por ejemplo, escriba `$(SendPort1)`:</span><span class="sxs-lookup"><span data-stu-id="567fb-117">For example, enter `$(SendPort1)`:</span></span> 

    ![Paquete de características de BizTalk 1 enlace 3](../core/media/biztalk-feature-pack-1-binding-3.png)


4. <span data-ttu-id="567fb-119">Cuando haya terminado, guarde el archivo de enlace y aplicarlo a la plantilla de compilación JSON.</span><span class="sxs-lookup"><span data-stu-id="567fb-119">When done, save the binding file, and apply it to your JSON build template.</span></span>
5. <span data-ttu-id="567fb-120">Inicie sesión la solución de Visual Studio Team Service y seleccione **de compilación y la versión**.</span><span class="sxs-lookup"><span data-stu-id="567fb-120">Sign in to your Visual Studio Team Service solution, and select **Build and release**.</span></span>
6. <span data-ttu-id="567fb-121">Vaya a **versión**.</span><span class="sxs-lookup"><span data-stu-id="567fb-121">Go to **Release**.</span></span> <span data-ttu-id="567fb-122">Seleccione el **definición de la versión**, o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="567fb-122">Select your **Release definition**, or create a new one.</span></span>
7. <span data-ttu-id="567fb-123">En **entornos**, seleccione **agregar un nuevo entorno**, o cambiar a un entorno existente:</span><span class="sxs-lookup"><span data-stu-id="567fb-123">Under **Environments**, select **Add a new environment**, or change to an existing environment:</span></span> 

    ![Agregar un nuevo entorno](../core/media/add-a-new-environment.png)

8. <span data-ttu-id="567fb-125">Haga clic en el botón de puntos suspensivos y seleccione **configurar variables**:</span><span class="sxs-lookup"><span data-stu-id="567fb-125">Click the ellipses, and select **configure variables**:</span></span>

    ![configurar variables](../core/media/configure-variables.png)

9. <span data-ttu-id="567fb-127">Mediante la adición de las variables para cada entorno, mediante los nombres de token que creó en el archivo de enlace, puede implementar las aplicaciones en varios entornos con distintos valores:</span><span class="sxs-lookup"><span data-stu-id="567fb-127">By adding the variables for each environment, using the token names created in the binding file, you can deploy your applications to multiple environments with different values:</span></span>

    ![variables de entorno específicas](../core/media/environment-specific-variables.png)
    
10. <span data-ttu-id="567fb-129">Seleccione **Aceptar** para guardar las nuevas variables.</span><span class="sxs-lookup"><span data-stu-id="567fb-129">Select **OK** to save the new variables.</span></span>
11. <span data-ttu-id="567fb-130">Una vez que se inicia la compilación, se agregan los valores del archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="567fb-130">Once the build is initiated, the values are added from binding file.</span></span>

## <a name="next-step"></a><span data-ttu-id="567fb-131">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="567fb-131">Next step</span></span>
[<span data-ttu-id="567fb-132">Agregar una aplicación de BizTalk a VSTS</span><span class="sxs-lookup"><span data-stu-id="567fb-132">Add a BizTalk application to VSTS</span></span>](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)