---
title: Esquemas de mensajes de ExecuteNonQuery, ExecuteReader y ExecuteScalar Operations1 | Documentos de Microsoft
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
ms.openlocfilehash: b42ed9075ad16708f835786fd1fd09b414d06ebb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216156"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a>Esquemas de mensaje para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery
La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone las operaciones de salida ExecuteNonQuery y ExecuteReader, ExecuteScalar en el nivel de raíz para ejecutar las instrucciones SQL arbitrarias o bloques de PL/SQL de Oracle E-Business Suite.  
  
 Para obtener más información acerca de:  
  
-   Estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
-   Realizar estas operaciones mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [ExecuteReader, ExecuteScalar u operaciones de ExecuteNonQuery en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a>Estructura de los mensajes de ExecuteNonQuery, ExecuteReader y operaciones ExecuteScalar  
 Los mensajes en estas operaciones siguen un patrón de intercambio de mensajes de solicitud y respuesta, y en la tabla siguiente muestra la estructura de estos mensajes de solicitud y respuesta.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|Operación|Mensaje XML|  
|---------------|-----------------|  
|ExecuteNonQuery solicitud|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQuery xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query>   <OutputRefCursorNames>     <string>[stringvalue1]</string>     <string>[stringvalue2]</string>     …   </OutputRefCursorNames> </ExecuteNonQuery>`|  
|ExecuteNonQuery respuesta|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult>   <OutputRefCursors>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </OutputRefCursors> </ExecuteNonQueryResponse>`|  
|Solicitud de ExecuteReader|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteReader>`|  
|Respuesta de ExecuteReader|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteReaderResult>     <Any>[value]</Any>     <Any>[value]</Any>       …   </ExecuteReaderResult> </ExecuteReaderResponse>`|  
|Solicitud de ExecuteScalar|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalar xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteScalar>`|  
|Respuesta de ExecuteScalar|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|  
  
 Descripciones de entidad:  
  
 [Bloque PL/SQL] = todo el bloque de PL/SQL que se ejecutará.  
  
 [stringvalue1] = un valor de la matriz de cadenas.  
  
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