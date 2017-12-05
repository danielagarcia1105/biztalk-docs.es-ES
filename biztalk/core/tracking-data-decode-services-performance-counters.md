---
title: "Contadores de rendimiento de servicios de descodificación de datos de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 733450b1-71b5-48a4-9ac3-cd880324440c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 501e321c5ad0126a39ad9ebbd3a5d2d687f121b0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="tracking-data-decode-services-performance-counters"></a>Contadores de rendimiento del Servicio de descodificación de datos de seguimiento
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **BizTalk: TDDS** categoría de objeto de rendimiento:  
  
|**Categoría**|**Contador**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:TDDS|Lotes que se están procesando|Número de lotes que se procesan dentro de la transacción actual SQL.|  
||Lotes asignados|Número de lotes asignados a la base de datos de destino.|  
||Eventos que se están procesando|Número de eventos que se procesan dentro de la transacción actual SQL.|  
||Eventos asignados|Número de eventos asignados a la base de datos de destino en este segundo.|  
||Registros que se están procesando|Número de registros que se procesan dentro de la transacción actual SQL.|  
||Registros asignados|Número de registros asignados a la base de datos de destino durante este segundo.|  
||N.º total de lotes|Nº total de lotes procesados por TDDS.|  
||N.º total de eventos|Nº total de eventos procesados por TDDS.|  
||N.º total de lotes erróneos|Número total de lotes que no pudo ejecutar TDDS|  
||N.º total de eventos erróneos|Número total de eventos que no pudo ejecutar TDDS.|  
||N.º total de registros|Nº total de registros procesados por TDDS.|  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.  
  
#### <a name="if-you-are-using-windows-2008"></a>Si está usando Windows 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **BizTalk: TDDS** objeto de contador de rendimiento y seleccione los contadores que desea supervisar  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.  Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**\>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.  
  
## <a name="see-also"></a>Vea también  
 [Trucos y sugerencias de rendimiento](../core/performance-tips-and-tricks.md)   
 [Medir el rendimiento máximo sostenible del motor](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [Optimizar el uso de recursos mediante la limitación de Host](../core/optimizing-resource-usage-through-host-throttling.md)