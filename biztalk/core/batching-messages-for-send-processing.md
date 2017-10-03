---
title: "Procesamiento de envío de mensajes por lotes para | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d9115ec-13bc-41a8-8928-57b168c95af4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e87600bec54679688fae5084af3b4a1bde9ca807
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="batching-messages-for-send-processing"></a>Procesar mensajes por lotes para el procesamiento de envío
## <a name="send-adapter-batch-management"></a>Administración de lotes del adaptador de envío  
 Cuando se usan transacciones en el envío, la misma transacción que creó BizTalk Server y se usó para el envío del sistema de destino se usa para la eliminación de los mensajes correspondientes una vez que ésta se ha enviado de forma correcta. Si no se producen errores, se puede finalizar la transacción, con lo que se anula la eliminación, y los datos permanecen en BizTalk Server y no en el sistema de destino. Esto evita que se dupliquen los mensajes. Las transacciones solo son compatibles con adaptadores de envío asíncronos. No debería usar transacciones con adaptadores de envío sincrónicos.  
  
 Pero el adaptador no puede finalizar simplemente la transacción; debe controlar también correctamente el estado de los mensajes. En concreto, el adaptador debe llamar a los métodos **reenviar**, **MoveToNextTransport**, y **MoveToSuspendQ** forma adecuada según el número de reintentos y si un transporte de copia de seguridad está disponible.  
  
 Es importante colocar el **eliminar** y **SubmitResponse** operaciones juntas en un lote que usa la misma transacción. Los errores se controlan al final de la transacción (para asegurar que los datos solo se envían una vez a un sistema externo). Pero todavía desea reenviar o llamar a **MoveToNextTransport** para el mensaje en BizTalk Server. Para ello, use un lote normal (no transaccional) independiente para estos tipos de operaciones.  
  
 En la siguiente ilustración, se muestra el uso de lotes independientes para mensajes de respuesta.  
  
 ![Usar un lote independiente para los mensajes de respuesta](../core/media/eawp-seperatebatch.gif "EAWP_SeperateBatch")  
  
## <a name="sorting-the-send-side-transactional-batches-by-endpoint"></a>Ordenar los lotes transaccionales de envío por extremo  
 Los lotes de mensajes que envía BizTalk Server al adaptador pueden abarcar varios puertos de envío (o extremos). Dado que el adaptador desea tener una transacción para un extremo único, normalmente, el adaptador debe ordenar los mensajes basándose en el puerto de envío (**SPName** o **OutboundTransportLocation**). Al hacerlo, el adaptador puede crear una transacción que abarque solo un determinado puerto de envío.  
  
 Por ejemplo, cuando un adaptador de envío FTP recibe un lote de mensajes de BizTalk Server, obtiene un lote mixto de mensajes para todos los puertos de envío FTP que estén activos en ese momento. Esto sucede porque la API se basa en singleton, lo que significa que se carga solo un único adaptador FTP, no uno por puerto de envío.  
  
 El adaptador debe ordenar primero en lotes independientes el lote de mensajes que ha proporcionado BizTalk Server, un lote por cada extremo. A continuación, puede tratar, a su vez, cada extremo y es posible que construya lotes de eliminación para cada uno. Las clases genéricas reutilizables BaseAdapter del código de ejemplo de SDK funcionan del mismo modo.  
  
## <a name="sorting-for-dynamic-send"></a>Ordenar envíos dinámicos  
 Una orquestación de BizTalk Server puede enviar un mensaje a un puerto que no se haya configurado, siempre y cuando proporcione detalles de configuración suficientes en el encabezado del mensaje y en la propia URL. BizTalk Server debe reconocer el protocolo de la URL.  
  
 A la hora de ordenar mensajes, debería prestar atención al establecimiento de lo que define un extremo. Esto es especialmente útil en el caso de un envío dinámico. Si solo el URI define el extremo, la operación es sencilla. Sin embargo, el servidor FTP puede usar los detalles de inicio de sesión del nombre de usuario en una sesión FTP para definir el extremo true. En este caso, si el adaptador inicia sesión en una cuenta diferente, puede estar conectado a un directorio distinto.  
  
 En algunos casos, no se conoce el extremo true hasta que haya ejecutado el comando de inicio de sesión único (SSO) empresarial **al método ValidateAndRedeemTicket**.  
  
 En el caso de MQSeries, se puede configurar la determinación de si se usan transacciones. Teniendo en cuenta la arquitectura y el uso de un objeto COM+ remoto, es mejor distinguir un extremo transaccional de un extremo no transaccional.  
  
 En resumen, la ordenación de mensajes en los lotes de único extremo es, en ocasiones, una tarea importante y puede implicar tantos pasos adicionales como valores de contexto e incluso el resultado de una llamada a SSO.  
  
## <a name="sorting-for-static-send"></a>Ordenar envíos estáticos  
 Si el extremo está configurado de forma estática, hay un único GUID en el contexto del mensaje denominado Id. de puerto estático (SPID). Este valor puede usarse para ordenar el extremo. El siguiente código puede usarse para recuperarlo:  
  
```  
string spid = (string)message.Context.Read("SPID", "http://schemas.microsoft.com/BizTalk/2003/system-properties");  
```  
  
 Éste es útil en el momento de considerar los problemas que ha provocado el marco de trabajo de configuración basado en definición de esquemas XML (XSD). Con este marco de trabajo, tiene una propiedad que puede ser parte de la clave de extremo incluida dentro de XML en una única propiedad de contexto. Si tiene un SPID en el contexto, puede usarlo para ordenar el lote. De lo contrario, está creando un envío dinámico y deberá construir una clave alternativa con la que ordenar el lote.  
  
 En la siguiente ilustración, se muestra la ordenación de mensajes por extremo.  
  
 ![Ordenar mensajes por extremo](../core/media/eawp-sortbatch.gif "EAWP_SortBatch")  
  
 Recuerde que el número de reintentos de un mensaje no tiene en cuenta si el lote es correcto o contiene errores. En el caso de los envíos, se pueden producir errores en un lote de mensajes porque haya errores en algunos de ellos. El adaptador debe tomar una determinación de cada mensaje que recibe. En el caso de lotes con errores, puede suponer que se vuelven a enviar todos los mensajes. Sin embargo, si se vuelven a enviar todos los mensajes de un lote con errores, el número de reintentos (que mantiene el motor de BizTalk Server) aumenta de forma incorrecta incluso para los mensajes correctos porque se encuentran en el mismo lote que los que tienen errores. En este caso, un adaptador podría modificar el lote de salida y reintentar los mensajes correctos con el sistema externo.