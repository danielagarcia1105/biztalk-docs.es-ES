---
title: Uso de BizTalk Server desde TIBCO Rendezvous para recibir mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receiving
- receiving messages
- memory use
ms.assetid: 4eee9c3a-2966-4d5f-ba49-201bb488458c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac81f269e19526f5466e8c12115d617b8171da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-receive-messages"></a>Uso de BizTalk Server desde TIBCO Rendezvous para recibir mensajes
El adaptador de Microsoft BizTalk para TIBCO Rendezvous distribuye eventos de una cola en varios subprocesos. Una ubicación de recepción de BizTalk Server está asociada con una cola de eventos TIBCO Rendezvous y su grupo de subprocesos de distribuidor.  
  
## <a name="memory-use-and-errors"></a>Uso de memoria y errores  
 Al procesar eventos, el adaptador vigila los recursos usados. Si el uso de memoria supera el umbral de marca de agua superior, el adaptador deja de distribuir eventos hasta que llega al consumo de memoria de la marca de agua inferior. Tenga en cuenta que, debido a esto, podrían perderse mensajes de TIBCO Rendezvous para mensajes no certificados (un consumidor de TIBCO RV tiene 60 segundos para quitar mensajes de una cola). Esta pérdida de datos se notifica como un error. Si el adaptador recibe un mensaje NO_MEMORY de aviso del sistema de TIBCO Rendezvous, significa que ya se han perdido mensajes.  
  
 El Adaptador de BizTalk para TIBCO Rendezvous mantiene un estado y ejecuta las tareas de diferente forma basándose en dicho estado. Si el Motor de mensajes de BizTalk notifica un error y el adaptador está configurado para ser una escucha certificada, notificará el error a TIBCO Rendezvous de modo que pueda reenviar el mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md)   
 [Controladores de recepción de creación TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)