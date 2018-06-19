---
title: Propiedades y esquema de propiedades del adaptador FTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [FTP adapters], schemas
- FTP adapters, properties
- BeforePut property [FTP adapters]
- PassiveMode property [FTP adapters]
- configuring [FTP adapters], properties
- UserName property, FTP adapters
- SSOAffiliateApplication property [FTP adapters]
- AfterPut property [FTP adapters]
- ReceivedFileName property [FTP adapters]
- RepresentationType property [FTP adapters]
- SpoolingFolder property [FTP adapters]
- FTP adapters, schemas
- CommandLogFileName property [FTP adapters]
- AllocateStorage property [FTP adapters]
- schemas, FTP adapters
- Password property [FTP adapters]
- MaxConnections property [FTP adapters]
ms.assetid: 677fdb61-c2b0-4df2-a826-840113e61e8b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cf72847fccd84a1435e436a4bf2b59d36e26179
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006141"
---
# <a name="ftp-adapter-property-schema-and-properties"></a>Propiedades y esquema de propiedades del adaptador de FTP
La tabla siguiente contiene las propiedades del esquema de propiedades del adaptador de FTP.  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/ftp-properties  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|**RepresentationType**|xs:string|Especifica cómo envía datos el adaptador de FTP.<br /><br /> **Los valores válidos:** binario o ASCII|  
|**SSOAffiliateApplication**|xs:string|Especifica la aplicación afiliada de inicio de sesión único empresarial que se va a utilizar en el puerto de envío FTP.|  
|**UserName**|xs:string|Especifica el nombre de usuario que hay que utilizar para iniciar sesión en el servidor FTP cuando se envían mensajes.|  
|**Contraseña**|xs:string|Especifica la contraseña que hay que utilizar para iniciar sesión en el servidor FTP cuando se envían mensajes.|  
|**BeforePut**|xs:string|Especifica los comandos FTP que se ejecutarán antes del archivo PUT, como los comandos para cambiar valores predeterminados en el servidor FTP. Separe los comandos con un punto y coma (;). No se requiere ningún comando open.|  
|**AfterPut**|xs:string|Especifica los comandos FTP que se ejecutarán después del archivo PUT. Separe los comandos con un punto y coma (;).|  
|**ReceivedFileName**|xs:string|Especifica el nombre completo del archivo en el que el adaptador de FTP leerá el mensaje.|  
|**MaxConnections**|xs:unsignedInt|Especifica el número máximo de conexiones FTP simultáneas que se pueden abrir con el servidor. El valor 0 significa que no hay ningún límite.|  
|**CommandLogFileName**|xs:string|Especifica la ubicación en la que se guardará una copia del archivo de registro que se puede utilizar para diagnosticar las condiciones de error cuando se envían o reciben archivos mediante FTP.|  
|**AllocateStorage**|xs:boolean|Esta opción está en desuso en BizTalk Server y se desaconseja el uso de esta propiedad.|  
|**PassiveMode**|xs:boolean|Especifica el modo en el que el adaptador establece la conexión con el servidor FTP.<br /><br /> En modo activo, el servidor FTP se conecta a un puerto abierto por el adaptador FTP. En modo pasivo, el adaptador FTP se conecta a un puerto abierto por el servidor FTP.<br /><br /> Si **PassiveMode** es false, el adaptador se conecta al servidor FTP con el modo activo. El valor predeterminado de esta propiedad es False.|  
|**SpoolingFolder**|xs:string|Especifica la ubicación para una carpeta temporal del servidor FTP. Esta carpeta se utiliza para asegurar la recuperación tras un error de transferencia.|  
|**UseSsl**|xs:boolean|Especifica si el adaptador FTP debe usar SSL para comunicarse con el servidor FTPS.|  
|**UseDataProtection**|xs:boolean|Especifica si se usa el cifrado SSL para las transferencias de archivos. Elija True si el adaptador debe usar el cifrado SSL cuando envía y recibe archivos de datos del servidor FTPS. Elija False para que el adaptador envíe y reciba como texto sin formato.|  
|**FtpsConnectionMode**|xs:string|Especifica el modo de conexión SSL realizada al servidor FTPS.<br /><br /> **Valores válidos:** implícita o explícita|  
|**ClientCertificateHash**|xs:string|Especifica el hash SHA1 del certificado de cliente que se debe usar en la negociación de la Capa de sockets seguros (SSL).<br /><br /> En función de este hash, el certificado de cliente se toma del almacén personal de la cuenta de usuario bajo la que se ejecuta la instancia de host de BizTalk.|  
  
## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de FTP](../core/configuring-the-ftp-adapter.md)
 
 [Procedimientos recomendados y recomendaciones para el adaptador de FTP](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)
 
 [Adaptador de FTP](../core/ftp-adapter.md)