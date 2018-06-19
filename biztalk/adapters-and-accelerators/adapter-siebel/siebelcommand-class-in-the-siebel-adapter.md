---
title: Clase SiebelCommand en el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelCommand
- Data Provider for Siebel, SiebelCommand
- SiebelCommand, supported methods and properties
ms.assetid: 7cba0e47-634b-4878-b480-80fbcbbf5c90
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d268e9a1d5954d703d392070a53c84bd9cee0d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222364"
---
# <a name="siebelcommand-class-in-the-siebel-adapter"></a>Clase SiebelCommand en el adaptador de Siebel
Después de establecer una conexión con el sistema Siebel, el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] analiza las cadenas de comandos de Siebel y parámetros de los comandos proporcionados por el cliente ADO.NET y asigna el comando en un mensaje de solicitud WCF. El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] , a continuación, envía la solicitud a la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y obtiene la respuesta XML y el contenido del cuerpo del adaptador. El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] , a continuación, utiliza el `XMLDataReader` para recuperar los datos relacionales desde el cuerpo XML.  
  
 Mediante una instancia de `Microsoft.Data.SiebelClient.SiebelClientFactory`, un programa cliente puede obtener una instancia de la `System.Data.Common.DbCommand` clase para construir un comando de Siebel.  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbCommand command = factory.CreateCommand();  
```  
  
 También se puede usar el siguiente método para crear un comando:  
  
```  
//Here connection is an instance of SiebelConnection  
SiebelCommand cmd = (SiebelCommand) connection.CreateCommand();  
cmd.CommandText = "SELECT [Name] as MyName, [City], [Country]  from Account.Account WHERE Name LIKE '3Com*' OPTION 'ViewMode 1'";  
```  
  
 El `SiebelCommand` clase hereda de `DbCommand`.  Se encuentra en el espacio de nombres `Microsoft.Data.SiebelClient`.  
  
## <a name="supported-properties"></a>Propiedades admitidas  
 El **SiebelCommand** clase admite las siguientes `DbCommand` *protegido* propiedades:  
  
|Nombre|Get/Set.|Description|  
|----------|--------------|-----------------|  
|**DbConnection**|Get y Set|Este archivo debe contener subyacente `DbConnection` instancia a partir del cual `DbCommand` se obtiene la instancia.|  
|**DbParameterCollection**|Obtener|Obtiene la colección de `DbParameter` objetos.|  
  
 `SiebelCommand`también admite las siguientes `DbCommand` *público* propiedades:  
  
|Nombre|Get/Set.|Description|  
|----------|--------------|-----------------|  
|**CommandText**|Get y Set|Esto contiene la instrucción SQL que desea ejecutar el cliente ADO.NET.|  
|**CommandType**|Get y Set|Sólo `CommandType.Text` se admite.|  
|**Conexión**|Get y Set|Esto utiliza el `DbConnection` miembro.|  
|**Parámetros**|Obtener|Esto utiliza el `DbParameterCollection` miembro.|  
  
> [!IMPORTANT]
>  El `SiebelCommand` clase omite el `CommandTimeout`, `DesignTimeVisible`, y `DbTransaction` propiedades.  
  
## <a name="supported-methods"></a>Métodos admitidos  
 El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] admite las siguientes `DbCommand` *protegido* métodos:  
  
|Nombre|Description|  
|----------|-----------------|  
|**CreateDbParameter**|Crea un nuevo `DbParameter` instancia.|  
|**ExecuteDbDataReader**|Esto ejecuta los comandos SELECT y EXEC y devuelve un `DbDataReader`.|  
  
 `SiebelCommand`también admite las siguientes `DbCommand` *público* métodos:  
  
|Nombre|Description|  
|----------|-----------------|  
|**CreateParameter**|Crea un nuevo `DbParameter` a través de la instancia`CreateDbParameter().`|  
|**ExecuteReader**|Ejecuta `CommandText` contra la `Connection` y devuelve `DbDataReader` a través de `ExecuteDbDataReader()`.|  
|**Preparar**|Este código analiza la `CommandText` y compila el árbol de análisis de comando SQL.|  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)