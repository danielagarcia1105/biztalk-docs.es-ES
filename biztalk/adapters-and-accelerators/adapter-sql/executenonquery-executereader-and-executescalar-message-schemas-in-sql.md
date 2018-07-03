---
title: Los esquemas de mensajes para el ExecuteNonQuery, ExecuteReader y ExecuteScalar Operations2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f8cb98-8da8-40c1-bf87-4aad5a24bba2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ede2d471ce935d11286c49cc7cfb53c0e7ea9d92
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001429"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a>Esquemas de mensaje para el ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones
La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone las operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar de salida en el nivel raíz para ejecutar cualquier instrucción SQL arbitraria en SQL Server.  
  
 Para obtener más información acerca de:  
  
- Estas operaciones, consulte [compatibilidad con ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
- Realizar estas operaciones mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [ExecuteReader, ExecuteScalar o ExecuteNonQuery operaciones en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a>Estructura de mensaje para el ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones  
 Los mensajes en estas operaciones siguen un patrón de intercambio de mensajes de solicitud y respuesta, y en la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.  
  
|Operación|Mensaje XML|Descripción|  
|---------------|-----------------|-----------------|  
|Solicitud ExecuteNonQuery|`<ExecuteNonQuery xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">    <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query>  </ExecuteNonQuery>`|Dentro de la `<Query>` etiqueta, puede especificar varias instrucciones de PL/SQL separadas por puntos y coma.|  
|Respuesta ExecuteNonQuery|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult> </ExecuteNonQueryResponse>`|Para las instrucciones UPDATE, INSERT y DELETE, `[value]` representa el número de filas afectadas por las instrucciones de PL/SQL en el *ExecuteNonQuery solicitud* mensaje. Para los demás tipos de instrucciones, `[value]` es -1.|  
|Solicitud ExecuteReader|`<ExecuteReader xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query> </ExecuteReader>`|Dentro de la `<Query>` etiqueta, puede especificar varias instrucciones de PL/SQL separadas por puntos y coma.|  
|Respuesta ExecuteReader|`<?xml version="1.0" encoding="utf-8" ?>  <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteReaderResult>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </ExecuteReaderResult> </ExecuteReaderResponse>`|El conjunto de resultados es el mensaje de respuesta de las instrucciones de PL/SQL que se ejecuta en el *ExecuteReader solicitud* del mensaje y se devuelve como una matriz de conjunto de datos. Para obtener información sobre el conjunto de datos, vea "Clase de conjunto de datos" en [ http://go.microsoft.com/fwlink/?LinkID=196853 ](http://go.microsoft.com/fwlink/?LinkID=196853).|  
|Solicitud ExecuteScalar|`<ExecuteScalar xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query> </ExecuteScalar>`|Dentro de la `<Query>` etiqueta, puede especificar varias instrucciones de PL/SQL separadas por puntos y coma.|  
|Respuesta ExecuteScalar|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|El `[value]` representa el valor de la primera columna de la primera fila del conjunto de resultados devuelto por las instrucciones de PL/SQL en el *ExecuteScalar solicitud* mensaje.|  
  
 [PL/SQL, instrucción] = toda la instrucción de PL/SQL que se ejecutará.  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a>Acción de mensaje para el ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones  
 La siguiente tabla muestra las acciones de mensaje usados por las operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar.  
  
|Operación|Acción|  
|---------------|------------|  
|Solicitud ExecuteNonQuery|GenericOp/ExecuteNonQuery|  
|Respuesta ExecuteNonQuery|GenericOp/ExecuteNonQuery/respuesta|  
|Solicitud ExecuteReader|GenericOp/ExecuteReader|  
|Respuesta ExecuteReader|GenericOp/ExecuteReader/respuesta|  
|Solicitud ExecuteScalar|GenericOp/ExecuteScalar|  
|Respuesta ExecuteScalar|GenericOp/ExecuteScalar/respuesta|  
  
## <a name="see-also"></a>Vea también  
 [Los mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)