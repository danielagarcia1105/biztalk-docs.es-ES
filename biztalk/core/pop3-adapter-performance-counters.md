---
title: POP3 Contadores de rendimiento de adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f799175e-e9e7-4937-93bd-aaec1c43b75a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0f48879fcc00041ce0fa1cf842a066c6da59804
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="pop3-adapter-performance-counters"></a>Contadores de rendimiento del adaptador de POP3
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **adaptador de recepción POP3** categoría de objeto de rendimiento:  
  
|**Categoría**|**Contador**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:Adaptador de recepción POP3|Sesiones activas|Número de conexiones POP3 abiertas que el adaptador administra a la vez.|  
||Bytes recibidos|Número total de bytes descargados por el adaptador de POP3 desde el servidor de correo.|  
||Bytes recibidos/s|Número de bytes descargados por segundo por el adaptador de POP3 desde el servidor de correo.|  
||Mensajes recibidos|Número total de mensajes de correo descargados por el adaptador de POP3 desde el servidor de correo.|  
||Mensajes recibidos/s|Número de mensajes de correo descargados por segundo por el adaptador de POP3 desde el servidor de correo.|  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Realice estos pasos para obtener acceso a los contadores de rendimiento para el adaptador de POP3:  
  
#### <a name="if-you-are-using-windows-2008"></a>Si está usando Windows 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **adaptador de recepción POP3** objeto de contador de rendimiento y seleccione los contadores que pueden supervisar  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.  Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de BizTalk Server](../core/monitoring-biztalk-server.md)  
 [Procesar mensajes de varias partes con el adaptador de POP3](../core/processing-multi-part-messages-with-the-pop3-adapter.md)   
 [Consideraciones para ejecutar controladores del adaptador en un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)