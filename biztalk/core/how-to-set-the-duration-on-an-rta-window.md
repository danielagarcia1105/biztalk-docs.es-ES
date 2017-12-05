---
title: "Cómo establecer la duración de una ventana ATR | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- aggregations [BAM], time intervals
- Set-RTAWindow command [BAM]
- managing [BAM], time intervals
ms.assetid: 3042c3f5-be0f-48fb-9831-daa4868b90fe
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8b43fc846835ab8f24f664d4af54ab99b88576
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-the-duration-on-an-rta-window"></a>Cómo establecer la duración en una ventana ATR
Los administradores utilizan el **set-rtawindow** comando para establecer la duración de la agregación en tiempo real especificada (ATR).  
  
### <a name="to-set-the-duration-on-an-aggregation"></a>Para establecer la duración en una agregación  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento. Presione **ENTRAR**.  
  
3.  Tipo de **bm set-rtawindow-View:\<nombre de la vista\> -actividad:\<nombre de la actividad\> -nombre:\<nombre de ATR\> - TimeLength:\<número entero\>- TimeUnit: día &#124; Hora &#124; Minuto**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Cómo obtener la duración en una ventana ATR](../core/how-to-get-the-duration-on-an-rta-window.md)