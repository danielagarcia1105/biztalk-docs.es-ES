---
title: Propiedades de contexto de mensaje de BizTalk Server (controladores de envío) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a065ba89-9fdb-47dc-9021-fb95cf347cdc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfd3dca7c807ef48c82d46743e749e19a40001bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016303"
---
# <a name="biztalk-server-message-context-properties-send-handlers"></a>Propiedades de contexto de mensaje de BizTalk Server (controladores de envío)
Además de la carga de mensaje, la información suplementaria que contiene un mensaje debe ser accesible desde la orquestación de BizTalk Server en tiempo de ejecución.  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a>Información de mensaje de TIBCO RV promocionada como propiedades de contexto de mensaje  
  
|Identificación de datos|Tipo|Enrutable|Ubicación de envío|  
|-------------------------|----------|--------------|-------------------|  
|Asunto de envío|string|Sí|La orquestación especifica el asunto de envío de TIBCO Rendezvous. El valor predeterminado es Null. Es obligatorio a menos que se especifique un asunto predeterminado en la configuración del puerto.|  
|Asunto de respuesta|string|Sí|La orquestación proporciona un asunto para los mensajes de respuesta, cuando es pertinente. El valor predeterminado es Null.|  
  
## <a name="getting-a-tibco-reply"></a>Obtención de una respuesta de TIBCO  
 **Pregunta:** ¿cómo el adaptador de BizTalk para TIBCO Rendezvous leer y manipular el asunto de respuesta dentro de una orquestación para que puede usarlo como asunto de envío para la respuesta? ¿Cómo llega el adaptador al contexto de un mensaje de entrada de Rendezvous?  
  
 **Respuesta:** el asunto de respuesta se rellena en el contexto del mensaje entrante y la orquestación puede leerlo. Si finalmente la orquestación produce una respuesta, puede usar ese valor para establecer el asunto de envío del mensaje de respuesta.  
  
1. En un proyecto de BizTalk Server, agregue una referencia a <directorio_instalación>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll.  
  
2. En la orquestación (en algún lugar entre la forma Recepción que controla el mensaje Rendezvous entrante y la forma Envío que envía la respuesta), agregue una forma de construcción/asignación (o una forma de expresión) para realizar alguna acción como la del siguiente ejemplo en la respuesta que construyó:  
  
   ```  
   OutgoingMsg(Rendezvous.SendSubject) = IncomingMsg  
   (Rendezvous.ReplySubject);  
   ```  
   ## <a name="management-assembly"></a>Ensamblado de administración
   TIBCO Rendezvous no proporciona repositorios de metadatos y el ensamblado de administración del Adaptador de Microsoft para TIBCO Rendezvous no proporciona capacidad de exploración ni generación de esquemas. Por lo tanto, debe proporcionar un esquema a BizTalk Server. Para obtener más información, consulte [Install, esquemas y limitaciones](../core/installing-biztalk-adapter-for-tibco-rendezvous.md).
  
   BizTalk Adapter para TIBCO Rendezvous incluye un esquema con tipos predefinidos. El adaptador usa estos tipos al generar mensajes para tipos de datos específicos (matrices).

  
## <a name="see-also"></a>Vea también  
 [Asignación de tipos de datos para controladores de envío de TIBCO Rendezvous](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)   
 [Creación de controladores de envío de TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md)