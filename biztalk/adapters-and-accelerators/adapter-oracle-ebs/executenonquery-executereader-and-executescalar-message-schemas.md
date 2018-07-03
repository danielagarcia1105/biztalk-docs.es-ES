---
title: Los esquemas de mensajes para el ExecuteNonQuery, ExecuteReader y ExecuteScalar Operations1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aa5fdb2-1e7f-4a34-a1e5-c16d8fb477d5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7078fed7a007eca4dfb3eb5608eb6e688bb74a45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011973"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a>Esquemas de mensaje para el ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones
La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone las operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar de salida en el nivel raíz para ejecutar bloques de PL/SQL ni instrucciones SQL arbitrarias en Oracle E-Business Suite.  
  
 Para obtener más información acerca de:  
  
- Estas operaciones, consulte [compatibilidad con ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
- Realizar estas operaciones mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [ExecuteReader, ExecuteScalar o ExecuteNonQuery operaciones en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a>Estructura de mensaje para el ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones  
 Los mensajes en estas operaciones siguen un patrón de intercambio de mensajes de solicitud y respuesta, y en la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.  
  
> [!NOTE]
>  Después de la tabla, vea las descripciones de entidad.  
  
|Operación|Mensaje XML|  
|---------------|-----------------|  
|Solicitud ExecuteNonQuery|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQuery xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query>   <OutputRefCursorNames>     <string>[stringvalue1]</string>     <string>[stringvalue2]</string>     …   </OutputRefCursorNames> </ExecuteNonQuery>`|  
|Respuesta ExecuteNonQuery|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult>   <OutputRefCursors>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </OutputRefCursors> </ExecuteNonQueryResponse>`|  
|Solicitud ExecuteReader|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteReader>`|  
|Respuesta ExecuteReader|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteReaderResult>     <Any>[value]</Any>     <Any>[value]</Any>       …   </ExecuteReaderResult> </ExecuteReaderResponse>`|  
|Solicitud ExecuteScalar|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalar xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteScalar>`|  
|Respuesta ExecuteScalar|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|  
  
 Descripciones de entidad:  
  
 [Bloque PL/SQL] = todo el bloque de PL/SQL que se ejecutará.  
  
 [stringvalue1] = un valor de la matriz de cadenas.  
  
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