---
title: "Cómo quitar vistas de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, views
- managing [BAM definitions], deleting views
- Remove-View command [BAM]
ms.assetid: 1a43ec81-20b1-41f7-941f-753132ac9ed2
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc49038c30cc6016c79f8e0d309f93217994327f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-remove-bam-views"></a>Cómo quitar vistas de BAM
Los administradores utilizan el **remove-view** comando para quitar una vista de la base de datos de importación principal de BAM.  
  
> [!NOTE]
>  Cuando quita una vista, también quita automáticamente cualquier alerta que esté definida para esa vista.  
  
### <a name="to-remove-bam-views"></a>Para quitar vistas de BAM  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Navegue hasta la carpeta de seguimiento escribiendo **C:\Program Files\Microsoft BizTalk Server 2009\Tracking** en el símbolo del sistema. Presione **ENTRAR**.  
  
3.  Tipo de **bm remove-view-Name:\<nombre de la vista\>**.  
  
4.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Cómo quitar alertas BAM](../core/how-to-remove-bam-alerts.md)