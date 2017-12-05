---
title: "Interactuar el adaptador de almacenamiento y reenvío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d596780a-085d-48db-be44-a3ae58f591d0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c7aff0b2421a19f5fe84ee914c4f9d2bd7ef04e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="interact-adapter-store-and-forward"></a>Interactuar el adaptador de almacenamiento y reenvío
En el almacén y el modo de avance (SnF), los mensajes se entregan a una cola en el momento de envío y se recuperan de la cola por parte del destino. Cuando se usa SnF, la respuesta procede de SWIFTNet SnF propio y no contiene ningún tipo de información desde el servicio de respuesta.  
  
 Mensajes y archivos se pueden enrutar en colas con la misma flexibilidad que un mensaje enrutado a un proceso de servidor si no usa SnF. Esta definición es dentro de MRR (dentro de SWIFTNet). Trata del receptor que decide en qué cola un mensaje o un archivo se colocará una vez enviada por el remitente. Poner un mensaje o archivo en una cola se debe marcar el mensaje para el modo de entrega SnF (dentro de la RequestControl).  
  
 Recuperar un mensaje de una cola puede producirse en dos modos diferentes, según la selección realizada por el Diseñador de aplicaciones. Se llaman a estos modos de inserción y extracción.  
  
 Cuando se usa el modo de inserción, la iniciativa de entregar un mensaje se encuentra con SWIFTNet SnF. El mensaje se "inserta" desde SWIFTNet SnF y se recibe por un servidor de aplicaciones en el vínculo de SWIFTNet. La aplicación de servidor tiene que asegurarse de que el mensaje es safestored antes de responder con una confirmación. Esta confirmación indica al SWIFTNet SnF cómo se recibió el mensaje. Un reconocimiento no contiene ninguna otra lógica adicional "business".  
  
## <a name="queues-in-swiftnet"></a>Colas de SWIFTNet  
 Las colas contienen los mensajes y los archivos que se han enviado por el remitente que se entregará al receptor especificado. Las colas también contienen las notificaciones de entrega que se generan por SWIFTNet SnF.  
  
 Las colas se definen y configuran organización del receptor. La creación real de una cola se realiza mediante SWIFT a petición del usuario. El remitente no sabe nada acerca de la cola en la que finalmente se colocará el mensaje. Que está completamente bajo control del receptor.  
  
 El atributo de tamaño de la ventana de cola controla el número máximo de mensajes que swiftnet SnF se recupera de una cola sin confirmación. El receptor todavía debe confirmar el mensaje antes de que se libere el espacio en la ventana.  
  
### <a name="delivery-into-a-queue"></a>Entrega en una cola  
 Servicios mediante el almacenamiento y reenvío, el receptor decide qué cola se usará para almacenar el mensaje que se envió en el modo de almacenamiento y reenvío.  
  
 Las notificaciones de entrega se colocan en una cola de la entidad de remitentes, para informar al remitente sobre el estado de entrega de un mensaje enviado. Esto es configurable con las propiedades del adaptador de envío.  
  
## <a name="sessions"></a>Sesiones  
 Al adquirir una cola, se inicia una sesión. Se devuelve el Sw:SnFSessionId para todos los mensajes que se entregan por SWIFTNet SnF. El Sw:SnFSessionId contiene el nombre de la cola, el modo de sesión: inserción y un número de sesión. El número de sesión se incrementa para cada sesión. Un ejemplo es:  
  
 **\<SW:SnFSessionId\>bankwxyz_applicq1:p:000458\</Sw:SnFSessionId\>**  
  
 "p" indica que una sesión de inserción. Una sesión también puede considerarse como una reserva de la cola por un autorizador. Los mensajes subsiguientes deben ser confirmadas por el mismo autorizador.  
  
 Las sesiones no son aplicables al enviar mensajes al almacenamiento y reenvío.  
  
### <a name="push-session-snf"></a>Sesión de inserción SnF  
 La secuencia de SnF presupone lo siguiente:  
  
-   El proceso de cliente ha terminado su trabajo y puede finalizar ahora. Para ello, se deben limpiar los contextos de seguridad abierta mediante la emisión de un SwSec:DestroyContextRequest. Después de la Sw:TermRequest, el proceso puede exit().  
  
-   Se inicia otro cliente. Los pasos de inicialización son los mismos que el primer cliente. La versión de la cola esté realizando un SwCall con el Sw:ReleaseSnFQueueRequest como primitivo de entrada.  
  
     SWIFTNet detiene la entrega de mensajes de la cola en cuanto procesa correctamente la versión de la cola.  
  
 El servidor procesa una solicitud en el momento. SWIFTNet SnF ofrece varias solicitudes de la cola. Estos se almacenan en búfer dentro de la red y vínculo SWIFTNet hasta que el servidor responde, o se produce un tiempo de espera.  
  
 Es posible que algunas solicitudes se ya se enviaron, pero no ha confirmado antes de liberar la cola. SWIFTNet SnF no procesa las confirmaciones más de estos mensajes hasta que se libere la cola. Estos mensajes serán volver a entregados en una sesión posterior.  
  
 Se deja a la implementación local si la aplicación de servidor todavía responde con una confirmación positiva para las solicitudes que se entrega desde una cola después de que el cliente ha emitido la versión de esa cola, pero normalmente no es el caso.  
  
## <a name="see-also"></a>Vea también  
 [Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Componentes de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Interactuar mensajes del adaptador para el intercambio de negocios](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [Aplicación de cliente de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Arquitectura de seguridad del adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [Interactuar entrega confiable de adaptador-to-End](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [No rechazo del adaptador de InterAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)