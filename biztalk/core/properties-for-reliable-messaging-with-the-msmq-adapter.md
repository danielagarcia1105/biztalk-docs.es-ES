---
title: Propiedades de mensajería de confianza con el adaptador de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, properties
- queues, MSMQ adapters
- MSMQ adapters, dead letters
- queues, failures [MSMQ adapters]
- MSMQ adapters, impersonation
- MSMQ adapters, remote queues
- queues
- reliability, MSMQ adapters
- impersonation, MSMQ adapters
- MSMQ adapters, queue failures
- clustering, MSMQ adapters
- queues, remote
- MSMQ adapters, reliability
- MSMQ adapters, clustering
ms.assetid: 34bfe028-b2aa-4816-a437-3679d19dffb2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49aebf12c86ae72d5dcb224d078c62afefcb8f46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268852"
---
# <a name="properties-for-reliable-messaging-with-the-msmq-adapter"></a>Propiedades de mensajería de confianza con el adaptador de MSMQ
Es posible mejorar la confiabilidad del envío y la recepción de mensajes con el adaptador de MSMQ mediante el modo de configuración de éste. En este tema se analiza el uso de varias propiedades de configuración para la mensajería confiable.  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a>Ejecutar controladores del adaptador de MSMQ en un host agrupado de BizTalk  
 Una forma de garantizar la alta disponibilidad es ejecutar los controladores del adaptador en varias instancias de host de diferentes servidores de BizTalk Server de forma simultánea. Este enfoque no resulta recomendable para los controladores del adaptador de MSMQ, puesto que MSMQ no admite transacciones de lecturas remotas y el controlador de envío MSMQ mantiene una dependencia en la instancia de ejecución local del servicio MSMQ. Para proporcionar una alta disponibilidad para los controladores de recepción y envío de MSMQ, se recomienda ejecutar los controladores del adaptador de MSMQ en una instancia de host agrupado de BizTalk. Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).  
  
## <a name="queue-failure-and-the-dead-letter-queue"></a>Error de cola y cola de mensajes con problemas de entrega  
 Tras enviar un mensaje correctamente, no habrá ningún error de los mensajes posteriores si la cola de recepción se deshabilita o elimina. Esto podría provocar pérdida de mensajes.  
  
 Establecer el **cola de mensajes no enviados de uso** propiedad de configuración a **True** impide la pérdida de mensajes. Si la propiedad se establece como `True` (valor predeterminado), los mensajes que no recibe la cola van a la cola de mensajes con problemas de entrega.  
  
## <a name="impersonation-and-remote-queues"></a>Colas remotas y suplantación  
 También tendrá que configurar el **usar cola de mensajes no enviados** propiedad de configuración a **True** cuando usa las colas remotas. Si el adaptador de MSMQ suplanta a un usuario sin permiso para utilizar la cola remota, el mensaje podría perderse.  
  
 Cuando la propiedad es **True** y el usuario suplantado no tiene permiso para utilizar la cola remota, el mensaje va a la cola de mensajes no enviados en el equipo local o remoto. En un envío transaccional, el mensaje va a la cola de mensajes con problemas de entrega del equipo local. En un envío no transaccional, el mensaje va a la cola de mensajes con problemas de entrega del equipo remoto.  
  
## <a name="recoverable-and-use-journal-queue-properties"></a>Propiedades Recuperable y Usar cola de diario  
 Tanto el **recuperables** y **usar cola de diario** propiedades guardan copias de los mensajes enviados. Para obtener más información acerca de estas propiedades, vea [cómo configurar una ubicación de recepción de MSMQ](../core/how-to-configure-an-msmq-receive-location.md) y [cómo configurar un puerto de envío MSMQ](../core/how-to-configure-an-msmq-send-port.md).  
  
## <a name="see-also"></a>Vea también  
 [Mensajería confiable con el adaptador de MSMQ](../core/reliable-messaging-with-the-msmq-adapter.md)   
 [Consideraciones para ejecutar controladores del adaptador en un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)