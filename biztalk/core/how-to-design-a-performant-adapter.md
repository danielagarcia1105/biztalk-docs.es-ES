---
title: "Cómo diseñar un adaptador de rendimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5a1f338-fd7c-41c8-a181-8da8b293c4cc
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7958968809dc224a3446ac81f3f89d08f6128a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-design-a-performant-adapter"></a>Cómo diseñar un adaptador con el que optimizar el rendimiento
Para optimizar el rendimiento, todos los adaptadores deberían admitir lotes con respecto al envío de lotes de mensajes, a la transmisión de lotes y, en general, a la realización de operaciones de mensajes en lotes. Los adaptadores deberían intentar exponer atributos configurables relacionados con el rendimiento, como, por ejemplo, el tamaño de los lotes o el número de bytes de un lote, que se puedan configurar en la interfaz de usuario de tiempo de diseño del adaptador.  
  
 Como se ha mencionado anteriormente, los adaptadores de envío deberían realizar siempre envíos que no sean de bloqueo para evitar la disminución del rendimiento del host de envío. No se recomienda el bloqueo adicional de las API del motor de mensajería.  
  
 Leer y escribir en el contexto del mensaje influye en el rendimiento en tiempo de ejecución. Por lo general, los adaptadores deben evitar la lectura, escritura y promoción de una cantidad excesiva de propiedades de contexto del mensaje. La promoción de propiedades da lugar a una mejora adicional del rendimiento debido a la evaluación de la suscripción que tiene lugar en cada propiedad promocionada en tiempo de ejecución. Sin embargo, sería necesario que un adaptador promocionara una cantidad elevada de propiedades para influir de un modo perceptible en el rendimiento. En cualquier caso, se recomienda promocionar solo las propiedades que así lo requieran.  
  
## <a name="throttle-send-and-receive"></a>Limitar envío y recepción  
 Cuando la carga del motor de BizTalk supera el umbral configurado, el motor limita los adaptadores y las orquestaciones para asegurar el rendimiento óptimo. En el lado de recepción, cuando la carga de trabajo en el motor supera un umbral determinado, la llamada del adaptador para **IBTTransportBatch.Done** se bloquea hasta que la carga disminuye lo suficiente. Este hecho obliga al adaptador a enviar un trabajo nuevo al motor solo cuando éste se encuentra disponible. En el caso del envío, cuando el motor limita los adaptadores que envían mensajes salientes, el motor no entrega mensajes nuevos que deban transmitirse hasta que la carga disminuya.  
  
 Por estos motivos, no es preciso tener en cuenta la limitación en lo que respecta al adaptador, a menos que sea necesario, por ejemplo, para limitar el número de conexiones a un sistema de servidor. Para estos tipos de escenarios, ni el motor ni el marco de trabajo de adaptadores proporcionan ninguna asistencia.  
  
 Puede controlar la limitación del número de mensajes enviados desde un adaptador de envío personalizado de varias formas, dependiendo de si controla el código fuente del adaptador.  
  
### <a name="send-side-throttling-improves-performance"></a>La limitación de los envíos mejora el rendimiento  
 Si controla el código fuente del adaptador, puede determinar, a partir de métodos heurísticos, el número máximo de mensajes que desee tener en cola para enviarlos en cualquier momento. Cuando se llama el motor de mensajería la `TransmitMessage` método y pasa el adaptador de envío de un mensaje nuevo, puede elegir bloquear el subproceso o comprobar para ver si el número de mensajes en la cola es mayor que el valor máximo que ha determinado anteriormente. Si se ha superado el número máximo de mensajes, puede usar el `Resubmit` método para volver a enviar el mensaje al motor de mensajería. Tenga en cuenta que si el adaptador es sincrónico, el mensaje ya debería estar bloqueado.  
  
 Si no se controla el código fuente para el adaptador, puede cambiar el número de mensajes en cola cambiando el **Highwatermark** valor en la tabla Adm_serviceclass de la base de datos de administración de BizTalk. El valor máximo para el **Highwatermark** propiedad es 200. También puede cambiar el valor de la **límite mínimo** propiedad con un valor menor.  
  
 Recuerde que el valor de la **Highwatermark** propiedad para las cuentas de adaptadores asíncronos para el número de mensajes que el motor de mensajería ha proporcionado para el adaptador. El motor de mensajería los pasa al adaptador a través de la `TransmitMessage` método, estos mensajes pueden estar pendientes aún en la transmisión, por ejemplo, si el adaptador no ha realizado una llamada correspondiente a la `DeleteMessage`, `Resubmit`, `MoveToNextTransport` , o [Microsoft.BizTalk.TransportProxy.Interop.BatchOperationType.MoveToSuspendQ](http://msdn.microsoft.com/library/microsoft.biztalk.transportproxy.interop.batchoperationtype.aspx) métodos. Para los adaptadores sincrónicos, la **Highwatermark** propiedad solo representan el número de mensajes que el motor de mensajería ha pasado al adaptador mediante utilizando la **TransmitMessage** método porque esta llamada procesa de manera sincrónica, bloquear el subproceso que realiza la llamada del motor de mensajería.  
  
 Si escribe un adaptador de envío para un protocolo que es de naturaleza inherentemente lenta (por ejemplo, HTTP, FTP o SOAP bidireccional), tenga en cuenta lo siguiente:  
  
-   Es posible que un adaptador de este tipo reciba mensajes para su transmisión desde el motor de mensajería de BizTalk más rápido de lo que puede transmitirlos. Esta discrepancia ocasiona problemas a distintos niveles. Los mensajes en transmisión permanecen en memoria y ocupan la memoria virtual, con lo que todo el sistema se ralentiza.  
  
-   Es posible que el adaptador ocupe los recursos específicos del protocolo. Por ejemplo, puede que abra demasiadas conexiones simultáneas al servidor, lo que podría interrumpir el servidor remoto.  
  
-   El adaptador puede influir en otros adaptadores. Por ejemplo, si hay demasiados mensajes en cola de un adaptador concreto, el motor de mensajería detiene la emisión de solicitudes a otros adaptadores de envío en ese proceso.  
  
 Una solución es colocar los adaptadores lentos y rápidos en hosts de BizTalk independientes y controlar el número de mensajes mediante los valores de configuración de "marca de agua máxima" y "marca de agua mínima".  
  
### <a name="receive-side-throttling-improves-performance"></a>La limitación de recepción mejora el rendimiento  
 Existen numerosas situaciones en las que un adaptador de recepción recibe los mensajes a una velocidad superior que aquella a la que el resto del sistema procesa los mensajes. Cuando se produce una situación de este tipo, el trabajo de la base de datos de cuadro de mensajes se acumula. Si esto sucede, el rendimiento de todo el sistema disminuye de forma considerable.  
  
 Si esto sucede con el adaptador, puede usar una de las siguientes técnicas para reducir la velocidad del adaptador de recepción:  
  
-   Reduzca el tamaño del grupo de subprocesos del motor de mensajería. Puede controlar el número de subprocesos que el motor de mensajería usa para publicar mensajes en el cuadro de mensajes. Mediante la reducción del número de subprocesos, puede reducir la velocidad a la que el adaptador de recepción recibe mensajes en el cuadro de mensajes. Solo es necesario que esta configuración se lleve a cabo para el host correspondiente en el controlador de recepción del adaptador. No debe establecer esta configuración para el host correspondiente al controlador de envío del adaptador, a menos que desee ralentizar también el adaptador de envío.  
  
-   Reduzca el tamaño del lote del adaptador. Los adaptadores de recepción más rápidos publican mensajes en el cuadro de mensajes en lotes. El tamaño de estos lotes se configura normalmente en la página de propiedades de la ubicación de recepción. Mediante la disminución del tamaño del lote, puede disminuir el rendimiento global de los mensajes que entran en el sistema.  
  
-   Cambie otros valores de configuración específicos del adaptador. Una vez que complete los dos pasos anteriores, puede tratar de ajustar otros parámetros del adaptador para efectuar una disminución adicional del rendimiento. Algunos adaptadores exponen parámetros internos que se pueden usar para disminuir el rendimiento. Por ejemplo, el adaptador de MQSeries tiene un parámetro de configuración para la “entrega ordenada”. La entrega ordenada especifica que el adaptador publicará un lote de mensajes, esperará a que se complete y, a continuación, publicará el siguiente lote. Mediante la habilitación de este parámetro de configuración, quita esencialmente todo paralelismo del adaptador de recepción. Por el contrario, el ajuste de los parámetros en el modo opuesto se puede usar para aumentar la velocidad de recepción de un adaptador de recepción.  
  
 Un adaptador puede enviar tantos lotes como sea necesario al proxy de transporte. Cuando el sistema se encuentra sobrecargado, una llamada a la **realiza** método de la **IBTTransportBatch** interfaz bloqueará el mensaje hasta que se liberen los recursos necesarios para el sistema.  
  
## <a name="plan-for-asynchronous-receive-and-send"></a>Plan para la recepción y el envío asíncronos  
 Las API de mensajería de BizTalk Server ofrecen una excelente compatibilidad para la programación asíncrona. Si desea escribir un adaptador escalable, planee el uso del modelo asíncrono desde el inicio, ya que el modelo asíncrono proporciona una mejor simultaneidad.  
  
 En el lado de recepción, cuando un adaptador envía un lote de mensajes para el motor de mensajería de BizTalk (mediante una llamada a **Ibttransportbatch**), el motor de mensajería pone en cola el trabajo con su grupo de subprocesos interno y vuelve inmediatamente. El motor procesa los mensajes en un subproceso independiente, dejando libre al adaptador para que lea más mensajes desde su origen y los envíe sin esperar a que finalice el procesamiento del mensaje anterior.  
  
 En el caso del envío, el adaptador puede ser asíncrono o sincrónico. Sin embargo, si el protocolo es compatible con operaciones asíncronas, debe usar esta compatibilidad para escribir un adaptador escalable. Por ejemplo, los adaptadores de envío de archivo y de HTTP son completamente asíncronos y llevan a cabo muy pocas operaciones de sincronía y bloqueo.  
  
 Las operaciones asíncronas garantizan que el motor de mensajería y el adaptador continúan realizando sus respectivos trabajos en paralelo y que no se esperan para realizar el procesamiento normal de mensajes.  
  
## <a name="use-batching-to-improve-performance"></a>Usar procesamiento por lotes para mejorar el rendimiento  
 El procesamiento por lotes es el mejor punto de partida para escribir un adaptador escalable. Esto ocurre para los adaptadores de envío y de recepción. Cada lote pasa a través de una transacción de base de datos en BizTalk Server, incluso cuando el adaptador es no transaccional. Puesto que hay un retraso fijo con cada transacción, debe tratar de minimizar el número de transacciones mediante la combinación de varias operaciones en un solo lote.  
  
## <a name="do-not-starve-the-net-thread-pool"></a>No privar al grupo de subprocesos .NET  
 La escritura de adaptadores de BizTalk constituye un ejercicio al escribir código de tiempo de ejecución .NET; la escritura de código de tiempo de ejecución .NET constituye, de forma invariable, un ejercicio de la programación asíncrona.  
  
 La privación de grupos de subprocesos .NET supone un riesgo para toda programación asíncrona en .NET; es especialmente importante que el programador de adaptador de BizTalk evite dicho riesgo.  
  
 El grupo de subprocesos .NET es un recurso limitado pero ampliamente compartido. Es fácil escribir código que use uno de los subprocesos del grupo de subprocesos .NET y lo conserve durante un largo período de tiempo, lo que bloquea la ejecución de otros elementos de trabajo.  
  
 Siempre que use **BeginInvoke** o utilizar un temporizador, se utiliza un subproceso de grupo de subprocesos. NET. Si tiene varios elementos de trabajo para realizar (por ejemplo, copiar mensajes externos a MQSeries en BizTalk Server), debe ejecutar un elemento de trabajo (un lote de mensajes en BizTalk Server) y, a continuación, colocarlo en cola en el grupo de subprocesos si hay más trabajo que realizar. No lo coloque en un `while` bucle en el subproceso.  
  
 En términos concretos, esto significa reemplazar `while` bucles con repetidas llamadas a **BeginInvoke**. Este cambio sencillo puede mejorar de forma considerable la respuesta y la capacidad para escalar toda la implementación de forma horizontal.  
  
## <a name="choose-the-right-measurement-when-limiting-batch-size"></a>Seleccionar la medición correcta al limitar el tamaño del lote  
 Si envía mensajes al servidor BizTalk Server en lotes, no limite el tamaño del lote basándose solo en el número de mensajes. Tenga en cuenta lo que ocurre cuando se ha configurado un adaptador procesar por lotes basándose únicamente en el número de mensajes: si el tamaño del lote es dos y el adaptador obtiene cuatro mensajes de tamaño 4 KB, 8 KB, 1 MB y 5MB respectivamente, el primer lote será de 12 KB de tamaño , y el segundo lote será de 6 MB de tamaño.  
  
 Puesto que el motor de mensajería de BizTalk procesa todos los mensajes en un solo lote de forma secuencial, el segundo lote de este ejemplo se procesará mucho más lento que el primero. De este modo, se reduce con eficacia el rendimiento. Un mejor modo de controlar este problema es llevar a cabo el procesamiento por lotes basándose en el número de mensajes y en los bytes totales del lote (es decir, el tamaño del lote en bytes). No hay un número mágico de bytes totales. Sin embargo, en un escenario de procesamiento normal, si el tamaño del lote supera 1 MB, empezará a observar una simultaneidad y un rendimiento pobres.  
  
 Por lo general, los adaptadores son independientes con respecto a los mensajes y desconocen el tamaño de los mensajes en el entorno de producción. Es probable que el tamaño de los mensajes entrantes varíe de forma significativa. Debido a ello, use siempre el número de mensajes y los bytes totales para generar el lote.