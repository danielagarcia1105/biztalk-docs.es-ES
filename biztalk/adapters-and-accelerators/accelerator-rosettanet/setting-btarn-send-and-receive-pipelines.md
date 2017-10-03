---
title: "Configuración de envío BTARN y canalizaciones de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines, modifying
- modifying, send pipelines
- receive pipelines, modifying
- modifying, receive pipelines
ms.assetid: 00960de0-3763-40aa-9e4b-1fedc7f1eea6
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47f2f12629965c3b01df8cc2f2fd7b1a7ea58a47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-btarn-send-and-receive-pipelines"></a><span data-ttu-id="5ae90-102">Configuración de envío BTARN y canalizaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="5ae90-102">Setting BTARN Send and Receive Pipelines</span></span>
<span data-ttu-id="5ae90-103">De forma predeterminada, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utiliza la norma [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviar canalización (Microsoft.Solutions.BTARN.Pipelines.Send) y el estándar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] (Microsoft.Solutions.BTARN.Pipelines.Receive) de la canalización de recepción cuando se crea puertos de envío de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="5ae90-103">By default, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline (Microsoft.Solutions.BTARN.Pipelines.Send) and the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline (Microsoft.Solutions.BTARN.Pipelines.Receive) when you create partner send ports.</span></span> <span data-ttu-id="5ae90-104">Sin embargo, puede cambiar el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuración para que use una canalización de BizTalk existente o una canalización personalizada que haya creado.</span><span class="sxs-lookup"><span data-stu-id="5ae90-104">However, you can change the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration to use an existing BizTalk pipeline or a custom pipeline that you have created.</span></span> <span data-ttu-id="5ae90-105">Acuerdos de socios comerciales y todos los socios y organizaciones internas, todo, use el mismo enviar canalización y la misma canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="5ae90-105">All trading partner agreements, and all partners and home organizations, use the same send pipeline and the same receive pipeline.</span></span>  
  
 <span data-ttu-id="5ae90-106">Cuando se crea un asociado, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] crea dos puertos de envío para ese socio usar uno asincrónica y otra sincrónica: \< *nombre del asociado de*>. Puerto de envío asincrónico y \< *nombre del asociado de*>. Puerto de envío de sincronización.</span><span class="sxs-lookup"><span data-stu-id="5ae90-106">When you first create a partner, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] creates two send ports for that partner to use, one asynchronous and one synchronous: \<*partner name*>.Async send port and \<*partner name*>.Sync send port.</span></span> <span data-ttu-id="5ae90-107">Estos predeterminado de puertos de envío con el estándar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviar canalización el valor predeterminado es el estándar de recepción de canalización y el puerto de envío de sincronización [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="5ae90-107">These send ports default to the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline, and the sync send port receive pipeline defaults to the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ae90-108">Cambiar el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] de canalización en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración puede restablecer las propiedades que se cambió directamente en el Explorador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5ae90-108">Changing the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipeline in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console might reset properties that you changed directly in BizTalk Explorer.</span></span>  
  
### <a name="to-change-the-send-or-receive-pipeline-that-btarn-uses"></a><span data-ttu-id="5ae90-109">Para cambiar el envío o la canalización de recepción que usa BTARN</span><span class="sxs-lookup"><span data-stu-id="5ae90-109">To change the send or receive pipeline that BTARN uses</span></span>  
  
1.  <span data-ttu-id="5ae90-110">Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.</span><span class="sxs-lookup"><span data-stu-id="5ae90-110">Click **Start**, point to **Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="5ae90-111">En la consola de administración de BTARN, haga clic en el [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] nodo y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5ae90-111">In the BTARN Management Console, right-click the [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] node, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5ae90-112">En el cuadro de diálogo Propiedades globales, seleccione una canalización diferente en la lista desplegable y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5ae90-112">In the Global Properties dialog box, select a different pipeline from the drop-down list, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="5ae90-113">En el **instancias de Host** nodo bajo el [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración** nodo, detenga y reinicie el host.</span><span class="sxs-lookup"><span data-stu-id="5ae90-113">In the **Host Instances** node under the [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration** node, stop and then restart the host.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5ae90-114">Los cambios realizados en las canalizaciones solo aplicarán si reinicia el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5ae90-114">The changes to the pipelines will only take effect if you restart the BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae90-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ae90-115">See Also</span></span>  
 <span data-ttu-id="5ae90-116">[Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md) </span><span class="sxs-lookup"><span data-stu-id="5ae90-116">[Manage configuration, certificates, databases, and security](manage-configuration-certificates-databases-security.md) </span></span>  
 [<span data-ttu-id="5ae90-117">Habilitar el seguimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="5ae90-117">Enabling BAM Tracking</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)