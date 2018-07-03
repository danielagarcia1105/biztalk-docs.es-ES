---
title: Cómo las Variables de entorno indican el estado de implementación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, variables
ms.assetid: 022b782b-008d-41a7-9880-d1c4e5e4015e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d21baa6ef6e6d82fc179497b4993cf3af6fb1a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983989"
---
# <a name="how-environment-variables-indicate-deployment-state"></a><span data-ttu-id="8a9dd-102">Cómo las variables de entorno indican el estado de la implementación</span><span class="sxs-lookup"><span data-stu-id="8a9dd-102">How Environment Variables Indicate Deployment State</span></span>
<span data-ttu-id="8a9dd-103">Una vez invocada, una secuencia de comandos previa o posterior al procesamiento puede determinar el estado de implementación (instalar, importar, eliminar, desinstalar, deshacer importación o deshacer instalación) que se está ejecutando mediante la comprobación de las variables de entorno BTAD_ChangeRequestAction, BTAD_InstallMode y BTAD_HostClass.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-103">Once invoked, a pre- or post-processing script can determine in which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode and BTAD_HostClass.</span></span>  

 <span data-ttu-id="8a9dd-104">En la tabla siguiente se describen las combinaciones de las tres variables que indican los distintos estados de la implementación.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-104">The following table describes the combinations of the three variables that indicate the different deployment states.</span></span>  


|       <span data-ttu-id="8a9dd-105">Estado de implementación</span><span class="sxs-lookup"><span data-stu-id="8a9dd-105">Deployment State</span></span>        |     <span data-ttu-id="8a9dd-106">Valores esperados</span><span class="sxs-lookup"><span data-stu-id="8a9dd-106">Expected Values</span></span>      |
|-------------------------------|--------------------------|
|                               | <span data-ttu-id="8a9dd-107">BTAD_ChangeRequestAction</span><span class="sxs-lookup"><span data-stu-id="8a9dd-107">BTAD_ChangeRequestAction</span></span> |
| <span data-ttu-id="8a9dd-108">Importar sin marca de sobrescritura</span><span class="sxs-lookup"><span data-stu-id="8a9dd-108">Import without overwrite flag</span></span> |          <span data-ttu-id="8a9dd-109">Crear</span><span class="sxs-lookup"><span data-stu-id="8a9dd-109">Create</span></span>          |
|  <span data-ttu-id="8a9dd-110">Importar con marca de sobrescritura</span><span class="sxs-lookup"><span data-stu-id="8a9dd-110">Import with overwrite flag</span></span>   |          <span data-ttu-id="8a9dd-111">Update</span><span class="sxs-lookup"><span data-stu-id="8a9dd-111">Update</span></span>          |
|            <span data-ttu-id="8a9dd-112">Install</span><span class="sxs-lookup"><span data-stu-id="8a9dd-112">Install</span></span>            |          <span data-ttu-id="8a9dd-113">Update</span><span class="sxs-lookup"><span data-stu-id="8a9dd-113">Update</span></span>          |
|           <span data-ttu-id="8a9dd-114">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="8a9dd-114">Uninstall</span></span>           |          <span data-ttu-id="8a9dd-115">DELETE</span><span class="sxs-lookup"><span data-stu-id="8a9dd-115">Delete</span></span>          |
|        <span data-ttu-id="8a9dd-116">Deshacer el proceso de importación</span><span class="sxs-lookup"><span data-stu-id="8a9dd-116">Import rollback</span></span>        |          <span data-ttu-id="8a9dd-117">DELETE</span><span class="sxs-lookup"><span data-stu-id="8a9dd-117">Delete</span></span>          |
|       <span data-ttu-id="8a9dd-118">Deshacer el proceso de instalación</span><span class="sxs-lookup"><span data-stu-id="8a9dd-118">Install rollback</span></span>        |          <span data-ttu-id="8a9dd-119">DELETE</span><span class="sxs-lookup"><span data-stu-id="8a9dd-119">Delete</span></span>          |

## <a name="see-also"></a><span data-ttu-id="8a9dd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a9dd-120">See Also</span></span>  
 <span data-ttu-id="8a9dd-121">[Uso de secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="8a9dd-121">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 <span data-ttu-id="8a9dd-122">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span><span class="sxs-lookup"><span data-stu-id="8a9dd-122">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span></span>  
 <span data-ttu-id="8a9dd-123">[BTAD_InstallMode](../core/btad-installmode.md) </span><span class="sxs-lookup"><span data-stu-id="8a9dd-123">[BTAD_InstallMode](../core/btad-installmode.md) </span></span>  
 [<span data-ttu-id="8a9dd-124">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="8a9dd-124">BTAD_HostClass</span></span>](../core/btad-hostclass.md)