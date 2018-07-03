---
title: Las propiedades de proveedor de datos de la cadena de conexión de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- conncting, to the Siebel system
- Data Provider for Siebel, connection string
ms.assetid: 8ab0c29e-e06b-4e74-be4e-9aa862a05539
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0954cbec3c2dbd044037cc817a8ef97b1250bf8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988829"
---
# <a name="data-provider-properties-for-the-siebel-connection-string"></a>Propiedades de proveedor de datos de la cadena de conexión de Siebel
El [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) usa el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para tener acceso al sistema Siebel. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a su vez usa la biblioteca de controles de datos de Siebel COM para tener acceso al sistema Siebel. El Control de datos de Siebel COM está equipado con el cliente Siebel Web.  

 Para establecer la conectividad a un sistema de Siebel, los clientes de ADO.NET deben especificar las propiedades de conexión de Siebel se codifican en una cadena de conexión de base de datos. Esto es necesario porque el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] implementa **DbConnection** para tener acceso a subyacente [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace.  

 La cadena de conexión para conectarse a un sistema de Siebel mediante el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] contiene las siguientes propiedades.  


|        Property        |                                                                                                                                                     Descripción                                                                                                                                                      |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        Contraseña        |            La contraseña del usuario en el sistema Siebel; Este valor distingue mayúsculas de minúsculas. **Nota:** el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] conserva el caso del valor que escriba la contraseña cuando se abre una conexión en el sistema Siebel.             |
|        Nombre de usuario        |                  El nombre de usuario en el sistema Siebel; Este valor distingue mayúsculas de minúsculas. **Nota:** el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] conserva el caso del valor que especifique para el nombre de usuario cuando se abre una conexión en el sistema Siebel.                  |
|      Compresión       |      El algoritmo de compresión debe utilizar entre el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] y el sistema Siebel. Los valores admitidos son **ninguno** o **zlib**. Este parámetro es opcional. Si no se especifica, el sistema Siebel proporciona un valor predeterminado (**zlib**).       |
|       Cifrado       | El tipo de cifrado debe utilizar entre el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] y el sistema Siebel. Los valores admitidos son **ninguno**, **mscrypto**, o **rsa**. Este parámetro es opcional. Si no se especifica, el sistema Siebel proporciona un valor predeterminado (**ninguno**). |
|        Idioma        |                                                                                                             El idioma del Administrador de objetos. Un valor de ejemplo es **ESN**. Este parámetro es obligatorio.                                                                                                             |
| SiebelEnterpriseServer |                                                                                                                        El nombre del servidor de empresa de Siebel. Este parámetro es obligatorio.                                                                                                                         |
|     SiebelGateway      |                                                                                                                     Consta de la dirección IP del servidor Siebel y el puerto. Por ejemplo, Siebel_Server:1234.                                                                                                                      |
|  SiebelObjectManager   |                                                                                                             El nombre del Administrador de objetos Siebel del servidor de empresa. Este parámetro es obligatorio.                                                                                                              |
|    SiebelRepository    |                                     El repositorio de Siebel. Necesario si existe más de un repositorio en el servidor. en caso contrario, es opcional. **Nota:** si existe más de un repositorio en el servidor, debe especificar un repositorio de destino en el parámetro SiebelRepository.                                      |
|      SiebelServer      |                                                                                                       El servidor de Siebel. Necesario para todas las conexiones de servidor Siebel 7.5; en caso contrario, no establezca este parámetro.                                                                                                       |
|       Transporte        |                                                                               El transporte; solo **tcpip** se admite. Este parámetro es opcional. Si no se especifica, el sistema Siebel proporciona un valor predeterminado (**tcpip**).                                                                                |

 Por ejemplo:  

```  
Username=YourUserName;Password=YourPassword;SiebelGateway=Siebel_Server:1234;SiebelObjectManager=obj_mgr;SiebelEnterpriseServer=ent_server;Language=enu;SiebelRepository=siebel_rep  
```  

## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos de .NET Framework para aplicaciones de negocio electrónico de Siebel](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)