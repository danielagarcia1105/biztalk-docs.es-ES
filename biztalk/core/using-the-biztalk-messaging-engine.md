---
title: "Motor de uso de la mensajería de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, Messaging Engine
- adapters, TransportProxy object
- Messaging Engine, adapters
- Messaging Engine, architecture
- TransportProxy object
- Messaging Engine, how to
- architecture, Messaging Engine
- messages, Messaging Engine
ms.assetid: e6b6d1ec-38cd-4721-9673-ae40da003dec
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 701ed3e82eb75b98a948313a99bb4debc65a8cce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-biztalk-messaging-engine"></a>Usar el motor de mensajería de BizTalk
El siguiente diagrama ilustra la arquitectura del motor de mensajería y muestra un escenario en el que un mensaje se recibe en un adaptador y se envía a BizTalk Server.  
  
 ![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")  
Arquitectura del motor de mensajería  
  
 Cada adaptador tiene su propia instancia de un **TransportProxy** objeto que utiliza para interactuar con el motor de mensajería. Los adaptadores funcionan con el motor de mensajería y producen lotes que se procesan de forma atómica. Un lote es una colección de operaciones, como SubmitMessage, SuspendMessage o DeleteMessage.  
  
 A continuación se muestra la secuencia de eventos de un escenario en el que un adaptador envía un mensaje al motor de mensajería:  
  
1.  El adaptador crea un nuevo mensaje y conecta la secuencia de datos al mensaje.  
  
2.  El adaptador obtiene un nuevo lote del motor de mensajería.  
  
3.  El adaptador agrega el mensaje al lote que se va a enviar.  
  
4.  El lote se confirma y se pone en la cola del grupo de subprocesos del motor de mensajería.  
  
5.  El grupo de subprocesos del motor de mensajería empieza a procesar el nuevo lote.  
  
6.  El mensaje se procesa en la canalización de recepción.  
  
7.  La canalización de recepción produce cero o más mensajes. Las canalizaciones pueden consumir mensajes si no devuelven ningún error. Las canalizaciones de recepción pueden producir más de un mensaje; esto ocurre normalmente cuando el componente de desensamblador desensambla un único intercambio en muchos mensajes. Por lo general, la canalización de recepción normaliza el mensaje enviado a XML.  
  
8.  Los mensajes producidos por la canalización se procesarán en el asignador si está configurada la asignación.  
  
9. Los mensajes se publican en el agente de mensaje o en la base de datos de cuadro de mensajes.  
  
10. El motor de mensajería vuelve a llamar al adaptador para notificarle el resultado del lote de trabajo.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Procesamiento de intercambio recuperable](../core/recoverable-interchange-processing.md)  
  
-   [Entrega ordenada de mensajes](../core/ordered-delivery-of-messages.md)  
  
-   [Tratamiento de errores](../core/error-handling.md)  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server procesa los mensajes de gran tamaño](../core/how-biztalk-server-processes-large-messages.md)   
 [Características de rendimiento del motor](../core/engine-performance-characteristics.md)   
 [Medir el rendimiento máximo sostenible del motor](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [Escenarios de prueba para medir MST del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [Con la herramienta de Microsoft BizTalk LoadGen 2007](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)