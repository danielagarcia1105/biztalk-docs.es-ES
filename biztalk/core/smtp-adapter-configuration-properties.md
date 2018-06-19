---
title: Propiedades de configuración de adaptador de SMTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, properties
- SMTP adapters, code sample
- SMTP adapters, send ports
- send ports, adapters
ms.assetid: 6af287f5-272a-42d7-9878-99a4157c06ce
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b8bb0c5562c07260a9d411b8144bd7a576eb3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279404"
---
# <a name="smtp-adapter-configuration-properties"></a>Propiedades de configuración del adaptador de SMTP
En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para un puerto de envío del adaptador de SMTP:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|DeliveryReceipt|VT_BOOL|Especifica si se debe enviar un mensaje de correo electrónico de confirmación cuando se entrega el mensaje.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
|De|VT_BSTR|Especificar la dirección de correo electrónico que se colocará en el encabezado De de SMTP.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Ninguno|  
|MessagePartsAttachments|VT_UI4|Especifica la forma de adjuntar partes del mensaje de BizTalk al mensaje de correo electrónico.|Los valores válidos son:<br /><br /> -0 (no adjuntar partes del mensaje)<br />-1 (adjuntar solo parte del cuerpo<br />-2 (adjuntar todas las partes)|El valor predeterminado es 0 (no adjuntar partes del mensaje).|  
|CC|VT_BSTR|Especificar la dirección de correo electrónico a la que desea enviar una copia del mensaje.|Longitud máxima: 1024|Puede especificar más de una dirección de correo electrónico.|  
|SMTPAuthenticate|VT_UI4|Los valores válidos son:<br /><br /> -0 (no autenticar)<br />-1 (autenticación básica)<br />-2 (cuenta de proceso (NTLM))|Si no se especifica este valor, entonces se aplica el valor (predeterminado).|El valor (predeterminado) indica que el puerto de envío SMTP utilizará los valores de configuración especificados en el controlador de envío.|  
|Nombre de usuario|VT_BSTR|Especifica el nombre de usuario que se utilizará para la autenticación en el servidor SMTP.|Esta propiedad no necesita ningún valor a menos que la propiedad SMTPAuthenticate esté definida como 1 (autenticación básica).<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|Ninguno|  
|EmailBodyFileCharset|VT_BSTR|Especificar la codificación del juego de caracteres del archivo que se envía.|Esta propiedad no necesita ningún valor a menos que la propiedad EmailBodyFile esté definida.|El adaptador de SMTP no aplica la codificación especificada al archivo; esta opción solo sirve para especificar el modo en que se ha codificado el archivo que se envía.<br /><br /> El valor predeterminado es utf-8.|  
|EmailBodyText|VT_BSTR|Especifica el texto que se utilizará para el cuerpo del correo electrónico que se va a enviar.|Longitud máxima: 64Kb|Ninguno|  
|ReadReceipt|VT_BOOL|Especifica si se debe enviar un mensaje de correo electrónico de confirmación cuando se lee el mensaje.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
|Para|VT_BSTR|Especificar la dirección de correo electrónico a la que desea enviar mensajes.|Ninguno|Ninguno|  
|EmailBodyFile|VT_BSTR|Especifica la ruta al archivo que se va a utilizar para el cuerpo del correo electrónico que se está enviando.|Longitud máxima de la ruta de acceso: 256 caracteres|Es un procedimiento recomendado para especificar una ruta de acceso en un recurso compartido de archivos que sea accesible desde todos los servidores de BizTalk Server en el grupo de BizTalk Server para su uso en producción.|  
|Asunto|VT_BSTR|Especifica el encabezado de asunto del mensaje.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Ninguno|  
|Contraseña|VT_NULL|Especifica la contraseña que se utilizará para la autenticación en el servidor SMTP.|Esta propiedad no necesita un valor a menos que la propiedad SMTPAuthenticate se establece en 1 (autenticación básica).<br /><br /> Este valor siempre se establece en NULL cuando se exporta un archivo de enlace. Este campo se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.|Ninguno|  
|Datos adjuntos|VT_BSTR|Especifica la ruta a un archivo que se va a adjuntar al correo electrónico que se está enviando.|Longitud máxima de la ruta de acceso: 256 caracteres|Ninguno|  
|SMTPHost|VT_BSTR|Especifica el nombre del servidor SMTP que se utilizará al enviar mensajes.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.<br /><br /> Longitud máxima de la ruta de acceso: 256 caracteres|Ninguno|  
|EmailBodyTextCharset|VT_BSTR|Especificar el juego de caracteres que se utilizará para codificar el cuerpo del correo electrónico que se está enviando.|Esta propiedad no necesita ningún valor a menos que la propiedad EmailBodyText esté definida.|El valor predeterminado es utf-8.|  
  
 En el siguiente código se muestra el formato de la cadena XML que se utiliza para establecer las propiedades:  
  
```  
<CustomProps>  
<DeliveryReceipt vt="11">-1</DeliveryReceipt>  
<From vt="8">someone@microsoft.com</From>  
<MessagePartsAttachments vt="19">0</MessagePartsAttachments>  
<CC vt="8">someoneelse@microsoft.com</CC>  
<SMTPAuthenticate vt="19">1</SMTPAuthenticate>  
<Username vt="8">OverrideUsername</Username>  
<EmailBodyFileCharset vt="8">utf-8</EmailBodyFileCharset>  
<EmailBodyText vt="8">Email Body Text</EmailBodyText>  
<ReadReceipt vt="11">-1</ReadReceipt>  
<To vt="8">recipient@microsoft.com</To>  
<EmailBodyFile vt="8">C:\emailbodyfile.xml</EmailBodyFile>  
<Subject vt="8">test mail</Subject>  
<Password vt="1" />  
<Attachments vt="8">C:\attachment.txt</Attachments>  
<SMTPHost vt="8">emailhost</SMTPHost>  
<EmailBodyTextCharset vt="8">utf-8</EmailBodyTextCharset>  
</CustomProps>  
```