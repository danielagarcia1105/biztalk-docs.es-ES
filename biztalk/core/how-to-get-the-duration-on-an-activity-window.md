---
title: "Cómo obtener la duración en una ventana actividad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], time intervals
- managing [BAM], time intervals
- Get-ActivityWindow command [BAM]
ms.assetid: d70f6767-f6f7-4ecf-ad9d-4a9d8c76edea
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dbef138603421a46edd4b2d17a5123116cece6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-get-the-duration-on-an-activity-window"></a><span data-ttu-id="db7f0-102">Cómo obtener la duración en una ventana Actividad</span><span class="sxs-lookup"><span data-stu-id="db7f0-102">How to Get the Duration on an Activity Window</span></span>
<span data-ttu-id="db7f0-103">Los administradores utilizan el **get-activitywindow** comando para obtener la duración de la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="db7f0-103">Administrators use the **get-activitywindow** command to get the duration for the specified activity.</span></span> <span data-ttu-id="db7f0-104">El comando recupera la longitud de la duración y las unidades con las que se mide la duración.</span><span class="sxs-lookup"><span data-stu-id="db7f0-104">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
### <a name="to-get-the-duration-on-an-activity"></a><span data-ttu-id="db7f0-105">Para obtener la duración de una actividad</span><span class="sxs-lookup"><span data-stu-id="db7f0-105">To get the duration on an activity</span></span>  
  
1.  <span data-ttu-id="db7f0-106">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db7f0-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="db7f0-107">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="db7f0-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="db7f0-108">Escriba bm get-activitywindow-actividad:\<nombre de actividad >.</span><span class="sxs-lookup"><span data-stu-id="db7f0-108">Type  bm get-activitywindow -Activity:\<activity name>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="db7f0-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="db7f0-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="db7f0-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="db7f0-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db7f0-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="db7f0-111">See Also</span></span>  
 <span data-ttu-id="db7f0-112">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="db7f0-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="db7f0-113">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="db7f0-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="db7f0-114">Cómo establecer la duración de una ventana actividad</span><span class="sxs-lookup"><span data-stu-id="db7f0-114">How to Set the Duration on an Activity Window</span></span>](../core/how-to-set-the-duration-on-an-activity-window.md)