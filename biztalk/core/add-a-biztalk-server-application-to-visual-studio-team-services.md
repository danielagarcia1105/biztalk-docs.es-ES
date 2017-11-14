---
redirect_url: /biztalk/core/feature-pack-add-application-project/
redirect_document_id: True
ROBOTS: NOINDEX
title: "Agregar una aplicación de BizTalk Server para Visual Studio Team Services | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2c7a1ff-0f26-45f3-9a9b-4c99a67b51a9
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 1a6b7ba32c0077b3df107b00525bb34ef011e483
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2017
---
# <a name="add-a-biztalk-server-application-to-visual-studio-team-services"></a><span data-ttu-id="5113f-102">Agregar una aplicación de BizTalk Server para Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="5113f-102">Add a BizTalk Server application to Visual Studio Team Services</span></span>
<span data-ttu-id="5113f-103">Agregar un [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] proyecto VSTS para implementar automáticamente mediante la integración continua.</span><span class="sxs-lookup"><span data-stu-id="5113f-103">Add a [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] project to VSTS to automatically deploy using continuous integration.</span></span>  

<span data-ttu-id="5113f-104">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , se pueden implementar automáticamente las aplicaciones para su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos con Visual Studio Team Services (VSTS).</span><span class="sxs-lookup"><span data-stu-id="5113f-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can automatically deploy your applications to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments using Visual Studio Team Services (VSTS).</span></span> 

<span data-ttu-id="5113f-105">Estos temas se proporciona información general y se enumeran los pasos claves para implementar la solución de Visual Studio para su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5113f-105">This topics provides an overview, and lists the key steps to deploy your solution from Visual Studio to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5113f-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5113f-106">Prerequisites</span></span>
* <span data-ttu-id="5113f-107">Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5113f-107">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* [<span data-ttu-id="5113f-108">Paso 3: Crear la compilación y las definiciones de la versión</span><span class="sxs-lookup"><span data-stu-id="5113f-108">Step 3: Create the build and release definitions</span></span>](../core/feature-pack-add-build-release-definitions.md)
* <span data-ttu-id="5113f-109">Conocimientos y experiencia en Git y repositorios en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5113f-109">Knowledge and experience working with Git and repositories in Visual Studio.</span></span> <span data-ttu-id="5113f-110">Si está familiarizado en repositorios y control de versiones, puede tratarse de buenos recursos:</span><span class="sxs-lookup"><span data-stu-id="5113f-110">If you're brand new to repositories and version control, these may be good resources:</span></span> 

    [<span data-ttu-id="5113f-111">Obtenga información acerca de Git</span><span class="sxs-lookup"><span data-stu-id="5113f-111">Learn Git</span></span>](https://www.visualstudio.com/learn-git/)  
    [<span data-ttu-id="5113f-112">GIT y Team Services</span><span class="sxs-lookup"><span data-stu-id="5113f-112">Git and Team Services</span></span>](https://www.visualstudio.com/docs/git/overview)
* <span data-ttu-id="5113f-113">Conocimientos y experiencia de trabajar con proyectos de BizTalk en[!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5113f-113">Knowledge and experience working with BizTalk projects in [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]</span></span>

## <a name="add-biztalk-project-to-vsts"></a><span data-ttu-id="5113f-114">Agregar proyecto de BizTalk a VSTS</span><span class="sxs-lookup"><span data-stu-id="5113f-114">Add BizTalk project to VSTS</span></span>
1. <span data-ttu-id="5113f-115">En **Visual Studio**, conectarse a su **repositorio de código fuente**, y **clon** a su equipo.</span><span class="sxs-lookup"><span data-stu-id="5113f-115">In **Visual Studio**, connect to your **Source repository**, and **Clone** it to your machine.</span></span>
2. <span data-ttu-id="5113f-116">Abra o cree una **proyecto de BizTalk** (.btproj).</span><span class="sxs-lookup"><span data-stu-id="5113f-116">Open or Create a **BizTalk Project** (.btproj).</span></span>

   > [!NOTE]
   > <span data-ttu-id="5113f-117">Puede agregar varios proyectos en la misma solución.</span><span class="sxs-lookup"><span data-stu-id="5113f-117">You can add multiple project into the same solution.</span></span>
   
3. <span data-ttu-id="5113f-118">Agregue un nuevo **proyecto de aplicación de BizTalk Server** (.btaproj).</span><span class="sxs-lookup"><span data-stu-id="5113f-118">Add a new **BizTalk Server Application Project** (.btaproj).</span></span>
4. <span data-ttu-id="5113f-119">Haga clic en el proyecto en el **el Explorador de soluciones**y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5113f-119">Right-click the project in the **Solution Explorer**, and select **Properties**.</span></span>
5. <span data-ttu-id="5113f-120">Configurar la **versión** y las propiedades de conexión para su **Visual Studio Team Services** cuenta.</span><span class="sxs-lookup"><span data-stu-id="5113f-120">Configure the **Version** and the connection properties to your **Visual Studio Team Services** account.</span></span>

    ![Visual Studio configuración FP1 BizTalk](../core/media/visual-studio-configuration-fp1-biztalk.png)

6. <span data-ttu-id="5113f-122">Agregue todos los ensamblados y los artefactos necesarios para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5113f-122">Add all the assemblies and artifacts needed by your application.</span></span>
7. <span data-ttu-id="5113f-123">Actualización de la **binding.xml** archivo con la información de enlace correcto.</span><span class="sxs-lookup"><span data-stu-id="5113f-123">Update the **binding.xml** file with the correct binding information.</span></span>
8. <span data-ttu-id="5113f-124">Actualización de la **BizTalkServerInventory.json** con todos los artefactos y el orden correcto para los artefactos que estén instalados en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5113f-124">Update the **BizTalkServerInventory.json** with all the artifacts, and the correct order for the artifacts to be installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>
9. <span data-ttu-id="5113f-125">Haga clic en y **generar** la solución para comprobar si hay algún error.</span><span class="sxs-lookup"><span data-stu-id="5113f-125">Right-click and **build** your solution to check for any errors.</span></span> 
10. <span data-ttu-id="5113f-126">Cuando la compilación finalice correctamente, haga clic en la solución y seleccione **implementar**.</span><span class="sxs-lookup"><span data-stu-id="5113f-126">When the build completes successfully, right-click your solution, and select **Deploy**.</span></span>
11. <span data-ttu-id="5113f-127">La aplicación debe implementarse automáticamente a su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5113f-127">Your application should automatically deploy to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="5113f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5113f-128">See also</span></span>
[<span data-ttu-id="5113f-129">Configurar el Feature Pack</span><span class="sxs-lookup"><span data-stu-id="5113f-129">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)