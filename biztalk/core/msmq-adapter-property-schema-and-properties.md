---
title: Propiedades y esquema de propiedades de adaptador MSMQ | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AcknowledgeType property [MSMQ adapters]
- MSMQ adapters, schemas
- AppSpecific property [MSMQ adapters]
- SegmentationSupport property [MSMQ adapters]
- SourceMachine property [MSMQ adapters]
- Label property, MSMQ adapters
- MSMQ adapters, properties
- TimeOut property [MSMQ adapters]
- BodyType property [MSMQ adapters]
- CorrelationId property [MSMQ adapters]
- Recoverable property [MSMQ adapters]
- Authenticated property [MSMQ adapters]
- EncryptionAlgorithm property [MSMQ adapters]
- ResponseQueue property [MSMQ adapters]
- configuring [MSMQ adapters], properties
- MaximumMessageSize property [MSMQ adapters]
- UseAuthentication property [MSMQ adapters]
- UseDeadLetterQueue property [MSMQ adapters]
- SentTime property [MSMQ adapters]
- schemas, MSMQ adapters
- TimeOutUnits property [MSMQ adapters]
- CertificateThumbPrint property [MSMQ adapters]
- Id property [MSMQ adapters]
- UseJournalQueue property [MSMQ adapters]
- MessageType property [MSMQ adapters]
- ArrivedTime property [MSMQ adapters]
- Transactional property [MSMQ adapters]
- configuring [MSMQ adapters], schemas
- Acknowledgement property [MSMQ adapters]
- Priority property [MSMQ adapters]
- AdministrationQueue property [MSMQ adapters]
ms.assetid: 9de29341-db8e-4d50-8f1d-3b7397afb58d
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb2d74848353c5c520a9a17d5a6d897d6a4dce1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="msmq-adapter-property-schema-and-properties"></a>Propiedades y esquema de propiedades del adaptador de MSMQ
El adaptador de MSMQ asigna valores a las propiedades de contexto que se utilizan en las aplicaciones. Para obtener una lista de envío y recepción de propiedades del adaptador de MSMQ, vea [cómo configurar una ubicación de recepción de MSMQ](../core/how-to-configure-an-msmq-receive-location.md) y [cómo configurar un puerto de envío MSMQ](../core/how-to-configure-an-msmq-send-port.md).  
  
## <a name="context-properties"></a>Propiedades de contexto  
 En la siguiente tabla se muestran las propiedades de contexto a las que el adaptador de MSMQ asigna valores.  
  
|**Nombre**|**Tipo**|**Description**|**Promueve**|  
|--------------|--------------|---------------------|------------------|  
|**Confirmación**|int|Especifica la clasificación de confirmación que este mensaje se representa mediante los valores de la **System.Messaging.Acknowledgment** enumeración.|No|  
|**AcknowledgeType**|int|Especifica el tipo de mensaje de confirmación que solicita la aplicación que realice el envío.|No|  
|**Propiedad AdministrationQueue**|string|Especifica el nombre de la cola que recibe el mensaje de confirmación.|No|  
|**AppSpecific**|int|Especifica la información concreta de la aplicación que se puede utilizar para organizar los diferentes tipos de mensajes.|Sí|  
|**ArrivedTime**|dateTime|Especifica la hora en la que llegó el mensaje a la cola de destino.|No|  
|**Autenticado**|boolean|Especifica si se autenticó el mensaje.|No|  
|**BodyType**|int|Especifica el tipo de datos que contiene el cuerpo del mensaje.|No|  
|**CertificateThumbPrint**|string|Especifica la huella digital del certificado de cliente que desea utilizar para la autenticación de los mensajes.|Sí|  
|**CorrelationId**|string|Especifica el identificador de mensaje que utilizan los mensajes de confirmación, de informe y de respuesta para hacer referencia al mensaje original.|Sí|  
|**EncryptionAlgorithm**|int|Especifica el algoritmo de cifrado utilizado para cifrar el cuerpo de un mensaje.|No|  
|**Id.**|string|Especifica el identificador del mensaje.|No|  
|**Etiqueta**|string|Especifica una cadena Unicode definida por la aplicación que describe el mensaje.|Sí|  
|**Tamaño máximo de mensaje**|unsignedInt|Especifica el tamaño máximo de mensaje en kilobytes de los mensajes que se envían a la cola en cuestión.|No|  
|**MessageType**|int|Especifica el tipo de mensaje. Un mensaje de Message Queue Server puede ser de uno de los siguientes tipos:<br /><br /> -Normal, que es un mensaje habitual enviado desde una aplicación a una cola o un mensaje de respuesta devuelto a la aplicación de envío.<br />-Confirmación, que genera Message Queue Server siempre que la aplicación de envío lo solicita. Por ejemplo, Message Queue Server puede generar mensajes positivos o negativos para indicar que ha llegado el mensaje original o que se ha leído. Message Queue Server devuelve el mensaje de confirmación correspondiente a la cola de administración especificada por la aplicación de envío.<br />-Report, que genera Message Queue Server siempre que se define una cola de informes en el Administrador de cola de origen. Cuando el seguimiento está habilitado, Message Queue Server envía un mensaje de informe a su cola de informes cada vez que el mensaje original entra o sale de un servidor de Message Queue Server.|No|  
|**Prioridad**|int|Especifica la prioridad del mensaje con los valores definidos en el **System.Messaging.MessagePriority** enumeración.|Sí|  
|**Recuperables**|boolean|Especifica si se garantiza la entrega del mensaje en caso de haber errores en el equipo o problemas en la red.|No|  
|**ResponseQueue**|string|Especifica la cola que recibe los mensajes de respuesta generados por la aplicación.|No|  
|**SegmentationSupport**|boolean|Especifica si se admite la segmentación de mensajes superior a 4 MB.|No|  
|**SentTime**|dateTime|Especifica la fecha y hora del equipo de envío en las que el administrador de cola de origen envió el mensaje.|No|  
|**Máquina de origen**|string|Especifica el equipo donde se originó el mensaje.|No|  
|**TimeOut**|int|Especifica el tiempo que ha tardado el mensaje en llegar a la cola de destino antes de que se produzca un tiempo en espera.|No|  
|**Timeoutunits como**|string|Especifica las unidades de la **tiempo de espera** propiedad. Puede establecer esta propiedad en Días, Horas, Minutos o Segundos.|No|  
|**Transaccional**|boolean|Especifica el comportamiento de las ubicaciones de recepción y los puertos de envío transaccionales y no transaccionales.|No|  
|**UseAuthentication**|boolean|Especifica si se ha autenticado el mensaje (o si debe autenticarse) antes de su envío.|No|  
|**UseDeadLetterQueue**|boolean|Especifica si una copia del mensaje que no se pudo entregar debe enviarse a una cola de mensajes con problemas en la entrega.|No|  
|**UseJournalQueue**|boolean|Especifica si se debe guardar una copia del mensaje en el diario del equipo en el que se originó.|No|  
  
> [!NOTE]
>  El **confirmación**, **AcknowledgeType**, **EncryptionAlgorithm**, y **MessageType** propiedades utilizan el equivalente de enteros valores de las enumeraciones en el **System.Messaging** espacio de nombres. Para obtener más información acerca de estos valores, vea el apartado "Espacio de nombres System.Messaging" en la Ayuda de la Biblioteca de clases de .NET Framework.  
  
> [!NOTE]
>  Si tiene que desarrollar un proyecto de BizTalk que harán que utilizar las propiedades de contexto del adaptador MSMQ, el proyecto de BizTalk debe contener una referencia al archivo **Microsoft.BizTalk.Adapter.MSMQ.MsmqAdapterProperties.dll** ubicado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directorio de instalación.  
  
## <a name="message-labels"></a>Etiquetas de mensaje  
 Puede usar Message Queue Server **etiqueta** propiedad en los filtros agregando una referencia a **Microsoft.BizTalk.Adapter.MSMQ.MsmqAdapterProperties.dll** y seleccionando la propiedad en el  **Filtro** cuadro de diálogo. También puede emplear la propiedad en otros contextos, pues el adaptador de MSMQ la agrega de forma automática al contexto del mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador MSMQ](../core/configuring-the-msmq-adapter.md)