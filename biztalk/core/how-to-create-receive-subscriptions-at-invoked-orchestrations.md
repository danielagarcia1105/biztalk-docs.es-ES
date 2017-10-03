---
title: "Cómo crear suscripciones de recepción en Orquestaciones invocadas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3423309a-cb5a-40a5-9582-6ee3ac82b538
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c419101aa16c23f5fd8a644c0fe33f269d06d6ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-receive-subscriptions-at-invoked-orchestrations"></a>Cómo crear suscripciones de recepción en orquestaciones invocadas
Aunque puede pasar mensajes como parámetros a través de la **Iniciar orquestación** forma cuando se inicia una orquestación, en algunos casos puede que desee para enviar mensajes desde la orquestación del autor a la orquestación invocada después de la invocación. Por ejemplo, es posible que no sepa qué mensajes quiere pasar en el momento de la llamada o que otras orquestaciones necesiten enviar mensajes a la orquestación invocada de forma dinámica.  
  
 La manera de enviar un mensaje a una orquestación invocada consiste en pasar una correlación de modo que la orquestación invocada pueda crear la suscripción que la correlación ayuda a definir y, después, pueda recibir el mensaje mediante esa suscripción. Sin embargo, no es suficiente con pasar una correlación y esperar que la orquestación invocada cree la suscripción basada en la correlación y reciba un mensaje mediante esa suscripción. Si lo hace así, los mensajes que envíe desde la orquestación del autor de llamada a la orquestación invocada producirá el error, "No se pudo enrutar el mensaje publicado. No se encontraron suscriptores.". Esto se debe a los siguientes motivos:  
  
-   Hay una condición de anticipación en la orquestación invocada.  
  
-   No hay ningún punto de confirmación para que la orquestación invocada envíe la suscripción a la base de datos de cuadro de mensajes para el enrutamiento de modo que pueda recibir los mensajes.  
  
 Para solucionar este problema, realice los siguientes pasos:  
  
1.  En la orquestación del autor de la llamada, tiene una recepción de activación para recibir el mensaje. Después de recibir el mensaje en la orquestación del autor, inicializar el conjunto de correlaciones y, a continuación, pasa el conjunto de correlaciones y puerto de enlace directo a través de recepción de un autocorrelación la **Iniciar orquestación** forma. El puerto que pase se convierte en un puerto de envío en la orquestación invocada y se usará para devolver el mensaje para sincronizar con la orquestación del autor de la llamada.  
  
2.  En la orquestación invocada, devuelva un mensaje a la orquestación del autor de la llamada a través del puerto de autocorrelación. Se sincroniza con la orquestación del autor de la llamada para evitar condiciones de anticipación y para proporcionar un punto de confirmación mientras se crea la suscripción de recepción en el cuadro de mensajes con el fin de enrutar la orquestación invocada.  
  
3.  La orquestación del autor de la llamada recibe el mensaje a través del puerto de autocorrelación y se sincroniza con la orquestación invocada. Tenga en cuenta que las recepciones del puerto de autocorrelación no necesitan seguidores de correlación. Ahora puede enviar mensajes de forma segura desde la orquestación del autor de la llamada a la orquestación invocada y ésta recibirá los mensajes en función de la correlación.  
  
 Aunque con el enfoque descrito anteriormente se puede conseguir el objetivo establecido, es mejor pasar el mensaje que inicia la correlación en la que quiere recibirlo. Al sincronizar una orquestación de autor de llamada con una orquestación invocada a través de un puerto de autocorrelación, se recomienda que siempre pase el mensaje que necesita para iniciar las correlaciones. Los pasos siguientes constituyen el enfoque más confiable y de mejor rendimiento y de mayor fiabilidad:  
  
1.  En la orquestación del autor de la llamada, tiene una recepción de activación para recibir el mensaje. Después de recibir el mensaje, pasa un mensaje y puerto de enlace directo a través de recepción de un autocorrelación la **Iniciar orquestación** forma. El mensaje que pase se usará para iniciar la correlación en la orquestación invocada. El puerto que pase se convierte en un puerto de envío en la orquestación invocada y se usará para devolver el mensaje para sincronizar con la orquestación del autor de la llamada.  
  
2.  En la orquestación invocada, inicie la correlación y devuelva un mensaje a la orquestación del autor de la llamada. Se sincroniza con la orquestación del autor de la llamada para evitar condiciones de anticipación y para proporcionar un punto de confirmación mientras se crea la suscripción de recepción en el cuadro de mensajes con el fin de enrutar la orquestación invocada.  
  
3.  La orquestación del autor de la llamada recibe el mensaje a través del puerto de autocorrelación y se sincroniza con la orquestación invocada. Tenga en cuenta que recibe el puerto de autocorrelación no necesitan seguidores de correlación. Ahora puede enviar mensajes de forma segura desde la orquestación del autor de la llamada a la orquestación invocada y ésta recibirá los mensajes en función de la correlación.  
  
## <a name="see-also"></a>Vea también  
 [Usar correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md)   
 [Puertos de enlace de uso directo de autocorrelación](../core/how-to-use-self-correlating-direct-bound-ports.md)