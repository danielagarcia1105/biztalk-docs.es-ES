---
title: "Cómo enumerar suscriptores de una alerta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- alerts, listing subscribers
- managing [BAM], listing alert subscribers
- subscriptions, listing subscribers
ms.assetid: 760cc88f-896d-43a3-a4af-b2a836190276
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 909854abd251d94fa71ce963c3714f6d664153c1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-list-subscribers-to-an-alert"></a><span data-ttu-id="4d927-102">Cómo enumerar suscriptores de una alerta</span><span class="sxs-lookup"><span data-stu-id="4d927-102">How to List Subscribers to an Alert</span></span>
<span data-ttu-id="4d927-103">Los administradores utilizan el **get-subscriptions** comando para enumerar todos los suscriptores a una alerta específica.</span><span class="sxs-lookup"><span data-stu-id="4d927-103">Administrators use the **get-subscriptions** command to list all of the subscribers to a specified alert.</span></span>  
  
### <a name="to-list-subscribers-to-an-alert"></a><span data-ttu-id="4d927-104">Para enumerar suscriptores de una alerta</span><span class="sxs-lookup"><span data-stu-id="4d927-104">To list subscribers to an alert</span></span>  
  
1.  <span data-ttu-id="4d927-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4d927-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4d927-106">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="4d927-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="4d927-107">Tipo de **bm get-subscriptions-View:\<nombre de la vista\> -alerta:\<nombre de la alerta\>**.</span><span class="sxs-lookup"><span data-stu-id="4d927-107">Type **bm get-subscriptions -View:\<view name\> -Alert:\<alert name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d927-108">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="4d927-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="4d927-109">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4d927-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d927-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d927-110">See Also</span></span>  
 <span data-ttu-id="4d927-111">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="4d927-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="4d927-112">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="4d927-112">BAM Management Utility</span></span>](../core/bam-management-utility.md)