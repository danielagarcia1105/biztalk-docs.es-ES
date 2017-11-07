---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: b93e747cdc665fb5a8407ca2a3d052b880236378
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a>TIBCO Rendezvous eventos y ubicaciones de recepción
Cualquier sistema TIBCO Rendezvous puede enviar mensajes a su nombre de asunto de elección. El concepto de *eventos* es la generación de mensajes de otros programas de TIBCO Rendezvous.  
  
 En los pasos siguientes se describe el ciclo de vida de una ubicación de recepción:  
  
1.  Se crea la ubicación de recepción.  
  
2.  La ubicación de recepción se asocia con un host.  
  
3.  La ubicación de recepción se enlaza con una orquestación.  
  
4.  La ubicación de recepción se habilita.  
  
5.  La ubicación de recepción recibe mensajes.  
  
> [!IMPORTANT]
>  Cada ubicación de recepción debe tener un nombre único. Dos ubicaciones de recepción no pueden tener el mismo nombre en la misma implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!IMPORTANT]
>  Asimismo, conviene establecer listas de control de acceso (ACL) seguras en las ubicaciones de destino de las ubicaciones de recepción. Por ejemplo, debe establecer listas ACL seguras para el directorio desde el que la ubicación de recepción de archivos toma los mensajes, de modo que solo los usuarios autorizados puedan entregar mensajes en esta ubicación.  
  
## <a name="see-also"></a>Vea también  
 [Creación de controladores de recepción de TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)