---
title: "Cómo las Variables de entorno indican el estado de implementación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: scripts, variables
ms.assetid: 022b782b-008d-41a7-9880-d1c4e5e4015e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 041e77eadb7c1b62e3441ee3b3c138203299f3a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-environment-variables-indicate-deployment-state"></a><span data-ttu-id="e2184-102">Cómo las variables de entorno indican el estado de la implementación</span><span class="sxs-lookup"><span data-stu-id="e2184-102">How Environment Variables Indicate Deployment State</span></span>
<span data-ttu-id="e2184-103">Una vez invocada, una secuencia de comandos previa o posterior al procesamiento puede determinar el estado de implementación (instalar, importar, eliminar, desinstalar, deshacer importación o deshacer instalación) que se está ejecutando mediante la comprobación de las variables de entorno BTAD_ChangeRequestAction, BTAD_InstallMode y BTAD_HostClass.</span><span class="sxs-lookup"><span data-stu-id="e2184-103">Once invoked, a pre- or post-processing script can determine in which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode and BTAD_HostClass.</span></span>  
  
 <span data-ttu-id="e2184-104">En la tabla siguiente se describen las combinaciones de las tres variables que indican los distintos estados de la implementación.</span><span class="sxs-lookup"><span data-stu-id="e2184-104">The following table describes the combinations of the three variables that indicate the different deployment states.</span></span>  
  
|<span data-ttu-id="e2184-105">Estado de implementación</span><span class="sxs-lookup"><span data-stu-id="e2184-105">Deployment State</span></span>|<span data-ttu-id="e2184-106">Valores esperados</span><span class="sxs-lookup"><span data-stu-id="e2184-106">Expected Values</span></span>|  
|----------------------|---------------------|  
||<span data-ttu-id="e2184-107">BTAD_ChangeRequestAction</span><span class="sxs-lookup"><span data-stu-id="e2184-107">BTAD_ChangeRequestAction</span></span>|<span data-ttu-id="e2184-108">BTAD_InstallMode</span><span class="sxs-lookup"><span data-stu-id="e2184-108">BTAD_InstallMode</span></span>|<span data-ttu-id="e2184-109">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="e2184-109">BTAD_HostClass</span></span>|  
|<span data-ttu-id="e2184-110">Importar sin marca de sobrescritura</span><span class="sxs-lookup"><span data-stu-id="e2184-110">Import without overwrite flag</span></span>|<span data-ttu-id="e2184-111">Crear</span><span class="sxs-lookup"><span data-stu-id="e2184-111">Create</span></span>|<span data-ttu-id="e2184-112">Importar</span><span class="sxs-lookup"><span data-stu-id="e2184-112">Import</span></span>|<span data-ttu-id="e2184-113">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="e2184-113">ConfigurationDb</span></span>|  
|<span data-ttu-id="e2184-114">Importar con marca de sobrescritura</span><span class="sxs-lookup"><span data-stu-id="e2184-114">Import with overwrite flag</span></span>|<span data-ttu-id="e2184-115">Update</span><span class="sxs-lookup"><span data-stu-id="e2184-115">Update</span></span>|<span data-ttu-id="e2184-116">Importar</span><span class="sxs-lookup"><span data-stu-id="e2184-116">Import</span></span>|<span data-ttu-id="e2184-117">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="e2184-117">ConfigurationDb</span></span>|  
|<span data-ttu-id="e2184-118">Install</span><span class="sxs-lookup"><span data-stu-id="e2184-118">Install</span></span>|<span data-ttu-id="e2184-119">Update</span><span class="sxs-lookup"><span data-stu-id="e2184-119">Update</span></span>|<span data-ttu-id="e2184-120">Install</span><span class="sxs-lookup"><span data-stu-id="e2184-120">Install</span></span>|<span data-ttu-id="e2184-121">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="e2184-121">BizTalkHostInstance</span></span>|  
|<span data-ttu-id="e2184-122">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="e2184-122">Uninstall</span></span>|<span data-ttu-id="e2184-123">DELETE</span><span class="sxs-lookup"><span data-stu-id="e2184-123">Delete</span></span>|<span data-ttu-id="e2184-124">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="e2184-124">Uninstall</span></span>|<span data-ttu-id="e2184-125">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="e2184-125">BizTalkHostInstance</span></span>|  
|<span data-ttu-id="e2184-126">Deshacer el proceso de importación</span><span class="sxs-lookup"><span data-stu-id="e2184-126">Import rollback</span></span>|<span data-ttu-id="e2184-127">DELETE</span><span class="sxs-lookup"><span data-stu-id="e2184-127">Delete</span></span>|<span data-ttu-id="e2184-128">Importar</span><span class="sxs-lookup"><span data-stu-id="e2184-128">Import</span></span>|<span data-ttu-id="e2184-129">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="e2184-129">ConfigurationDb</span></span>|  
|<span data-ttu-id="e2184-130">Deshacer el proceso de instalación</span><span class="sxs-lookup"><span data-stu-id="e2184-130">Install rollback</span></span>|<span data-ttu-id="e2184-131">DELETE</span><span class="sxs-lookup"><span data-stu-id="e2184-131">Delete</span></span>|<span data-ttu-id="e2184-132">Install</span><span class="sxs-lookup"><span data-stu-id="e2184-132">Install</span></span>|<span data-ttu-id="e2184-133">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="e2184-133">BizTalkHostInstance</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2184-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2184-134">See Also</span></span>  
 <span data-ttu-id="e2184-135">[Uso de secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicación](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="e2184-135">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 <span data-ttu-id="e2184-136">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span><span class="sxs-lookup"><span data-stu-id="e2184-136">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span></span>  
 <span data-ttu-id="e2184-137">[BTAD_InstallMode](../core/btad-installmode.md) </span><span class="sxs-lookup"><span data-stu-id="e2184-137">[BTAD_InstallMode](../core/btad-installmode.md) </span></span>  
 [<span data-ttu-id="e2184-138">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="e2184-138">BTAD_HostClass</span></span>](../core/btad-hostclass.md)