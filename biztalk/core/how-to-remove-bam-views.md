---
title: Cómo quitar vistas de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, views
- managing [BAM definitions], deleting views
- Remove-View command [BAM]
ms.assetid: 1a43ec81-20b1-41f7-941f-753132ac9ed2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc49038c30cc6016c79f8e0d309f93217994327f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972186"
---
# <a name="how-to-remove-bam-views"></a><span data-ttu-id="fb69e-102">Cómo quitar vistas de BAM</span><span class="sxs-lookup"><span data-stu-id="fb69e-102">How to Remove BAM Views</span></span>
<span data-ttu-id="fb69e-103">Los administradores utilizan el **remove-view** comando para quitar una vista de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="fb69e-103">Administrators use the **remove-view** command to remove a view from the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb69e-104">Cuando quita una vista, también quita automáticamente cualquier alerta que esté definida para esa vista.</span><span class="sxs-lookup"><span data-stu-id="fb69e-104">When you remove a view, you also automatically remove any alerts defined for that view.</span></span>  
  
### <a name="to-remove-bam-views"></a><span data-ttu-id="fb69e-105">Para quitar vistas de BAM</span><span class="sxs-lookup"><span data-stu-id="fb69e-105">To remove BAM views</span></span>  
  
1.  <span data-ttu-id="fb69e-106">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb69e-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="fb69e-107">Navegue hasta la carpeta de seguimiento escribiendo **C:\Program Files\Microsoft BizTalk Server 2009\Tracking** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="fb69e-107">Navigate to the tracking folder by typing **C:\Program Files\Microsoft BizTalk Server 2009\Tracking** at the command prompt.</span></span> <span data-ttu-id="fb69e-108">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="fb69e-108">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="fb69e-109">Tipo de **bm remove-view-Name:\<nombre de la vista\>**.</span><span class="sxs-lookup"><span data-stu-id="fb69e-109">Type **bm remove-view -Name:\<view name\>**.</span></span>  
  
4.  <span data-ttu-id="fb69e-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="fb69e-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb69e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb69e-111">See Also</span></span>  
 <span data-ttu-id="fb69e-112">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="fb69e-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="fb69e-113">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="fb69e-113">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 <span data-ttu-id="fb69e-114">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="fb69e-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="fb69e-115">Cómo quitar alertas BAM</span><span class="sxs-lookup"><span data-stu-id="fb69e-115">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)