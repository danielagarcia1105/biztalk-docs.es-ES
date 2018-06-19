---
title: AS2 Mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fac8418-3c07-4513-94aa-e7a25087d789
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d54d05a459eb6fef772add6d4bb77f0269fa0ba8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008069"
---
# <a name="as2-messages"></a>Mensajes AS2
En este tema se describe un mensaje AS2, incluida su estructura, propiedades de contexto y encabezados.  
  
## <a name="structure-of-an-as2-message"></a>Estructura de un mensaje AS2  
 En BizTalk Server, mensajes de AS2 se estructuran de acuerdo con [RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/? LinkID = 184212](http://go.microsoft.com/fwlink/?LinkID=184212)).  
  
 La estructura básica de un mensaje AS2 está compuesta de formato MIME dentro de un mensaje HTTP con encabezados específicos de AS2 adicionales. La naturaleza del mensaje bajo los encabezados HTTP, AS2 y MIME depende del tipo de mensaje:  
  
-   **Firmado** : si el mensaje está firmado, se agrega un contenedor de firma en la carga de documentos.  
  
-   **Comprimido** : si el mensaje se comprime, se agrega un contenedor de compresión en las cargas de firmas y documentos.  
  
-   **Cifra** : si el mensaje está cifrado, se agrega un contenedor de cifrado en las cargas de documento, la firma y compresión.  
  
 La estructura de mensaje de un mensaje AS2, que se basa en el cifrado, firma y compresión, se muestra en la siguiente tabla.  
  
|Opciones de los mensajes AS2|Estructura del mensaje|  
|-------------------------|-----------------------|  
|-No hay compresión<br /><br /> -Sin cifrado<br /><br /> -No hay ninguna firma|`HTTP, AS2, MIME Header      EDI/XML Payload`|  
|-Comprimido<br /><br /> -Sin cifrado<br /><br /> -No hay ninguna firma|`HTTP, AS2, MIME Header      PKCS7-MIME Compression           EDI/XML Payload (compressed)`|  
|-Firmado<br /><br /> -No hay compresión<br /><br /> -Sin cifrado|`HTTP, AS2, MIME Header       MIME Security Multipart (signed)           EDI/XML Payload           CMS-PKCS7 Signature`|  
|-Firmado<br /><br /> -Comprimido<br /><br /> -Sin cifrado|`HTTP, AS2, MIME Header       PKCS7-MIME Compression           MIME Security Multipart (signed)(compressed)                EDI/XML Payload (compressed)                CMS-PKCS7 Signature (compressed)`|  
|-Cifrado<br /><br /> -No hay compresión<br /><br /> -No hay ninguna firma|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           EDI/XML Payload (encrypted)`|  
|-Comprimido<br /><br /> -Cifrado<br /><br /> -No hay ninguna firma|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                EDI/XML Payload (compressed)(encrypted)`|  
|-Cifrado<br /><br /> -Firmado<br /><br /> -No hay compresión|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           MIME Security Multiparts (signed)(encrypted)                EDI/XML Payload (encrypted)                CMS-PKCS7 Signature (encrypted)`|  
|-Comprimido<br /><br /> -Cifrado<br /><br /> -Firmado|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                MIME Security Multiparts (signed)(compressed)(encrypted)                     EDI/XML Payload (compressed)(encrypted)                     CMS-PKCS7 Signature (compressed)(encrypted)`|  
  
 Si la carga de documento consta de varios documentos, se almacenan dentro de un sobre MIME multiparte/relacionado como se describe en RFC 2387. Se puede usar un encabezado MIME Content-Disposition para especificar el nombre de archivo de cada documento del mensaje.  
  
 En la siguiente tabla se muestra la estructura de mensaje de un mensaje AS2 que contiene varios datos adjuntos, en función de las opciones de cifrado, firma y compresión del mensaje.  
  
|Opciones de los mensajes AS2|Estructura del mensaje|  
|-------------------------|-----------------------|  
|-No hay compresión<br /><br /> -Sin cifrado<br /><br /> -No hay ninguna firma|`HTTP, AS2, MIME Header      MIME Multipart/related           EDI/XML Payloads`|  
|-Comprimido<br /><br /> -Sin cifrado<br /><br /> -No hay ninguna firma|`HTTP, AS2, MIME Header      PKCS7-MIME Compression           MIME Multipart/related                EDI/XML Payload (compressed)`|  
|-Firmado<br /><br /> -No hay compresión<br /><br /> -No hay ninguna firma|`HTTP, AS2, MIME Header       MIME Security Multipart (signed)           MIME Multipart/related                EDI/XML Payload           CMS-PKCS7 Signature`|  
|-Comprimido<br /><br /> -Firmado<br /><br /> -Sin cifrado|`HTTP, AS2, MIME Header       PKCS7-MIME Compression           MIME Security Multipart (signed)(compressed)                MIME Multipart/related (compressed)                     EDI/XML Payload (compressed)                CMS-PKCS7 Signature (compressed)`|  
|: Cifrado<br /><br /> -No hay compresión<br /><br /> -No hay ninguna firma|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           MIME Multipart/related (encrypted)                EDI/XML Payload (encrypted)`|  
|-Comprimido<br /><br /> -Cifrado<br /><br /> -No hay ninguna firma|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                MIME Multipart/related                     EDI/XML Payload (compressed)(encrypted)`|  
|-Cifrado<br /><br /> -Firmado<br /><br /> -No hay compresión|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           MIME Security Multiparts (signed)(encrypted)                MIME Multipart/related                     EDI/XML Payload (encrypted)                CMS-PKCS7 Signature (encrypted)`|  
|-Comprimido<br /><br /> -Cifrado<br /><br /> -Firmado|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                MIME Security Multiparts (signed)(compressed)(encrypted)                     MIME Multipart/related                          EDI/XML Payload (compressed)(encrypted)                     CMS-PKCS7 Signature (compressed)(encrypted)`|  
  
## <a name="as2-context-properties"></a>Propiedades de contexto de AS2  
 Las propiedades de contexto utilizadas en el procesamiento de los mensajes AS2 tienen propiedades que se pueden promocionar y propiedades que no se exponen públicamente, pero se pueden ver en los mensajes de seguimiento o suspendidos. Para obtener una lista de propiedades de contexto de AS2, vea [propiedades de contexto AS2](../core/as2-context-properties.md).  
  
## <a name="as2-headers"></a>Encabezados AS2  
 Los encabezados AS2 en mensajes AS2 describen las entidades de envío y recepción, y proporcionan la información que necesita la entidad de recepción para enviar una respuesta MDN. La entidad de recepción usará los encabezados MDN a menos que la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad está seleccionada en el acuerdo de AS2, o si la información no está disponible en el acuerdo Propiedades.  
  
 Las propiedades de contexto de encabezado AS2-From, encabezado AS2-To y MessageID describen de forma exclusiva un mensaje AS2. También se usan para correlacionar un MDN en el mensaje AS2 al que se está respondiendo.  
  
 Estos encabezados se enumeran (en orden alfabético) en la siguiente tabla:  
  
|Encabezado AS2|Opcional/Requerido|Valores|  
|----------------|------------------------|------------|  
|AS2-Version|Opcional|"1.1"|  
|AS2-From|Necesario|Nombre de la compañía que envió el mensaje AS2.<br /><br /> Valores: cadena, ASCII imprimible, de 1 a 128 caracteres de longitud|  
|AS2-To|Necesario|Nombre de la compañía a la que se envió el mensaje AS2.<br /><br /> Valores: cadena, ASCII imprimible, de 1 a 128 caracteres de longitud|  
|AS2-Text|Necesario|Text (en este encabezado del mensaje)<br /><br /> Valores: cadena, ASCII imprimible, de 1 a 128 caracteres de longitud|  
|Disposition-Notification-To|Necesario|Cuando esté presente, sirve como solicitud para un MDN que se va a devolver. Si se acompaña mediante un encabezado Receipt-Delivery-Option, se trata de una solicitud para un MDN asíncrono. Si no es así, se trata de una solicitud para un MDN sincrónico.<br /><br /> Cuando no esté presente, no será necesario un MDN.<br /><br /> Valor: debe estar presente una dirección de correo electrónico. Sin embargo, la dirección no debe utilizarse para identificar el lugar en el que devolver el MDN. La aplicación de recepción debe ignorar la dirección de correo electrónico y no debe informar de infracciones en la sintaxis de la dirección.|  
|EDIINT-Features|Necesario|Indica las características admitidas por el sistema de origen. BizTalk utiliza este encabezado para indicar la compatibilidad con varios datos adjuntos.<br /><br /> Valor: “MA”|  
|Receipt-Delivery-Option|Necesario|Indica la URL a la que se debe enviar el MDN. Cuando Receipt-Delivery-Option está presente, Disposition-notification-to sirve como solicitud para un MDN asíncrono. Receipt-Delivery-Option debe estar siempre acompañada de Disposition-Notification-To.<br /><br /> Cuando Receipt-Delivery-Option no está presente y Disposition-notification-to sí lo está, Disposition-notification-to sirve como solicitud para un MDN sincrónico.<br /><br /> Valores: una cadena URL.|  
|signed-receipt-protocol<br /><br /> (en Disposition-Notification-Options)|Opcional|Cuando se establece en "pcks7-signature", se usa para solicitar una recepción firmada a partir de la entidad de recepción e indica el formato en el que la recepción firmada debe devolverse al solicitante.<br /><br /> Valores: opcional, pcks7-signature|  
|signed-receipt-micalg<br /><br /> (en Disposition-Notification-Options)|Opcional|Una lista de algoritmos MIC preferida por el solicitante para usarla en la firma de la recepción devuelta. La entidad de recepción debe respetar la lista de algoritmos de izquierda a derecha.<br /><br /> Valores: opcional, MD5 o SHA1|  
  
 Para mensajes entrantes, las canalizaciones de recepción AS2EdiReceive y AS2Receive validan los valores del protocolo de recepción firmada y el algoritmo MIC de recepción firmada de las propiedades del acuerdo AS2.  
  
 Para los mensajes AS2 salientes, las canalizaciones de envío AS2EdiSend y AS2Send rellenan los encabezados AS2 anteriores a partir de los valores especificados en el acuerdo de AS2 (con la excepción de AS2-Version, que está codificada como 1.1).  
  
 **Solicitud de MDN**  
  
 Se solicita que la entidad de recepción devuelva un MDN (Message Disposition Notification) mediante la colocación del siguiente encabezado en el mensaje que se va a enviar:  
  
 MDN-request-header = "Disposition-notification-to"  ":"  mail-address  
  
 La dirección de correo no se utiliza para identificar el lugar en el que devolver el MDN. Las aplicaciones de recepción deben ignorar el valor y no registrar un error sobre las infracciones en la sintaxis de la dirección.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes MDN](../core/mdn-messages.md)