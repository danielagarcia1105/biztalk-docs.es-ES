---
title: Mejorado seguimiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tracking
ms.assetid: 8adf78f0-ab0f-44d4-aa5b-9546e2bdf01f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6660cf8f783a407c3ddead342effecfb4cdd0201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enhanced-tracking"></a>Seguimiento mejorado
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporciona una capacidad mejorada para realizar el seguimiento de mensajes y procesos. La funcionalidad nativa de actividad de supervisión económica (BAM) en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consiste en realizar un seguimiento de sólo metadatos. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]realiza un seguimiento de contenido del mensaje, encabezados y contenido del servicio.  
  
 En la tabla siguiente se muestra todo el rango de datos de seguimiento en [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]. En este tema se aborda proceso y seguimiento de mensajes. Para obtener más información acerca de los datos sin repudio, consulte [el procesamiento de mensajes de RNIF](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md).  
  
|Información sometida a seguimiento|Característica|Acceso de usuario|  
|-------------------------|-------------|-----------------|  
|Proceso de RosettaNet y seguimiento de mensajes|A través de BAM (con las tablas de base de datos y vistas de los datos) de metadatos e interfaces de propietarias para el cuerpo del mensaje|Interfaz de usuario BAM o interfaz de usuario personalizada|  
|Errores y eventos|A través de la [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos|Registro de eventos|  
|Datos sin repudio|A través de interfaces propietarios (formatos de los mensajes se almacenan el cable)|Tabla MessageStorageIn y MessageStorageOut de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos de archivo y a través del SDK|  
  
## <a name="process-and-message-tracking"></a>Proceso y seguimiento de mensajes  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]realiza un seguimiento de dos actividades básicas: la actividad del proceso y la actividad de mensaje. La actividad del proceso realiza un seguimiento de procesamiento de mensajes en orquestaciones de proceso público. El mensaje hace un seguimiento de la actividad de procesamiento de envío o canalizaciones de recepción.  
  
 La actividad del proceso realiza un seguimiento de los metadatos de mensaje completo. Realiza un seguimiento de la actividad de mensaje de metadatos de actividad de proceso y el contenido del mensaje.  
  
### <a name="process-activity"></a>Actividad de proceso  
 Cada vez que se crea una instancia de una orquestación de proceso público (iniciador o el servicio de respuesta), el proceso público crea un registro de actividad de los procesos en la base de datos de seguimiento de BAM. En diversos puntos en el proceso público, la orquestación guarda los metadatos de seguimiento. La actividad del proceso se detiene cuando se detiene la orquestación.  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]realiza un seguimiento complete metadatos para el proceso en dos instancias:  
  
-   Cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es un servicio de respuesta y recibe un mensaje de acción de solicitud  
  
-   Cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es un iniciador y recibe un mensaje de solicitud de la aplicación de línea de negocio (LOB).  
  
 Cada vez que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía o recibe un mensaje, el proceso público actualiza el estado de la actividad del proceso.  
  
### <a name="message-activity"></a>Actividad de mensaje  
 La actividad de mensaje realiza un seguimiento de mensajes a través del envío y las canalizaciones de recepción. Cada vez que un envío o la canalización de recepción procesa un mensaje, la canalización crea una actividad de mensaje. La canalización crea un registro de actividad de mensaje en la base de datos y un registro de mensajes de seguimiento de BAM el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos de archivo.  
  
 La actividad de mensaje guarda el contenido del mensaje, incluidos los encabezados y contenido del servicio. En la canalización de recepción, si el descodificador de MIME se realiza correctamente, la actividad guarda las cuatro partes del contenido del mensaje como XML en formato de texto en la columna ContentXml de la tabla MessageContent. Si se produce un error en el descodificador de MIME, la actividad guarda el contenido del mensaje en formato binario en la columna ContentBinary de la tabla MessageContent.  
  
### <a name="use-of-tracking-data-in-correlation"></a>Uso de datos de correlación de seguimiento  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]realiza un seguimiento de la información necesaria para poner en correlación cada proceso para todos los mensajes intercambiados para una PIP específica (señales positivas o negativas y las señales de solicitud y respuesta). También hace un seguimiento la información que se usa para correlacionar un mensaje 0A1, si [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía una notificación de error para esa PIP. La combinación de los Id. de instancia PIP, el nombre de entidad de iniciador y el nombre de la entidad de destino determinan los mensajes relacionados con una actividad.  
  
### <a name="tracking-databases"></a>Bases de datos de seguimiento  
 Las actividades de proceso y mensaje guardar metadatos en el BAMPrimaryImport de seguimiento [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos. En esta base de datos, tablas cuyos nombres empiezan por el prefijo "bam_Process" almacenan los datos de seguimiento de actividad de los procesos y las tablas cuyos nombres empiezan por el prefijo "bam_Message" almacenan los datos de seguimiento de actividad de mensaje. Cada proceso independiente o una actividad de mensaje tiene un único registro correspondiente en las tablas. Información sobre las dos actividades y seguimiento de metadatos, se incluye en las tablas de metadatos cuyos nombres empiezan por el prefijo "bam_Metadata".  
  
 Puede consumir los datos en la base de datos de seguimiento BAMPrimaryImport mediante las siguientes vistas. Estas y otras vistas están disponibles en la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nodo de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración.  
  
|Vista de seguimiento|data|  
|-------------------|----------|  
|bam_Process_AllInstances|Estado del proceso de RosettaNet definido el PIP|  
|bam_Message_AllInstances|Estados de todos los mensajes|  
|bam_Process_CompletedInstances|Estado de procesos completados|  
  
 La actividad de mensaje guarda el contenido del mensaje en la tabla MessageContent de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos de archivo. Puede examinar el contenido mediante la ejecución de una consulta en la tabla MessageContent, utilizando el identificador único para el mensaje. La actividad almacena el identificador único de la columna ContentKey de la actividad de mensaje de tablas de seguimiento, con el prefijo "bam_Message.  
  
> [!IMPORTANT]
>  La actividad de mensaje comparte el contenido del mensaje en texto no cifrado en la tabla MessageContent de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos de archivo. Esto sucede en todos los escenarios de seguimiento, incluidos aquellos en los que los mensajes están cifrados o firmados. Si le preocupa la accesibilidad del contenido del mensaje, puede restringir el acceso a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos de archivo.  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]usa la API de seguimiento de BAM para guardar los datos de seguimiento.  
  
### <a name="status-codes"></a>Códigos de estado  
 Las tablas bam_Process_Active y bam_Process_Completed en la base de datos BAMPrimaryImport incluyen una columna de estado que indica el estado del proceso. En la tabla siguiente se muestra los valores para cada código de estado.  
  
|Código de estado|Estado del proceso|  
|-----------------|-------------------|  
|-1000|ActivityNotPresentFatalError|  
|-500|UnexpectedFatalError|  
|-100|Initiated0A1|  
|-99|TerminatedOnError<br /> (Cualquier otra conclusión de terminar con 0A1)|  
|-85|TerminatedBy0A1|  
|-75|TimedOutOnResponseSignal|  
|-50|TimedOutOnResponse|  
|-25|TimedOutOnActionSignal|  
|0|RegisteredActivity|  
|1|ActivityToBeInitiated|  
|10|ReceivedAction o SentAction|  
|25|ReceivedActionSignal o SentActionSignal|  
|35|ReceivedActionSignal2 o SentActionSignal2<br /> (Señal 2 está destinado a RNIF v11)|  
|50|ReceivedResponse o SentResponse|  
|75|ReceivedResponseSignal o SentResponseSignal|  
|85|ReceivedResponseSignal2 o SentResponseSignal2<br /> (Señal 2 está destinado a RNIF v11)|  
|100|ActivityCompleted|  
  
### <a name="activity-definition-file"></a>Archivo de definición de actividad  
 El archivo de definición de actividad define los campos que realizan el seguimiento de BAM, y cómo verlos. Para obtener más información acerca de este archivo, consulte [trabajar con el archivo de definición de actividad de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/working-with-the-tracking-activity-definition-file.md).  
  
 Para obtener más información acerca de BAM, vea "actividad supervisión económica (BAM)" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con el archivo de definición de actividad de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/working-with-the-tracking-activity-definition-file.md)   
 [Lo que agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)