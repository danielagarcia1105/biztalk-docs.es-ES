---
title: "Propiedades de contexto de mensaje de recepción para TIBCO Rendezvous | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36f4de92dbe7c4c235a1c9ebd092b28b3a198c92
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a>Propiedades de contexto de mensaje de BizTalk Server (controladores de recepción)
Además de la carga del mensaje, se debe poder acceder a la información complementaria que compone un mensaje desde una orquestación de BizTalk Server en tiempo de ejecución.  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a>Información de mensaje de TIBCO RV promocionada como propiedades de contexto de mensaje  
 En la tabla siguiente se enumera la información complementaria:  
  
|Identificación de datos|Tipo|Enrutable|Ubicación de recepción|  
|-------------------------|----------|--------------|----------------------|  
|Enviar a asunto [nulo]|string|Sí|Indica a la orquestación a qué asunto se envío el mensaje.|  
|Asunto de respuesta [nulo]|string|Sí|Indica a la orquestación dónde espera el remitente que se envíe la respuesta, si se espera que una.|  
|Recuento de campo [solo lectura]|unsigned int|No|Número de campos en mensaje de nivel superior. Una propiedad proporcionada por TIBCO RV.|  
|Nombre del remitente CM [solo lectura]|string|Sí|Nombre correspondiente de CM del remitente.|  
|Número de secuencia CM [solo lectura]|long|No|Número de secuencia asignado por el objeto de transporte TIBCO remitente.|  
|Límite de tiempo CM [solo lectura]|double|No|Un límite de tiempo, tras el cual el programa remitente no esperará que el transporte CM certifique la entrega del mensaje.|  
  
## <a name="see-also"></a>Vea también  
 [Asignación de mensaje de TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md)   
 [Creación de controladores de recepción de TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)