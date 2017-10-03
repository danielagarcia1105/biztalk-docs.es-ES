---
title: "Propiedades de configuración de adaptador de MSMQ | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, send ports
- receive locations, adapters
- MSMQ adapters, properties
- MSMQ adapters, code sample
- send ports, adapters
ms.assetid: d660d0ce-bff9-4bc5-be1d-38954c2fdbe2
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2460f359e0a9a3954d9417fdf441e9bd01de58b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="msmq-adapter-configuration-properties"></a>Propiedades de configuración del adaptador de MSMQ
En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para una ubicación de recepción de un adaptador de MSMQ:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|cola|VT_BSTR|Especifica una ruta válida de acceso de la cola a la ubicación supervisada por la ubicación de recepción.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
|batchSize|VT_BSTR|Especifica el tamaño de lote que usa el adaptador de MSMQ al enviar un lote de mensajes a la base de datos de cuadro de mensajes.|Los valores válidos son de 1 a 4294967295.|El valor predeterminado es 20.|  
|transaccional|VT_BSTR|Especifica si se leen mensajes de la cola de origen bajo el contexto de una transacción distribuida de Microsoft  (MSDTC).|Los valores válidos son:<br /><br /> -true<br />-false<br /><br /> El adaptador no admite lecturas transaccionales en las colas remotas.|El valor predeterminado es false.|  
|serialProcessing|VT_BSTR|Especifica si los mensajes se procesan por orden.|Los valores válidos son:<br /><br /> -true<br />-false|El valor predeterminado es false.|  
|onFailure|VT_BSTR|Especificar el modo en que el adaptador debe responder a un error.|Los valores válidos son:<br /><br /> -stopOnFailure<br />-suspendNonResumable<br />-suspendResumable|El valor predeterminado es suspendResumable.|  
|uri|VT_BSTR|Especifica la ruta completa a la cola supervisada por la ubicación de recepción.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
  
 En el siguiente código se muestra el formato de la cadena que se utiliza para establecer las propiedades:  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><queue>FORMATNAME:DIRECT=OS:.\PRIVATE$\QUEUE</queue><batchSize>20</batchSize><transactional>false</transactional><serialProcessing>false</serialProcessing><onFailure>suspendResumable</onFailure><uri>FORMATNAME:DIRECT=OS:.\PRIVATE$\QUEUE</uri></Config></AdapterConfig></CustomProps>  
```  
  
 En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para un puerto de envío del adaptador de MSMQ:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|Cola|VT_BSTR|Especificar la cola de destino.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
|maximumMessageSiz|VT_BSTR|Especifica el tamaño máximo de mensaje en kilobytes (KB) de los mensajes que se envían a la cola en cuestión.|Los valores válidos son de 1 a 4294967295 si segmentationSupport y transactional se establecen como True. De lo contrario, los valores válidos son de 1 a 4095.|El valor predeterminado es 1024.|  
|acknowledgeType|VT_BSTR|Especifica uno o más tipos de confirmación.|Los valores válidos son los miembros de .NET **System.Messaging.AcknowledgeTypes** enumeración.|El valor predeterminado es None.|  
|administrationQueue|VT_BSTR|Especifica la cola de administración de MSMQ.|Ninguno|Ninguno|  
|timeOut|VT_BSTR|Especificar el tiempo de espera máximo de los mensajes hasta alcanzar la cola de destino.|Esta propiedad solo se aplica cuando propiedad transactional está establecida en True.<br /><br /> -Valores válidos son 1 a 10675199 cuando se especifica un valor de timeoutunits como de días.<br />-Valores válidos son 1 a 596523 cuando se especifica un valor de timeoutunits como de horas.<br />-Valores válidos son 1 a 35791394 cuando se especifica un valor de timeoutunits como de minutos.<br />-Valores válidos son de 1 a 2147483647 cuando se especifica un valor de timeoutunits como de segundos.|Ninguno|  
|priority|VT_BSTR|Especifica la prioridad del mensaje.|Los valores válidos son los miembros de .NET **System.Messaging.MessagePriority** enumeración.|Ninguno|  
|recuperable|VT_BSTR|Especificar si se garantizará que se podrá recuperar un mensaje.|Los valores válidos son:<br /><br /> -true<br />-false|El valor predeterminado es false.|  
|encryptionAlgorithm|VT_BSTR|Especifica el algoritmo de cifrado que se va a usar.|Los valores válidos son los miembros de .NET **System.Messaging.EncryptionAlgorithm** enumeración.|El valor predeterminado es None.|  
|useAuthentication|VT_BSTR|Especifica si se usará autenticación.|Utilizar esta propiedad en combinación con la propiedad certificate para comprobar el mensaje. Utilizar las propiedades userName y password para obtener acceso a las colas.|Ninguno|  
|certificado|VT_BSTR|Especifica el certificado utilizado para comprobar mensajes.|Escriba la huella digital de certificado de 40 caracteres.|Ninguno|  
|segmentationSupport|VT_BSTR|Especifica si se admite la segmentación.|Los valores válidos son:<br /><br /> -true<br />-false|El valor predeterminado es false.|  
|transaccional|VT_BSTR|Especifica si se admite el envío de mensajes bajo el contexto de una transacción distribuida de Microsoft  (MSDTC).|Los valores válidos son:<br /><br /> -true<br />-false|El valor predeterminado es false.|  
|useJournalQueue|VT_BSTR|Especifica si se guarda una copia del mensaje cada vez que se procese.|Los valores válidos son:<br /><br /> -true<br />-false|El valor predeterminado es false.|  
|useDeadLetterQueue|VT_BSTR|Especifica si se envían mensajes a la cola de mensajes con problemas de entrega si se produce un error.|Los valores válidos son:<br /><br /> -true<br />-false|El valor predeterminado es true.|  
|ackTypeEnumsValue|VT_BSTR|Especifica el operador OR bit a bit de los valores asociados con los valores acknowledgeType especificados.|Ninguno|El valor predeterminado es 0.|  
|timeOutUnits|VT_BSTR|Especifica la unidad que se usará junto con el valor especificado para la propiedad timeOut.|Los valores válidos son:<br /><br /> -Días<br />-Horas<br />-Minutos<br />-Segundos|El valor predeterminado es Días.|  
|userName|VT_BSTR|Especificar el nombre de usuario de una cola remota.|El valor predeterminado está vacío.|  
|password|VT_BSTR|Especifica la contraseña que se usará junto con el valor especificado para la propiedad userName para obtener acceso a una cola remota.|Siempre se marca este valor cuando se exporta un archivo de enlace. Este campo se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.|El valor predeterminado está vacío.|  
|bodyType|VT_BSTR|Especificar el tipo de cuerpo del mensaje en MSMQ.|Los valores válidos son los miembros de .NET **VarEnum** enumeración.|El valor predeterminado es 8209.|  
|uri|VT_BSTR|Especifica la ruta completa a la cola de destino.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
  
 En el siguiente código se muestra el formato de la cadena que se utiliza para establecer las propiedades:  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><queue>FORMATNAME:DIRECT=OS:TESTSERVER\PRIVATE$\DESTQUEUE</queue><maximumMessageSize>1024</maximumMessageSize><acknowledgeType>None</acknowledgeType><administrationQueue>Direct=OS:TestServer\Private$\AdminQueue</administrationQueue><timeOut>4</timeOut><priority>Normal</priority><recoverable>false</recoverable><encryptionAlgorithm>None</encryptionAlgorithm><useAuthentication>false</useAuthentication><segmentationSupport>false</segmentationSupport><transactional>false</transactional><useJournalQueue>false</useJournalQueue><useDeadLetterQueue>true</useDeadLetterQueue><ackTypeEnumsValue>0</ackTypeEnumsValue><timeOutUnits>Days</timeOutUnits><userName>TestUser</userName><password>******</password><bodyType>8209</bodyType><uri>FORMATNAME:DIRECT=OS:TESTSERVER\PRIVATE$\DESTQUEUE</uri></Config></AdapterConfig>  
```  
  
> [!NOTE]
>  Al especificar los datos de configuración de TransportTypeData para un adaptador que se genera utilizando el marco de trabajo, los pares de nombre/valor que se usan todos se almacenarán en el \<AdapterConfig > elemento. Puesto que la \<AdapterConfig > elemento especifica la VT_BSTR (vt = "8"), a continuación, el tipo de datos de la \< > caracteres en los datos deben convertirse.