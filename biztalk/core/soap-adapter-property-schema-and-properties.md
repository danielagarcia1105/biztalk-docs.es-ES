---
title: Esquema de propiedades del adaptador SOAP y propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ProxyUsername property [SOAP adapters]
- ClientConnectionTimeout property [SOAP adapters]
- SOAP adapters, properties
- ProxyAddress property [SOAP adapters]
- UserDefined property [SOAP adapters]
- AssemblyName property [SOAP adapters]
- ClientCertificate property [SOAP adapters]
- AffiliateApplicationName property [SOAP adapters]
- schemas, SOAP adapters
- AuthenticationScheme property [SOAP adapters]
- UserName property, SOAP adapters
- UseProxy property [SOAP adapters]
- Password property [SOAP adapters]
- configuring [SOAP adapters], schemas
- UnknownHeaders property [SOAP adapters]
- configuring [SOAP adapters], properties
- UseSoap12 property [SOAP adapters]
- UseHandlerSetting property [SOAP adapters]
- SOAP adapters, schemas
- ProxyPassword property [SOAP adapters]
- UseSSO property [SOAP adapters]
- MethodName property [SOAP adapters]
- ProxyPort property [SOAP adapters]
ms.assetid: b471cf4b-2d87-4aa2-ae4a-f48517fd4c94
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a24a9ccfc3a07abe925761fe2d6886646981be9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277516"
---
# <a name="soap-adapter-property-schema-and-properties"></a>Propiedades y esquema de propiedades del adaptador de SOAP
La tabla siguiente enumera las propiedades incluidas en el esquema de propiedades del adaptador de SOAP.  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|**AssemblyName**|xs:string|Identifica el tipo .NET y el ensamblado que se va a cargar y a ejecutar.|  
|**MethodName**|xs:string|Identifica el método de destino en el ensamblado .NET que se va a invocar.|  
|**Nombre de usuario**|xs:string|Nombre de usuario que se utiliza para la autenticación con el servidor.|  
|**Contraseña**|xs:string|Contraseña de usuario que se utilizará para la autenticación con el servidor.|  
|**ClientCertificate**|xs:string|Huella digital del certificado de cliente SSL.|  
|**UseProxy**|xs:Boolean|Especifica si el adaptador de SOAP utilizará un servidor proxy.|  
|**ProxyAddress**|xs:string|Especifica la dirección del servidor proxy.|  
|**ProxyPort**|xs:int|Especifica el puerto del servidor proxy.|  
|**ProxyUsername**|xs:string|Especifica el nombre de usuario para la autenticación con el servidor proxy.|  
|**ProxyPassword**|xs:string|Especifica la contraseña de usuario para la autenticación con el servidor proxy.|  
|**UnknownHeaders**|xs:string|Especifica la lista serializada de encabezados SOAP desconocidos.|  
|**AffiliateApplicationName**|xs:string|Define el nombre de la aplicación afiliada que se utilizará para SSO.|  
|**AuthenticationScheme**|xs:string|Especifica el tipo de autenticación que se utilizará con el servidor de destino.|  
|**UseSSO**|xs:boolean|Determina si el adaptador de SOAP utilizará SSO para el puerto de envío.|  
|**UseHandlerSetting**|xs:boolean|Determina si el puerto de envío de SOAP utilizará la configuración del servidor proxy para el controlador.|  
|**ClientConnectionTimeout**|xs:int|Especifica el periodo de tiempo de espera de una respuesta por parte del servidor. Si se establece como cero (0), el sistema calculará el tiempo de espera en función del tamaño del mensaje de solicitud.|  
|**UserDefined**|xs:string|Define las clases definidas por el usuario.|  
|**UseSoap12**|xs:boolean|Especifica si se genera código de proxy que admita el protocolo SOAP 1.2.|  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador SOAP](../core/configuring-the-soap-adapter.md)