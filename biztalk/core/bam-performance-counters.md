---
title: Contadores de rendimiento de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], performance counters
- performance, counters [BAM]
ms.assetid: e23f7038-36a5-4957-bc73-47011763d109
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4307f72f149405fbc04e4e6cc51efe87229c2bff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-performance-counters"></a>Contadores de rendimiento de BAM
Los contadores de rendimiento permiten controlar aspectos específicos del trabajo llevado a cabo por el servicio de bus de eventos BAM. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 En la tabla siguiente se enumeran los contadores de rendimiento disponibles en la Supervisión de la actividad económica (BAM).  
  
|Contador|Description|  
|-------------|-----------------|  
|Eventos que se están procesando|Número de eventos que está procesando actualmente el servicio de bus de eventos BAM|  
|Lotes que se están procesando|Número de lotes que está procesando actualmente el servicio de bus de eventos BAM|  
|eventos asignados|Número de eventos que el servicio de bus de eventos BAM ha asignado al servidor SQL Server en el último segundo.|  
|Registros asignados|Número de registros que el servicio de bus de eventos BAM ha asignado al servidor SQL Server en el último segundo.|  
|Lotes asignados|Número de lotes que el servicio de bus de eventos BAM ha asignado al servidor SQL Server en el último segundo.|  
|N.º total de eventos|Número de eventos que el servicio de bus de eventos BAM ha procesado desde que fue iniciado.|  
|N.º total de registros|Número de registros que el servicio de bus de eventos BAM ha procesado desde que fue iniciado.|  
|N.º total de lotes|Número de lotes que el servicio de bus de eventos BAM ha procesado desde que fue iniciado.|  
|N.º total de lotes erróneos|Número de lotes que el servicio de bus de eventos BAM no ha podido procesar desde que fue iniciado.|  
|N.º total de eventos erróneos|Número de eventos que el servicio de bus de eventos BAM no ha podido procesar desde que fue iniciado.|  
  
 Los contadores de rendimiento están ubicados en el monitor de rendimiento (perfmon), bajo el objeto de rendimiento BizTalk:TDDS. El nombre de instancia de los contadores de rendimiento es una combinación del nombre del servidor de origen y el nombre de la base de datos de origen. Si dos de los servicios de bus de eventos BAM se están ejecutando en el mismo equipo, utilizando dos bases de datos de origen distintas, verá dos instancias de los contadores de servicios de bus de eventos BAM.  
  
## <a name="see-also"></a>Vea también  
 [Administrar el servicio de Bus de eventos BAM](../core/managing-the-bam-event-bus-service.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Administración de BAM](../core/managing-bam.md)