---
title: AS2 Propiedades de contexto | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4d63104-f31e-4ed2-b294-ba3ea8a39ae6
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03897ce3bd74329a19d85d48b3704f551122d272
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="as2-context-properties"></a>Propiedades de contexto de AS2
Cinco tipos de propiedades de contexto que se aplican a los mensajes de AS2 en BizTalk Server:  
  
-   Propiedades de contexto del esquema EdiIntProperties.xsd  
  
-   Propiedades de contexto internas con respecto a BizTalk Server  
  
-   Propiedades de contexto internas con respecto a MIME de BizTalk  
  
-   Propiedades de contexto internas con respecto a AS2  
  
-   Propiedades de contexto internas con respecto a informes de estado de AS2  
  
## <a name="context-properties-in-the-ediintpropertiesxsd-schema"></a>Propiedades de contexto del esquema EdiIntProperties.xsd  
 Las propiedades de contexto del mensaje del esquema de propiedades global de EDI/INT están expuestas públicamente, lo que permite que los usuarios las utilicen en operaciones como el enrutamiento de mensajes. Estas propiedades de contexto se definen en EdiIntProperties.xsd en el ensamblado `Microsoft.BizTalk.Edi.BaseArtifacts`. El espacio de nombres para las propiedades es `http://schemas.microsoft.com/BizTalk/2006/as2-properties`. Si se promocionan, estas propiedades de contexto de mensaje están disponibles como `EdiIntAS.<Property Name>` en el **filtros** página de la **propiedades de puerto de envío** cuadro de diálogo.  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|AS2From|string|Contiene el valor AS2-From del encabezado AS2 que representa el nombre del remitente.|  
|AS2PayloadContentType|string|Contiene el tipo de contenido del mensaje de carga.|  
|AS2To|string|Contiene el valor AS2-To del encabezado AS2 que representa el nombre del receptor.|  
|DispositionMode|string|Contiene el valor del modo de disposición de MDN.<br /><br /> Esta propiedad de contexto y la propiedad de contexto DispositionType deben promocionarse para que se genere el MDN.|  
|DispositionType|string|Contiene el valor del tipo de disposición de MDN.<br /><br /> Esta propiedad de contexto y la propiedad de contexto DispositionMode deben promocionarse para que se genere el MDN.|  
|IsAS2AsynchronousMdn|boolean|Indica que el mensaje es un MDN asíncrono.|  
|IsAS2FailedMessage|boolean|Indica que el procesamiento del mensaje AS2 entrante tiene errores en AS2, lo que ha provocado la suspensión del mensaje de carga.|  
|IsAS2Http200OKResponse|boolean|Se establece en un mensaje que se generará como mensaje de respuesta HTTP 200 OK. Se usa cuando no se vaya a generar ningún MDN para un mensaje AS2 o cuando el MDN se envía de forma asíncrona.|  
|IsAS2MdnResponseMessage|boolean|Indica que el mensaje es un mensaje de respuesta MDN.|  
|IsAS2MessageDuplicate|boolean|Indica que el mensaje AS2 entrante se ha recibido previamente.|  
|IsAS2MessageCompressed|boolean|Indica que el mensaje AS2 entrante estaba comprimido.|  
|IsAS2MessageEncrypted|boolean|Indica que el mensaje AS2 entrante estaba cifrado.|  
|IsAS2MessageSigned|boolean|Indica que el mensaje AS2 entrante estaba firmado.|  
|IsAS2PayloadMessage|boolean|Indica que este mensaje incluye el contenido del mensaje AS2 descodificado y debe procesarse como la carga.|  
|MDNAsyncURI|string|Contiene el **Receipt-Delivery-Option** valor que se usa al enviar mensajes de respuesta MDN asincrónicos.|  
|MessageId|string|Contiene el Id. de mensaje AS2 incluido en los encabezados del mensaje AS2.|  
|OriginalMessageId|string|Contiene el Id. de mensaje del mensaje AS2 original. Esta propiedad de contexto forma parte de un mensaje de MDN y se emplea para correlacionar mensajes AS2 y sus respuestas MDN.|  
|PreservedFileName|string|Contiene el nombre de archivo original del mensaje. Esta propiedad de contexto solo se rellenará si el mensaje entrante incluye la información de nombre de archivo como parte del encabezado MIME Content-Disposition.|  
|SendMDN|boolean|Se establece como True si se debe generar un mensaje MDN.|  
  
## <a name="context-properties-internal-to-biztalk-server"></a>Propiedades de contexto internas con respecto a BizTalk Server  
 Las siguientes propiedades de contexto del mensaje no están expuestas públicamente por lo que los usuarios no pueden usarlas en operaciones como el enrutamiento de mensajes. Sin embargo, se pueden ver en mensajes suspendidos y sometidos a seguimiento. El espacio de nombres para estas propiedades de contexto es `http://schemas.microsoft.com/BizTalk/2006/system-properties`.  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|IgnoreSslCertificateNameMismatchErrors|boolean|Dirige el proceso HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que pase por alto los errores de no coincidencia de nombres SSL durante el proceso.|  
|KeepAlive|Boolean|Controla el comportamiento de la funcionalidad Keep Alive de HTTP.|  
|TreatEPMSuspendAsSuccess|boolean|Dirige [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que trate un mensaje suspendido como un mensaje correcto cuando se procesa una conexión entrante HTTP bidireccional.|  
|IsSolicitResponse|boolean|Se establece por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e indica que se trata de un mensaje de petición-respuesta.|  
  
## <a name="context-properties-internal-to-biztalk-mime"></a>Propiedades de contexto internas con respecto a MIME de BizTalk  
 Las siguientes propiedades de contexto del mensaje no están expuestas públicamente por lo que los usuarios no pueden usarlas en operaciones como el enrutamiento de mensajes. Sin embargo, se pueden ver en mensajes suspendidos y sometidos a seguimiento. El espacio de nombres para estas propiedades de contexto es `http://schemas.microsoft.com/BizTalk/2006/system-properties`.  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|IsMultipartReport|boolean|Hace que el codificador MIME de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genere un mensaje de varias partes/informe.|  
|SuppressMimeVersionFromMultiPartMessage|boolean|Hace que el codificador MIME de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suprima el encabezado de la versión MIME en cada parte de un mensaje de varias partes.|  
  
## <a name="context-properties-internal-to-as2"></a>Propiedades de contexto internas con respecto a AS2  
 Las siguientes propiedades de contexto del mensaje no están expuestas públicamente por lo que los usuarios no pueden usarlas en operaciones como el enrutamiento de mensajes. Sin embargo, se pueden ver en mensajes suspendidos y sometidos a seguimiento. El espacio de nombres para estas propiedades de contexto es `http://schemas.microsoft.com/BizTalk/2006/as2-properties`.  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|MicHashAlgorithm|string|Contiene el algoritmo hash que se usa al calcular el valor hash de MIC.|  
|ReceivedContentMic|string|Contiene el valor hash de MIC calculado.|  
  
## <a name="context-properties-internal-to-as2-status-reporting"></a>Propiedades de contexto internas con respecto a AS2 informes de estado  
 Las siguientes propiedades de contexto del mensaje no están expuestas públicamente por lo que los usuarios no pueden usarlas en operaciones como el enrutamiento de mensajes. Sin embargo, se pueden ver en mensajes suspendidos y sometidos a seguimiento. El espacio de nombres para estas propiedades de contexto es `http://schemas.microsoft.com/BizTalk/2006/edi-properties`.  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|InterchangeControlNo|string|Número de control de intercambio de un intercambio EDI. Esta propiedad se lee desde un mensaje durante la codificación AS2 y se usa para informar de una actividad de intercambio AS2.|  
|InterchangeDate|string|Fecha de intercambio de un intercambio EDI. Esta propiedad se lee desde un mensaje durante la codificación AS2 y se usa para informar de una actividad de intercambio AS2.|  
|InterchangeTime|string|Hora de intercambio de un intercambio EDI. Esta propiedad de contexto del mensaje se lee desde un mensaje durante la codificación AS2 y se usa para informar de una actividad de intercambio AS2.|  
|ReceiverID|string|El Id. del receptor del intercambio de un intercambio EDI. Esta propiedad se lee desde un mensaje durante la codificación AS2 y se usa para informar de una actividad de intercambio AS2.|  
|ReceiverQualifier|string|El calificador del receptor del intercambio de un intercambio EDI. Esta propiedad se lee desde un mensaje durante la codificación AS2 y se usa para informar de una actividad de intercambio AS2.|  
|SenderID|string|El Id. del remitente del intercambio de un intercambio EDI. Esta propiedad se lee desde un mensaje durante la codificación AS2 y se usa para informar de una actividad de intercambio AS2.|  
|SenderQualifier|string|El calificador del remitente del intercambio de un intercambio EDI. Esta propiedad se lee desde un mensaje durante la codificación AS2 y se usa para informar de una actividad de intercambio AS2.|  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo y configuración de soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)