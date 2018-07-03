---
title: Cómo habilitar alertas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enable-Alerts command [BAM]
- managing [BAM definitions], enabling alerts
- alerts, enabling
ms.assetid: 18f494b7-54fb-4aaf-89d1-7e3fe91f35c6
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9fee863613feea040e05856d8246f94b4a3f835
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969157"
---
# <a name="how-to-enable-alerts"></a>Cómo habilitar alertas
Los administradores utilizan el **enable-alerts** comando para habilitar todas las alertas en la vista especificada.  
  
### <a name="to-enable-an-alert"></a>Para habilitar una alerta  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento. Presione **ENTRAR**.  
  
3. Tipo **bm enable-alerts-View:\<nombre de la vista\>**.  
  
   > [!NOTE]
   >  Si ha exportado configuraciones de BAM como archivos XML, no modifique el código XML relativo a las alertas. Si modifica el código XML relativo a las alertas e implementa los cambios, bm.exe detectará el cambio y habilitará las alertas de BAM.  
  
4. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Escriba aquí la descripción del vínculo](../core/how-to-disable-alerts.md)