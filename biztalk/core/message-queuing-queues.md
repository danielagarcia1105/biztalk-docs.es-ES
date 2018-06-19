---
title: Colas de puesta en cola de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [MSMQ adapters], queue paths
- naming conventions, MSMQ adapters
- configuring [MSMQ adapters], naming conventions
- messages, queuing
- MSMQ adapters, troubleshooting
- MSMQ adapters, message queues
- configuring [MSMQ adapters], troubleshooting
- troubleshooting, queue paths [MSMQ adapters]
- naming conventions, queue paths [MSMQ adapters]
- configuring [MSMQ adapters], message queues
ms.assetid: b802348e-8543-4b06-a6e4-149b86139fb1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa8d2521a8cf434c7a0ea56f749f9df3f032551e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971466"
---
# <a name="message-queuing-queues"></a>Colas de puesta en cola de mensajes
Esta sección describe cómo especificar colas de Microsoft Message Queue Server (a la que también se conoce como MSMQ) cuando utiliza el adaptador de MSMQ. Describe las convenciones para especificar rutas y la función que los nombres de formato desempeñan cuando se traducen rutas a designaciones de cola.  
  
## <a name="queue-path-naming-conventions"></a>Convenciones de nomenclatura de ruta de cola  
 Si el nombre de la cola hace referencia a una ruta, utilice las convenciones de nomenclatura en la tabla siguiente.  
  
|**Tipo de cola**|**Sintaxis de ruta de acceso**|  
|--------------------|-------------------------|  
|Cola pública|*NombreDeEquipo*\QueueName|  
|Cola privada|*NombreDeEquipo*\Private$\QueueName|  
|Cola de diario|*NombreDeEquipo*\QueueName\Journal$|  
|Cola de diario de equipo **Nota:** para cola de recepción solo.|*NombreDeEquipo*\Journal$|  
|Cola de mensajes no enviados del equipo **Nota:** para cola de recepción solo.|*NombreDeEquipo*\Deadletter$|  
|Cola de mensajes no enviados de transacciones de equipo **Nota:** para cola de recepción solo.|*NombreDeEquipo*\XactDeadletter$|  
  
> [!NOTE]
>  La ruta de la cola debe ser única.  
  
 Si el nombre de cola hace referencia a un nombre de formato, toma la forma de una cadena que indica si una cola es pública o privada seguida de un GUID generado para la cola y otros identificadores, según sea necesario. Utilice las convenciones de nomenclatura de la tabla siguiente.  
  
|**Tipo de formato**|**Sintaxis de nombre de formato**|  
|---------------------|--------------------------------|  
|Público|*FormatName*: Public = QueueGUID|  
|Directo|*FormatName*: DIRECT = SPX:NetworkNumber:HostNumber\QueueName<br /><br /> *FormatName*: DIRECT = TCP:IPAddress\QueueName<br /><br /> *FormatName*: DIRECT = OS:ComputerName\QueueName|  
  
 Si la ruta de la cola del puerto de envío es una lista de distribución, la sintaxis de la ruta de la cola es:  
  
 DL=DistributionListGUID  
  
 Si la ruta de la cola de envío o recepción es una URL HTTP o HTTPS, la sintaxis es:  
  
 FormatName:DIRECT = http: / /\<nombre de cliente\>/MSMQ /\<nombre de la cola\>  
  
 FormatName:DIRECT = https: / /\<nombre de cliente\>/MSMQ /\<nombre de la cola\>  
  
> [!NOTE]
>  "msmq" es la carpeta virtual creada por Message Queue Server en Servicios de Internet Information Server (IIS).  
  
> [!NOTE]
>  Sólo puede utilizar HTTP para enviar mensajes. No es posible leer mensajes de una cola de un equipo remoto si aquélla se abre mediante un nombre de formato directo HTTP. No obstante, podrá seguir recibiendo mensajes (con formato) SOAP desde una cola remota mediante la ruta de cola pública o privada sin HTTP.  
  
 Si el nombre de cola hace referencia a una etiqueta de texto descriptivo que el administrador ha especificado para la cola, la sintaxis de la ruta de cola que hace referencia a esta etiqueta es:  
  
 LABEL:MyQueue  
  
> [!NOTE]
>  Las etiquetas no siempre son exclusivas. Por tanto, recibirá un mensaje de error si existe un conflicto de nombres cuando intenta conectarse a una cola específica mediante esta etiqueta.  
  
> [!NOTE]
>  La etiqueta es un campo de transporte necesario para el adaptador.  
  
## <a name="role-of-the-format-name"></a>Función del nombre de formato  
 Message Queue Server utiliza el nombre de formato para identificar una cola y determinar cómo obtener acceso a ella. Message Queue Server asigna el nombre de formato a la cola.  
  
 Cuando especifica una cola mediante la sintaxis del nombre de la ruta, por ejemplo, myMachine\myQueue, Message Queue Server busca la ruta para encontrar el nombre de formato asociado. Message Queue Server utiliza ese nombre de formato para obtener acceso a la cola. Cuando especifica el nombre de formato, Message Queue Server utiliza el nombre de formato utilizado por el usuario.  
  
 Para obtener más información acerca de nombres de formato, vea "Propiedad MessageQueue.FormatName" en la Ayuda de la biblioteca de clases de .Net Framework.  
  
## <a name="troubleshooting-queue-paths"></a>Solucionar problemas de rutas de cola  
  
-   Se produce una excepción si no coincide la sintaxis de la ruta de cola proporcionada con uno de los formatos descritos anteriormente en "Convenciones de nomenclatura de ruta de cola."  
  
-   Los siguientes caracteres no son válidos como nombre de equipo en la ruta de cola:  
  
     \ ; , + "  
  
     Se produce una excepción si el nombre de equipo es un número. Por ejemplo: 234\private$ \queue.  
  
-   Para una cola de mensajes con problemas de entrega de equipo, una cola de diario de equipo y una cola de mensajes con problemas de entrega de transacción de equipos, se produce una excepción si el usuario especifica cualquiera de las colas de sistema como la cola de destino para envío.  
  
-   **System.Messaging.MessageQueue.Exists** no funciona para las colas remotas. Para obtener más información, vea "Método MessageQueue.Exists" en la Ayuda de la biblioteca de clases de .NET Framework.  
  
## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de MSMQ](../core/configuring-the-msmq-adapter.md)