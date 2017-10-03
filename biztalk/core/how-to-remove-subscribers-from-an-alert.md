---
title: "Cómo quitar suscriptores de una alerta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- managing [BAM], deleting alert subscibers
- alerts, subscribers
ms.assetid: d5571863-26e3-4c1b-991f-538cd1fef347
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92855ecc4e4e5ad2f7932327de7da8e19a80d490
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-subscribers-from-an-alert"></a><span data-ttu-id="b85fc-102">Cómo quitar suscriptores de una alerta</span><span class="sxs-lookup"><span data-stu-id="b85fc-102">How to Remove Subscribers from an Alert</span></span>
<span data-ttu-id="b85fc-103">Los administradores utilizan el **remove-subscription** comando para quitar el usuario especificado como un suscriptor de una alerta.</span><span class="sxs-lookup"><span data-stu-id="b85fc-103">Administrators use the **remove-subscription** command to remove the specified user as a subscriber from an alert.</span></span>  
  
### <a name="to-remove-subscribers-from-an-alert"></a><span data-ttu-id="b85fc-104">Para quitar suscriptores de una alerta</span><span class="sxs-lookup"><span data-stu-id="b85fc-104">To remove subscribers from an alert</span></span>  
  
1.  <span data-ttu-id="b85fc-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b85fc-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="b85fc-106">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="b85fc-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="b85fc-107">Tipo de **bm remove-subscription-View:\<nombre de vista >-alerta:\<nombre de la alerta > - AccountName:\<nombre de cuenta >**.</span><span class="sxs-lookup"><span data-stu-id="b85fc-107">Type **bm remove-subscription -View:\<view name> -Alert:\<alert name> -AccountName:\<account name>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b85fc-108">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="b85fc-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="b85fc-109">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="b85fc-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85fc-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b85fc-110">See Also</span></span>  
 <span data-ttu-id="b85fc-111">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="b85fc-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="b85fc-112">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b85fc-112">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="b85fc-113">Cómo agregar suscriptores a una alerta</span><span class="sxs-lookup"><span data-stu-id="b85fc-113">How to Add Subscribers to an Alert</span></span>](../core/how-to-add-subscribers-to-an-alert.md)