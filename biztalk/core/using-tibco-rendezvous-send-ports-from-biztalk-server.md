---
title: Uso de puertos de envío de TIBCO Rendezvous desde BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 950c4c367fe053195ba14029405f5015381fc6be
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "24013739"
---
# <a name="using-tibco-rendezvous-send-ports"></a>Uso de puertos de envío de TIBCO Rendezvous
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

## <a name="using-biztalk-to-send-messages"></a>Uso de BizTalk para enviar mensajes
Microsoft BizTalk Adapter para TIBCO Rendezvous usa la API asincrónica (Transport.Send). Puede especificar qué tipo de mensaje envía el adaptador usando una propiedad de contexto de mensaje:  
  
-   **Estructurado**: el adaptador genera un mensaje estructurado TIBRVMSG_MSG, basado en los datos XML recibidos de BizTalk Server. (*)  
  
 Si BizTalk Server envía un mensaje con campos con nombres de más de 127 caracteres de longitud, BizTalk Adapter para TIBCO Rendezvous trunca los nombres en el tamaño máximo de nombre de campo para TIBCO Rendezvous, que es 127.  
  
 Si se proporciona una propiedad `reply subject name`, se usa para establecer el asunto de la respuesta en el mensaje de TIBCO Rendezvous. Se supone que hay un puerto de recepción establecido para escuchar la respuesta y reenviarla a BizTalk Server, o que otro programa de TIBCO Rendezvous se hace cargo de la respuesta.  
  
 La terna (servicio, daemon, red) forma la configuración de transporte. Una configuración de transporte vacía (predeterminada) da lugar a que se envíe un mensaje mediante el objeto de transporte predeterminado.  
  
 Si la página de códigos se deja sin especificar, el adaptador usa la codificación UTF-8 (página de códigos 65001). Los mensajes certificados no están admitidos en el lado del transmisor.  
  
## <a name="see-also"></a>Vea también  
 [Creación de puertos de envío](../core/creating-send-ports2.md)   
 [Creación de controladores de envío de TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md)