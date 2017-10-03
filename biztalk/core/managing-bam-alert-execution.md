---
title: "Administrar la ejecución de alertas de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], executing alerts
- Notification Services, configuration files
- BAM Management utility
- alerts, executing
ms.assetid: 44bb738e-fa2c-4b32-9e8d-e756d6c3778e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5607bed785ee4f91a341b546dbe81ec39458c4e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-bam-alert-execution"></a><span data-ttu-id="322e0-102">Administrar la ejecución de alertas BAM</span><span class="sxs-lookup"><span data-stu-id="322e0-102">Managing BAM Alert Execution</span></span>
<span data-ttu-id="322e0-103">Se puede modificar la ejecución de alertas BAM mediante la acción de tres elementos, a saber, el portal de BAM, la utilidad de administración de BAM y la cadena ProcessBamNSFiles.vbs.</span><span class="sxs-lookup"><span data-stu-id="322e0-103">BAM Alert execution can be modified through three avenues, The BAM Portal, the BAM management utility, and the ProcessBamNSFiles.vbs script.</span></span>  
  
## <a name="bam-portal"></a><span data-ttu-id="322e0-104">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="322e0-104">BAM Portal</span></span>  
 <span data-ttu-id="322e0-105">Los administradores y trabajadores del conocimiento pueden modificar la forma en la que se entregan las alertas mediante el Administrador de alertas en el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="322e0-105">Knowledge workers and administrators can modify the manner in which alerts are delivered by using the Alert Manager in the BAM portal.</span></span> <span data-ttu-id="322e0-106">Desde el portal de BAM se pueden habilitar o deshabilitar las alertas, modificar los niveles de umbral, modificar las ubicaciones de entrega y otros parámetros que afectan a la ejecución de la alerta.</span><span class="sxs-lookup"><span data-stu-id="322e0-106">From the BAM portal, the Alert can be enabled or disabled, threshold levels can be modified, delivery locations can be modified, as well as other parameters the affect the execution of the alert.</span></span>  
  
 <span data-ttu-id="322e0-107">Para obtener más información acerca de cómo modificar alertas, consulte [Alert Manager en la página de Portal de BAM](../core/alert-manager-on-the-bam-portal-page.md) y [alertas del Portal de BAM](../core/alerts-in-the-bam-portal.md).</span><span class="sxs-lookup"><span data-stu-id="322e0-107">For more information on modifying alerts, see [Alert Manager on the BAM Portal Page](../core/alert-manager-on-the-bam-portal-page.md) and [Alerts in the BAM Portal](../core/alerts-in-the-bam-portal.md).</span></span>  
  
### <a name="bam-management-utility"></a><span data-ttu-id="322e0-108">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="322e0-108">BAM Management Utility</span></span>  
 <span data-ttu-id="322e0-109">Los administradores pueden usar la utilidad de administración de BAM para habilitar, deshabilitar y quitar alertas.</span><span class="sxs-lookup"><span data-stu-id="322e0-109">Administrators can use the BAM Management utility to enable, disable, and remove alerts.</span></span>  
  
 <span data-ttu-id="322e0-110">Para obtener información acerca de cómo usar la utilidad de administración de BAM para administrar alertas, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="322e0-110">For information on using the BAM Management Utility to mange alerts, the following topics:</span></span>  
  
-   [<span data-ttu-id="322e0-111">Cómo habilitar las alertas</span><span class="sxs-lookup"><span data-stu-id="322e0-111">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md) 
  
-   [<span data-ttu-id="322e0-112">Cómo deshabilitar las alertas</span><span class="sxs-lookup"><span data-stu-id="322e0-112">How to Disable Alerts</span></span>](../core/how-to-disable-alerts.md)  
  
-   [<span data-ttu-id="322e0-113">Cómo quitar alertas BAM</span><span class="sxs-lookup"><span data-stu-id="322e0-113">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)  
  
### <a name="modifying-notification-services-configuration-files"></a><span data-ttu-id="322e0-114">Modificar los archivos de configuración de servicios de notificación</span><span class="sxs-lookup"><span data-stu-id="322e0-114">Modifying Notification Services Configuration Files</span></span>  
 <span data-ttu-id="322e0-115">Los administradores pueden utilizar la secuencia de comandos ProcessBamNSFiles.vbs para cambiar la forma en la que los servicios de notificación entregan las alertas.</span><span class="sxs-lookup"><span data-stu-id="322e0-115">Administrators can use the ProcessBamNSFiles.vbs script to change the manner in which the Notification Services delivers alerts.</span></span> <span data-ttu-id="322e0-116">Para obtener más información del archivo de definición de aplicación (ADF) para que Notification Services, vea [http://go.microsoft.com/fwlink/?LinkId=127016](http://go.microsoft.com/fwlink/?LinkId=127016).</span><span class="sxs-lookup"><span data-stu-id="322e0-116">For more information the Application Definition File (ADF) for Notification Services, see [http://go.microsoft.com/fwlink/?LinkId=127016](http://go.microsoft.com/fwlink/?LinkId=127016).</span></span>  
  
 <span data-ttu-id="322e0-117">Para modificar el ADF asociado a BAM, puede seguir estos pasos generales:</span><span class="sxs-lookup"><span data-stu-id="322e0-117">To modify the ADF associated with BAM you can follow these general steps:</span></span>  
  
1.  <span data-ttu-id="322e0-118">Ejecute la secuencia de comandos para obtener la configuración actual y los archivos ADF.</span><span class="sxs-lookup"><span data-stu-id="322e0-118">Run the script to obtain the current configuration and ADF files.</span></span>  
  
2.  <span data-ttu-id="322e0-119">Modifique los archivos.</span><span class="sxs-lookup"><span data-stu-id="322e0-119">Modify the files.</span></span>  
  
3.  <span data-ttu-id="322e0-120">Ejecute la secuencia de comandos para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="322e0-120">Run the script to apply the changes.</span></span>  
  
 <span data-ttu-id="322e0-121">Para obtener más información sobre la secuencia de comandos ProcessBamNSFiles.vbs, consulte [secuencia de comandos de línea de comandos de BAM para archivos de configuración de servicios de notificación](../core/bam-command-line-script-for-notification-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="322e0-121">For more information on the ProcessBamNSFiles.vbs script, see [BAM Command-Line Script for Notification Services Configuration Files](../core/bam-command-line-script-for-notification-services-configuration-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322e0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="322e0-122">See Also</span></span>  
 <span data-ttu-id="322e0-123">[Administración del Portal BAM](../core/managing-the-bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="322e0-123">[Managing the BAM Portal](../core/managing-the-bam-portal.md) </span></span>  
 <span data-ttu-id="322e0-124">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="322e0-124">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="322e0-125">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="322e0-125">BAM Management Utility</span></span>](../core/bam-management-utility.md)