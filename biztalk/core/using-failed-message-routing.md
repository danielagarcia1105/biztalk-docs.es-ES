---
title: Enrutamiento de mensajes de error | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.ops.tsroutingfailure
ms.assetid: d081934c-600e-44ce-8ba4-fb646d494589
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af6d006aeebd5e2a5f8625a994c8a6f9b0cb6f6a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289668"
---
# <a name="using-failed-message-routing"></a>Utilizar el enrutamiento de mensajes con errores
La funcionalidad de control de errores permite al diseñador designar un control automatizado de los mensajes con errores como alternativa al comportamiento tradicional (ahora como configuración predeterminada) de colocar los mensajes con errores en la cola de suspensión. Este control automatizado enruta un mensaje con error a cualquier destino de enrutamiento de suscripción, como un puerto de envío o una orquestación. El mensaje de error es un clon del mensaje original, que incluye todas las propiedades anteriormente promocionadas ahora degradadas y con las propiedades seleccionadas relativas al error de mensajería específico promocionadas en el contexto del mensaje.  
  
> [!WARNING]
>  Los mensajes con errores contienen una copia del mensaje original. Si el mensaje original contiene información confidencial, diseñe los procesos manuales y automáticos de mensajes con errores para evitar que se revelen accidentalmente.  
  
## <a name="what-does-failed-message-routing-consist-of"></a>¿De qué se compone el enrutamiento de mensajes con errores?  
 Cuando el enrutamiento de mensajes con errores está habilitado, BizTalk Server no suspende el mensaje, sino que lo enruta. El enrutamiento de mensajes con errores se puede habilitar tanto en puertos de recepción como de envío, con el siguiente resultado:  
  
-   Si el enrutamiento de mensajes con errores está habilitado en un puerto de recepción y un mensaje tiene errores en la canalización de recepción o en el enrutamiento, se genera un mensaje con errores. Si se produce un error en la fase de desensamblado o antes de ella, el mensaje de error es un clon del intercambio original.  
  
-   Si el enrutamiento de mensajes con errores está habilitado en un puerto de envío y el mensaje tiene errores en la canalización de envío, se genera un mensaje con errores.  
  
 Cuando se genera un mensaje con errores, BizTalk Server promociona las propiedades de contexto del mensaje relacionado con el informe de errores y degrada las propiedades de contexto del mensaje normal antes de publicar el mensaje con errores. Compare este comportamiento con el comportamiento predeterminado cuando el enrutamiento de mensajes con errores no está habilitado: los mensajes que dan error se suspenden.  
  
## <a name="what-kinds-of-messaging-failures-trigger-an-error-message"></a>¿Qué tipos de errores de mensajería desencadenan un mensaje de error?  
 Cualquier error que se produzca en el procesamiento de los adaptadores, en el procesamiento de las canalizaciones, en las asignaciones o en el enrutamiento de mensajes tiene como resultado un mensaje de error si el enrutamiento de mensajes con errores está habilitado. Cuando se produce un error de mensajería en una orquestación, durante la recepción desde un puerto de recepción o durante el envío a un puerto de envío, el mensaje de error resultante se asocia con los puertos de mensajería con los que está enlazada la orquestación.  
  
## <a name="subscribing-to-an-error-message"></a>Suscribirse a un mensaje de error  
 Los mensajes de error se entregan a las orquestaciones o a los puertos de envío que se han suscrito para recibirlos. Una suscripción normalmente selecciona un mensaje de error según el nombre del puerto en el que se ha producido el error de mensajería (un puerto envío o un puerto de recepción). Una suscripción también podría filtrar otras propiedades promocionadas al contexto del mensaje de error (por ejemplo, **InboundTransportLocation** o **FailureCode**).  
  
## <a name="error-message-specification"></a>Especificación de mensajes de error  
 Un mensaje de error es un clon del mensaje con errores original que contiene todas las propiedades anteriormente promocionadas ahora degradadas y un juego de propiedades específicas del error promocionadas en el contexto del mensaje. Las propiedades promocionadas anteriormente se degradan para evitar la entrega imprevista a los suscriptores no designados para recibir el mensaje de error. El mensaje de error se publica para su distribución a los suscriptores (orquestaciones, puertos de envío y grupos de puertos de envío).  
  
 Las propiedades que se promocionan al contexto de un mensaje de error todos quedan en el **ErrorReport** espacio de nombres en el servidor BizTalk Server. Son las siguientes:  
  
|Nombre de propiedad|Tipo de datos|Promocionada|Descripción|  
|-------------------|---------------|--------------|-----------------|  
|FailureCode|System.String|Sí|Código de error. Un valor hexadecimal que se notifica en la consola de administración de BizTalk Server.|  
|FailureCategory|System.Int32|Sí|No se usa esta propiedad. Su valor no está definido.|  
|Descripción|System.String|No|Descripción del error. El mismo texto de diagnóstico como está escrito en el registro de eventos de aplicación con respecto a este error de mensajería.|  
|MessageType|System.String|Sí|Mensaje de tipo mensaje con errores, o vacío si el tipo de mensaje es indeterminado.<br /><br /> BizTalk Server utiliza el tipo de mensaje para asociar los mensajes con los esquemas XML correspondientes. El tipo de mensaje se forma mediante la concatenación del espacio de nombres del esquema con el nodo raíz del esquema: http://mynamespace#rootnode. **Nota:** conjunto de mensajes que generan errores antes de que se determina el tipo de mensaje no tiene esta propiedad.|  
|ReceivePortName|System.String|**Promocionada** si el error se produjo durante el procesamiento de entrada (en un puerto de recepción).<br /><br /> **No promocionada** si el error se produjo en un puerto de envío.|Nombre del puerto de recepción donde se produjo el error.|  
|InboundTransportLocation|System.String|**Promocionada** si el error se produjo durante el procesamiento de entrada (en un puerto de recepción).<br /><br /> **No promocionada** si el error se produjo en un puerto de envío.|URI de la ubicación de recepción donde se produjo el error.|  
|SendPortName|System.String|**Promocionada** si el error se produjo durante el procesamiento de salida (en un puerto de envío).<br /><br /> **No promocionada** si el error se produjo en un puerto de recepción.|Nombre del puerto de envío donde se produjo el error.|  
|OutboundTransportLocation|System.String|**Promocionada** si el error se produjo durante el procesamiento de salida (en un puerto de envío).<br /><br /> **No promocionada** si el error se produjo en un puerto de recepción.|URI de la ubicación de envío donde se produjo el error.|  
|ErrorType|System.String|Sí|Indica el tipo de mensaje que contiene el error. Esta propiedad siempre contiene el valor **FailedMessage**, que significa que el error contiene el mensaje con errores original.|  
|RoutingFailureReportID|System.String|Sí|Esta propiedad proporciona el identificador del informe de errores de enrutamiento que genera BizTalk Server cuando hay un error de enrutamiento. Un informe de error de enrutamiento es un mensaje especial que BizTalk Server genera y suspende. Este mensaje no tiene cuerpo pero incluye el contexto del mensaje con errores. Con este identificador, una orquestación de control de errores o un puerto de envío pueden consultar la base de datos de cuadro de mensajes y procesar el informe de error de enrutamiento. Por ejemplo, puede que una orquestación decida finalizar el informe de error de enrutamiento después de recibir el mensaje con errores.|  
  
## <a name="handling-error-messages"></a>Controlar mensajes de error  
 El control de errores se especifica mediante una orquestación o una suscripción de puerto de envío cuyo filtro coincide con las propiedades que se han promocionado al contexto del mensaje de error.  
  
## <a name="security-implications"></a>Implicaciones de seguridad  
 La identidad asociada al mensaje original, ya se determine su identidad inicial o su identidad final mediante la fase Resolver entidad de la canalización de recepción, se asigna al mensaje de error.  
  
 Los mecanismos de seguridad que restringen la entrega de mensajes a los puertos y orquestaciones de suscripción autorizados también se aplican a los mensajes de error.  
  
 Un puerto de envío que se suscribe a un mensaje de error pero que no está configurado con un certificado de cifrado apropiado, no recibirá los mensajes de error originados por los errores de mensajería en la fase o antes de la fase de descifrado de la canalización de recepción por la que el mensaje original tuvo acceso a BizTalk Server. En su lugar, los mensajes con errores se colocan en la cola de suspensión.  
  
## <a name="adapter-messaging-failure"></a>Error de mensajería del adaptador  
 Si un adaptador suspende un mensaje, se publica un mensaje de error. No se genera ningún mensaje de error si no se suspende el mensaje.  
  
## <a name="transactional-receive-pipelines"></a>Canalizaciones de recepción transaccionales  
 Si una canalización de recepción transaccional produce una excepción (especifica que se debe anular la transacción), la transacción se anula y se publica un mensaje de error.  
  
 Si una canalización de recepción transaccional suspende explícitamente un mensaje (especifica que MessageDestination = SuspendQueue), la transacción actual puede continuar (y se puede confirmar a no ser que las fases posteriores especifiquen que se anule) y se publica el mensaje de error resultante.  
  
## <a name="solicit-response-send-ports"></a>Puertos de envío de petición-respuesta  
 Cuando se envía un mensaje de solicitud desde una orquestación y hay errores en la transmisión o su respuesta genera errores de procesamiento entrante, la orquestación recibe una excepción independientemente de que el mensaje con errores se haya enrutado.  
  
 En el caso de que un puerto de envío de petición-respuesta esté conectado a un puerto de recepción de solicitud-respuesta, el puerto de recepción recibe un mensaje de respuesta (si la transmisión se realiza correctamente) o un mensaje de confirmación negativa (NACK), independientemente de que se haya enrutado el mensaje con errores.  
  
## <a name="one-way-send-ports"></a>Puertos de envío unidireccionales  
 Cuando se envía un mensaje desde una orquestación a través de un puerto de envío configurado para la notificación de entrega, la orquestación recibe una notificación de entrega independientemente de que se haya enrutado el mensaje de error. Es decir, el puerto de envío genera una notificación de entrega para la orquestación aunque el puerto encuentre un error de mensajería durante el procesamiento. La notificación confirma la entrega al puerto, pero no informa del procesamiento correcto a través del puerto.  
  
## <a name="resuming-suspended-messages"></a>Reanudar mensajes suspendidos  
 La mayoría de mensajes que generan errores durante el procesamiento de entrada (es decir, el procesamiento desde, en y hasta el adaptador de recepción pero sin incluir la publicación en el cuadro de mensajes) y cuyos errores no se controlan, se suspenden como reanudables. La excepción es que los mensajes de solicitud desde los puertos de recepción bidireccionales se suspenden como no reanudables.  
  
 Normalmente, se suspenden los mensajes en su forma original (como eran antes del procesamiento de canalización), pero hay dos excepciones:  
  
-   **Mensajes suspendidos por componentes de canalización.** BizTalk Server suspende este tipo de mensajes en el mismo formato que se proporcionaron al componente de canalización con errores. Cuando se reanuda el mensaje, se realiza el procesamiento de canalización desde el principio de la misma canalización. Esto implica que un componente de canalización en una fase de canalización anterior a la fase donde se produjo el error original debe estar preparado para controlar el "mismo" mensaje en un formato diferente del original en el que se procesó dicho mensaje.  
  
-   **Desensamblado posteriormente errores de enrutamiento de intercambio de mensajes de recuperables.** BizTalk Server suspende este tipo de mensajes en el mismo formato en el que se publicaron. Es el formato que tenía el mensaje **después** de la ejecución de la canalización. Cuando se reanuda el mensaje, se omite el procesamiento de canalización y se publica directamente en la base de datos de cuadro de mensajes.  
  
## <a name="scenarios-leading-to-suspended-non-resumable-messages"></a>Escenarios que dan lugar a mensajes suspendidos (no reanudables)  
 Si bien lo más habitual es que los mensajes se suspendan como reanudables, hay algunos escenarios que dan lugar a mensajes no reanudables:  
  
-   En un puerto de envío de entrega ordenada con la opción de continuar en caso de error de canalización, asignación o transmisión habilitada.  
  
-   En un puerto de recepción de entrega ordenada, si el adaptador se ha configurado para suspender mensajes como no reanudables en caso de error. Por ejemplo, si el valor de configuración del adaptador de MSMQ "En caso de error" se ha definido como "Suspender (no reanudable)", o si el adaptador de MQSeries tiene la opción "Suspender como no reanudable" habilitada, los mensajes con errores se suspenderán como no reanudables.  
  
-   En un puerto de recepción bidireccional, si se produce un error del mensaje de respuesta en la transmisión, asignación o canalización.  
  
-   En un puerto de recepción bidireccional, si se produce un error del mensaje de recepción en la transmisión, asignación o canalización. El comportamiento del adaptador individual puede ser diferente. Por ejemplo, el adaptador de HTTP no suspende mensajes de forma predeterminada, aunque puede configurarse para que lo haga.  
  
## <a name="see-also"></a>Vea también  
 [Control de errores](../core/error-handling.md)   
 [Usar confirmaciones](../core/using-acknowledgments.md)   
 [Entrega ordenada de mensajes](../core/ordered-delivery-of-messages.md)