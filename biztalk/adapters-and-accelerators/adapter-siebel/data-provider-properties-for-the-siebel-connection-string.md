---
title: "Propiedades de proveedor de datos de la cadena de conexión de Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- conncting, to the Siebel system
- Data Provider for Siebel, connection string
ms.assetid: 8ab0c29e-e06b-4e74-be4e-9aa862a05539
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1caedbc1e9560c1bc4d97669241046f0959c2db6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-provider-properties-for-the-siebel-connection-string"></a>Propiedades de proveedor de datos de la cadena de conexión de Siebel
El [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) utiliza el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para tener acceso al sistema Siebel. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a su vez usa la biblioteca de controles de datos de Siebel COM para tener acceso al sistema Siebel. El Control de datos de Siebel COM viene incluido con el cliente Siebel Web.  
  
 Para establecer la conexión con un sistema Siebel, los clientes ADO.NET deben especificar las propiedades de conexión de Siebel se codifican en una cadena de conexión de base de datos. Esto es necesario porque el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] implementa **DbConnection** para tener acceso a subyacente [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace.  
  
 La cadena de conexión para conectarse a un sistema Siebel mediante el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] contiene las siguientes propiedades.  
  
|Propiedad|Description|  
|--------------|-----------------|  
|Contraseña|La contraseña para el usuario en el sistema Siebel; Este valor distingue mayúsculas de minúsculas. **Nota:** el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] conserva el caso del valor que especifique para la contraseña cuando se abre una conexión en el sistema Siebel.|  
|Nombre de usuario|El nombre de usuario en el sistema Siebel; Este valor distingue mayúsculas de minúsculas. **Nota:** el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] conserva el caso del valor que especifique para el nombre de usuario cuando se abre una conexión en el sistema Siebel.|  
|Compresión|El algoritmo de compresión utilizado entre el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] y el sistema Siebel. Los valores admitidos son **ninguno** o **zlib**. Este parámetro es opcional. Si no se especifica, el sistema Siebel proporciona un valor predeterminado (**zlib**).|  
|Cifrado|El tipo de cifrado utilizado entre el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] y el sistema Siebel. Los valores admitidos son **ninguno**, **mscrypto**, o **rsa**. Este parámetro es opcional. Si no se especifica, el sistema Siebel proporciona un valor predeterminado (**ninguno**).|  
|Lenguaje|El idioma del Administrador de objetos. Un valor de ejemplo es **enu**. Este parámetro es obligatorio.|  
|SiebelEnterpriseServer|El nombre del servidor de empresa de Siebel. Este parámetro es obligatorio.|  
|SiebelGateway|Consta de la dirección IP del servidor Siebel y puerto. Por ejemplo, Siebel_Server:1234.|  
|SiebelObjectManager|Nombre del Administrador de objetos de Siebel en el servidor de empresa. Este parámetro es obligatorio.|  
|SiebelRepository|El repositorio de Siebel. Necesario si existe más de un repositorio en el servidor; en caso contrario, es opcional. **Nota:** si existe más de un repositorio en el servidor, debe especificar un repositorio de destino en el parámetro SiebelRepository.|  
|SiebelServer|El servidor de Siebel. Necesario para todas las conexiones de servidor Siebel 7.5; en caso contrario, no se establece este parámetro.|  
|Transporte|El transporte; solo **TCP/IP** se admite. Este parámetro es opcional. Si no se especifica, el sistema Siebel proporciona un valor predeterminado (**tcpip**).|  
  
 Por ejemplo:  
  
```  
Username=YourUserName;Password=YourPassword;SiebelGateway=Siebel_Server:1234;SiebelObjectManager=obj_mgr;SiebelEnterpriseServer=ent_server;Language=enu;SiebelRepository=siebel_rep  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)