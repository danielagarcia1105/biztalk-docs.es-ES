---
title: Establecer el tiempo de espera de retraso FRR | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring delay time-out
ms.assetid: 62209bf6-56c8-483a-96d5-328bffc8b680
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbf4c08984876627c0f11f935b0be3e32769b5f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-frr-delay-time-out"></a><span data-ttu-id="1ca33-102">Establecer el tiempo de espera de retraso FRR</span><span class="sxs-lookup"><span data-stu-id="1ca33-102">Setting the FRR Delay Time-Out</span></span>
<span data-ttu-id="1ca33-103">Debe configurar la orquestación FRR tiempo de espera después de algún tiempo, por lo que no esperará la respuesta FNN indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="1ca33-103">You must configure the FRR orchestration to time out after some duration, so it will not wait for the FNN response indefinitely.</span></span> <span data-ttu-id="1ca33-104">Si la duración de tiempo de espera expira, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] publica los mensajes ha superado el tiempo de espera en un controlador de tiempo de espera personalizado.</span><span class="sxs-lookup"><span data-stu-id="1ca33-104">If the time-out duration expires, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] publishes the timed-out messages to a custom time-out handler.</span></span>  
  
### <a name="to-set-the-frr-delay-time-out"></a><span data-ttu-id="1ca33-105">Para establecer el tiempo de espera de retraso FRR</span><span class="sxs-lookup"><span data-stu-id="1ca33-105">To set the FRR delay time-out</span></span>  
  
1.  <span data-ttu-id="1ca33-106">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ca33-106">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="1ca33-107">En el panel izquierdo del Editor del registro, pase a la aceleración de mi equipo/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk para SWIFT/FRR.</span><span class="sxs-lookup"><span data-stu-id="1ca33-107">In the left pane of the Registry Editor, move to My Computer/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk Accelerator for SWIFT/FRR.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1ca33-108">El rol se agregará en la posición en el flujo de trabajo que se define en el nodo funciones.</span><span class="sxs-lookup"><span data-stu-id="1ca33-108">The role will be added in the position in the workflow that is defined in the Roles node.</span></span> <span data-ttu-id="1ca33-109">Para cambiar esa posición, debe realizar el paso 8 para cambiar el orden de los roles en el nodo funciones.</span><span class="sxs-lookup"><span data-stu-id="1ca33-109">To change that position, you need to perform step 8 to change the order of the roles in the Roles node.</span></span>  
  
3.  <span data-ttu-id="1ca33-110">En el panel derecho del Editor del registro, haga doble clic en **DelayTimeout**.</span><span class="sxs-lookup"><span data-stu-id="1ca33-110">In the right pane of the Registry Editor, double-click **DelayTimeout**.</span></span>  
  
4.  <span data-ttu-id="1ca33-111">En el **Editar valor DWORD** cuadro de diálogo, en la **datos del valor** , escriba la duración de tiempo de espera en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="1ca33-111">In the **Edit DWORD Value** dialog box, in the **Value data** box, type the time-out duration in hexadecimal format.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ca33-112">El valor predeterminado para la **FRR DelayTimeout** propiedad es 600 segundos (258 Hexadecimal).</span><span class="sxs-lookup"><span data-stu-id="1ca33-112">The default value for the **FRR DelayTimeout** property is 600 seconds (258 Hexadecimal).</span></span>  
  
5.  <span data-ttu-id="1ca33-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ca33-113">Click **OK**.</span></span>