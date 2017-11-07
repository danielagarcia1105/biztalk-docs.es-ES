---
redirect_url: /biztalk/core/using-tibco-rendezvous-receive-ports-from-biztalk-server/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: b1738a0933b5f570edfd882778e50ebf7e2ca730
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-receive-messages"></a>Uso de BizTalk Server desde TIBCO Rendezvous para recibir mensajes
El adaptador de Microsoft BizTalk para TIBCO Rendezvous distribuye eventos de una cola en varios subprocesos. Una ubicación de recepción de BizTalk Server está asociada con una cola de eventos TIBCO Rendezvous y su grupo de subprocesos de distribuidor.  
  
## <a name="memory-use-and-errors"></a>Uso de memoria y errores  
 Al procesar eventos, el adaptador vigila los recursos usados. Si el uso de memoria supera el umbral de marca de agua superior, el adaptador deja de distribuir eventos hasta que llega al consumo de memoria de la marca de agua inferior. Tenga en cuenta que, debido a esto, podrían perderse mensajes de TIBCO Rendezvous para mensajes no certificados (un consumidor de TIBCO RV tiene 60 segundos para quitar mensajes de una cola). Esta pérdida de datos se notifica como un error. Si el adaptador recibe un mensaje NO_MEMORY de aviso del sistema de TIBCO Rendezvous, significa que ya se han perdido mensajes.  
  
 El Adaptador de BizTalk para TIBCO Rendezvous mantiene un estado y ejecuta las tareas de diferente forma basándose en dicho estado. Si el Motor de mensajes de BizTalk notifica un error y el adaptador está configurado para ser una escucha certificada, notificará el error a TIBCO Rendezvous de modo que pueda reenviar el mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md)   
 [Creación de controladores de recepción de TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)