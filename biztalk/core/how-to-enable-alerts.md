---
title: Cómo habilitar alertas | Documentos de Microsoft
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
ms.openlocfilehash: 9986bea177471a236cab888f20d915292d540e5b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968826"
---
# <a name="how-to-enable-alerts"></a>Cómo habilitar alertas
Los administradores utilizan el **enable-alerts** comando para habilitar todas las alertas de la vista especificada.  
  
### <a name="to-enable-an-alert"></a>Para habilitar una alerta  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento. Presione **ENTRAR**.  
  
3.  Tipo de **bm enable-alerts-View:\<nombre de la vista\>**.  
  
    > [!NOTE]
    >  Si ha exportado configuraciones de BAM como archivos XML, no modifique el código XML relativo a las alertas. Si modifica el código XML relativo a las alertas e implementa los cambios, bm.exe detectará el cambio y habilitará las alertas de BAM.  
  
4.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Escriba aquí la descripción del vínculo](../core/how-to-disable-alerts.md)