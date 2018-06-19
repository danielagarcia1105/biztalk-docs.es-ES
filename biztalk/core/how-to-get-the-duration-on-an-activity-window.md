---
title: Cómo obtener la duración en una ventana actividad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], time intervals
- managing [BAM], time intervals
- Get-ActivityWindow command [BAM]
ms.assetid: d70f6767-f6f7-4ecf-ad9d-4a9d8c76edea
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c5bb2c60133d19887e157f8e06633527e0fa11
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971402"
---
# <a name="how-to-get-the-duration-on-an-activity-window"></a>Cómo obtener la duración en una ventana Actividad
Los administradores utilizan el **get-activitywindow** comando para obtener la duración de la actividad especificada. El comando recupera la longitud de la duración y las unidades con las que se mide la duración.  
  
### <a name="to-get-the-duration-on-an-activity"></a>Para obtener la duración de una actividad  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Escriba bm get-activitywindow-actividad:\<nombre de la actividad\>.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Cómo establecer la duración de una ventana actividad](../core/how-to-set-the-duration-on-an-activity-window.md)