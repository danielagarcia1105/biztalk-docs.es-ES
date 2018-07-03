---
title: Publicar y suscribirse arquitectura | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- publish/subscribe architecture, publishers
- architecture, publish/subscribe
- publishing, publish/subscribe architecture
- publish/subscribe architecture, about publish/subscribe architecture
- creating, subscriptions
- publish/subscribe architecture, Messaging Engine
- routing, publishing
- Messaging Engine, publishing
- publish/subscribe architecture, subscribers
- publish/subscribe architecture
- subscriptions, publish/subscribe architecture
- publish/subscribe architecture, creating subscriptions
- subscriptions, creating
- Messaging Engine, subscribing
- publishing, routing
- Messaging Engine, publish/subscribe architecture
- publish/subscribe architecture, events
ms.assetid: 5ed36c1f-077d-468f-a99e-60f97377cef6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39c69d98b1d386d373ebb045e50a554e1a98afb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019826"
---
# <a name="publish-and-subscribe-architecture"></a>Arquitectura de publicación y suscripción
En un diseño de publicación y suscripción, hay tres componentes:  
  
- Publicadores  
  
- Suscriptores  
  
- Eventos  
  
  Entre los publicadores, están los puertos de recepción que publican los mensajes que llegan a sus ubicaciones de recepción, las orquestaciones que publican mensajes cuando envían mensajes o inician otra orquestación en modo asincrónico, y los puertos de envío de solicitud-respuesta que publican mensajes cuando reciben una respuesta del transporte o la aplicación de destino.  
  
  En BizTalk Server, hay dos tipos principales de suscripciones: activación e instancia. Un *suscripción de activación* es la que especifica que un mensaje que satisface la suscripción debería activar, o crear una nueva instancia del suscriptor cuando se recibe. Ejemplos de cosas que crean suscripciones de activación son los puertos de envío con filtros o que están enlazados a orquestaciones, y las formas de recepción de orquestaciones que tienen la propiedad Activar establecida en true. Un *instancia suscripción* indica que se deben enrutar los mensajes que cumplan la suscripción a una instancia de ejecución del suscriptor. Ejemplos de cosas que crean suscripciones de instancia son las orquestaciones con recepciones correlativas y puertos de recepción de solicitud-respuesta que esperan una respuesta de BizTalk Server.  
  
  La diferencia entre los dos tipos de suscripción en el nivel de información es que una suscripción de instancia incluye el Id. de instancia único, almacenado en la tabla de suscripciones de la base de datos de cuadro de mensajes principal. Cuando una instancia de orquestación o un puerto de recepción finaliza el procesamiento, las suscripciones de instancia se quitan del cuadro de mensajes mientras que las suscripciones de activación permanecen activas mientras esté dada de alta la orquestación o el puerto de envío.  
  
## <a name="creating-subscriptions"></a>Crear suscripciones  
 Las suscripciones se crean mediante clases de servicio en BizTalk Server, que se enumeran en la tabla adm_ServiceClass de la base de datos de administración de BizTalk Server. Entre estos servicios están el servicio de almacenamiento en caché; la mensajería de tipo En curso y aislada, alojada por el administrador de extremos; orchestrations/XLANG, alojada por el subservicio XLANG. Cada una de estas clases de servicio puede crear suscripciones y recibir mensajes publicados.  
  
 Una suscripción es una colección de instrucciones de comparación, conocidas como predicados, que implican propiedades de contexto de mensajes y los valores específicos de la suscripción. Por ejemplo, Tipo de mensaje es una propiedad contextual de mensajes y muchas suscripciones especifican el tipo de mensaje en su suscripción. El agente de mensaje inserta información general de la suscripción en la tabla de suscripciones mientras que los predicados específicos van a alguna de las siguientes tablas de predicados, dependiendo del tipo de operación especificada para la suscripción:  
  
- BitwiseANDPredicates  
  
- EqualsPredicates  
  
- EqualsPredicates2ndPass  
  
- ExistsPredicates  
  
- FirstPassPredicates  
  
- GreaterThanOrEqualsPredicates  
  
- GreaterThanPredicates  
  
- LessThenOrEqualsPredicates  
  
- LessThenPredicates  
  
- NotEqualsPredicates  
  
  Todo esto se logra mediante una llamada a la Bts_CreateSubscription_\<nombre de la aplicación\> y Bts_InsertPredicate_\<nombre de la aplicación\> procedimientos almacenados en el cuadro de mensajes de base de datos donde \< nombre de la aplicación\> es el nombre del host de BizTalk que está creando la suscripción.  
  
  Cuando se da de alta un puerto de envío, el puerto crea, en un mínimo, una suscripción para cualquier mensaje con el Id. de transporte de ese puerto de envío en el contexto. Esto permite que el puerto de envío reciba siempre los mensajes dirigidos específicamente a él. Cuando se enlaza un puerto de orquestación a un puerto de envío concreto, la información acerca de ese enlace se almacena en la base de datos de administración de BizTalk. Cuando se envían mensajes desde la orquestación a través del puerto enlazado al puerto de envío físico, se incluye el Id. de transporte en el contexto de forma que el mensaje se enruta hacia ese puerto de envío. Sin embargo, es importante tener en cuenta que este puerto de envío no es el único puerto de envío que puede recibir mensajes enviados desde la orquestación. Cuando una orquestación envía un mensaje, ese mensaje se publica en el cuadro de mensajes con todas las propiedades promocionadas relevantes. El puerto de envío enlazado tiene garantizada la recepción de una copia del mensaje porque el Id. de transporte está en el contexto, pero cualquier otro puerto de envío, u orquestación, puede tener una suscripción que también coincide con las propiedades del mensaje. Es muy importante tener claro que siempre que se publica un mensaje directamente en el cuadro de mensajes, todos los suscriptores con suscripciones coincidentes recibirán una copia del mensaje.  
  
## <a name="publishing-and-routing"></a>Publicar y enrutar  
 Una vez creada y habilitada una suscripción, se debe publicar un mensaje antes de que se lleve a cabo el procesamiento. Los mensajes se publican cuando se reciben en BizTalk Server desde uno de los servicios mencionados anteriormente. Para este tema sobre enrutamiento, nos centraremos en los mensajes recibidos en BizTalk Server a través de un adaptador.  
  
 Cuando se procesan los mensajes en la canalización de recepción, se promocionan las propiedades en el contexto del mensaje. Una vez que un mensaje está listo para publicarlo en el cuadro de mensajes después de haberlo procesado el adaptador y la canalización de recepción, lo primero que ocurre es que el agente de mensaje inserta los valores de las propiedades promocionadas y los valores de predicado del contexto del mensaje en la base de datos de SQL Server de cuadro de mensajes principal. Tener estos valores en la base de datos habilita al agente de mensaje para tomar decisiones de enrutamiento.  
  
 El siguiente paso es para que el agente de mensaje pida a la base de datos de cuadro de mensajes principal que busque suscripciones para el lote de mensajes actual que se va a publicar. Tenga en cuenta que los mensajes no se han escrito aún en la base de datos, solo las propiedades del contexto. El procedimiento almacenado bts_FindSubscriptions del cuadro de mensajes consulta las tablas de suscripciones y predicados identificadas anteriormente y las vincula a las propiedades de mensaje almacenadas para el lote de mensajes actual.  
  
 Con esta información, el agente de mensaje inserta el mensaje una vez en cada base de datos de cuadro de mensajes que tiene una suscripción llamando al procedimiento almacenado bts_InsertMessage. El procedimiento almacenado bts_InsertMessage se llama primero con un identificador de suscripción. En esta primera fase, las llamadas de procedimiento almacenado la int_EvaluateSubscriptions procedimiento almacenan que es responsable de buscar la información detallada de suscripción, comprobando que el mensaje cumple los requisitos de seguridad para la aplicación mediante la comprobación de que predicados coinciden con las propiedades de la aplicación para el host y la inserción de una referencia al mensaje en la cola específica de la aplicación o la cola de suspensión específica de aplicación en función del estado de mensaje. El Id. de mensaje, el Id. de suscripción, el Id. de servicio y otra información de suscripción se insertan en la tabla de la cola específica de la aplicación para cada suscripción que se encuentra para esta aplicación. Tras insertar los mensajes, las propiedades de mensaje y las tablas de propiedades de mensaje se borran de los valores relacionados con el lote.  
  
 El procedimiento almacenado bts_InsertMessage se llama después para cada parte del mensaje. En la primera llamada, se pasa el contexto del mensaje y, a continuación, se inserta en la tabla SPOOL junto con metadatos sobre el mensaje como el número de elementos, el nombre de parte del cuerpo y el Id. Además, la parte del cuerpo del mensaje se inserta en la tabla PARTS mediante el procedimiento almacenado de int_InsertPart. A continuación, se llama al procedimiento almacenado bts_InsertMessage para cada parte restante del mensaje, donde solo se pasan al procedimiento almacenado int_InsertPart para que las guarde en la tabla PARTS.  
  
 Cuando se enrutan los mensajes, se agregan referencias para cada servicio que recibe la instancia específica del mensaje y sus partes insertando registros en las tablas siguientes:  
  
- MessageRefCountLog1  
  
- MessageRefCountLog2  
  
- PartRefCountLog1  
  
- PartRefCountLog2  
  
  Estas referencias evitan que los mensajes y sus partes se eliminen con trabajos de limpieza que se ejecutan periódicamente para impedir que el cuadro de mensajes se llene con datos de mensajes que ya no están en el sistema. Se usan dos tablas para reducir los problemas de contención y bloqueo.  
  
  Ahora que el mensaje se ha enrutado hacia la cola correcta, se ha almacenado en las tablas de cola de impresión y partes, y se hace referencia a él en las colas específicas de la aplicación, las instancias de la aplicación deben extraer los mensajes de las colas. Cada instancia de host tiene una serie de subprocesos de extracción de la cola que sondean continuamente la base de datos en un intervalo configurado en la tabla adm_ServiceClass de la base de datos de administración de BizTalk. Esta misma tabla tiene una columna para indicar el número de subprocesos de extracción de la cola que se usarán. Cada subproceso llama a la base de datos de cuadro de mensajes y llama a la bts_DequeueMessages_\<nombre de la aplicación\> procedimiento adecuado para la aplicación host se está ejecutando en almacenado. Este procedimiento almacenado utiliza semántica de bloqueo para asegurarse de que solo una instancia y un subproceso de eliminación de cola pueden operar en un mensaje en la cola en un momento dado. La instancia de host que obtiene el bloqueo obtiene el mensaje y es responsable de entregarlo al subservicio al que está dirigido.  
  
  Si el servicio que recibe el mensaje es el administrador de extremos, se llama al puerto de envío (o la parte de respuesta de un puerto de recepción de solicitud-respuesta) y, si es el subservicio XLANG/s, se crea o se ubica una orquestación para servir la suscripción en función de si hay un Id. de instancia en la suscripción. El servicio entrega después la referencia al mensaje y su parte de manera que, si no hay más servicios con referencias, los datos del mensaje se pueden eliminar.  
  
## <a name="see-also"></a>Vea también  
 [El motor de mensajería ](../core/the-messaging-engine.md)