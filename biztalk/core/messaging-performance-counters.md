---
title: Contadores de rendimiento de mensajería | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 162d761a-fe69-45b0-a6af-c5d9f714e0ca
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72604822559d855f51bd24c6eacae3be3be4cbdd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972554"
---
# <a name="messaging-performance-counters"></a>Contadores de rendimiento de mensajería
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **BizTalk: mensajería** y **BizTalk: latencia de mensajería** categorías de objetos de rendimiento:  
  
|**Categoría**|**Contador**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:Mensajería|Ubicaciones de recepción activas|Número de ubicaciones de recepción habilitadas actualmente en esta instancia de host.|  
||Subprocesos de recepción activos|Número de subprocesos del motor de mensajería que procesan actualmente mensajes recibidos de adaptadores que se ejecutan en esta instancia de host. Se incluyen mensajes que los adaptadores de envío han procesado de forma asincrónica.|  
||Mensajes en proceso de envío|Número de mensajes que el motor de mensajería está procesando para su envío. Se incluyen los mensajes que ya están en el procesamiento de la canalización de envío y los mensajes de respuesta para adaptadores de recepción.|  
||Subprocesos de envío activos|Número de subprocesos del motor de mensajería que están procesando mensajes que se van a enviar a los adaptadores. Se incluyen los mensajes de respuesta a los adaptadores de recepción.|  
||Documentos procesados|Documentos procesados.|  
||Documentos procesados/seg.|Documentos procesados/seg.|  
||Documentos recibidos|Documentos recibidos.|  
||Documentos recibidos/seg.|Documentos recibidos por segundo.|  
||Documentos reenviados|Número total de documentos reenviados por adaptadores de envío.|  
||Documentos enviados/lote|Promedio de documentos enviados por lote.|  
||Documentos suspendidos|Documentos suspendidos.|  
||Documentos suspendidos/seg.|Documentos suspendidos por segundo.|  
||Documentos transmitidos/lote|Promedio de mensajes transmitidos por lote.|  
||Proceso de Id.|El Id. de proceso de esta instancia de host.|  
||Lotes recibidos pendientes|Número de lotes recibidos por el motor de mensajería cuyo procesamiento no se ha completado. Se incluyen los lotes procesados de forma asincrónica por los adaptadores de envío.|  
||Mensajes transmitidos pendientes|Número de mensajes transferidos por el motor de mensajería a adaptadores de envío cuyo procesamiento no se ha completado. Se incluyen los mensajes de respuesta para los adaptadores de recepción.|  
||Tiempo de espera de solicitud-respuesta|Número de mensajes de solicitud que no han recibido un mensaje de respuesta dentro del límite de tiempo especificado por el adaptador.|  
||Lotes recibidos restringidos|Número de lotes bloqueados durante la recepción por el motor de mensajería debido a una elevada carga de trabajo. Estos lotes contienen mensajes nuevos que deben procesarse.|  
|BizTalk:Latencia de mensajería|Latencia de entrada (s)|Promedio de latencia en milisegundos desde el momento en que el motor de mensajería recibe un documento del adaptador hasta que se publica en los cuadros de mensajes.|  
||Latencia de salida del adaptador (s)|Promedio de latencia en milisegundos desde el momento en que el adaptador obtiene un documento del motor de mensajería hasta que el adaptador envía el documento.|  
||Latencia de salida (s)|Promedio de latencia en milisegundos desde el momento en que el motor de mensajería recibe un documento del cuadro de mensajes hasta que el adaptador envía el documento.|  
||Latencia de solicitud-respuesta (s)|Promedio de latencia en milisegundos desde el momento en que el motor de mensajería recibe un documento de solicitud del adaptador hasta que se le envía a éste un documento de respuesta.|  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.  
  
#### <a name="if-you-are-using-windows-2008"></a>Si está usando Windows 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **BizTalk: mensajería** objeto de contador de rendimiento y seleccione los contadores que desea supervisar  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.  Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**\>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.  
  
## <a name="see-also"></a>Vea también  
 [Trucos y sugerencias de rendimiento](../core/performance-tips-and-tricks.md)   
 [Medir el rendimiento máximo sostenible del motor](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [Optimizar el uso de recursos mediante la limitación de Host](../core/optimizing-resource-usage-through-host-throttling.md)