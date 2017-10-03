---
title: Entrega ordenada de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, message order
- file transport, message order
- Messaging Engine, transports
- messages, performance
- dynamic send ports, message order
- BTS.SuspendAsNonResumable message context property
- performance, message order
- Messaging Engine, performance
- Messaging Engine, message order
- MessageBox database, message order
- messages, sorting
- backing up, backup transports
- adapters, custom receive adapters
- adapters, messages
- customizing, receive adapters
ms.assetid: 39e0bba6-81f5-4ae0-af92-837b225bc801
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abfb0b78065d4eb3aee022d141cc833399fc1496
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ordered-delivery-of-messages"></a>Entrega ordenada de mensajes
La entrega ordenada de mensajes garantiza que los mensajes publicados con un determinado orden en la base de datos de cuadro de mensajes se entreguen a los suscriptores correspondientes en ese mismo orden.  
  
## <a name="configuring-ordered-message-delivery"></a>Configurar la entrega ordenada de mensajes   
 La entrega ordenada de mensajes se puede configurar en los siguiente lugares:  
  
-   **Recibir** forma de una orquestación  
  
-   Puerto de envío  
  
## <a name="ordered-delivery-with-existing-transports"></a>Entrega ordenada con transportes existentes  
 Los protocolos empleados en determinados transportes, como ARCHIVO y HTTP, no son coherentes con la noción de entrega ordenada. Sin embargo, incluso con este tipo de transportes, si el puerto enlazado con el transporte está marcado para entrega ordenada, BizTalk Server aplica la característica de entrega ordenada y, de este modo, garantiza que el transporte no obtenga el siguiente mensaje de salida hasta que no se haya enviado correctamente el actual. Para ello, BizTalk Server pasa cada mensaje al adaptador del transporte en un único lote y espera hasta que el adaptador haya eliminado correctamente el mensaje del cuadro de mensajes antes de enviar al adaptador el siguiente mensaje, en otro lote.  
  
### <a name="ordered-delivery-for-custom-adapters"></a>Entrega ordenada con adaptadores personalizados  
 Existen algunas cuestiones especiales que deben tenerse en cuenta con relación a los adaptadores de recepción personalizados. Si crea un adaptador personalizado que es compatible con la característica de entrega ordenada al recibir mensajes, el adaptador debería hacer lo siguiente:  
  
-   Después de enviar un lote de mensajes, de recepción personalizada de su adaptador debe esperar la **BatchComplete** devolución de llamada del servidor BizTalk Server antes de enviar el siguiente lote. Para obtener más información, consulte [Interfaces para un adaptador de recepción de Batch-Supported](../core/interfaces-for-a-batch-supported-receive-adapter.md).  
  
-   Si un mensaje tiene errores en la canalización, se debe suspender, si es posible de forma no reanudable. Use la **BTS. SuspendAsNonResumable** message (propiedad) contexto en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para marcar el mensaje correctamente.  
  
> [!NOTE]
>  El orden de los mensajes se puede interrumpir si un mensaje suspendido se reanuda después. Si no desea que se produzca este comportamiento, suspenda los mensajes con errores como no reanudables.  
  
 Para obtener más detalles sobre la creación de un adaptador personalizado, consulte [desarrollar adaptadores personalizados](../core/developing-custom-adapters.md).  
  
## <a name="conditions-for-end-to-end-ordered-message-processing"></a>Condiciones del procesamiento de entrega ordenada de mensajes de un extremo a otro  
 Para proporcionar una entrega ordenada de extremo a extremo, deben cumplirse las siguientes condiciones:  
  
-   Los mensajes se tienen que recibir con un adaptador que conserve el orden de los mensajes cuando se envíen al servidor BizTalk Server. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ejemplos de estos adaptadores son MSMQ y MQSeries. Además, se pueden usar adaptadores HTTP o SOAP para enviar los mensajes de manera ordenada, aunque en ese caso el cliente HTTP o SOAP necesita aplicar el orden al enviar los mensajes de uno en uno.  
  
-   Debe suscribirse a estos mensajes con un puerto de envío que tiene la **entrega ordenada** opción establecida en `True`.  
  
-   Si una orquestación se utiliza para procesar los mensajes, una sola instancia de la orquestación deben usarse, la orquestación debe estar configurada para utilizar un convoy secuencial y la **entrega ordenada** propiedad de la puerto de recepción de la orquestación debe establecerse en `True`.  
  
## <a name="restrictions"></a>Restricciones  
 No se admite la entrega ordenada de mensajes en:  
  
-   Puertos de envío dinámico de [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] y versiones anteriores

- Puertos de envío dinámico de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] (y las versiones más recientes) para los tipos adaptador que **no** compatibilidad con entrega en puertos de envío estáticos ordenada
  
-   Transportes de reserva  

  
## <a name="interactions"></a>Interacciones  
 Si configura la entrega ordenada para un puerto de envío, tenga en cuenta las siguientes interacciones con otros comportamientos configurados en BizTalk Server:  
  
-   Si el puerto de envío tiene establecido "Detener envío de los siguientes mensajes si hay un error en el mensaje actual" como:  
  
    -   **False.** Sólo se suspende (como no reanudable) el mensaje con errores y se siguen procesando todos los mensajes sucesivos. Esto permite mantener el orden de los mensajes sin errores, pero puede causar discontinuidades en la secuencia. Por ejemplo, si se reciben los mensajes 101, 102 y 103, y si se suspende el 102, se seguirán procesando los mensajes 101 y 103 en orden.  
  
    -   **Es true.** Se suspende la instancia de puerto de envío si alguno de los mensajes no puede procesarse. Esto provoca la suspensión de todos los mensajes sucesivos del conjunto ordenado de mensajes. El orden de los mensajes se mantiene al impedir que se entreguen los mensajes sucesivos si no se ha entregado antes el mensaje con errores.  
  
-   Si el puerto de envío de petición-respuesta tiene la propiedad "Detener envío de los mensajes subsiguientes en caso de error de mensaje actual" establecida en `true`, y si el procesamiento de intercambio recuperable está configurado para la fase de desensamblado de la canalización de recepción para la respuesta, a continuación, el puerto de envío no detiene el envío de mensajes (es decir, no se suspende la instancia) si hay un error recuperable en la respuesta de desensamblado.  
  
-   Antes de eliminar un puerto de envío que tenga establecida la característica de entrega ordenada, asegúrese de que no tiene instancias asociadas. Si tiene instancias asociadas, las debería finalizar antes de eliminar el puerto de envío.  
  
## <a name="ordered-delivery-to-file-transport"></a>Entrega ordenada a transportes de archivo  
 Los mensajes llegan al adaptador de archivo en secuencia. El adaptador de archivo puede anexar mensajes a un único archivo o escribir una secuencia de archivos, con los resultados siguientes:  
  
-   Si los datos del mensaje se anexan a un único archivo, los mensajes individuales se anexan en orden. La opción de entrega ordenada en un puerto de envío que utiliza el adaptador de archivo sólo tiene sentido si el transporte de envío funciona en modo de anexar  
  
-   Si los mensajes se escriben en archivos individuales, el orden se refleja en los nombres de archivo, que tendrán un nombre asignado de forma secuencial. En este caso, para los archivos escritos por el adaptador, las propiedades del sistema de archivos relativas a información cronológica (por ejemplo, fecha y hora de creación o modificación del archivo) no reflejan necesariamente la secuencia de llegada de los mensajes.  
  
## <a name="performance-impact-of-ordered-delivery"></a>Impacto de la entrega ordenada sobre el rendimiento  
 Para implementar la entrega ordenada, BizTalk Server debe serializar el procesamiento de los mensajes ordenados en varios puntos de la ruta de los mensajes. Para ello, se usan técnicas de implementación escalada, como el uso de varias instancias de host para el procesamiento paralelo de mensajes. Cuando se utiliza la entrega ordenada, incluso los puertos configurados para ejecutarse en varias instancias de host sólo se ejecutan en una instancia de host para garantizar este tipo de entrega. Sin embargo, en esta situación, se sigue manteniendo una disponibilidad elevada: si hay un error en una instancia de host que esté procesando los mensajes con entrega ordenada, el mensaje con errores se volverá a procesar en otra instancia de host disponible.  
  
 Cuando se habilita la entrega ordenada, el valor predeterminado **intervalo de reintento** es 5 minutos. Para mejorar el rendimiento, configúrelo en el valor mínimo (un minuto). El **intervalo de reintento** propiedad puede aceptar un valor de cero (0), pero no es válida (0). El **número de reintentos** también se puede ajustar el número de reintentos necesario. Por ejemplo, si sabe que la solicitud se debería procesar en <un minuto y que el destino de puerto de envío siempre está accesible, defina ambos valores en 1.  
  
 Para cambiar los valores de reintento, vaya a [cómo configurar opciones avanzadas de transporte para un puerto de envío](http://go.microsoft.com/fwlink/p/?LinkID=267697).  
  
 Para obtener más información sobre la entrega ordenada, consulte:  
  
 [BizTalk:-To-End ordenada de las opciones de procesamiento de mensajes](http://social.technet.microsoft.com/wiki/contents/articles/12887.biztalk-end-to-end-ordered-message-processing-options.aspx)  
  
 [BizTalk: Entrega ordenada](http://social.technet.microsoft.com/wiki/contents/articles/6681.biztalk-ordered-delivery.aspx)  
  
## <a name="see-also"></a>Vea también  
 [Entrega ordenada de mensajes con el adaptador de MSMQ](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md)   
 [Entrega ordenada de mensajes con el adaptador de MQSeries](../core/ordered-delivery-of-messages-with-the-mqseries-adapter.md)