---
title: Interactuar adaptador Store y reenvío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d596780a-085d-48db-be44-a3ae58f591d0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f3ce047de1c926e6e144b1351954774c1d3edb5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022594"
---
# <a name="interact-adapter-store-and-forward"></a>Interactuar adaptador Store y reenvío
En Store y el modo de avance (SnF), los mensajes se entregan a una cola en tiempo de envío y se recuperan de la cola de destino. Cuando se usa SnF, la respuesta proviene de SWIFTNet SnF propio y no tiene ningún comentario desde el servicio de respuesta.  
  
 Mensajes y archivos se pueden enrutar en colas con la misma flexibilidad que un mensaje enrutado a un proceso de servidor cuando no se usa SnF. Esta definición es dentro de MRR (dentro de SWIFTNet). Es el receptor que decide en qué cola un mensaje o el archivo se colocará una vez enviado por el remitente. Colocar un mensaje o archivo en una cola se realiza al marcar el mensaje para el modo de entrega SnF (dentro de la RequestControl).  
  
 Recuperar un mensaje de una cola puede producirse en dos modos diferentes, según la selección realizada por el Diseñador de aplicaciones. Se denominan estos modos de inserción y extracción.  
  
 Cuando se usa el modo de inserción, la iniciativa para entregar un mensaje reside con SWIFTNet SnF. El mensaje, a continuación, se "insertan" de SWIFTNet SnF y se recibe por un servidor de aplicaciones en el vínculo de SWIFTNet. La aplicación de servidor tiene que asegurarse de que el mensaje es safestored antes de responder con una confirmación. Esta confirmación indica al SWIFTNet SnF cómo se recibió el mensaje. Una confirmación no contiene cualquier otra lógica de negocio"adicionales".  
  
## <a name="queues-in-swiftnet"></a>Colas de SWIFTNet  
 Las colas contienen los mensajes y los archivos que se enviaron por el remitente entrega al receptor especificado. Las colas también contienen las notificaciones de entrega que se generan mediante SWIFTNet SnF.  
  
 Las colas se definen y configuradas por la organización del receptor. La creación real de una cola se realiza mediante SWIFT en la solicitud del usuario. El remitente no sabe nada acerca de la cola en la que en última instancia, se colocará el mensaje. Que está completamente bajo control del receptor.  
  
 El atributo de tamaño de la ventana de la cola controla el número máximo de mensajes que swiftnet SnF recupera de una cola sin confirmación. El receptor todavía tiene que confirmar el mensaje antes de que se libere el espacio en la ventana.  
  
### <a name="delivery-into-a-queue"></a>Entrega en una cola  
 Para servicios de almacenamiento y reenvío de mediante el receptor decide qué cola se usará para almacenar el mensaje que se envió en el modo de almacenamiento y reenvío.  
  
 Las notificaciones de entrega se colocan en una cola de la entidad de los remitentes, para informar al remitente sobre el estado de entrega de un mensaje enviado. Esto es configurable con las propiedades del adaptador de envío.  
  
## <a name="sessions"></a>Sesiones  
 Al adquirir una cola, se inicia una sesión. Se devuelve el Sw:SnFSessionId para todos los mensajes que se entregan por SWIFTNet SnF. El Sw:SnFSessionId contiene el nombre de cola, el modo de sesión: inserción y un número de sesión. El número de sesión se incrementa para cada sesión. Un ejemplo es:  
  
 **\<SW:SnFSessionId\>bankwxyz_applicq1:p:000458\</Sw:SnFSessionId\>**  
  
 La "p" indica que una sesión de inserción. Una sesión también puede considerarse como una reserva de la cola por un autorizador. Los mensajes subsiguientes deben ser confirmadas por el mismo autorizador.  
  
 Las sesiones no son aplicables al enviar mensajes al almacenamiento y reenvío.  
  
### <a name="push-session-snf"></a>Sesión de inserción SnF  
 La secuencia SnF supone lo siguiente:  
  
- El proceso del cliente ha realizado su trabajo y ahora se puede finalizar. Para ello, deben limpiarse los contextos de seguridad abierto mediante la emisión de un SwSec:DestroyContextRequest. Después de la Sw:TermRequest, el proceso puede exit().  
  
- Se inicia otro cliente. Los pasos de inicialización son los mismos que para el primer cliente. La versión de la cola está realizando un SwCall con el Sw:ReleaseSnFQueueRequest como primitivo de entrada.  
  
   SWIFTNet detiene la entrega de mensajes de la cola en cuanto procesa correctamente la versión de la cola.  
  
  El servidor procesa una solicitud en el momento. SWIFTNet SnF ofrece varias solicitudes fuera de la cola. Estos se almacenan en búfer dentro de la red y el vínculo de SWIFTNet hasta que el servidor responde, o se produce un tiempo de espera.  
  
  Es posible que algunas solicitudes ya que se entregaron, pero no ha confirmado antes de liberar la cola. SWIFTNet SnF no procesa las confirmaciones más de estos mensajes hasta que se libere la cola. Estos mensajes se vuelve a entregados en una sesión posterior.  
  
  Si la aplicación de servidor todavía responde con una confirmación positiva para enviar de una cola después de que el cliente ha emitido la versión de esa cola, pero normalmente esto no sería el caso de las solicitudes se deja a la implementación local.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura de adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Componentes del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Interactuar mensajes del adaptador para el intercambio empresarial](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [Aplicación de cliente del adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [Aplicación de servidor del adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Arquitectura de seguridad adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [Entrega confiable de extremo a otro adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [No rechazo del adaptador de InterAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)