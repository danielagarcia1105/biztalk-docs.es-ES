---
title: Cómo controlar errores de adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdceb364-38d6-4aab-a176-bf751da1be25
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac87b905d7eb68bdb37a900840f7bd747c92ed77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971925"
---
# <a name="how-to-handle-adapter-failures"></a>Cómo controlar errores de adaptador
Por lo general, los adaptadores deberían suspender los mensajes que no pueden procesar. Un adaptador de recepción, por ejemplo, que experimente un error de envío debería suspender los mensajes, aunque esta decisión depende del propósito del adaptador. Además, hay consideraciones de seguridad que se deben tener en cuenta con respecto al control de errores. Si un adaptador, por ejemplo, suspende de forma automática todos los mensajes con errores, es posible que el adaptador esté abierto a un ataque de denegación de servicio que provoque que se llene la cola de suspensión de BizTalk Server.  Algunos adaptadores, como HTTP, pueden devolver un código de error al cliente que indique que se ha rechazado la solicitud. Para estos tipos de adaptadores resulta conveniente devolver un código de error en lugar de suspender el mensaje. Como norma general, los adaptadores de envío solo suspenden los mensajes una vez que se han agotado los reintentos tanto para los transportes primarios como los secundarios.  
  
## <a name="associate-error-processing-with-an-individual-operation-and-not-with-the-batch-that-contains-the-operation"></a>Asociar el procesamiento de errores con una operación individual y no con el lote que contiene la operación  
 El procesamiento por lotes de los mensajes de un adaptador debería ser invisible al usuario de éste. Esto significa que el error de una operación en un lote no debería afectar en ningún caso a ninguna operación. Sin embargo, los lotes son atómicos con lo que el error de un mensaje provoca un error en el lote y no se procesan las operaciones.  
  
 Escriba el código responsable del control de errores, volviendo a enviar los mensajes correctos y suspendiendo los que no lo son. Afortunadamente, BizTalk Server proporciona una estructura de errores detallada que permite al adaptador determinar la operación específica en la que se ha producido el error. Además, permite crear más lotes en los que las operaciones correctas se vuelven a enviar y las que no lo son se suspenden.  
  
 El estado final de la operación no debería verse afectado por el procesamiento por lotes del adaptador.  
  
## <a name="use-seterrorinfo-to-report-failure-to-biztalk-server"></a>Utilizar SetErrorInfo para informar de los errores a BizTalk Server  
 Si está suspendiendo un mensaje, debe proporcionar información de los errores a BizTalk Server desde el contexto del mensaje anterior. BizTalk Server proporciona capacidades con los informes de errores el **SetErrorInfo** método tanto en el **IBaseMessage** y **ITransportProxy** interfaces. Es posible informar de los errores de la siguiente forma:  
  
- Cuando se produce un error al procesar un mensaje, establezca la excepción mediante **SetErrorInfo (Exception e)** en el mensaje (**IBaseMessage**) va a suspender. Esto permite al motor conservar el error con el mensaje para un diagnóstico posterior y registrarlo en el registro de eventos para alertar al administrador.  
  
- Si se produce un error durante la inicialización o la contabilización interna (no durante el procesamiento de mensajes) debe llamar a **SetErrorInfo (Exception e)** en el **ITransportProxy** puntero que se pasó a los usuarios durante la inicialización. Si el adaptador se basa en la implementación de BaseAdapter, siempre debería tener acceso a este puntero. De lo contrario, debe asegurarse de que lo almacena en la memoria caché.  
  
  Al informar de un error mediante alguno de estos métodos, el mensaje de error se escribe en el registro de eventos. Es importante que, siempre que sea posible, se asocie el error con el mensaje relacionado.  
  
## <a name="handle-a-database-offline-condition"></a>Controlar una condición de base de datos sin conexión  
 Si alguna de las bases de datos de BizTalk Server se desconecta, el servicio de BizTalk se recicla. El motor de mensajería hace lo posible por cerrar todas las ubicaciones de recepción antes de reciclar el servicio. Si este proceso tarda más de 60 segundos, el servicio finaliza. Debido a que se trata de un motor de transacción, no se pierden datos.  
  
 Este tiempo de espera puede ajustarse en el Registro mediante la siguiente tecla:  
  
```  
DWORD   
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingDBFailoverShutdownTimeLimit  
```  
  
 En el caso de adaptadores aislados, debido a que no es un proceso propio de BizTalk Server, se deshabilitan las ubicaciones de recepción cuando una de las bases de datos de BizTalk Server se desconecta. Las ubicaciones de recepción se habilitan de nuevo una vez que la base de datos se vuelve a conectar.  
  
## <a name="write-to-the-event-log"></a>Escribir en el registro de eventos  
 El adaptador puede escribir entradas del registro de eventos mediante el uso de la **IBTTransportProxy** interfaz pasa una excepción. Los adaptadores desarrollados en código nativo deben pasar en un **IErrorInfo** interfaz, **IBTTransportProxy.SetErrorInfo (excepción** `e` **)**.  
  
 El motor de mensajería escribe en el registro de eventos en nombre del adaptador los eventos en los que se da alguno de los siguientes casos: un adaptador vuelve a intentar un mensaje después de un error en la transmisión, mueve un mensaje al transporte de reserva o suspende un mensaje. Para operaciones como las anteriores, el adaptador solo necesita establecer la excepción en el mensaje antes de llamar a la API. En el siguiente fragmento de código se muestra este caso:  
  
```  
IBaseMessage msg;  
...  
// Set exception on msg to indicate why transmission failed...  
msg.SetErrorInfo(  
 new ApplicationException(  
 "The TCP connection was closed by the destination"));  
```  
  
## <a name="handle-receive-specific-batch-errors"></a>Controlar errores de lote específicos de recepciones  
  
### <a name="handle-receive-failures"></a>Controlar errores de recepción  
 Cuando un adaptador envía una operación (o un lote de operaciones) a BizTalk Server pueden producirse errores por varias razones. A continuación se indican las dos más importantes:  
  
- Error en la canalización de recepción.  
  
- Error de enrutamiento mientras se publicaba un mensaje.  
  
  El motor de mensajería intenta suspender de forma automática el mensaje cuando se produce un error en la canalización de recepción. Es posible que la operación de suspensión no siempre se ejecute correctamente. Por ejemplo, si el motor de mensajería coincide con un error de enrutamiento mientras se publica un mensaje, no intentará siquiera suspender el mensaje.  
  
  Siempre existe la posibilidad de que se produzca un error en un mensaje. En esta situación, el adaptador debe llamar explícitamente la **MoveToSuspendQ** API y debería intentar suspender el mensaje. Cuando un adaptador intenta suspender un mensaje, una de las siguientes afirmaciones debería ser verdadera:  
  
- Se debería suspender el mismo objeto de mensaje que el adaptador enviado (recomendado).  
  
- Si el adaptador tiene que crear un mensaje nuevo, debería establecerse el contexto de mensaje del mensaje nuevo con el puntero como contexto de mensaje del mensaje que se envió en un principio. Esto se debe a que el contexto de mensaje de un mensaje contiene bastante información valiosa acerca del mensaje y del error. Esta información es necesaria para depurar el mensaje con errores.  
  
> [!NOTE]
>  Si el adaptador crea un objeto nuevo de mensaje y lo suspende, debería copiar la información del error del objeto anterior del mensaje al nuevo.  
  
 Algunos adaptadores, como el HTTP que se proporciona con BizTalk Server, no requieren que se suspenda el mensaje. Estos adaptadores pueden devolver un error a sus equipos cliente.  
  
#### <a name="causes-of-failure"></a>Causas de error  
 Las causas más sencillas de error son los errores que pueden producirse cuando se crea el lote o cuando **ibttransportbatch:: Done** se llama.  
  
-   **Error de envío.** El **enviar** puede producir un error de llamada para un número limitado de razones y todas ellas son fatales. Estas razones incluyen las siguientes:  
  
-   Los errores de memoria insuficiente que se producen en el espacio de procesos de BizTalk Server.  
  
-   El ensamblado de esquema se ha colocado desde la implementación. En este caso, el **enviar** produce un error críptico. En el adaptador de MQSeries, se captura la excepción de error genérico de BizTalk Server y se escribe un mensaje de error extendido en el registro de eventos del sistema. Este mensaje sugiere que una de las posibles causas del error es que, de alguna forma, el ensamblado de esquema se ha colocado desde la implementación.  
  
     En general, si **enviar** se produce un error, debería intentar suspender el mensaje mediante la misma transacción.  
  
-   **Error ibttransportbatch:: done.** El **ibttransportbatch:: Done** llamada puede producir errores por varios motivos. Por lo general, debería intentar suspender una operación y finalizar la transacción solo si se producen errores. Uno de los códigos de error que puede recibir el error de **ibttransportbatch:: Done** es que BizTalk Server está intentando cerrarse. En este caso, simplemente debe finalizar la transacción y dejarla porque el **Terminate** llamada probablemente se producen simultáneamente. Se producen otros escenarios cuando ha creado correctamente el lote y se ha ejecutado correctamente **ibttransportbatch:: Done**. En estos casos, los errores se devuelven en **BatchComplete** y el adaptador debe determinar qué hacer con ellos. El resto de la sección trata este caso.  
  
#### <a name="processing-batchcomplete-errors"></a>Procesamiento de errores BatchComplete  
 **BatchComplete** es una devolución de llamada proporcionada por el adaptador que se invoca mediante BizTalk Server para indicar el estado de finalización de una operación por lotes.  
  
 El parámetro más importante pasado a **BatchComplete** es el estado del lote `hResult`. Esto indica si el lote es correcto o contiene errores. Si el lote contiene errores, significa que ninguna de las operaciones que se han realizado en el lote se ha hecho de forma correcta. El adaptador pasa a través de la estructura de estado de lote y determina qué mensajes de error (Esto se conoce como *filtrado del lote*).  
  
#### <a name="nontransactional-batchcomplete-errors"></a>Errores BatchComplete no transaccionales  
 Adaptadores no transaccionales, debe elegir la respuesta si se produce un error para un **SubmitMessage**/**SubmitRequestMessage** o **SubmitResponseMessage** operación. Los adaptadores suelen suspender el mensaje mediante una llamada a **MoveToSuspendQ**.  
  
 Siempre se deberían producirse las siguientes operaciones: **DeleteMessage**, **MoveToSuspendQ**, **ResubmitMessage**. Si se producen errores en estas operaciones, significa, por lo general, que hay un error en el adaptador. En esos casos, no es necesario que escriba código para controlar un error. Sin embargo, si se produce un error en el lote porque hay errores en otra operación, esas operaciones deben volver a ejecutarse en un lote nuevo.  
  
 Si el adaptador llama a **MovetoBackupTransport** y se produce un error (porque no había transporte de copia de seguridad) y, después, el adaptador debería llamar a **MoveToSuspendQ** para suspender el mensaje.  
  
#### <a name="transactional-batchcomplete-errors"></a>Errores BatchComplete transaccionales  
 Cuando envía lotes a BizTalk Server mediante una transacción que ha creado el adaptador, debería seguir uno de los dos escenarios siguientes:  
  
-   **Usar lotes de mensajes únicos.** Enviar un lote de mensaje único a BizTalk Server. Si se producen errores en ese único mensaje, puede enviar de forma válida un segundo lote a BizTalk Server en la misma transacción pero debe mover el mensaje infractor a la cola de suspensión en lugar de reenviarlo. Una vez que se ha eliminado el mensaje con errores, el envío del segundo lote debería producirse de forma correcta. Cuando esto suceda, puede confirmar la transacción una vez que BizTalk Server confirme que el segundo lote es correcto. Si se producen errores en el segundo lote, el adaptador debe anular la transacción o encontrar otro sitio donde colocar el mensaje. En este escenario, enseguida sufrirá una importante merma en el rendimiento debido al procesamiento de reversión de transacciones.  
  
     Para mejorar el rendimiento del adaptador se pueden utilizar algunas técnicas. Por ejemplo, el adaptador de MQSeries ajusta su aproximación de forma dinámica al tiempo de ejecución. Se ejecuta con lotes de 100 mensajes. Si se produce un error, se debe finalizar el lote pero cambia a lotes de mensajes únicos durante un breve período de tiempo cuando pasa por el mensaje malintencionado. A continuación, vuelve a lotes de 100 mensajes. Si se produce el error de nuevo, se vuelve a ralentizar.  
  
-   **Utilizar suspensión preferente.** Construir un lote de mensajes múltiples en los que los mensajes erróneos se suspenden de forma preferente. El lote contiene una mezcla de **enviar** y **MoveToSuspendQ** operaciones, y es el primer y único lote en la transacción. Debería realizarse de forma correcta porque los datos no válidos se han suspendido de forma preferente y, además, se puede confirmar la transacción (después de esperar para recibir la confirmación de BizTalk Server).  
  
     Puede parecer que sea necesario adelantarse en el futuro, pero esta técnica se ha utilizado en el adaptador de MSMQ. Depende de si se tiene o no identificadores de mensajes únicos confiables. Este adaptador construye un lote de mensajes. Si no se producen errores se revierte la transacción (y, por lo tanto, el lote), pero recuerda el Id. de mensaje en una estructura temporal de datos. (Para evitar que esta estructura crezca de forma indefinida, se eliminan elementos de ella tras un retardo fijo.) Antes de que se envíe cada lote, el adaptador comprueba la lista de los Id. de mensajes no válidos. Si ve uno, sabe que se van a producir errores en él (porque ya sucedió lo mismo con anterioridad) y lo suspende de forma preferente en lugar de intentar enviarlo.  
  
     No todos los adaptadores tienen un Id. de mensaje único confiable y es menos probable que un almacén transaccional lo tenga. Debido a esto, numerosos adaptadores transaccionales están restringidos al envío de lotes de mensajes únicos.  
  
#### <a name="processing-other-errors"></a>Procesamiento de otros errores  
 En el resto de los casos (como en los errores de los mensajes de suspensión), el adaptador debe finalizar la transacción. Cualquier otro resultado produce mensajes duplicados o quita mensajes.  
  
 Siempre que el adaptador pueda, debería anular la transacción cuando se produzcan errores en un lote. Sin embargo, hay escenarios en los que el adaptador no puede anular la transacción. En dichos escenarios, se debería suspender el mensaje mediante la misma transacción.  
  
#### <a name="processing-errors-on-transactional-receive"></a>Procesamiento de errores en la recepción transaccional  
 Un patrón de procesos transaccional común es finalizar una transacción cuando se produce un error. En ese caso todo vuelve al estado anterior y no se pierden datos. Sin embargo, si utiliza datos de un suministro transaccional (por ejemplo, extrayendo filas de una en una de una tabla provisional de una base de datos o extrayendo mensajes de uno en uno de productos de cola como MQSeries o MSMQ), es posible que esto no sea suficiente. Si simplemente finaliza la transacción, vuelve atrás y recoge los mismos datos de nuevo, es posible que se produzca el mismo error y que el sistema se quede bloqueado en un bucle repetido.  
  
 El adaptador de SQL en una versión anterior de BizTalk Server se envió con este comportamiento. Sin embargo, poco después de liberar el adaptador, el comportamiento se cambia para intentar suspender un mensaje con errores y confirmar la transacción. Al mover un mensaje a la cola de suspensión en la misma transacción y, a continuación, confirmar la transacción, se evita que se pierdan datos y, además, permite que el adaptador pase datos no válidos.  
  
 Cuando la parte de un adaptador de recepción se pasa un mensaje de error en respuesta a un **enviar** mensaje de operación, el adaptador debería procesar ese error y mover el mensaje a la cola de suspensión.  
  
 En el caso de lotes transaccionales en los que el adaptador ha creado el objeto de transacción y envía mensajes en la transacción, el adaptador debería mover el mensaje de forma lógica a la cola de suspensión en la misma transacción cuando se produce el error. La transacción asegura que no se quitan datos aunque provoquen errores.  
  
### <a name="handle-messages-without-subscriptions"></a>Controlar mensajes sin suscripciones  
 BizTalk Server no acepta que se publique un mensaje en su base de datos de cuadro de mensajes si no hay suscripciones definidas que lo acepten. Las orquestaciones o los puertos de envío registran las suscripciones. Se pueden definir numerosas suscripciones, en cuyo caso el mensaje se envía a varios destinos. Si no hay suscripciones, BizTalk Server rechaza el mensaje y no intenta suspenderlo. Si el adaptador no controla este error y suspende el mensaje de forma explícita, se quita el mensaje y es posible que se pierdan sus datos. Es evidente que un adaptador transaccional puede finalizar la transacción y devolver el mensaje a su destino.  
  
### <a name="support-seek-with-your-receive-stream"></a>Búsqueda con la secuencia de recepción  
 La secuencia de lado de recepción debe admitir la **Seek** método para BizTalk Server pueda suspender el mensaje en un error de canalización. Si la secuencia de mensajes no pueden realizar búsqueda, BizTalk Server genera un error cuando intenta ejecutar **Seek**.  
  
 En muchos casos que admiten **Seek** no es fácil. Cuando se transmiten datos por secuencias desde una red, por ejemplo, puede resultar difícil volver al recurso de red y solicitar los datos de nuevo.  
  
 Varios adaptadores que se incluyen con BizTalk Server ponen en cola los datos de mensaje en un archivo de un disco al mismo tiempo que BizTalk Server lee los datos. Esto permite al adaptador utilizar **Seek** en ese archivo si encuentra un error (en el procesamiento de canalización de los datos del mensaje, por ejemplo). Internamente, el adaptador utiliza el **ReadOnlySeekableStream** clase que contiene un flujo de entrada no permite búsquedas y desborda al disco cuando se alcanza un umbral de tamaño configurable. En caso de que haya mensajes más pequeños que el tamaño del umbral, nunca se utiliza el disco.  
  
### <a name="consider-user-configurable-error-handling-options"></a>Considerar opciones configurables por el usuario para el control de errores  
 En algunos casos no existe una respuesta correcta para un error. Si esto sucede, debería considerar una opción configurable por el usuario para elegir entre comportamientos. El adaptador de MQSeries realiza esta operación.  
  
 El problema de que el adaptador suspenda mensajes cuando ve un error es que la cola de suspensión en BizTalk Server es algo parecido a un "agujero negro". Es relativamente sencillo llevar mensajes a la cola, pero algo complicado sacarlos de nuevo.  
  
 Es posible que algunos usuarios del adaptador no deseen utilizar la cola de suspensión. Por ejemplo, en el caso del adaptador de MQSeries, el usuario cuenta con una opción de configuración para realizar una de las siguientes operaciones:  
  
-   Configurar el adaptador para que finalice la transacción actual y se deshabilite cuando vea un error.  
  
-   Suspender el mensaje con errores y confirmar la transacción. El adaptador realiza esta operación incluso cuando BizTalk Server ha suspendido el mensaje correctamente. Esta acción cumple los requisitos del cliente incluso si provoca que el registro de eventos no sea del todo correcto.  
  
### <a name="implement-receive-ordering-by-using-a-single-thread-and-waiting-on-batchcomplete"></a>Implementar órdenes de recepción mediante un único subproceso y a la espera de BatchComplete  
 La interfaz de BizTalk Server está diseñada para conseguir rendimiento y la capacidad para escalar admitiendo concurrencia. Sin embargo, si desea una recepción estrictamente ordenada de mensajes (como la que se requiere en ocasiones cuando se reciben mensajes de un producto de cola de mensajes, como MQSeries o MSMQ), deberá realizar algunas operaciones adicionales en el adaptador para deshabilitar esa concurrencia. Esto se puede llevar a cabo en dos pasos:  
  
1. Debe utilizar un único subproceso para el procesamiento de todos los datos en el adaptador.  
  
2. Debe esperar a que BizTalk Server procese por completo cada lote. Este requisito es importante y se puede conseguir utilizando primitivas de sincronización de subprocesos .NET. Por ejemplo, si se usa un **AutoResetEvent**, haría:  
  
   -   Declarar el objeto de evento donde se puede tener acceso a ambos el subproceso de trabajo principal y la **BatchComplete** objeto de devolución de llamada.  
  
   -   En el subproceso de trabajo principal, envíe los mensajes al lote como de costumbre, pero, a continuación, llame a **AutoResetEvent.Reset** en el objeto de evento justo antes de llamar al lote **ibttransportbatch:: Done**.  
  
   -   Llame a **AutoResetEvent.WaitOne** en el objeto de evento desde este mismo subproceso. Esto provoca el bloqueo del subproceso de trabajo principal. En el **BatchComplete** devolución de llamada de BizTalk Server, a continuación, llamar a **AutoResetEvent.Set** en el mismo objeto de evento para desbloquear el subproceso de trabajo para que esté listo para procesar otro mensaje.  
  
   Se recomienda encarecidamente que *órdenes de recepción* como se vuelve configurable porque provoca una degradación del rendimiento significativa. Numerosos escenarios de usuarios, si no se trata de la mayoría, no requieren órdenes de mensajes. La suspensión de mensajes puede interrumpir también la orden. Lo que se deba hacer en este caso exactamente depende de la aplicación, por lo tanto lo mejor que puede hacer el adaptador es ofrecer al usuario un punto de configuración.  
  
   En escenarios ordenados, algunos clientes han declarado que preferirían detener el procesamiento, es decir, deshabilitar el adaptador en lugar de interrumpir la orden. El adaptador de MQSeries, que admite la recepción ordenada, proporciona esta opción al usuario.  
  
## <a name="handle-send-specific-batch-errors"></a>Controlar errores de lote específicos de envíos  
  
### <a name="handle-send-retry-and-batching"></a>Controlar el reintento y el procesamiento por lotes de envíos  
 A continuación se muestra un ejemplo frecuente de procesamiento por lotes de envíos:  
  
- BizTalk Server proporciona un lote de mensajes al adaptador.  
  
- Cuando el adaptador determina que ha entregado el mensaje en su destino de forma correcta, ejecuta la eliminación en BizTalk Server para indicar que está listo. (Como es habitual, varios mensajes de eliminación pueden procesarse en lotes de forma arbitraria para mejorar el rendimiento.)  
  
  Si el adaptador de envíos produce errores al procesar un mensaje, se puede realizar una de las siguientes operaciones con ese mensaje:  
  
- El adaptador debería decir a BizTalk Server que quiere que se reintente un mensaje. BizTalk Server no reintenta de forma automática el mensaje. BizTalk Server mantiene un recuento de los reintentos, que puede consultarse en el contexto del mensaje.  
  
- El adaptador puede determinar que no puede procesar un mensaje. En ese caso, el adaptador puede mover el mensaje al siguiente transporte. El adaptador realiza esto con la **MoveToNextTransport** llamar en el **Batch** objeto.  
  
- El adaptador puede mover el mensaje a la cola de suspensión.  
  
  El adaptador determina lo que le ocurrirá al mensaje. Sin embargo, se recomienda que cuente con adaptadores que se comporten de forma coherente ya que esto hace que se admita de forma más sencilla la instalación de BizTalk Server.  
  
  Se recomienda encarecidamente que los adaptadores se comporten como se describe a continuación. Los adaptadores incluidos con BizTalk Server se comportan de la siguiente forma.  
  
### <a name="recommended-behavior-for-handling-send-errors-in-a-batch"></a>Comportamiento recomendado para el control de errores de envío en un lote  
 El adaptador de envío recibe algunos mensajes y los envía a BizTalk Server.  
  
 Por cada mensaje correcto, el adaptador debería eliminar ese mensaje en BizTalk Server. Toda la comunicación que se devuelve a BizTalk Server se produce mediante lotes; las eliminaciones también se pueden procesar por lotes. No tiene que ser el mismo lote que BizTalk Server creó en el adaptador. Si hay mensajes de respuesta (como en un escenario SolicitResponse), se deberían enviar de vuelta a BizTalk Server (con SubmitResponse) junto con la eliminación asociada.  
  
- Si los mensajes no se han procesado de forma correcta en el adaptador, compruebe el número de reintentos.  
  
  -   Si no se ha superado el número de reintentos, reenvíe el mensaje a BizTalk Server, sin olvidarse de definir el tiempo de reintentos en el mensaje. El contexto del mensaje proporciona el número y el intervalo de reintentos que debería utilizar el adaptador.  
  
  -   Si se ha superado el número de reintentos, el adaptador debería intentar mover el mensaje mediante **MoveToNextTransport**. El reenvío y **MoveToNextTransport** los mensajes se pueden mezclar con las eliminaciones en el mismo lote en BizTalk Server. Esto no es necesario, pero puede ser un paso útil.  
  
- El reenvío y el **MoveToNextTransport** son formas para que el adaptador tratar errores. Pero, es posible que se produzcan errores dentro del procesamiento del error. En este caso, en el procesamiento de la respuesta del servidor BizTalk Server (en el **BatchComplete** método) el adaptador debe crear otro lote de BizTalk Server para indicar qué hacer con ese error.  
  
   Siga los pasos que se presentan a continuación cuando se procese un error que se ha producido en el procesamiento de otro error:  
  
  -   Si se produce un error en el reenvío, utilice **MoveToNextTransport**.  
  
  -   Si el **MoveToNextTransport** se produce un error, utilice **MoveToSuspendQ**.  
  
  Debe continuar con la creación de lotes en BizTalk Server hasta que reciba una acción correcta en BizTalk Server.  
  
### <a name="serialization-of-message-context-property"></a>Serialización de propiedad del contexto de mensaje  
 Todos los objetos que estén asignados a una propiedad de contexto de mensaje deben ser serializables. En caso contrario, el motor de mensajería se iniciará una excepción de tipo **E_NOINTERFACE**. Este valor devuelto representa de forma ambigua un objeto no serializable que intenta que se le asigne al contexto del mensaje.