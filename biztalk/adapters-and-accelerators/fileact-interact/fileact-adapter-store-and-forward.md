---
title: Almacenamiento de adaptador FileAct y reenvío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50110bf0-75c2-426c-9833-65c3117224b2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1201a5ab5cb45ceba2622aa1c269404acec910df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223572"
---
# <a name="fileact-adapter-store-and-forward"></a>Almacenamiento de adaptador FileAct y reenvío
En el almacén y el modo de avance (SnF), los archivos se entregan a poner en cola en el momento de envío y se recuperan de la cola por parte del destino. Las respuestas intermedias se devuelven por SWIFTNet al remitente hasta que el archivo de forma segura se entregue en el destino.  
  
## <a name="sending-using-snf"></a>Envía mediante SnF  
 Si crea un puerto de envío unidireccional, el adaptador funciona en modo de SnF y envía mensajes a la cola.  
  
## <a name="receiving-using-snf"></a>Recibir mediante SnF  
 SnF FileAct funciona en modo de inserción. Se trata de una opción de tiempo de ejecución.  
  
 Antes de poder recuperar los mensajes de una cola, SWIFTNet SnF debería recibir una solicitud de adquisición de la cola. Esto se logra mediante el adaptador de recepción que se invoca el componente COM + fuera de proceso. Después de una adquisición correcta, se crea una sesión. La cola, a continuación, se abrirá en el modo especificado en la solicitud. Todos los mensajes se devolverá el nodo físico que emitió la solicitud.  
  
 Los mensajes se entregan en el orden especificado (Observe que las transmisiones de interacción y FileAct pueden intercaladas y organizadas por prioridad). Sin embargo, la secuencia de mensajes, es dependiente en el momento en que están almacenados. En el caso de FileAct, esto es el tiempo que se complete el almacenamiento en archivo, no cuando inicia.  
  
### <a name="push-a-file-from-the-queue"></a>Insertar un archivo de la cola  
 El adaptador de FileAct (servidor) recibe un HandleFileRequest de SWIFTNet, que contiene la información de la cola, la sesión y la secuencia. El servidor responde con un HandleFileResponse.  
  
 El servidor, a continuación, emite FetchFileRequest y los archivos se entregan al servidor.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [Primitivas de extremo a extremo de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [Primitivos locales de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [Arquitectura de seguridad del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [Archivo de adaptador FileAct e identificación de transferencia](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [Transferencia de información de soporte de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [Estado del adaptador de FileAct supervisión](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)