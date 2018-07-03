---
title: Clase DbDataReader del adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, DbDataReader
- DbDataReader
ms.assetid: 7673cd10-ec1e-4cb0-93c2-f11928d00ca2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ad584571f7ef746a43032935e42e377ceb6cd70
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012621"
---
# <a name="dbdatareader-class-in-the-siebel-adapter"></a>Clase DbDataReader del adaptador de Siebel
El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] proporciona un `DbDataReader` aprovechando el lector de datos XML. Esto permite al consumidor del origen de datos de Siebel para leer una secuencia de sólo avance de filas.  

## <a name="supported-properties"></a>Propiedades admitidas  
 El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] admite las siguientes `DbDataReader` propiedades.  

|Nombre|Get/Set.|Descripción|  
|----------|--------------|-----------------|  
|**HasRows**|Obtener|Esta propiedad no se admite e iniciará una excepción si tiene acceso.|  
|**IsClosed**|Obtener|Obtiene un valor que indica si el `DbDataReader` está cerrado.|  
|**RecordsAffected**|Obtener|Obtiene un valor que indica si el `DbDataReader` contiene una o varias filas.|  
|**Item (Int32)**|Obtener|Obtiene el valor de la columna especificada como una instancia del objeto. Use el número ordinal de la columna que desee al invocar este indizador.|  
|**Item (String)**|Obtener|Obtiene el valor de la columna especificada como una instancia del objeto. Use el nombre de la columna que desee al invocar este indizador.|  

## <a name="supported-methods"></a>Métodos admitidos  
 El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] admite las siguientes `DbDataReader` métodos.  


|        Nombre        |                                                                                                                                                                                                                            Descripción                                                                                                                                                                                                                             |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **GetSchemaTable** | Devuelve un valor `DataTable` que describe los metadatos de la columna de `DbDataReader`. Los atributos de columna de esquema admitidos por el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] son:<br /><br /> : ColumnName<br />-ColumnOrdinal<br />Tipo de datos. NET<br />-Longitud<br />-Precisión (si está disponible)<br />-Escalado (si está disponible)<br />-AllowDBNull<br />-LocalName<br />-LocalName extendido<br />-Namespace |
|   **GetString**    |                                                                                                                                                                                                 Obtiene el valor de la columna especificada como instancia de `String`.                                                                                                                                                                                                 |
|    **GetValue**    |                                                                                                                                                                                                 Obtiene el valor de la columna especificada como instancia de `String`.                                                                                                                                                                                                 |
|    **isDbNull**    |                                                                                                                                                                                       Obtiene un valor que indica si la columna contiene valores inexistentes o ausentes.                                                                                                                                                                                       |
|   **NextResult**   |                                                                                                                                                           El proveedor de datos de Siebel siempre devuelve un conjunto de resultados único; por lo tanto, esta llamada agota completamente el conjunto antes de la devolución de resultados actual **false**.                                                                                                                                                           |
|      **Lectura**      |                                                                                                                                                         Avanza el lector al registro siguiente en un conjunto de resultados.  Devuelve **true** si se realiza correctamente, y **false** si el lector no tiene más registros izquierda.                                                                                                                                                         |
|     **Cerrar**      |                                                                                                         Cierra el `DbDataReader` objeto. **Precaución:** cuando haya terminado con el `DbDataReader` de objeto, debe cerrarlo, con el fin de liberar los objetos de biblioteca COM de Siebel. En caso contrario, pasará uso de memoria y el identificador de la aplicación cliente.                                                                                                          |

## <a name="see-also"></a>Vea también  
 [Ampliar Interfaces de ADO.NET con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)