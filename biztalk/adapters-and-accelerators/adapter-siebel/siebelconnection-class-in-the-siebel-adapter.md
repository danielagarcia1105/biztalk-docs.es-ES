---
title: Clase SiebelConnection en el adaptador de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, SiebelConnection
- SiebelConnection, supported properties and methods
- SiebelConnection
ms.assetid: 661d9876-4c14-4748-b05f-cc4fd1c4ebcf
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fc99c2e3f019f2ddf88647b0faeb7e41644fd0e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="siebelconnection-class-in-the-siebel-adapter"></a>Clase SiebelConnection en el adaptador de Siebel
El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] tiene acceso a subyacente [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] `Binding`, `ConnectionFactory`, y `Channel` para conectarse al sistema Siebel. El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] implementa el `DbConnection` características de la clase para admitir los anteriores.  
  
 Mediante una instancia de `Microsoft.Data.SiebelClient.SiebelClientFactory`, un programa cliente puede obtener una instancia de la `System.Data.Common.DbConnection` clase para conectarse al sistema Siebel.  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbConnection connection = factory.CreateConnection();  
```  
  
 También se puede usar el siguiente método para crear una conexión:  
  
```  
  
SiebelConnection connection = new SiebelConnection();  
connection.ConnectionString = connectionString;  
```  
  
 El `SiebelConnection` clase hereda de `DbConnection`. Se encuentra en el espacio de nombres `Microsoft.Data.SiebelClient`.  
  
## <a name="supported-properties"></a>Propiedades admitidas  
 El `SiebelConnection` clase admite las siguientes `DbConnection` propiedades.  
  
|Nombre|Get/Set.|Description|  
|----------|--------------|-----------------|  
|**ConnectionString**|Get y Set|Obtiene o establece la cadena que se usa para abrir la conexión.|  
|**Base de datos**|Obtener|Obtiene el nombre de la base de datos actual una vez que se abre una conexión o el nombre de base de datos especificado en la cadena de conexión antes de abrirse la conexión. Debe ser el nombre del repositorio de Siebel.|  
|**DataSource**|Obtener|Obtiene el nombre de la puerta de enlace de Siebel para esta conexión.|  
|**ServerVersion**|Obtener|En la versión actual de [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], esta propiedad devuelve un valor codificado de forma rígida, que no representa la versión real del servidor Siebel.|  
|**State**|Obtener|Obtiene una cadena que describe el estado de la conexión. Este archivo puede contener tres valores posibles: abierto, ROTO o cerrado.|  
  
## <a name="supported-methods"></a>Métodos admitidos  
 El `SiebelConnection` clase admite las siguientes `DbConnection` métodos.  
  
|Nombre|Description|  
|----------|-----------------|  
|**CreateDbCommand**|Este método protegido proporciona una nueva instancia de DbCommand.|  
|**ChangeDatabase**|Este método público no se admite e iniciará una excepción si se llama.|  
|**Abrir**|Abre una conexión con el sistema Siebel mediante la creación de un canal WCF.|  
|**Cerrar**|Cierra una conexión con el sistema Siebel, el cierre de un canal WCF.|  
|**CreateCommand**|Crea un objeto de comando.|  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)