---
title: Habilitación del seguimiento de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM tracking, enabling
- BAM tracking, disabling
ms.assetid: 3fee3315-fba7-4eea-89f3-6a061b450bb8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e7260ed387ae5bb09e229c8721f5c40c61d4e80
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971565"
---
# <a name="enabling-bam-tracking"></a>Habilitar el seguimiento de BAM
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] admite mejoradas de seguimiento mediante BizTalk Activity Monitoring (BAM). Habilitar el seguimiento como parte de las propiedades globales de la configuración de BTARN. Después de habilitar el seguimiento, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] realiza un seguimiento de todos los mensajes para todos los contratos. De forma predeterminada, el seguimiento está habilitado.  
  
 Para obtener más información acerca del seguimiento, vea [mejorada de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md).  
  
### <a name="to-enable-or-disable-bam-tracking"></a>Para habilitar o deshabilitar el seguimiento de BAM  
  
1. Haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.  
  
2. Haga clic en el [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] nodo en el panel de ámbito y, a continuación, haga clic en **propiedades**.  
  
3. En el **propiedades globales** cuadro de diálogo, seleccione **Habilitar seguimiento de BAM** para habilitar el seguimiento, o desactive esta opción para deshabilitarlo.  
  
> [!IMPORTANT]
>  Cada vez que cambie la marca de habilitación para habilitar o deshabilitar el seguimiento, tendrá que reiniciar todos los servicios en la que se ejecutan los procesos públicos y el adaptador de HTTP. Esto incluye el servicio de host y el servicio de host aislado.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)   
 [Seguimiento mejorado](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)   
 [Administración de la configuración de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)