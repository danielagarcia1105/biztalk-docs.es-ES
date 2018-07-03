---
title: Limitación de supervisión mediante reglas de umbral de rendimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc2c3024-a54b-4485-8110-c2ec9ec52721
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5bf8f327cbdb12ebe0723941afd6e37b5d2409
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968053"
---
# <a name="monitoring-throttling-using-performance-threshold-rules"></a>Limitación de supervisión mediante reglas de umbral de rendimiento
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se inicializará la limitación para proteger el sistema de alcanzar un estado irrecuperable. La limitación puede indicar un problema y le ayuda a identificar su origen. Después de haber identificado la causa del cuello de botella en función del estado de limitación, analice otros contadores de rendimiento para reducir el origen del problema.  
  
 Por ejemplo, podría ser elevada contención en la base de datos debido al uso elevado de CPU, lo que podría estar provocada por la paginación excesiva en disco, que a su vez, podría deberse a condiciones de memoria insuficiente. Elevada contención en el cuadro de mensajes también podría deberse a la contención de bloqueo alto, lo que podría ser debido a las unidades de disco saturadas.  
  
 Supervisar el estado de limitación de entrega de mensajes y el estado de limitación de publicación de mensaje para cada instancia de host suele ser un buen lugar para comenzar al solucionar problemas de limitación. Si el valor de estos contadores no es cero, es indicativo de que se produce la limitación dentro del sistema de BizTalk Server y es posible analizar la causa del cuello de botella. Para obtener descripciones de los otros contadores de rendimiento, consulte [identificar cuellos de botella en el nivel de base de datos](http://go.microsoft.com/fwlink/?LinkID=154678) (<http://go.microsoft.com/fwlink/?LinkID=154678>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
## <a name="biztalk-server-system-performance-counters"></a>Contadores de rendimiento del sistema de BizTalk Server  
  
|Objeto|Instancia|Contador|Finalidad de la supervisión|  
|------------|--------------|-------------|------------------------|  
|Procesador|_Total|% de tiempo de procesador|Contención de recursos|  
|Procesar|BTSNTSvc|Bytes virtuales|Pérdida o inundación de memoria|  
|Procesar|BTSNTSvc|Bytes privados|Pérdida o inundación de memoria|  
|Procesar|BTSNTSvc|Recuento de identificadores|Contención de recursos|  
|Procesar|BTSNTSvc|Número de subprocesos|Contención de recursos|  
|Disco físico|_Total|% de tiempo de inactividad|Contención de recursos|  
|Disco físico|_Total|Current Disk Queue Length|Contención de recursos|  
  
## <a name="biztalk-application-counters"></a>Contadores de la aplicación de BizTalk  
  
|Objeto|Instancia|Contador|Descripción|  
|------------|--------------|-------------|-----------------|  
|Mensajería de BizTalk|RxHost|Documentos recibidos/seg.|Tasa de entrada|  
|Mensajería de BizTalk|TxHost|Documentos procesados/seg.|Tasa de salida|  
|XLANG/orquestaciones|PxHost|Orquestaciones completadas/seg|Tasa de procesamiento|  
|BizTalk: Cuadro de mensajes: contadores generales|MsgBoxName|Tamaño de cola de impresión|Tamaño acumulado de todas las colas de host|  
|BizTalk: Cuadro de mensajes: contadores generales|MsgBoxName|Tamaño de los datos de seguimiento|Tamaño de la tabla TrackingData en el cuadro de mensajes|  
|BizTalk: Cuadro de mensajes: contadores de Host|PxHost:MsgBoxName|Cola de host - Longitud|Número de mensajes en la cola de host específica|  
|BizTalk: Cuadro de mensajes: contadores de Host|TxHost:MsgBoxName|Cola de host - Longitud|Número de mensajes en la cola de host específica|  
|BizTalk: Agente de mensaje|RxHost|Tamaño de base de datos|Tamaño de la cola de publicación (PxHost)|  
|BizTalk: Agente de mensaje|PxHost|Tamaño de base de datos|Tamaño de la cola de publicación (TxHost)|  
|BizTalk: Agente de mensaje|HostName|Estado de limitación de entrega de mensajes|Afecta a los transportes XLANG y de salida|  
|BizTalk: Agente de mensaje|HostName|Estado de la limitación de publicación de mensajes|Afecta a los transportes XLANG y de entrada|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Supervisión de limitación](../technical-guides/monitoring-for-throttling.md)