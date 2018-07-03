---
title: Cómo habilitar alertas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enable-Alerts command [BAM]
- managing [BAM definitions], enabling alerts
- alerts, enabling
ms.assetid: 18f494b7-54fb-4aaf-89d1-7e3fe91f35c6
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9fee863613feea040e05856d8246f94b4a3f835
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969157"
---
# <a name="how-to-enable-alerts"></a><span data-ttu-id="08d84-102">Cómo habilitar alertas</span><span class="sxs-lookup"><span data-stu-id="08d84-102">How to Enable Alerts</span></span>
<span data-ttu-id="08d84-103">Los administradores utilizan el **enable-alerts** comando para habilitar todas las alertas en la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="08d84-103">Administrators use the **enable-alerts** command to enable all of the alerts on the specified view.</span></span>  
  
### <a name="to-enable-an-alert"></a><span data-ttu-id="08d84-104">Para habilitar una alerta</span><span class="sxs-lookup"><span data-stu-id="08d84-104">To enable an alert</span></span>  
  
1. <span data-ttu-id="08d84-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="08d84-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="08d84-106">Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="08d84-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="08d84-107">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="08d84-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="08d84-108">Tipo **bm enable-alerts-View:\<nombre de la vista\>**.</span><span class="sxs-lookup"><span data-stu-id="08d84-108">Type **bm enable-alerts -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="08d84-109">Si ha exportado configuraciones de BAM como archivos XML, no modifique el código XML relativo a las alertas.</span><span class="sxs-lookup"><span data-stu-id="08d84-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="08d84-110">Si modifica el código XML relativo a las alertas e implementa los cambios, bm.exe detectará el cambio y habilitará las alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="08d84-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4. <span data-ttu-id="08d84-111">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="08d84-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d84-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="08d84-112">See Also</span></span>  
 <span data-ttu-id="08d84-113">[Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="08d84-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="08d84-114">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="08d84-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="08d84-115">Escriba aquí la descripción del vínculo</span><span class="sxs-lookup"><span data-stu-id="08d84-115">enter link description here</span></span>](../core/how-to-disable-alerts.md)