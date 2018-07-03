---
title: Cómo enumerar los usuarios de cuentas con acceso a una vista | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, BAM
- managing [BAM], user accounts
- Get-Accounts utility [BAM]
ms.assetid: 690fb45a-6de0-489e-9ddd-e88e29413c16
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8e27f1f48846c1eb134c2ee71bf9c00c72d4a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981709"
---
# <a name="how-to-list-user-accounts-with-access-to-a-view"></a><span data-ttu-id="2a1ff-102">Cómo enumerar cuentas de usuario con acceso a una vista</span><span class="sxs-lookup"><span data-stu-id="2a1ff-102">How to List User Accounts With Access to a View</span></span>
<span data-ttu-id="2a1ff-103">Los administradores utilizan el **get-accounts** comando de la utilidad de administración de BAM para obtener una lista de todas las cuentas de usuario para un rol de vista, lo que significa que todas las cuentas de usuario con acceso a la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="2a1ff-103">Administrators use the **get-accounts** BAM Management utility command to get a list all user accounts for a view role, meaning all user accounts with access to the specified view.</span></span>  
  
 <span data-ttu-id="2a1ff-104">Para obtener información acerca de cómo ver las vistas de BAM, consulte [cómo enumerar vistas de BAM](../core/how-to-list-bam-views.md).</span><span class="sxs-lookup"><span data-stu-id="2a1ff-104">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-list-user-accounts-with-access-to-a-view"></a><span data-ttu-id="2a1ff-105">Para enumerar cuentas de usuario con acceso a una vista</span><span class="sxs-lookup"><span data-stu-id="2a1ff-105">To list user accounts with access to a view</span></span>  
  
1. <span data-ttu-id="2a1ff-106">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2a1ff-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="2a1ff-107">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span><span class="sxs-lookup"><span data-stu-id="2a1ff-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span></span>  
  
3. <span data-ttu-id="2a1ff-108">Tipo **bm get-accounts-View:\<nombre de la vista\>**.</span><span class="sxs-lookup"><span data-stu-id="2a1ff-108">Type **bm get-accounts -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2a1ff-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2a1ff-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="2a1ff-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="2a1ff-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a1ff-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a1ff-111">See Also</span></span>  
 <span data-ttu-id="2a1ff-112">[Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="2a1ff-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="2a1ff-113">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="2a1ff-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)