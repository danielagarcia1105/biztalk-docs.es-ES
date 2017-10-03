---
title: Uso de BizTalk Server desde TIBCO Rendezvous para enviar mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, sending
- sending messages
- BizTalk Server, using from TIBCO Rendezvous
ms.assetid: 72057d42-32b5-4748-81e4-5ffb89630f5a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4556ce5ca90b3c62f779d2df55e78c4506458d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-send-messages"></a>Uso de BizTalk Server desde TIBCO Rendezvous para enviar mensajes
Microsoft BizTalk Adapter para TIBCO Rendezvous usa la API asincrónica (Transport.Send). Puede especificar qué tipo de mensaje envía el adaptador usando una propiedad de contexto de mensaje:  
  
-   **Estructurado**: el adaptador genera un mensaje estructurado TIBRVMSG_MSG, basado en los datos XML recibidos de BizTalk Server. (*)  
  
 Si BizTalk Server envía un mensaje con campos con nombres de más de 127 caracteres de longitud, BizTalk Adapter para TIBCO Rendezvous trunca los nombres en el tamaño máximo de nombre de campo para TIBCO Rendezvous, que es 127.  
  
 Si se proporciona una propiedad `reply subject name`, se usa para establecer el asunto de la respuesta en el mensaje de TIBCO Rendezvous. Se supone que hay un puerto de recepción establecido para escuchar la respuesta y reenviarla a BizTalk Server, o que otro programa de TIBCO Rendezvous se hace cargo de la respuesta.  
  
 La terna (servicio, daemon, red) forma la configuración de transporte. Una configuración de transporte vacía (predeterminada) da lugar a que se envíe un mensaje mediante el objeto de transporte predeterminado.  
  
 Si la página de códigos se deja sin especificar, el adaptador usa la codificación UTF-8 (página de códigos 65001). Los mensajes certificados no están admitidos en el lado del transmisor.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md)   
 [Crear controladores de envío TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md)