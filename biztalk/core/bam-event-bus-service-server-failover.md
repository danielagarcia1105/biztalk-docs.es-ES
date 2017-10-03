---
title: "Conmutación por error el servidor de servicio BAM eventos Bus | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f12378c8-09bb-45c1-ade1-d9b20131461f
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c1fafc3e97d9905a6efd0de8ff0f389c2a389bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-event-bus-service-server-failover"></a>Conmutación por error del servicio de bus de eventos de BAM
El servicio de bus de eventos de SAE incluye una lógica de tolerancia a errores que le permite recuperarse y reiniciarse a partir de un error inesperado sin pérdida alguna de datos.  
  
 Cuando habilite el servicio de bus de eventos BAM en varios equipos y se produzca un error en el servicio, la conmutación por errores lógicos detectará que un servicio de bus de eventos BAM ha terminado y la lógica iniciará automáticamente una nueva instancia del servicio de eventos BAM en otro equipo.  
  
 La siguiente ilustración muestra el modo en que el bus de eventos BAM controla el equipo o los errores de red mediante la realización de un equilibrio de carga simple. Se han configurado dos orígenes y un destino antes de que se inicie el servicio de bus de eventos BAM.  
  
 ![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")  
Cómo se equilibra la carga del servicio de bus de eventos BAM  
  
 La carga del servicio de bus de eventos BAM se equilibra mediante la realización de los siguientes pasos:  
  
-   **R: Server1 procesa los datos del evento desde 2 orígenes (sesiones)**. Antes de que se cree una instancia del servicio de bus de eventos BAM en Server2, se crea una instancia de orquestación de bus de eventos BAM en Server1. El servidor encuentra que no hay otros servidores disponibles y por tanto, recoge ambas sesiones para Src1 y Src2.  
  
-   **B: Server2 se pone en línea y se une al grupo de Bus de sucesos SAE**. Después de que se cree una instancia del servicio de bus de eventos BAM en Server2, Server1 coloca una sesión de servicio de bus de eventos BAM y Server2 la recoge.  
  
-   **C: se produce un error en Server1**. Se produce un error en Server1 después de que Server2 se une al grupo de bus de eventos BAM.  
  
-   **D: Server2 procesa los datos del evento desde 2 orígenes (sesiones)**. Server2 recoge ambas sesiones para Src1 y Src2.  
  
## <a name="see-also"></a>Vea también  
 [Administrar el servicio de Bus de eventos BAM](../core/managing-the-bam-event-bus-service.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Actividad económica (BAM) de supervisión](../core/business-activity-monitoring-bam.md)