---
title: Implementar y administrar aplicaciones de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, managing
- Administration Console [BizTalk Server], applications
- bts06.deployment.application
- managing, applications
ms.assetid: d933ad2b-702b-48df-8ef6-a5702d0521e2
caps.latest.revision: "49"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f355c66f7550f5e4cf2b04cfc8bb1f705cc6ade7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-and-managing-biztalk-applications"></a><span data-ttu-id="459d9-102">Implementar y administrar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="459d9-102">Deploying and Managing BizTalk Applications</span></span>
<span data-ttu-id="459d9-103">En esta sección se proporciona información acerca de cómo administrar aplicaciones de BizTalk, además de cómo implementar, modificar, actualizar y anular la implementación de dichas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="459d9-103">This section provides information about managing BizTalk applications, including how to deploy, modify, update, and undeploy them.</span></span> <span data-ttu-id="459d9-104">Las aplicaciones de BizTalk proporcionan un modo de ver y administrar los elementos, denominados "artefactos", que constituyen la solución empresarial de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="459d9-104">BizTalk applications provide a way to view and manage the items, called "artifacts," that make up a BizTalk business solution.</span></span> <span data-ttu-id="459d9-105">Entre los ejemplos de artefactos podemos encontrar los ensamblados de BizTalk, los ensamblados .NET, los esquemas, las asignaciones, los enlaces, certificados, etc.</span><span class="sxs-lookup"><span data-stu-id="459d9-105">Examples of artifacts are BizTalk assemblies, .NET assemblies, schemas, maps, bindings, and certificates.</span></span>  
  
 <span data-ttu-id="459d9-106">Puede crear una aplicación de BizTalk y agregarle artefactos.</span><span class="sxs-lookup"><span data-stu-id="459d9-106">You can create a BizTalk application and add artifacts to it.</span></span> <span data-ttu-id="459d9-107">Después puede ver, empaquetar, implementar y administrar la aplicación y sus artefactos como una entidad única desde la consola de administración de BizTalk Server o mediante la herramienta de la línea de comandos BTSTask.</span><span class="sxs-lookup"><span data-stu-id="459d9-107">You can then view, package, deploy, and manage the application and its artifacts as a single entity from within the BizTalk Administration console or by using the BTSTask command-line tool.</span></span>  
  
 <span data-ttu-id="459d9-108">Para obtener información general acerca de la implementación de la aplicación de BizTalk y el mantenimiento, consulte [implementación de aplicación de BizTalk de descripción y administración](../core/understanding-biztalk-application-deployment-and-management.md).</span><span class="sxs-lookup"><span data-stu-id="459d9-108">For background information about BizTalk application deployment and maintenance, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="459d9-109">Para obtener instrucciones paso a paso sobre cómo implementar una aplicación sencilla, que le permitirá familiarizarse con las características de implementación de aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [Tutorial: implementar una aplicación básica de BizTalk](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="459d9-109">For step-by-step instructions on deploying a simple application, which will familiarize you with the application deployment features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="459d9-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="459d9-110">In This Section</span></span>  
  
-   [<span data-ttu-id="459d9-111">Prácticas recomendadas para implementar una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="459d9-111">Best Practices for Deploying a BizTalk Application</span></span>](../core/best-practices-for-deploying-a-biztalk-application.md)  
  
-   [<span data-ttu-id="459d9-112">Implementación de aplicaciones de BizTalk y listas de comprobación de administración</span><span class="sxs-lookup"><span data-stu-id="459d9-112">BizTalk Application Deployment and Management Checklists</span></span>](../core/biztalk-application-deployment-and-management-checklists.md)  
  
-   [<span data-ttu-id="459d9-113">Tutorial: Implementar una aplicación de BizTalk básico</span><span class="sxs-lookup"><span data-stu-id="459d9-113">Walkthrough: Deploying a Basic BizTalk Application</span></span>](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md) 
  
-   [<span data-ttu-id="459d9-114">Descripción de la implementación de aplicaciones de BizTalk y administración</span><span class="sxs-lookup"><span data-stu-id="459d9-114">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)  
  
-   [<span data-ttu-id="459d9-115">Cómo iniciar y detener una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="459d9-115">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)  
  
-   [<span data-ttu-id="459d9-116">Creación y modificación de las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="459d9-116">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)  
  
-   [<span data-ttu-id="459d9-117">Administrar artefactos</span><span class="sxs-lookup"><span data-stu-id="459d9-117">Managing Artifacts</span></span>](../core/managing-artifacts.md)  
  
-   [<span data-ttu-id="459d9-118">Personalizar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="459d9-118">Customizing Binding Files</span></span>](../core/customizing-binding-files.md)  
  
-   [<span data-ttu-id="459d9-119">Uso de secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicación</span><span class="sxs-lookup"><span data-stu-id="459d9-119">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)  
  
-   [<span data-ttu-id="459d9-120">Implementar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="459d9-120">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)  
  
-   [<span data-ttu-id="459d9-121">Actualizar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="459d9-121">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)  
  
-   [<span data-ttu-id="459d9-122">Anular la implementación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="459d9-122">Undeploying BizTalk Applications</span></span>](../core/undeploying-biztalk-applications.md)