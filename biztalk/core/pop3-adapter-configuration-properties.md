---
title: "POP3 Propiedades de configuración de adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, adapters
- POP3 adapters, receive locations
- POP3 adapters, code sample
- POP3 adapters, properties
ms.assetid: e30c848d-afff-42f3-8162-c7ea8c7e3b9a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bf7aa17f36143f80a82f664dbabd257d7b924db
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="pop3-adapter-configuration-properties"></a>Propiedades de configuración del adaptador de POP3
En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para una ubicación de recepción de un adaptador de POP3:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|mailServer|VT_BSTR|Especificar el servidor de correo POP3 que aloja el buzón que sondeará el adaptador de POP3.|Ninguno|Ninguno|  
|serverPort|VT_BSTR|Especificar el puerto del servidor de correo POP3.|Los valores válidos son de 0 a 65535.|El valor 0 indica que se va a utilizar el puerto POP3 predeterminado 110 si la propiedad sslRequired tiene el valor False o el puerto 995 si la propiedad sslRrequired tiene el valor True.<br /><br /> El valor predeterminado es 0.|  
|userName|VT_BSTR|Especificar el nombre de usuario que se utilizará para la autenticación con el servidor POP3.|Ninguno|Ninguno|  
|password|VT_BSTR|Especificar la contraseña de usuario que se utilizará para la autenticación con el servidor POP3.|Siempre se marca este valor cuando se exporta un archivo de enlace. Este campo se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.|Ninguno|  
|authenticationScheme|VT_BSTR|Especificar el tipo de autenticación que se utilizará con el servidor de destino.|Los valores válidos son:<br /><br /> -Básico<br />-Resumen<br />-SPA|No hay valor predeterminado para esta propiedad.|  
|sslRequired|VT_BSTR|Especificar si se utilizará SSL para la comunicación con el servidor de destino.|Los valores válidos son:<br /><br /> -true<br />-false|El valor predeterminado es false.|  
|applyMIME|VT_BSTR|Especificar si se aplica la descodificación MIME a los mensajes que recibe el adaptador de POP3.|Los valores válidos son:<br /><br /> -true<br />-false|El valor predeterminado es true.|  
|bodyPartContentType|VT_BSTR|Especificar el tipo de contenido de parte del cuerpo del mensaje de correo electrónico entrante que se va a enviar a BizTalk Server.|Los valores válidos son:<br /><br /> -cuerpo<br />-texto/xml<br />-texto/sin formato<br />-texto /|No hay valor predeterminado para esta propiedad.|  
|bodyPartIndex|VT_BSTR|Especificar la parte del cuerpo del mensaje de correo electrónico entrante que se va a enviar a BizTalk Server.|Los valores válidos son de 0 a 128.|El valor predeterminado es 0.|  
|errorThreshold|VT_BSTR|Especificar el número máximo de errores de red o de protocolo que se esperará antes de cerrar el adaptador.|Los valores válidos son de 0 a 4294967295.|Especificar el valor 0 para evitar que se cierre el adaptador.<br /><br /> El valor predeterminado es 10.|  
|pollingInterval|VT_BSTR|Especificar el intervalo entre intentos de recuperar mensajes del servidor POP3.|Los valores válidos son:<br /><br /> -De 1 a 120 si el valor de pollingUnitOfMeasure es días.<br />-De 1 a 2880 si el valor de pollingUnitOfMeasure es horas.<br />-De 1 a 172800 si el valor de pollingUnitOfMeasure es minutos.<br />-De 2 a 10368000 si el valor de pollingUnitOfMeasure es segundos.|El valor predeterminado es 5.|  
|pollingUnitOfMeasure|VT_BSTR|Especificar la unidad de medida que se utilizará junto con el valor de pollingInterval.|Los valores válidos son:<br /><br /> -Días<br />-Horas<br />-Minutos<br />-Segundos|El valor predeterminado es Minutos.|  
|uri|VT_BSTR|Especifica la ruta completa al buzón supervisado por la ubicación de recepción.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
  
 En el siguiente código se muestra el formato de la cadena que se utiliza para establecer las propiedades:  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><mailServer>test.microsoft.com</mailServer><serverPort>0</serverPort><userName>testuser</userName><password>******</password><authenticationScheme>Basic</authenticationScheme><sslRequired>false</sslRequired><applyMIME>true</applyMIME><bodyPartContentType>text/xml</bodyPartContentType><bodyPartIndex>1</bodyPartIndex><errorThreshold>10</errorThreshold><pollingInterval>5</pollingInterval><pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure><uri>POP3://test.microsoft.com#testuser</uri></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  Al especificar los datos de configuración de TransportTypeData para un adaptador que se genera utilizando el marco de trabajo, los pares de nombre/valor que se usan todos se almacenarán en el \<AdapterConfig > elemento. Puesto que la \<AdapterConfig > elemento especifica la VT_BSTR (vt = "8"), a continuación, el tipo de datos de la \< \> caracteres en los datos deben convertirse.