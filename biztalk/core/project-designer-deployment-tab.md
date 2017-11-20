---
title: "Diseñador de proyectos: Pestaña de implementación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties, Configuration database [BizTalk Server]
- Redeploy property
- configuration properties [deployment], Server property
- Server property
- configuration properties [deployment], Install to Global Assembly Cache (GAC) property
- properties, Management database
- Install to Global Assembly Cache (GAC) property
- Configuration database [BizTalk Server], properties
- Management database, properties
- Administration Group property
- configuration properties [deployment], Redeploy property
- configuration properties [deployment], Management database property
- configuration properties [deployment], Administration Group property
ms.assetid: 5b64f99c-4ec6-4ed3-8590-46420e2f75b8
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972f3956a19d66d47238ee8170584b4faf6ba886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="project-designer-deployment-tab"></a><span data-ttu-id="8f535-102">Diseñador de proyectos: pestaña Implementación</span><span class="sxs-lookup"><span data-stu-id="8f535-102">Project Designer: Deployment Tab</span></span>
<span data-ttu-id="8f535-103">El **implementación** ficha de propiedades del Diseñador de proyectos le permite configurar los atributos de implementación del proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8f535-103">The **Deployment** property tab of the Project Designer allows you to configure the deployment attributes for the BizTalk project.</span></span> <span data-ttu-id="8f535-104">Debe configurar tanto el **Server** y la **base de datos de configuración** (también conocido como la base de datos de administración de BizTalk) propiedades como un conjunto para la implementación se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="8f535-104">You must configure both the **Server** and the **Configuration Database** (also known as the BizTalk Management database) properties as a set for deployment to be successful.</span></span>  
  
## <a name="application-name"></a><span data-ttu-id="8f535-105">Application Name</span><span class="sxs-lookup"><span data-stu-id="8f535-105">Application Name</span></span>  
 <span data-ttu-id="8f535-106">Especificar la aplicación de BizTalk en la que se va a implementar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8f535-106">Specify the BizTalk application in which to deploy the assembly.</span></span> <span data-ttu-id="8f535-107">Si está vacío, el proyecto se implementará en la aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8f535-107">If this is empty, the project will be deployed into the default application.</span></span>  
  
## <a name="configuration-database"></a><span data-ttu-id="8f535-108">Base de datos de configuración</span><span class="sxs-lookup"><span data-stu-id="8f535-108">Configuration Database</span></span>  
 <span data-ttu-id="8f535-109">Este campo se utiliza para especificar el nombre de la base de datos de configuración de BizTalk para el ensamblado implementado.</span><span class="sxs-lookup"><span data-stu-id="8f535-109">You use this field to specify the name of the BizTalk Configuration database for the deployed assembly.</span></span> <span data-ttu-id="8f535-110">Esto es aplicable si ha configurado el proyecto de BizTalk como un proyecto de implementación.</span><span class="sxs-lookup"><span data-stu-id="8f535-110">This applies if you have configured the BizTalk project as a deployment project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f535-111">La base de datos de configuración de BizTalk también se llama base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8f535-111">The BizTalk Configuration database is also referred to as the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="8f535-112">El nombre de la base de datos de configuración predeterminada es BizTalkMgmtDb.</span><span class="sxs-lookup"><span data-stu-id="8f535-112">The default Configuration database name is BizTalkMgmtDb.</span></span>  
  
## <a name="server"></a><span data-ttu-id="8f535-113">Server</span><span class="sxs-lookup"><span data-stu-id="8f535-113">Server</span></span>  
 <span data-ttu-id="8f535-114">Éste es el nombre del servidor en el que está ubicado el Repositorio de configuración (también conocido como base de datos de administración o de configuración de BizTalk).</span><span class="sxs-lookup"><span data-stu-id="8f535-114">This is the name of the server where the Configuration repository (also known as the BizTalk Management or Configuration database) is located.</span></span> <span data-ttu-id="8f535-115">El proyecto de BizTalk se implementa en este servidor si configura el proyecto de BizTalk como "Implementación".</span><span class="sxs-lookup"><span data-stu-id="8f535-115">You deploy the BizTalk project to this server if you configure the BizTalk project as "Deployment."</span></span>  
  
## <a name="redeploy"></a><span data-ttu-id="8f535-116">Volver a implementar</span><span class="sxs-lookup"><span data-stu-id="8f535-116">Redeploy</span></span>  
 <span data-ttu-id="8f535-117">Usa el **volver a implementar** propiedad para determinar si se debe eliminar la configuración existente y volver a crear la configuración cada vez que implemente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8f535-117">You use the **Redeploy** property to determine whether to delete the existing configuration and re-create the configuration each time you deploy the assembly.</span></span> <span data-ttu-id="8f535-118">El valor predeterminado es `True`.</span><span class="sxs-lookup"><span data-stu-id="8f535-118">The default value is `True`.</span></span>  
  
## <a name="install-to-global-assembly-cache"></a><span data-ttu-id="8f535-119">Instalar caché de ensamblados total (GAC)</span><span class="sxs-lookup"><span data-stu-id="8f535-119">Install to Global Assembly Cache</span></span>  
 <span data-ttu-id="8f535-120">Usa el **instalar en la caché Global de ensamblados** propiedad para indicar si [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] necesita instalar el ensamblado de BizTalk a la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="8f535-120">You use the **Install to Global Assembly Cache** property to indicate if [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] needs to install the BizTalk assembly to the global assembly cache (GAC).</span></span>  
  
## <a name="restart-host-instances"></a><span data-ttu-id="8f535-121">Reiniciar instancias de host</span><span class="sxs-lookup"><span data-stu-id="8f535-121">Restart Host Instances</span></span>  
 <span data-ttu-id="8f535-122">Si establece **reiniciar instancias de Host** a **True**, las instancias de host en el equipo local se reiniciará cuando se implementa el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f535-122">If you set **Restart Host Instances** to **True**, the host instances on the local computer will be restarted when the project is deployed by [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="8f535-123">Esto resulta útil durante el ciclo de desarrollo cuando se hacen cambios y, con frecuencia, vuelve a realizarse la implementación; no tendrá que reiniciar manualmente las instancias de host relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8f535-123">This is useful during the development cycle when you are making changes and frequently redeploying; you will not have to manually restart related host instances.</span></span>  
  
 <span data-ttu-id="8f535-124">Si no reinicia las instancias de host relacionadas, los últimos cambios no se verán reflejados en la aplicación de BizTalk porque es posible que la versión antigua esté aún almacenada en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8f535-124">If you do not restart related host instances, your latest changes may not be reflected in your BizTalk application because the old version may still be cached.</span></span> <span data-ttu-id="8f535-125">Reiniciar la instancia de host purga los ensamblados almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="8f535-125">Restarting the host instance purges cached assemblies.</span></span>  
  
## <a name="enable-unit-testing"></a><span data-ttu-id="8f535-126">Habilitar pruebas de unidades</span><span class="sxs-lookup"><span data-stu-id="8f535-126">Enable Unit Testing</span></span>  
 <span data-ttu-id="8f535-127">Se especifica si se va a habilitar la prueba de unidad para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8f535-127">Specified whether to enable unit testing for the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f535-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f535-128">See Also</span></span>  
 <span data-ttu-id="8f535-129">[Cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="8f535-129">[How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span></span>  
 [<span data-ttu-id="8f535-130">Ventana de propiedades de proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8f535-130">BizTalk Project Properties Window</span></span>](../core/biztalk-project-properties-window.md)