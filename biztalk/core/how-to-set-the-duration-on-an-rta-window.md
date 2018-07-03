---
title: Cómo establecer la duración en una ventana ATR | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- aggregations [BAM], time intervals
- Set-RTAWindow command [BAM]
- managing [BAM], time intervals
ms.assetid: 3042c3f5-be0f-48fb-9831-daa4868b90fe
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 067e70ec9bff40e0b7dcee6152791f194a104218
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992277"
---
# <a name="how-to-set-the-duration-on-an-rta-window"></a><span data-ttu-id="4eb56-102">Cómo establecer la duración en una ventana ATR</span><span class="sxs-lookup"><span data-stu-id="4eb56-102">How to Set the Duration on an RTA Window</span></span>
<span data-ttu-id="4eb56-103">Los administradores utilizan el **set-rtawindow** comando para establecer la duración de la agregación en tiempo real especificada (ATR).</span><span class="sxs-lookup"><span data-stu-id="4eb56-103">Administrators use the **set-rtawindow** command to set the duration for the specified real-time aggregation (RTA).</span></span>  
  
### <a name="to-set-the-duration-on-an-aggregation"></a><span data-ttu-id="4eb56-104">Para establecer la duración en una agregación</span><span class="sxs-lookup"><span data-stu-id="4eb56-104">To set the duration on an aggregation</span></span>  
  
1. <span data-ttu-id="4eb56-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4eb56-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="4eb56-106">Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4eb56-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="4eb56-107">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4eb56-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="4eb56-108">Tipo **bm set-rtawindow-View:\<nombre de la vista\> -actividad:\<nombre de la actividad\> -nombre:\<nombre de ATR\> - TimeLength:\<número entero\>- TimeUnit: día&#124;hora&#124;minuto**.</span><span class="sxs-lookup"><span data-stu-id="4eb56-108">Type **bm set-rtawindow -View:\<view name\> -Activity:\<activity name\> -Name:\<RTA name\> -TimeLength:\<integer number\> -TimeUnit:Day&#124;Hour&#124;Minute**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4eb56-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="4eb56-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="4eb56-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4eb56-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eb56-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4eb56-111">See Also</span></span>  
 <span data-ttu-id="4eb56-112">[Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="4eb56-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="4eb56-113">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4eb56-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="4eb56-114">Cómo obtener la duración en una ventana ATR</span><span class="sxs-lookup"><span data-stu-id="4eb56-114">How to Get the Duration on an RTA Window</span></span>](../core/how-to-get-the-duration-on-an-rta-window.md)