---
title: Mensajería de solicitud y respuesta | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- request/response messaging, about request/response messaging
- SOAP adapters, message processing
- SOAP adapters, request/response messaging
- request/response messaging
- patterns, messages
- messages, request/response messaging
- request/response messaging, processing
- request/response messaging, SOAP adapters
- messages, patterns
ms.assetid: 1a2f79b5-1f44-4191-8ce1-b3c9043be4f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa8d58fbcac6803adb36495f1aa9982909580e1c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985077"
---
# <a name="request-response-messaging"></a>Mensajería de solicitud-respuesta
En un patrón de mensajería de solicitud-respuesta, una parte envía un mensaje de solicitud y la parte receptora devuelve un mensaje de respuesta. Dos ejemplos típicos del procesamiento de solicitud-respuesta son la interacción que tiene un explorador con un servidor Web que usa el adaptador de HTTP y el procesamiento de servicios Web que usan el adaptador de protocolo de acceso simple a objetos (SOAP). En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la solicitud y los mensajes de respuesta se controlan de forma típica publicación-suscripción. Ésta es una consideración importante para comprender el ajuste de rendimiento de una aplicación de BizTalk, porque es posible que un sistema que requiera un alto rendimiento deba configurarse de forma diferente a otro que requiera baja latencia para mensajes individuales.  
  
 ![Solicitar&#47;mensajería respuesta](../core/media/arch-request-response-1.gif "arch_request-response-1")  
  
 Cuando un adaptador de recepción de tipo solicitud-respuesta recibe un mensaje, BizTalk Server publica primero el mensaje de solicitud en la base de datos de cuadro de mensajes. A continuación, el suscriptor adecuado recibe este mensaje, que es probablemente una orquestación enlazada a un puerto de recepción. Este suscriptor formula un mensaje de respuesta y lo publica en la base de datos de cuadro de mensajes junto con las propiedades que causan que se devuelva al puerto de recepción del que llegó la solicitud. Por último, el editor de la solicitud (el adaptador de recepción que envió la solicitud) recoge el mensaje de respuesta y lo devuelve a la aplicación que realiza la llamada. El diagrama siguiente muestra una representación gráfica detallada de estos pasos.  
  
 ![Solicitar&#47;mensaje de respuesta recibido por el adaptador SOAP](../core/media/arch-request-response-2.gif "arch_request-response-2")  
  
 **Flujo de mensaje de solicitud/respuesta recibido por el adaptador SOAP**  
  
1. El adaptador de SOAP envía mensajes al Gestor extremo.  
  
2. El Gestor extremo publica el mensaje en el cuadro de mensajes.  
  
3. La orquestación, que está enlazada al puerto de recepción y que, por lo tanto, tiene una suscripción para el mensaje, lo recibe y lo procesa.  
  
4. La orquestación envía un mensaje de respuesta que se publica en el cuadro de mensajes.  
  
5. El Gestor extremo recibe el mensaje de respuesta.  
  
6. El Gestor extremo devuelve la respuesta al adaptador de SOAP  
  
   Las implicaciones de este tipo de comportamiento en el rendimiento pueden no verse claramente si no se entiende la implementación interna. BizTalk Server se optimiza inicialmente para escenarios de alto rendimiento, pero también se puede configurar para un entorno de menor rendimiento y que necesite latencia más baja, especialmente en escenarios de solicitud-respuesta. Debe tener en cuenta varios componentes que hay que optimizar en este escenario. En primer lugar, los suscriptores obtienen información acerca de los mensajes publicados mediante un mecanismo de sondeo. Si el intervalo de sondeo se establece demasiado alto, podría ocurrir que las interacciones de tipo solicitud-respuesta tuvieran una latencia más elevada de la deseada.  
  
   Tenga en cuenta que en este escenario, hay dos suscripciones que se debe rellenar: la suscripción para el mensaje inicial, así como el otro para el mensaje de respuesta y esto aumenta el impacto de este intervalo de sondeo. En segundo lugar, los adaptadores de recepción están configurados para insertar mensajes en el cuadro de mensajes por lotes de varios tamaños. La mayoría de adaptadores permiten configurar el tamaño de los lotes mediante la interfaz típica de configuración del adaptador o mediante parámetros en BizTalk Server o en el Registro. Si el tamaño del lote se establece demasiado alto, la latencia para mensajes individuales puede verse aumentada. Para obtener más información acerca de las características de rendimiento [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [planear el rendimiento sostenido](../core/planning-for-sustained-performance.md).  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura en tiempo de ejecución](../core/runtime-architecture.md)