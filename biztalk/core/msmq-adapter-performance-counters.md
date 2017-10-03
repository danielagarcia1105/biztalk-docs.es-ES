---
title: Contadores de rendimiento de adaptador MSMQ | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab8b0342-c6c2-4113-ae54-359df28e5d30
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f346feea5f3c651d466f40fc7c67507292f585a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="msmq-adapter-performance-counters"></a>Contadores de rendimiento del adaptador de MSMQ
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **: adaptador de recepción MSMQ** y **adaptador de envío MSMQ** categorías de objetos de rendimiento:  
  
|**Categoría**|**Contador**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:Adaptador de recepción MSMQ|Bytes recibidos|Número total de bytes recibidos por el adaptador de recepción MSMQ. El contador aumenta cuando el adaptador de recepción MSMQ lee completamente un mensaje desde la cola de origen.|  
||Bytes recibidos/seg.|Número de bytes recibidos por el adaptador de recepción MSMQ por segundo. El contador solo es aplicable a los mensajes que el adaptador de recepción MSMQ ha leído completamente desde la cola de origen.|  
||Mensajes recibidos|Número total de mensajes recibidos por el adaptador de recepción MSMQ por segundo. El contador aumenta cuando el adaptador de recepción MSMQ lee completamente un mensaje desde la cola de origen.|  
||Mensajes recibidos/s|Número de mensajes recibidos por el adaptador de recepción MSMQ por segundo. El contador solo es aplicable a los mensajes que el adaptador de recepción MSMQ ha leído completamente desde la cola de origen.|  
|BizTalk:Adaptador de envío MSMQ|Bytes enviados|Número total de bytes enviados por el adaptador de envío MSMQ. El contador solo aumenta con mensajes que han alcanzado la cola de destino.|  
||Bytes enviados/seg.|Número de bytes enviados por el adaptador de envío MSMQ por segundo. El contador solo es aplicable a mensajes que han alcanzado la cola de destino.|  
||Mensajes enviados|Número total de mensajes enviados por el adaptador de envío MSMQ. El contador solo aumenta con mensajes que han alcanzado la cola de destino.|  
||Mensajes enviados/s|Número de mensajes enviados por el adaptador de envío MSMQ por segundo. El contador solo es aplicable a mensajes que han alcanzado la cola de destino.|  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.  
  
#### <a name="if-you-are-using-windows-2008"></a>Si está usando Windows 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **MSMQ** objeto de contador de rendimiento y seleccione los contadores que desea supervisar  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.  Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.  
  
## <a name="see-also"></a>Vea también  
 [Uso de LoadGen 2007 con MSMQ](../core/using-loadgen-2007-with-msmq.md)   
 [Optimizar el rendimiento del adaptador de MSMQ](../core/optimizing-performance-of-the-msmq-adapter.md)