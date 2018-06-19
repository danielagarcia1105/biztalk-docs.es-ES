---
title: Patrones de intercambio para adaptadores de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ad65fb5-640d-4bd2-aabe-946210f58a22
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 997aaa9a92f90f30bdaaeb59cc9cecb0c454496f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248356"
---
# <a name="exchange-patterns-for-send-adapters"></a>Patrones de intercambio para adaptadores de envío
Los adaptadores de envío son mensajes entregados desde el motor de mensajería de BizTalk cuya transmisión debe efectuarse a través de la red. Estos mensajes pueden enviarse mediante un patrón de intercambio de mensajes bidireccional o unidireccional. Un adaptador que controla este patrón de intercambio de mensajes bidireccional se conoce como adaptador de petición-respuesta.  
  
## <a name="blocking-vs-non-blocking-transmissions"></a>Bloqueo de vs. Transmisiones de no bloqueo  
 El motor de mensajería entrega mensajes al adaptador de envío utilizando la **IBTTransmitter.TransmitMessage** método o la **IBTTransmitterBatch.TransmitMessage** método, dependiendo de si el adaptador es compatible con lotes. Ambas versiones del método tienen un valor de devolución booleano que indica el modo en el que el adaptador efectúa la transmisión del mensaje. Si el adaptador devuelve `true`, completamente ha enviado el mensaje antes de devolver. En este caso, el motor de mensajería elimina el mensaje de la base de datos de cuadro de mensajes en nombre del adaptador. Si el adaptador devuelve `false`, se inicia la transmisión del mensaje y devuelve antes de completar la transmisión. En este caso, el adaptador no es solo responsable de la eliminación del mensaje de la cola de aplicación correspondiente, sino también del control de errores de transmisión que requiere volver a intentar la transmisión o suspensión del mensaje.  
  
 El adaptador devuelve `false` es una llamada de no bloqueo, lo que significa que la **TransmitMessage** código de implementación no bloquea el subproceso que realiza la llamada del motor de mensajería. El adaptador tan solo agrega el mensaje a una cola en memoria, preparado para su transmisión y, seguidamente, efectúa su devolución. El adaptador debería tener su propio grupo de subprocesos para efectuar la entrega de la cola en memoria, la transmisión del mensaje y, a continuación, la notificación al motor de la salida de la transmisión.  
  
 Por lo general, los subprocesos del motor de mensajería están más enlazados a la CPU que los subprocesos que se utilizan para enviar datos a través de la red. La combinación de estos dos tipos de subprocesos tiene un impacto negativo en el rendimiento. Los envíos de no bloqueo permiten separar estos dos tipos de subprocesos y mejorar considerablemente el rendimiento con respecto a las llamadas de bloqueo.  
  
 En el siguiente diagrama, se muestra el grupo de subprocesos del adaptador que, posiblemente, las operaciones E/S tiendan a enlazar. El enlace del grupo de subprocesos del motor de mensajería de BizTalk Server está más relacionado con el procesamiento de la CPU. El sistema funciona de forma más eficaz al conservar dos grupos de subprocesos distintos sin mezclar el mismo tipo de subproceso.  
  
 ![](../core/media/io-cpu-bound-threadpools.gif "Io_cpu_bound_threadpools")  
  
 **Consejo de rendimiento:** para un rendimiento óptimo, enviar adaptadores deben ser no sea de bloqueo y con lotes. Cuando se cambia el carácter de bloqueo y la incompatibilidad con lotes del adaptador de archivo de BizTalk al carácter de no bloqueo y de compatibilidad con lotes, se obtiene una mejora del rendimiento en tres aspectos.  
  
 **Sugerencia de solución de problemas:** transmite de bloqueo puede provocar una degradación del rendimiento de una instancia de host completo. Si el adaptador realiza un bloqueo excesivo en **TransmitMessage** impedirá subprocesos del motor de entrega de mensajes a otros adaptadores.  
  
## <a name="non-batched-sends"></a>Envíos no compatibles con lotes  
 Los adaptadores que no son compatibles con lotes deberían implementar **IBTTransmitter** tal como se detalla en [Interfaces para un adaptador de envío asincrónico](../core/interfaces-for-an-asynchronous-send-adapter.md). Para las llamadas de cada mensaje que el adaptador necesita transmitir el motor de mensajería de **IBTTransmitter.TransmitMessage**. En el diagrama de interacción de objetos que se muestra a continuación, se ilustra el enfoque habitual para la transmisión de mensajes, que consta de los pasos siguientes:  
  
1.  El motor entrega el mensaje al adaptador.  
  
2.  El adaptador coloca el mensaje en una cola en memoria, preparado para su transmisión.  
  
3.  Un subproceso del grupo de subprocesos del adaptador quita el mensaje de la cola, lee la configuración que le corresponde a éste y lo transmite a través de la red.  
  
4.  El adaptador obtiene un nuevo lote del motor.  
  
5.  El adaptador llama **DeleteMessage** en el lote, pasa el mensaje recién transmitido.  
  
6.  El adaptador llama **realiza** en el lote.  
  
7.  El motor procesa el lote y elimina el mensaje de la cola de la aplicación.  
  
8.  El motor llama al adaptador para notificarle del resultado de la **DeleteMessage** operación.  
  
 ![](../core/media/deleting-from-message-queue.gif "Deleting_from_message_queue")  
  
 El diagrama de interacción de objetos anterior muestra la eliminación que lleva a cabo el adaptador de un solo mensaje de la cola de la aplicación. Idealmente, el adaptador procesa por lotes operaciones de mensaje, lo que se opone al funcionamiento con un solo mensaje cada vez.  
  
## <a name="batched-sends"></a>Envíos compatibles con lotes  
 Los adaptadores que son compatibles con lotes deberían implementar **IBTBatchTransmitter** y **IBTTransmitterBatch** tal como se detalla en [Interfaces para los adaptadores de envío](../core/interfaces-for-send-adapters.md). Cuando el motor tiene mensajes para el adaptador transmitir, el motor Obtiene un nuevo lote del adaptador mediante una llamada a **IBTBatchTransmitter.GetBatch**. El adaptador devuelve un nuevo objeto de lote que implementa **IBTTransmitterBatch**. El motor, a continuación, inicia el lote mediante una llamada a **IBTTransmitterBatch.BeginBatch**. La API dispone de un parámetro de salida que permite que el adaptador especifique el número máximo de mensajes que se aceptará en el lote. De forma opcional, el adaptador puede devolver una transacción de DTC. A continuación, llama el motor de **IBTTransmitterBatch.TransmitMessage** una vez para cada mensaje saliente que se va a agregarse al lote. El número de veces que se efectúa esta llamada es superior a 0 pero inferior o igual al tamaño máximo del lote, tal y como lo indica el adaptador. Cuando todos los mensajes se han agregado al lote, el adaptador llama **IBTTransmitterBatch.Done**. En este punto, por lo general, el adaptador coloca todos los mensajes del lote en la cola en memoria correspondiente. El adaptador transmite los mensajes a partir de uno o varios subprocesos de su propio grupo de subprocesos, como en el caso de adaptadores no compatibles con lotes. Después, el adaptador notifica al motor del resultado de la transmisión.  
  
 En el diagrama de interacción de objetos que se muestra a continuación, se ilustra la transmisión que efectúa un adaptador de envío por lotes de dos mensajes.  
  
 ![](../core/media/batchedsends.gif "BatchedSends")  
  
## <a name="handling-transmission-failures"></a>Controlar errores de transmisión  
 En la ilustración siguiente, se ilustra la semántica recomendada para los errores de transmisión. Se trata únicamente de recomendaciones que no impone el motor de mensajería. Se puede desarrollar un adaptador que difiera de estas directrices si hay razones válidas para ello, aunque se debe tener especial cuidado en ese caso. Por ejemplo, en términos generales, un adaptador siempre debe mover mensajes al transporte de reserva una vez agotados todos los reintentos.  
  
 Lo más habitual es que un transporte necesite efectuar un número de reintentos superior al que establece la configuración. Aunque esta situación es ligeramente distinta, se considera aceptable porque se aumenta la capacidad de recuperación de la capa de transporte. En general, las API que expone el motor de mensajería están diseñadas para ofrecer al adaptador el control máximo allí donde sea posible. Este control conlleva un nivel más alto de responsabilidad.  
  
 ![](../core/media/handlingerrors.gif "HandlingErrors")  
  
 El adaptador determina el número de reintentos disponibles en un mensaje mediante la comprobación de la propiedad de contexto de sistema **RetryCount**. El adaptador llama el **reenviar** API una vez para cada reintento intento y pasa el mensaje que se va a reenviar. Además del mensaje, pasa la marca de tiempo que indica el momento en el que debe volver a entregarse el mensaje al adaptador. Este valor debe ser la hora actual más el valor de **RetryInterval**. **RetryInterval** es una propiedad de contexto de sistema cuyas unidades son minutos. Tanto el **RetryCount** y **RetryInterval** en el contexto del mensaje son los valores que se configuran en el puerto de envío. Consideremos una implementación escalada horizontalmente con instancias del mismo host de BizTalk implementadas en varios equipos. Si el mensaje se entrega una vez agotado el intervalo de reintentos, podrá entregarse a cualquiera de las instancias de host de cualquiera de los equipos en los que aquéllas están configuradas para ejecutarse. Por ello, el adaptador no debería conservar ningún estado asociado con un mensaje que se deba utilizar en el reintento, ya que no hay garantía de que la misma instancia del adaptador se haga responsable, posteriormente, de la transmisión.  
  
 El adaptador solo debe intentar mover el mensaje al transporte de reserva después de que el recuento de reintentos sea inferior o igual a cero. Si no hay ningún transporte de reserva configurado para el puerto, el intento de mover el mensaje a dicho transporte no se llevará a cabo correctamente. En este caso, el mensaje debería suspenderse.  
  
 El código siguiente muestra cómo determinar el intervalo y el recuento de reintentos a partir del contexto del mensaje, así como el reenvío o el movimiento siguiente al transporte de reserva.  
  
```  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  
 …  
// RetryCount and RetyInterval are system context properties...  
private static readonly PropertyBase RetryCountProperty =   
 new BTS.RetryCount();  
private static readonly PropertyBase RetryIntervalProperty =   
 new BTS.RetryInterval();  
  
public void HandleRetry(IBaseMessage msg, IBTTransportBatch batch)  
{  
int retryCount = 0;  
int retryInterval = 0;  
  
// Get the RetryCount and RetryInterval off the msg ctx...  
 GetMessageRetryState(msg, out retryCount, out retryInterval);  
  
// If we have retries available resubmit, else move to   
 // backup transport...  
 if ( retryCount > 0 )  
batch.Resubmit(  
 msg, DateTime.Now.AddMinutes(retryInterval));  
else  
batch.MoveToNextTransport(msg);  
}  
  
public void GetMessageRetryState(  
 IBaseMessage msg,   
 out int retryCount,   
 out int retryInterval )  
{  
retryCount = 0;  
retryInterval = 0;  
  
object obj =  msg.Context.Read(  
RetryCountProperty.Name.Name,    
RetryCountProperty.Name.Namespace);   
  
if ( null != obj )  
retryCount = (int)obj;  
  
obj =  msg.Context.Read(  
RetryIntervalProperty.Name.Name,    
RetryIntervalProperty.Name.Namespace);   
  
if ( null != obj )  
retryInterval = (int)obj;  
}  
```  
  
## <a name="throwing-an-exception-from-transmitmessage"></a>Lanzar una excepción desde TransmitMessage  
 Si el adaptador lanza una excepción en cualquiera de las API **IBTTransmitter.TransmitMessage**, **IBTTransmitterBatch.TransmitMessage**, **IBTTransmitterBatch.Done**, el motor tratará la transmisión de los mensajes implicados como errores de transmisión y toma las medidas oportunas para el mensaje, como se detalla en [cómo controlar errores de los adaptadores](../core/how-to-handle-adapter-failures.md).  
  
 En el caso de los adaptadores de envío compatibles con lotes, el lanzamiento de una excepción en la API TransmitMessage tiene como resultado la eliminación de la totalidad del lote y la puesta en práctica de las acciones de errores de transmisión predeterminadas para todos los mensajes de ese lote.  
  
## <a name="solicit-response"></a>Petición-Respuesta  
 Los adaptadores de envío bidireccionales admiten, por lo general, tanto transmisiones bidireccionales como unidireccionales. El adaptador de envío determina si el mensaje debe transmitirse como un envío unidireccional o bidireccional inspeccionando la **IsSolicitResponse** propiedad de contexto de sistema en el contexto del mensaje.  
  
 En el siguiente fragmento de código se muestra este caso:  
  
```  
private bool portIsTwoWay = false;  
private static readonly PropertyBase IsSolicitResponseProperty= new BTS.IsSolicitResponse();  
  
...  
  
 // Port is one way or two way...  
 object obj =  this.message.Context.Read(  
 IsSolicitResponseProperty.Name.Name,    
 IsSolicitResponseProperty.Name.Namespace);   
  
if ( null != obj )  
 this.portIsTwoWay = (bool)obj;  
```  
  
 Durante una transmisión de petición-respuesta, el adaptador transmite el mensaje de petición. Una vez completado lo anterior, envía la respuesta asociada y le ordena al motor de mensajería que elimine el mensaje de petición original de la base de datos de cuadro de mensajes. La acción de eliminar el mensaje de la cola de la aplicación debe efectuarse en el mismo lote de proxy de transporte que el envío del mensaje de respuesta. Con ello, se asegura el carácter atómico de la eliminación y el envío de la respuesta. Para obtener una atomicidad completa, el adaptador debe utilizar una transacción de DTC en cuyo contexto se encuentren el mensaje de petición a un recurso compatible con transacciones, el envío del mensaje de respuesta y la eliminación del mensaje de petición. Como siempre, se recomienda que el mensaje de petición se transmita mediante un envío de no bloqueo.  
  
 En el siguiente fragmento de código se muestran los aspectos principales de un envío bidireccional. Cuando el motor llama **IBTTransmitter.TransmitMessage** el adaptador coloca el mensaje que se transmitan a una cola en memoria. El adaptador devuelve `false` para indicar que está realizando un envío de no bloqueo. Grupo de subprocesos del adaptador (**WorkerThreadThunk**) de servicios de la cola en memoria y quita de la cola un mensaje para entregarlo a un método auxiliar. Este método es el responsable del envío del mensaje de petición y de la recepción del mensaje de respuesta. (La implementación de este método auxiliar excede el alcance de este tema.) El mensaje de respuesta se envía al motor y el mensaje de petición se elimina de la cola de la aplicación.  
  
```  
using System.Collections;  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  
  
     static private Queue _transmitQueue = new Queue();  
  static private IBTTransportProxy _transportProxy = null;   
// IBTTransmitter...  
 public bool TransmitMessage(IBaseMessage msg)  
{  
// Add message to the transmit queue...  
lock(_transmitQueue.SyncRoot)  
 {  
_transmitQueue.Enqueue(msg);  
 }  
  
 return false;  
}  
  
 // Threadpool worker thread...   
private void WorkerThreadThunk()  
{  
try  
{  
 IBaseMessage solicitMsg = null;  
  
 lock(_transmitQueue.SyncRoot)  
 {  
 solicitMsg =   
 (IBaseMessage)_transmitQueue.Dequeue();  
}  
  
 IBaseMessage responseMsg = SendSolicitResponse(   
 solicitMsg );  
Callback cb = new Callback();  
  
IBTTransportBatch batch = _transportProxy.GetBatch(  
 cb, null);  
batch.SubmitResponseMessage( solicitMsg, responseMsg );  
batch.DeleteMessage( solicitMsg );  
batch.Done(null);  
}  
catch(Exception)  
{  
// Handle failure....  
}  
}  
  
static private IBaseMessage SendSolicitResponse(  
 IBaseMessage solicitMsg )  
{  
// Helper method to send solicit message and receive   
 // response message...  
IBaseMessage responseMsg = null;  
return responseMsg;  
}  
```  
  
## <a name="dynamic-sends"></a>Envíos dinámicos  
 Los puertos de envío dinámico no tienen una configuración de adaptador asociada a ellos. En lugar de ello, utilizan la configuración del controlador para cualquier propiedad predeterminada que necesite el adaptador para transmitir mensajes en un puerto dinámico. Por ejemplo, es posible que un adaptador de HTTP necesite utilizar un proxy y tenga que proporcionar credenciales. El nombre de usuario, la contraseña y el puerto pueden especificarse en la configuración del controlador que el adaptador guarda en la caché en tiempo de ejecución.  
  
 Para el motor determine el transporte que se enviará a través, un mensaje dinámico el **OutboundTransportLocation** tiene como prefijo el alias del adaptador. Un adaptador puede registrar uno o varios alias con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] durante la instalación. El motor analiza la **OutboundTransportLocation** en tiempo de ejecución para buscar una coincidencia. El adaptador es responsable de control de la **OutboundTransportLocation** con o sin el alias antepuesto a él. En la tabla siguiente se muestran algunos ejemplos de alias registrados para adaptadores de BizTalk predeterminados.  
  
|Alias de adaptador|Adaptador|Ejemplo de OutboundTransportLocation|  
|-------------------|-------------|---------------------------------------|  
|HTTP://|HTTP|http://www. MyCompany.com/bar|  
|HTTPS://|HTTP|https://www. MyCompany.com/bar|  
|mailto:|SMTP|mailto:A.User@MyCompany.com|  
|FILE://|FILE|FILE://C:\ MyCompany \\%MessageID%.xml|