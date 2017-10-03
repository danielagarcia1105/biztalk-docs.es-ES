---
title: Contadores de rendimiento del adaptador HTTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d85473f1-1d67-4990-8d2f-fc7fe0e80108
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21ae11dfb3ecd9a2b5e63449961af70aa3bc6f7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-performance-counters"></a>Contadores de rendimiento del adaptador de HTTP
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **adaptador de recepción HTTP** y **adaptador de envío HTTP** categorías de objetos de rendimiento:  
  
|**Categoría**|**Contador**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:Adaptador de recepción HTTP|Tamaño de cola en memoria|Número de mensajes entrantes de la cola de la cola de memoria interna del adaptador de recepción HTTP.|  
||Mensaje recibido|Número total de solicitudes HTTP recibidas por el adaptador de recepción HTTP. El contador aumenta cuando el adaptador de recepción HTTP lee completamente un mensaje de solicitud desde el cliente HTTP.|  
||Mensajes recibidos/s|Número de solicitudes HTTP recibidas por el adaptador de recepción HTTP por segundo. El contador solo es aplicable para mensajes de solicitud que el adaptador de recepción HTTP ha leído completamente desde el cliente HTTP.|  
||Mensajes enviados|Número total de respuestas HTTP enviadas por el adaptador de recepción HTTP. El contador solo aumenta con mensajes de respuesta que se han enviado correctamente a los clientes HTTP.|  
||Mensajes enviados/s|Número de respuestas HTTP enviadas por el adaptador de recepción HTTP por segundo. El contador solo es aplicable a mensajes de respuesta que se han enviado a clientes HTTP correctamente.|  
||Tiempo de agregación de mensaje a lote|Promedio de tiempo existente entre el momento en el que IIS da un mensaje al adaptador de recepción HTTP y el momento en que el mensaje se agrega a un lote.|  
||Tiempo de generación de lote|Promedio de tiempo que tarda el adaptador de recepción HTTP en crear un lote de mensajes.|  
|BizTalk:Adaptador de envío HTTP|Tamaño de cola en memoria|Número de mensajes salientes de la cola de la cola de memoria interna del adaptador de envío HTTP.|  
||Mensajes recibidos|Número total de mensajes de respuesta HTTP recibidos por el adaptador de envío HTTP. El contador aumenta cuando el adaptador de envío HTTP lee completamente un mensaje de respuesta desde servidores HTTP.|  
||Mensaje recibido/s|Número de respuestas HTTP recibidas por el adaptador de envío HTTP por segundo. El contador solo es aplicable para mensajes de respuesta que el adaptador de  envío HTTP ha leído completamente desde los servidores HTTP.|  
||Mensajes enviados|Número total de solicitudes HTTP enviadas por el adaptador de envío HTTP. El contador solo aumenta con mensajes de solicitud que han alcanzado la dirección URL de destino.|  
||Mensajes enviados/s|Número de solicitudes HTTP enviadas por el adaptador de envío HTTP por segundo. El contador solo es aplicable a mensajes de solicitud que han alcanzado la dirección URL de destino.|  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.  
  
#### <a name="if-you-are-using-windows-2008"></a>Si está usando Windows 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **HTTP** objeto de contador de rendimiento y seleccione los contadores que desea supervisar  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.  Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de BizTalk Server](../core/monitoring-biztalk-server.md)   
 [Configuración del adaptador de HTTP y parámetros de ajuste](../core/http-adapter-configuration-and-tuning-parameters.md)   
 [Consideraciones para ejecutar controladores del adaptador en un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)