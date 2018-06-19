---
title: Mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, headers
- messages, acknowledgements
- messages, persisting
- messages
- examples, message headers
- properties
- message headers
- EMS messages
ms.assetid: 65bb3431-7186-4d4c-b004-932cdf070e73
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f7313e93029ca75d345aa4e9603699c50399230
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266692"
---
# <a name="messages"></a>Mensajes
Un mensaje de Enterprise Message Service (EMS), como un mensaje JMS, contiene tres partes independientes: encabezado, propiedades y cuerpo. El encabezado es la única parte obligatoria de un mensaje de EMS. En este tema se describe cómo se tratan los mensajes en el Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service.  
  
> [!NOTE]
>  Para establecer o recuperar un campo de encabezado (por ejemplo, establezca la prioridad del mensaje o el Id. de correlación) o una propiedad de mensaje desde la orquestación, debe agregar una referencia a la **Microsoft.BizTalk.Adapters.TIBCOEMSProperties.dll** en el proyecto mediante el Explorador de soluciones.  
  
## <a name="message-header"></a>Encabezado de mensaje  
 El encabezado de mensaje tiene una serie de campos predefinidos que contienen valores. El adaptador de BizTalk para TIBCO Enterprise Message Service sabe lo que puede y lo que no puede establecer en el encabezado. Si intenta establecer un valor de sólo lectura, el adaptador redirecciona o establece el valor en la sección Propiedades{}.  
  
### <a name="header-example"></a>Ejemplo de encabezado  
 En el ejemplo siguiente, observe que **propiedades = {destino = {String: Queue [Q2]}}**. `Properties`es una propiedad que contiene una cadena y el contenido de la cadena es **Q2**. Esto no tiene nada que ver con la sección Destino; contiene cadenas de valores establecidas que no pueden colocarse en ningún otro lugar, por lo que el adaptador las ha almacenado en esta ubicación de la sección.  
  
 Se puede establecer la propiedad `ReplyTo` en la orquestación para indicar a un cliente final dónde debe enviar una respuesta. EMS establece la propiedad `Destination` cuando el mensaje se recibe de TIBCOEMS. Esta segunda propiedad es de sólo lectura en la orquestación que recibe el mensaje de TIBCOEMS y no se puede editar en la orquestación.  
  
 Por ejemplo, una orquestación no puede distribuir mensajes ni establecer el destino de forma dinámica dentro de una orquestación. El valor de Destination viene establecido por el puerto al que se va a transmitir el mensaje.  
  
 Si desea distribuir mensajes en distintas colas, debe crear puertos de envío para cada una de ellas. La orquestación puede decidir a qué puerto se va a asignar el mensaje.  
  
 En el siguiente ejemplo de mensaje, Destination= `{Queue[Q1]}` es de sólo lectura. TIBCOEMS establece este valor cuando el servidor recibe el mensaje. El valor de Destination, Q1, proviene de las propiedades de transporte.  
  
#### <a name="example"></a>Ejemplo  
  
```  
TextMessage={   
    Header={ MessageID={ID:EMS-SERVER.824437A58B11C75F4:1}   
    Destination={Queue[Q1]}   
  
        ' This is READONLY. It gets set by the server when the  
        ' message is received by the server (EMS). It is set in the  
        ' Transport Properties when you specify that you want to  
        ' listen for messages on Q1.  
    ReplyTo={}   
    DeliveryMode={Persistent}   
    Redelivered={False}   
    CorrelationID={}   
    MsgType={}   
    Timestamp={12/1/2005 11:59:01 PM}   
    Expiration={0}   
    Priority={1} }   
    Properties={ Destination={String:Queue[Q2]} }   
  
        ' This is a property that contains a string, and the   
        ' contents of the string is Q2. This has nothing to do with  
        ' the Destination section above – it is just another   
        ' property that is set.   
        ' This is in the schema. The adapter knows what it can and   
        ' cannot set in an EMS header. The values that the adapter   
        ' cannot set are put in the Properties section.   
    text={<?xml version="1.0" encoding="utf-16"?>  
    <ns0:Employees xmlns:ns0="http://BizTalk_Server_Project1.Employee">  
        <Emp Id="Id_0">  
            Name>Name_0</Name>  
        </Emp>  
    </ns0:Employees>  
    }  
```  
  
 El encabezado contiene una serie de campos predefinidos que contienen valores, que el adaptador promueve al contexto del mensaje de BizTalk Server para usarlos en la orquestación. Las propiedades promocionadas son idénticas en su definición a las propiedades de encabezado estándar, de acuerdo con la definición de la especificación JMS y las extensiones de TIBCO Enterprise Message Service. Todas las propiedades excepto dos están disponibles en la orquestación como recibidas de EMS: `Destination` y `ReplyTo` describen un destino que no se puede asignar correctamente para su uso en una orquestación como una única propiedad.  
  
 El adaptador de BizTalk para TIBCO EMS asigna la propiedad TIBCOEMS a un tipo de cadena y usa la representación de la cadena Destination. Es similar a `StaticQueue[queuename]` o `StatisTopic[topicname]`. La orquestación puede establecer el valor de `ReplyTo` y el adaptador lo sustituye con un objeto de destino válido en el encabezado.  
  
 El adaptador proporciona un ensamblado de esquema y referencia que describe todas las propiedades de encabezado TIBCO EMS que pueden usar las orquestaciones. Estas propiedades se pueden usar para filtrar mensajes entrantes o agregarlas al mensaje saliente. Las reglas que dirigen el filtro de orquestación son distintas de aquéllas del selector de mensajes para el servidor EMS. Por ejemplo, las orquestaciones pueden filtrar según `TibcoEMS.ReplyTo` o la propiedad `TibcoEMS.Destination`, pero no se admite en la especificación JMS para permitir el selector de mensajes en esta misma propiedad.  
  
 Si la orquestación define estas propiedades, éstas se incluyen en las propiedades de encabezado del mensaje de JMS. De forma alternativa, si se recibe el mensaje de EMS, estas propiedades de encabezado se copian en el contexto del mensaje de BizTalk Server.  
  
 En caso de que una propiedad coincida con la configuración del puerto, el valor de la propiedad del mensaje tiene prioridad en la configuración del puerto. Por ejemplo, si la prioridad se establece como 4 en el puerto, pero la prioridad del mensaje se establece como 9 en la lógica de la orquestación, TIBCO EMS recibe el mensaje con una prioridad de 9.  
  
### <a name="property-descriptions"></a>Descripciones de propiedades  
 En la siguiente tabla se describe cómo el adaptador de BizTalk usa cada una de estas propiedades para TIBCO Enterprise Message Service.  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|TibcoEMS.MessageID|string|El envío de llamadas asigna un Id. único a los mensajes y lo registra en el encabezado.<br /><br /> Todos los valores de Id. de mensaje empiezan con un Id. de prefijo de tres caracteres (que se reserva con este propósito).<br /><br /> Solo lectura. Cambiar el valor no influye en el mensaje.|  
|TibcoEMS.Timestamp|long|El envío de llamadas registra una marca de tiempo UTC en el encabezado. Indica el tiempo aproximado que tarda el servidor en aceptar el mensaje.<br /><br /> El valor está en milisegundos desde el 1 de enero de 1970.<br /><br /> Solo lectura. Cambiar el valor no influye en el mensaje.|  
|TibcoEMS.Redelivered|boolean|El servidor establece el encabezado para indicar si un mensaje puede duplicar un mensaje entregado anteriormente:<br /><br /> -false: el servidor no ha intentado anteriormente entregar este mensaje al consumidor.<br />-true: es probable que, aunque no está garantizado, que el servidor haya intentado anteriormente entregar este mensaje al consumidor, pero el cliente no devolvió la confirmación a tiempo.<br /><br /> Solo lectura. Cambiar el valor no influye en el mensaje.|  
|TibcoEMS.Destination|string|El envío de llamadas registra el destino (cola o tema) del mensaje en el encabezado. El formato se adapta de un destino a una cadena. El formato se ha descrito anteriormente.<br /><br /> Solo lectura. Cambiar el valor no influye en el mensaje.|  
|TibcoEMS.DeliveryMode|string|Tiene dos valores posibles: PERSISTENTE y no PERSISTENTE. El valor predeterminado es el modo PERSISTENT.<br /><br /> El adaptador espera una confirmación del servidor EMS antes de confirmar el mensaje enviado al servidor BizTalk Server. Esta propiedad de encabezado y el elemento de configuración del puerto controla el tiempo que tarda EMS en enviar esta confirmación al adaptador así como la confiabilidad de la transmisión del mensaje.<br /><br /> Usar el modo de entrega PERSISTENT: el servidor EMS espera hasta que el mensaje se almacena correctamente en el servidor EMS. Esta acción garantiza que el mensaje ha llegado a la cola. Si usa el modo de entrega PERSISTENT, tenga en cuenta lo siguiente:<br /><br /> Cuanto más grandes sean los mensajes, más tiempo tardará BizTalk Server en considerar el mensaje como enviado.<br /><br /> Usar el modo NON-PERSISTENT: el servidor EMS devuelve la confirmación antes de almacenar el mensaje. En caso de que se produzca algún error en el servidor EMS, el mensaje se puede perder si se considera que BizTalk Server lo ha enviado correctamente.|  
|TibcoEMS.Expiration|long|Tiempo de validez del mensaje antes de que caduque. Si se establece como 0, el mensaje no caduca.<br /><br /> El tiempo de validez se especifica en milisegundos.|  
|TibcoEMS.Priority|int|Usa un ranking numérico, entre 0 y 9, para definir la prioridad del mensaje como normal o expedida. Los números más altos representan mayor prioridad.|  
|TibcoEMS.CorrolationID|string|Se puede usar para vincular mensajes, por ejemplo, vincular un mensaje de respuesta a una mensaje de solicitud.<br /><br /> Por lo general, es el mismo valor que `EMS.JMSMessageID`. Se suele utilizar junto con la propiedad `EMS.JMSReplyTo`.|  
|TibcoEMS.ReplyTo|string|Destino al que se debe enviar la respuesta del mensaje. El formato es idéntico a `EMS.JMSDestination` y también a la configuración del puerto.|  
|TibcoEMS.Type|string|No describe el tipo de mensaje (texto, byte, cadena …).<br /><br /> Algunos proveedores de JMS usan un repositorio de mensajes para almacenar definiciones de tipo de mensaje. Los programas cliente pueden almacenar un valor en este campo para hacer referencia a una definición del repositorio. EMS admite este encabezado pero no lo usa.<br /><br /> La especificación JMS no define un repositorio de definición de mensajes estándar, ni define una directiva de cambio de nombre para definiciones de tipo de mensaje.<br /><br /> Algunos proveedores requieren definiciones de tipo de mensaje para los mensajes de la aplicación. Para garantizar la compatibilidad con dichos proveedores, los programas cliente pueden establecer este encabezado, incluso si la aplicación cliente no lo usa.<br /><br /> Para garantizar la portabilidad, los clientes pueden establecer este encabezado con valores simbólicos (en lugar de literales) y configurarlos para coincidir con el repositorio del proveedor.|  
  
## <a name="properties"></a>Propiedades  
 El integrador puede definir un conjunto de propiedades para promocionarlas en el contexto del mensaje de BizTalk Server, tras lo cual las propiedades se agregan a la parte de propiedades del mensaje de JMS. El integrador tiene cuidado al definir el tipo de la propiedad mientras se crea el esquema. Si este valor de propiedad se usa en un selector de mensajes, determinadas operaciones son válidas según el tipo de propiedad. Por ejemplo, si un selector de mensajes **myMessageProperty > 5** es usa, la propiedad debe definirse como un valor entero y el adaptador coloca el valor en el mensaje como un valor entero. En cuanto a las propiedades que se van a promocionar, los nombres de propiedades deben empezar con EMSX. Además, deben tener el mismo nombre que las propiedades predefinidas.  
  
 El adaptador de BizTalk para TIBCO Enterprise Message Service proporciona un esquema y un ensamblado, que declaran las propiedades específicas de EMS y JMS que pueden aparecer en esta sección. Éstas se pueden aumentar para incluir algunas omisiones. Todas las propiedades EMSX a las que se hace referencia en el contexto del mensaje se colocan en la sección de propiedades del mensaje de EMS. Para obtener más información, vea la Guía de usuario de TIBCO EMS.  
  
## <a name="body"></a>Cuerpo  
 EMS admite todos los mensajes enumerados en la especificación JMS: texto, byte, secuencia, asignación y objeto. El adaptador de BizTalk para TIBCO EMS admite únicamente el tipo de mensaje de texto.  
  
 JMS no requiere que los mensajes de tipo de texto contengan cuerpos con formato XML. El adaptador no procesa el cuerpo del mensaje; se proporciona para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como recibidos.  Por lo tanto, los mensajes enviados a BizTalk por el adaptador no pueden analizar siempre como datos XML.  
  
## <a name="persistent-messages"></a>Mensajes persistentes  
 Los mensajes se pueden almacenar en el servidor EMS para garantizar exactamente una entrega única a un suscriptor. No obstante, esto puede tener una influencia significativa en el rendimiento del adaptador. Cuando envía mensajes, EMS almacena el mensaje en un almacenamiento local antes de que confirmar la recepción del mensaje en el adaptador. Puede establecer esta propiedad en cada uno de los mensajes de la orquestación o para todos los mensajes procesados por el puerto.  
  
 Desde el punto de vista de la recepción, el adaptador puede perder mensajes cuando no se suscribe al tema. Los mensajes enviados a temas cuando no hay suscriptores, no se almacenan en EMS. El adaptador necesita un mecanismo para recibir mensajes que se envían incluso cando no se han suscrito actualmente. No obstante, al igual que el uso de mensajes persistentes, esto tiene una influencia significativa en el rendimiento de EMS y no siempre es necesario.  
  
> [!NOTE]
>  Hay un mecanismo para la recepción desde el punto de vista de EMS, pero no se implementa si no se desea realmente. Este es sólo un problema del tema. No afecta a las colas. Por lo general, un tema se usa para los datos específicos de tiempo -- cotizaciones de acciones, por ejemplo. Si se pierde el precio de una acción, sabrá que deberá enviarlo de nuevo posteriormente.  
  
 Por estos motivos, la configuración de puerto le permite habilitar o deshabilitar la persistencia del mensaje en el servidor EMS.  
  
## <a name="message-acknowledgement"></a>Reconocimiento de mensajes  
 El adaptador de BizTalk para TIBCO Enterprise Message Service siempre confirma la recepción de un mensajes cuando dicho mensaje se ha distribuido correctamente en el servidor BizTalk Server. Esto significa que los mensajes sin confirmar se vuelven a enviar de EMS al adaptador. El adaptador no puede controlar el número de veces que se vuelve a enviar el mensaje mediante EMS ya que se trata de una configuración de destino. No obstante, el adaptador puede controlar si el mensaje se envía o no al cuadro de mensajes. El servidor EMS controla el número máximo de veces que se envía un mensaje erróneo a una cola.  
  
 Para mensajes que se van a volver a entregar, el servidor EMS establece la propiedad `JMSRedelivered` como True e incrementa `JMSXDeliveryCount`. Ambos valores de propiedad se encuentran disponibles en la orquestación. No puede mover un mensaje a la cola sin entregar EMS sin entregarlo allí. Hacerlo cambiaría las propiedades del mensaje.  
  
 Cuando un mensaje alcanza el recuento máximo de reentregas configurado, el servidor EMS determina si el mensaje se debe eliminar o colocar en la cola sin entregar $sys. El servidor EMS toma la decisión basándose en la propiedad `JMS_TIBCO_PRESERVE_UNDELIVERED`; si se establece como True, el mensaje se envía a la cola sin entregar o se elimina. Esta propiedad se puede establecer en la orquestación antes de enviar el mensaje. Tras la entrega, no se puede cambiar la propiedad del mensaje. Los mensajes enviados a EMS se confirman en BizTalk Server cuando se reciben correctamente. Si hay un error en el envío de temas a EMS, se suspenden y se marcan como recuperables.  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)