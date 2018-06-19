---
title: Esquemas de mensajes de ExecuteNonQuery, ExecuteReader y ExecuteScalar Operations2 | Documentos de Microsoft
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
ms.openlocfilehash: 0aaef682ad0528e8d22e043da94dc31e4f723f24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222476"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a>Esquemas de mensaje para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery
La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone las operaciones de salida ExecuteNonQuery y ExecuteReader, ExecuteScalar en el nivel de raíz para ejecutar cualquier instrucción SQL arbitrario en SQL Server.  
  
 Para obtener más información acerca de:  
  
-   Estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
-   Realizar estas operaciones mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [ExecuteReader, ExecuteScalar u operaciones de ExecuteNonQuery en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a>Estructura de los mensajes de ExecuteNonQuery, ExecuteReader y operaciones ExecuteScalar  
 Los mensajes en estas operaciones siguen un patrón de intercambio de mensajes de solicitud y respuesta, y en la tabla siguiente muestra la estructura de estos mensajes de solicitud y respuesta.  
  
|Operación|Mensaje XML|Description|  
|---------------|-----------------|-----------------|  
|ExecuteNonQuery solicitud|`<ExecuteNonQuery xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">    <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query>  </ExecuteNonQuery>`|En la `<Query>` etiqueta, puede especificar varias instrucciones de PL/SQL separadas por punto y coma.|  
|ExecuteNonQuery respuesta|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult> </ExecuteNonQueryResponse>`|Para las instrucciones UPDATE, INSERT y DELETE, `[value]` representa el número de filas afectadas por las instrucciones de PL/SQL en el *ExecuteNonQuery solicitud* mensaje. Para los demás tipos de instrucciones, `[value]` es -1.|  
|Solicitud de ExecuteReader|`<ExecuteReader xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query> </ExecuteReader>`|En la `<Query>` etiqueta, puede especificar varias instrucciones de PL/SQL separadas por punto y coma.|  
|Respuesta de ExecuteReader|`<?xml version="1.0" encoding="utf-8" ?>  <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteReaderResult>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </ExecuteReaderResult> </ExecuteReaderResponse>`|El conjunto de resultados es el mensaje de respuesta de las instrucciones de PL/SQL ejecutadas en la *ExecuteReader solicitud* , el mensaje y se devuelve como una matriz de conjunto de datos. Para obtener información sobre el conjunto de datos, vea "Clase de conjunto de datos" en [http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853).|  
|Solicitud de ExecuteScalar|`<ExecuteScalar xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query> </ExecuteScalar>`|En la `<Query>` etiqueta, puede especificar varias instrucciones de PL/SQL separadas por punto y coma.|  
|Respuesta de ExecuteScalar|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|El `[value]` representa el valor de la primera columna de la primera fila del conjunto de resultados devuelto por las instrucciones de PL/SQL en el *ExecuteScalar solicitud* mensaje.|  
  
 [PL/SQL, instrucción] = toda la instrucción de PL/SQL que se ejecutará.  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a>Acción de mensaje para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery  
 La siguiente tabla muestra las acciones de mensaje que se utilizan en las operaciones ExecuteNonQuery y ExecuteReader, ExecuteScalar.  
  
|Operación|Acción|  
|---------------|------------|  
|ExecuteNonQuery solicitud|GenericOp/ExecuteNonQuery|  
|ExecuteNonQuery respuesta|GenericOp/ExecuteNonQuery/respuesta|  
|Solicitud de ExecuteReader|GenericOp/ExecuteReader|  
|Respuesta de ExecuteReader|GenericOp/ExecuteReader/respuesta|  
|Solicitud de ExecuteScalar|GenericOp/ExecuteScalar|  
|Respuesta de ExecuteScalar|GenericOp/ExecuteScalar/respuesta|  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)