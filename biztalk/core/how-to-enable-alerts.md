---
title: "Cómo habilitar alertas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Enable-Alerts command [BAM]
- managing [BAM definitions], enabling alerts
- alerts, enabling
ms.assetid: 18f494b7-54fb-4aaf-89d1-7e3fe91f35c6
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9986bea177471a236cab888f20d915292d540e5b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-alerts"></a><span data-ttu-id="181d3-102">Cómo habilitar alertas</span><span class="sxs-lookup"><span data-stu-id="181d3-102">How to Enable Alerts</span></span>
<span data-ttu-id="181d3-103">Los administradores utilizan el **enable-alerts** comando para habilitar todas las alertas de la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="181d3-103">Administrators use the **enable-alerts** command to enable all of the alerts on the specified view.</span></span>  
  
### <a name="to-enable-an-alert"></a><span data-ttu-id="181d3-104">Para habilitar una alerta</span><span class="sxs-lookup"><span data-stu-id="181d3-104">To enable an alert</span></span>  
  
1.  <span data-ttu-id="181d3-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="181d3-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="181d3-106">Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="181d3-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="181d3-107">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="181d3-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="181d3-108">Tipo de **bm enable-alerts-View:\<nombre de la vista\>**.</span><span class="sxs-lookup"><span data-stu-id="181d3-108">Type **bm enable-alerts -View:\<view name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="181d3-109">Si ha exportado configuraciones de BAM como archivos XML, no modifique el código XML relativo a las alertas.</span><span class="sxs-lookup"><span data-stu-id="181d3-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="181d3-110">Si modifica el código XML relativo a las alertas e implementa los cambios, bm.exe detectará el cambio y habilitará las alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="181d3-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4.  <span data-ttu-id="181d3-111">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="181d3-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="181d3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="181d3-112">See Also</span></span>  
 <span data-ttu-id="181d3-113">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="181d3-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="181d3-114">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="181d3-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="181d3-115">Escriba aquí la descripción del vínculo</span><span class="sxs-lookup"><span data-stu-id="181d3-115">enter link description here</span></span>](../core/how-to-disable-alerts.md)