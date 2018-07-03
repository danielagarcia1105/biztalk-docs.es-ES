---
title: Mejorado seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking
ms.assetid: 8adf78f0-ab0f-44d4-aa5b-9546e2bdf01f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f5fc6e16ebbdc8f76ff07c03742e3231025dc29
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973349"
---
# <a name="enhanced-tracking"></a>Seguimiento mejorado
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporciona una capacidad mejorada para realizar un seguimiento de los procesos y los mensajes. La funcionalidad nativa de actividad de supervisión económica (BAM) en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consiste en realizar un seguimiento de sólo metadatos. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] contenido del mensaje pistas: contenido del servicio y los encabezados.  

 En la tabla siguiente se muestra la gama completa de los datos de seguimiento en [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]. En este tema aborda el proceso y seguimiento de mensajes. Para obtener más información acerca de los datos sin repudio, consulte [el procesamiento de mensajes de RNIF](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md).  


|           Información sometida a seguimiento           |                                                        Característica                                                        |                                                                                   Acceso de usuario                                                                                   |
|-----------------------------------------|-----------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Proceso de RosettaNet y seguimiento de mensajes | A través de BAM (con las tablas de base de datos y vistas de los datos) para los metadatos y las interfaces patentadas para el cuerpo del mensaje |                                                                   Interfaz de usuario BAM o la interfaz de usuario personalizada                                                                   |
|            Errores y eventos            |                A través de la [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos                |                                                                                    Registro de eventos                                                                                    |
|          Datos sin repudio           |                         A través de interfaces patentadas (hilo se almacenan los formatos de mensajes)                          | Las tablas MessageStorageIn y MessageStorageOut de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos de archivo y a través del SDK |

## <a name="process-and-message-tracking"></a>Proceso y seguimiento de mensajes  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] realiza un seguimiento de dos actividades básicas: la actividad del proceso y la actividad de mensaje. Procesamiento de mensajes en orquestaciones de proceso público realiza el seguimiento de la actividad del proceso. El mensaje realiza un seguimiento de la actividad de procesamiento de envío o canalizaciones de recepción.  

 La actividad del proceso realiza un seguimiento de los metadatos del mensaje completo. La actividad de mensaje realiza el seguimiento de los metadatos de actividad de proceso y el contenido del mensaje.  

### <a name="process-activity"></a>Actividad de proceso  
 Cada vez que se crea una instancia de una orquestación de proceso público (iniciador o el servicio de respuesta), el proceso público crea un registro de actividad del proceso en la base de datos de seguimiento de BAM. En diversos puntos en el proceso público, la orquestación guarda los metadatos de seguimiento. La actividad del proceso se detiene cuando se detiene la orquestación.  

 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pistas de completar los metadatos para el proceso en dos instancias:  

- Cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es un servicio de respuesta y recibe un mensaje de acción de solicitud  

- Cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es un iniciador y recibe un mensaje de solicitud de la aplicación de línea de negocio (LOB).  

  Cada vez que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía o recibe un mensaje, el proceso público actualiza el estado de la actividad del proceso.  

### <a name="message-activity"></a>Actividad de mensaje  
 La actividad de mensaje realiza el seguimiento de mensajes mediante el envío y las canalizaciones de recepción. Cada vez que un envío o la canalización de recepción procesa un mensaje, la canalización crea una actividad de mensaje. La canalización crea un registro de actividad de mensaje en la base de datos y un registro de mensajes en de seguimiento de BAM el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archivar base de datos.  

 La actividad de mensaje guarda el contenido del mensaje, incluidos el contenido del servicio y encabezados. En la canalización de recepción, si el descodificador de MIME se realiza correctamente, la actividad guarda las cuatro partes del contenido del mensaje como XML en formato de texto en la columna ContentXml de la tabla en el elemento MessageContent. Si se produce un error en el descodificador de MIME, la actividad guarda el contenido del mensaje en formato binario en la columna ContentBinary de la tabla en el elemento MessageContent.  

### <a name="use-of-tracking-data-in-correlation"></a>Uso de datos de correlación de seguimiento  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] realiza un seguimiento de la información necesaria para poner en correlación cada proceso para todos los mensajes intercambiados para un PIP específico (positivas o negativas de las señales y las señales de solicitud y respuesta). Asimismo, rastrea la información que se usa para correlacionar un mensaje 0A1, si [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía una notificación de error para ese PIP. La combinación de los Id. de instancia PIP, el nombre de entidad de iniciador y el nombre de la entidad de destino determine los mensajes relacionados con una actividad.  

### <a name="tracking-databases"></a>Bases de datos de seguimiento  
 Las actividades de proceso y el mensaje de guardar el seguimiento de los metadatos en el BAMPrimaryImport [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos. En esta base de datos, las tablas cuyos nombres empiezan por el prefijo "bam_Process" almacenan datos de seguimiento de actividad del proceso y las tablas cuyos nombres empiezan por el prefijo "bam_Message" almacenan los datos de seguimiento de actividad de mensaje. Cada proceso independiente o una actividad de mensaje tiene un único registro correspondiente en las tablas. Información acerca de las dos actividades y seguimiento de los metadatos, se incluye en las tablas de metadatos cuyos nombres empiezan por el prefijo "bam_Metadata".  

 Puede consumir los datos en la base de datos de seguimiento BAMPrimaryImport mediante las siguientes vistas. Estas y otras vistas están disponibles en Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nodo de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración.  

|Vista de seguimiento|data|  
|-------------------|----------|  
|bam_Process_AllInstances|Estado del proceso de RosettaNet definido por el PIP|  
|bam_Message_AllInstances|Estados de todos los mensajes|  
|bam_Process_CompletedInstances|Estado de los procesos completados|  

 La actividad de mensaje guarda el contenido del mensaje en la tabla en el elemento MessageContent de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archivar base de datos. Puede examinar el contenido mediante la ejecución de una consulta en la tabla el elemento MessageContent, mediante el identificador único para el mensaje. La actividad almacena el identificador único de la columna ContentKey de la actividad de mensaje de las tablas de seguimiento, con el prefijo "bam_Message.  

> [!IMPORTANT]
>  La actividad de mensaje comparte el contenido del mensaje en texto no cifrado en la tabla en el elemento MessageContent de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archivar base de datos. Esto se produce en todos los escenarios de seguimiento, incluidos aquellos en los que los mensajes están cifrados o firmados. Si le preocupa la accesibilidad del contenido del mensaje, puede restringir el acceso a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archivar base de datos.  

 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] el seguimiento de las API de BAM se utiliza para guardar los datos de seguimiento.  

### <a name="status-codes"></a>Códigos de estado  
 Las tablas bam_Process_Active y bam_Process_Completed en la base de datos BAMPrimaryImport incluyen una columna de estado que indica el estado del proceso. En la tabla siguiente se muestra los valores para cada código de estado.  

|Código de estado|Estado del proceso|  
|-----------------|-------------------|  
|-1000|ActivityNotPresentFatalError|  
|-500|UnexpectedFatalError|  
|-100|Initiated0A1|  
|-99|TerminatedOnError<br /> (Cualquier otra conclusión que termina con 0A1)|  
|-85|TerminatedBy0A1|  
|-75|TimedOutOnResponseSignal|  
|-50|TimedOutOnResponse|  
|-25|TimedOutOnActionSignal|  
|0|RegisteredActivity|  
|1|ActivityToBeInitiated|  
|10|ReceivedAction o SentAction|  
|25|ReceivedActionSignal o SentActionSignal|  
|35|ReceivedActionSignal2 o SentActionSignal2<br /> (2 de la señal está pensada para RNIF v11)|  
|50|ReceivedResponse o SentResponse|  
|75|ReceivedResponseSignal o SentResponseSignal|  
|85|ReceivedResponseSignal2 o SentResponseSignal2<br /> (2 de la señal está pensada para RNIF v11)|  
|100|ActivityCompleted|  

### <a name="activity-definition-file"></a>Archivo de definición de actividad  
 El archivo de definición de actividad define los campos que realiza el seguimiento en BAM, y cómo verlos. Para obtener más información acerca de este archivo, consulte [trabajar con el archivo de definición de actividad de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/working-with-the-tracking-activity-definition-file.md).  

 Para obtener más información acerca de SAE, vea "actividad de supervisión económica (BAM)" en la Ayuda de BizTalk Server.  

## <a name="see-also"></a>Vea también  
 [Trabajar con el archivo de definición de actividad de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/working-with-the-tracking-activity-definition-file.md)   
 [Qué agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)