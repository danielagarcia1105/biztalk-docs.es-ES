---
title: Cómo deshabilitar las alertas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- alerts, disabling
- managing [BAM definitions], disabling alerts
- Disable-Alerts command [BAM]
ms.assetid: c5938bc2-1043-4633-8cad-02caf442f2e8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac107300ff14f024da02d6959f695790fe7ff80
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002797"
---
# <a name="how-to-disable-alerts"></a>Cómo deshabilitar alertas
Los administradores utilizan el **disable-alerts** comando para deshabilitar todas las alertas en la vista especificada.  
  
### <a name="to-disable-an-alert"></a>Para deshabilitar una alerta  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento. Presione **ENTRAR**.  
  
3. Tipo **bm disable-alerts-View:\<nombre de la vista\>**.  
  
   > [!NOTE]
   >  Si ha exportado configuraciones de BAM como archivos XML, no modifique el código XML relativo a las alertas. Si modifica el código XML relativo a las alertas e implementa los cambios, bm.exe detectará el cambio y habilitará las alertas de BAM.  
  
4. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Cómo habilitar las alertas](../core/how-to-enable-alerts.md)