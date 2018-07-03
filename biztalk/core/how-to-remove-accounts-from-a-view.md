---
title: Cómo quitar las cuentas de una vista | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- managing [BAM], deleting accounts from views
- Remove-Account command [BAM]
ms.assetid: b74a64a0-ddb3-45d2-add7-6261c31be0f0
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 243c7ee549aea06acb199f718c6eef55e578f91f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995397"
---
# <a name="how-to-remove-accounts-from-a-view"></a><span data-ttu-id="e42ee-102">Cómo quitar cuentas de una vista</span><span class="sxs-lookup"><span data-stu-id="e42ee-102">How to Remove Accounts from a View</span></span>
<span data-ttu-id="e42ee-103">Los administradores utilizan el **remove-account** comando para quitar usuarios de las vistas de BAM y proteger las vistas de hojas de cálculo de Excel de BAM de accesos no autorizados.</span><span class="sxs-lookup"><span data-stu-id="e42ee-103">Administrators use the **remove-account** command to remove users from BAM views and protect BAM Excel Spreadsheet views from unauthorized access.</span></span>  
  
 <span data-ttu-id="e42ee-104">Para obtener información acerca de cómo ver las vistas de BAM, consulte [cómo enumerar vistas de BAM](../core/how-to-list-bam-views.md).</span><span class="sxs-lookup"><span data-stu-id="e42ee-104">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-remove-an-account-from-a-view"></a><span data-ttu-id="e42ee-105">Para quitar una cuenta de una vista</span><span class="sxs-lookup"><span data-stu-id="e42ee-105">To remove an account from a view</span></span>  
  
1. <span data-ttu-id="e42ee-106">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e42ee-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="e42ee-107">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span><span class="sxs-lookup"><span data-stu-id="e42ee-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span></span>  
  
3. <span data-ttu-id="e42ee-108">Tipo **bm remove-account - AccountName:\<nombreCuenta\> -View:\<nombre de la vista\>**.</span><span class="sxs-lookup"><span data-stu-id="e42ee-108">Type **bm remove-account -AccountName:\<account name\> -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e42ee-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e42ee-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="e42ee-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="e42ee-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e42ee-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e42ee-111">See Also</span></span>  
 <span data-ttu-id="e42ee-112">[Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="e42ee-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="e42ee-113">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="e42ee-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)