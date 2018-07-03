---
title: Control de transacciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d360742-e969-4651-b364-9edc6a93b8d4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c82bb8077b1a89a979a658e4bd7cd9a61220f48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980453"
---
# <a name="handling-transactions"></a>Control de transacciones
## <a name="transacted-receivers"></a>Receptores con transacciones  
 La diferencia principal entre receptores con o sin transacciones receptores es que los receptores con transacciones creación y usar una transacción MSDTC explícita para garantizar la atomicidad entre su origen de datos y el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensajes. En general, todos los demás aspectos del adaptador son iguales.  
  
 Cabe destacar que un adaptador de recepción de solicitud-respuesta solo usa una transacción para enviar el mensaje de solicitud original al motor de mensajería. Se necesita otra transacción para transmitir la respuesta enviada desde el motor de mensajería al adaptador. Esto se debe a que el ámbito de la primera transacción está comprendido entre el adaptador y la base de datos de cuadro de mensajes. El mensaje de solicitud posterior no se envía al adaptador desde el motor de mensajería hasta que se confirma la transacción correspondiente al mensaje de solicitud original.  
  
 En el diagrama de interacción de objetos que se muestra a continuación, se ilustra la interacción entre el adaptador y el motor de mensajería durante un envío transaccional de mensajes entrantes. En este ejemplo, tiene lugar la siguiente secuencia de interacciones:  
  
1. El adaptador obtiene un nuevo lote del motor.  
  
2. El adaptador crea una nueva transacción MSDTC.  
  
3. El adaptador realiza una lectura destructiva desde su origen de datos que se ha dado de alta en la transacción.  
  
4. El adaptador envía el mensaje.  
  
5. El adaptador llama a **realiza** en el lote, pasa su transacción MSDTC y su **BatchComplete** puntero de devolución de llamada. El motor devuelve una **IBTDTCCommitConfirm** interfaz.  
  
6. El motor procesa el lote, la llamada al adaptador en su **BatchComplete** implementación y transmite el estado de su mensaje de procesamiento para el adaptador.  
  
7. Si el lote se realizó correctamente el adaptador confirma la transacción y llama a la **IBTDTCCommitConfirm.DTCCommitConfirm** API con un `true` valor que significa confirmar.  
  
   ![](../core/media/transactedreceiver.gif "TransactedReceiver")  
  
## <a name="transacted-transmitters"></a>Transmisores con transacciones  
 Los adaptadores con transacciones son, en su mayoría, muy parecidos a los adaptadores sin transacciones. La diferencia principal reside en que el adaptador con transacción envía los datos del mensaje a un recurso que ha dado de alta en una transacción MSDTC.  
  
 **Sugerencia para la implementación:** para envíos de transacción, el adaptador debe usar la misma transacción MSDTC para escribir los datos en el destino y para su eliminación a través de la **IBTTransportBatch.DeleteMessage** llamada al método. solo requieren transacciones estas dos operaciones. Las demás operaciones, tales como **IBTTransportBatch.Resubmit**, **IBTTransportBatch.MoveToNextTransport**, y **IBTTransportBatch.MoveToSuspendQ** no es necesario de transacción. Esto se debe a que el motor usa de manera implícita una transacción, y estos tipos de operaciones no necesitan ser atómicas con respecto a su destino.  
  
 El diagrama siguiente de interacción de objetos ilustra las interacciones entre el adaptador y el motor. La secuencia de eventos es la siguiente:  
  
1. El motor obtiene un nuevo lote del adaptador.  
  
2. El motor agrega dos mensajes al nuevo lote.  
  
3. El motor llama a **realiza** en el lote, provocando el adaptador publicar el lote a su cola de transmisión interna que presta servicio su grupo de subprocesos.  
  
4. El adaptador crea una nueva transacción MSDTC.  
  
5. El adaptador transmite los mensajes dando de alta el destino en la transacción MSDTC. Por ejemplo, esto podría hacerlo escribiendo un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] base de datos.  
  
6. Después de la transmisión, el adaptador obtiene un nuevo lote del motor.  
  
7. El adaptador llama a **DeleteMessage** para los mensajes que se ha transmitido correctamente.  
  
8. El adaptador llama a **realiza** en el lote y pasa su transacción DTC. El motor devuelve una **IBTDTCCommitConfirm** interfaz.  
  
9. El motor procesa el lote y elimina los mensajes de la cola de la aplicación.  
  
10. El motor llama del adaptador **IBTBatchCallback** interfaz con información sobre el éxito de las operaciones de eliminación.  
  
11. Si el lote se ha procesado correctamente, el adaptador confirma las transacciones.  
  
12. El adaptador llama a **IBTDTCCommitConfirm.DTCCommitConfirm** para informar al motor que la transacción se ha confirmado correctamente.  
  
    ![](../core/media/transactedtransmitter.gif "Transactedtransmitter")  
  
### <a name="transacted-solicit-response-adapters"></a>Adaptadores con transacciones de petición-respuesta  
 Al contrario que las recepciones bidireccionales, los envíos bidireccionales se pueden realizar mediante la misma transacción DTC. Adaptadores con transacciones petición-respuesta deben usar el mismo **IBTTransportBatch** para el **SubmitResponseMessage** y **DeleteMessage** operaciones. Este lote debe usar la misma transacción MSDTC usada para enviar y recibir el par de mensajes de petición-respuesta. De este modo se garantiza la atomicidad para el intercambio de mensajes de petición-respuesta.  
  
## <a name="service-components-and-byot"></a>Componentes de servicios y BYOT  
 Las API del motor de mensajería requieren que se proporcione una transacción MSDTC. No obstante, los componentes .NET están diseñados para usarse como componentes con servicios y no permiten la confirmación ni anulación de transacciones mediante programación. En lugar de ello, la transacción se confirma automáticamente en el tiempo de ejecución de COM+ en esa plataforma.  
  
 Para estos escenarios, el adaptador debe usar la aportación de una transacción propia (BYOT, Bring Your Own Transaction). Esto permite al adaptador crear una transacción MSDTC, crear una instancia del componente .NET que usa la transacción y permitir que dicho componente herede la transacción creada en lugar de crear la suya propia. .NET Framework proporciona **System.EnterpriseServices.BYOT** para este propósito. El BaseAdapter del SDK proporciona una clase auxiliar, **BYOTTransaction**, para este propósito.  
  
## <a name="avoiding-race-conditions"></a>Evitar condiciones de anticipación  
 Al escribir un adaptador que crea un objeto de transacción y lo entrega a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se acepta la responsabilidad para escribir código que realiza lo siguiente:  
  
- Resuelve los errores de los mensajes asociados al lote.  
  
- Decide el resultado final de la transacción asociada a la operación por lotes.  
  
  El adaptador debe informar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] datos de seguimiento sobre el resultado final de la transacción para mantener su texto interno. El adaptador informa a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del resultado mediante una llamada a **DTCConfirmCommit**. Si el adaptador no lo hace, se produce una pérdida de memoria considerable.  
  
  Las dos tareas indicadas anteriormente (resolución de errores y decisión del resultado final) parecen bastante sencillas, pero en realidad se basan en información procedente de varios subprocesos:  
  
- El adaptador procesa los errores basándose en información pasada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a la **BatchComplete** devolución de llamada en el adaptador. Esta devolución de llamada se produce en el subproceso del adaptador.  
  
- **DTCConfirmCommit** es un método en el **IBTDTCCommitConfirm** objeto. Una instancia de la **IBTDTCCommitConfirm** objeto devuelto por el lote **ibttransportbatch:: Done** llamar. Esta instancia está en el mismo subproceso que la **ibttransportbatch:: Done** llamar, que es diferente del subproceso del adaptador.  
  
- Para todas las llamadas que el adaptador efectúa a **ibttransportbatch:: Done** hay una devolución de llamada correspondiente, **BatchComplete**, que se lo llama el motor de mensajería en un subproceso independiente para informar del resultado de el envío del lote. En **BatchComplete** el adaptador debe confirmar o revertir la transacción en función de si el lote superado o no superado. En cualquier caso, el adaptador debe llamar a **DTCConfirmCommit** para informar del estado de la transacción al motor de mensajería.  
  
  Una posible condición de carrera se produce porque la implementación del adaptador de **BatchComplete** puede asumir que el **IBTDTCCommitConfirm** objeto devuelto por **ibttransportbatch:: Done** siempre está disponible cuando **BatchComplete** ejecuta. Sin embargo, **BatchComplete** puede llamarse en un subproceso independiente del motor de mensajería, incluso antes **ibttransportbatch:: Done** devuelve. Es posible que cuando el adaptador intente obtener acceso a la **IBTDTCCommitConfirm** objeto como parte de la **BatchComplete** implementación, hay una infracción de acceso.  
  
  En el siguiente ejemplo, se soluciona el problema mediante un evento. En este caso, se tiene acceso al puntero de la interfaz mediante una propiedad que utiliza el evento. El método get siempre espera a que set finalice.  
  
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
  
 Ahora asigne el valor devuelto de **ibttransportbatch:: Done** a esta propiedad y su uso en el **BatchComplete** llamar.  
  
## <a name="see-also"></a>Vea también  
 [Lotes de mensajes transaccionales](../core/transactional-message-batches.md)