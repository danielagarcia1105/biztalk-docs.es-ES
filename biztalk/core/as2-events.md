---
title: AS2 Eventos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9de140d-8961-4c19-a2e5-14631016541f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 824fda0d49ddfd9c5d6f6c12a379568775b8d160
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233596"
---
# <a name="as2-events"></a>Eventos de AS2
La tabla siguiente lista mensajes de eventos que se pueden publicar en el registro de eventos durante el procesamiento de AS2.  
  
> [!NOTE]
>  Para obtener más información acerca de los errores de AS2 enumerados en la tabla siguiente, vea [eventos EDI y AS2](../core/edi-and-as2-events.md).  
  
|Código de error|Condición|  
|----------------|---------------|  
|AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError|El descodificador AS2 no ha podido localizar el encabezado HTTP Disposition-Notification-Options necesario para la generación de MDN.|  
|SynchronousMdnRequestedOnOneWayReceivePortError|Error de configuración.  MDN sincrónico solicitado en puerto de recepción HTTP unidireccional.|  
|SynchronousMdnRequestedOnOneWaySendPortError|Error de configuración.  MDN sincrónico solicitado en puerto de envío HTTP unidireccional.|  
|EncryptionCertNotConfiguredError|El certificado de cifrado no se ha configurado para la entidad AS2.  AS2-de: {0} AS2-a: {1}|  
|AS2DecoderPartySigningConfigurationError|Error de configuración.  La firma del mensaje no coincide con el valor esperado.  Póngase en contacto con el socio remitente y verifique el uso de la firma.  AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}"|  
|AS2DecoderExceptionEncounteredDuringProcessing|El descodificador AS2 detectó una excepción durante el procesamiento.  Detalles del mensaje y excepción son los siguientes: AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}" MessageType: "{3}" excepción: "\ {4\}"|  
|AS2DecoderMdnMicFailureDuringProcessing|Error de procesamiento de descodificador AS2 al validar el valor MIC devuelto en MDN.  Detalles del mensaje MDN son los siguientes: AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}" OriginalMessageID: "\ {3\}"|  
|AS2DecoderMdnSigningMismatchFailureDuringProcessing|Error de procesamiento de descodificador AS2. La firma MDN no cumplía nuestra solicitud.  Detalles del mensaje MDN son los siguientes: AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}" OriginalMessageID: "\ {3\}"|  
|AS2DecoderMdnProcessingFailureReturned|Error de procesamiento de descodificador AS2. MDN indicó un error de procesamiento del mensaje AS2.  Detalles del mensaje MDN son los siguientes: AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}" OriginalMessageID: "\ {3\}"|  
|AS2InvalidQuotedStringHeaderError|Se detectó un encabezado HTTP entre comillas no válido.  Detalles son los siguientes: nombre de encabezado: valor de encabezado "{0}": "{{1}"|  
|AS2MicDataStoreDuplicateMicError|La entrada Mic de error ya existe.|  
|AS2StreamingNonSeekableStreamError|Esta secuencia no permite búsquedas.|  
|AS2StreamingSetLengthError|No se puede definir la longitud de esta secuencia.|  
|AS2StreamingWriteToReadonlyStreamError|Esta secuencia es de sólo lectura.|  
|AS2StreamingMethodNotImplementedError|y que no se ha implementado la operación o el método.|  
|BtsMimeExceptionEncounteredDuringMessageDecoding|Error de BTS MIME al intentar descodificar un mensaje AS2.  AS2-de: {0}, AS2-a: {1}, MessageId: {2}, Error: {3}|  
|AS2DecoderPartyEncryptionConfigurationError|Error de configuración.  El cifrado del mensaje no coincide con el valor esperado.  Póngase en contacto con el socio remitente y verifique el uso del cifrado.  AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}"|  
|AS2DecoderPartySignatureError|Error de configuración.  La firma del mensaje no coincide con la firma configurada para esta entidad.  Póngase en contacto con el socio remitente y verifique el certificado utilizado.  AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}"|  
|InvalidAgreementAS2FromName|La entidad de este intercambio AS2 debe contener un valor AS2-From.|  
|InvalidAgreementAS2ToName|La entidad de este intercambio AS2 debe contener un valor para AS2-To.|  
|UnsupportedAS2HashAlgorithmError|El algoritmo de hash especificado en el mensaje AS2 no es compatible.|  
|UnableToLocateAS2PartyError|No se puede a la entidad de acceso usando el calificador: entidad de {0}: {1}.  Error: {2}|  
|UnableToLocateAS2PartyByPartyNameError|No se puede obtener acceso a entidad usando la entidad: {0}.|  
|UnableToLocateAS2PartyBySendPortNameError|No se puede obtener acceso a la entidad usando el puerto de envío: {0} Error: {1}.|  
|InvalidAS2FromNameConfiguredError|AS2 no válido: nombre configurado para la entidad: {0} valor: {1}|  
|InvalidAS2ToNameConfiguredError|AS2 no válido: nombre configurado para la entidad: {0} valor: {1}|  
|InvalidAS2FromNameHeaderReceivedError|Encabezado AS2-From no válido recibido.  Valor: {0}|  
|InvalidAS2ToNameHeaderReceivedError|Encabezado AS2-To recibido.  Valor: {0}|  
|MissingAS2FromHeaderError|Se recibió un mensaje AS2 sin el encabezado AS2-From.|  
|MissingAS2ToHeaderError|Se recibió un mensaje AS2 que no contenía AS2-al encabezado.|  
|InvalidDispositionNotificationOptionToError|Valor de disposition-Notification-Option: "{0}" no es válido.  {1}|  
|InvalidReceiptDeliveryOptionError|Valor Receipt-Delivery-Option: "{0}" no es válido.  {1}|  
|InvalidOrMissingASN1DataLengthHeader|Campo de longitud de datos ASN.1 ausente o no válido detectado durante el proceso de descompresión.|  
|InvalidOrMissingASN1TrailingBytes|Bytes de estructura comprimida ASN.1 CMS ausentes o no válidos detectados durante el proceso de descompresión.|  
|InvalidASN1CompressedStructureEncountered|ASN.1 comprimido no válido detectado durante el proceso de descompresión.|  
|InvalidOrMissingDataHeaderEncountered|Encabezado comprimido ASN.1 ausente o no válido detectado durante el proceso de descompresión.|  
|InvalidOptionalZLibFieldEncountered|Campo de compresión ASN.1 ZLib no válido detectado durante el proceso de descompresión.|  
|InvalidOrMissingDataOIDEncountered|OID de datos ASN.1 ausente o no válido detectado durante el proceso de descompresión.|  
|InvalidOrMissingZLibOIDEncountered|OID ASN.1 ZLib ausente o no válido detectado durante el proceso de descompresión.|  
|InvalidOrMissingCompressedDataOIDEncountered|OID de datos comprimidos ASN.1 ausente o no válido detectado durante el proceso de descompresión.|  
|InvalidAdler32ChecksumInCompressedMessageError|La suma de comprobación Adler32 encontrada no es válida.|  
|UnsupportedOctetStringLengthEncountered|Longitud de cadena de bytes no admitida.  La longitud máxima de bytes es 4.|  
|DecompressionFailedError|Error de descompresión al procesar un mensaje AS2 comprimido.  Error: {0}|  
|DecryptionFailedError|Error al descifrar un mensaje AS2.|  
|IntegrityCheckFailedError|Se produjo un error al validar un mensaje AS2.  Asegúrese de que los certificados no han caducado ni se han revocado.|  
|EncryptionCertificateHasBeenRevokedError|El certificado utilizado para cifrar un mensaje se ha revocado. Huella digital del certificado: {0}|  
|DecryptionCertificateHasBeenRevokedError|Se ha revocado el certificado usado para descifrar un mensaje. Huella digital del certificado: {0}|  
|SigningCertificateHasBeenRevokedError|El certificado usado para firmar un mensaje se ha revocado. Huella digital del certificado: {0}|  
|SignatureCertificateHasBeenRevokedError|El certificado usado para firmar un mensaje se ha revocado. Huella digital del certificado: {0}|  
|CertificateMissingError|El certificado usado para firmar un mensaje no puede ubicarse en el almacén local de certificados. Huella digital del certificado: {0}|  
|EmptyContentOnAS2MessageEncountered|Se recibió un mensaje AS2 vacío.  El mensaje se suspenderá.|  
|AS2FromMatchesAS2ToError|El valor AS2-From coincide con el valor AS2-To.|  
|GenericEdiIntException|Se ha producido una excepción EdiInt.|  
|BtsMimeExceptionEncounteredDuringMessageEncoding|Error de BTS MIME al intentar codificar un mensaje.  Error: {0}, HResult: \ {1\\}|  
|BtsMimeGeneralExceptionEncounteredDuringMessageEncoding|Error de BTS MIME al intentar codificar un mensaje.  Error: {0}|  
|AS2StatusReportingExceptionEncountered|Error al intentar generar un informe de estado AS2.  Error: {0}|