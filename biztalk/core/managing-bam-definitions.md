---
title: Administrar definiciones de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions]
- definitions [BAM], managing
- definition files [BAM], managing
- managing [BAM], definitions
- managing [BAM definitions], about managing BAM definitions
ms.assetid: 7aba0e40-b8d3-4afc-9e4c-92392f1f6269
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93cf3d280d0e615442a4141b7fa41f6ee3566490
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-bam-definitions"></a><span data-ttu-id="0bec6-102">Administrar definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-102">Managing BAM Definitions</span></span>
<span data-ttu-id="0bec6-103">Una definición de BAM es una parte de la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="0bec6-103">A BAM definition is part of the BAM infrastructure.</span></span> <span data-ttu-id="0bec6-104">Establece los datos que se van a agregar y de los que se va a realizar el seguimiento, así como la vista del usuario empresarial final en los datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0bec6-104">It defines the data to track and aggregate, as well as the business end user's view on the tracking data.</span></span> <span data-ttu-id="0bec6-105">Los temas de esta sección explican los procedimientos para administrar los elementos de las definiciones de BAM, que incluyen actividades, vistas, artefactos y alertas.</span><span class="sxs-lookup"><span data-stu-id="0bec6-105">The topics in this section give procedures for managing the elements of BAM definitions, which include activities, views, artifacts, and alerts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bec6-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0bec6-106">In This Section</span></span>  
  
-   [<span data-ttu-id="0bec6-107">Derechos de usuario necesarios para administrar archivos de definición de BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-107">Required User Rights for Managing BAM Definition Files</span></span>](../core/required-user-rights-for-managing-bam-definition-files.md)  
  
-   [<span data-ttu-id="0bec6-108">Cómo implementar definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-108">How to Deploy BAM Definitions</span></span>](../core/how-to-deploy-bam-definitions.md)  
  
-   [<span data-ttu-id="0bec6-109">Cómo quitar definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-109">How to Remove BAM Definitions</span></span>](../core/how-to-remove-bam-activities.md)  
  
-   [<span data-ttu-id="0bec6-110">Cómo enumerar los cambios en la infraestructura de BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-110">How to List Changes to the BAM Infrastructure</span></span>](../core/how-to-list-changes-to-the-bam-infrastructure.md)  
  
-   [<span data-ttu-id="0bec6-111">Cómo enumerar actividades de BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-111">How to List BAM Activities</span></span>](../core/how-to-list-bam-activities.md)  
  
-   [<span data-ttu-id="0bec6-112">Cómo quitar actividades BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-112">How to Remove BAM Activities</span></span>](../core/how-to-remove-bam-activities.md)  
  
-   [<span data-ttu-id="0bec6-113">Cómo enumerar vistas de BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-113">How to List BAM Views</span></span>](../core/how-to-list-bam-views.md)  
  
-   [<span data-ttu-id="0bec6-114">Cómo quitar vistas de BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-114">How to Remove BAM Views</span></span>](../core/how-to-remove-bam-views.md)  
  
-   [<span data-ttu-id="0bec6-115">Cómo habilitar las alertas</span><span class="sxs-lookup"><span data-stu-id="0bec6-115">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md)  
  
-   [<span data-ttu-id="0bec6-116">Cómo deshabilitar las alertas</span><span class="sxs-lookup"><span data-stu-id="0bec6-116">How to Disable Alerts</span></span>](../core/how-to-disable-alerts.md)  
  
-   [<span data-ttu-id="0bec6-117">Cómo quitar alertas BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-117">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)  
  
-   [<span data-ttu-id="0bec6-118">Cómo actualizar artefactos de BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-118">How to Update BAM Artifacts</span></span>](../core/how-to-update-bam-artifacts.md)  
  
-   [<span data-ttu-id="0bec6-119">Cómo quitar artefactos implementados</span><span class="sxs-lookup"><span data-stu-id="0bec6-119">How to Remove Deployed Artifacts</span></span>](../core/how-to-remove-deployed-artifacts.md)  
  
-   [<span data-ttu-id="0bec6-120">La configuración de alertas BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-120">Configuring BAM Alerts</span></span>](../core/configuring-bam-alerts.md)  
  
-   [<span data-ttu-id="0bec6-121">Administrar la ejecución de alertas de BAM</span><span class="sxs-lookup"><span data-stu-id="0bec6-121">Managing BAM Alert Execution</span></span>](../core/managing-bam-alert-execution.md)  
  
-   [<span data-ttu-id="0bec6-122">Cómo cambiar la frecuencia con las alertas que se evalúan</span><span class="sxs-lookup"><span data-stu-id="0bec6-122">How to Change the Frequency With Which Alerts Are Evaluated</span></span>](../core/how-to-change-the-frequency-with-which-alerts-are-evaluated.md)