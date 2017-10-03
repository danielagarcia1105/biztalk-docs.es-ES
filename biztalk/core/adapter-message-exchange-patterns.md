---
title: Patrones de intercambio de mensajes de adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54a3fc8f-33d0-4b7e-ad4c-b00912dc3328
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f42368d8687bbed4cbce60243a3b8528364b5fda
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-message-exchange-patterns"></a>Patrones de intercambio de mensajes de adaptador
El marco de trabajo de adaptadores de BizTalk admite un nutrido conjunto de patrones de intercambio de mensajes que los adaptadores pueden utilizar en muchos escenarios potentes de mensajería.  
  
## <a name="one-way-asynchronous"></a>Unidireccional (asíncrono)  
 Aquí el concepto clave es que los mensajes fluyen en una dirección.  
  
 En este patrón de intercambio de mensajes, mensajes de fluyen de unidireccional forma hacia [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a través de un adaptador. El motor de mensajería publica el mensaje en la base de datos de cuadro de mensajes. Si una orquestación tiene una suscripción activa a un mensaje de ese tipo, el mensaje se enruta a dicha orquestación.  
  
 Después de procesar el mensaje, la orquestación lo vuelve a publicar en la base de datos de cuadro de mensajes antes de enrutarlo a un adaptador para su transmisión al extremo especificado.  
  
 Cuando se envía el mensaje al motor, no se espera ninguna respuesta. En la parte de la salida, cuando se transmite el mensaje, no se espera ninguna respuesta. A esto normalmente se le llama mensajería asíncrona y se trata, en muchos aspectos, del bloque de creación fundamental utilizado por el motor para todos los escenarios de mensajería.  
  
## <a name="request-response-style-protocols-sync-on-async"></a>Protocolos de tipo Solicitud-Respuesta (sincrónico sobre asíncrono)  
 Un escenario de solicitud-respuesta consiste en la recepción de un mensaje de solicitud, su proceso y el envío de un mensaje de respuesta. También se conoce como sincrónico en asincrónico (sincronización sobre asíncrono) porque subyacente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] arquitectura es asíncrona por motivos de escalabilidad. Sin embargo, la arquitectura del motor de mensajería de BizTalk permite la exposición de un patrón de intercambio de mensajes sincrónicos sobre estos intercambios asíncronos. Para ello, el motor controla la compleja tarea de establecer una correlación entre los mensajes de solicitud y de respuesta en una arquitectura escalada horizontalmente al vincular entre sí un número de intercambios de mensajes asíncronos para exponer una interfaz sincrónica.  
  
 Por ejemplo, el adaptador de recepción de una página Web que comprueba el inventario podría realizar una llamada SOAP a un SOAP de BizTalk. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Orquesta una serie de servicios Web que agregan la información y devolverlo en una respuesta SOAP. El cliente lo interpreta como una llamada SOAP sincrónica, pero en realidad el motor entrelaza un número de intercambio de mensajes asíncronos.  
  
## <a name="solicit-response-style-protocols"></a>Protocolos de tipo Petición-Respuesta  
 Este escenario se inicia enviando un mensaje de petición y se completa recibiendo un mensaje de respuesta. Se denomina petición-respuesta porque el mensaje inicial enviado solicita un extremo para un mensaje de respuesta. Un escenario que utilice este patrón de intercambio de mensajes podría consistir en una orquestación que realice una llamada HTTP saliente (una petición de respuesta) y que espere la respuesta.  
  
## <a name="request-multiresponse"></a>Solicitud-multirespuesta  
 Este escenario es parecido al de solicitud-respuesta. Sin embargo, en este escenario se pueden devolver varias respuestas para una solicitud determinada. Las API permiten especificar un valor de tiempo de espera y todas las respuestas recibidas en ese intervalo se devuelven al adaptador de respuesta.  
  
## <a name="loop-back"></a>Bucle invertido  
 Este escenario es parecido al de solicitud-respuesta. El mensaje de solicitud se publica del modo habitual, pero el motor se asegura de que el mensaje de respuesta se vuelva a enrutar a la misma instancia de adaptador que publicó el mensaje de solicitud. Puesto que el mensaje de solicitud se publica en la base de datos de cuadro de mensajes, la infraestructura de seguimiento garantiza el seguimiento de los mensajes de solicitud y de respuesta. Éste también resulta un buen modo de invocar un procesamiento de la canalización de envío en el mensaje, recibir el mensaje de salida y volverlo a enviar al adaptador para su procesamiento posterior.  
  
 Un ejemplo de este escenario sería un cliente que requiere una notificación de un mensaje. El mensaje entrante se publica en la base de datos de cuadro de mensajes. Tanto el mensaje como la notificación se devuelven al adaptador en el mismo lote. En este caso, el mensaje entrante se copia con una instancia que se devuelve al cliente, y la otra se procesa del modo habitual. Este escenario concreto también requiere la escritura de un desensamblado XML personalizado.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el marco de trabajo?](../core/what-is-the-adapter-framework.md)