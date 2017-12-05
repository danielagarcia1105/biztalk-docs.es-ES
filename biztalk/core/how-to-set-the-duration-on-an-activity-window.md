---
title: "Cómo establecer la duración de una ventana actividad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Set-ActivityWindow command [BAM]
- activities [BAM], time intervals
- managing [BAM], time intervals
ms.assetid: e39c315e-f215-4f81-9774-cf7aedf6ba33
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66ef0c7200c69cd69a72a5743ca8f14a8950b17d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-the-duration-on-an-activity-window"></a><span data-ttu-id="4f949-102">Cómo definir la duración en una ventana Actividad</span><span class="sxs-lookup"><span data-stu-id="4f949-102">How to Set the Duration on an Activity Window</span></span>
<span data-ttu-id="4f949-103">Los administradores utilizan el **set-activitywindow** comando para establecer la duración de la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="4f949-103">Administrators use the **set-activitywindow** command to set the duration for the specified activity.</span></span>  
  
### <a name="to-set-the-duration-on-an-activity"></a><span data-ttu-id="4f949-104">Para definir la duración en una actividad</span><span class="sxs-lookup"><span data-stu-id="4f949-104">To set the duration on an activity</span></span>  
  
1.  <span data-ttu-id="4f949-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f949-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4f949-106">Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4f949-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="4f949-107">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4f949-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="4f949-108">Tipo de **bm set-activitywindow-actividad:\<nombre de la actividad\> - TimeLength:\<número entero\> - TimeUnit: mes &#124; día &#124; Hora &#124; Minuto**.</span><span class="sxs-lookup"><span data-stu-id="4f949-108">Type **bm set-activitywindow -Activity:\<activity name\> -TimeLength:\<integer number\> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f949-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="4f949-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="4f949-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4f949-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f949-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f949-111">See Also</span></span>  
 <span data-ttu-id="4f949-112">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="4f949-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="4f949-113">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4f949-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="4f949-114">Cómo obtener la duración en una ventana actividad</span><span class="sxs-lookup"><span data-stu-id="4f949-114">How to Get the Duration on an Activity Window</span></span>](../core/how-to-get-the-duration-on-an-activity-window.md)