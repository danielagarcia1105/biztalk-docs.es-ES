---
title: Las actividades BAM creadas para realizar un seguimiento de mensajes EDI-AS2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a10ab846-0fbb-46f5-920e-cb2b5be75814
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f255f2bb71ecef857860fdd5c512f4320b35cc95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-activities-created-to-track-edi-as2-messages"></a>Actividades BAM creadas para realizar un seguimiento de mensajes EDI-AS2
[!INCLUDE[prague](../includes/prague-md.md)] incluye actividades de BAM que se han creado para los informes de estado de EDI y AS2. Estas actividades determinan los datos que se muestran en los informes de estado. En este tema se explican las actividades de BAM y los campos definidos en ellas, además de describir los valores de enumeración definidos para ciertos campos en las actividades de BAM.  
  
 Se puede crear un informe de estado personalizado mediante la creación de una actividad de BAM. La actividad personalizada se puede basar en una de las actividades estándar. También se puede mostrar el contenido del mensaje del informe de estado personalizado consultando la tabla EdiMessageContent en la base de datos BizTalkDTADb. Para obtener más información, vea la sección "Consultar la tabla EdiMessageContent" abajo.  
  
> [!CAUTION]
>  La modificación de una actividad de BAM puede afectar al procesamiento de los tiempos de ejecución de EDI y AS2 de BizTalk, que dependen de las actividades.  
  
## <a name="bam-activities-used-in-status-reporting"></a>Actividades de BAM usadas en los informes de estado  
 Las actividades de BAM creadas para realizar el seguimiento de los mensajes EDI/AS2 se incluyen como vistas en la base de datos BAMPrimaryImport. En la tabla siguiente se enumeran las actividades de BAM y las columnas que contienen.  
  
|Actividad de BAM|Campos|  
|------------------|------------|  
|AS2InterchangeActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Dirección<br /><br /> MessageID<br /><br /> AS2From<br /><br /> AS2To<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|AS2MdnActivity|RecordID<br /><br /> ActivityID<br /><br /> AS2PartyRole<br /><br /> AS2From<br /><br /> AS2To<br /><br /> MessageID<br /><br /> MdnDateTime<br /><br /> MdnDispositionType<br /><br /> DispositionModifierExtType<br /><br /> DispositionModifierExtDescription<br /><br /> MdnEncryptionType<br /><br /> MdnSignatureType<br /><br /> MdnPayloadContentKey<br /><br /> MdnWireContentKey<br /><br /> MdnMicValue<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|AS2MessageActivity|RecordID<br /><br /> ActivityID<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> AS2PartyRole<br /><br /> AS2From<br /><br /> AS2To<br /><br /> MessageID<br /><br /> MessageDateTime<br /><br /> BTSInterchangeID<br /><br /> BTSMessageID<br /><br /> MdnProcessingStatus<br /><br /> MessageEncryptionType<br /><br /> IsMdnExpected<br /><br /> MicAlgorithmType<br /><br /> MessageSignatureType<br /><br /> MessagePayloadContentKey<br /><br /> MessageWireContentKey<br /><br /> MessageMicValue<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> IsAS2MessageDuplicate<br /><br /> DaysToCheckDuplicate<br /><br /> FileName<br /><br /> TrackingActivityID<br /><br /> LastModified|  
|BatchingActivity|RecordID<br /><br /> ActivityID<br /><br /> BatchStatus<br /><br /> DestinationPartyID<br /><br /> DestinationPartyName<br /><br /> ActivationTime<br /><br /> BatchOccurrenceCount<br /><br /> EdiEncodingType<br /><br /> BatchType<br /><br /> TargetedBatchCount<br /><br /> ScheduledReleaseTime<br /><br /> BatchElementCount<br /><br /> RejectedBatchElementCount<br /><br /> BatchSize<br /><br /> LastBatchAction<br /><br /> CreationTime<br /><br /> ReleaseTime<br /><br /> BatchReleaseType<br /><br /> BatchServiceID<br /><br /> ActivationMessageID<br /><br /> ReleaseMessageID<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> BatchCorrelationID<br /><br /> BatchName<br /><br /> BatchID<br /><br /> LastModified|  
|BatchInterchangeActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Dirección<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> BatchCorrelationID<br /><br /> LastModified|  
|BusinessMessageJournal|RecordID<br /><br /> ActivityID<br /><br /> MessageTrackingID<br /><br /> ActionType<br /><br /> ContainerActivityID<br /><br /> ContainerType<br /><br /> BTSInterchangeID<br /><br /> BTSMessageId<br /><br /> BTSServiceInstanceId<br /><br /> BTSHostName<br /><br /> RoutedToPartyName<br /><br /> LinkedMessageTrackingID<br /><br /> TimeCreated<br /><br /> LastModified|  
|FunctionalAckActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeActivityID<br /><br /> GroupControlNo<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Dirección<br /><br /> AckProcessingStatus<br /><br /> AckStatusCode<br /><br /> DeliveredTSCount<br /><br /> AcceptedTSCount<br /><br /> AckIcn<br /><br /> AckIcnDate<br /><br /> AckIcnTime<br /><br /> ErrorCode1<br /><br /> ErrorCode2<br /><br /> ErrorCode3<br /><br /> ErrorCode4<br /><br /> ErrorCode5<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|FunctionalGroupInfo|RecordID<br /><br /> ActivityID<br /><br /> InterchangeActivityID<br /><br /> GroupControlNo<br /><br /> FunctionalIDCode<br /><br /> TSCount<br /><br /> LastModified|  
|InterchangeAckActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Dirección<br /><br /> AckProcessingStatus<br /><br /> AckStatusCode<br /><br /> AckIcn<br /><br /> AckIcnDate<br /><br /> AckIcnTime<br /><br /> AckNoteCode1<br /><br /> AckNoteCode2<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> AckCorrelationId<br /><br /> LastModified|  
|InterchangeStatusActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> InterchangeDateTime<br /><br /> Dirección<br /><br /> AckStatusCode<br /><br /> GroupCount<br /><br /> EdiMessageType<br /><br /> PortID<br /><br /> IsInterchangeAckExpected<br /><br /> IsFunctionalAckExpected<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> AckCorrelationId<br /><br /> TsCorrelationId<br /><br /> LastModified|  
|ResendJournalActivity|RecordID<br /><br /> ActivityID<br /><br /> TrackingActivityId<br /><br /> ResendIndex<br /><br /> ResendStatus<br /><br /> BTSInterchangeID<br /><br /> LastModified|  
|ResendTrackingActivity|RecordID<br /><br /> ActivityID<br /><br /> CorrelationId<br /><br /> AdapterPrefix<br /><br /> ResendCount<br /><br /> MaxResendCount<br /><br /> ResendInterval<br /><br /> MaxRetryCount<br /><br /> RetryInterval<br /><br /> MessageContentID<br /><br /> ResendTimeout<br /><br /> RetryTimeout<br /><br /> BTSInterchangeID<br /><br /> LastModified|  
|TransactionSetActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Dirección<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> ApplicationSender<br /><br /> ApplicationReceiver<br /><br /> GroupDateTime<br /><br /> GroupControlNo<br /><br /> TransactionSetId<br /><br /> DocType<br /><br /> TransactionSetControlNo<br /><br /> AckStatusCode<br /><br /> BatchProcessing<br /><br /> ProcessingDateTime<br /><br /> GroupOrdinal<br /><br /> TransactionSetOrdinal<br /><br /> MessageContentKey<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> TsCorrelationId<br /><br /> LastModified|  
  
## <a name="data-enumerations-in-the-bamprimaryimport-database"></a>Enumeraciones de datos en la base de datos BAMPrimaryImport  
 Algunos datos EDI y AS2 se guardan como enumeraciones en las tablas de la base de datos BAMPrimaryImport. Cuando se muestran en el informe de estado, los datos se muestran como texto. Estos valores son los siguientes:  
  
|Campo|Valores de enumeración|  
|-----------|-----------------|  
|AckProcessingStatus|NotExpected = -1<br /><br /> Se esperaba = 0<br /><br /> Received = 1<br /><br /> Enviados = 2<br /><br /> Generated = 3|  
|AS2PartyRole|All = 0<br /><br /> Receiver = 1<br /><br /> Sender = 2|  
|BatchAction|Creation = 0<br /><br /> Activation = 1<br /><br /> ElementReference = 2<br /><br /> Release = 3<br /><br /> Override = 4<br /><br /> Termination = 5<br /><br /> Sent = 6<br /><br /> ToBeReleased = 7|  
|BatchStatus|Todos los = -1<br /><br /> Defined = 0<br /><br /> Activo<br /><br /> Released<br /><br /> Completado|  
|BatchType|ScheduleBased = 0<br /><br /> MessagesCountInGroup = 1<br /><br /> MessagesCountIn<br />Intercambio = 2<br /><br /> CharacterCount = 3<br /><br /> ExternalTrigger = 4|  
|Dirección|All = 0<br /><br /> Receive = 1<br /><br /> Send = 2|  
|DisplayAckStatusCode|Todos los = 100<br /><br /> Accepted = 0<br /><br /> PartiallyAccepted = 1<br /><br /> Rejected = -1<br /><br /> AckExpected = 500<br /><br /> AckNotExpected = 600|  
|DispositionModifierExt<br />Description|Not Valued = 1<br /><br /> Authentication Failed = 2<br /><br /> Decryption Failed = 3<br /><br /> Mensaje insuficiente<br />Seguridad = 4<br /><br /> Integrity Check Failed = 5<br /><br /> Procesamiento inesperado <br />Error = 6|  
|DispositionModifierExt<br />Tipo|Not Valued = 1<br /><br /> Error = 2<br /><br /> Warning = 3|  
|EdiMessageType|X12,<br /><br /> Edifact,<br /><br /> Desconocido|  
|IsMdnExpected|MDN is not expected = 0<br /><br /> MDN is expected = 1|  
|MdnDispositionType|Processed = 1<br /><br /> Failed = 2|  
|MdnProcessingStatus|All = 0<br /><br /> Processed = 1<br /><br /> Failed = 2<br /><br /> Expected = 3<br /><br /> Not Expected = 4|  
|MessageEncryptionType|Message is not encrypted = 0<br /><br /> Message is encrypted = 1|  
|MessageSignatureType|Message is not signed = 0<br /><br /> Message is signed = 1|  
|MicAlgorithmType|Unknown type = -1<br /><br /> SHA1 = 1<br /><br /> MD5 = 2|  
  
## <a name="businessmessagejournal-bam-activity"></a>Actividad de BAM BusinessMessageJournal  
 La actividad de BAM BusinessMessageJournal permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] correlacione un intercambio EDI recibido que contenga un conjunto de transacciones con un intercambio por lotes saliente que contenga el mismo conjunto de transacciones. Para obtener más información, consulte [correlacionar un conjunto de transacciones entrante con un lote saliente](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md).  
  
##  <a name="BKMK_Query"></a>Consultar la tabla EdiMessageContent  
 La tabla EdiMessageContent de la base de datos BizTalkDTADb almacena la carga de mensajes, junto con los metadatos de mensajes. A partir de un informe de estado personalizado, puede consultar la tabla EdiMessageContent para ver el contenido del mensaje. Se asemeja al modo en que algunos informes de estado del producto permiten ver el contenido del mensaje, por ejemplo, el modo en que el informe Mensaje AS2 y estado de MDN correlacionado permiten ver el formato del mensaje.  
  
 Se vincula una actividad de BAM personalizada con la tabla EdiMessageContent mediante las columnas de clave de la actividad de BAM que corresponden a la columna ContentKey de la tabla EdiMessageContent. Por ejemplo, para vincular la actividad de BAM AS2MessageActivity con la tabla EdiMessageContent, se usaría la columna MessagePayloadContentKey o la columna MessageWireContentKey para establecer el vínculo a la columna ContentKey.  
  
|Tabla|Columnas|  
|-----------|-------------|  
|EdiMessageContent<br /><br /> (en la base de datos BizTalkDTADb)|ContentKey<br /><br /> MessageFormat<br /><br /> ContentType<br /><br /> Charset<br /><br /> TimeCreated<br /><br /> TimeInserted<br /><br /> IsOrphaned<br /><br /> ContentBinary|  
  
## <a name="see-also"></a>Vea también  
 [Cómo se almacenan los datos para informes de estado de AS2 y EDI](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)   
 [Correlacionar un conjunto de transacciones entrante con un lote saliente](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)