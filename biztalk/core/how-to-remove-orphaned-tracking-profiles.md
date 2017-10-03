---
title: "Cómo quitar perfiles de seguimiento huérfanos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, orphans
- tracking profiles, activities
- tracking profiles, deleting
- activities, tracking profiles
ms.assetid: e8923dab-5d02-41a3-840b-104b20624e6c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33ddea8751a017db21306c06cdcca5929de641ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-orphaned-tracking-profiles"></a><span data-ttu-id="00ce1-102">Cómo quitar perfiles de seguimiento huérfanos</span><span class="sxs-lookup"><span data-stu-id="00ce1-102">How to Remove Orphaned Tracking Profiles</span></span>
<span data-ttu-id="00ce1-103">Los perfiles de seguimiento están asociados a una actividad.</span><span class="sxs-lookup"><span data-stu-id="00ce1-103">Tracking profiles are associated with an activity.</span></span> <span data-ttu-id="00ce1-104">Cuando una actividad no está implementada, los perfiles de seguimiento pueden quedarse “huérfanos”, lo que significa que dejan de estar asociados a una actividad.</span><span class="sxs-lookup"><span data-stu-id="00ce1-104">If an activity is undeployed, the associated tracking profiles can become orphaned, which means they are no longer associated with an activity.</span></span> <span data-ttu-id="00ce1-105">Puede utilizar el procedimiento siguiente para quitar el perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="00ce1-105">You can use the following procedure to remove the tracking profile.</span></span>  
  
### <a name="to-remove-an-orphaned-tracking-profile"></a><span data-ttu-id="00ce1-106">Para quitar un perfil de seguimiento huérfano</span><span class="sxs-lookup"><span data-stu-id="00ce1-106">To remove an orphaned tracking profile</span></span>  
  
1.  <span data-ttu-id="00ce1-107">Vuelva a implementar la definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="00ce1-107">Redeploy the BAM definition.</span></span> <span data-ttu-id="00ce1-108">Para obtener información acerca de cómo implementar definiciones de BAM, consulte [cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="00ce1-108">For information about deploying BAM definitions, see [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
2.  <span data-ttu-id="00ce1-109">Utilice el Editor de perfiles de seguimiento (TPE) para quitar el perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="00ce1-109">Use the Tracking Profile Editor (TPE) to remove the tracking profile.</span></span> <span data-ttu-id="00ce1-110">Para obtener información acerca de cómo quitar perfiles de seguimiento, vea [cómo aplicar y quitar un perfil de seguimiento](../core/how-to-apply-and-remove-a-tracking-profile.md).</span><span class="sxs-lookup"><span data-stu-id="00ce1-110">For information about removing tracking profiles, see [How to Apply and Remove a Tracking Profile](../core/how-to-apply-and-remove-a-tracking-profile.md).</span></span>  
  
3.  <span data-ttu-id="00ce1-111">Anule la implementación de la definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="00ce1-111">Undeploy the BAM definition.</span></span> <span data-ttu-id="00ce1-112">Para obtener información acerca de cómo quitar definiciones de BAM, consulte [cómo quitar definiciones de BAM](../core/how-to-remove-bam-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="00ce1-112">For information about removing BAM definitions, see [How to Remove BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ce1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="00ce1-113">See Also</span></span>  
 <span data-ttu-id="00ce1-114">[Editor de perfiles de seguimiento](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="00ce1-114">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="00ce1-115">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="00ce1-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)