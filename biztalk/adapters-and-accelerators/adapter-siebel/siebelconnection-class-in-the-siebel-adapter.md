---
title: Clase SiebelConnection del adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, SiebelConnection
- SiebelConnection, supported properties and methods
- SiebelConnection
ms.assetid: 661d9876-4c14-4748-b05f-cc4fd1c4ebcf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dd9e4bbf08d73c8fa48113aad1ecf12fdf0f237
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001989"
---
# <a name="siebelconnection-class-in-the-siebel-adapter"></a>Clase SiebelConnection del adaptador de Siebel
El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] tiene acceso a subyacente [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] `Binding`, `ConnectionFactory`, y `Channel` para conectarse al sistema Siebel. El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] implementa el `DbConnection` características de clase para admitir la anterior.  

 Mediante una instancia de `Microsoft.Data.SiebelClient.SiebelClientFactory`, un programa cliente puede obtener una instancia de la `System.Data.Common.DbConnection` clase para conectarse al sistema Siebel.  

```  
//In this example, factory is an instance of SiebelClientFactory  
DbConnection connection = factory.CreateConnection();  
```  

 Como alternativa, el enfoque siguiente puede utilizarse para crear una conexión:  

```  

SiebelConnection connection = new SiebelConnection();  
connection.ConnectionString = connectionString;  
```  

 El `SiebelConnection` clase hereda de `DbConnection`. Existe en el espacio de nombres `Microsoft.Data.SiebelClient`.  

## <a name="supported-properties"></a>Propiedades admitidas  
 El `SiebelConnection` clase admite las siguientes `DbConnection` propiedades.  


|         Nombre         |   Get/Set.   |                                                                                                      Descripción                                                                                                       |
|----------------------|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **ConnectionString** | Get y Set. |                                                                                  Obtiene o establece la cadena que se usa para abrir la conexión.                                                                                  |
|     **Base de datos**     |     Obtener     |        Obtiene el nombre de la base de datos actual una vez abierta una conexión o el nombre de base de datos especificado en la cadena de conexión antes de abrirse la conexión. Debe ser el nombre del repositorio de Siebel.         |
|    **DataSource**    |     Obtener     |                                                                                Obtiene el nombre de la puerta de enlace de Siebel para esta conexión.                                                                                |
|  **ServerVersion**   |     Obtener     | En la versión actual de [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], esta propiedad devuelve un valor codificado de forma rígida, que no representa la versión real del servidor Siebel. |
|      **State**       |     Obtener     |                                               Obtiene una cadena que describe el estado de la conexión. Este archivo puede contener tres valores posibles: abierto, ROTO o cerrado.                                               |

## <a name="supported-methods"></a>Métodos admitidos  
 El `SiebelConnection` clase admite las siguientes `DbConnection` métodos.  

|Nombre|Descripción|  
|----------|-----------------|  
|**CreateDbCommand**|Este método protegido proporciona una nueva instancia de DbCommand.|  
|**ChangeDatabase**|Este método público no se admite y producirá una excepción si se llama.|  
|**Abrir**|Abre una conexión con el sistema Siebel mediante la creación de un canal de WCF.|  
|**Cerrar**|Cierra una conexión con el sistema de Siebel al cerrar un canal de WCF.|  
|**CreateCommand**|Crea un objeto de comando.|  

## <a name="see-also"></a>Vea también  
 [Ampliar Interfaces de ADO.NET con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)