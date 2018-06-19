---
title: Crear tokens de entorno y variables | Documentos de Microsoft"
description: Actualizar el archivo de enlace para utilizar los tokens de entorno y crear variables en VSTS para automatizar la implementación de aplicaciones de BizTalk Server
ms.custom: ''
ms.date: 11/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: 4
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d84fa393410e3084c87e762140530a45b0b78b5
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2017
ms.locfileid: "24054572"
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a><span data-ttu-id="c66cd-103">Configurar los tokens de entorno y variables para la implementación automática</span><span class="sxs-lookup"><span data-stu-id="c66cd-103">Configure environmental tokens and variables for automatic deployment</span></span>
<span data-ttu-id="c66cd-104">Usar variables de Visual Studio Team Services (VSTS) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="c66cd-104">Use Visual Studio Team Services (VSTS) variables in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] binding files.</span></span>

## <a name="overview"></a><span data-ttu-id="c66cd-105">Información general</span><span class="sxs-lookup"><span data-stu-id="c66cd-105">Overview</span></span>
<span data-ttu-id="c66cd-106">En un entorno de VSTS, puede agregar las variables y establecerlos en un valor.</span><span class="sxs-lookup"><span data-stu-id="c66cd-106">In a VSTS environment, you can add variables, and set them to a value.</span></span> <span data-ttu-id="c66cd-107">Por ejemplo, puede crear un *sendPortPath* variable y establezca su valor en una carpeta física en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c66cd-107">For example, you can create a *sendPortPath* variable, and set its value to a physical folder on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="c66cd-108">En el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] archivo de enlace de la aplicación, las variables configurables pueden ser cualquier elemento dentro de una etiqueta XML, como el nombre de la ubicación de recepción, host, URI del puerto de envío y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="c66cd-108">Within the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] application binding file, the configurable variables can be anything within an XML tag, such as the receive location name, host, send port URI, and so on.</span></span> 

<span data-ttu-id="c66cd-109">Estas variables son específicas de su entorno de VSTS y puede utilizarse para implementar la misma aplicación para varios [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos.</span><span class="sxs-lookup"><span data-stu-id="c66cd-109">These variables are specific to your VSTS environment, and can be used to deploy the same application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span> 

<span data-ttu-id="c66cd-110">Le mostramos cómo agregar la variable VSTS en el archivo de enlace y cómo crear la variable dentro de VSTS.</span><span class="sxs-lookup"><span data-stu-id="c66cd-110">We show you how to add the VSTS variable in your binding file, and how to create the variable within VSTS.</span></span> 

## <a name="add-variables-to-the-binding-file"></a><span data-ttu-id="c66cd-111">Agregar variables para el archivo de enlace</span><span class="sxs-lookup"><span data-stu-id="c66cd-111">Add variables to the binding file</span></span>

1. <span data-ttu-id="c66cd-112">Abra el archivo de enlace de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="c66cd-112">Open the application binding file:</span></span>

    ![Abra el archivo de enlace](../core/media/biztalk-feature-pack-1-binding-1.png)

2. <span data-ttu-id="c66cd-114">Busque el elemento que desea cambiar:</span><span class="sxs-lookup"><span data-stu-id="c66cd-114">Find the element you want to change:</span></span>

    ![Seleccione el elemento](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. <span data-ttu-id="c66cd-116">Quitar el valor rellenado y reemplazarlo con usted variables: `$(YourValue)`.</span><span class="sxs-lookup"><span data-stu-id="c66cd-116">Remove the populated value, and replace it with you variables: `$(YourValue)`.</span></span> <span data-ttu-id="c66cd-117">Por ejemplo, escriba `$(SendPort1)`:</span><span class="sxs-lookup"><span data-stu-id="c66cd-117">For example, enter `$(SendPort1)`:</span></span> 

    ![Archivo de enlace](../core/media/biztalk-feature-pack-1-binding-3.png)

4. <span data-ttu-id="c66cd-119">Cuando haya terminado, guarde el archivo de enlace y agregarlo a la plantilla de compilación JSON (pasos de [paso 1: plantilla de aplicación Agregar proyecto & actualización .json](feature-pack-add-application-project.md)).</span><span class="sxs-lookup"><span data-stu-id="c66cd-119">When done, save the binding file, and add it to your JSON build template (steps in [Step 1: Add Application project & update .json template](feature-pack-add-application-project.md)).</span></span>

## <a name="create-the-variables-in-vsts"></a><span data-ttu-id="c66cd-120">Cree las variables en VSTS</span><span class="sxs-lookup"><span data-stu-id="c66cd-120">Create the variables in VSTS</span></span>

1. <span data-ttu-id="c66cd-121">En su cuenta VSTS, seleccione **de compilación y la versión**y seleccione **versiones**.</span><span class="sxs-lookup"><span data-stu-id="c66cd-121">In your VSTS account, select **Build and release**, and select **Releases**.</span></span>

2. <span data-ttu-id="c66cd-122">Seleccione el **definición de la versión**y seleccione **Variables**:</span><span class="sxs-lookup"><span data-stu-id="c66cd-122">Select your **Release definition**, and select **Variables**:</span></span>  

    ![Archivo de enlace](../core/media/vsts-release-variables.png)

3. <span data-ttu-id="c66cd-124">Seleccione **agregar**y cree los nombres de las variables y valores:</span><span class="sxs-lookup"><span data-stu-id="c66cd-124">Select **Add**, and create the variable names and values:</span></span>   

    ![configurar variables](../core/media/environment-specific-variables.png)

4. <span data-ttu-id="c66cd-126">**Guardar** los cambios.</span><span class="sxs-lookup"><span data-stu-id="c66cd-126">**Save** your changes.</span></span> <span data-ttu-id="c66cd-127">Cuando se inicia la implementación, los valores se agregan desde el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="c66cd-127">When the deploy is initiated, the values are added from the binding file.</span></span>

## <a name="see-also"></a><span data-ttu-id="c66cd-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c66cd-128">See also</span></span>
[<span data-ttu-id="c66cd-129">Configurar la implementación automática con Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="c66cd-129">Configure automatic deployment with Visual Studio Team Services</span></span>](configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  
[<span data-ttu-id="c66cd-130">Configuración del Feature Pack</span><span class="sxs-lookup"><span data-stu-id="c66cd-130">Configure the feature pack</span></span>](configure-the-feature-pack.md)