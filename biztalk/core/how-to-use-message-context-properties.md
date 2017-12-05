---
title: "Cómo utilizar propiedades de contexto de mensaje | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, building
- building, insufficient configuration
ms.assetid: 6ca95017-74e0-42d7-befa-93e0c1e1ecd1
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084eae49777b62b190e8e090c0b1045d301d420b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-message-context-properties"></a>Cómo utilizar las propiedades de contexto de mensaje
Las propiedades del sistema son las que suele utilizar de forma interna el motor de mensajería de BizTalk Server y sus componentes. En general, no se recomienda cambiar los valores que establece el motor para estas propiedades, ya que esto puede afectar a la lógica de ejecución del motor. Sin embargo, hay numerosas propiedades que sí se pueden modificar.  
  
 La siguiente tabla contiene una lista de propiedades de contexto de mensaje que el motor de mensajería puede promocionar. Estas propiedades pueden usarse para la creación de expresiones de filtro en puertos de envío y orquestaciones en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Por ejemplo,  
  
```  
PortName = MyMessage(BTS.ReceivePortName);  
MyFileName = MyMessage(BTS.ReceivedFileName);  
MySubject= MyMessage(POP3.Subject);  
```  
  
 En otra tabla se enumeran otras propiedades que pueden resultar útiles en ciertas aplicaciones de BizTalk que no se pueden promocionar.  
  
|Propiedad|Cuándo y dónde se promociona|Tipo|Description|  
|--------------|-----------------------------------|----------|-----------------|  
|BTS.AckFailureCategory|Promocionada por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:int|Identifica la **ErrorCategory**, que proporciona la ubicación y el motivo de la suspensión.|  
|BTS.AckFailureCode|Promocionada por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:string|Identifica la **ErrorCode**, que proporciona la ubicación y el motivo de la suspensión.|  
|BTS.AckID|Promocionada por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:string|Identifica la **MessageID** del mensaje original.|  
|BTS.AckInboundTransportLocation|Promocionada por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:string|Identifica la **InboundTransportLocation** del mensaje original.|  
|BTS.AckOutboundTransportLocation|Promocionada por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:string|Identifica la **OutboundTransportLocation** del mensaje original.|  
|BTS.AckOwnerID|Promocionada por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:string|Identifica el identificador de instancia de mensaje original.|  
|BTS.AckReceivePortID|Promocionada por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:string|Identifica la **ReceivePortID** del mensaje original.|  
|BTS.AckReceivePortName|Promocionada por el motor de mensajería para el mensaje de confirmación.|xs:string|Identifica la **ReceivePortName** del mensaje original.|  
|BTS.AckSendPortID|Promocionada por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:string|Identifica la **SendPortID** del mensaje original.|  
|BTS.AckSendPortName|Promocionada por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:string|Identifica la **SendPortName** del mensaje original.|  
|BTS.AckType|Promocionada por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:string|Permite la supervisión de confirmaciones y confirmaciones negativas por parte de una orquestación. El valor será ACK para una confirmación positiva y NACK en el caso de una confirmación negativa.|  
|BTS.ActionOnFailure|Esta propiedad puede establecerla un adaptador antes de llamar a la interfaz API IBTTTransportBatch::SubmitMessage() para enviar el mensaje a BizTalk.|xs:int|Controla el comportamiento del motor de mensajería cuando se produce un error en la canalización de recepción. Generalmente, el motor de mensajería suspende los mensajes con error; sin embargo, ciertos adaptadores (como HTTP) informarían del error al cliente en lugar de suspender el mensaje debido a un error de canalización de recepción.<br /><br /> Valores válidos:<br /><br /> -Valor predeterminado. si la propiedad no existe, el motor de mensajería intentará suspender el mensaje.<br />-   0. indica que el motor de mensajería no debería suspender automáticamente el mensaje.<br /><br /> Otros valores se reservan para un uso futuro.|  
|BTS.CorrelationToken|Si se establece esta propiedad en el contexto de mensaje, el motor de mensajería la promociona. Esta propiedad se establece implícitamente en un contexto cuando un adaptador solicitud-respuesta o una orquestación envían un mensaje de solicitud a la base de datos de cuadro de mensajes.|xs:string|Habilita el enrutamiento de respuesta a puertos de solicitud-respuesta.|  
|BTS.EpmRRCorrelationToken|Promocionada por el motor de mensajería al ejecutar el mensaje de solicitud-respuesta. Esta propiedad se promociona antes de que los mensajes se envíen a la base de datos de cuadro de mensajes.|xs:int|Utilizada internamente por el motor de mensajería. Especifica el Nombre del servidor, el Id. del proceso y un GUID único para una secuencia de mensajes de solicitud-respuesta.|  
|BTS.InboundTransportLocation|Promocionada por el motor de mensajería después de recibir un mensaje de un adaptador de recepción y antes de publicarla en la base de datos de cuadro de mensajes.|xs:string|Especifica la ubicación (URI) en la que el controlador recibió el mensaje.|  
|BTS.InboundTransportType|Promocionada por el motor de mensajería después de recibir un mensaje de un adaptador de recepción y antes de publicarla en la base de datos de cuadro de mensajes.|xs:string|Especifica el tipo de adaptador que ha recibido este mensaje y lo ha enviado al servidor: archivo, HTTP, etcetera.|  
|BTS.InterchangeSequenceNumber|Promocionada por el motor de mensajería después de recibir un mensaje del adaptador de recepción y antes de publicarlo en la base de datos de cuadro de mensajes.|xs:int|Indica el número de secuencia del documento en el intercambio. Si el documento no forma parte de un intercambio que se ha desensamblado en documentos individuales, este valor será 1. La propiedad puede leerse en una orquestación, una canalización de envío y del adaptador de envío.|  
|BTS.IsDynamicSend|Esta propiedad puede definirse en el contexto del mensaje. No se promocionará y sólo se aplicará a las operaciones de envío.|xs:boolean|El motor de mensajería la escribe en el contexto del mensaje con un valor true cuando la operación de envío se efectúa en un puerto de envío dinámico. Si quisiera definir de forma dinámica propiedades para puertos de envío estáticos en las canalizaciones de envío, tendría que definir este valor como true.|  
|BTS.MessageDestination|Esta propiedad puede establecerla un componente de canalización de desensamblador en la canalización de recepción cuando devuelve un mensaje de GetNext().|xs:string|Se utiliza principalmente para admitir el procesamiento de intercambio recuperable en desensambladores, esta propiedad controla si un mensaje se publica en el cuadro de mensajes o se suspende en la cola de suspensión. Si una canalización detecta un mensaje no válido en un intercambio y desea suspender el mensaje y continuar el procesamiento, puede hacerlo estableciendo MessageDestination = SuspendQueue y devolver el mensaje cuando el motor llame a GetNext() en el desensamblador.<br /><br /> Valores válidos:<br /><br /> -Valor predeterminado. si la propiedad no existe, el mensaje se da por válido y se publica en el cuadro de mensajes.<br />-SuspendQueue. indica al motor de mensajería que suspenda el mensaje. **Nota:** el mensaje suspendido será el mensaje de poscanalización y asignación posterior y no en el mensaje enviado por el adaptador (es decir, el mensaje de conexión).|  
|BTS.MessageType|Promocionada por los componentes de canalización de desensamblador durante el análisis del mensaje.|xs:string|Especifica el tipo del mensaje. El tipo de mensaje se define como una concatenación del espacio de nombres de esquema de documento y el nodo raíz del documento: http://<*MyNamespace*>#<*MyRoot*>.|  
|BTS.OutboundTransportLocation|Si se establece esta propiedad en el contexto de mensaje, el motor de mensajería la promociona. Esta propiedad se establece implícitamente en un contexto de mensaje cuando una orquestación envía un mensaje a un puerto de envío. Esta propiedad también se puede establecer explícitamente en una orquestación o en una canalización.|xs:string|Especifica el URI de la ubicación de destino al que se envía el mensaje. El URI puede contener el prefijo del adaptador, como **http://**. El motor de mensajería utiliza el prefijo del adaptador para determinar el tipo de adaptador que se va a utilizar al enviar el mensaje. Si tanto el prefijo del adaptador y el **BTS. OutboundTransportType** propiedad se establece, el tipo de adaptador de **BTS. OutboundTransportType** siempre tiene prioridad sobre el tipo de adaptador determinado desde el prefijo.<br /><br /> Valores válidos:<br /><br /> BizTalk para Message Queue: **DIRECT =**, **privada =**, y **pública =**<br /><br /> ARCHIVO: **file://**<br /><br /> FTP: **FTP: / /**<br /><br /> HTTP: **http://** y **https://**<br /><br /> SMTP: **mailto:**<br /><br /> SOAP: **SOAP: / /**<br /><br /> SQL: **SQL: / /**|  
|BTS.OutboundTransportType|Si se establece esta propiedad en el contexto de mensaje, el motor de mensajería la promociona. Esta propiedad se establece implícitamente en un contexto cuando una orquestación envía un mensaje a un puerto de envío. Esta propiedad también puede establecerse explícitamente en una orquestación o en una canalización.|xs:string|Especifica el tipo de adaptador utilizado para enviar el mensaje. Los tipos de adaptador disponibles son **archivo**, **FTP**, **HTTP**, **SMTP**, **SOAP**y **SQL**.<br /><br /> Los valores establecidos en esta propiedad, así como los prefijos del adaptador especificados en la dirección, no hacen distinción entre mayúsculas y minúsculas.|  
|BTS.PropertiesToUpdate|Un adaptador establece esta propiedad cuando tiene que conservar algunos valores de la propiedad en un mensaje con error que se reenvía o suspende.<br /><br /> Esto quiere decir que, cuando el mensaje se reenvía o reanuda, las propiedades especificadas estarán establecidas en el contexto.|xs:string|Contiene una cadena XML con elementos que representan nombres de propiedades, espacios de nombres y valores.|  
|BTS.ReceivePortID|Promocionada por el motor de mensajería después de recibir un mensaje de un adaptador de recepción y antes de publicarla en la base de datos de cuadro de mensajes.|xs:int|Identifica el puerto de recepción donde se recibió el mensaje.|  
|BTS.ReceivePortName|Promocionada por el motor de mensajería después de recibir un mensaje de un adaptador de recepción y antes de publicarla en la base de datos de cuadro de mensajes.|xs:string|Nombre descriptivo del puerto de recepción donde se recibió el mensaje.|  
|BTS.RouteDirectToTP|Promocionada por el motor de mensajería en mensajes de ejecución de bucle invertido o solicitud-respuesta. Esta propiedad se promociona antes de que los mensajes se envíen a la base de datos de cuadro de mensajes.|xs:boolean|Utilizada internamente por el motor de mensajería para habilitar escenarios de bucle invertido o de solicitud-respuesta.|  
|BTS.SPGroupID|Promocionada por el motor de mensajería cuando el mensaje se envía a un puerto de envío desde una orquestación.|xs:string|Especifica el Id. del grupo de puertos de envío.|  
|BTS.SPID|Promocionada por el motor de mensajería cuando se envía un mensaje a un puerto de envío desde una orquestación.|xs:string|Especifica el Id. del puerto de envío.|  
|BTS.SPName|Promocionado por el motor de mensajería cuando se publica un mensaje de respuesta desde un puerto de envío de petición-respuesta.|xs:string|Se usa para suscribirse a los mensajes de respuesta desde un puerto de envío de petición-respuesta. El valor es el nombre del puerto de envío.|  
|BTS.SPTransportBackupID|Promocionada por el motor de mensajería cuando se envía un mensaje a un puerto de envío desde una orquestación.|xs:string|Especifica el Id. del adaptador de copia de seguridad del puerto de envío.|  
|BTS.SPTransportID|Promocionada por el motor de mensajería cuando se envía un mensaje a un puerto de envío desde una orquestación.|xs:string|Especifica el Id. del adaptador principal del puerto de envío.|  
|BTS.SuspendAsNonResumable|Esta propiedad puede establecerla un adaptador antes de llamar a SubmitMessage() o en una orquestación antes de enviar un mensaje a un puerto de envío. **Nota:** SubmitRequestMessage() omitirá esta propiedad; mensajes bidireccionales siempre se suspenden como no reanudables.|xs:boolean|Controla si el motor de mensajería debe suspender un mensaje como no reanudable si hay un error en él. Generalmente, los mensajes se suspenden como reanudables, pero hay casos en que resulta inadecuado: por ejemplo, la reanudación de un mensaje de un puerto de envío o recepción solicitado alteraría el orden de los mensajes.<br /><br /> Valores válidos:<br /><br /> -False. el mensaje se suspende como reanudable (éste es el valor predeterminado).<br />-Es true. el mensaje se suspende como no reanudable.|  
|BTS.SuspendMessageOnRoutingFailure|Promocionada por el motor de mensajería después de recibir un mensaje de un adaptador de recepción y antes de publicarla en la base de datos de cuadro de mensajes.|xs:boolean|Especifica el comportamiento cuando se produce un error de enrutamiento de un mensaje entrante.<br /><br /> Valores válidos:<br /><br /> -Valor predeterminado / False. si la propiedad no existe o está definida como False, el motor informa del error al adaptador cuando se produce un error de enrutamiento.<br />-Es true. el motor de enrutamiento suspenderá de forma automática el mensaje cuando se produzca un error de enrutamiento. **Nota:** el mensaje suspendido será el mensaje de poscanalización y asignación posterior y no en el mensaje enviado por el adaptador (es decir, el mensaje de conexión).|  
  
 Hay otras propiedades en este espacio de nombres que contienen información que puede resultar útil para ciertas aplicaciones de BizTalk.  
  
|Propiedad|Cuándo y dónde se promociona|Tipo|Description|  
|--------------|-----------------------------------|----------|-----------------|  
|BTS.AckDescription|Establecida por el motor de mensajería antes de publicar un mensaje de confirmación en la base de datos de cuadro de mensajes.|xs:string|Identifica la **ErrorDescription**, que proporciona la ubicación y el motivo de la suspensión.|  
|BTS.EncryptionCert|No promocionable.|xs:int|Identifica la huella digital correspondiente al certificado de cifrado. Para llevar a cabo el cifrado de respuesta en un puerto de solicitud-respuesta que recibe un mensaje firmado y cifrado, defina esta propiedad en una orquestación o en un componente de canalización personalizado antes del componente de canalización de codificación de MIME/SMIME de una canalización.|  
|BTS.InterchangeID|Establecida por el motor de mensajería para cada mensaje que llega al servidor.|xs:string|Define el Id. único utilizado para agrupar los documentos resultantes del mismo mensaje de intercambio.|  
|BTS.Loopback|Establecida por un adaptador al enviar el mensaje de solicitud para la ejecución de bucle invertido.|xs:boolean|Define si el mensaje debe enviarse al servidor para una ejecución de bucle invertido. En una ejecución de bucle invertido, el mensaje de solicitud se publica en la base de datos de cuadro de mensajes donde se enruta directamente al adaptador de recepción como respuesta.|  
|BTS.SignatureCertificate|Establecida por algunos adaptadores al enviar un mensaje al servidor. Esta propiedad lo usa componente de canalización de resolución de entidades.|xs:string|Identifica la huella digital del certificado de firma utilizado para firmar el mensaje recibido por BizTalk Server.|  
|BTS.SourcePartyID|Establecida por el componente de canalización de resolución de entidades después de que se haya identificado la entidad correspondiente al mensaje entrante.|xs:string|Indica el Id. de la entidad de BizTalk.|  
|BTS.SSOTicket|Si el adaptador de recepción admite esta propiedad, se establece al publicar el mensaje en un servidor.|xs:string|Un vale contiene el dominio y el nombre de usuario cifrados del usuario actual, así como la fecha de caducidad del vale. Los adaptadores con inicio de sesión único habilitado utilizan el vale para obtener las credenciales para el usuario al autenticar con los extremos de destino.|  
|BTS.WindowsUser|Establecida por algunos adaptadores al enviar un mensaje al servidor. Esta propiedad lo usa componente de canalización de resolución de entidades.|xs:string|Especifica la cuenta del usuario en nombre de quien se envía el mensaje al servidor:|  
  
 Para obtener más información sobre propiedades y esquemas de propiedades asociados a componentes de canalización y adaptadores, vea los temas siguientes:  
  
-   [Propiedades y esquema de propiedades del adaptador de archivo](../core/file-adapter-property-schema-and-properties.md)
  
-   [Propiedades y esquema de propiedades del adaptador de FTP](../core/ftp-adapter-property-schema-and-properties.md)  
  
-   [Propiedades y esquema de propiedades del adaptador de HTTP](../core/http-adapter-property-schema-and-properties.md)  
  
-   [Propiedades y esquema de propiedades del adaptador de MSMQ](../core/msmq-adapter-property-schema-and-properties.md)  
  
-   [Propiedades y esquema de propiedades del adaptador de SMTP](../core/smtp-adapter-property-schema-and-properties.md)  
  
-   [Propiedades y esquema de propiedades del adaptador de SOAP](../core/soap-adapter-property-schema-and-properties.md)  
  
-   [Propiedades y esquema de BizTalk Framework](../core/biztalk-framework-schema-and-properties.md)  
  
-   [Propiedades del adaptador de MQSeries](../core/mqseries-adapter-properties.md)  
  
-   [Propiedades y esquema de propiedades del adaptador de POP3](../core/pop3-adapter-property-schema-and-properties.md)  
  
-   [Referencia de propiedades del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-properties-reference.md)  
  
-   [Propiedades y esquema de propiedades MIME/SMIME](../core/mime-smime-property-schema-and-properties.md)  
  
-   [Propiedades y esquema de propiedades de archivo sin formato y XML](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
## <a name="see-also"></a>Vea también  
 [Acerca de las propiedades de contexto de mensaje de BizTalk](../core/about-biztalk-message-context-properties.md)   
 [Cómo usar expresiones para asignar valores a puertos dinámicos](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)