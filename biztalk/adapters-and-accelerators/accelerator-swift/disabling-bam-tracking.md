---
title: Deshabilitar el seguimiento de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, disabling BAM tracking
- BAM tracking
ms.assetid: ea5fef0e-7a96-46f5-81d8-9b1d8a5d24d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4e734bd31147ecacc8bbbe98d98297edfb4f0de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209052"
---
# <a name="disabling-bam-tracking"></a><span data-ttu-id="35b4c-102">Deshabilitar el seguimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="35b4c-102">Disabling BAM Tracking</span></span>
<span data-ttu-id="35b4c-103">De forma predeterminada, está habilitado el seguimiento de BAM para la conciliación de respuesta de FIN.</span><span class="sxs-lookup"><span data-stu-id="35b4c-103">By default, BAM tracking is enabled for FIN Response Reconciliation.</span></span> <span data-ttu-id="35b4c-104">Puede deshabilitar como sigue.</span><span class="sxs-lookup"><span data-stu-id="35b4c-104">You can disable it as follows.</span></span>  
  
### <a name="to-disable-bam-tracking-for-frr"></a><span data-ttu-id="35b4c-105">Para deshabilitar el seguimiento para FRR de BAM</span><span class="sxs-lookup"><span data-stu-id="35b4c-105">To disable BAM tracking for FRR</span></span>  
  
1.  <span data-ttu-id="35b4c-106">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="35b4c-106">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="35b4c-107">En el panel izquierdo del Editor del registro, pase a la aceleración de mi equipo/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk para SWIFT/FRR.</span><span class="sxs-lookup"><span data-stu-id="35b4c-107">In the left pane of the Registry Editor, move to My Computer/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk Accelerator for SWIFT/FRR.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="35b4c-108">Esta entrada del registro debe modificarse en cada equipo que se está ejecutando conciliación de respuesta de FIN.</span><span class="sxs-lookup"><span data-stu-id="35b4c-108">This registry entry must be modified on each computer that FIN Response Reconciliation is running on.</span></span>  
  
3.  <span data-ttu-id="35b4c-109">En el panel derecho del Editor del registro, haga doble clic en **BAMTrackingEnabled**.</span><span class="sxs-lookup"><span data-stu-id="35b4c-109">In the right pane of the Registry Editor, double-click **BAMTrackingEnabled**.</span></span>  
  
4.  <span data-ttu-id="35b4c-110">En el **Editar valor DWORD** cuadro de diálogo, en la **datos del valor** , escriba **0** para deshabilitar el seguimiento de BAM.</span><span class="sxs-lookup"><span data-stu-id="35b4c-110">In the **Edit DWORD Value** dialog box, in the **Value data** box, type **0** to disable BAM tracking.</span></span>  
  
5.  <span data-ttu-id="35b4c-111">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="35b4c-111">Click **OK**.</span></span>