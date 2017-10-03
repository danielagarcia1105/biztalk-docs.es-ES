---
title: "Procesamiento de recepción de mensajes por lotes para | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32bf0b70-e9d1-4fab-9c74-160e51390700
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef14179c1af460afc516b7fa331ee30a758219c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="batching-messages-for-receive-processing"></a>Procesar mensajes por lotes para el procesamiento de recepción
## <a name="batch-callbacks"></a>Devoluciones de llamada por lotes  
 Los lotes que los adaptadores de recepción envían al motor de mensajería se procesan de forma asíncrona. En consecuencia, los adaptadores necesitan un mecanismo para asociar una devolución de llamada a algún estado de adaptador con el fin de que se les pueda notificar sobre las acciones concluidas correctamente o con errores, así como llevar a cabo cualquier acción de limpieza que sea necesaria. La semántica de devolución de llamada es flexible para que los adaptadores puedan utilizar uno de los tres enfoques siguientes o una combinación de éstos. Los enfoques son:  
  
-   Todas las devoluciones de llamada se realizan en la misma instancia de objeto que implementa **IBTBatchCallBack**.  
  
-   La cookie pasada al motor al solicitar un nuevo lote se utiliza para correlacionar la devolución de llamada con el estado de los adaptadores.  
  
-   Hay un objeto de devolución de llamada distinto para cada lote que implementa **IBTBatchCallBack**. En este caso, cada objeto mantiene su propio estado privado.  
  
 Cuando se ha procesado el lote, el adaptador se llama de nuevo en su implementación de **IBTBatchCallBack.BatchComplete**. El primer parámetro, el estado HRESULT, indica el estado general del lote. Si este valor es igual o superior a cero, el lote se ha procesado correctamente, en el sentido de que el motor tiene la propiedad de los datos y el adaptador puede eliminarlos de la red. Un estado negativo indica que el lote contiene errores: ninguna de las operaciones del lote se efectuó correctamente y el adaptador es responsable de controlar el error.  
  
 Si se producen errores en el lote, el adaptador necesita saber qué elemento de qué operación causó esos errores. Por ejemplo, suponga que el adaptador lee 20 archivos de disco y los envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante un único lote. Si el décimo archivo está dañado, el adaptador necesitaría suspender que un archivo y volver a enviar los otros 19. Esta información está disponible para el adaptador en los parámetros segundo y terceros:`opCount` (número de operaciones) de tipo corto y `operationStatus`, que es de tipo BTBatchOperationStatus [].  
  
> [!NOTE]
>  En un objeto de lote único, nunca debe enviar un mensaje más de una vez. Si se envía el mismo objeto de mensaje varias veces en el mismo lote, se producirán errores en el motor.  
  
 El número de operaciones indica cuántos tipos de operaciones que se encontraban en el lote (el tamaño de la **BTBatchOperationStatus** matriz). Cada uno de los elementos de la matriz de estados de operaciones corresponde a un tipo de operación dado. Mediante el uso de la **BTBatchOperationStatus** matriz, el adaptador puede determinar qué elemento de una determinada operación no se pudo examinando el **BTBatchOperationStatus.MessageStatus** matriz para HRESULT negativo valores de un error. En el escenario anterior, el adaptador crea un nuevo lote con el envío de 19 mensajes y la suspensión de 1 mensaje.  
  
 El fragmento de código siguiente muestra cómo un adaptador efectúa una solicitud de un nuevo lote desde el motor a través del proxy de transporte y envía un mensaje único al motor mediante el enfoque de cookies. El motor de mensajería llama el **BatchComplete** método como la devolución de llamada de lote cuando ha terminado de procesar el lote completo de enviar mensajes.  
  
```  
using Microsoft.BizTalk.TransportProxy.Interop;  
using Microsoft.BizTalk.Message.Interop;  
  
public class MyAdapter :   
                  IBTTransport,   
                  IBTTransportConfig,   
                  IBTTransportControl,  
                  IPersistPropertyBag,   
                  IBaseComponent,  
                  IBTBatchCallBack  
{  
      private IBTTransportProxy _tp;  
  
      public void BatchComplete(      
            Int32                         status,   
            Int16                         opCount,   
            BTBatchOperationStatus[]      operationStatus,   
            System.Object                 callbackCookie)  
      {  
            // Use cookie to correlate callback with work done,  
            // in this example the batch is to submit a single  
            // file the name of which will be in the  
            // callbackCookie  
            string fileName = (string)callbackCookie;  
            if ( status >= 0 )  
                  // DeleteFile from disc  
                  File.Delete(fileName);          
            else  
                  // Rename file to fileName.bad  
                  File.Move(fileName, fileName + ".bad");  
      }  
  
      private void SubmitMessage(  
            IBaseMessage                  msg,   
            string                        fileName)  
      {  
            // Note: Pass in the filename as the cookie  
            IBTTransportBatch batch =   
                  _tp.GetBatch(this, (object)fileName);  
  
            // Add msg to batch for submitting   
            batch.SubmitMessage(msg);   
  
            // Process this batch  
            batch.Done(null);  
      }  
}  
```  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK incluye ejemplos para los siguientes adaptadores: archivo, HTTP, MSMQ y el adaptador transaccional. Todos estos adaptadores se crean sobre un bloque de creación común denominado BaseAdapter. La versión 1.0.1 de BaseAdapter incluye todo el código relevante para analizar el estado de la operación y volver a crear un nuevo lote para su envío.  
  
## <a name="race-condition"></a>Condición de carrera  
 Las dos tareas de resolución de errores y decisión del resultado final de un lote enviado parecen bastante sencillas, pero en realidad se basan en información procedente de varios subprocesos:  
  
-   El adaptador procesa los errores basándose en información pasada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el adaptador **BatchComplete** método de devolución de llamada. Esta devolución de llamada se ejecuta en el subproceso del adaptador.  
  
-   **DTCCommitConfirm** es un método en el **IBTDTCCommitConfirm** objeto. Una instancia de la **IBTDTCCommitConfirm** objeto devuelto por el lote **ibttransportbatch:: Done** llamar. Esta instancia se encuentra en el mismo subproceso que el **ibttransportbatch:: Done** llamar a, que es diferente del subproceso de devolución de llamada del adaptador.  
  
 Para cada llamada que el adaptador efectúa a **Ibttransportbatch** el motor de mensajería realiza la llamada correspondiente al método de devolución de llamada **BatchComplete** en un subproceso independiente para informar del resultado de la envío del lote. En **BatchComplete** el adaptador debe confirmar o revertir la transacción en función de si el lote superado o no superado. En cualquier caso, el adaptador debe llamar **DTCCommitConfirm** para informar del estado de la transacción.  
  
 No existe una posible condición de carrera porque la implementación del adaptador de **BatchComplete** puede asumir que la **IBTDTCCommitConfirm** objeto devuelto por **Ibttransportbatch** siempre está disponible cuando **BatchComplete** se ejecuta. Sin embargo, **BatchComplete** puede llamarse en un subproceso independiente del motor de mensajería, incluso antes **ibttransportbatch:: Done** devuelve. Es posible que cuando el adaptador intente obtener acceso a la **IBTDTCCommitConfirm** objeto como parte de la **BatchComplete** implementación, hay una infracción de acceso porque ya no es de subproceso que la llamada a existe. Para evitar este problema, ponga en práctica lo que se especifica a continuación.  
  
 En el siguiente ejemplo, el problema se soluciona con el uso de un evento. En este caso, se tiene acceso al puntero de la interfaz mediante una propiedad que utiliza el evento. get siempre espera a que set finalice para comenzar.  
  
```  
protected IBTDTCCommitConfirm CommitConfirm  
{  
      set  
      {  
            this.commitConfirm = value;  
            this.commitConfirmEvent.Set();  
      }  
      get  
      {  
            this.commitConfirmEvent.WaitOne();  
            return this.commitConfirm;  
      }  
}  
protected IBTDTCCommitConfirm commitConfirm = null;  
private ManualResetEvent commitConfirmEvent = new ManualResetEvent(false);  
```  
  
## <a name="batch-status-codes"></a>Códigos de estado de lotes  
 El código de estado de lote general indica el resultado del lote. El estado de la operación ofrece el código de estado de envío de los elementos de mensajes individuales. El error de los lotes puede producirse por varias razones. Es posible que se produzca un error relacionado con la seguridad o que el mensaje se haya enviado cuando el motor se estaba cerrando. (Por lo general, cuando el motor se cierra, no se acepta ningún trabajo nuevo, aunque se permite finalizar el trabajo que esté en curso.) En la tabla siguiente se indican algunos valores HRESULT comunes devueltos en el estado del lote o de la operación. También se indica si se trata de códigos correctos o con errores. El tratamiento adecuado de estos códigos se describe más detalladamente en [cómo controlar errores de los adaptadores](../core/how-to-handle-adapter-failures.md).  
  
|Código (definido en la clase BTTransportProxy)|Código correcto o con errores|Description|  
|----------------------------------------------------|---------------------------|-----------------|  
|BTS_S_EPM_SECURITY_CHECK_FAILED|Success|El puerto se configuró para realizar una comprobación de seguridad y eliminar los mensajes con errores de autenticación. Los adaptadores no deben suspender los lotes que devuelvan este código de estado.|  
|BTS_S_EPM_MESSAGE_SUSPENDED|Success|Indica la suspensión de uno o varios mensajes, además de que el motor tiene la propiedad de los datos. Se trata de un código correcto en el que el motor de mensajería ha aceptado el envío del mensaje.|  
|E_BTS_URL_DISALLOWED|Failure|Se envió un mensaje con una etiqueta **InboundTransportLocation**.|  
  
## <a name="batch-operations"></a>Operaciones de lotes  
 La siguiente tabla describen los métodos de miembro y las operaciones de la **IBTTransportBatch** objeto que el adaptador utiliza para agregar trabajo a un lote dado.  
  
|Nombre del método|Tipo de operación|Description|  
|-----------------|--------------------|-----------------|  
|**SubmitMessage**|Enviar|Envía un mensaje al motor.|  
|**SubmitResponseMessage**|Enviar|Envía un mensaje de respuesta al motor. Se trata del mensaje de respuesta de un par petición-respuesta.|  
|**DeleteMessage**|DELETE|Elimina un mensaje transmitido correctamente por un adaptador a través de la red mediante un envío de no bloqueo. Adaptadores que utilizan envíos de bloqueo no es necesario llamar a este método porque el motor de mensajería lo eliminará en nombre del adaptador si el adaptador devuelve `true` de **TransmitMesssage**.|  
|**MoveToSuspendQ**|MoveToSuspendQ|Mueve los mensajes a la cola de suspensión.|  
|**Vuelva a intentarlo**|Resubmit|Solicita que se vuelva a intentar transmitir un mensaje en un momento posterior. Por lo general, se llama cuando se han producido errores en un intento de transmisión.|  
|**MoveToNextTransport**|MoveToNextTransport|Solicita la transmisión de un mensaje mediante su transporte de copia de seguridad. Por lo general, se llama una vez agotados todos los reintentos. Si no hay ningún transporte de copia de seguridad, éste método no se ejecutará correctamente.|  
|**SubmitRequestMessage**|SubmitRequest|Envía un mensaje de solicitud. Se trata del mensaje de solicitud de un par solicitud-respuesta.|  
|**CancelRequestForResponse**|CancelRequestForResponse|Notifica al motor que el adaptador no desea esperar el mensaje de respuesta de un par solicitud-respuesta.|  
|**Desactivar**|N/D|Borra todo el trabajo del lote.|  
|**Realiza**|N/D|Envía un lote de mensajes al motor para su procesamiento.|  
  
## <a name="batch-management"></a>Administración de lotes  
 Los lotes se implementan en código nativo en el motor de mensajería. Por ello, un adaptador escrito en código administrado debe liberar el contenedor al que se puede llamar en tiempo de ejecución (RCW) para el lote después de finalizar con dicho lote. Esto se hace en el código administrado mediante la **Marshal.ReleaseComObject** API. Es importante recordar que la llamada a esta API debe efectuarse en un bucle Mientras hasta que el recuento de referencia devuelto sea igual a cero.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]procesa los mensajes de forma sincrónica en un lote. Es posible procesar muchos lotes a la vez, lo que permite optimizar el adaptador al ajustar el tamaño del lote en el dominio de la aplicación. Por ejemplo, se pueden procesar todos los archivos de un sitio FTP (hasta que se alcance cierto límite). En el caso de SAP, es posible procesar una única secuencia en forma de varios mensajes que posteriormente se envían como un lote.  
  
 El lote que se utiliza un adaptador para pasar las operaciones a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no es necesario tener una correspondencia exacta a la lista de mensajes que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona al adaptador. En otras palabras, al cabo envíos transaccionales, es preciso dividir las operaciones de reenvío **MoveToNextTransport** y **MoveToSuspendQ** en lotes independientes. Muchos adaptadores ordenan un lote de mensajes enviados a varios extremos en listas independientes de mensajes para su procesamiento posterior.  
  
 El punto es que no hay ninguna regla (además de los asociados a la transacción) asociado con el mensaje de procesamiento por lotes en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Procesamiento por lotes es simplemente una manera específica de la implementación para el adaptador fragmente los mensajes entrantes dentro y fuera de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Un adaptador puede procesar por lotes los mensajes procedentes de varios más pequeños que los lotes [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ha proporcionado en un lote mayor para la respuesta a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Con ello se puede lograr una optimización considerable de los adaptadores transaccionales que utilizan un elevado número de mensajes muy pequeños. Esto reduce al mínimo la proporción del número total de transacciones por mensaje.  
  
 Por lo general [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] produce lotes de envío de entre 5 y 10 mensajes. Si se trata de mensajes muy pequeños, un adaptador puede procesar por lotes hasta 100 mensajes o más antes de devolver un lote transaccional de eliminaciones a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Una optimización de este tipo no es fácil de implementar; es preciso asegurarse de que los mensajes no se bloquean nunca en la memoria del adaptador como resultado de esperar interminablemente a que se alcance un determinado umbral.  
  
 La importancia del procesamiento por lotes puede verse en las cifras de rendimiento [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para los adaptadores de alto rendimiento como MQSeries. En estos adaptadores, los mensajes se reciben con al menos el doble de la frecuencia con la que se envían. De forma predeterminada, el adaptador de recepción utiliza lotes de 100 mensajes y el adaptador de envío utiliza el valor predeterminado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] por lotes que se genera.  
  
## <a name="transactional-batches"></a>Lotes transaccionales  
 Al escribir un adaptador que crea un objeto de transacción y lo entrega a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se acepta la responsabilidad de escribir código que hace lo siguiente:  
  
-   Decide el resultado final de la operación por lotes: para confirmar o finalizar la transacción. Esto puede depender de otras ramas transaccionales dentro del ámbito de esta transacción que no son [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependientes, como la escritura en una cola de Message Queuing (MSMQ) o una operación de base de datos transaccional.  
  
-   Informa a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del resultado final mediante una llamada a la **IBTDTCCommitConfirm.DTCCommitConfirm** método. Devolver `true` indica una confirmación correcta de la transacción; devolver `false` indica error y revertir la transacción.  
  
 El adaptador debe informar a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] acerca del resultado final de la transacción para mantener su interno de seguimiento de datos. El adaptador informa a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del resultado mediante una llamada a **DTCCommitConfirm**. Si el adaptador no hace esto, se produce una pérdida de memoria considerable y la transacción de Microsoft DTC puede superar el tiempo de espera y presentar errores a pesar de que las operaciones se hayan finalizado correctamente.