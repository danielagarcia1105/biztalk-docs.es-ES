---
title: Habilitar el seguimiento de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM tracking, enabling
- BAM tracking, disabling
ms.assetid: 3fee3315-fba7-4eea-89f3-6a061b450bb8
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90fae70edf7f748de3790aeaa9e13e3381c44c48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-bam-tracking"></a><span data-ttu-id="fbba9-102">Habilitar el seguimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="fbba9-102">Enabling BAM Tracking</span></span>
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]<span data-ttu-id="fbba9-103">admite mejoradas de seguimiento mediante la supervisión de actividad de BizTalk (BAM).</span><span class="sxs-lookup"><span data-stu-id="fbba9-103"> supports enhanced tracking using BizTalk Activity Monitoring (BAM).</span></span> <span data-ttu-id="fbba9-104">Habilitar el seguimiento como parte de las propiedades globales de la configuración de BTARN.</span><span class="sxs-lookup"><span data-stu-id="fbba9-104">You enable tracking as part of the global properties of the BTARN configuration.</span></span> <span data-ttu-id="fbba9-105">Después de habilitar el seguimiento, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] realiza un seguimiento de todos los mensajes para todos los contratos.</span><span class="sxs-lookup"><span data-stu-id="fbba9-105">After you enable tracking, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] tracks all messages for all agreements.</span></span> <span data-ttu-id="fbba9-106">De forma predeterminada, el seguimiento está habilitado.</span><span class="sxs-lookup"><span data-stu-id="fbba9-106">By default, tracking is enabled.</span></span>  
  
 <span data-ttu-id="fbba9-107">Para obtener más información acerca del seguimiento, vea [mejorada de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md).</span><span class="sxs-lookup"><span data-stu-id="fbba9-107">For more information about tracking, see [Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md).</span></span>  
  
### <a name="to-enable-or-disable-bam-tracking"></a><span data-ttu-id="fbba9-108">Para habilitar o deshabilitar el seguimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="fbba9-108">To enable or disable BAM tracking</span></span>  
  
1.  <span data-ttu-id="fbba9-109">Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.</span><span class="sxs-lookup"><span data-stu-id="fbba9-109">Click **Start**, point to **Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="fbba9-110">Haga clic en el [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] nodo en el panel de ámbito y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fbba9-110">Right-click the [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] node in the scope pane, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="fbba9-111">En el **propiedades globales** cuadro de diálogo, seleccione **Habilitar seguimiento de BAM** para habilitar el seguimiento, o desactive esta opción para deshabilitarla.</span><span class="sxs-lookup"><span data-stu-id="fbba9-111">In the **Global Properties** dialog box, select **Enable BAM Tracking** to enable tracking, or clear this option to disable it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fbba9-112">Cada vez que cambie la marca de habilitar para habilitar o deshabilitar el seguimiento, tendrá que reiniciar todos los servicios en la que se ejecutan los procesos públicos y el adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="fbba9-112">Whenever you change the enable flag to enable or disable tracking, you have to restart all services on which the public processes and the HTTP adapter are running.</span></span> <span data-ttu-id="fbba9-113">Esto incluye el servicio de host y el servicio de host aislado.</span><span class="sxs-lookup"><span data-stu-id="fbba9-113">This includes the host service and the isolated host service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbba9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbba9-114">See Also</span></span>  
 <span data-ttu-id="fbba9-115">[Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md) </span><span class="sxs-lookup"><span data-stu-id="fbba9-115">[Manage configuration, certificates, databases, and security](manage-configuration-certificates-databases-security.md) </span></span>  
 <span data-ttu-id="fbba9-116">[Seguimiento mejorado](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="fbba9-116">[Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span></span>  
 [<span data-ttu-id="fbba9-117">Administrar la configuración de BTARN</span><span class="sxs-lookup"><span data-stu-id="fbba9-117">Administering the BTARN Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)