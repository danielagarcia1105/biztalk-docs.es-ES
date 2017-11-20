---
title: "Cómo obtener la duración en una ventana ATR | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- aggregations [BAM], time intervals
- managing [BAM], time intervals
- Get-RTAWindow command [BAM]
ms.assetid: 4e7ad0fd-e7ed-47f7-9435-ef01bbe17afa
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb930c3e9d252a23653f0464e1adaa1e18b4f45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-get-the-duration-on-an-rta-window"></a><span data-ttu-id="d50de-102">Cómo obtener la duración en una ventana ATR</span><span class="sxs-lookup"><span data-stu-id="d50de-102">How to Get the Duration on an RTA Window</span></span>
<span data-ttu-id="d50de-103">Los administradores utilizan el **get-rtawindow** comando para obtener la duración de la agregación en tiempo real especificada (ATR).</span><span class="sxs-lookup"><span data-stu-id="d50de-103">Administrators use the **get-rtawindow** command to get the duration for the specified real-time aggregation (RTA).</span></span> <span data-ttu-id="d50de-104">El comando recupera la longitud de la duración y las unidades con las que se mide la duración.</span><span class="sxs-lookup"><span data-stu-id="d50de-104">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
### <a name="to-get-the-duration-on-an-aggregation"></a><span data-ttu-id="d50de-105">Para obtener la duración en una agregación</span><span class="sxs-lookup"><span data-stu-id="d50de-105">To get the duration on an aggregation</span></span>  
  
1.  <span data-ttu-id="d50de-106">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d50de-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="d50de-107">Desplácese a la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="d50de-107">Navigate to the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="d50de-108">Tipo **bm get-rtawindow-View:\<nombre de vista >-actividad:\<nombre de actividad > -ATR:\<nombre de ATR >**.</span><span class="sxs-lookup"><span data-stu-id="d50de-108">Type **bm get-rtawindow -View:\<view name> -Activity:\<activity name> -Rta:\<RTA name>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d50de-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d50de-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="d50de-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d50de-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d50de-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d50de-111">See Also</span></span>  
 <span data-ttu-id="d50de-112">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="d50de-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="d50de-113">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="d50de-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="d50de-114">Cómo establecer la duración de una ventana ATR</span><span class="sxs-lookup"><span data-stu-id="d50de-114">How to Set the Duration on an RTA Window</span></span>](../core/how-to-set-the-duration-on-an-rta-window.md)