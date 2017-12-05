---
title: "Cómo deshabilitar las alertas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- alerts, disabling
- managing [BAM definitions], disabling alerts
- Disable-Alerts command [BAM]
ms.assetid: c5938bc2-1043-4633-8cad-02caf442f2e8
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4279030b9c3bcc7913bf64cc870b0d82d618dff8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-disable-alerts"></a><span data-ttu-id="02270-102">Cómo deshabilitar alertas</span><span class="sxs-lookup"><span data-stu-id="02270-102">How to Disable Alerts</span></span>
<span data-ttu-id="02270-103">Los administradores utilizan el **disable-alerts** comando para deshabilitar todas las alertas en la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="02270-103">Administrators use the **disable-alerts** command to disable all of the alerts on the specified view.</span></span>  
  
### <a name="to-disable-an-alert"></a><span data-ttu-id="02270-104">Para deshabilitar una alerta</span><span class="sxs-lookup"><span data-stu-id="02270-104">To disable an alert</span></span>  
  
1.  <span data-ttu-id="02270-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02270-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="02270-106">Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="02270-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="02270-107">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="02270-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="02270-108">Tipo de **bm disable-alerts-View:\<nombre de la vista\>**.</span><span class="sxs-lookup"><span data-stu-id="02270-108">Type **bm disable-alerts -View:\<view name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02270-109">Si ha exportado configuraciones de BAM como archivos XML, no modifique el código XML relativo a las alertas.</span><span class="sxs-lookup"><span data-stu-id="02270-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="02270-110">Si modifica el código XML relativo a las alertas e implementa los cambios, bm.exe detectará el cambio y habilitará las alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="02270-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4.  <span data-ttu-id="02270-111">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="02270-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02270-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="02270-112">See Also</span></span>  
 <span data-ttu-id="02270-113">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="02270-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="02270-114">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="02270-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="02270-115">Cómo habilitar las alertas</span><span class="sxs-lookup"><span data-stu-id="02270-115">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md)