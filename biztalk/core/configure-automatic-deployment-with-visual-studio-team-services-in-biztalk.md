---
title: "Configurar la implementación automática con Visual Studio Team Services | Documentos de Microsoft"
description: "Instalar BizTalk Feature Pack para usar la administración del ciclo de vida de aplicaciones con VSTS para implementar las aplicaciones en diferentes entornos de BizTalk."
ms.custom: 
ms.date: 11/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04a7d2b2430a5dc57403fc179fa1c1859d3a82b3
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2017
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a><span data-ttu-id="82c63-103">Configurar la implementación automática con Visual Studio Team Services en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="82c63-103">Configure automatic deployment with Visual Studio Team Services in BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="82c63-104">Información general</span><span class="sxs-lookup"><span data-stu-id="82c63-104">Overview</span></span>

<span data-ttu-id="82c63-105">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] proporciona una implementación automática mejorada y experiencia con aplicaciones lifecycle management (ALM).</span><span class="sxs-lookup"><span data-stu-id="82c63-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] provides an improved automatic deployment and application lifecycle management (ALM) experience.</span></span> 

<span data-ttu-id="82c63-106">Con Visual Studio Team Services, puede implementar automáticamente [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] aplicaciones para diferentes entornos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="82c63-106">Using Visual Studio Team Services, you can automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] applications to different BizTalk environments.</span></span> 

<span data-ttu-id="82c63-107">Por lo general, hay dos roles implicados:</span><span class="sxs-lookup"><span data-stu-id="82c63-107">Typically, there are two roles involved:</span></span>

- <span data-ttu-id="82c63-108">Programador de BizTalk crea la aplicación y genera de forma local.</span><span class="sxs-lookup"><span data-stu-id="82c63-108">BizTalk developer creates the application, and builds it locally.</span></span> <span data-ttu-id="82c63-109">A continuación, comprueba si la aplicación en Git o Control de versiones de Team Foundation.</span><span class="sxs-lookup"><span data-stu-id="82c63-109">Then, checks the application into Git or Team Foundation Version Control.</span></span>
- <span data-ttu-id="82c63-110">Administrador VSTS crea las definiciones de compilación y versión e implementa en la aplicación de BizTalk para diferentes entornos (desarrollo, UAT, producción).</span><span class="sxs-lookup"><span data-stu-id="82c63-110">VSTS admin creates the build and release definitions, and deploys to the BizTalk application to different environments (Dev, UAT, Production).</span></span>

<span data-ttu-id="82c63-111">Si nunca ha utilizado VSTS, este tutorial puede ser un desafío.</span><span class="sxs-lookup"><span data-stu-id="82c63-111">If you’ve never used VSTS, this walkthrough may be challenging.</span></span> <span data-ttu-id="82c63-112">Requieren ciertos conocimientos de git, incluida la clonación e insertar los cambios.</span><span class="sxs-lookup"><span data-stu-id="82c63-112">It does require some understanding of git, including cloning, and pushing changes.</span></span> 

<span data-ttu-id="82c63-113">Le mostramos cómo configurar VSTS con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]y agregar su primera aplicación para la implementación.</span><span class="sxs-lookup"><span data-stu-id="82c63-113">We show you how to setup VSTS with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and add your first application to deploy.</span></span> <span data-ttu-id="82c63-114">Se recomienda que haga referencia a la [instrucciones de VSTS](https://docs.microsoft.com/vsts/user-guide/), tal y como se cambia la UI VSTS.</span><span class="sxs-lookup"><span data-stu-id="82c63-114">We recommend you refer to the [VSTS guidance](https://docs.microsoft.com/vsts/user-guide/), as the VSTS UI changes.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="82c63-115">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="82c63-115">Before you begin</span></span>

* <span data-ttu-id="82c63-116">Tener una cuenta de Visual Studio Team Services (VSTS) listo.</span><span class="sxs-lookup"><span data-stu-id="82c63-116">Have your Visual Studio Team Services (VSTS) account ready.</span></span> <span data-ttu-id="82c63-117">¿No tiene?</span><span class="sxs-lookup"><span data-stu-id="82c63-117">Don't have one?</span></span> <span data-ttu-id="82c63-118">[Registrarse para obtener Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).</span><span class="sxs-lookup"><span data-stu-id="82c63-118">[Sign up for Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).</span></span>
* <span data-ttu-id="82c63-119">Si ya tiene un agente de VSTS instalado en el equipo de BizTalk, el agente existente se sobrescribe con el agente de VSTS más reciente.</span><span class="sxs-lookup"><span data-stu-id="82c63-119">If you already have a VSTS Agent installed on your BizTalk computer, then the existing agent is overwritten with the latest VSTS Agent.</span></span> <span data-ttu-id="82c63-120">Quizás tenga que actualizar su [servicio VSTS para alinearlo con el nuevo agente](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).</span><span class="sxs-lookup"><span data-stu-id="82c63-120">You may have to update your [VSTS service to align with the new agent](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).</span></span>
* <span data-ttu-id="82c63-121">Implementación automática con VSTS se realiza en una [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo.</span><span class="sxs-lookup"><span data-stu-id="82c63-121">Automatic deployment with VSTS is done on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="82c63-122">Asegúrese de que el equipo tiene Visual Studio y la [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] instalado SDK y herramientas de programadores.</span><span class="sxs-lookup"><span data-stu-id="82c63-122">Be sure the computer has Visual Studio and the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Developer Tools and SDK installed.</span></span> <span data-ttu-id="82c63-123">Consulte la [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [requisitos de hardware y software](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="82c63-123">See the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [hardware and software requirements](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="82c63-124">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="82c63-124">Prerequisites</span></span>

* <span data-ttu-id="82c63-125">Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82c63-125">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="82c63-126">Algunos experiencia y conocimientos de crear y trabajar con definiciones de VSTS.</span><span class="sxs-lookup"><span data-stu-id="82c63-126">Some experience and knowledge with creating and working with definitions in VSTS.</span></span> <span data-ttu-id="82c63-127">Si está familiarizado en VSTS, puede tratarse de buenos recursos:</span><span class="sxs-lookup"><span data-stu-id="82c63-127">If you're brand new to VSTS, these may be good resources:</span></span> 

  [<span data-ttu-id="82c63-128">Introducción a Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="82c63-128">Visual Studio Team Services overview</span></span>](https://www.visualstudio.com/docs/overview)  
  [<span data-ttu-id="82c63-129">Elemento de configuración/CD para principiantes</span><span class="sxs-lookup"><span data-stu-id="82c63-129">CI/CD for newbies</span></span>](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a><span data-ttu-id="82c63-130">Introducción</span><span class="sxs-lookup"><span data-stu-id="82c63-130">Get started</span></span>
[<span data-ttu-id="82c63-131">Paso 1: Agregar proyecto de aplicación & Actualizar plantilla .json</span><span class="sxs-lookup"><span data-stu-id="82c63-131">Step 1: Add Application project & update .json template</span></span>](feature-pack-add-application-project.md)  

[<span data-ttu-id="82c63-132">Paso 2: Crear el token VSTS e instalar al agente de compilación</span><span class="sxs-lookup"><span data-stu-id="82c63-132">Step 2: Create the VSTS token & install the build agent</span></span>](feature-pack-create-vsts-token.md)

[<span data-ttu-id="82c63-133">Paso 3: Crear la compilación y las definiciones de la versión</span><span class="sxs-lookup"><span data-stu-id="82c63-133">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)

[<span data-ttu-id="82c63-134">Configurar las variables y tokens de entorno</span><span class="sxs-lookup"><span data-stu-id="82c63-134">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)