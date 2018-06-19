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
# <a name="disabling-bam-tracking"></a>Deshabilitar el seguimiento de BAM
De forma predeterminada, está habilitado el seguimiento de BAM para la conciliación de respuesta de FIN. Puede deshabilitar como sigue.  
  
### <a name="to-disable-bam-tracking-for-frr"></a>Para deshabilitar el seguimiento para FRR de BAM  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit**y, a continuación, haga clic en **Aceptar**.  
  
2.  En el panel izquierdo del Editor del registro, pase a la aceleración de mi equipo/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk para SWIFT/FRR.  
  
    > [!IMPORTANT]
    >  Esta entrada del registro debe modificarse en cada equipo que se está ejecutando conciliación de respuesta de FIN.  
  
3.  En el panel derecho del Editor del registro, haga doble clic en **BAMTrackingEnabled**.  
  
4.  En el **Editar valor DWORD** cuadro de diálogo, en la **datos del valor** , escriba **0** para deshabilitar el seguimiento de BAM.  
  
5.  Haga clic en **Aceptar**.