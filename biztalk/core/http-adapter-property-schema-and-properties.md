---
title: Esquema de propiedades del adaptador HTTP y propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- AffiliateApplicationName property [HTTP adapters]
- Certificate property [HTTP adapters]
- Password property [HTTP adapters]
- HTTP adapters, properties
- InboundHttpHeaders property [HTTP adapters]
- UseHandlerProxySettings property [HTTP adapters]
- configuring [HTTP adapters], properties
- schemas, HTTP adapters
- RequestTimeout property [HTTP adapters]
- ProxyPassword property [HTTP adapters]
- UseSSO property [HTTP adapters]
- HTTP adapters, schemas
- AuthenticationScheme property [HTTP adapters]
- ProxyName property [HTTP adapters]
- ProxyPort property [HTTP adapters]
- UseProxy property [HTTP adapters]
- configuring [HTTP adapters], schemas
- ContentType property [HTTP adapters]
- MaxRedirects property [HTTP adapters]
- ProxyUsername property [HTTP adapters]
- UserName property, HTTP adapters
ms.assetid: c9b50a82-8cb1-4521-9cf3-5fd77a3531e1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 416ad39e804a4907dc39c7cef941e9a1bb57d3dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257428"
---
# <a name="http-adapter-property-schema-and-properties"></a>Propiedades y esquema de propiedades del adaptador de HTTP
La tabla siguiente enumera las propiedades incluidas en el esquema de propiedades del adaptador de HTTP.  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/http-properties  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|**ProxyName**|xs:string|Especifica el nombre del servidor proxy.|  
|**ProxyPort**|xs:int|Especifica el puerto del servidor proxy.|  
|**UseHandlerProxySettings**|xs:boolean|Determina si el puerto de envío de HTTP utilizará la configuración del servidor proxy para el controlador.|  
|**UseProxy**|xs:boolean|Especifica si el adaptador de HTTP utiliza el servidor proxy.|  
|**RequestTimeout**|xs:int|Período de tiempo de espera de una respuesta del servidor. Cuando esta propiedad se define como cero (0), el sistema calcula el tiempo de espera en función del tamaño del mensaje de solicitud.|  
|**Nombre de usuario**|xs:string|El nombre de usuario que se utilizará para la autenticación con el servidor.|  
|**Contraseña**|xs:string|Contraseña de usuario que se utilizará para la autenticación con el servidor.|  
|**ProxyUsername**|xs:string|Especifica el nombre de usuario para la autenticación con el servidor proxy.|  
|**ProxyPassword**|xs:string|Especifica la contraseña de usuario para la autenticación con el servidor proxy.|  
|**MaxRedirects**|xs:int|Número máximo de veces que el adaptador de HTTP puede redirigir la solicitud.|  
|**Tipo de contenido**|xs:string|Tipo de contenido de los mensajes de solicitud.|  
|**AuthenticationScheme**|xs:string|Tipo de autenticación que se utiliza con el servidor de destino.|  
|**Certificado**|xs:string|Huella digital del certificado de cliente SSL.|  
|**UseSSO**|xs:boolean|Especifica si el puerto de envío de HTTP utilizará SSO.|  
|**AffiliateApplicationName**|xs:string|Nombre de la aplicación afiliada que se utilizará para SSO.|  
|**InboundHttpHeaders**|xs:string|Contiene los encabezados HTTP de las solicitudes HTTP entrantes.|  
|**SubmissionHandle**|xs:string|Contiene el token de correlación (GUID) de BizTalk Server para el mensaje de solicitud.|  
|**EnableChunkedEncoding**|xs:boolean|Especifica si el adaptador de HTTP deberá utilizar la codificación fragmentada.|  
|**UserHttpHeaders**|xs:string|Incluye los encabezados personalizados contenidos en el mensaje HTTP de respuesta o solicitud<br /><br /> El valor de la **UserHttpHeaders** propiedad debe tener el formato siguiente:<br /><br /> `Header1: value\r\nHeader2: value\r\n`<br /><br /> **Tenga en cuenta** colocar un signo de dos puntos (:) y un carácter de espacio () entre el encabezado y el valor. Si el encabezado se deja en blanco, se filtrará la entrada. Está permitido dejar el valor en blanco.<br /><br /> Puede modificar los siguientes cinco encabezados HTTP estándares mediante el **UserHttpHeaders** propiedad:<br /><br /> -Aceptar<br /><br /> -El origen de referencia<br /><br /> -Espera<br /><br /> If-Modified-Since<br /><br /> -User-Agent|  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador HTTP](../core/configuring-the-http-adapter.md)