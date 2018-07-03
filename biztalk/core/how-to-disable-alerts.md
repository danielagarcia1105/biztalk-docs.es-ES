---
title: Cómo deshabilitar las alertas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- alerts, disabling
- managing [BAM definitions], disabling alerts
- Disable-Alerts command [BAM]
ms.assetid: c5938bc2-1043-4633-8cad-02caf442f2e8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac107300ff14f024da02d6959f695790fe7ff80
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002797"
---
# <a name="how-to-disable-alerts"></a><span data-ttu-id="60253-102">Cómo deshabilitar alertas</span><span class="sxs-lookup"><span data-stu-id="60253-102">How to Disable Alerts</span></span>
<span data-ttu-id="60253-103">Los administradores utilizan el **disable-alerts** comando para deshabilitar todas las alertas en la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="60253-103">Administrators use the **disable-alerts** command to disable all of the alerts on the specified view.</span></span>  
  
### <a name="to-disable-an-alert"></a><span data-ttu-id="60253-104">Para deshabilitar una alerta</span><span class="sxs-lookup"><span data-stu-id="60253-104">To disable an alert</span></span>  
  
1. <span data-ttu-id="60253-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="60253-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="60253-106">Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="60253-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="60253-107">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="60253-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="60253-108">Tipo **bm disable-alerts-View:\<nombre de la vista\>**.</span><span class="sxs-lookup"><span data-stu-id="60253-108">Type **bm disable-alerts -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="60253-109">Si ha exportado configuraciones de BAM como archivos XML, no modifique el código XML relativo a las alertas.</span><span class="sxs-lookup"><span data-stu-id="60253-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="60253-110">Si modifica el código XML relativo a las alertas e implementa los cambios, bm.exe detectará el cambio y habilitará las alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="60253-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4. <span data-ttu-id="60253-111">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="60253-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60253-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="60253-112">See Also</span></span>  
 <span data-ttu-id="60253-113">[Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="60253-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="60253-114">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="60253-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="60253-115">Cómo habilitar las alertas</span><span class="sxs-lookup"><span data-stu-id="60253-115">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md)