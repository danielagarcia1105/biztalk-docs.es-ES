---
title: Orquestaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations
- correlations, orchestrations
- orchestrations, correlations
- orchestrations, deploying
- deploying, orchestrations
- orchestrations, about orchestrations
ms.assetid: fb01f78a-b805-46be-a7d9-2b7597daab96
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0ef446e5cc04e7fc7b4d151d0f034ab0dee695c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991127"
---
# <a name="orchestrations"></a>Orquestaciones
*Orquestaciones* son procesos empresariales ejecutables que se pueden suscribir para recibir y publicar (enviar) mensajes a través de la base de datos de cuadro de mensajes. Además, las orquestaciones pueden construir nuevos mensajes. Los mensajes se reciben mediante la suscripción y la infraestructura de enrutamiento, descrito en [ciclo de vida de un mensaje](../core/lifecycle-of-a-message.md). Cuando se completan las suscripciones para las orquestaciones, se activa una nueva instancia y el mensaje se entrega, o, en caso de que se trate de suscripciones de instancia, la instancia vuelve a hidratarse si es necesario y el mensaje se entrega. Cuando los mensajes se envían desde una orquestación, éstos se publican en el cuadro de mensajes de la misma forma en que un mensaje que llega a la ubicación de recepción con las propiedades adecuadas se inserta en la base de datos para su enrutamiento.  
  
 Los mensajes que se construyen en una orquestación deben colocarse en la base de datos de cuadro de mensajes y servir de referencia para la instancia de orquestación. Sin embargo, no es aconsejable publicar mensajes, pues aún no se han enviado. El subservicio XLANG/s realiza llamadas a la API del agente de mensaje para insertar los mensajes de forma directa. Así se permite al motor de orquestaciones insertar el cuerpo del mensaje en el cuadro de mensajes y asociarlo directamente a la instancia de orquestación que se encuentra en ejecución. La persistencia del mensaje construido en la base de datos de cuadro de mensajes está coordinada con los puntos de persistencia de la orquestación como una optimización adicional de las operaciones de base de datos.  
  
 El elemento de las orquestaciones que hace que la publicación y la suscripción parezcan acciones diferentes es el enlace. Los puertos de orquestación son puertos lógicos que describen una interacción. Debe enlazar estos puertos lógicos a un puerto físico para que se lleve a cabo la entrega de los mensajes, aunque este proceso de enlace no sea otra cosa que configurar suscripciones para el enrutamiento de mensajes.  
  
 Existen cuatro opciones básicas a la hora de enlazar estos puertos:  
  
-   Especificar ahora (especificación directa de los puertos en la orquestación).  
  
-   Especificar más tarde (la especificación se realiza durante la implementación).  
  
-   Mediante un puerto de envío dinámico en el que la dirección está configurada en el código de orquestación.  
  
-   Mediante la creación de un enlace directo desde la orquestación hasta la base de datos de cuadro de mensajes o hasta otra orquestación  
  
## <a name="deploying-orchestrations"></a>Implementar orquestaciones  
 Cuando se especifica un enlace en tiempo de diseño, el puerto físico que coincide con los parámetros configurados en la orquestación se crea durante la implementación de la orquestación. Cuando el enlace se configura durante la implementación, los puertos que cumplan los requisitos del puerto lógico se pueden enlazar al puerto de orquestación. En el enlace dinámico, un puerto físico se crea simplemente de forma similar a la opción Especificar ahora, pero el puerto es un puerto de envío dinámico en el que no se ha configurado la información de dirección.  
  
 Un concepto que confunde a menudo es el hecho de que, aunque un puerto de envío de una orquestación se enlaza a un puerto de envío físico, éste no impide que el mensaje se entregue a otros suscriptores Es decir, si otro puerto de envío posee una suscripción a través de sus filtros para el mensaje que se envía al puerto enlazado, los dos puertos de envío reciben el mensaje. El enlace tan solo crea la suscripción de forma que el mensaje enviado desde la orquestación cumpla siempre los criterios del puerto de envío enlazado. Del mismo modo, el puerto de orquestación enlazado a un puerto de recepción crea la suscripción adecuada según el identificador del mensaje recepción y tipo de puerto. Las suscripciones garantizan que los mensajes que entran y salen de la orquestación se entreguen a los puertos enlazados, pero los mensajes aún pasar por el mismo publicar y suscripción mecanismo descrito anteriormente.  
  
 Probablemente, la opción de enlace de empleo inadecuado y menos frecuente, y que provoca mayores malentendidos, es la opción de Enlace directo. El enlace directo permite a una orquestación publicar mensajes en la base de datos de cuadro de mensajes con propiedades de enrutamiento variables, tal y como ocurre con los mensajes publicados por ubicaciones de recepción. En la mensajería directa sencilla, el mensaje se publica en el cuadro de mensajes con sus propiedades promocionadas para el enrutamiento, como cualquier otro mensaje publicado que se recibe en BizTalk Server. Esto permite a los suscriptores recibir este mensaje, pero, al mismo tiempo, requiere que exista al menos un suscriptor, pues en caso contrario la orquestación recibirá un error en el enrutamiento.  
  
 Otra opción para el enlace directo consiste en utilizar puertos que se autocorrelacionan. Los puertos que se autocorrelacionan son puertos que crean un token de correlación único para utilizarlo en la correlación de mensajes entre instancias. El empleo más habitual de los puertos que se autocorrelacionan consiste en la llamada o el inicio de una orquestación adecuada para un parámetro de puerto. En la orquestación llamada, puede utilizarse el puerto para enviar un mensaje, mientras que en la orquestación que realiza la llamada el mismo puerto puede emplearse para recibirlo. Dado que el puerto posee un token de correlación único, el mensaje se enruta de vuelta a la orquestación de llamada. Los puertos que se autocorrelacionan actúan como canales privados de comunicación entre las instancias de orquestación.  
  
 La última opción consiste en utilizar una orquestación de socio comercial, en la que en ambas orquestaciones el puerto esté configurado con el mismo tipo de puerto compartido y esté seleccionado el mismo puerto en la configuración del puerto. Por ejemplo, en Orch1 y en Orch2 se selecciona Orch2.MyDirectPort. Este tipo de enlace configura una suscripción para la orquestación de recepción, en función del tipo de orquestación de envío, el nombre de puerto y el nombre de operación. De nuevo, esto garantiza que los mensajes se enruten a la instancia correcta.  
  
 Todas las opciones de mensajería directa utilizan la publicación subyacente y el modelo de suscripción. La diferencia entre ellas radica en las propiedades que se utilizan en la creación de suscripciones y en el enrutamiento, así como en los casos de uso que ayuden a resolver.  
  
 Un problema habitual del empleo de puertos de enlace directo se produce cuando la orquestación publica un mensaje al que también está suscrita. Por ejemplo, una orquestación se configura para que se active con un mensaje PurchaseOrder. Esta orquestación utiliza un puerto directo para publicar el mensaje PurchaseOrder en el cuadro de mensajes. No obstante, además de recibir el mensaje como se esperaba, se inicia otra instancia de una orquestación, dado que también poseía una suscripción para mensajes PurchaseOrder. El procesamiento entra en un bucle infinito y el programador puede tardar cierto tiempo en averiguar lo que ocurre.  
  
## <a name="correlation"></a>Correlation  
 *Correlación* en las orquestaciones es el mecanismo para recibir mensajes relacionados en la misma instancia de orquestación de ejecución. En el Diseñador de orquestaciones, un programador sigue estos pasos generales para utilizar una correlación:  
  
- Define un tipo de correlación que incluye las propiedades promocionadas utilizadas para relacionar mensajes.  
  
- Define un conjunto de correlaciones que representa una instancia del tipo de correlación que se acaba de definir.  
  
- En los puertos de envío y recepción, especifica si inician o siguen un conjunto de correlaciones determinado.  
  
  Las suscripciones de instancia entran en juego cuando se inicia un conjunto de correlaciones, pues esto ocurre cuando se crean suscripciones para todos los puertos que siguen este conjunto de correlaciones para recibir mensajes. Puesto que el tipo de correlación define las propiedades que se van a utilizar en la correlación, el motor de orquestaciones puede extraer estas propiedades del mensaje que la acción de iniciación está enviando o recibiendo. Estos valores se utilizan para definir suscripciones para el resto de las acciones restantes que siguen este conjunto de correlaciones.  
  
  Es importante que los mensajes que se reciben en BizTalk Server y que pretenden utilizarse en una correlación tengan las propiedades promocionadas correctamente definidas y promocionadas en el contexto del mensaje. La mayoría de las propiedades se promocionan cuando un componente de desensamblador de una canalización extrae los valores al recibirse el mensaje en un primer momento. Por esta razón no existe posibilidad alguna de utilizar la canalización de recepción PassThrough para recibir mensajes que deben correlacionarse con una instancia de orquestación en ejecución. Este problema surge cuando se utiliza el adaptador de recepción SOAP para recibir mensajes correlacionados, puesto que la canalización PassThrough es el valor predeterminado para la canalización de recepción al utilizar el Asistente para publicación de servicios Web.  
  
## <a name="see-also"></a>Vea también  
 [Artefactos](../core/artifacts.md)   
 [Creación de orquestaciones mediante el Diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md)