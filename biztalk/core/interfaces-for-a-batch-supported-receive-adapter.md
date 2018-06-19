---
title: Interfaces para un compatible con lotes del adaptador de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa6ee780-189c-41e3-9ab0-6b869e791c0a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2de4d27ec65620adbb5428491c5ab1a53300fd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258012"
---
# <a name="interfaces-for-a-batch-supported-receive-adapter"></a>Interfaces de un adaptador de recepción compatible con lotes
Un adaptador de recepción siempre envía mensajes en un lote. Un lote es una unidad de operaciones de base de datos que se puede utilizar para realizar acciones que no sean envíos. Por ejemplo, un adaptador de recepción puede enviar un conjunto de mensajes, suspender un conjunto diferente de mensajes y eliminar otro conjunto de mensajes en el mismo lote. Agrupar estas operaciones individuales en el mismo lote optimiza el rendimiento, con lo que se minimiza el número de ciclos de ida y vuelta de bases de datos necesario y se recomienda encarecidamente.  
  
 Los adaptadores de recepción aislados y de tipo En curso necesitan implementar las siguientes interfaces para enviar lotes de mensajes al servidor:  
  
-   **IBTTransport**  
  
-   **IBTTransportControl** (sólo para adaptadores en proceso)  
  
-   **IBTTransportConfig**  
  
-   **IBaseComponent**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchCallBack**  
  
 Los siguientes pasos describen la secuencia de acciones que realiza un adaptador de recepción para enviar mensajes al servidor.  
  
1.  Un adaptador de recepción Obtiene el lote del proxy de transporte mediante una llamada a la **GetBatch** método de la **IBTTransportProxy** interfaz. En su llamada a **GetBatch** el adaptador pasa un puntero a su **IBTBatchCallback** implementación de la interfaz.  
  
2.  Un adaptador agrega mensajes de uno en uno en el lote mediante una llamada a la **SubmitMessage** método de la **IBTTransportBatch** interfaz. Si se trata de una operación bidireccional como mensajería petición-respuesta, el **SubmitResponseMessage** se denomina método de esta misma interfaz para enviar el mensaje de respuesta.  
  
3.  Cuando todos los mensajes se han agregado al lote, el adaptador llama a la **realiza** método de la **IBTTransportBatch** interfaz para enviar el lote al proxy de transporte. Dado que recibir adaptadores son de naturaleza asíncrona, el adaptador inmediatamente puede obtener un nuevo lote y comenzar a enviar otros mensajes después de llamar a **realiza**.  
  
4.  Una vez que se ha procesado el lote, el motor de mensajería invoca el adaptador **BatchComplete** método de devolución de llamada mediante el proxy de transporte para realizar la llamada real. Una matriz de **BTBatchOperationStatus** objetos que contiene el estado del envío se pasa al adaptador. Cada objeto corresponde a un tipo de operación y contiene el estado general de la operación, así como el estado para cada uno de los mensajes para los que se ha realizado la operación. Las siguiente secuencia describe las acciones que el adaptador necesita realizar para analizar el estado de proceso por lotes:  
  
    1.  Compruebe el estado de lote general valor HRESULT pasado como parámetro a la **BatchComplete** método. Si se produce un error significa que al menos una de las operaciones del lote no se ha realizado correctamente. Por tanto, se ha producido un error en el envío del lote completo como una entidad. El adaptador debe intentar descubrir los mensajes infractores y reenviar por lotes solo los que al principio no produjeron error.  
  
         Si el estado de lote general se completó correctamente, significa que todos los mensajes que se entregaron al proxy de transporte se han guardado en el disco. Sin embargo, no quiere decir que la canalización haya procesado todos los mensajes correctamente. Es posible que los mensajes que han producido errores en la canalización se suspendan. En cuanto a los mensajes que producen errores en la canalización, el estado de lote general devuelto es correcto, debido a que los datos se han escrito en el disco.  
  
    2.  Compruebe el estado de cada tipo de operación en el parámetro `operationStatus`. Si el estado es **S_OK**, el envío de esta operación se realizó correctamente y no es necesario comprobar el estado de cualquier aún más. Si el estado se establece en **BTS_S_EPM_MESSAGE_SUSPENDED** algunos de los mensajes se han suspendido. **BTS_S_EPM_SECURITY_CHECK_FAILED** significa que algunos mensajes de error de autenticación en el puerto de recepción de una autenticación necesaria. Si **E_FAIL** se devuelve, o cualquier HRESULT tiene un valor que es menor que cero, el envío de mensajes de este error en la operación.  
  
    3.  Compruebe el estado de los mensajes individuales para el tipo de operación. Para el tipo de operación de envío, el estado de cada mensaje se establece en **S_OK** si el envío se realizó correctamente. **BTS_S_EPM_MESSAGE_SUSPENDED** se devuelve si el mensaje se suspende. **BTS_S_EPM_SECURITY_CHECK_FAILED** se devuelve si el mensaje de error de autenticación en un puerto de recepción que requiere autenticación. **E_BTS_NO_SUBSCRIPTION** vuelve a aparecer si no había suscriptores para el mensaje publicado. Si **E_FAIL** se devuelve, o cualquier HRESULT tiene un valor que es menor que cero, el error de envío de mensaje.  
  
    4.  Según el adaptador, puede que desee suspender mensajes que devuelven **E_FAIL** o cualquier HRESULT que produzca errores.  
  
5.  El **BatchComplete** método debe devolver **S_OK** o **E_FAIL** para indicar el resultado de ejecución. Si el **BatchComplete** método **E_FAIL** o cualquier HRESULT negativo, el proxy de transporte registra un error.  
  
 La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de recepción compatible con lotes.  
  
 ![](../core/media/ebiz-sdk-devadapter1.gif "ebiz_sdk_devadapter1")  
Flujo de trabajo de un adaptador de recepción que envía un lote de mensajes  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de recepción](../core/developing-a-receive-adapter.md)   
 [Crear instancias e inicializar un adaptador de recepción](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [Interfaces para un proceso en el adaptador de recepción](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [Adaptador de recepción de interfaces para un aislado](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [Adaptador de recepción de interfaces para transaccional compatible con lotes](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [Adaptador de recepción de interfaces para una solicitud-respuesta sincrónico](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)