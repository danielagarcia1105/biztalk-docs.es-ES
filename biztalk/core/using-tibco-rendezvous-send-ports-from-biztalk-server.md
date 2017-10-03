---
title: "Uso de puertos de envío de TIBCO Rendezvous desde BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, handling
- message handling
- BizTalk Server, using send ports from
- send ports, using from BizTalk Server
- messages, generating
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e11657e8e15ac0739124178e85f0c7c5c0a70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-send-ports-from-biztalk-server"></a>Uso de puertos de envío de TIBCO Rendezvous desde BizTalk Server
Un puerto de transmisión puede enviar cualquier tipo de mensaje. Cuando BizTalk Server envía un mensaje a través del Adaptador de Microsoft BizTalk para TIBCO Rendezvous, el adaptador genera el mensaje basándose en los valores de las propiedades de contexto del mensaje o bien usa el valor predeterminado y lo envía al destinatario especificado.  
  
> [!NOTE]
>  Según la documentación de TIBCO Rendezvous, no se admiten caracteres comodín en nombres de destinatarios de transmisión.  
  
## <a name="message-handling"></a>Tratamiento de mensajes  
 El adaptador mantiene un estado y trata los mensajes entrantes de BizTalk Server en consecuencia.  
  
-   Si no se puede enviar un mensaje debido a un fallo de transporte, se indica a BizTalk Server que vuelva a enviar más tarde.  
  
-   Si no se puede enviar un mensaje porque el adaptador esté aún inicializándose, el mensaje de BizTalk Server se pondrá en cola. Si se produce un error de inicialización, BizTalk Server tiene instrucciones de volver a enviarlo más adelante.  
  
## <a name="message-generation"></a>Generación de mensajes  
 Con el adaptador de transmisión, el Adaptador de BizTalk para TIBCO Rendezvous ignora el espacio de nombres de destino del mensaje y el elemento raíz. Si el adaptador envía mensajes, envía la carga como está. Si el adaptador genera un mensaje TIBCO Rendezvous estructurado, el nombre del elemento raíz se ignora (el mensaje no tiene nombre). En cada caso, el adaptador usa una propiedad de contexto para encontrar el asunto que debe usar al publicar el mensaje.  
  
 Para obtener más información, consulte [propiedades de contexto de mensaje de BizTalk Server (controladores de envío)](../core/biztalk-server-message-context-properties-send-handlers.md) y [Data Type Mapping para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).  
  
## <a name="see-also"></a>Vea también  
 [Creación de puertos de envío](../core/creating-send-ports2.md)   
 [Crear controladores de envío TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md)