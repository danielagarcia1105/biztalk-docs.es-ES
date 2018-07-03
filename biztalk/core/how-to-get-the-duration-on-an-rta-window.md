---
title: Cómo obtener la duración en una ventana ATR | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- aggregations [BAM], time intervals
- managing [BAM], time intervals
- Get-RTAWindow command [BAM]
ms.assetid: 4e7ad0fd-e7ed-47f7-9435-ef01bbe17afa
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6893200c498fc387d9a1948d332db409cf3b4d61
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992701"
---
# <a name="how-to-get-the-duration-on-an-rta-window"></a>Cómo obtener la duración en una ventana ATR
Los administradores utilizan el **get-rtawindow** comando para obtener la duración de la agregación de en tiempo real (ATR) especificada. El comando recupera la longitud de la duración y las unidades con las que se mide la duración.  
  
### <a name="to-get-the-duration-on-an-aggregation"></a>Para obtener la duración en una agregación  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Desplácese a la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3. Tipo **bm get-rtawindow-View:\<nombre de la vista\> -actividad:\<nombre de la actividad\> -Rta:\<nombre de ATR\>**.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Cómo establecer la duración en una ventana ATR](../core/how-to-set-the-duration-on-an-rta-window.md)