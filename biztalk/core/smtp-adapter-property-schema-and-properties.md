---
title: Propiedades y esquema de propiedades de adaptador de SMTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UserName property, SMTP adapters
- EmailBodyTextCharset property [SMTP adapters]
- configuring [SMTP adapters], properties
- Subject property [SMTP adapters]
- EmailBodyFileCharset property [SMTP adapters]
- Attachments property [SMTP adapters]
- SMTP adapters, schemas
- EmailBodyText property [SMTP adapters]
- configuring [SMTP adapters], schemas
- CC property [SMTP adapters]
- ReadReceipt property [SMTP adapters]
- Password property [SMTP adapters]
- ReplyBy property [SMTP adapters]
- DeliveryReceipt property [SMTP adapters]
- SMTP adapters, properties
- SMTPAuthenticate property [SMTP adapters]
- EmailBodyFile property [SMTP adapters]
- schemas, SMTP adapters
- SMTPHost property [SMTP adapters]
- From property [SMTP adapters]
- MessagePartsAttachments property [SMTP adapters]
ms.assetid: 6d062fb6-d728-4525-8f0d-bd3f0f8ff7ca
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09f7dfa67bfad53e43a4a6678ff6ad67705e0e27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278676"
---
# <a name="smtp-adapter-property-schema-and-properties"></a>Propiedades y esquema de propiedades del adaptador de SMTP
La tabla siguiente enumera las propiedades incluidas en el esquema de propiedades del adaptador de SMTP.  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/smtp-properties  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|**Nombre de usuario**|xs:string|Especifica el nombre de usuario que se utilizará para la autenticación en el servidor SMTP.|  
|**Contraseña**|xs:string|Especifica la contraseña que se utilizará para la autenticación en el servidor SMTP.|  
|**SMTPHost**|xs:string|Especifica el nombre del servidor SMTP que se utilizará al enviar mensajes.|  
|**De**|xs:string|Especifique la dirección de correo electrónico que coloque en el protocolo SMTP **de** encabezado.|  
|**CC**|xs:string|Especifica la dirección de correo electrónico a la que enviar una copia del mensaje.|  
|**Asunto**|xs:string|Especifica el encabezado de asunto del mensaje.|  
|**SMTPAuthenticate**|xs:int|Especifica el tipo de autenticación que se utilizará con el servidor SMTP.|  
|**ReadReceipt**|xs:boolean|Especifica si se envía un mensaje de correo electrónico de confirmación cuando se lea el mensaje.|  
|**DeliveryReceipt**|xs:boolean|Especifica si se envía un mensaje de correo electrónico de confirmación tras entregar el mensaje.|  
|**EmailBodyText**|xs:string|Especifica el texto que se utilizará para el cuerpo del correo electrónico que se va a enviar.|  
|**EmailBodyTextCharset**|xs:string|Especifica el carácter establecido para codificar el cuerpo del correo electrónico que se envía cuando el **EmailBodyText** se utiliza la opción. El adaptador de SMTP convertirá la **EmailBodyText** para el juego de caracteres especificado por **EmailBodyTextCharset**.|  
|**EmailBodyFile**|xs:string|Especifica que se utilice el contenido de un archivo para el cuerpo del correo electrónico que se va a enviar y la ruta de acceso completa de dicho archivo. Esta ruta debe estar a disposición del host para el adaptador de SMTP en tiempo de ejecución.|  
|**EmailBodyFileCharset**|xs:string|Especifica el carácter establecido para codificar el cuerpo del correo electrónico enviado cuando el **EmailBodyFile** propiedad está establecida. El adaptador de SMTP no realizará ninguna conversión en el archivo; el archivo ya se debe haber codificado en este juego de caracteres. Si el archivo tiene una marca de orden de bytes (BOM), el adaptador de SMTP la quitará.|  
|**Datos adjuntos**|xs:string|Especifica que se adjuntarán archivos al mensaje de correo electrónico y la ruta completa de esos archivos. Las rutas especificadas deben estar a disposición del host para el adaptador de SMTP en tiempo de ejecución.|  
|**MessagePartsAttachments**|xs:unsignedInt|Especifica la forma de adjuntar partes del mensaje de BizTalk al mensaje de correo electrónico.|  
|**ReplyBy**|xs:dateTime|Especifique un valor de fecha y hora para la **responder a** encabezado en el mensaje de correo electrónico saliente.|  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de SMTP](../core/configuring-the-smtp-adapter.md)