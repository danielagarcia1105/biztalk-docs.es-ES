---
title: Habilitar o deshabilitar el seguimiento de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, BAM tracking
- BAM tracking
ms.assetid: 07896fab-88a0-4759-8547-16edcd1eebc0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1132c41e9a017e42139d988d1588f79d7d3afaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207396"
---
# <a name="enabling-or-disabling-bam-tracking"></a><span data-ttu-id="17c6d-102">Habilitar o deshabilitar el seguimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="17c6d-102">Enabling or Disabling BAM Tracking</span></span>
<span data-ttu-id="17c6d-103">Puede habilitar o deshabilitar el seguimiento en cualquier momento, incluso aunque el proceso de reparación de mensajes y nuevo transmisión tiene transacciones en proceso de BAM.</span><span class="sxs-lookup"><span data-stu-id="17c6d-103">You can enable or disable BAM tracking at any point, even while the Message Repair and New Transmission process has transactions in process.</span></span> <span data-ttu-id="17c6d-104">Sin embargo, si deshabilita el seguimiento de BAM mientras las transacciones están en curso, los datos de BAM pueden estar incompletos en las transacciones.</span><span class="sxs-lookup"><span data-stu-id="17c6d-104">However, if you disable BAM tracking while transactions are in process, the BAM data may be incomplete for those transactions.</span></span> <span data-ttu-id="17c6d-105">Si esto ocurre, la tabla de historial todavía contendrá datos precisos de todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="17c6d-105">If this occurs, the history table will still contain accurate data for all instances.</span></span>  
  
 <span data-ttu-id="17c6d-106">Para obtener información acerca de cómo habilitar o deshabilitar el seguimiento como parte del proceso de configuración de componente de A4SWIFT de BAM, consulte [establecer las propiedades de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md).</span><span class="sxs-lookup"><span data-stu-id="17c6d-106">For information about enabling or disabling BAM tracking as part of the A4SWIFT component configuration process, see [Setting A4SWIFT Properties](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md).</span></span>  
  
### <a name="to-enable-or-disable-bam-tracking"></a><span data-ttu-id="17c6d-107">Para habilitar o deshabilitar el seguimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="17c6d-107">To enable or disable BAM Tracking</span></span>  
  
1.  <span data-ttu-id="17c6d-108">En el cliente Web de perfil, haga clic en **Acelerador de BizTalk para SWIFT** en el árbol de consola y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="17c6d-108">In the Profile Web Client, right-click **BizTalk Accelerator for SWIFT** in the console tree, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="17c6d-109">En el cuadro de diálogo Propiedades globales, deshabilitar el seguimiento de BAM mediante anulando la selección de **Habilitar seguimiento de BAM**, o habilitar el seguimiento de BAM mediante selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="17c6d-109">In the Global Properties dialog box, disable BAM tracking by deselecting **Enable BAM Tracking**, or enable BAM tracking by selecting it.</span></span>  
  
3.  <span data-ttu-id="17c6d-110">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="17c6d-110">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="17c6d-111">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**y, a continuación, **configuración de plataforma**.</span><span class="sxs-lookup"><span data-stu-id="17c6d-111">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, and then **Platform Settings**.</span></span> <span data-ttu-id="17c6d-112">Haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="17c6d-112">Click **Host Instances**.</span></span>  
  
5.  <span data-ttu-id="17c6d-113">En el panel de detalles, haga clic en la instancia de host y, a continuación, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="17c6d-113">In the details pane, right-click the host instance , and then click **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17c6d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="17c6d-114">See Also</span></span>  
 [<span data-ttu-id="17c6d-115">Establecer las propiedades de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="17c6d-115">Setting A4SWIFT Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)